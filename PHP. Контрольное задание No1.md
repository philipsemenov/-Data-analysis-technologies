> # Семенов Ф.С.
> ## ИСТ-822

# PHP. Контрольное задание №1
## Задание 18
В HTML-форме предусмотреть поле для ввода фамилии пользователя и список книг в виде checkbox. Пользователю предложить отметить те из них, которые он читал, и далее, используя php-скрипт, вывести их в виде отсортированного списка. Дополнительно предусмотреть в форме выпадающий список с этими же книгами, в котором пользователь указывает одну любимую. При выводе списка книг любимая должна быть выделена жирным шрифтом. 
### Выполнение задания
#### Скрипт программы
```PHP
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <style>
        body{background: no-repeat center/90% url(https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwallpapercave.com%2Fwp%2Fwp2213285.jpg&f=1&nofb=1); margin-left: 290px}
        h3{padding-bottom: 5px;margin: 0px;padding-top: 10px}
        h4{padding-bottom: 3px;margin: 0px;padding-top: 3px}
    </style>
</head>
<body>
    <h1>Список прочитанных книг</h1>
    <form action="PHP2.php" method="POST">
        <h3>Введите ваше ФИО:</h3>
        <input type="text" name="username_FIO" size="55">
        <h3>Выберете книги, которые вы читали:</h3>
        <h4>Иностранные книги</h4>
        <input type="checkbox" name="book[]" value="Библия">Библия<br>
        <input type="checkbox" name="book[]" value="Божественная комедия">Божественная комедия<br>
        <input type="checkbox" name="book[]" value="Так говорил заратустра">Так говорил заратустра<br>
        <input type="checkbox" name="book[]" value="Тошнота">Тошнота<br>
        <input type="checkbox" name="book[]" value="Симулякры и симуляции">Симулякры и симуляции
        <h4>Отечественные книги</h4>
        <input type="checkbox" name="book[]" value="Мастер и Маргарита">Мастер и Маргарита<br>
        <input type="checkbox" name="book[]" value="Муму">Муму<br>
        <input type="checkbox" name="book[]" value="Простоквашино">Простоквашино<br>
        <input type="checkbox" name="book[]" value="Биография Владимира Путина">Биография Владимира Путина<br>
        <input type="checkbox" name="book[]" value="Конституция">Конституция
        <h3>Выберете вашу любимую книгу:</h3>
        <select name="fav_book">
            <option>Библия</option>
            <option>Божественная комедия</option>
            <option>Так говорил заратустра</option>
            <option>Тошнота</option>
            <option>Симулякры и симуляции</option>
            <option>Мастер и Маргарита</option>
            <option>Муму</option>
            <option>Простоквашино</option>
            <option>Биография Владимира Путина</option>
            <option>Конституция</option>
        </select><br>
        <input type="submit" value="Сформировать список">
    </form>
    <?php
        sort($_POST['book'], SORT_STRING);
        $length = count($_POST['book']);
        $length--;
        $favbook = $_POST['fav_book'];
        if ($length > 1){
            echo "<h3>Книги, прочитаные <i> {$_POST['username_FIO']}</i>!</h3>";
        }
        for ($i = 0; $i <= $length ; $i++){
            if(strcasecmp($_POST['book'][$i], $favbook) == 0){
    ?>
                <b><?=$_POST['book'][$i]?></b><br>
    <?php
            }
            else{
    ?>
                <?=$_POST['book'][$i]?><br>
    <?php
                }
        }
    ?>
    </body>
</html>
```
![image](/images/PHP_2_1.png)
![image](/images/PHP_2_2.png)
![image](/images/PHP_2_3.png)