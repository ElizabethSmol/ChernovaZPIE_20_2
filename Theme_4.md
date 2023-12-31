# Тема 4. Функции и модули
Отчет по Теме #4 выполнил(а):
- Чернова Елизавета Андреевна
- ЗПИЭ-20-2

| Задание | Сам_раб |
| ------ | ------ |
| Задание 1 | + |
| Задание 2 | + | 
| Задание 3 | + | 
| Задание 4 | + |
| Задание 5 | + |

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Самостоятельная работа №1
### Дайте подробный комментарий для кода, написаного ниже. Комментарий нужен для каждой строчки кода, нужно описать что она делает. Не забудьте, что функции комментируются по-особенному.
![Меню](https://github.com/ElizabethSmol/ChernovaZPIE_20_2/blob/pic/sam_4_1_ex.PNG)
```python
#Импортируется модуль datetime из библиотеки datetime.
from datetime import datetime
#Импортируется функция sqrt из модуля math.
from math import sqrt

def main(**kwargs):

    """
    Функция main, принимающая произвольное количество именованных аргументов (kwargs)
    В цикле проходится по каждому элементу в kwargs и присваивает его ключ (имя) переменной key.
    Args:
        param kwargs: произвольное количество именованных аргументов
    Return:
        float: результат, который равен квадратному корню из суммы квадратов компонентов значения элемента
    """

    for key in kwargs.items():
        result = sqrt(key[1][0] ** 2 + key[1][1] ** 2)
        print(result)

if __name__ == '__main__':
    #Этот код выполняется при запуске модуля напрямую
    #Записывается текущее время в переменную start_time.
    start_time = datetime.now()
    # Вызов функция main с набором именованных аргументов.
    main(
        one=[10, 3],
        two=[5, 4],
        three=[15, 13],
        four=[93, 53],
        five=[133, 15]
    )
    # Вычисляется время выполнения программы путем вычитания start_time из текущего времени.
    time_costs = datetime.now() - start_time
    # Выводится информация о времени выполнения программы.
    print(f"Время выполнения программы - {time_costs}")

```

### Результат.
![Меню](https://github.com/ElizabethSmol/ChernovaZPIE_20_2/blob/pic/sam_4_1.PNG)

## Выводы
В данном коде определяется функция main,которая принимает ключевые аргументы в форме словаря kwargs, и выводится строка с использованием функции `print()`. Строки содержат значение:

1. `print(result)`: Выводится числовое значение, равное квадратному корню суммы квадратов первого и второго элементов значения;
2. `print(f"Время выполнения программы - {time_costs}")`: Выводится информация о времени выполнения программы.

## Самостоятельная работа №2
### Напишите программу, которая будет заменять игральную кость с 6 гранями. 
### Если значение равно 5 или 6, то в консоль выводится «Вы победили», если значения 3 или 4, то вы рекурсивно должны вызвать эту же функцию, если значение 1 или 2, то в консоль выводится «Вы проиграли». 
### При этом каждый вызов функции необходимо выводить в консоль значение "кубика". Для выполнения задания необходимо использовать стандартную библиотеку random. Программу нужно написать, используя одну функцию и "точку входа"

```python
import random

def sqrt():
    sqr = random.randint(1, 6)
    print(sqr)
    if sqr == 5 or sqr == 6:
        print("Вы победили!")
    elif sqr == 3 or sqr == 4:
        sqrt()
    else: print("Вы проиграли.")

sqrt()
```
### Результат.
![Меню](https://github.com/ElizabethSmol/ChernovaZPIE_20_2/blob/pic/sam_4_2.PNG)

## Выводы

В данном коде импортируется модуль random, определяется функция sqrt() и выводятся строки с использованием функции `print()`. Функция sqrt() вызывается в конце кода, чтобы начать выполнение процесса. Строки содержат значения:
1. `print(sqr)`: Выводится значение sqr, которое генерируется случайно в диапазоне от 1 до 6 (включительно) с помощью функции random.randint(1, 6).
2. `print("Вы победили!")` или `print("Вы проиграли.")`: если sqr равно 5 или 6, выводится сообщение "Вы победили!", если sqr равно 3 или 4, вызывается функция sqrt(), что приведет к генерации нового случайного числа и выполнению процесса снова, если sqr не соответствует ни одному из условий выше, печатается сообщение "Вы проиграли.".

   
## Самостоятельная работа №3
### Напишите программу, которая будет выводить текущее время, с точностью до секунд на протяжении 5 секунд. Программу нужно написать с использованием цикла. 
### Подсказка: необходимо использовать модуль datetime и time, а также вам необходимо как-то "усыплять" программу на 1 секунду.

```python
import datetime
import time

for _ in range(5):
    с_time = datetime.datetime.now()
    print("Текущее время, с точностью до секунд", с_time.strftime("%Y-%m-%d %H:%M:%S"))
    time.sleep(1)
```
### Результат.
![Меню](https://github.com/ElizabethSmol/ChernovaZPIE_20_2/blob/pic/sam_4_3.PNG)

## Выводы

Данный код создает цикл, который выполняется 5 раз. также выводятся строки с использованием функции `print()`. Строки содержат значения:

1. `print("Текущее время, с точностью до секунд", с_time.strftime("%Y-%m-%d %H:%M:%S"))`: На каждой итерации он получает текущее время с помощью datetime.datetime.now() и выводит его с точностью до секунд, используя strftime(). Затем программа "усыпляется" на 1 секунду с помощью time.sleep(1), прежде чем продолжить выполнение следующей итерации.

## Самостоятельная работа №4
### Напишите программу, которая считает среднее арифметическое от аргументов вызываемой функции, с условием того, что изначальное количество этих аргументов неизвестно. 
### Программу необходимо реализовать используя одну функцию и "точку входа"

```python
def sred(*args):
    summa = sum(args)
    sr = summa / len(args)
    return sr

i = input("Введите числа через пробел: ")
chs = [float(ch) for ch in i.split()]

result = sred(*chs)
print(result)

```
### Результат.
![Меню](https://github.com/ElizabethSmol/ChernovaZPIE_20_2/blob/pic/sam_4_4.PNG)

## Выводы

В данном коде определяется функция sred() и выводятся строки с использованием функции `print()`. Каждая строка содержит разные значения:
1. `("Введите числа через пробел: ")": строка выводит текст "Введите числа через пробел: " для ввода чисел пользователем;
2.  `print(result)`: строка выводит среднее арифметическое произвольного количества аргументов, изначально вводимые пользователем и разбитые на список.


## Самостоятельная работа №5
### Создайте два Python файла, в одном будет выполняться вычисление площади треугольника при помощи формулы Герона (необходимо реализовать через функцию), 
### а во втором будет происходить взаимодействие с пользователем (получение всей необходимой информации и вывод результатов). 
### Напишите эту программу и выведите в консоль полученную площадь.

```python
main.py
import geron


a = float(input("Введите длину первой стороны треугольника: "))
b = float(input("Введите длину второй стороны треугольника: "))
c = float(input("Введите длину третьей стороны треугольника: "))

print(geron.sqr_ger(a, b, c))

geron.py
import math

def sqr_ger(a, b, c):
    p = (a + b + c)/2
    s = float( math.sqrt(p*(p-a)*(p-b)*(p-c)))
    return s
```
### Результат.
![Меню](https://github.com/ElizabethSmol/ChernovaZPIE_20_2/blob/pic/sam_4_5.PNG)

## Выводы

В данном коде создаются два файла .py и выводятся строки с использованием функции `print()`. Каждая строка содержит разные значения:

1. `("Введите длину первой стороны треугольника: ")` и т.п.: Выводится строка для того, чтобы пользователь ввел сторону треугольника с помощью функциии input();
2. `print(geron.sqr_ger(a, b, c))`: Выводится результат выполнения функции geron.sqr_ger() при помощи импорта класса, в котором вычисляется полупериметр и площадь треугольника, также используется функция math.sqrt() для вычисления корня.


## Общие выводы по теме
Таким образом, при работе по теме 4, мы сделали вывод, что функции это блок кода, который помогает при работе с программой для выполнения определенных задач, группируя данные. Можно работать с несколькими аргументами или без них, используя код def название_функции(аргументы_функции_можно_оставить_пустым):
