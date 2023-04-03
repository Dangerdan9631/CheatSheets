# Python
## Overview
* Python is an interpreted language.
* Python is cross platform.
* Python uses automatic garbage collection.
* Python supports object oriented classes.
* Python supports functional concepts like lambda functions and map/reduce/filter operations.
* Use `pip` package manager to install and manage packages

## Installing Python
https://www.python.org/downloads/
* Add Python to PATH to invoke from command line.

## Execution
Execute python interactive shell.
```shell
python
```
Execute a line of python code.
```shell
python <python code>
```
Execute the python script in a `.py` file.
```shell
python <filename>
```

## Basics
Comments start with `#`
```python
# This is a comment
x = 10 # This is also a comment
```

Variables are dynamically typed
```python
x = 5
name = "John"
```

Console IO
```python
print "Hello, Python!"
input = input("Enter your name: ")
```

Python uses indentation to denote code blocks. 

`\` can be used to create multiline statements 
```python
total = item_one + \
        item_two + \
        item_three
```

`;` can be used to put multiple statments on the same line.
```python
x = 'foo'; sys.stdout.write(x + '\n')
```

## Data Types
```python
# Boolean
x = True
x = False

# Integer
x = 5

# Long
xL = 5L

# Float
y = 3.14

# String
name = "John"

# List
my_list = [1, 2, 3]

# Tuple
my_tuple = (1, 2, 3)

# Set
my_set = {1, 2, 3, 4}

# Dictionary
my_dict = {"name": "John", "age": 30}
```

## Operators
```python
# Arithmetic
x = 5 + 2
y = 10 - 3
z = 2 * 4
w = 10 / 2
v = 107 % 3 # modulus
u = 2 ** 3  # exponent
t = 9 // 2  # floor division (rounded towards negative infinity)
# All arithmetic operators can also be assignment operators: +=, /=, %=, ...

# Comparison
x = 5 > 3
y = 10 <= 20
z = "John" == "john"
w = "John" != "john"
v = "John" <> "john" # Same as !=

# Binary
x = 0 & 1   # AND
y = 0 | 1   # OR
z = 0 ^ 1   # XOR
w = ~1      # Binary one's complement
v = 2 << 1  # Shift left (and shift right >>)

# Logical
x = True and False
y = True or False
z = not True

# Membership
x = 10 in sequence
y = 20 not in sequence

# Identity
# Indicates whether variables point to the same object.
x = a is b
y = a is not b
```

## Control Flow
```python
if x > 5:
    print("x is greater than 5")
else:
    print("x is les than or equal to 5")

if x > 5 : print("x is greather than 5")

for i in range(10):
    print(i)

i = 0
while i < 10:
    print(i)
    i += 1

while True:
    if x == 5:
        break

for i in range(10):
    if i % 2 == 0:
        continue
    print(i)
```


## Strings
```python
word = `word`
sentence = "This is a sentence."
paragraph = """This is a paragraph. It is
made up of multiple lines and sentences."""
```

```python
str = 'Hello World!'

print str          # Prints complete string                     "Hello World!"
print str[0]       # Prints first character of the string       "H"
print str[2:5]     # Prints characters starting from 3rd to 5th "llo"
print str[2:]      # Prints string starting from 3rd character  "llo World!"
print str * 2      # Prints string two times                    "Hello World!Hello World!"
print str + "TEST" # Prints concatenated string                 "Hello World!TEST"
```

Format strings
```python
num = 10
str = f'{num} + 10 = {num + 10}'
print str
```

Looping
```python
for char in "foo":
    print(char)
```

Functions
```python
# Length
hello = "Hello, World!"
print(len(hello))

# Format
str = "My name is {fname}, I'm {age}".format(fname="John", age=30)
str2 = "My name is {0}, I'm {1}".format("John", 30)
str3 = "My name is {}, I'm {}".format("John", 30)

# Join
"#".join(["John", "Peter", "Vicky"]) # Outputs: 'John#Peter#Vicky'

# Searching
"!" in "Hello, World!"          # True
"Hello, world!".endswith("!")   # True
```

Slicing
```python
s = 'mybacon'
s[2:5]          # 'bac'
s[0:2]          # 'my'
s[:2]           # 'my'
s[2:]           # 'bacon'
s[:2] + s[2:]   # 'mybacon'
s[:]            # 'mybacon'
s[-5:-1]        # 'baco'
s[2:6]          # 'baco'
```

## Lists
Values stored in a list can be accessed using the slice operator (`[]` and `[:]`) with indexes starting at 0 and ending at -1.


```python
list = [ 'abcd', 786, 2.23, 'john', 70.2 ]
tinylist = [123, 'john']

