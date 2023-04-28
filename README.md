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

