> # Семенов Ф.С.
> ## ИСТ-822

# R. Контрольное задание №3
Создайте веб приложение Shiny с заголовком «Вэб юмор!», использующее на «Боковой панели» виджет «Числовой ввод». При вводе номера комикса приложение в «Основной панели» должно выводить соответствующий комикс с сайта: http://xkcd.com
## Задание 3
### Код задания:
```R
library ("RXKCD")
library(shiny)
ui <- fluidPage(
    titlePanel("Вэб юмор!"),
    sidebarLayout(
        sidebarPanel(
            numericInput("n", "Выбери номер смешной картинки!", floor(runif(1,1,1000)))),
        mainPanel(plotOutput("joke"))
    )
)
server <- function(input, output) {
    output$joke <- renderPlot({
        getXKCD(input$n)
    })
}
shinyApp(ui = ui, server = server)
```
![image](/images/R_3.png)