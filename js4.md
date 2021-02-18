> # Семенов Ф.С.
> ## ИСТ-822

# JavaScript. Контрольное задание №5
## Задание 1
Ввести данные в анкету, состоящую из текстовых полей формы и сформировать биографию по этим данным на отдельной странице.
### Выполнение задания
#### Скрипт программы
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <style type="text/css">
        h1 {color:red;text-align:left;}
        body {background-color:palegoldenrod; font-weight:bold;}
        input {align: right;}
        .form_style {clear:both; text-align:right;}
        label {float:left;}
        .text_style {float:left}
    </style>
    <script>
        function bio(){
            var family_name = document.getElementById('family_name').value;
            var name = document.getElementById('name').value;
            var fathers_name = document.getElementById('fathers_name').value;
            var year = document.getElementById('year').value;
            var place = document.getElementById('place').value;
            var hobby = document.getElementById('hobby').value;
            var not_hobby = document.getElementById('not_hobby').value;
            
            var header="<h1>О себе</h1><hr> <p>Я, " + family_name + " " + name + " " + fathers_name + " родился в " + year + " году в городе " + place + "</p>";
            var hobby="<p>Больше всего я люблю " + hobby + " и очень не люблю " + not_hobby + ".<br> Было бы замечательно, всю жизнь только " + hobby + ", но к сожалению приходиться иногда и " + not_hobby + ".</p>";
            var win=window.open("","","width=400,height=500");
            var close ='<input type="button" value="закрыть"'+'onClick="window.close();">';
            win.document.open();
            win.document.write(header);
            win.document.write(hobby);
            win.document.write(close);
            win.document.close();
        }
    </script>
</head>
<body>
    <h1>Анкета</h1>
    <hr>
    <div class="text_style">
        <form class="form_style">
            <p> <label>Фамилия: </label><input type=text id='family_name' size="30"></p>
            <p><label>Имя: </label> <input type=text id='name' size="30"></p>
            <p><label>Отчество: </label> <input type=text  id='fathers_name' size="30"></p>
            <p><label>Год рождения: </label> <input type=text  id='year' size="30"></p>
            <p><label>Место рождения: </label><input type=text  id='place' size="30"></p>
            <p><label>Любимое занятие: </label> <input type=text  id='hobby' size="30"></p>
            <p><label>Нелюбимое занятие: </label> <input type=text  id='not_hobby'size="30"></p>
            <input type=button value="Сформировать биографию" OnClick="bio()"><hr>
        </form>
</div>
</body>
</html>
```
#### Изображения
![image](/images/JS3_1_1.png)
![image](/images/JS3_1_2.png)
