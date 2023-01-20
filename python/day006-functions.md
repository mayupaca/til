# Day 6

## Functions

[Python Built in Functions](https://docs.python.org/3/library/functions.html) / 
[Style Guide for Python Code](https://peps.python.org/pep-0008/)


```python
# python built in functions
# print
# len
# int... etc
print("Hello")
num_char = len("Hello")
print(num_char)

# build your own functions
# def = definition
def my_function():
  print("Hello")
  print("Bye")
#calling functions
my_function() 
# Hello
# Bye
```
### While
[Reeborg's World](https://reeborg.ca/index_en.html)
```python
#While
while something_is_true:
  # trueの間、繰り返される
  #Do something repeatedly

# Reeborg's World python practice
# turn_right() functionの作成
def turn_right():
    turn_left()
    turn_left()    
    turn_left()
    
# 用意されているfunctionを使って、ロボットがジャンプするfunctionを作成
def jump():
    turn_left()
    while wall_on_right():
        move()  
    turn_right()
    move()
    turn_right()
    while front_is_clear():
        move()
    turn_left()
       
while not at_goal():
    if wall_in_front():
        jump()
    else:
        move()
        
#while not at_goal():
#    if wall_in_front():
#        jump()
#   else:
#        move()
    
#while not at_goal():
#    jump()

#for step in range(6):
#   jump()
    
#number_of_hurdles = 6
#while number_of_hurdles > 0:
#    jump()
#   number_of_hurdles -= 1
#    print(number_of_hurdles)

```
### Python VS JavaScript
- while

> Python

```python
password = ""
correct_password = "password123"

while password != correct_password:
    password = input("Enter your password:")
    if password == correct_password:
        print("Access granted.")
    else:
        print("Incorrect password. Try again.")
```
> JavaScript

```javascript
let password = "";
let correctPassword = "password123";

while (password !== correctPassword) {
    password = prompt("Enter your password:");
    if (password === correctPassword) {
        console.log("Access granted.");
    } else {
        console.log("Incorrect password. Try again.");
    }
}
```
- Create functions

> Python

```python
def reverse_string(string):
    return string[::-1]
print(reverse_string("Hello World!")) 
# "!dlroW olleH"

# '::-1'はpythonのスライス
# 文字列やリストのスライスの構文は、'start:stop:step'
```
> JavaScript

```javascript
function reverseString(str) {
    return str.split('').reverse().join('');
}
console.log(reverseString("Hello World!")); 
// "!dlroW olleH"
```
