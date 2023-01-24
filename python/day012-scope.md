# Day 12
## Scope

```python
# Modifying Global Scope
enemies = 1

def increase_enemies():
  # ememiesはfunctionの中からアクセスできない
  # でも、globalを使えばアクセスできるようになる
  global enemies
  enemies += 1
  print(f"enemies inside function: {enemies}")

increase_enemies()
print(f"enemies outside function: {enemies}")

# globalはあまり使わない方がいい
# じゃあ、どうやってlocal scope内の変数を変更したらいいの？
# returnを使う↓
enemies = 1
def increase_enemies():
  print(f"enemies inside function: {enemies}")
  return enemies + 1

enemies = increase_enemies()
print(f"enemies outside function: {enemies}")
# returnを使って、global scopeでincrease_enemies functionを呼び出す
# OK
################################################

enemies = 1
 
def increase_enemies():
  print(f"enemies before assignment inside function: {enemies}")
  # local scope内で変数localemeniesにenemiesのコピーを作る
  # OK
  localenemies = enemies + 1
  print(f"enemies inside function: {localenemies}")
 
increase_enemies()
print(f"enemies outside function: {enemies}")

# Global Constants
PI = 3.14159
URL = "https://www.google.com"
TWITTER_HANDLE = "@yamamoto"
```



> Mayu's code

```python
import random

computer_number = random.randint(1, 100)

print("Welcome to the Number Guessing Game!")
print("I'm thinking of a number between 1 and 100.")
print(f"Pssst, the correct answer is {computer_number}")

remains = 0
chosen_level = input("Choose a difficulty. Type 'easy' or 'hard': ")
if chosen_level == "easy":
  remains += 10
else:
  remains += 5

def compare_number(remains):
  if computer_number < user_guess_number:
    print("Too high.")
    print("Guess again.")
    return remains - 1
  elif computer_number > user_guess_number:
    print("Too low.")
    print("Guess again.")
    return remains - 1
  elif remains == 0:
    return "You have run out of guesses, you lose."
  elif computer_number == user_guess_number:
    return f"The answer was {computer_number}. You win!"

is_number_matched = False

while not is_number_matched:
  print(f"You have {remains} attempts remaining to guess the number.")
  user_guess_number = int(input("Make a guess: "))

  remains = compare_number(remains)

  if remains == "You have run out of guesses, you lose." or remains == f"The answer was {computer_number}. You win!" in remains:
    is_number_matched = True
    print(remains)
  elif remains == "You have run out of guesses, you lose." in remains:
    is_number_matched = True
    print(remains)
```

> Angel code 

```python
from random import randint

EASY_LEVEL_TURNS = 10
HARD_LEVEL_TURNS = 5

#Function to check user's guess against actual answer.
def check_answer(guess, answer, turns):
  """checks answer against guess. Returns the number of turns remaining."""
  if guess > answer:
    print("Too high.")
    return turns - 1
  elif guess < answer:
    print("Too low.")
    return turns - 1
  else:
    print(f"You got it! The answer was {answer}.")

#Make function to set difficulty.
def set_difficulty():
  level = input("Choose a difficulty. Type 'easy' or 'hard': ")
  if level == "easy":
    return EASY_LEVEL_TURNS
  else:
    return HARD_LEVEL_TURNS

def game():
  #Choosing a random number between 1 and 100.
  print("Welcome to the Number Guessing Game!")
  print("I'm thinking of a number between 1 and 100.")
  answer = randint(1, 100)
  print(f"Pssst, the correct answer is {answer}") 

  turns = set_difficulty()
  #Repeat the guessing functionality if they get it wrong.
  guess = 0
  while guess != answer:
    print(f"You have {turns} attempts remaining to guess the number.")

    #Let the user guess a number.
    guess = int(input("Make a guess: "))

    #Track the number of turns and reduce by 1 if they get it wrong.
    turns = check_answer(guess, answer, turns)
    if turns == 0:
      print("You've run out of guesses, you lose.")
      return
    elif guess != answer:
      print("Guess again.")

game()
```
