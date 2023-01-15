# Day 4

## Randomisation and Python List

### Random module

[Python random Module – Generate Random Numbers/Sequences](https://www.askpython.com/python-modules/python-random-module-generate-random-numbers-sequences)

```python
# random moduleを使うときは必ず👇をimport
import random

# 1-10の整数のランダムナンバー
random_integer = random.randint(1, 10)
print(random_integer)

# 0.0000... - 0.99999...の間の浮動小数点数
random_float = random.random()
print(random_float)

# 0.0000... - 4.9999...の間の浮動小数点数
random_float_5 = random.random() * 5
print(random_float_5)
```
### List

[Convert String to List in Python](https://www.askpython.com/python/string/convert-string-to-list-in-python) / 
[List Data Structures](https://docs.python.org/3/tutorial/datastructures.html)

```python

# inputで入力した文字列を指定した文字列で区切ってリストとして返すメソッド
string = "apple, peach, lemon, orange, banana"
new_string = string.split(", ") #", "で区切ったリストになる
print(new_string)
# output["apple", "peach", "lemon", "orange", "banana"]

# リストの値を取りだす
print(new_strint[1]) #index 1の値が取得できる

# Nested List
fruits = ["Strawberries", "Nectarines", "Apples", "Grapes", "Peaches", "Cherries", "Pears"]
vegetables = ["Spinach", "Kale", "Tomatoes", "Celery", "Potatoes"]

dirty_dozen = [fruits, vegetables]

print(dirty_dozen)
#output: [['Strawberries', 'Nectarines', 'Apples', 'Grapes', 'Peaches', 'Cherries', 'Pears'], ['Spinach', 'Kale', 'Tomatoes', 'Celery', 'Potatoes']]

print(dirty_dozen[0][4])
#output: Peaches

# リストの最後の値の取り方
print(fruits[len(fruits) - 1])
#output: Pears

```






