# Day 13
## Debugging

```python
############DEBUGGING#####################

# # Describe Problem
def my_function():
  for i in range(1, 20):
    if i == 20:
      print("You got it")
my_function()
# # range関数の第二引数-1までの数字をループする
# # だから、range(1, 21)にしたら、コードが動く

# # Reproduce the Bug
from random import randint
dice_imgs = ["❶", "❷", "❸", "❹", "❺", "❻"]
dice_num = randint(1, 6)
print(dice_imgs[dice_num])
# # randint(1, 6)だと、1から6のインデックス番号だからエラーになる
# #randint(0, 5)が正しい


# #Play Computer
year = int(input("What's your year of birth?"))
if year > 1980 and year < 1994:
  print("You are a millenial.")
elif year > 1994:
  print("You are a Gen Z.")
## 1994をinputするとoutputが何も出ない
## 1994がどこにも含まれてない
## year <= 1994に変更する


# # Fix the Errors
age = input("How old are you?")
if age > 18:
  print("You can drive at age {age}.")
# # indentが必要
# # inputは文字列になるからintにしないといけない
# # int(input("How old are you?"))


# #Print is Your Friend
pages = 0
word_per_page = 0
pages = int(input("Number of pages: "))
word_per_page == int(input("Number of words per page: "))
total_words = pages * word_per_page
print(total_words)
## word_per_pageが==になってるから=にする


# Use a Debugger
def mutate(a_list):
  b_list = []
  for item in a_list:
    new_item = item * 2
  b_list.append(new_item)
  print(b_list)

mutate([1,2,3,5,8,13])
# expected output - [2, 4, 6, 10, 16, 26]
# but output is [26]
# b_list.append(new_item)がfor loopと同じレベルにいる
# インデントつけてあげる
```
