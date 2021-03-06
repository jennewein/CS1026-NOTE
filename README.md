### **Concepts**

#### Hardware

##### Computer components

![image-20211021153956937](C:\Users\Lenovo\AppData\Roaming\Typora\typora-user-images\image-20211021153956937.png)

##### The CPU

###### Control unit

- all computer resources
- input/output devices 的交流合作
- reads & interprets instructions, determines the **sequence** of process
- timing & control signals

###### Arithmetic logic unit

主力，follow control unit

##### Storage

###### Primary Storage 内存

memory chips: store data & provide electric power

###### Secondary Storage 硬存

slower & cheaper storage: persistent x power

data & program stored, will load to **memory** when execute

##### Memory

primary memory: table of cells, one byte, each containing a unique address beginning with 0

电脑：4G - 32G

##### Execute program

program start ==> memory ==> CPU read it ==> run one instruction at a time ==> modify data ==> write back to memory



#### Software

Application program: sequence of instruction & decisions implemented

programming: design & implement programs

##### Algorithms

a sequence (order matter) of actions to accomplish a task

- Unambiguous 明确
- Executable 可执行
- Terminating 有结束

Problem solving: algorithm design

##### Pseudocode

half-way between natural language & programming language

easily translated into python



#### Python Language

1990's, Guido van Rossum

##### Programming Environment

##### python: interpreter

![image-20211021161801683](C:\Users\Lenovo\AppData\Roaming\Typora\typora-user-images\image-20211021161801683.png)

##### PyCharm: IDE

- List line numbers

- Color lines of codes
- Auto-indent source code
- Output window
- Debugger



#### Error

##### Compile-time Error (aka syntax errors)

- 标点，拼写，大小写
- 语句顺序，括号没括死，引号没引上
- 没有可执行程序

- crash
- 运行了但没完全运行（奇怪的结果出现了
- 除以0
- 输出拼写错误（hello word）
- 没写输出



```python
# 把内容集中在一行
print("Hello there.", end=" ")
print("My name is...", end=" ")
print("Carl?", end=" ")

# 换行
print("\n1\n2\n3")
# \n会换行
print("hello")
# print结尾（打印hello后）本身会换一行
print()
# whitespace
print("go!")

# ,和+的区别
num = input("How many people are there? ")
print("there are", num, "people.")
print("there are "+num+" people.")

# Common error types

# syntax error 语法错误
# 如：一行有多个print，括号没括上，引号不对应

# runtime error 运行错误 -- crash
# 包含: value error, name error, type error, indentation error.
# 如：int(input())输入了一个字符串，"hello"*"ABC"等

# Indentation error: the lines of the programs are not properly indented
# Value error: An invalid value is used - can occur if giving letters in int()
# Name error: the program tries to use a variable that does not exist
# Type error: an operation uses incorrect types - can occur if adding an integer to a string.

# logic error 逻辑错误 -- bug
# 没有报错，但输出结果有问题,hard to debug

# Whitespace: black space or newline

# Identifiers (name) 变量命名法
# identifier: sequence of letters, underscores, digits,
# and must start with a letter or an underscore.
# Python is case sensitive, means Cats and cats are different.
# Reserved words (keywords): words that are part of the language.
# good practice：全部小写，下划线放在单词之间，有意义
# —— from python style guide (PEP 8)

# KEYWORDS
'''
False    await    else    import    pass    None    break    except
in       raise    True    finally   class   is      return   continue
and      for      lambda  try       as      def     from     nonlocal
while    assert   del     global    not     with    async    elif
if       or       yield
'''

'''
LOOP: a program construct that repeatedly executes the loop's statements (loop body) 
while the loop's expression is true, when false, execution proceeds past the loop. 
Each time through a loop's statements is called an iteration.
'''
# Example
curr_power = 2
user_char = 'y'

while user_char == 'y':
    print(curr_power)
    curr_power = curr_power * 2
    user_char = input("input char")

print('Done')
```



### **LOOP**

a program construct that repeatedly executes the loop's statements (**loop body**) while the loop's expression is true, when false, execution proceeds past the loop. Each time through a loop's statements is called an **iteration**.



