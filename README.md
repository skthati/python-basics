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


## List1 - List2

To show the items in list1 whcih are not in list2

```Python
lst = ['sam', 'ram', 'jam', 'fam', 'ram', 'sam']
lst2 = ['sam', 'ram']

lst3 = [i for i in lst if i not in lst2]
print(lst3)
```





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

