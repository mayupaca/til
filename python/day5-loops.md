# Day5
## Loops
```python
fruits = ["Apple", "Peach", "Pear"]
for fruit in fruits:
  print(fruit + " Pie")
```
### For Loop with Range
```python

# 第二引数は含まない
for number in range(1, 10):
  print(number)
# output: 1 2 3 4 5 6 7 8 9

# 第二引数を含むなら
for number in range(1, 11):
  print(number)
# output: 1 2 3 4 5 6 7 8 9 10

# 第3引数を追加すると、その数字で増える
# 3ずつ増やす
for number in range(1, 11, 3):
  print(number)
# output: 1 4 7 10
  
# 1 - 100の数字をrange fanctionを使って合計を出す
total = 0
for number in range(1, 101):
  total += number
print(total)
# output: 5050
```

> FizzBuzz
```python
#Python
for number in range(1, 101):
    if number % 15 == 0:
        print("FizzBuzz")
    elif number % 3 == 0:
        print("Fizz")
    elif number % 5 == 0:
        print("Buzz")
    else:
        print(number)
```
```javascript
// JavaScript
for (let number = 1; number <= 100; number++) {
  if (number % 15 === 0) {
    console.log("FizzBuzz");
  } else if (number % 3 === 0) {
    console.log("Fizz");
  } else if (number % 5 === 0) {
    console.log("Buzz");
  } else {
    console.log(number);
  }
}
```

> .append VS +=

- .append()は、リストや文字列などのオブジェクトの末尾に1つの要素を追加するために使う。
```python
list1 = [1, 2, 3]
list1.append(4)
print(list1) # [1, 2, 3, 4]
# Javascript.push的な関数
```
- +=は、オブジェクトの末尾に新しいオブジェクトを結合するために使う。文字列だと文字を連結する。
```python
string1 = "hello"
string1 += " world"
print(string1) # "hello world"
```
- リストを連結できる。
```python
list1 = [1, 2, 3]
list2 = [4, 5, 6]
list1 += list2
print(list1) # [1, 2, 3, 4, 5, 6]
```
> random.shuffle

random.shuffleはPythonの標準ライブラリのrandomモジュールにある関数。
この関数はリスト内の要素をランダムな順序で並べ替えます。
```python
# 1.
my_list = [1, 2, 3, 4, 5]
random.shuffle(my_list)
print(my_list)

# 2.
fruits = ["apple", "orange", "strowberry", "watermelon", "banana"]
random.shuffle(fruits)
print(fruits)
# ["watermelon", "banana", "orange", "strowberry", "apple"]

```
















