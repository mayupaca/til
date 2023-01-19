# Day 9
## Python Dictionaries and Nesting

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
















