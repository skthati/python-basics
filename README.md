<a name="readme-top"></a>


<div align="center">
<!-- Title: -->
<h1><a href="https://github.com/skthati/python-basics/">Python</a> - Basics </h1>
</div>

<!-- Table of contents -->
<hr>
<hr>
<ol>
    <li><a href="#python-basics">Python Basics</a></li>
    <li><a href="#exceptions">Python Exceptions</a></li>
    <li><a href="#function_overloading">Function Overloading</a></li>
    <li><a href="#bloopers">Bloopers</a></li>
</ol>
<hr>
<hr>


# Python Basics
 All basic code syntax 


 ## Float decimals

Round function is used to format decimals.
 ```Python
x = 3.232
y = round(x, 2)
print(y)
 ```
## String formatting
Alternate way to round the decimals of float is using format methond.

```Python
x = 3.232
y = "{:.2f}".format(x)
print(y)
```

## Dictionary Iteration

Iterate over key, value pairs in a dictionary Items

```Python
lst = [v for k, v in student_marks.items() if k == query_name]
```

## Sets

Sets are best way to remove duplicates.

```Python
lst = [2, 2, 2, 2, 2, 3, 2, 2, 2]
lst1 = set(lst)

print(lst1)
```
Output is:
```Python
{2, 3}
``` 

## Count occurrences 



```Python
lst = [2, 2, 2, 2, 2, 3, 2, 2, 2]
dct = {}

for i in lst:
    dct[i] = lst.count(i)
print(dct)

dct1 = {i : lst.count(i) for i in lst}
print(dct1)
```

## One liner for loop

```Python
print(','.join(str(i) for i in range(5) if i % 2 == 0))
```
Output is a generator object, which has to be joined with "," or '\n'.

## Find duplicates

Below code is using brute force.

```Python
lst = [1, 3, 5, 2, 7, 8]

for i in range(len(lst)):
    for j in range(i+1, len(lst)):
        if lst[i] > lst[j]:
            lst[j], lst[i] = lst[i], lst[j]

print(lst)
```
## Reverse a List
Palindrome: 
To reverse a list, change if statement to not equals to.

```Python
lst = [1, 3, 5, 2, 7, 8, 3, 2]

for i in range(len(lst)):
    for j in range(i+1, len(lst)):
        if lst[i] != lst[j]:
            lst[j], lst[i] = lst[i], lst[j]

print(lst)
```

## Remove Duplicates from list

```Python
lst = [1, 3, 5, 2, 7, 8, 3, 2]
lst1 = []

for i in range(len(lst)):
    if lst[i] not in lst1:
        lst1.append(lst[i])

print(lst1)

```

Another way of removing duplicates

```Python
lst = [1, 3, 5, 2, 7, 8, 3, 2]
lst1 = []

[lst1.append(i) for i in lst if i not in lst1]

print(lst1)
```

One liner to remove duplicates

```Python
lst = [1, 3, 5, 2, 7, 8, 3, 2]
lst = [j for i, j in enumerate(lst) if j not in lst[:i] ]
print(lst)
```

## Check if a list has duplicates.

To check if a list has duplicates and return True or False


Easiest way is to convert the list to Set and check the lenght of original list and converted Set.

```Python
lst = [1, 3, 5, 2, 7, 8, 3, 2]
print((len(lst) != len(set(lst))))

#Output:
True

```

## Shuffle a string

To check all possible shuffles of a given string

```Python
import itertools

s = "abc"

# Use permutations function to generate all possible permutations
perms = set(itertools.permutations(s))
print(perms)

# Convert permutations to list of strings
perm_strings = [''.join(p) for p in perms]

print(perm_strings)
```

## Permutations of a string

Using the permutations function using the itertools

```Python
import itertools

s = "abc"
permutations = list(itertools.permutations(s))

print(permutations)
```
Another way of permutations

```Python
def get_permutation(string, i=0):

    if i == len(string):   	 
        print("".join(string))

    for j in range(i, len(string)):

        words = [c for c in string]
   
        # swap
        words[i], words[j] = words[j], words[i]
   	 
        get_permutation(words, i + 1)

print(get_permutation('yup'))
```

One more way of permutations

```Python
def perms(s):        
    if(len(s)==1): return [s]
    result=[]
    for i,v in enumerate(s):
        result += [v+p for p in perms(s[:i]+s[i+1:])]
    return result

print(perms('abc'))
```

One more

```Python
def permute(data, i, length): 
    if i==length: 
        print(''.join(data) )
    else: 
        for j in range(i,length): 
            #swap
            data[i], data[j] = data[j], data[i] 
            permute(data, i+1, length) 
            data[i], data[j] = data[j], data[i]  
  

string = "ABC"
n = len(string) 
data = list(string) 
permute(data, 0, n)
```

Returns as a list, recursive iteration. Changed small bit of code.

