# Python Practice - Session 2

### Task 2.1
Write a Python program to calculate the length of a string without using the `len` function.
```
string = "Hello"
counter = 0
for i in string:
	counter += 1
print(counter)
```

### Task 2.2
Write a Python program to count the number of characters (character frequency) in a string (ignore case of letters).
Examples:
```
Input: 'Oh, it is python' 
Output: {',': 1, ' ': 3, 'o': 2, 'h': 2, 'i': 2, 't': 2, 's': 1, 'p': 1, 'y': 1, 'n': 1}
```

```
string = "Oh, it is python"
newSet = {}

for i in string:
  if i in newSet:
    newSet[i] += 1
  else:
    newSet[i] = 1

print(newSet)
```

### Task 2.3
Write a Python program that accepts a comma separated sequence of words as input and prints the unique words in sorted form.
Examples:
```
Input: ['red', 'white', 'black', 'red', 'green', 'black']
Output: ['black', 'green', 'red', 'white']
```

```
input = ['red', 'white', 'black', 'red', 'green', 'black']
output = []

for item in input:
  if item not in output:
    output.append(item)
    
print(output)
```

### Task 2.4
Create a program that asks the user for a number and then prints out a list of all the [divisors](https://en.wikipedia.org/wiki/Divisor) of that number.
Examples:
```
Input: 60
Output: [1, 2, 3, 4, 5, 6, 10, 12, 15, 20, 30, 60]
```

```
input = 60;
divisors = []

counter = 1
while counter <= input:
  if (input % counter == 0):
    divisors.append(counter)

  counter += 1
    
print(divisors)
```

### Task 2.5
Write a Python program to sort a dictionary by key.
```
color_dict = {'red':'#FF0000',
          'green':'#008000',
          'black':'#000000',
          'white':'#FFFFFF'}

color_dict_sorted = {k: v for k,v in sorted(color_dict.items())}

print(color_dict_sorted)
```


### Task 2.6
Write a Python program to print all unique values of all dictionaries in a list.
Examples:
```
Input: [{"V":"S001"}, {"V": "S002"}, {"VI": "S001"}, {"VI": "S005"}, {"VII":"S005"}, {"V":"S009"},{"VIII":"S007"}]
Output: ['S005', 'S002', 'S007', 'S001', 'S009']
```

```
output = [];

for item in input:
  val = item.values()[0]
  if val not in output:
    output.append(val)
    
print(output)
```

### Task 2.7
Write a Python program to convert a given tuple of positive integers into an integer. 
Examples:
```
Input: (1, 2, 3, 4)
Output: 1234
```

```
output = ""

for val in input:
  output += str(val)

print(int(output))
```


### Task 2.8
Write a program which makes a pretty print of a part of the multiplication table.
Examples:
```
Input:
a = 2
b = 4
c = 3
d = 7

Output:
	3	 4	5	  6	  7	
2	6	 8	10	12	14	
3	9	 12	15	18	21	
4	12 16	20	24	28
```
```
a = 2
b = 4
c = 3
d = 7

counter = 0
for row in range(a, b + 1):
  
    if counter == 0:
      print("", end = "   ") # initial empty spacing

      for col in range(c, d + 1):
        print(col, end = "   ") # print all column

      print()
      
      counter += 1


    
    print(row, end = "  ") # print row one by one

    
    for col in range(c, d + 1): # print multiplication output
        multiplication_num = row * col
        print(multiplication_num, end = "  ")
        
    print()
```

### Materials
* [Python Data Types](https://realpython.com/python-data-types/)
* [Python Data Structures](https://realpython.com/python-data-structures/)
* [Conditional Statements](https://realpython.com/python-conditional-statements/)
* [While loop](https://realpython.com/python-while-loop/)
* [For loop](https://realpython.com/python-for-loop/)
* [Operators](http://pythonicway.com/python-operators)

