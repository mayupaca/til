```python
File Reading and Writing
.txt text
.csv coma separated values

fileA = open('sample.txt', 'w') # file name and a(append) or w(write) or r(read)
fileA.write('Jane Do\nJohn Smith\nCleo Patra\n')
fileA.write('Nefer Titi')
fileA.close()
```
```python
lookup=['Jane Do', 'Cleo Patra']
with open('sample.txt','r') as readfile:
  for line in readfile:
    line=line.strip() # remove \n
    if line in lookup:
      print(line, 'is in the file!')
```
> ----- output -----  
> Jane Do is in the file!  
> Cleo Patra is in the file!  
  
```python
fileA = open('sample.txt', 'r')
print(fileA.read())
fileA.close()
```
> ----- output -----  
> Jane Do  
> John Smith  
> Cleo Patra  
> Nefer Titi  

```python
listA = []
with open('sample.txt', 'r') as readfile: # with method auto close
  for line in readfile:
    listA.append(line)

print(listA)
```
> ----- output -----  
> ['Jane Do\n', 'John Smith\n', 'Cleo Patra\n', 'Nefer Titi']

### Writing csv file
```python
import csv

with open('pupils.csv', 'w') as pupils:
  csvwriter = csv.writer(pupils)
  csvwriter.writerow(["Name", "Address", "DOB", "Registered"])

pupil = []
usrin = "y"
while usrin == "y":
  usrin = input("Enter Pupil Name: ")
  pupil.append(usrin)
  usrin = input("Enter Pupil Address: ")
  pupil.append(usrin)
  usrin = input("Enter Pupil DOB: ")
  pupil.append(usrin)
  usrin = input("Is pupil registerd?: ")
  pupil.append(usrin)
  with open('pupils.csv', 'a') as pupils:
    csvwriter = csv.writer(pupils)
    csvwriter.writerow(pupil)
  pupil = []
  usrin = input("Do you want to enter more records? (y/n): ")
```
### Reading csv file
```python
import csv
search = input('enter search name: ')
found = False

with open('pupils.csv', 'r') as readfile:
    csvreader = csv.reader(readfile)
    for row in csvreader:
        if search in row:
            found = True
            print(row[0], 'Registered; ',row[3])
    if found == False:
        print(search, 'is not in the file')
```


