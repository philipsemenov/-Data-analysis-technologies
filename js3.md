> # Семенов Ф.С.
> ## ИСТ-822

# JavaScript. Контрольное задание №3
## Задание 1
Создать HTML-страницу, которая при загрузке запрашивает дату вашего рождения и выводит на страницу день недели, число, месяц и год этой даты. Для месяцев и дней недели организовать массивы.
### Выполнение задания
#### Скрипт программы
``` html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
</head>
<body>
    <h2>
        <script>
            var months_list = new Array('января', 'февраля', 'марта', 'апреля', 'мая', 'июня', 'июля', 'августа', 'сентября','октября', 'ноября', 'декабря')
            var days_list=new Array('понедельник', 'вторник', 'среду', 'четверг','пятницу','субботу','воскресенье')
        
            var user_year = prompt("Введите год вашего рождения");
            var user_month = prompt("Ведите номер месяца вашего рождения");
            var user_day = prompt("Ведите день вашего рождения");
            user_date=new Date(user_year, user_month, user_day).getDay()
            document.write("Я родилися " + user_day + " " + months_list[user_month - 1] + " " + user_year + " года, " + days_list[user_date - 1]);
        </script>
    </h2>
</body>
</html>
```
#### Изображения
![image](/images/JS2_1_1.png)
![image](/images/JS2_1_2.png)
![image](/images/JS2_1_3.png)
![image](/images/JS2_1_4.png)

## Задание 2
Создать HTML-страницу, которая при загрузке выводит в текстовое поле формы, сколько дней осталось до каникул.
### Выполнение задания
#### Скрипт программы
``` html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <script>
        function get_date(){
            document.getElementById('insert_date').value=Math.floor((new Date(2021,6,27).getTime() - new Date().getTime())/86400000 + 1);
        }
    </script>
</head>
<body onLoad="get_date()">
        <form>
            <h1>
                До каникул осталось <input type="text" id="insert_date" size="4"> дней
            </h1>
        </form>
    </body>
</html>
```
#### Изображения
![image](/images/JS2_2_1.png)

## Задание 3
Ввести длину и ширину прямоугольника в поля формы и определить площадь этого прямоугольника. Площадь должна вычисляться по нажатию кнопки.
### Выполнение задания
#### Скрипт программы
``` html
<!DOCTYPE html>
<html>
<head>
     <meta charset="utf-8" />
    <script>
        function sqr(){
            var l = document.getElementById('length');
            var w = document.getElementById('width');
            var size = l.value * w.value;
            
            alert("Площадь прямоугольника: " + size)
        }
    </script>
</head>
<body>
    Вычисление площади прямоугольника
    <form>
        Длина:
        <input type=text value="" id='length' size="5">
        Ширина:
        <input type=text value="" id='width' size="5">
        <input type=button value="Площадь" OnClick="sqr()">
        <hr>
</form>

</body>
</html>
```
#### Изображения
![image](/images/JS2_3_1.png)
![image](/images/JS2_3_2.png)
