## List
List is the most basic data structure in Python.

To creat a list, use:
```Python
>>> my_list = ["cat", "dog", 261]
>>> print(my_list)
['cat', 'dog', 261]
```
The items in the list do not need to be of the same type, which means a list can contain ints, strings at the same time.

In addition, you can make an empty list:
```Python
my_list2 = [ ]
```

### Indexing
Each value in the list has a corresponding positional value, called an index, with the first index being 0, the second index being 1, and so on.

<div align=center><img src=https://github.com/Cafwell/Learning-Python/blob/main/imgs/positive-indexes.png height=194 width=704></div>

Indexes can also start at the end, with an index of -1 for the last element, -2 for the previous bit, and so on.

<div align=center><img src=https://github.com/Cafwell/Learning-Python/blob/main/imgs/negative-indexes.png height=194 width=704></div>

```Python
>>> list = ['red', 'green', 'blue', 'yellow', 'white', 'black']
>>> print(list[0])
>>> print(list[1])
>>> print(list[-1])
red
green
black
```

### Slicing
Using the form of square brackets [ ]
```Python
>>> list1 = [3, 5, "green", 5.3, "house", 100, 1]
>>> print(list1[2:5])
['green', 5.3, 'house']
```
That's because:

<div align=center><img src=https://github.com/Cafwell/Learning-Python/blob/main/imgs/slicing.jpg></div>

Between 2 and 5 are green, 5.3 and house.

Use [:num] is OK as well!
```Python
>>> print(list1[:4])
[3, 5, 'green', 5.3]
```

### Update the list
+ Use = can modify or update the data items in the list
+ Use the append () method to add list items
+ Use the del() function to delete the elements of the list

```Python
>>> list2 = ['Google', 'Bing', 'Yahoo']
>>> print(list1)
['Google', 'Bing', 'Yahoo']

>>> list2[2] = 'Yandex'
>>> print(list1)
['Google', 'Bing', 'Yandex']

>>> list2.append('Baidu')
>>> print(list1)
['Google', 'Bing', 'Yandex', 'Baidu']

>>> del list2[2]
>>> print(list1)
['Google', 'Bing', 'Baidu']
```

Furthermore, the +sign can be used to combine lists
```Python
list3 = [1, 2, 3] + [4, 5, 6]
print(list3)
[1, 2, 3, 4, 5, 6]
```

## Dictionary
Each 'key => value' pair of the dictionary is separated by a colon, each pair is separated by a comma (,) , and the entire dictionary is enclosed in curly braces{ }
```Python
d = {key1 : value1, key2 : value2, key3 : value3 }
# Variable names are not recommended as 'dict'
```
The key must be unique, but the value is not.

```Python
# It can be written vertically
>>> d1 = {
    'Name': 'Zelda',
    'Age': 18,
    'Class': 'First'
}
>>> print("tinydict['Name']:", tinydict['Name'])
tinydict['Name']: Zara
```
If one key have more than one value, they should be a list;
```Python
d = {
    'a' : [1, 2, 3],
    'b' : [4, 5]
}
```

### Update the Dict
```Python
>>> d1['Age'] = 20 # Update
>>> d1['School'] = " HappySchool " # Add new item
```

### Function & Method
```Python
>>> sounds = {"cat": "meow", "dog": "woof", "horse": "neigh"}
>>> print(len(sounds))
>>> print(str(sounds))
3
{'cat': 'meow', 'dog': 'woof', 'horse': 'neigh'}
```

Built-in methods:
+ dict.items() 以列表返回一个视图对象
+ dict.keys() 返回一个视图对象
+ dict.values() 返回一个视图对象
+ dict.clear() 删除字典内所有元素
