# Day 9
## Python Dictionaries and Nesting

[day9 Replit](https://replit.com/@mayupaca/blind-auction-start#main.py)

### Dictionaries
|key|value|
|-----|-----|
|Bug|An error in a program that prevents the program from running as expexted|
|Function|A piece of code that you can easily call over and over again|
|Loop|The action of doing something over and over again.|


```python
{Key: Value}
👇
programming_dictionary = {
  "Bug": "An error in a program that prevents the program from running as expected.", 
  "Function": "A piece of code that you can easily call over and over again.",
  # "Loop": "The action of doing something over and over again.",
}
#Retrieving items from dictionary.
print(programming_dictionary["Bug"])

#Adding new items to dictionary.
programming_dictionary["Loop"] = "The action of doing something over and over again."
print(programming_dictionary)

#Creating an empty dictionary.
empty_dictionary = {}

#Wipe an existing dictionary
programming_dictionary = {}
print(programming_dictionary)

#Edit an item in a dictionary
programming_dictionary["Bug"] = "A moth in your computer."
print(programming_dictionary)

#Loop through a dictionary
for key in programming_dictionary:
  print(key)
  print(programming_dictionary[key])
```
### Nesting
```python
#Nesting a list in a Dictionary
travel_log = {
  "France": ["Paris", "Lille", "Dijon"],
  "Germany": ["Berlin", "Hamburg", "Stuttgart"]
}

#Nested Dictionary in Dictionary
travel_log = {
  "France": {"city_visited": ["Paris", "Lille", "Dijon"], "total_visits": 12},
  "Germany": {"city_visited": ["Berlin", "Hamburg", "Stuttgart"], "total_visits": 7},
}

#Nesting Dictionary in a List
travel_log = [
  {
    "country": "France",
    "city_visited": ["Paris", "Lille", "Dijon"],
    "total_visits": 12,
  },
  {
    "country": "Germany",
    "city_visited": ["Berlin", "Hamburg", "Stuttgart"], 
    "total_visits": 7,
  },
]
```
```python
from replit import clear
from art import logo
print(logo)

bidders = []

def add_bidder(bidder_name, bid_amount):
  new_bidder = {}
  new_bidder["Name"] = bidder_name
  new_bidder["Bid"] = bid_amount
  bidders.append(new_bidder)
  
any_bidders = True
while any_bidders:
  name = input("What is your name?: \n")
  bid = int(input("What is your bid?: \n$"))
  add_bidder(bidder_name=name, bid_amount=bid)
  others = input("Are there any other bidders? Type 'yes or 'no'. \n")
  
  if others == "no":
    any_bidders = False
    #winnerはdictionary。配列bittersのindex0に設定しておく
    winner = bidders[0]
    for bidder in bidders:
      if bidder["Bid"] > winner["Bid"]:
        winner = bidder
        
    print(f"The winner is {winner['Name']} with a bid of ${winner['Bid']}")
    
  else:
    clear()

#-------------------------------------------------------------------
# Angela's code

from replit import clear
from art import logo
print(logo)

bids = {}
bidding_finished = False

def find_highest_bidder(bidding_record):
  highest_bid = 0
  winner = ""
  # bidding_record = {"Angela": 123, "James": 321}
  for bidder in bidding_record:
    bid_amount = bidding_record[bidder]
    if bid_amount > highest_bid: 
      highest_bid = bid_amount
      winner = bidder
  print(f"The winner is {winner} with a bid of ${highest_bid}")

while not bidding_finished:
  name = input("What is your name?: ")
  price = int(input("What is your bid?: $"))
  bids[name] = price
  should_continue = input("Are there any other bidders? Type 'yes or 'no'.\n")
  if should_continue == "no":
    bidding_finished = True
    find_highest_bidder(bids)
  elif should_continue == "yes":
    clear()
```















