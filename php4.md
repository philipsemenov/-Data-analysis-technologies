> # Семенов Ф.С.
> ## ИСТ-822

# PHP. Контрольное задание №4
## Задание 28
Осуществить задачу перевода числа из одной системы счисления (СС) в другую. Дана пользовательская форма с тремя полями (число, из какой СС, в какую СС).
### Выполнение задания
#### Скрипт программы
```php
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <style>
        input{width: 30px}
        body{font-size: 20px}
        td {background-color: pink; text-align: center}
    </style>
</head>
<body>
    <h2>Перевод числа в другую систему счисления</h2>
    <i>Основания систем счисления должны быть между 2 и 36 (включительно)</i>
    <form action="PHP4.php" method="post">
        Число равное
        <input style="width: 70px;" type="text" name="number" value="<?php echo $_POST['number']; ?>"/>
        перевести из системы счисления с основанием
        <input type="number" min=0 max=36 name="coun_sys1" value="<?php echo $_POST['coun_sys1']; ?>"/>
        в систему счисления с основанием
        <input type="number" min=0 max=36  name="coun_sys2" value="<?php echo $_POST['coun_sys2']; ?>"/>
        <br>
        <input style="width: 150px; font-size: 100px" type="submit" value="Вычислить" name="count"/>

</form>
    <?php
    if (isset($_POST['count']) ) {
        echo "<table border='3px'> <tr> <td><b>", $_POST['coun_sys1'] ,"</b>ая система счисления </td>";
        echo "<td><b>", $_POST['coun_sys2'] ,"</b>ая система счисления </td></tr>";
        echo " <tr> <td>",$_POST['number'],"</td>";
        echo "<td>",base_convert($_POST['number'], $_POST['coun_sys1'], $_POST['coun_sys2']),"</td> </tr> </table>";
    }
    ?>
</body>
</html>
```
![image](/images/PHP4_1.png)
