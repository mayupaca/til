# Day 8
## Function Parameters and Ceasar Cipher

[Python List index() Method](https://www.w3schools.com/python/ref_list_index.asp) 

[caesar-cipher](https://replit.com/@mayupaca/caesar-cipher-4-start#main.py)

```python
from art import logo
print(logo)

alphabet = [
            'a', 'b', 'c', 'd', 'e', 
            'f', 'g', 'h', 'i', 'j', 
            'k', 'l', 'm', 'n', 'o', 
            'p', 'q', 'r', 's', 't', 
            'u', 'v', 'w', 'x', 'y', 'z'
            ]
            
def caesar(start_text, shift_amount, cipher_direction):
  end_text = ""
  if cipher_direction == "decode":
    shift_amount *= -1
  for char in start_text:
    if char in alphabet:
      position = alphabet.index(char)
      new_position = position + shift_amount
      end_text += alphabet[new_position]
    else:
      end_text += char
    
  print(f"Here's the {cipher_direction}d result: {end_text}")

should_continue = True
while should_continue:
  direction = input("Type 'encode' to encrypt, type 'decode' to decrypt:\n")
  text = input("Type your message:\n").lower()
  shift = int(input("Type the shift number:\n"))
  
  # もしshift_amountがalphabet数の26より多かったときの余り
  shift = shift % 26
  # e.g.
  # text = y
  # shift = 30
  # 30 = 30 % 26 = 4
  # shift = 4, text = c 
  
  caesar(start_text=text, shift_amount=shift, cipher_direction=direction)

  result = input("Type 'yes' if you want to go again. Otherwise type 'no', \n")
  #ここでnoが選ばれるまで、should_continueはずっとTrue
  if result == "no":
    should_continue = False
    print("Goodbye")
```




> encode and decode

- encoded

  abcdefg #Shift = 0

  shift by 3 

  defghij #Shift = 3

- decoded

  defghij #Shift = 0

  shift by -3 

  abcdefg #Shift = -3

> Arguments VS Parameters 

```python
def my_function(something)
  #Do this with something
  #Then do this
  #Finally do this
 
 something = 123
 # 👆         👆
 # Prameter   Argument
 
 #The parameter is the name of the data that's being passed in, the argument is the actual value of the data. 
 #The argument is the peace of data that's going to be passed over to this function when it's being called.
 #The parameter is the name of that data and we use the parameter inside the function to refer to it and todo thinds with is.
```
> Keyword Aguments

```python
def my_function(a, b, c)
  #Do thid with a
  #Then do this with b
  #Finally do this with c

my_function(a=1, b=2, c=3)
my_function(c=3, a=1, b=2) #This works too.
```