print list              # Prints complete list                          ['abcd', 786, 2.23, 'john', 70.2]
print list[0]           # Prints first element of the list              abcd
print list[1:3]         # Prints elements starting from 2nd till 3rd    [786, 2.23]
print list[2:]          # Prints elements starting from 3rd element     [2.23, 'john', 70.2]
print tinylist * 2      # Prints list two times                         [123, 'john', 123, 'john']
print list + tinylist   # Prints concatenated lists                     ['abcd', 786, 2.23, 'john', 70.2, 123, 'john']
```

## Tuples
Tuples's size cannot be changed. They can be thought of as a read only list.
```python
tuple = ( 'abcd', 786 , 2.23, 'john', 70.2  )
tinytuple = (123, 'john')

print tuple               # Prints the complete tuple                               ('abcd', 786, 2.23, 'john', 70.2)
print tuple[0]            # Prints first element of the tuple                       abcd
print tuple[1:3]          # Prints elements of the tuple starting from 2nd till 3rd (786, 2.23)
print tuple[2:]           # Prints elements of the tuple starting from 3rd element  (2.23, 'john', 70.2)
print tinytuple * 2       # Prints the contents of the tuple twice                  (123, 'john', 123, 'john')
print tuple + tinytuple   # Prints concatenated tuples                              ('abcd', 786, 2.23, 'john', 70.2, 123, 'john')
```

## Sets
```python
# Creating two sets
set1 = {1, 2, 3, 4, 5}
set2 = {4, 5, 6, 7, 8}

# Adding an element to a set
set1.add(6)
print(set1)  # output: {1, 2, 3, 4, 5, 6}

# Removing an element from a set
set2.remove(8)
print(set2)  # output: {4, 5, 6, 7}

# Taking the union of two sets
set3 = set1.union(set2)
print(set3)  # output: {1, 2, 3, 4, 5, 6, 7}

# Taking the intersection of two sets
set4 = set1.intersection(set2)
print(set4)  # output: {4, 5}

# Taking the difference of two sets
set5 = set1.difference(set2)
print(set5)  # output: {1, 2, 3, 6}
```

## Dictionaries
```python
dict = {}
dict['one'] = "This is one"
dict[2]     = "This is two"

tinydict = {'name': 'john','code':6734, 'dept': 'sales'}


print dict['one']       # Prints value for 'one' key    This is one
print dict[2]           # Prints value for 2 key        This is two
print tinydict          # Prints complete dictionary    {'dept': 'sales', 'code': 6734, 'name': 'john'}
print tinydict.keys()   # Prints all the keys           ['dept', 'code', 'name']
print tinydict.values() # Prints all the values         ['sales', 6734, 'john']
```

## Functions
```python
def add_numbers(x, y):
    return x + y

result = add_numbers(5, 10)
```

## Classes
```python
class Person
    def __init__(self, name, age):
        self.name = name
        self.age = age

person1 = Person("John", 30)
```

## File Handling
```python
with open("myfile.txt", "r", encoding='utf8') as file:
    for line in file:
        print(line)
```

## Multiple Assignment
```python
a = b = c = 1
a,b,c = 1,2,"john"
```

## Data Type Conversion
Typically use type name as a function
```python
int(x [,base])  # Base is used if x is a string
long(x [,base]) # Base is used if x is a string
float(x)
complex(real [,imag])
str(x)
repr(x)     # Converts X to an expression string. This is the complement of eval(str).
eval(str)   # Evaluates a string as a python script
tuple(s)
list(s)
set(s)
dict(d)     # d must be a sequence of (key, value) tuples
frozenset(s)    # immutable set
char(x)     # int to character
unichr(x)   # int to unicode character
ord(x)      # character to integer value
hex(x)      # int to hexadecimal string
oct(x)      # int to octal string
```

## Conventions
* Class Names start with an upper case letter.
* All other identifiers start with lowercase letter.
* Private identifiers start with leading underscore.
* Strongly private identifiers start with two leading underscores.
  * Any value starting with two leading underscores will be mangled by the interpreter by adding `_classname` to the beginning.
* Language defined special names start and end with two underscores.

## Reserved Words
| | | |
|---        |---        |---
| and       | exec      | not
| assert    | finally   | or
| break     | for       | pass
| class     | from      | print
| continue  | global    | raise
| def       | if        | return
| del       | import    | try
| elif      | in        | while
| else      | is        | with
| except    | lambda    | yield


* import modules using the `import` keyword.
* Python supports exception handling using `try/except` block
  