#### **While loop**

Example

```python
curr_power = 2
user_char = 'y'

while user_char == 'y':
    print(curr_power)
    curr_power = curr_power * 2
    user_char = input()
    
print('Done')
```

Sentinel value:

```python
while user_value != 'q':
```

- the letter q is the sentinel value, allow a user to end a face-drawing program by entering the character 'q'

Random number: 

```python
randint(0,20)
```

0-20 的随机数

Loop variable: a variable that count the number of iterations.



#### **For loop**

```python
for name in ['Bill','Nicole','Johnson']:
    print('Hi {}!'.format(name))
```

Output: 

Hi Bill!

Hi Nicole!

Hi Johnson!



##### For loop 遍历 dictionary using a variable called c

```python
channels = {
    'MTV': 35,
    'CNN': 28,
    'FOX': 11,
    'NBC': 4,
    'CBS': 12
}

for c in channels:
    print('{} is on channel {}'.format(c, channels[c]))
```

Output:

MTV is on channel 35
CNN is on channel 28
FOX is on channel 11
NBC is on channel 4
CBS is on channel 12

```python
for price in my_prices:
↑ Iterate over the list my_prices using a variable called price.
for number in '911':
↑ Iterate the string '911' using a variable called number.
```

##### For loop 遍历 list using a variable called day

```python
daily_revenues = [
    2356.23,  # Monday
    1800.12,  # Tuesday
    1792.50,  # Wednesday
    2058.10,  # Thursday
    1988.00,  # Friday
    2002.99,  # Saturday
    1890.75   # Sunday
]

total = 0
for day in daily_revenues:
    total += day

average = total / len(daily_revenues)

print('Weekly revenue: ${:.2f}'.format(total))
print('Daily average revenue: ${:.2f}'.format(average))
```

For loop iterate backwards

```python
for name in reversed(names):
```

##### The range() function

- `range(Y)` generates a sequence of all non-negative integers less than Y.
  Ex: `range(3)` creates the sequence 0, 1, 2.
- `range(X, Y)` generates a sequence of all integers >= X and < Y.
  Ex: `range(-7, -3)` creates the sequence -7, -6, -5, -4.
- `range(X, Y, Z)`, where Z is positive, generates a sequence of all integers >= X and < Y, incrementing by Z.
  Ex: `range(0, 50, 10)` creates the sequence 0, 10, 20, 30, 40.
- `range(X, Y, Z)`, where Z is negative, generates a sequence of all integers <= X and > Y, incrementing by Z.
  Ex: `range(3, -1, -1)` creates the sequence 3, 2, 1, 0.

##### The enumerate() function

A programmer commonly requires both the current position index and corresponding element value when iterating over a sequence.

方法一

```python
origins = [4, 8, 10]

for index in range(len(origins)):
    value = origins[index]  
    print('Element {}: {}'.format(index, value))
```

方法二

```python
origins = [4, 8, 10]
for value in origins:
    index = origins.index(value)  
    print('Element {}: {}'.format(index, value))
```

方法三

```python
origins = [4, 8, 10]

for (index, value) in enumerate(origins):
    print('Element {}: {}'.format(index, value))
```

The **enumerate()** function yields a new tuple each iteration of the loop, containing the current index and corresponding element value.

The for loop *unpacks* the tuple yielded by each iteration of `enumerate(origins)` into two new variables: "index" and "value". **Unpacking** is a process that performs multiple assignments at once, binding comma-separated names on the left to the elements of a sequence on the right. Ex: `num1, num2 = [350, 400]` is equivalent to the statements `num1 = 350` and `num2 = 400`.

<span style="color:green">**EXAMPLE**</span>

```python
for (index, value) in enumerate(my_list):
    print(index, value)
```

If `my_list = ['Greek', 'Nordic', 'Mayan']`, the output is:

0 Greek
1 Nordic
2 Mayan



##### Compare

When the **number of iterations** is <span style="color:red">known</span>, use for loop, because it's more easily to make mistake with while loop in this situation since a programmer may easily forget to increment a while loop's variable (causing an infinite loop)

##### Nested loops 套娃

Consists of: **outer loop** & **inner loop**

