> # Семенов Ф.С.
> ## ИСТ-822

# JavaScript. Контрольное задание №3
## Задание 1
Ввести данные в анкету, состоящую из текстовых полей формы и сформировать биографию по этим данным на отдельной странице.
### Выполнение задания
#### Скрипт программы
```html
<html>
<head>
    <meta charset="UTF-8">
    <style type="text/css">
        h1 {text-align:left;}
        body {background-color:mistyrose;}
        input {align: right;}
        label {float:left;}
    </style>
    <script>
        function create()
        {
            var pa_1=document.getElementById('pa_1');
            var pa_2=document.getElementById('pa_2');
            var pa_3=document.getElementById('pa_3');
            
            var signature = document.getElementById('signature').value;
            
            italic = "";
            underline = "";
            bold = "";
            
            if(bg_1.checked)
                url="Поле.jpg";
            if(bg_2.checked)
                url="Океан.jpg";
            if(bg_3.checked)
                url="Горы.jpg";
            if(sty_1.checked)
                italic="font-style: italic;";
            if(sty_2.checked)
                underline="text-decoration: underline; ";
            if(sty_3.checked)
                bold="font-weight:bold";

            signature_text = "<p>Сайт создал: " + signature + "<p>";
            
            body="<head><style type='text/css'>body {font-size: 20pt; color:white; background-image: url(" + url + "); background-size: cover;" + italic + underline + bold +";}</style></head>";

            if(pa_1.selected){
                label="<label>Хаим Сутин</label><br><br>";
                img2="'Хаим_Сутин.jpg'";}
            if(pa_2.selected){
                label="<label>Морис Утрилло</label><br><br>";
                img2="'Морис_Утрилло.jpg'";}
            if(pa_3.selected){
                label="<label>Каземир Малевич</label><br><br>";
                img2="'Каземир_Малевич.jpg'";}
            img1="<img src=";
            img3=" width=280,height=400/>";
            img=img1+img2+img3;
            var win=window.open("","","width=500,height=600");
            win.document.open();
            win.document.write(body);
            win.document.write(label);
            win.document.write(img);
            win.document.write(signature_text);
        }
    </script>
</head>
    
<body>
    <h1>Страничка по заказу</h1>
    <label>Художник: </label><br>
    <select>
        <option id='pa_1'>Хаим Сутин</option>
        <option id='pa_2'>Морис Утрилло</option>
        <option id='pa_3'>Каземир Малевич</option>
    </select>
    <p><label>Подпись:</label><br>
    <input type=text id='signature' size="50"></p>
    <label>Картинка для фона </label><br>
        <input type='radio' id='bg_1' name='bg' checked> Поле<br>
        <input type='radio' id='bg_2' name='bg'> Океан<br>
        <input type='radio' id='bg_3' name='bg'> Горы<br><br>
    <label>Декорирование текста:</label><br>
    <form>
        <input type="checkbox" id="sty_1"> Курсив <br>
        <input type="checkbox" id="sty_2"> Подчёркивание<br>
        <input type="checkbox" id="sty_3"> Жирный<br>
    </form>
    <input type=button value="Сброс" OnClick="window.location.reload()">
    <input type=button value="Показать" OnClick="create()">
</body>
</html>

```
#### Изображения
![image](/images/JS4_1_1.png)
![image](/images/JS4_1_2.png)
![image](/images/JS4_1_3.png)
![image](/images/JS4_1_4.png)