```Python
def permutations(str, i = 0):
    
    if len(str) == i:
        lst.append(''.join(str))
        return (lst)
    
    for j in range(i, len(str)):
        n_str = [x for x in str]
        n_str[i], n_str[j] = n_str[j], n_str[i]
        permutations(n_str, i+1)

lst = []            
permutations("abcd")
print(lst)
```

```Python
strs = ["eat","tea","tan","ate","nat","bat"]

dct = {k:v for k,v in enumerate(strs)}
print(dct)
dct1 = {}

for i in range(len(strs)):
    new_sorted_word = sorted(strs[i])
    new_sorted_word = ''.join(new_sorted_word)
    dct1[i] = new_sorted_word

print(dct1)

keys = list(dct1.keys())

for i in range(len(keys)):
    for j in range(i, len(keys)):
        if dct1[keys[i]] > dct1[keys[j]]:
            keys[i], keys[j] = keys[j], keys[i]

dct2 = {}

for k in keys:
    dct2[k] = dct1[k]

print(dct2)

dct3 = []

for k in dct2.keys():
    dct3.append(dct1[k])

dct4 = []
for i in range(len(dct3)):
    temp_d =[]
    for j in range(i+1, len(dct3)):
        if dct3[i] != dct3[j]:
            dct4.append(dct3[i])
        elif dct3[i] == dct3[j]:
            temp_d += dct3[i]
        
    dct4.append(temp_d)

print(dct3)
print(dct4)    
```



## List1 - List2

To show the items in list1 whcih are not in list2

```Python
lst = ['sam', 'ram', 'jam', 'fam', 'ram', 'sam']
lst2 = ['sam', 'ram']

lst3 = [i for i in lst if i not in lst2]
print(lst3)
```
## Function overloading <a name="function_overloading"></a>

```Python

# Function overloading

def sum(a, b):
    return (a + b)

def sub(a, b):
    return (a - b)

def multiply(a, b):
    return (a * b)

def divide(a, b):
    return (a / b)

def calculate_func(func, a, b):
    function = {
        'sum': sum,
        'sub': sub,
        'multiply': multiply,
        'divide': divide
    }
    if func in function:
        return function[func](a, b)
    

a = int(input('Enter 1st number: '))
b = int(input('Enter 2nd number: '))
c = input('Select sum/sub/multiply/divide: ')

result = calculate_func(c, a, b)

print(f'{c} of {a} and {b} is {result}')

```

 
## Python Exceptions <a name="exceptions"></a>
Python Exceptions

try: Executes a piece of code.
except: if try has errors, then except is executed. We can use any number of except blocks.
else: If try has no errors, then else is executed.
finally: Is executed at the end of block. 

```Python
try:
    file = open("test.txt")
    a_dic = {"key":"value"}
    print(a_dic["test1"])
except FileNotFoundError:
    file = open("a_file.txt", "w")
    file.write("Something")
except KeyError as er:
    print(f"The key {er} does not exist.")
else:
    content = file.read()
    print(content)
finally:
    file.close()
    print("file was closed.")

```

### Custom exceptions:

```Python
if height > 3:
    raise ValueError("Human height is no more than 3 meters")
```

### Index Exception:

```Python
fruits = ["Apple", "Banana", "Orange"]

def make_pie(index):
    try:
        fruit = fruits[index]
    except IndexError:
        print("Fruit Pie")
    else:
        print(fruit + " pie")
```

### Key Exception:
 

<p align="right">(<a href="#readme-top">back to top</a>)</p>
<hr>  

## Json

Python has inbuilt library for json.

To serialize json data to python dictionary we use dump.
To deserialize we use load.

`import json`



Write : json.dump()

```Python
with open("password-manager/data.json", "w") as df:
    json.dump(new_data, df, indent==4) # indent creates space so code is more readable.
```
`w` stands for write.

Read  : json.load()

```Python
with open("password-manager/data.json", "r") as df:
    data = json.load(df)
    print(data)
```


To create data as json format and write it in a json file

```Python
def save():
    web_url = website_entry.get()
    username = username_entry.get()
    password = password_entry.get()
    new_data = {
        web_url: {
            "email": username,
            "password": password,
        }
    }

    if len(web_url) == 0 or len(password) == 0:
        messagebox.showinfo(title="Warning", message="Please fill all details.")
    else:
        with open("password-manager/data.json", "w") as df:
            json.dump(new_data, df, indent=4)
```


Update: Json.update()

To update json data

```Python
with open("password-manager/data.json", "r") as df:
    data = json.load("df")
    updated_data = data.update(new_data)

with open("password-manager/data.json", "w") as df:
    json.dump(updated_data, df, indent=4)

```

d



<!--
```Python

``` 
-->
<!-- 

Test1  
## Test <a name="test"></a>
Test Test

1. Code
    ```Python
    sc.onkey(key="Up", fun=up_move)
    sc.onkey(key="Right", fun=right_move)
    sc.onkey(key="Left", fun=left_move)
    sc.onkey(key="Down", fun=down_move)
    ```

2. Output

    ![Alt text](images/snake_working.gif)

<p align="right">(<a href="#readme-top">back to top</a>)</p>
<hr>  


-->