```python
for i in range(2):
    for j in range(3):
        #inner loop body
how many times will the inner loop body execute?
6
```

#### Break & Continue

A **break** statement in a loop causes the loop to exit immediately.

```python
for num_tacos in range(max_tacos + 1):
    for num_empanadas in range(max_empanadas + 1):
        meal_cost = (num_empanadas * empanada_cost) + (num_tacos * taco_cost)

        if meal_cost == user_money:
            break

    if meal_cost == user_money:
        break
```

A **continue** statement in a loop causes an immediate jump to the while or for loop header statement. Can improve the readability of a loop.

```python
for num_empanadas in range(max_empanadas + 1):
    if (num_tacos + num_empanadas) % num_diners != 0:
            continue
```

### **FUNCTION**

A **function definition** consists of the new function's name and a block of statements

A **function call** is an invocation（调用）of the function's name, causing the function's statement to execute.

The **def** keyword is used to create new functions.

##### Return statement

```python
def compute_square(num_to_square):
    return num_to_square * num_to_square
```

- can only return one thing at a time

- **Void function: **no return statement / return statement with no following expression: returns the value **None**

  ```python
  def print_summary(oid, items, price):
  
  	print('Order {}:'.format(oid))
  	print('   Items: {}'.format(items))
  	print('   Total: ${:.2f}'.format(price))
  
  
  print_summary(oid, items, price)
  ```

  ##### Calling a print function multiple times

  只需要写一遍，防止重复出错



**Parameter**: a function input specified in a function definition. CANNOT be an expression.

**Argument**: a value provided to a function's parameter during a function call.

E,G,: calc_pizza_area(12.0)



##### Multiple parameter

```python
def calc_pizza_volume(pizza_diameter, pizza_height):
   pi_val = 3.14159265

   pizza_radius = pizza_diameter / 2.0
   pizza_area = pi_val * pizza_radius * pizza_radius
   pizza_volume = pizza_area * pizza_height
   return pizza_volume

print('12.0 x 0.3 inch pizza is {:.3f} cubic inches.'
     .format(calc_pizza_volume(12.0, 0.3)))
```



##### Hierarchical function calls (Nested function calls) 套娃calls

```python
user_input = int(input())
```



##### Dynamic and Static Typing

**Polymorphism**: The behavior of an operator, such as + or *, depends on the type of the operands. 说人话：The function behavior of being able to add together different types. E.G. add() 可以 add(5,7)也可以add("Tora","Bora")

**Dynamic typing:** determine the type of objects, such as python

**Static typing**: requires to define the type of every variable and every function parameter in a program's source code. Such as Java, C, C++



**Function Stubs**: function definitions whose statements haven't been written yet. 配合**pass**使用更佳哦~

pass: keyword, performs no operation except to act as a placeholder for a required statement.

A program that requires user input should not execute if the user-defined function that gets input is not completed. In such cases, a **NotImplementedError** can be generated with the statement *raise NotImplementedError*, indicates that the function is not implemented and causes the program to stop execution

```python
import math

def get_points(num_points):
    """Get num_points from the user. Return a list of (x,y) tuples."""
    raise NotImplementedError
        
def side_length(p1, p2):
    return math.sqrt((p2[0] - p1[0])**2 + (p2[1] - p1[1])**2)

def get_perimeter_length(points):
    perimeter = side_length(points[0], points[1])
    perimeter += side_length(points[0], points[2])
    perimeter += side_length(points[1], points[2])
    return perimeter

coordinates = get_points(3)
print('Perimeter of triangle:', get_perimeter_length(coordinates))
```

modify(my_list[:])

默认参数值

```python
def append_to_list(value, my_list=None):  # Use default parameter value of None
    if my_list == None:  # Create a new list if a list was not provided
        my_list = []

    my_list.append(value)
    return my_list

numbers = append_to_list(50)  # default list appended with 50
print(numbers)
numbers = append_to_list(100)  # default list appended with 100
print(numbers)
```

任意长度list

*args

