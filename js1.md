# Семенов Ф.С.                   ИСТ-822

# JavaScript. Контрольное задание №1
## Задание 1
Введите свою фамилию, имя и отчество. Запросите подтверждение. Если все верно, то вывести приветствие, если нет, вывести сообщение об ошибке.
### Выполнение задания
#### Скрипт программы
``` html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
</head>
<body>
    <script>
        let name = prompt("Введите свою фамилию:"),
            family_name = prompt("Введите свое имя:"),
            fathers_name = prompt("Введите свое отчество:");
        
        full_name = name + " " + family_name  + " " + fathers_name;
 
        var full_name_promt = confirm(full_name + "\nВсе верно?" );
        
        if (full_name_promt) alert("Молодец,\n" + full_name)
        else alert("Ошибка в данных");
    </script>
</body>
</html>
```

#### Ввод фамилии
![image](/images/JS1_1_1.png)

#### Ввод имени
![image](/images/JS1_1_2.png)

#### Ввод отчества
![image](/images/JS1_1_3.png)

#### Подтверждение правильности введенного ФИО
![image](/images/JS1_1_4.png)

#### Окно при вводе неверной информации 
![image](/images/JS1_1_5.png)

#### Окно при вводе верной информации 
![image](/images/JS1_1_6.png)

## Задание 2
Введите время в часах и минутах. Определите время, которое будет через минуту. Используйте вложенные операторы IF. Возможны три случая.
### Выполнение задания
#### Скрипт программы
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
</head>
<body>
    <script>
        hours = parseInt(prompt("Введите количество часов:","0"));
        minutes = parseInt(prompt("Введите количество минут:","0"));
        
        if (minutes < 59) {
            minutes += 1; 
        } else if (minutes == 59 && hours == 23) {
            hours = 0;
            minutes = 00;
        } else {
            hours += 1;
            minutes = 00;
        }
    
        alert("Через минуту время будет " + hours + ":" + minutes);
    </script>
</body>
</html>
```
#### Случай 1
![image](/images/JS1_2_1.png)
![image](/images/JS1_2_2.png)
![image](/images/JS1_2_3.png)
#### Случай 2
![image](/images/JS1_2_4.png)
![image](/images/JS1_2_5.png)
![image](/images/JS1_2_6.png)
#### Случай 3
![image](/images/JS1_2_7.png)
![image](/images/JS1_2_8.png)
![image](/images/JS1_2_9.png)


## Задание 3
### Выполнение задания
#### Скрипт программы
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
</head>
    <style>
        td.cell {width: 15px; height: 15px}
    </style>
<body>
    Квадрат 1
    <script>
        var side = 10
        document.write("<table>")
        for (let i = 0; i < side; i++) {
            document.write("<tr>")
            for (let k = 0; k <= i; k++) {
                document.write("<td class='cell' style='background: red'></td>")
            }
            for (let k = side - 1; k >= i + 1; k--) {
                document.write("<td class='cell' style='background: black'></td>")
            }
            document.write("</tr>")
        }
        document.write("</table>")

    </script>
    <br>Квадрат 2
    <script>
        var side = 10
        document.write("<table>")
        for (let i = 0; i < side; i++) {
            document.write("<tr>")
            for (let k = 0; k < side; k ++) {
                str = (i+k)%3
                if (str === 0 || str === 2) {
                    document.write("<td class='cell' style='background: purple'></td>")
                } else {
                    document.write("<td class='cell' style='background: silver'></td>")
                }
            }
            document.write("</tr>")
        }
        document.write("</table>")

    </script>
</body>    
</html>
```
#### Результат выполнения скрипта
![image](/images/JS1_3_1.png)
