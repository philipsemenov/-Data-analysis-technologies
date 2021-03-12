> # Семенов Ф.С.
> ## ИСТ-822

# PHP. Контрольное задание №1
## Задание 5
Составьте программу «Угадай число» для цикла по условию. На странице с формой пользователь вводит число и нажимает на кла-
вишу Enter. До тех пор пока пользователь не отгадает число, вызывается скрипт, который сначала выводит сообщение «Не отгадали», а затем снова вызывает файл с формой. Цикл не вызывается, если число отгадано. В процессе угадывания, так же как и ранее (задача 3), предусмотрите подсказки:загаданное число больше (или меньше).
### Выполнение задания
#### Скрипт программы
```php
<?php 
    session_set_cookie_params(0);
    session_start();
    if(!isset($_SESSION['number']))
        $_SESSION['number'] = rand(1,100);
?>

<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <style>
        h3{padding-bottom: 5px;margin: 0px;padding-top: 10px}
    </style>
</head>
<body>
    <h3>Угадай число</h3>
    <?php
    if ($_POST["guess"] == $_SESSION["number"])
        echo 'Вы угадали число!';
    else {
    ?>
    <form action="PHP3.php" method="POST">
        <input type="number" name="guess" min="1" max="100">
    </form>
    <?php
        if (!isset($_POST["guess"]))
            echo "Введите число от 1 до 100";
        else {
            if ($_POST["guess"] > $_SESSION["number"])
                echo 'Ваше число больше';
            else
                echo 'Ваше число меньше';
        }
        }
    ?>
</body>
</html>
```
![image](/images/PHP1_1.png)
![image](/images/PHP1_2.png)
![image](/images/PHP1_3.png)
![image](/images/PHP1_4.png)