```python
def print_sandwich(bread, meat, *args): 
    print('{} on {}'.format(meat, bread), end=' ') 
    if len(args) > 0: 
        print('with', end=' ') 
    for extra in args: 
        print(extra, end=' ') 
    print('')


print_sandwich('sourdough', 'turkey', 'mayo')
print_sandwich('wheat', 'ham', 'mustard', 'tomato', 'lettuce')
```

任意长度dictionary

***\*kwargs**

```python
def print_sandwich(bread, meat, **kwargs):
    print('{} on {}'.format(meat, bread))
    for category, extra in kwargs.items():
        print('   {}: {}'.format(category, extra))

print_sandwich('sourdough', 'turkey', sauce='mayo')
print_sandwich('wheat', 'ham', sauce1='mustard', veggie1='tomato', veggie2='lettuce')
```

！都要放在最后



Multiple output

Using **tuple** （用逗号隔开）

```python
student_scores = [75, 84, 66, 99, 51, 65]

def get_grade_stats(scores):
    # Calculate the arithmetic mean
    mean = sum(scores)/len(scores)
    
    # Calculate the standard deviation
    tmp = 0
    for score in scores:
        tmp += (score - mean )**2
    std_dev = (tmp/len(scores))**0.5

    # Package and return average, standard deviation in a tuple
    return mean, std_dev

# Unpack tuple
average, standard_deviation = get_grade_stats(student_scores)

print('Average score:', average)
print('Standard deviation:', standard_deviation)
```



### **LIST**

mutable, able to grow and shrink without program having to replace the entire list.

In-place modification: the growing and shrinking capability.

| Operation                    | Description                                                  | Example code                                                 | Example output    |
| ---------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ----------------- |
| my_list = [1, 2, 3]          | Creates a list.                                              | `my_list = [1, 2, 3] print(my_list)`                         | `[1, 2, 3]`       |
| list(iter)                   | Creates a list.                                              | `my_list = list('123') print(my_list)`                       | `['1', '2', '3']` |
| my_list[index]               | Get an element from a list.                                  | `my_list = [1, 2, 3] print(my_list[1])`                      | `2`               |
| my_list[start:end]           | Get a *new* list containing some of another list's elements. | `my_list = [1, 2, 3] print(my_list[1:3])`                    | `[2, 3]`          |
| my_list1 + my_list2          | Get a *new* list with elements of my_list2 added to end of my_list1. | `my_list = [1, 2] + [3]  print(my_list)`                     | `[1, 2, 3]`       |
| my_list[i] = x               | Change the value of the ith element in-place.                | `my_list = [1, 2, 3] my_list[2] = 9  print(my_list)`         | `[1, 2, 9]`       |
| my_list[len(my_list):] = [x] | Add the elements in [x] to the end of my_list. The append(x) method (explained in another section) may be preferred for clarity. | `my_list = [1, 2, 3] my_list[len(my_list):] = [9] print(my_list)` | `[1, 2, 3, 9]`    |
| del my_list[i]               | Delete an element from a list.                               | `my_list = [1, 2, 3] del my_list[1] print(my_list)`          | `[1, 3]`          |

#### List Method

| List method         | Description                             | Code example                              | Final my_list value |
| ------------------- | --------------------------------------- | ----------------------------------------- | ------------------- |
| **Adding elements** |                                         |                                           |                     |
| list.append(x)      | Add an item to the end of list.         | `my_list = [5, 8]my_list.append(16)`      | `[5, 8, 16]`        |
| list.extend([x])    | Add all items in [x] to list.           | `my_list = [5, 8]my_list.extend([4, 12])` | `[5, 8, 4, 12]`     |
| list.insert(i, x)   | Insert x into list *before* position i. | `my_list = [5, 8]my_list.insert(1, 1.7)`  | `[5, 1.7, 8]`       |

| Removing elements |                                               |                                            |                    |
| ----------------- | --------------------------------------------- | ------------------------------------------ | ------------------ |
| list.remove(x)    | Remove first item from list with value x.     | `my_list = [5, 8, 14]my_list.remove(8)`    | `[5, 14]`          |
| list.pop()        | Remove and return last item in list.          | `my_list = [5, 8, 14]val = my_list.pop()`  | `[5, 8]` val is 14 |
| list.pop(i)       | Remove and return item at position i in list. | `my_list = [5, 8, 14]val = my_list.pop(0)` | `[8, 14]` val is 5 |

