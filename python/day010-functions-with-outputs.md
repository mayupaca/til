# Day 10
## Functions with Outputs
[Relit](https://replit.com/@mayupaca/calculator-start#main.py)

### More Functions - Return
```python
def format_name(f_name, l_name):
  if f_name == "" or l_name == "":
    return "You didn't provide valid inputs."
    #ここでfunctionが終わる
  formated_f_name = f_name.title()
  formated_l_name = l_name.title()
  return f"{formated_f_name} {formated_l_name}"
  #return tells computer its end of this function
print(format_name(input("What is your first name?: \n"), input("What is your last name?: \n")))

# formated_strint = format_name("mayu", "suzumura")
# print(formated_strint)
```
> Leap year calculation
```python
def is_leap(year):
  if year % 4 == 0:
    if year % 100 == 0:
      if year % 400 == 0:
        return True
      else:
        return False
    else:
      return True
  else:
    return False

def days_in_month(year, month):
  month_days = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]  
  #is_leap functionを呼んで、入力された年がtrueかfalseの確認をする
  if is_leap(year) and month == 2:
    return 29
  return month_days[month - 1]
  
year = int(input("Enter a year: "))
month = int(input("Enter a month: "))
days = days_in_month(year, month)
print(days)
```
> Calculator

```python
#それぞれの計算のfunctionを作る
def add(n1, n2):
  return n1 + n2
#Subtract
def subtract(n1, n2):
  return n1 - n2
#Multiply
def multiply(n1, n2):
  return n1 * n2
#Divide
def divide(n1, n2):
  return n1 / n2
  
#dictionsryを作ってkey(オペレーター)でfunctionを選べるようにする
operations = {
  "+": add,
  "-": subtract,
  "*": multiply,
  "/": divide
}

def calculator():
　#最初の一回だけ
  first_number = float(input("What's the first number?: "))
  #+, -, *, /をloopで回して表示させる
  for symbol in operations:
    print(symbol)
    
  #計算し終えて、他の計算を続けるかどうか
  continue_calculate = True
  while continue_calculate:
    operation_symbol = input("Pick an operation: ")
    next_number = float(input("What is the next number?: "))
    #calculation_functionに計算のfunctionを入れる
    calculation_function = operations[operation_symbol]
    answer = calculation_function(first_number, next_number)
    
    print(f"{first_number} {operation_symbol} {next_number} = {answer}")
 
    check_continue = input(f"Type 'y' to continue calculating with {answer}, or type 'n' to start new calculation.: ")
    #計算したanswerにもっと計算するか
    if check_continue == "y":
      first_number = answer
    #新しい計算に行く
    else:
      continue_calculate = False
      calculator()
      
calculator()

#----------------------------------------------------------------------------------------------------

# num1 = int(input("What's the first number?: "))
# for symbol in operations:
#   print(symbol)
# operation_symbol = input("Pick an operation from the line above: ")

# num2 = int(input("What's the second number?: "))
# calculation_function = operations[operation_symbol]
# first_answer = calculation_function(num1, num2)

# print(f"{num1} {operation_symbol} {num2} = {first_answer}")

#second round------------------
# operation_symbol = input("Pick another operation: ")
# num3 = int(input("What's the next number?: "))

# calculation_function = operations[operation_symbol]
# second_answer = calculation_function(calculation_function(num1, num2), num3)

# print(f"{first_answer} {operation_symbol} {num3} = {second_answer}")

```
