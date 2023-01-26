# Day 14
## Higher Lower Game
[Replit](https://replit.com/@mayupaca/higher-lower-start#main.py)

```python
import random
from game_data import data 
from art import logo, vs
from replit import clear

def format_data(account):
  """Takes the account data and returns the printable format."""
  account_name = account['name']
  account_descr = account['description']
  account_country = account['country']
  return f"{account_name}, a {account_descr}, from {account_country}"

def check_answer(guess, a_followers, b_followers):
  """Take the user guess and follower counts and returns if they got it right."""
  if a_followers > b_followers:
    return guess == "a"
    # if guess == "a":
    #   return True
    # else:
    #   return False
  else:
    return guess == "b"
  
# Display art
print(logo)

# Score keeping.
score = 0
game_should_continue = True
account_b = random.choice(data)

# Make the game repeatable.
while game_should_continue:

  # Generate a random account from the game data.
  # Making account at position B become the next account at position A.
  account_a = account_b
  account_b = random.choice(data)
  # もしaccount_bがaccount_aと同じだったら
  while account_a == account_b:
    account_b = random.choice(data)
  
  print(f"Compare A: {format_data(account_a)}.")
  print(vs)
  print(f"Against B: {format_data(account_b)}.")
  
  # Ask user for a guess.
  guess = input("Who has more followers? Type 'A' or 'B': ").lower()
  
  # Check if user is correct.
  ## Get follower count of each accout.
  a_follower_count = account_a["follower_count"]
  b_follower_count = account_b["follower_count"]
  is_correct = check_answer(guess, a_follower_count, b_follower_count)

  # Clear the screen
  print(logo)
  clear()
  
  # Give user feedback on their guess.
  if is_correct:
    score += 1
    print(f"You are right! Current score: {score}")
  else:
    game_should_continue = False
    print(f"Sorry, That is wrong. Final score: {score}")

# 正解したら、You are right! Current Score: を表示させる
# and フォロワーの多いほうをCompareAにする
# AgainstBをランダムに表示させる
# 答えが不正解なら、ゲームを終わらせる Sorry, that is wrong. Final score:
# アスキーアートの表示
# CompareAとAgainstBをランダムに表示させる関数
# Compare A: Lionel Messi, a Footballer, from Argentina.
# Against B: Shawn Mendes, a Musician, from Canada.
# import random
# from game_data import data 
# from art import logo 

# def celebrity_data():
#   return random.choice(data)
  
# celebrity_a = celebrity_data()
# celebrity_b = celebrity_data()

# def check_follower_count():
#   more_followers = ""
#   if celebrity_a["follower_count"] > celebrity_b["follower_count"]:
#     more_followers = "A"
#   else:
#     more_followers = "B"

#   return more_followers

# # 答えを入力させる
# def play_game():
  
#   print(f"Compare A: {celebrity_a['name']}, {celebrity_a['description']}, from {celebrity_a['country']}.")
#   print(f"Against B: {celebrity_b['name']}, {celebrity_b['description']}, from {celebrity_b['country']}.")
    
#   answer = True
#   while answer:
#     score = 0
#     more_followers = check_follower_count()
#     answer = input("Who has more followers? Type 'A' or 'B': ").upper()
#     # 答えが正解か判断する
#     if answer == "A" and more_followers == "A":
#       score += 1
#     elif answer == "B" and more_followers == "B":
#       score += 1
#     else:
#       answer = False
# play_game()
```
