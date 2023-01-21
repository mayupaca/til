# Day 11
## Blackjack Project

[Blackjack Replit](https://replit.com/@mayupaca/blackjack-start#main.py)

```python
import random
from replit import clear

#配列からランダムなカードを選ぶ関数
def deal_card():
"""Returns a random card from the deck."""
  cards = [11, 2, 3, 4, 5, 6, 7, 8, 9, 10, 10, 10]
  random_card = random.choice(cards)
  return random_card

#After refactoring
#A function takes a List of cards as input and returns the score.
def calculate_score(cards):
  if sum(cards) == 21 and len(cards) == 2:
    return 0
  if 11 in cards and sum(cards) > 21:
    cards.remove(11)
    cards.append(1)
  return sum(cards)
  
#Before refactoring
# def calculate_score(user_cards, computer_cards):
#   if len(user_cards) == 2 and sum(user_cards) == 21:
#     return 0, sum(computer_cards)
#   elif len(computer_cards) == 2 and sum(computer_cards) == 21:
#     return sum(user_cards), 0
    
#   if 11 in user_cards and sum(user_cards) > 21:
#     user_cards.remove(11)
#     user_cards.append(1)
#   elif 11 in computer_cards and sum(computer_cards) > 21:
#     computer_cards.remove(11)
#     computer_cards.append(1)
#   return sum(user_cards), sum(computer_cards)

#A function conpares the user_score and computer_score.
def compare(user_score, computer_score):
  if user_score == computer_score:
    return "Draw 🙃"
  elif computer_score == 0:
    return "Lose, opponent has Blackjack 😱"
  elif user_score == 0:
    return "Win with a Blackjack 😎"
  elif user_score > 21:
    return "You went over. You lose 😭"
  elif computer_score == 21:
    return "Opponent went over. You win 😆"
  elif user_score > computer_score:
    return "You win 😄"
  else:
    return "You lose 😤"

def play_game():
  #Deal the user and computer 2 cards
  #ゲームの一番最初に実行される。2枚のカードがuserとcomputerに配られる
  user_cards = []
  computer_ cards = []
  is_game_over = False
  
  for card in range(2):
    user_cards.append(deal_card())
    computer_cards.append(deal_card())
  
  #is_geme_over = Trueになるまでリピートされる
  while not is_game_over:
    #userの合計スコア
    user_score = caluculate_score(user_cards)
    #computerの合計スコア
    computer_score = calculate_score(computer_cards)
    print(f"  Your cards: {user_cards}, current score: {user_score}")
    print(f"  Computer's first cards: {computer_cards[0]}")
    
    #0はBlackjackの意味
    #user turn
    #userかcomputerがblackjackかuserの合計が21より大きかったらゲームオーバー
    if user_score == 0 or computer_score == 0 or user_score > 21:
      is_game_over = True
    else:
      #To ask the user if they want to draw another card.
      should_draw_card = input("Type 'y' to get another card, type 'n' to pass: ")
      if should_draw_card == "y":
        user_cards.append(deal_card())
      else:
        is_game_over = True

    #computer turn
    #The computer should keep drawing cards as long as it has a score less than 17.
    while computer_score != 0 and computer_score < 17:
      computer_cards.append(deal_card())
      computer_score = calculate_score(computer_cards
      
    print(f"  Your final hand: {user_cards}, final score: {user_score}")
    print(f"  Computer's final hand: {computer_cards}, final score: {computer_score}")
    print(compare(user_score, computer_score))

#To ask the user if they want to restart the game.
while input("Do you want to play a game of Blackjack? Tyle 'y' or 'n': ") == 'y':
  clear()
  play_game()
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
 ```   
  
