#Си_Шарп 

**LINQ (Language Integrated Query)** 
Это компонент в C#, который позволяет выполнять запросы к различным источникам данных, таким как массивы, коллекции, базы данных и XML-документы, используя синтаксис, интегрированный в язык.

**Существует несколько разновидностей LINQ:**
- LINQ to Objects: применяется для работы с массивами и коллекциями
- LINQ to Entities: используется при обращении к базам данных через технологию Entity Framework
- LINQ to XML: применяется при работе с файлами XML
- LINQ to DataSet: применяется при работе с объектом DataSet
- Parallel LINQ (PLINQ): используется для выполнения параллельных запросов

Простейшее определение запроса LINQ выглядит следующим образом:
```
from переменная in набор_объектов
	select переменная;
```

**Методы расширения LINQ**
Кроме стандартного синтаксиса `from .. in .. select` для создания запроса LINQ мы можем применять специальные методы расширения, которые определены для интерфейса `IEnumerable`. Как правило, эти методы реализуют ту же функциональность, что и операторы LINQ типа `where` или `orderby`.

# LINQ to Objects
```
string[] people = { "Tom", "Bob", "Sam", "Tim", "Tomas", "Bill" };

// создаем новый список для результатов и передаём из массива в p
var selectedPeople = from p in people 
	where p.ToUpper().StartsWith("T")//фильтрация по критерию`
	orderby p// упорядочиваем по возрастанию`
	select p;// выбираем объект в создаваемую коллекцию`

foreach (string person in selectedPeople)`
	Console.WriteLine(person);`
```
Выражение так же можно было бы записать в одну строку
```
var selectedPeople = from p in people where p.ToUpper().StartsWith("T") orderby p  select p;`
```


# Список используемых методов расширения LINQ

- Select: определяет проекцию выбранных значений
    
- Where: определяет фильтр выборки
    
- OrderBy: упорядочивает элементы по возрастанию
    
- OrderByDescending: упорядочивает элементы по убыванию
    
- ThenBy: задает дополнительные критерии для упорядочивания элементов возрастанию
    
- ThenByDescending: задает дополнительные критерии для упорядочивания элементов по убыванию
    
- Join: соединяет две коллекции по определенному признаку
    
- Aggregate: применяет к элементам последовательности агрегатную функцию, которая сводит их к одному объекту
    
- GroupBy: группирует элементы по ключу
    
- ToLookup: группирует элементы по ключу, при этом все элементы добавляются в словарь
    
- GroupJoin: выполняет одновременно соединение коллекций и группировку элементов по ключу
    
- Reverse: располагает элементы в обратном порядке
    
- All: определяет, все ли элементы коллекции удовлятворяют определенному условию
    
- Any: определяет, удовлетворяет хотя бы один элемент коллекции определенному условию
    
- Contains: определяет, содержит ли коллекция определенный элемент
    
- Distinct: удаляет дублирующиеся элементы из коллекции
    
- Except: возвращает разность двух коллекцию, то есть те элементы, которые создаются только в одной коллекции
    
- Union: объединяет две однородные коллекции
    
- Intersect: возвращает пересечение двух коллекций, то есть те элементы, которые встречаются в обоих коллекциях
    
- Count: подсчитывает количество элементов коллекции, которые удовлетворяют определенному условию
    
- Sum: подсчитывает сумму числовых значений в коллекции
    
- Average: подсчитывает cреднее значение числовых значений в коллекции
    
- Min: находит минимальное значение
    
- Max: находит максимальное значение
    
- Take: выбирает определенное количество элементов
    
- Skip: пропускает определенное количество элементов
    
- TakeWhile: возвращает цепочку элементов последовательности, до тех пор, пока условие истинно
    
- SkipWhile: пропускает элементы в последовательности, пока они удовлетворяют заданному условию, и затем возвращает оставшиеся элементы
    
- Concat: объединяет две коллекции
    
- Zip: объединяет две коллекции в соответствии с определенным условием
    
- First: выбирает первый элемент коллекции
    
- FirstOrDefault: выбирает первый элемент коллекции или возвращает значение по умолчанию
    
- Single: выбирает единственный элемент коллекции, если коллекция содержит больше или меньше одного элемента, то генерируется исключение
    
- SingleOrDefault: выбирает единственный элемент коллекции. Если коллекция пуста, возвращает значение по умолчанию. Если в коллекции больше одного элемента, генерирует исключение
    
- ElementAt: выбирает элемент последовательности по определенному индексу
    
- ElementAtOrDefault: выбирает элемент коллекции по определенному индексу или возвращает значение по умолчанию, если индекс вне допустимого диапазона
    
- Last: выбирает последний элемент коллекции
    
- LastOrDefault: выбирает последний элемент коллекции или возвращает значение по умолчанию

