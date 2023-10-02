# Тема 8. Основы ООП программирования
Отчет по Теме #8 выполнила:
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
###  Самостоятельно создайте класс и его объект. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Cat:
    def __init__(self, name, breed):
        self.name = name
        self.breed = breed

friends_cat = Cat("Собака", "Вислоухая")

print(f"Имя кошки: {friends_cat.name}")
print(f"Порода кошки: {friends_cat.breed}")
```

### Результат.
![Меню](https://github.com/ElizabethSmol/ChernovaZPIE_20_2/blob/pic/sam_8_1.PNG)

## Выводы

В данном коде создается класс Cat, который имеет два атрибута: name (имя кошки) и breed (порода кошки), а затем объект этого класса с именем friends_cat и выводятся строки с использованием функции `print()`. Строки содержат значение:

1. `print(f"Имя кошки: {friends_cat.name}")`: Выводится "Имя кошки: Собака"

2. `print(f"Порода кошки: {friends_cat.breed}")`: Выводится "Порода кошки: Вислоухая"

## Самостоятельная работа №2
###  Самостоятельно создайте атрибуты и методы для ранее созданного класса. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.
```python
class Cat:
    def __init__(self, name, breed, age, color):
        self.name = name
        self.breed = breed
        self.age = age
        self.color = color

    def introduce(self):
        return f"Кошку моего друга зовут {self.name}. Ей- {self.age}-лет, порода {self.breed}, ее цвет - {self.color}."


friends_cat = Cat("Сима", "Без породы", 3, "рыжий")


print(friends_cat.introduce())
```
### Результат.
![Меню](https://github.com/ElizabethSmol/ChernovaZPIE_20_2/blob/pic/sam_8_2.PNG)

## Выводы

В предыдущий код добавим атрибуты age (возраст) и color (цвет) и метод introduce и выводятся строки с использованием функции `print()`. Строки содержат значение:

1. `print(friends_cat.introduce())`: Выводится "Кошку моего друга зовут Сима. Ей- 3-лет, порода Без породы, ее цвет - рыжий.";

   
## Самостоятельная работа №3
### Самостоятельно реализуйте наследование, продолжая работать с ранее созданным классом. Оно должно отличаться, от того, что указано в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.
```python
class Cat:
    def __init__(self, name, breed, age, color):
        self.name = name
        self.breed = breed
        self.age = age
        self.color = color

    def introduce(self):
        return f"Кошку моего друга зовут {self.name}. Ей- {self.age}-лет, порода {self.breed}, ее цвет - {self.color}."


class Vet(Cat):

    def __init__(self, name, breed, age, color, doctor=False):
        super().__init__(name, breed, age, color)
        self.doctor = doctor

    def record(self):
        if self.doctor:
            return f"{self.name} пойдет к ветеринару"
        else:
            return f"{self.name} не пойдет к ветеринару сегодня."


friends_cat = Cat("Сима", "Без породы", 3, "рыжий")
vet = Vet("Варя", "Сиамская", 8, "белый")
print(friends_cat.introduce())
print(vet.introduce())
print(vet.record())

```
### Результат.
![Меню](https://github.com/ElizabethSmol/ChernovaZPIE_20_2/blob/pic/sam_8_3.PNG)

## Выводы

В предыдущий код добавили класс Vet, который наследуется от класса cat, и у него есть метод record, который показывает, идет ли кошка к ветеринару. После этого создаются объекты friends_cat и vet для представления кошки. Также выводятся строки с использованием функции `print()`. Строки содержат значения:

1. `print(friends_cat.introduce())`: Выводится "Кошку моего друга зовут Сима. Ей- 3-лет, порода Без породы, ее цвет - рыжий."
2. `print(friends_cat.introduce())`: Выводится "Кошку моего друга зовут Варя. Ей- 8-лет, порода Сиамская, ее цвет - белый."
3. `print(friends_cat.introduce())`: Выводится "Варя не пойдет к ветеренару сегодня."
   
## Самостоятельная работа №4
###  Самостоятельно реализуйте инкапсуляцию, продолжая работать с ранее созданным классом. Она должна отличаться, от того, что указана в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.
```python
class Cat:
    def __init__(self, name, breed, age, color):
        self._name = name
        self._breed = breed
        self.__age = age
        self._color = color

    def introduce(self):
        return f"Кошку моего друга зовут {self._name}. Ей- {self.__age}-лет, порода {self._breed}, ее цвет - {self._color}."


class Vet(Cat):

    def __init__(self, name, breed, age, color, doctor=False):
        super().__init__(name, breed, age, color)
        self._doctor = doctor

    def record(self):
        if self._doctor:
            return f"{self._name} пойдет к ветеринару"
        else:
            return f"{self._name} не пойдет к ветеринару сегодня."


friends_cat = Cat("Сима", "Без породы", 3, "рыжий")
vet = Vet("Варя", "Сиамская", 8, "белый")
print(friends_cat.introduce())
print(vet.introduce())
print(vet.record())
```
### Результат.
![Меню](https://github.com/ElizabethSmol/ChernovaZPIE_20_2/blob/pic/sam_8_3.PNG)

## Выводы

В предыдущий код добавили атрибуты _name, _breed, __age, _color, и _doctor инкапсулированы, и их доступ ограничен снаружи класса. Атрибут __age  "приватный". Это означает, что атрибут __age будет недоступен для прямого доступа извне класса cat, но методы класса могут работать с ним внутри класса.


## Самостоятельная работа №5
### Самостоятельно реализуйте полиморфизм. Он должна отличаться, от того, что указано в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Cat:
    def __init__(self, name, breed, age, color):
        self._name = name
        self._breed = breed
        self.__age = age
        self._color = color

    def introduce(self):
        return f"Кошку моего друга зовут {self._name}. Ей- {self.__age}-лет, порода {self._breed}, ее цвет - {self._color}."


class Vet(Cat):

    def __init__(self, name, breed, age, color, doctor=False):
        super().__init__(name, breed, age, color)
        self._doctor = doctor

    def record(self):
        if self._doctor:
            return f"{self._name} пойдет к ветеринару"
        else:
            return f"{self._name} не пойдет к ветеринару сегодня."

    def introduce(self):
        return f"Кошка {self._name}, порода {self._breed}, возраст {self._Cat__age} года, цвет {self._color}."


friends_cat = Cat("Сима", "Без породы", 3, "рыжий")
vet = Vet("Варя", "Сиамская", 8, "белый", True)

print(friends_cat.introduce())
print(vet.introduce())
print(vet.record())
```
### Результат.
![Меню](https://github.com/ElizabethSmol/ChernovaZPIE_20_2/blob/pic/sam_8_5_1.PNG)

## Выводы

В предыдущий код добавили полиморфизм, переопределяя метод introduce в классе Vet. 
    def introduce(self):
        return f"Ветеринар {self._name}, порода {self._breed}, возраст {self._Cat__age} года, цвет {self._color}."
1. `print(vet.record())`: Выводится "Варя пойдет к ветеринару"

## Общие выводы по теме
Таким образом, при работе по теме 8, мы сделали вывод, что объектно-ориентированное программирование позволяет организовать код в виде объектов, которые являются экземплярами классов. Классы определяют атрибуты (переменные) и методы (функции), которые могут быть использованы объектами. ООП способствует упрощению кода, повторному использованию, и способствует абстракции, что делает его более структурированным и легким в поддержке. Основные концепции в Python ООП включают классы, объекты, наследование, инкапсуляцию и полиморфизм, которые позволяют эффективно моделировать и решать задачи, создавая более чистый и организованный код.







