```python
import tkinter
from tkinter import ttk
from tkinter import messagebox
```

```python
def save():
# .get()メソッドで入力された値を取得
    petname = petnametxt.get()
    petage = petagebox.get()
    pettype = pettypecombo.get()
    ownerfirstname = owfnametxt.get()
    ownerlastname = owlnametxt.get()
# Validation and store info to the file
    if pettype == '' and ownerfirstname == '':
        tkinter.messagebox.showwarning(title="Error", message='Type of pet and your name cannot be blank.')
    else:
        with open('petinfo.txt', 'a') as petfile:
            petfile.write(
                f'Owner Name: {ownerfirstname} {ownerlastname}\n'
                f'Pet Name: {petname}\n'
                f'Pet Age: {petage}\n'
                f'Pet Type: {pettype}\n')
        print('Saved!')
```

```python
window = tkinter.Tk()
window.title('Pets')
frame = tkinter.Frame(window)
frame.pack()
# ---------- Pet Frame ---------------------------------------------------
petinfoframe = tkinter.LabelFrame(frame, text='Pet Information')
# sticky(position): 'w' = West, 'e' = East, 'n' = North, 's' = South, 'news' = center
petinfoframe.grid(row=0, column=0, sticky='news')
# Label for text box
petnamelabel = tkinter.Label(petinfoframe, text='Pet Name: ')
petnamelabel.grid(row=0, column=0, padx=10, pady=10)   # padx, pady = padding
# Text box
petnametxt = tkinter.Entry(petinfoframe)
petnametxt.grid(row=0, column=1, padx=10, pady=10)
# Creat drop down box
pettypelabel=tkinter.Label(petinfoframe, text="Type of Pet: ")
pettypelabel.grid(row=1,column=0, padx=10, pady=10)
pettypecombo=ttk.Combobox(petinfoframe, values=['Dog', 'Cat', 'Hamster', 'Fish', 'Rabbit'])
pettypecombo.grid(row=1,column=1, padx=10, pady=10)
# Creat spinbox
petagelabel=tkinter.Label(petinfoframe, text="Age: ")
petagelabel.grid(row=0,column=2, padx=10, pady=10)
petagebox=tkinter.Spinbox(petinfoframe, from_= 1, to= 'infinity')
petagebox.grid(row=0,column=3)

# ---------- Owner Frame -------------------------------------------------
ownerinfoframe=tkinter.LabelFrame(frame, text='Owner Information')
ownerinfoframe.grid(row=1,column=0)

ownerfirstnamelabel=tkinter.Label(ownerinfoframe, text='First Name: ')
ownerfirstnamelabel.grid(row=0,column=0, padx=10, pady=10)
owfnametxt=tkinter.Entry(ownerinfoframe)
owfnametxt.grid(row=0,column=1, padx=10, pady=10)

ownerlastnamelabel=tkinter.Label(ownerinfoframe, text='Last Name: ')
ownerlastnamelabel.grid(row=0,column=2, padx=10, pady=10)
owlnametxt=tkinter. Entry(ownerinfoframe)
owlnametxt.grid(row=0,column=3, padx=10, pady=10)

# ---------- Adding button ------------------------------------------------
savebutton=tkinter.Button(frame, text='Save', command=save)
savebutton.grid(row=2,column=0)

window.mainloop()
```