| Modifying elements |                                        |                                         |              |
| ------------------ | -------------------------------------- | --------------------------------------- | ------------ |
| list.sort()        | Sort the items of list in-place.       | `my_list = [14, 5, 8]my_list.sort()`    | `[5, 8, 14]` |
| list.reverse()     | Reverse the elements of list in-place. | `my_list = [14, 5, 8]my_list.reverse()` | `[8, 5, 14]` |

| Miscellaneous |                                                  |                                                     |            |
| ------------- | ------------------------------------------------ | --------------------------------------------------- | ---------- |
| list.index(x) | Return index of first item in list with value x. | `my_list = [5, 8, 14]print(my_list.index(14))`      | Prints "2" |
| list.count(x) | Count the number of times value x is in list.    | `my_list = [5, 8, 5, 5, 14]print(my_list.count(5))` | Prints "3" |

#### Iterating over a list 遍历列表

```python
for my_var in my_list:
    # Loop body statements go here
```

| Function  | Description                                                  | Example code                                 | Example output |
| --------- | ------------------------------------------------------------ | -------------------------------------------- | -------------- |
| all(list) | True if every element in list is True (!= 0), or if the list is empty. | `print(all([1, 2, 3]))print(all([0, 1, 2]))` | `True False`   |
| any(list) | True if any element in the list is True.                     | `print(any([0, 2]))print(any([0, 0]))`       | `True False`   |
| max(list) | Get the maximum element in the list.                         | `print(max([-3, 5, 25]))`                    | `25`           |
| min(list) | Get the minimum element in the list.                         | `print(min([-3, 5, 25]))`                    | `-3`           |
| sum(list) | Get the sum of all elements in the list.                     | `print(sum([-3, 5, 25]))`                    | `27`           |

*any(list): 元素除了是 0、空、FALSE 外都算 TRUE



#### List Nesting 喜闻乐见的套娃

```python
my_list = [[10, 20], [30, 40]]
print('First nested list:', my_list[0])
print('Second nested list:', my_list[1])
print('Element 0 of first nested list:', my_list[0][0])
```

Output:

First nested list: [10, 20]
Second nested list: [30, 40]
Element 0 of first nested
List: 10

List nesting: allows to create a **multi-dimensional data structure**, the simplest being a two-dimensional table, like a spreadsheet.

```python
tic_tac_toe = [
    ['X', 'O', 'X'],
    [' ', 'X', ' '],
    ['O', 'O', 'X']
]

print(tic_tac_toe[0][0], tic_tac_toe[0][1], tic_tac_toe[0][2])
print(tic_tac_toe[1][0], tic_tac_toe[1][1], tic_tac_toe[1][2])
print(tic_tac_toe[2][0], tic_tac_toe[2][1], tic_tac_toe[2][2])
```

Output:

X O X
    X  
O O X

##### 用Enumerate() 遍历多重list

```python
currency = [
   [1, 5, 10 ],  # US Dollars
   [0.75, 3.77, 7.53],  #Euros
   [0.65, 3.25, 6.50]  # British pounds
]
for row_index, row in enumerate(currency):
   for column_index, item in enumerate(row):
       print('currency[{}][{}] is {:.2f}'.format(row_index, column_index, item))
```

Output:

currency\[0][0] is 1.00
currency\[0][1] is 5.00
currency\[0][2] is 10.00
currency\[1][0] is 0.75
currency\[1][1] is 3.77
currency\[1][2] is 7.53
currency\[2][0] is 0.65
currency\[2][1] is 3.25
currency\[2][2] is 6.50



#### List Slicing

**Slice notation**: read multiple elements from a list, creating a new list that contains only the desired elements.

<span style="color:green">as in `my_list[0:2]`. The 0 is the position of the first element to read, and the 2 indicates last element. Every element between 0 and 2 from my_list will be in the new list. The end position, 2 in this case, is *not* included in the resulting list.</span>

##### Stride

indicates how many elements are skipped between extracted items in the source list.

