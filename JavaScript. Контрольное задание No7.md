> # Семенов Ф.С.
> ## ИСТ-822

# JavaScript. Контрольное задание №7
## Задание 1
Создать документ, в котором блоковый элемент размерами 250 на 250 и заливкой красного цвета заключен в рамку темно-синего цвета типа inset и толщиной 10. По нажатию кнопки изменять цвет заливки на голубой и надпись на кнопке. При следующем нажатии изменять цвет заливки на красный надпись на кнопке.  
### Выполнение задания
#### Скрипт программы
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
</head>
    <style>
        .block_element {
            background: red;
            width: 250px;
            height: 250px;
            border: inset 10px darkblue;
        }
    </style>
<body>

<div class="block_element" id='block_element'> </div>
<form>
  <input type="button" id='button'  value="Измени цвет!" onClick="change_block()">
</form>
    <script>
        j=0;
        function change_block() {
            blk = document.getElementById('block_element')
            btn = document.getElementById('button')
            if (j == 0) {
                blk.style.background = 'lightblue';
                btn.value = 'Изменить на красный';
            j = 1;} else {
                blk.style.background = 'red';
                btn.value = 'Изменить на голубой';
                j=0
            }
        }
    </script>
</body>
</html>
```
#### Изображения
![image](/images/JS7_1_1.png)
![image](/images/JS7_1_2.png)

## Задание 2
Сначала на странице две картинки в рамках и две кнопки с надписью «спрячь меня». При нажатии на кнопку картинка прячется, и надпись на кнопке меняется на «покажи меня». Если еще раз нажать на кнопку, картинка появляется и меняется надпись на кнопке. Параметры форматирования страницы: 
- Цвет фона темно-синий. 
- Картинки размером 200 на 200.
- Рамка вокруг первой картинки: цвет #ffA089, тип outset, толщина 50, отступы по 5. 
- Рамка вокруг второй картинки: цвет # 89ffA0, тип outset, толщина 50, отступы по 5. 
### Выполнение задания
#### Скрипт программы
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <style>
        body {
            background: darkblue;
        }
        td {
            width: 300px;
        }
        img {
            width: 200px;
            height: 200px;
        }
        #sutin {
            padding: 5px;
            border: outset 50px #ffA089;
        }
        #pig {
            padding: 5px;
            border: outset 50px #89ffA0;
        }
    </style>
</head>
<body>
<table>
  <tr>
    <td>
      <img id="sutin" src="Хаим_Сутин.jpg">
    </td>
    <td>
      <img id="pig" src="pig.jpg">
    </td>
  </tr>
  <tr>
    <td align="center">
      <input type="button" id="sutin_btn"  value="Спрячь меня!" onClick="hide_sutin()">
    </td>
    <td align="center">
      <input type="button" id="pig_btn"  value="Спрячь меня!" onClick="hide_pig()">
    </td>
  </tr>
</table>
    <script>
    function hide_sutin () {
        pic = document.getElementById('sutin')
        btn = document.getElementById('sutin_btn')
        if (pic.style.display == 'none') {
            pic.style.display = 'block'
            btn.value = 'Спрячь меня'
        } else {
            pic.style.display = 'none'
            btn.value = 'Покажи меня!'
        }
    }
    function hide_pig () {
        pic = document.getElementById('pig')
        btn = document.getElementById('pig_btn')
        if (pic.style.display == 'none') {
            pic.style.display = 'block'
            btn.value = 'Спрячь меня'
        } else {
            pic.style.display = 'none'
            btn.value = 'Покажи меня!'
        }
    }
</script>
</body>
</html>
```
#### Изображения
![image](/images/JS7_2_1.png)
![image](/images/JS7_2_2.png)
![image](/images/JS7_2_3.png)
![image](/images/JS7_2_4.png)

## Задание 3
Создать документ, в котором рисунок фон занимает 50% окна и является нижним слоем. На верхнем слое второй рисунок, который двигается по вертикали к нижней границе первого рисунка, затем на столбец (ширину рисунка) вправо и вверх, к верхней границе, на столбец вправо и к нижней границе, и т.д. до правой границы нижнего рисунка. 
### Выполнение задания
#### Скрипт программы
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <style>
        #pig {position:absolute;}
    </style>
</head>
<body>
  <img src="Поле.jpg" id="field" height="440px" width="720"/>
  <img src="pig.jpg" id="pig" />
<script>
    vel_const = 20;
    
    function flying_pig () {
        x = x + s;
        y = y + n;
        pig.style.top = x + 'px';
        pig.style.left = y + 'px';
        if (x >= height - vel_const)  {
            s = 0
            n = vel_const
        }
        if (y >= (width/2)-vel_const)  {
            s = - vel_const
            n = 0
        }
        if (x <= 0)  {
            s = 0
            n = vel_const
        }
        if (y >= width-vel_const)  {
            s = vel_const
            n = 0
        }
        if (y >= width-vel_const && x >= height - vel_const )  {
            x = 0
            y  = 0
        }
        setTimeout("flying_pig()", 10);
    }
    
    x = 0;
    y = 0;
    s = vel_const;
    n = 0;
    
    field = document.getElementById('field')
    pig  = document.getElementById('pig')
    width = field.width
    height = field.height
    flying_pig();
</script>
</body>
</html>
```
#### Изображения
![image](/images/JS7_3_1.gif)