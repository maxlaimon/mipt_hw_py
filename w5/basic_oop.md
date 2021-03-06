### Объект
Экземпляр класса, который вызывается использованием имени класса и передачей аргументов, объявленных в `__init__`.
```python
class SomeClass:
    def __init__(self, name):
        self.__name = name

object = SomeClass(name)
object.__name  #object - объект класса, __name - аргумент объявленный в __init__
```

### Инкапсуляция 
По умолчанию атрибуты в классах являются общедоступными, а это значит, что из любого места программы мы можем получить атрибут объекта и изменить его. Инкапсуляция предотвращает прямой доступ к атрибутам объекта из вызывающего кода.
```python
class SomeClass:
    def __init__(self, name1, name2):
        self.__name1 = name1
        self.name2 = name2
    def get_name1(self):
        return self.__name1
    def get_name2(self):
        return self.name2
name1 = 'name1'
name2 = 'name2'

object = SomeClass(name1, name2)
#попробуем поменять атрибуты __name1 и name2
object.name2 = 'somename2'
print(object.get_name2()) #name2 изменился
object.__name1 = 'somename1'
print(object.get_name1()) #с __name1 ничего не произошло
#теперь посмотрим на атрибуты вне класса
print(object.__name1) #создался новый атрибут, оригинальный __name1 не поменялся
print(object.name2) 
```
### Полиморфизм
Способность к изменению функционала, унаследованного от базового класса.
### Наследование
Можно создать один класс (дочерний) на основе другого (материнского). Дочерний класс обладает всеми свойствами материнского, а также может иметь свои собственные свойства