The expression my_list[0:5:2] has a stride of 2, thus skipping every other element, and resulting in a slice that contains the elements in positions 0, 2, and 4. The default stride value is 1

##### COMMON SLICE OPERATION

| Operation                 | Description                                                  | Example code                                         | Example output        |
| ------------------------- | ------------------------------------------------------------ | ---------------------------------------------------- | --------------------- |
| my_list[start:end]        | Get a list from start to end (minus 1).                      | `my_list = [5, 10, 20]print(my_list[0:2])`           | `[5, 10]`             |
| my_list[start:end:stride] | Get a list of every stride element from start to end (minus 1). | `my_list = [5, 10, 20, 40, 80]print(my_list[0:5:3])` | `[5, 40]`             |
| my_list[start:]           | Get a list from start to end of the list.                    | `my_list = [5, 10, 20, 40, 80]print(my_list[2:])`    | `[20, 40, 80]`        |
| my_list[:end]             | Get a list from beginning of list to end (minus 1).          | `my_list = [5, 10, 20, 40, 80]print(my_list[:4])`    | `[5, 10, 20, 40]`     |
| my_list[:]                | Get a copy of the list.                                      | `my_list = [5, 10, 20, 40, 80]print(my_list[:])`     | `[5, 10, 20, 40, 80]` |

**Slice notation** has the form `my_str[start:end]`, which creates a new string whose value contains the characters of `my_str` from indices start to end - 1. If `my_str` is 'Boggle', then `my_str[0:3]` yields string 'Bog'. Other sequence types like lists and tuples also support slice notation.

**Negative numbers** can be used to specify an index relative to the end of the string. Ex: If the variable `my_str` is 'Jane Doe!?', then `my_str[0:-2]` yields 'Jane Doe' because the -2 refers to the second-to-last character '!' (and the character at the end index is not included in the result string).



A list of common slicing operations a programmer might use. Assume the value of my_str is 'http://en.wikipedia.org/wiki/Nasa/'

| Syntax          | Result                            | Description                                                  |
| --------------- | --------------------------------- | ------------------------------------------------------------ |
| `my_str[10:19]` | wikipedia                         | Gets the characters in indices 10-18.                        |
| `my_str[10:-5]` | wikipedia.org/wiki/               | Gets the characters in indices 10-28.                        |
| `my_str[8:]`    | n.wikipedia.org/wiki/Nasa/        | All characters from index 8 until the end of the string.     |
| `my_str[:23]`   | http://en.wikipedia.org           | Every character up to index 23, but not including my_str[23]. |
| `my_str[:-1]`   | http://en.wikipedia.org/wiki/Nasa | All but the last character.                                  |

**Stride**

```python
numbers = '0123456789'

print('All numbers: {}'.format(numbers[::]))
print('Every even number: {}'.format(numbers[::2]))
print('Every third number between 1 and 8: {}'.format(numbers[1:9:3]))
```

##### Split() Method

**split()** splits a string into a list of tokens. Each **token** is a substring that forms a part of a larger string. A **separator** is a character or sequence of characters that indicates where to split the string into tokens.

<p style = "color:green"> Ex: `'Martin Luther King Jr.'.split()` splits the string literal "Martin Luther King Jr." using any whitespace character as the default separator and returns the list of tokens ['Martin', 'Luther', 'King', 'Jr.'].


<p style = "color:green">The separator can be changed by calling split() with a string argument. Ex: `'a#b#c'.split('#')` uses the "#" separator to split the string "a#b#c" into the three tokens ['a', 'b', 'c'].</p>

join() Method

```python
path = input('Enter file name: ')

new_separator = input('Enter new separator: ')
tokens = path.split('/')
print(new_separator.join(tokens))
```

Output:

![image-20211020110526538](C:\Users\Lenovo\AppData\Roaming\Typora\typora-user-images\image-20211020110526538.png)



#### Loops Modify List

```python
for num in nums:
    if num < 0:
        num = 0 
错！
for pos in range(len(nums)):
    if nums[pos] < 0:
        nums[pos] = 0
对了！
```

加一个副本不影响iterate

