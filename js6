> # Семенов Ф.С.
> ## ИСТ-822

# JavaScript. Контрольное задание №6
## Задание 1
 В задании при наведении курсора мыши на названии животного, в ячейке таблицы появляется рисунок этого животного. При наведении курсора в сторону рисунок исчезает (то есть подставляется пустой рисунок empty-1.gif).
### Выполнение задания
#### Скрипт программы
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <style>
        td {font-size: 22px; padding: 5px 7px; border: 3px solid coral; height: 70px; cursor: pointer;}
        tr {height: 70px;}
        body {background-color: antiquewhite; color:cornflowerblue;}
        img {width: 100%; height: 340%;}
    </style>
</head>
<body>
    <h1>Наведи курсор на название животного</h1>
    <table style="width: 30%;">
        <tr>
            <td onMouseOver="doEvent(1)" onMouseOut="doEvent(0)">Леопард</td>
            <td rowspan="3"><img id='pic' src="question.jpg"></td>
        </tr>
        <tr>
            <td onMouseOver="doEvent(2)" onMouseOut="doEvent(0)">Свинка</td>
        </tr>
        <tr>
            <td onMouseOver="doEvent(3)" onMouseOut="doEvent(0)">Коала</td>
        </tr>
    </table>
</body>
<script>
    var pictures = new Array("question.jpg","leo.jpg", "pig.jpg", "coala.jpg");
    function doEvent(i) {
        var picture = document.getElementById('pic');
        picture.src = pictures[i];
    }
</script>
</html>
```
![image](/images/JS5_1_1.png)
![image](/images/JS5_1_2.png)
![image](/images/JS5_1_3.png)
![image](/images/JS5_1_4.png)

## Задание 2
 Организовать показ слайд-шоу из этих же картинок, чтобы каждая следующая картинка показывалась не автоматически, а при нажатии кнопки.
### Выполнение задания
#### Скрипт программы
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <style>
        body {background-color: antiquewhite; color:cornflowerblue;}
        img {width: auto; height: 200px;}
    </style>
</head>
<body>
    <h1> Слайд шоу зверей </h1>
    <img id='animal' src="coala.jpg"/><br>
    <input type="button" value="Следующее животное" onClick="animal_show()">
    <script>
    var n = 0;
    function animal_show() {
        pictures = new Array("leo.jpg", "pig.jpg", "coala.jpg");
        if (n >= 3)
            n = 0;
        picture = document.getElementById('animal')
        picture.src = pictures[n];
        n++;
    }
  </script>
</body>
</html>
```
![image](/images/JS5_2_1.png)
![image](/images/JS5_2_2.png)
![image](/images/JS5_2_3.png)