```python
nums1 = [5, 10, 15]
nums2 = [10, 15]

for val in nums1[:]:
    if val in nums2:
        nums1.remove(val)
```

#### Sorting list

##### **sort()**: 

in-place rearranging of the list elements, sorting the elements from lowest to highest.

```python
books = []
prompt = 'Enter new book: '
user_input = input(prompt).strip()

while (user_input.lower() != 'exit'):
    books.append(user_input)
    user_input = input(prompt).strip()

books.sort()

print('\nAlphabetical order:')
for book in books:
    print(book)
```

output:

Enter new book: Pride, Prejudice, and Zombies
Enter new book: Programming in Python
Enter new book: Hackers and Painters
Enter new book: World War Z
Enter new book: exit

Alphabetical order:
Hackers and Painters
Pride, Prejudice, and Zombies
Programming in Python
World War Z

##### **sorted()**: 

built-in function provides the same sorting functionality as the list.sort() method, however, sorted() creates and returns a **new** list instead of modifying an existing list.

```python
numbers = [int(i) for i in input('Enter numbers: ').split()]

sorted_numbers = sorted(numbers)

print('\nOriginal numbers:', numbers)
print('Sorted numbers:', sorted_numbers)
```

Output:

Enter numbers: -5 5 -100 23 4 5
Original numbers: [-5, 5, -100, 23, 4, 5]
Sorted numbers: [-100, -5, 4, 5, 5, 23]

<h5>Key:</h5>

Both the list.sort() method and the built-in sorted() function have an optional **key** argument. The key specifies a function to be applied to each element prior to being compared. Examples of key functions are the string methods str.lower, str.upper, or str.capitalize.

<span style="color:green"> Ex: A programmer might want to sort a two-dimensional list by the max of the rows, which can be accomplished by assigning key with the built-in function max, as in: sorted(x, key=max).</span>

```python
my_list = [[25], [15, 25, 35], [10, 15]]

sorted_list = sorted(my_list, key=max)

print('Sorted list:', sorted_list)
```

Output:

Sorted list: [[10, 15], [25], [15, 25, 35]]

##### Reverse:

`sorted([15, 20, 25], reverse=True)` produces a list with the elements [25, 20, 15].

### **Files**

#### Reading file

```python
print('Opening file myfile.txt.')
f = open('myfile.txt')  # create file object

print('Reading file myfile.txt.')
contents = f.read()  # read file text into a string

print('Closing file myfile.txt.')
f.close()  # close the file

print('\nContents of myfile.txt:\n', contents)
```

##### read():

returns the file contents as a string

##### readlines():

returns a **list** of strings. 

E.G. 

 my_file = open('readme.txt') 
 lines = my_file.readlines() 

my_file.readlines() reads the contents of readme.txt and stores each line as an element in the "lines" list.

##### close()

close the file, after which no more reads or writes to the file are allowed.

#### Writing file:

```python
num1 = 5
num2 = 7.5
num3 = num1 + num2

f = open('myfile.txt', 'w')
f.write(str(num1))
f.write(' + ')
f.write(str(num2))
f.write(' = ')
f.write(str(num3))
f.close()
```

Final contents of myfile.txt:

5 + 7.5 = 12.5

#### Mode:

Modes for opening files.

| Mode | Description                                                  | Allow read? | Allow write? | Create missing file? | Overwrite file? |
| ---- | ------------------------------------------------------------ | ----------- | ------------ | -------------------- | --------------- |
| 'r'  | Open the file for reading.                                   | Yes         | No           | No                   | No              |
| 'w'  | Open the file for writing. If file does not exist then the file is created. Contents of an existing file are overwritten. | No          | Yes          | Yes                  | Yes             |
| 'a'  | Open the file for appending. If file does not exist then the file is created. Writes are added to end of existing file contents. | No          | Yes          | Yes                  | No              |
| 'a+' | Opens the file for both reading and writing, appending new writes. | yes         | yes          | yes                  | yes             |



### **Appendix**

String interpolation: print("the number is {%d}".format(integer))

Mutable: 可更改的, Lists

Immutable: 不可更改的, String

Constant: use all caps for a variable name (e.g., PI_VALUE)



















