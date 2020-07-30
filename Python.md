
- [Introduction](#introduction)
  - [Installation](#installation)
    - [Ubuntu](#ubuntu)
    - [Pip](#pip)
    - [Virtual Environment](#virtual-environment)
      - [venv](#venv)
    - [wheel](#wheel)
    - [Dynamic Language](#dynamic-language)
    - [Linting/Formatting](#lintingformatting)
  - [Variables](#variables)
    - [Data types](#data-types)
      - [Operators](#operators)
        - [Numerical functions](#numerical-functions)
      - [Strings](#strings)
        - [escape sequences](#escape-sequences)
        - [format strings](#format-strings)
        - [String Functions](#string-functions)
      - [Type Casting](#type-casting)
  - [Control Flow](#control-flow)
    - [Comparison operators](#comparison-operators)
      - [Chaining Comparison operators](#chaining-comparison-operators)
    - [Logical operators](#logical-operators)
    - [Conditional Statements](#conditional-statements)
      - [IF](#if)
        - [If else](#if-else)
        - [elif](#elif)
      - [Ternary operator](#ternary-operator)
    - [Iterative statements](#iterative-statements)
      - [Break](#break)
      - [Continue](#continue)
      - [For loops](#for-loops)
        - [For Else](#for-else)
      - [While loops](#while-loops)
      - [Nested Loops](#nested-loops)
      - [Iterables](#iterables)
  - [Functions](#functions)
    - [Parameters](#parameters)
    - [Arguments](#arguments)
      - [Default Arguments](#default-arguments)
      - [Keyword Arguments](#keyword-arguments)
      - [Variable Arguments](#variable-arguments)
      - [Global](#global)
    - [lambda](#lambda)
    - [Scope](#scope)
    - [NameSpace](#namespace)
  - [Data Structures](#data-structures)
    - [lists](#lists)
      - [Enumerate](#enumerate)
      - [Map](#map)
      - [Filter](#filter)
      - [List Comprehension](#list-comprehension)
      - [Zip](#zip)
      - [Unpacking Operator](#unpacking-operator)
    - [Tuple](#tuple)
      - [Swap](#swap)
      - [Generators](#generators)
    - [Set](#set)
    - [Dictionary](#dictionary)
      - [Dictionary Comprehension](#dictionary-comprehension)
    - [Stack](#stack)
    - [Queue](#queue)
    - [Array](#array)
  - [Exceptions](#exceptions)
    - [Multiple exceptions](#multiple-exceptions)
    - [Error object](#error-object)
    - [Else](#else)
    - [Finally](#finally)
    - [Finally vs Else](#finally-vs-else)
    - [Raising Exceptions](#raising-exceptions)
  - [Class](#class)
    - [Object](#object)
      - [\_\_init__()](#__init__)
        - [Self](#self)
      - [isinstance](#isinstance)
      - [Instance Members](#instance-members)
      - [Class Members](#class-members)
  - [Inheritance](#inheritance)
    - [Single Inheritance](#single-inheritance)
    - [Multi-Level Inheritance](#multi-level-inheritance)
    - [Multiple Inheritance](#multiple-inheritance)
    - [Hierarchical Inheritance](#hierarchical-inheritance)
    - [Hybrid Inheritance](#hybrid-inheritance)
    - [Object Class](#object-class)
  - [Polymorphism](#polymorphism)
    - [Method Overloading](#method-overloading)
    - [Method Overriding](#method-overriding)
  - [Encapsulation](#encapsulation)
  - [Abstraction](#abstraction)
    - [Abstract Class](#abstract-class)
      - [Abstract method](#abstract-method)
      - [Concrete method](#concrete-method)
    - [Interface](#interface)
  - [Higher Order Programming](#higher-order-programming)
    - [Function Decorator](#function-decorator)
    - [Class Decorator](#class-decorator)
    - [First Class Functions](#first-class-functions)
    - [Nested Function](#nested-function)

# Introduction
Python is an interpreted language.
Basic python is a language specification,that provides what should be done.This specification is used to create an implementation.        
Syntax is mostly common for all the below implementations.        
There are multiple implementations of python.         
1. Cpython:
   In cpython the python code is compiled to byte code,which is then interpreted.              
   Default implementation,the most used,officially supported implementation of python.              
   We can use c-libraries and c-modules inside python,which provides an improvement in speed.         
   When we download python from internet,It is a CPython implementation.        
2. Jython:This is written in java,can use JVM and java libraries,can't use C-libraries.
3. Ironpython:this is written in C#,can use .net's virtual machine
4. pypy.etc.,their are many more emerging technologies that may be better in future.

## Installation
To install python we download it from official python website depending on our platform.        
For Windows we have to download an exe.         
Mac and linux will have a default interpreter,that is used in the development of the O.S. So don't have to install.      

### Ubuntu
Ubuntu is a linux distribution,good for beginners entering linux world,Ubuntu is developed using multiple technologies and has C,Java,Python by default.          
* These version may be outdated or deeply linked to functionality of Operating System. So we shouldn't mess with it,which may result in Operating System malfunctions.   
* If we are comfortable with the default(existing) python interpreter version we can use it.  
* But if we want to use another interpreter version follow below steps.

**Running multiple Python Versions in Ubuntu:**    
There are four methods,to run multiple python interpreters with out errors.Prefer 4th     
1. Install from official repositories,which contains versions compatible by the O.S.      

        sudo apt install python3.x-version

2. Install from third party repository with a ppa,add the ppa,then install the interpreter with necessary tools/packages.     

        sudo apt install python3.9 python3.9-distutils python3.9-venv python3.9-dev

   * python3.9 is the latest version
   * python3.9-distutils is used to install packages with pip
   * python3.9-dev is used to compile packages with pip
   * python3.9-venv is used to create [Virtual Environments](#virtual-environment)

   * python3.9 is installed just like any other package/application,this won't effect existing python3.8 version.    
   * When running python file with this interpreter,we have to specify the full version,to distinguish from other interpreters.

            python3.9 somefile.py

   * Best practice is to create a [virtual environment](#virtual-environment) when ever running a python project.so our system/custom python install doesn't get bloated with packages/configs.
   * this may be dangerous  because it will install the python in system directory which can result in a dependency hell issue.
3. Download the python tar file,then extract and install from source
   * follow these commands,might have to tweak,copy pasted these.
   * Search install python version,ubuntu version,from source on google.

            sudo apt update        
            sudo apt install software-properties-common       
            sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev wget libbz2-dev            
            tar -xf Python-3.8.0.tgz           
            cd Python-3.8.0        
            ./configure --enable-optimizations       
            make -j 8        
            sudo make altinstall   

4. We use a package called pyenv,this was created to use multiple python versions without issues,this works by installing all the interpreters in the user environment and can even create virtual environments for them.
   * pyenv can install all the needed python versions.
   * after installing we can use the python  in multiple ways,
     * globally(entire system will use this),

            pyenv global versionnumber

     * locally(a folder with .python-version file uses this specific version),

            pyenv local versionnumber

     * shell(uses this python version till shell session)

            pyenv shell versionnumber

   * we can create virtual environments with pyenv,they will be located in pyenv directory.(not a great idea)  

            pyenv virtualenv pythonversionnumber environmentname       
        Example

            pyenv virtualenv 3.9 env             
   * Having all virtual environments in separate directory maybe prone to errors.
   * instead we can use the venv method inside pyenv.    

      * --->sets which version to use,in shell       

            pyenv shell versionnumber       

      * --->creates a local virtual environment,we do this in the same shell    

            python -m venv env           

      * --->activates virtual environment.               

            env env/bin/activate     

### Pip
1. Python Package Installer,is the default package management system for python,it is used to install modules,libraries from pypi.org repository.     

*  Pip is bundled with the python installation.     
*  pip was in use since python2, so if a system has both python2 and python3,then their will be two pip version,pip2/pip for python2,pip3 for python3.      
*  we can use the default pip by O.S's interpreter.For suppose O.S uses python3.8 then *pip* will use python3.8      

            pip3 install numpy

*  This Will install *numpy* in python3.8 global site-packages.        
*  We can have multiple python3.x versions but their will be only one pip for all of them
*  So we have to specify which interpreter to use when running,or the default interpreter is selected.
*  Now a days the following syntax is used even for a single python version,for better context.here -m is telling to run the module

            python3.8 -m pip install numpy
*  To upgrade pip use the below syntax

            python3.8 -m pip install --upgrade pip
*  So if we have a custom installation of python3.9,we use

            python3.9 -m pip install numpy
* we use `pip list` to show all the packages inside the site-packages of environment.
* will show all the packages in python2 interpreter global site-packages

            pip list 
* will show all the packages installed in python3(default version) interpreter global site-packages.

            pip3 list 
* will show packages in python3.8 site-packages.

            python3.8 -m pip list 
* In a Virtual Environment,We only have a copy of python,pip and setuptools to use.
* Any thing additional have to installed.
* When we are sharing other developers our code they might not have the dependencies needed,instead of uploading our environment directory to web,we create a *requirements.txt*/anyfilename.txt from pip and sent that.

            pip freeze > requirements.txt
* We use this file to install all the requirements on the end user pc.     

            pip install -r requirements.txt

### Virtual Environment
It is a best and most preferred practice to create a virtual environment for every project we work on.   
Virtual environments are great to isolate work environments from other projects,interpreters.      

* When we have multiple python versions,for example python2.7,python3.6,python3.8,python3.9 then we have to be very careful with installation and package management.     
* Virtual Environment makes this easy.         
* When we create a virtual Environment,the *python interpreter,pip,setuptools* are the only files that are copied to specified directory.None of the existing packages in site-packages are copied.                  
* So any new installations,modifications will sit inside that directory only.         
* Inside a virtual environment we can just use *python* to call  our interpreter,as their will only be one interpreter available inside it.
    * this is the default way to call a interpreter

            python3.9 file.py         

    * the above command uses python3.x inside the environment. 

            python file.py         

    * the above command uses the pip version inside the environment.

            pip install numpy         

* to remove a virtual environment, we can either deactivate it or delete the folder.

#### venv       
* To create a Virtual environment we have many methods.          
* Due to this,their can be so much confusion and chaos if not understood properly.       
* Before venv we used wrapper,virtualenv packages to create virtual environments.But venv solved many problems and made it easy,to create a Environment.     
* venv is a python package which comes by default with the python installation,if not,run the command to install

        sudo apt install python3.9-venv
  
*creating a virtual environment*.      

Syntax:     

    python3.9 -m venv environmentname.    

Ex:

    python3.9 -m venv env     

env is the most commonly used name for a virtual environment,we can change it to any thing.   

    python3.9 -m venv somethingtoputempfiles    

After creating the virtual environment we have to activate it in order to use it.  

    source dirlocation/env/bin/activate      

to stop using it we deactivate the environment.

    deactivate

The name of virtual environment is showed at the beginning of terminal to show it's inside a virtual environment.       
Any thing we install here, will be inside it and won't affect the global python packages.       
Ex:         
We can have a virtual environment using python3.9 and numpy package version 4.0.0      
Another virtual environment using python3.6 and numpy package version 2.2.0      
These two environments won't conflict and the global system wouldn't know which environment uses which package.      

### wheel         
When we distribute our code,project we are giving the people our source code,to use this in their computer,they have to compile,interpret it.      

To reduce the time of compilation we use pre-compiled packages,in python the latest type is wheels.      
Wheels is a pre-compiled binary,so it is highly coupled to the Operating System,architecture,Version of interpreter.       

So when we execute pip to install a package it will find the package in zip format or .whl format then unzips the contents and copies to site-packages ready to use.    

If the package is not a wheel format,we have to compile it following the specified methods to install it,in our system.       

### Dynamic Language
Python is a dynamic typed language,which means the data type of the variable doesn't need to be specified,the python interpreter will take care of it for us.     

In python we can change the data type of a variable,on fly,by inserting new type of data into a variable.      

* We can create variables with their name and assign value to it.      

    Ex:
    ```python
    name="something"     
    x=5     
    objectname=obj
    ```    

* We don't have to define the data type,python will assign automatically. 
* we can even change the data in a variable with different type,it will be casted automatically.

    Ex:
    ```python
    name=obj   
    x="somet"  
    objectname=5  
    ```

* This dynamic typing makes the language run slow but makes development easier and faster.That's why is preferred to use in machine learning where the problem is the complex one,while the language is easy to understand.  

### Linting/Formatting
* Linting is the concept of checking for error before running the project,this can reveal syntax errors that may take time to find,This is done while we type the code.
* Formatting is keeping the document code in a specific format,having exact number of tab spaces for each indentation,keeping spaces,arranging arguments etc., 
* Python follows PEP8 standards for code formatting.
* To use Linting we can install any linter program.Vscode support live linting.

        pip install pylint        
        pip install yanf         

## Variables
Python is a CASE-SENSITIVE language,so have to be careful with syntax and naming conventions.
We use variables to store data,In python their is no concept of data types, like in static typed languages.

### Data types
Even though we don't need to specify the data type of a variable,we have to be cautious about our variables,to make code better maintainable.      
**integer**,whole numbers 
**float**,decimal point numbers
**boolean**,True,False values.


Ex: 
```python
x = 1
x= 1.1
x = "1234"
x = objectname
```
![Variable Container](./SVG/variable_container.svg)

#### Operators
We can perform arithmetic operations on numerical data.     
operators in python are 
1. **+** addition
2. **\*** multiplication
3. **-** subtraction
4. **/** division
5. **%** modulus,returns the reminder of division instead of quotient 
6. **\*\*** power,exponent

We have sum short hand operators that can make code easy to read.
1. **+=** x+=3 this is same as x=x+3
2. **-=** x-=3 this is same as x=x-3
3. **\*=** x*=3 this is same as x=x*3
4. **/=** x/=3 this is same as x=x/3
5. **%=** x%=3 this is same as x=x%3
6. **\*\*=** x**=3 this is same as x=x**3

##### Numerical functions
These are some of most used mathematical methods
1. round():rounds of the input to nearest number
2. abs():returns the absolute value,the positive value
3. math.ceil():returns the highest number of input,2.2 will return 3


#### Strings
character values,should be inside either single/double quotes.

Ex:     
```python 
x="hello"
x='hello'
``` 
-->both are valid,    

To use single quotes inside our string we enclose them with double quotes,and vice versa.
We can use triple quotes to use formatted string.

Ex:
```python
x = """
this is a test   text

test is end
""" 
```   

##### escape sequences
To use symbols that have a meaning to python interpreter in our string we use escape sequences.    

| escape sequence | usage                  |
| --------------- | ---------------------- |
| \               | escape character       |
| \n              | goes to next line      |
| \t              | inserts a tab space    |
| \\\\            | inserts a backslash    |
| \'              | inserts a single quote |

##### format strings
To use multiple strings in print or our logic we need to format them.         
we use concatenation to join two strings,       
f/F(format) prefix to insert a variable inside a string.      

Syntax:     
```python
variablename="hel"
x=f'some string{variablename}'#this is new syntax since python 3.8    
s=string1 + string2    
s="hello"+"world"#we are concatenating two strings
```

##### String Functions
In python every thing is a object,so we can use the string class methods with a string variable.
**Important point** In python strings are immutable,i.e the methods are performed on a copy of string,original string is not changed.always a copy is returned. 
Following are the most commonly used string methods.
1. upper():returns a upper case string
2. lower():returns a lower case string
3. title():capitalizes the first letter of every word
4. strip():removes the starting and ending white spaces of a string.
5. find():returns the index of a string 
6. replace():replaces given string with specified string.
7. in: we use in method to check if a string/sequence of characters are present in a given string.


#### Type Casting
The process of conversion of one data type into other data type is called type casting.      
Two Types:
1. **Implicit Type Cast**:Type casting done by Python is implicit type casting.
2. **Explicit Type Cast**:Type casting done manually by the programmer is explicit casting

>we use this in times of taking user input,as it will always come as string.

We type cast by specifying the type of variable we want.
Syntax:         
```python 
x ="5"
print(int(x))
```
Ex:int(variable),float(variable),bool(variable),str(variable)

![Type Casting](./SVG/type_Casting.svg)

## Control Flow
Control flow defines how the execution of a program is handled.         
We control the execution in various ways.     

### Comparison operators
We can compare two statements,variables etc., with comparison operators.
comparison operators return a boolean value,True is comparison is true,False if comparison is false.
1. **>** less than
2. **<** greater than
3. **<=** less than or equal to
4. **>=** greater than or equal to
5. **==** is equal to
6. **!=** not equal to

#### Chaining Comparison operators
Instead of using two operators to check a values range between two values.          

Ex:
```python 
if age > 15 and age < 60     
```
we can use chaining option to write it simple,just like we write in maths.       

Ex:
```python 
if 15 < age < 60
```

### Logical operators
To control flow of execution we have multiple types of statements.      
They use either comparison or Logical operators,to determine the flow.        
logical operators, well perform a logic!

Logical operators are performed on two statements,variables.         
1. **and** returns True when both statements are True    
2. **or** returns True When at least one statement is True     
3. **not** returns True when Statement is False and Vice versa 


**short circuit evaluation**     
* When using *and*,even a single false statement means the entire condition is false.       
* the same can be applied to *or*,even a single true means entire condition is true.        
* So python interpreter doesn't check the remaining condition,to evaluated(as it already has the answer).        
* This process is called short circuit evaluation.         

### Conditional Statements
Conditional Statements are used to check a condition and if true a logic is performed

#### IF
If statement is the most commonly used conditional statement.        
When the condition is True the logic inside is executed.    

Syntax:
```python 
if (condition):
    logic 
```


Ex:   
```python
if (9>6):
    print('hello')
```
       
##### If else
If condition returns True,then if block code is executed,if condition returns False,then else block code is executed.      

Syntax:
```python
if (condition):
    logic
else:
    logic

```


Ex:
```python
if(9<7):
    print('hello')
else:
    print('bye')
```

##### elif
when we want to perform multiple conditional checks in one go,we can use elif.           
The execution flows from if to elif to else.          
When a condition is satisfied, the remaining conditions are not checked,so order of priority is needed.         

Syntax:
```python
if(condition):
    logic
elif(condition):
    logic
else:
    logic
```

Ex:
```python
if(9<7):
    print('hello')
elif(9<10):
    print('bye')
else:
    print("good bye")
```

#### Ternary operator
Ternary works the same way as if else,in just single line.     
We use ternary operator to write cleaner code.        

Syntax:     
```python 
logic if condition else logic
```

Ex:          
```python
message="test" if v == 18 else message="time"
```  

Here logic is a single line statement,can't have a block of code.    

### Iterative statements
Statements that needs to be repeated a certain number of times,we use iterative statements.     

#### Break  
We use Break inside loops,this will exit the immediate loop

#### Continue
We use continue in loops,will skip the code below it and loops next condition

#### For loops
For loops are the most used Iterative statements in any programming languages.         

Syntax:
```python
for variable in listtoiterate:
    logic

```

Here listtoiterate is a list/range/group of values to be iterated.        
this is the execution flow,         
1. variable is given the first value of list
2. code inside the loop is executed once
3. after execution ends,control moves back to for,then variable is given the next element in list
4. this process repeats till list is completed
5. once list is completed the loop ends.

Ex:      
```python
for i in range(5):
    print(i)
```

here *i* is the variable,initial value is zero     
*in* is the condition that checks whether a variable is in list,if i is not initialized,it takes value from the list.     
*range()* is a function that returns a list of values between specified range.         
here the loop runs 5 times.        

##### For Else
For else is used to execute statements after the execution of for block.      
The code in else block will only be executed when the for loop is executed successfully without any break.
If a Loop break is done, then else block will not be executed.

Syntax:     
```python
for condition:  
    logic   
else:   
    logic   
```
Ex:
```python
for i in range(3):
    print(i)
    if i==2:
        print(i)
        break#if break is executed,else block  won't be
else:
    print('done')
```

#### While loops
While loops are used when we don't know the exact number of repetitions to perform.         
If not careful with condition check, can result in 
infinite repetitions.Have to be careful and avoid them.     

Syntax:     
```python
while condition:
    logic
```

Ex:      
```python
x =10
while x > 0:
    print(x)
```

this code will run infinitely,since x is always 10 and greater than 0.          
so to make it quit we have to either increment the value each time,or give the user an option to exit,manually.                         

Ex:      
```python
x=10
while x>0:
    print(x)
    x--
```

this code will run 10 times.     

#### Nested Loops
When we keep a loop inside a inside it is called Nested loop.     
we can put any iterative loop inside another one.        
The major use of nested loops is when working with multiple dimensional data.       
this has to be done carefully,because it has time complexity of O(2^n)     
ex:      
consider a for loop that prints hi, ten times.        
another for loop inside it,that prints bye ten times.          
So for every one hi printed,ten bye statements are printed.          
Which results in total 100 bye prints.                
So have to careful when to use and where to use.          

#### Iterables
a object tha can used in loops to iterate over is called iterable object.         
some of the most used python iterable objects are 
Strings
range() values
lists

## Functions
A function is a block of code that can be reused any number of times.      
A function in general takes some input as arguments and return a output.         
Their are many built in function into the language.These functions can be used in our logic.  
In functional/sequential programming we call these Functions,In Object Oriente Programming we call these methods.            

We use our functions by calling them with their name and passing any required arguments.     

Syntax:
```python
def functionname(parameters):
    logic
functionaname(arguments)#calling a function
```

In programming their are two types of functions.      
Functions that 
1. Perform a Task    
   These functions take some data,And perform a Task.       
2. Return Data(preferred)    
   These Functions take some data,performs logic on data,returns the result      
   We use return keyword to **return** a value,object, etc.,    
**None**    
When the user tries to print a value,function that returns nothing,They will be given a **None** value.     
In python None means the absence of data.    

### Parameters
Parameters are the names of variables that are used inside a function.     
We use parameters to take input and work on them.     

Ex:    
```python
def add(x,y):#x,y are parameters
    logic
```  
Here x,y are place holders/variables/parameters for actual values,we create a logic using these variables.     

### Arguments
Arguments are the values given to parameters on function call.     

Ex:
```python
def add(x,y):#x,y are parameters
    logic
add(3,4)#3,4 are arguments
```

Here 3,4 are the arguments that are being passed on function call,these arguments are given to the parameters defined in function.     

* The arguments passed are matched by their position.      
add(x,y,name)        
add(3,4,'ironman')         
so 3 is matched to x,4 to y,'ironman' to name.      
* Missing arguments will raise an error.    

#### Default Arguments
We use default arguments,to avoid errors,when user doesn't pass the argument.       
These are used to provide some default behavior irrespective of user input.      
* all the default arguments should be at the last,after the user provided arguments.               
  
Ex:
```python 
def add(x=0,y=0):
    print(x+y)
add()#will return 0     
add(1)#will return 1    
add(1,3)#will return 4     
```

#### Keyword Arguments
* To make code more readable,we can assign the arguments to a variable, inside the function call.       
* These are called keyword arguments,they have to be the same name as the parameter name.       
    
Ex:
```python
def add(first,second):
    print(first+second)
add(3,4)#difficult to understand
add(first=3,second=4)#easy to read and valid code
```

#### Variable Arguments
When we want to pass arguments for a function,we have to define them.      
This becomes tiresome when their are 10 to 20 values or a list of values being passed.    
We can use variable arguments to take multiple inputs and iterate over them.     

**\*args**     
* \*args is used to take multiple *arguments* as a list of values.     
* We can then iterate over this list to get values.      
* can store from 0 to any number of values.          
* We have to provide *args at the end of arguments list.      
* As we don't know how many variables are being passed. 

Syntax:
```python 
def func(*variablename):
    logic
```

    
Ex:
```python
def add(y,z,*x):#valid,add(*x,y,z):--->invalid
    logic
add(1,2,3,4,5,6)
```

**\*\*kwargs**     
* \*\*kwargs is used to take multiple *Keyword arguments* as a dictionary of values.     
* We can use this dictionary to get values.      
* can store from 0 to any number of keyword arguments.          
* We have to provide **kwargs at the end of arguments list.      
* As we don't know how many *Keyword arguments* are being passed.


Syntax:
```python 
def func(**userdetails):
    logic
```

ex:     
```python 
def func(**user):           
    logic            

func(id=1,name="some",roll=234)
#these keyword arguments are packed into a dictionary by python.             
func(1,2,"some")#not valid          
```


The syntax to use both *args and **kwargs is   
```python 
def func(x,y,*args,**kwargs):
    logic

func("name","test",2,3,4,4,5,id=1,name="some")
```                
![Function Logic](./SVG/function_block.svg)


#### Global
We can access global variables inside a function,but we can't change it.      
To change the global variable we use the **global** keyword.            
Ex:      
```python 
x=5#global variable
def func():
    x=10#local variable
    print(x)
print(x)#global value 5
def func1():
    global x = 10#changing global   value
    print(x)
print(x)#global value 10
```

* This practice is controversial as some prefer it,while some disregard it completely.  
* Nevertheless we need to consider it's consequences
* Multiple functions might depend on a global variables,so changing this variable might cause a bug. 


### lambda
lambda is an anonymous function,that exists for one time use,can only have one expression       
syntax:        
```python 
lambda arguments:expression
```

ex:      
```python 
(lambda a : print(a+10))(5)#defining the function and passing arguments
x = lambda a: print(a+10)
x(5)#same as above
```

a lambda function can be inside another function.a normal function has to be encapsulated for this to work.       

### Scope
Scope is the level at which a single variable is accessible.         
There are Three Types of Variable Scopes.       
1. **Global Variables**       
   A Global Variable can be accessed by any function inside a python file(module)            
   Ex:  
```python 
collegename="Oxford university"        
def function():       
    print(collegename)#accessible         
```          
2. **Local Variables**           
   * A Local Variable can only be accessed inside a single Function.               
   * If we try to access a local variable from another function.We will get a "not defined error".     
   * This can be used as an advantage,to create a better readable code,where each method can have same variable name.      
   * As they are only accessible inside a function,we don't have to worry about name errors.   
Ex:
```python 
def function():          
    studentname="somerandomdude"          
print(studentname)#not defined error            
```   

3. **Enclosed Variables**   
    In python we can have method inside method,[nested function](#nested-function),here we have a scope called enclosed variable.           
    We can't access variables inside a nested function.             
    * The variables in outer function is called non-local variable.
    * To modify nonlocal variable we use **nonlocal** keyword



Ex:
```python
def fun():
    x=5#enclosed variable
    def fun2():
        nonlocal x # can modify the enclosed variable
        x = 20
        print(x)# prints 20
        y = 10
        print(y)
```

![Scope](./SVG/Scope.svg)


### NameSpace
We name our functions,variables,class,packages.             
But we have to keep track of them and all of them have to unique to properly identify them.         
Ex: 
```python
x = 5 # here x is a variable
def y():# here y is a function
    print('hello')
```

But in production development we have to keep track of all the names,which gets tedious.    
That means we have to make sure our variables are named properly and not repeated,if repeated the data related to that name will be lost.   

Namespace is used to keep track of our naming process.  
* instead of keeping track of all names in a project,we track them in this order function,class,module,project.  
* Any repetition is okay,we identify each name with their group/namespace.
* We can import external modules,packages with same names in your code,but refer them with their namespace.

Ex:
```python
import extra
y = 5
class test:
    y = 10
    def func():
        x = 10#x is inside func,with its namespace
        print(x)

print(y)# accessing the variable name
print(test.y)#accessing variable with its namespace
extra.test()#calling test method inside extra module with namespace.
```

Name space are of two types
1. Local namespace
    * A local namespace is when we resolve different variables with same name,inside a function or class.
    * Ex: x =5 in function and x=10 in class,here we refer to class variable with classname.variable,here classname is its namespace.
    * Even though we have multiple variables with same name we have a unique variable with a namespace
2. Global namespace
    * Global namespace is when we use variables from another class or module in our code
    * We refer to it with the classname or module name

## Data Structures
Every Programming language structures data in one way or other.      
In Python we have 4 types of data.     

### lists
list is a ordered collection of items,similar to array.
* a list is mutable(editable),can change items in it.
  
syntax:  
```python
listname = ["items","items"]
```   

* we access the item with index number,starting from 0    
```python
listname[0]
```


* we access the item from last using negative values,from -1.       
here -1 is the last element in the list,-2 is the last second element in the list.            

```python
listname[-2]
```
* can access items in a range,this is slicing a list.      
* end of index is excluded,so items from 2,3,4 are returned.      
```python
listname[2:5]
```

* we can step/jump through items in list.returns every 2nd item.       
```python
listname[::2]
```


1. **clear()**    clears list items.  
2. **append()**   appends new value at the end of list
3. **insert()**   adds value at specified index
4. **pop()**      removes item at end of list.
5. **remove()**   removes specified value
6. **del**        can remove a range of items,'del list[index]'
7. **index()**    search the index of a item
8. **count()**    returns the number of times a item is present
9. **sort()**     sorts the items in a list,ascending or descending order

#### Enumerate
Enumerate is a method used to return a tuple of index and value in a list.    
This can be used with loop

Syntax:
```python
somelist = ['test','some','another']
for pos, val in enumerate(somelist):
    print(pos)#returns the index like 0,1,
    print(val)#returns the value at the index.
```

#### Map
map is a built in function used to **apply** a function on each item of a list,tuple(iterable object).    
This makes code better readable and don't have to use for loop to access items.     

Syntax:     
```python
map(function_Name/lambda_Function,*iterables)
```
We have to give the name of function to apply or define a lambda function inside,then pass single or multiple lists/iterable objects.

Ex:
```python
l=['123','1234']
list(map(lambda item: print(item),l))
```
* map takes the list then applies given function on it.
* the returned map object is cast to list,we can access values in list.

#### Filter
Just like Enumerate,Map another function built into python to make list manipulation easier is filter.      
This function take a condition/function to **check** on a list/iterables.      

Syntax:     
```python 
filter(function/lambda_function,*iterable)#returns a iterable filter object     
```

Ex: 
```python     
items=[('product',10),('slfj','1'),('sldfj','123')]#checks if the price is greater than 10.
list(filter(lambda item : item[1] >= 10,items))#casting the filter object to list to access.
```

#### List Comprehension
The above methods are available in multiple programming languages,but in python we have better options.     
this is called list comprehension.It is preferable.           

Syntax:
```python 
[expression for item in items if statements]
```

Ex:
```python 
[ item for item in items if item[1]>=10]
#we can use this instead of filter,this is easy to read,but specific to python.
```

#### Zip
we can combine multiple lists based on their index in to a tuple.    
>
```python 
zip(lst name,list name)
```

Ex:     
```python     
l=[1,2,3]
l1=[5,6,7]
zip(l,l1)#[(1,5),(2,6),(3,7)]
```

#### Unpacking Operator
we can get the values inside a iterable object with unpacking operator.    
Syntax:
```python
*object#this is the syntax
```

Ex:   
```python    
v = [1,2,3,4,5]
print(*v)#prints 1 2 3 4 5
```
can be used with any iterable like list,tuple et.     
**Trick**         
```python 
val = [*range(5)]
```

can unpack a dictionary with double asterisk
```python 
val =[**dictname]
```

### Tuple
A Tuple is a Immutable(Non writable/read-only) List.       
* we can create a tuple once,after that can't add new ones or remove existing.      
* To edit a tuple,we copy tuple==>list==>edit===>tuple   
* copy the tuple to a list,then edit on that list,then copy the output to a tuple.  
* we use () for tuple, [] for list.    

Syntax:     
```python 
tuplename = ("item1","item2","item3")
tuplename[1]
```

* the () are optional,python doesn't mind tuple with () or without.     

Ex: 
```python 
x = (1,2,3)#both are same.    
x = 1,2,3 
```

#### Swap
we can swap variables using tuples.   
```python  
x,y = y,x#swaps variables.        
```

#### Generators
Instead of storing all the values in a list/tuple we create a generator object.          
A generator object takes consistent small amount of memory,compared to a list.         
We use generators when the data we get is in terms of thousands,millions.     
But we can't access all the items inside a generator at once.

Syntax:    
```python  
val = (comprehensive code)
```            
Ex:
```python 
val = (x * 2 for x in range(1000000))#takes around 1230 Bytes
val = [x * 2 for x in range(1000000)]#takes around 82 KiloBytes
```

### Set
Set is a unordered,non indexed data Structure.     
We can have multiple repetitions inside a set. 

Syntax:
```python
setname={"item","item","item"}
```

* we cannot access an item by index,we can just check if the data exists or not using **in**.
```python 
item1 in setname
```

* a set is used mostly in the mathematical operations.         
  * **|** Union of two sets.   
    ```python   
    print({1,2,3} | {4,5,1})#{1,2,3,4,5}    
    ```   
  * **&** Intersection of two sets. 
    ```python       
    print({1,2,3} & {4,5,2})#{2}
    ```     
  * **-** Difference of two sets. 
    ```python         
    print({1,2,3} - {2,4,5})#{1,3}
    ```  
1. **mutable** 
once a set is created we can add new items,but can't change old items.
we use set with following and some more methods/functions.
2. **add()**      
3. **update()**      
4. **remove()**

### Dictionary
Dictionary is a unordered,mutable,indexed(key) data structure.    
Dictionaries are key,value pairs.   

Syntax:   
```python   
dictionaryname = {
   "key":"value",
   "key1":"value1"}
print(dictionaryname["key"])
```
we work with key of an item to identify a value.     

1. **get()** returns the value of specified key,if no item is present None is returned.    
2. **values()** returns all values      
3. **keys()** returns all keys
4. **items()** returns all key-value pairs in a tuple.

* We can iterate over a dictionary
ex:   for key, value in dictname.items():       

#### Dictionary Comprehension
We can create,iterate over a dictionary. with single code.         

Syntax:        
```python 
{key:valueexpression for item in items}
```
Ex:   
```python       
values={x:x * 2 for i in range(5)}
print(values)
```

### Stack
Stack is a Last in first out(lifo) order of items or list.     
we use stacks to store data in log.       
In python we can implement stack behavior with lists.   
we use Pop to remove data,on top.         
we use append to push data on top.     
Ex:      
a = [1,2,3,4]     
so we remove 4 first,then 3, then 2, then 1.this is called pop          
we insert 5,6,7 at the end 1,2,3,4,5,6,7.this is called push      


### Queue
Queue is a data structure with the behavior First In First Out(FIFO).         
we add item at last of queue and remove item at the first of queue.     
Just like in real world queue.      
We implement queues in python with collections.    
we use deque class.  

a = [1,2,3,4]     
we input 5,6,7 at the end of que, 1,2,3,4,5,6,7 
still we remove 1,2,.... in sequence of queue         

Ex: 
```python         
from collections import deque
ques=deque([])#creates a queue with given list
ques.append(1)#appends item at the end of queue
ques.popleft()#removes item at the start of queue
```

### Array
In python lists provide good functionality,but if we need optimized data structure we use Arrays.     
We can use arrays in python using array class.      

Ex:   
```python    
array(typecode,list)
```
typecode is the data type of array.    

Ex:   
```python    
n=array("i",[1,2,3,4])     
n.append()#to add at end.        
n.pop()#removes last element.         
```
* when inserting values it has to match the data type.      
* only use arrays when items are more than 10,000.    

## Exceptions     
Exceptions are the errors raised by python when we try to do some operation and it couldn't complete the task for any number of reasons.         
We have many number of exceptions in python.      
    

Programmers have to make sure of the input taken,data accessed in our code,to reduce incompatibility,this will stop errors.          

Ex:
accessing a element in array that doesn't exist.will raise a indexoutofbound exception.

* We can test the code that can cause exceptions,and handle according to need.  

Syntax:
```python 
try:
    code
except exceptionerrorname:
    logic
```

Ex:
```python 
try:--->runs the code block
    age=int(input('age' ))
except ValueError as e :--->this block  executed when valueerror is raised
    print('not a number')
```

### Multiple exceptions       
Multiple exceptions can be checked in a single except statement.        

Syntax:
```python 
try
    block
except (error,error,error):
    block
```
* The except block will be executed when one of specified error is raised.    

* Multiple exceptions can also be implimented individually.      

    Syntax:
    ```python 
    try:
       block
    except errorname:
       block
    except errorname:
       block
    ```

* The order matters,if first except block is executed remaining blocks will be skipped.

### Error object
We can take the error object in to our code using the **as** keyword.      
* This can be used to create logs,change flow of code.     

Ex:
```python 
try:       
    code         
except exceptionerrorname as e:#e is the current exceptions object
    logic   
```

### Else
when no exceptions are raised,else block is executed.

Ex:
```python 
try:
    block
except errorname:
    block
else:
    code
```

### Finally
A Finally block is always executed at the end of **try** execution.
* doesn't depend on try,except,else.
```python
try:
    block
except errorname:
    block
finally:#this block will always execute
    block
```

### Finally vs Else
* An Else block is only executed when there are no exceptions raised.  
* A Finally block is always executed.

### Raising Exceptions
We can manually raise exceptions in our code.   

Syntax:    
```python  
raise errorname
```
* We raise errors when a condition is met or not met.
* It is not preferrable to raise exceptions,it is time consuming.Takes 4 times long to raise a exception and handle it.      
* If possible just handle the error.    


## Class
A Class is a blueprint to create an object.      
We define the data and operations(functions/methods) that a class can perform.      
This class can be used to create any number of objects.     

Syntax:
```python
class ClassName(inheritanceclasses):
    code
```

* All functions/methods in a class should contain a first parameter,called [self](#self).     
* Block of code in sequential programming is called function,in object oriented is called method.

### Object
We have two types of memory.   
1. Stack
   * Stack is a sequential memory,which operate on LIFO(last in first out) 
   * Stack contains variables,reference variables
2. Heap
    * Heap is a dynamic memory,which contains objects.

An object is an instance of class.      

We can create an object with *Classname()* inside heap memory.      
* To access this we create a *reference variable* in Stack memory,that hold address of object
* We link the objects address to this variable.

Syntax: 
```python
class Point():
    pass

test=Point()
#Point() is creating a object
#test is a reference variable in stack memory
#= is assigning the objects address to reference variable.
```

* When an object is created, all the methods,variables inside the class are copied to it.
* Each object of a class is unique,and can have specific methods,variables,data.
<hr>

* When using inheritance the methods,data of parent,child,grand-child are copied to a grand child object.      
* These methods,data are always inside the object,but depending on the reference their access type changes.  

![Class and Object](./SVG/class_object.svg)

#### \_\_init__()       
We need a constructor to create(instantiate) an object of a class.      
If no constructor is given,python interpreter supplies a default empty constructor.      

A constructor is a method that is called automatically on object creation.       
Constructor can be used to provide data for an object on creation.      


Syntax: 
```python
def __init__(self,parameters):
    logic
```

Ex:
```python
def __init__(self,x,y):
    self.x=x#assigning the argument to an instance variable.
    self.y=y#we reffer to instance variables/methods with self

obj = Point(1,2)#creating objects with provided data
```

* an object can have other variables that are unique to it.
```python
obj=Point()
obj.z=10#z is not in Point class,unique to object.
```

##### Self
self is the reference to the current object of class.   

* To access data/methods inside the object we use the reference.   
* We use *self*,to access data inside of an object. 
* *self* contains the address of current object,so *self.x* will return variable x.This is equivalent to *obj.x*
* We don't have to use *self*,we can use any word that is consistent across the class.

Ex:
```python
class Run:
    def draw(self,x):
        self.x=x

obj1= Run()

class Point:
    def draw(somerandomname,x):
        somerandomname.x=x

obj = Classname()
#here classname() is the object created in memory
#= is linking the object's address to obj.        
```

* Methods in a class should have the first argument as *self*.This is mandatory.
* Every method call must have a *self/objectname* as the first argument.But the python interpreter provides that for us.We can specify it though if we want.  
  
```python
point=Point(1,2)
point.draw()#method call,python puts self as the first argument
point.draw(self)#invalid, here self is a new argument,not a reference
point.draw(point)#valid, as this is the object reference,But not needed as python does this automatically
```

#### isinstance
*isinstance* is a python builtin method that checks the type of a given object.Returns a boolean value.                 
We use isinstance to accept only a certain class objects.     

Syntax:
```python
isinstance(objectname,Classname)
```

Ex:
```python
x=1
print(isinstance(x,int))#True
```


#### Instance Members      
Variables and methods combined are called members.      

*Instance Variables*        
* Variables inside an Object are called Instance Variables.    
* We create instance variables with a constructor or an object reference      
* We access Instance variables with a reference variable(self/objectname)

*Instance method*      
* Methods inside a object are called Instance methods.
* By default every method in a class is a instance method.And has *self* as the first argument.     
* An instance method can only be accessed with an object reference     

Ex:     
```python
class Point:
    def draw(self):#creating instance method
        self.x=4#instance variable

po = Point()
print(po.draw())#Calling instance method
print(po.x)#calling instace variables
```
* Every Object has unique variables and methods in its memory

#### Class Members
Members of a class are same to all objects. 

*Class Variable*        
* Variables outside of methods are called Class variables.
* We can access a class variable with either object reference or Class name itself.
* A Class variable is common to all the objects of a class,is stored in stack memory.
* A change in class variable affects all the objects

*Class Method*      
* Methods with a **@classmethod** decorator before them are Class Methods
* A class method should have a [decorator](#decorator) on top and *cls* as the first argument.
* *cls* refer to current class. Just like *self*,*cls* can be any name as long as consistent across the class.
* We can access a class method with either a class name or object reference

Ex:
```python
class Point:
    tempvar=10#Class Variable

    #this is a decorator
    @classmethod
    def test(cls):
        cls.x=11#class variable
        return cls.x

    @classmethod
    def test2(somerandomname):
        somerandomname.x=11

    def draw(self):
        print('draw')
        self.x = 10
        return self.x
po = Point()

print(Point.tempvar)#accessing Class variable with class name
print(po.tempvar)#accessing Class variable with object

print(Point.test())#accessing class method with class name
print(po.test())#accessing class method with object
```
* Every object will have same class variables/methods.



## Inheritance
Inheritance is the property when a class inherits functionality from another class.         
This can be extending/reusing the methods into a new class,or creating new implementations for existing methods.        

The class that inherits is called Sub/Child/Derivative class.           
The class,the child class inherits from is Super/Parent/Base Class.                 

Ex:         
`parent-->child-->grandchild`         

* Main use of Inheritance is to create complex architecture with reusable code.

Syntax:
```python
class childclass(parentclass):  
   code
```

Ex: 
```python    
class Animal:
    code
class dog(Animal):
    code
```

Ex:
```python
class Animal:
    print('inside Animal Class')#will be printed first
    def __init__(self):
        print('inside Animal')

    def func1(self):
        print('inside func1 of Animal')

class Dog(Animal):#inheriting animal class
    print('inside Dog Class')#will be printed second,rest are based on their order of call
    def __init__(self):
        super().__init__()#calls the animal init method
        print('inside Dog')


    def func2(self):
        print("inside func2 of Dog")

puppy = Dog()
puppy.func2()#calling the child method
puppy.func1()#calling the parent method
```

![Inheritance](./SVG/inheritance.svg)

**Code Flow**           
Consider the Above Code Example
1. The code flow always start from the base/parent class.Here From Animal.
2. All the Data and methods of Animal class are put inside a object.Ex obj1 = [ func1() ]
3. But Dog inherits Animal,So Code execution moves to Dog(child class) 
4. All the Data and methods of Dog class are put inside another object.Ex obj2=[ func2() ]
5. Now the parent class object is put inside child object.
6. Now object looks kind of like this `obj2 = [ [ obj1 ] func2() ]`
7. When a function is called python interpreter first checks the members of obj2,if it is present then executes it .
8. If not present then moves inside the obj1 and checks.This process continues till the method is found in the object.If not present an error is raised.

* after considering code flow in an inherited environment we have make sure our code and method calls are appropriate and any exception handled before hand.    

Their are 4 Types of Inheritance

### Single Inheritance
Single Inheritance is having One parent and One child in a relation.    
This is an example of Single Inheritance
```python
class Parent:
    code
class Child(Parent):
    code
```

* This is the most used Inheritance Type.


### Multi-Level Inheritance
Multi-Level Inheritance is when we go multiple levels deeper with inheritance.  
i.e, 
A GreatGrandParent-->GrandParent -->Parent-->Child--->GrandChild--->GreatGrandChild

* We can implement inheritance any number of levels deeper,but it is not adviced to go more than 3 or 4 levels of inheritance.        
* The more deeper Levels we go,the more complex and dense the objects get.

Ex:
```python
class parent:
    code
class child(parent):
    code
class grandchild(child):
    code
```

![multilevel_inheritance](./SVG/multilevel_inheritance.svg)


* Here the grandchild object will have grandchild's,child's,parent's methods and variables in it.
* We can access them based on our permissions and reference type.

Ex:     
```python
class Dad:
    def eyecolor(self):
        print('blue')

class Me(Dad):
    def iq(self):
        print('80')

class Son(Me):
    def height(self):
        print('6 feet')

myson = Son()
myson.iq()#inherits Me iq
myson.height()#has their unique height
myson.eyecolor()#inherits from grand parent eyecolor
```



### Multiple Inheritance
Multiple Inheritance is when we inherit from multiple parents.      
This is not possible in java,and some languages due to the ambiguity problem.Python Supports this by not giving room for ambiguity.      

Syntax:
```python
class parent1:
    code
class parent2:
    code
class child(parent1,parent2):
    code
```

Example 1:
```python
class Mom:
    def smile(self):
        print('great smile')

class Dad:
    def iq(self)
        print('100 iq')

class Me(Dad,Mom):
    def eyecolor(self):
        print('blue')

myObject=Me()
myObject.eyecolor()#child's own method
myObject.smile()#inherits mom smile
myObject.iq()#inherits dad's iq
```

Example 2:
```python
class Mom:
    def iq(self):
        print('10 iq')

class Dad:
    def iq(self)
        print('100 iq')

class Me(Dad,Mom):
    def eyecolor(self):
        print('blue')

myObject=Me()
myObject.eyecolor()#child's own method
myObject.iq()#calls Dad's iq method.Depends on order of inheritance 
```

![multiple_inhertiance](./SVG/multiple_inhertiance.svg)

Example 3:      
```python
class Dad(): 
    def iq(self): 
        print("stupid")

class Mom(): 
    def iq(self): 
         print("smart")      

class Son(Mom,Dad): 
    def iq(self): 
        print(" Average smart")  
obj=Son()
obj.iq()#will call the Son's iq
Mom.iq(obj)#will call the Mom's iq method
#since obj=[[Mom iq] [Dad iq] iq], when we specify the class's method,inside object is triggered.
Dad.iq(obj)#will call Dad.iq method 
```


The Above Examples provide different scenarios of multiple inheritance
1. Example 1 shows, When both parents and child class have unique methods,Then their is no problem of ambiguity.
2. Example 2 shows when both parents has same method but child doesn't.
    * Here python solves the ambiguity problem of which method to access,by taking the method of first class in order of inheritance
    * So the first class in (Mom,Dad),i.e, Mom's method is called.
3. Example 3 show when both parents and child classes have same method,then the child method is accessed.   
    * We can also access the parent classes method,by specifying the class and passing the child object as reference.
    * Syntax: `parentclass.methodname(objectreference)`
    * This object reference is used to unpack the parent method in it.  

### Hierarchical Inheritance
Hierarchical Inheritance is when a single class is used to inherit multiple child classes.      
This is similar to a parent having multiple children.       
Ex:     
A-->B       
A-->C       

Syntax:
```python
class A:
    code
class B(A):
    code
class C(A):
    code
```

Example:
```python
class Parent:
    def smile(self):
        print('good smile')

class Kid1(Parent):
    def height(self):
        print('5 feet')

class Kid2(Parent):
    def height(self):
        print('6 feet')

kid2 = Kid2
kid2.smile()

kid1 = Kid1
kid1.smile()
```

![Hierarchical_Inheritance](./SVG/Hierarchical_Inheritance.svg)


### Hybrid Inheritance
Hybrid Inheritance is when a parent and child class are used to create a new class.
Ex:     
A-->B
C-->A,B

Syntax:
```python
class A:
    code
class B(A):
    code
class C(A,B):
    code
```

Example:
```python
class Parent:
    def say(self):
        print('saying hello')

class Child(Parent):
    def childsay(self):
        print('saying hello from child')

class hybridChild(Parent,Child):
    def timer(self):
        print('inside the hybrid)

hybrid = hybridChild()
hybrid.timer()
hybrid.childsay()
hybrid.say()
```


### Object Class
In python Every class is a child class of Object Class.     
This is done by default.    
All the methods that are accessible for objects are provided by Object Class.       
Object Class only has [magic methods](#magic-methods).  


## Polymorphism
Poly==>Many.morph==>Forms/Shapes.
Polymorphism means having many forms,can think of a man depending on the context, is a father,student,cook,worker,husband,friend.   
Here the man(object) is same but the context and their work changes from time to time.    

We can implement polymorphism in Object Oriented Languages.Like Python,Java,C++.etc.,

There are two types of polymorphism in python.
1. Compile Time Polymorphism    
    * Compile Time polymorphism is known at compile time,so python doesn't support it.
    * **Method Overloading** is an example of Compile Time Polymorphism
    * But In other languages we know which object or which method is working in what context
2. Run Time Polymorphism
    * Run Time Polymorphism is resolved at Execution time.Python supports.
    * **Method Overriding** is an example of Run Time Polymorphism
    * At execution time python interpreter will use the object or method in our logic depending on context.

### Method Overloading
Method Overloading is the process of having same method name with different Parameters.     
Syntax:
```python
def add(x,y):
    pass
def add(x,y,z):
    pass
```

* The above example is a Method Overloading example
* Python doesn't need overloading as the data type is dynamic,so can pass any type of data.  
* Instead we use single method and define logic depending on the type of parameters.

Ex:
```python
class Employee:
    def hello_Emp(self,e_name=None):
        if e_name is not None:
            print("Hello "+e_name)
        else:
            print("Hello ")

emp1=Employee()
emp1.hello_Emp()#Calling with no arguments
emp1.hello_Emp("Besant")#Calling with arguments
```

* Here when we call the method hello_emp with no parameters one logic is executed
* When we pass a argument another logic is executed,This is method overloading but in java it has a different implementation,but the concept is same.   
* If we try to define two methods with different signature(different parameters) the last method will be executed when called.

```python
def fun():#will be disregarded
    print('hello')

def fun(test):#will be disregarded
    print(f"{test}hello")

def fun(test,test2):
    print(f"{test} {test2} hello")

fun()#will raise an error,asks for the parameter test,test2
#always the latest method signature is executed
```

### Method Overriding
Method Overriding works with inheritance,we can override existing parent method with new child method containing same method signature. 

Syntax:
```python
class Parent:
    def fun(self):
        print("inside parent fun")

class Child(Parent):
    def fun(self):#Overridding the parent class method
        print("inside child fun")
ch = Child()
ch.fun()#this will call Child fun method,as they have same method signature
Parent.fun(ch)
#this will call the parent fun method inside the child object.
```

![method_overridding](./SVG/method_overridding.svg)

* Here we have the parent fun method inside the child object
* but child fun method overrides it,we can call it using super().fun() from child class.    
* We can also access the parent fun method present inside child object by specifing `Parent.fun(ch)`,this just gives us access to existing parent method.

Example 2:
```python
class Parent:
    def fun(self,test,time):
        print("inside parent class and fun method with parameters")
        #this method will only execute when called with parent class object.
class Child:
    def fun(self):
        print("inside child class and no parameters")
        #This method will only execute when called with child class object.
        #The parent method will not work,since overridden.
        super().fun()#not possible with out, arguments that we don't know
        super().fun('something',"same")
        #this is valid but these are magic values that are hardcoded

ch = Child()
p = Parent()

ch.fun()#calls child method
p.fun()#calls parent method
```

* The above is valid and possible in pyton but it is not a good python practice as we might not know which function parameters are actually needed.
* It is impossible to call the parent method inside child method using super() without arguments.




## Encapsulation
Encapsulation is the process of bundling data and methods in to single unit.            
Here we can have any number of variables or methods.               




Encapsulation is achieved with help of access modifiers.        
**Access Modifiers**           
We have two types of Access modifiers in python       
1. Public       
   * By default all the data(variables) and methods in a class are public,i.e, accessible by other classes and methods.    
   * Any data,methods without any access modifier is public.
2. Private
   * Double underscore **__** before variables/methods makes it private member.
   * Private members are only accessible inside a python class.
   * Objects of the same class or other classes can't access private variables/methods.



**Setters**         
In Object Oriented Programming We use encapsulation to achieve better interaction with other classes or objects.    

* The Best practice of using Encapsulation in our code is making all the variables private
* And using Getters and Setters to get and set variable values.

Syntax:
```python
__name=""#private variable

def setname(self,name):
    self.__name = name
```

**Getters**     
A getter is used to return the value of  private variable.      

Syntax:     
```python
__name = "testvalue"
def getname(self):
    return self.__name#accessing private value
```

* We can access the private variable only inside the class,but to access it with a object we have to use getters and setters.   
* Encapsulation is used to create abstraction
* We can create private methods that are hidden from objects,These methods are used by other public methods which are accessible.   

![Encapsulation](./SVG/Encapsulation.svg )

Example:    
```python
class Animal:
    __name = ""#empty private string variable

    def __someprivatefun(self):
        #private method with some logic
        print("this is just a function using other functions")

    def __init__(self,name):
        #calling the setter method  
        self.setanimalname(name)

    def setname(self,name):
        #setting value to private variable
        self.__name = name

    def getname(self):
        #getting value from private variable
        return self.__name

    def fun(self):
        #a public method that uses existing private methods.
        print("this is a function")
        self.__someprivatefun()

a = Animal("raj")
print(a.getanimalname())#accessing the private variable
a.fun()
print(a.__name)#raises a not found error
a.__someprivatefun()#raises a not found error
```

Explanation of above Example:
1. We are creating a variable and a method as private
2. creating a getter and setter for the variable
3. Calling the setter from the init method,can also call from object
4. using the private method inside a public method
5. we can't call the private method with object,raises an error
6. This way we only access public method with other classes or objects.



## Abstraction 
In General terms Abstraction is the concept of hiding unnecessary details.          
Ex: A tv remote with lot of circuitry and software being hidden,with only buttons that perform a task.          

In programming we use Abstraction concept to make our code easily accessible to others.             
In building an application we might use Abstraction for a better structure and architecture to make future changes easy.        
Gives better understanding how the entire project works.        

Abstraction ( both abstract class and interface) is used mostly to provide API and building Packages.  

![Abstraction](./SVG/Abstraction.svg)

Consider the above diagram:
1. We create an Interface,to specify all the other classes that the child classes should implement those methods.
2. This interface is made public to extend our application,an example is API
3. the child classes are structured depending on their  need from the interface.
4. Here we use the maths interface to build a mathematical class structure and a bank system.   


**Important**       
In day to day programming we mostly don't use Abstraction.     
We discuss how our project should be structured and create a bunch of interfaces to implement our idea in code.      

* After that the child classes perform the actual logic,so we take the latest child object and refer to it for our implementation.    
* Java being static typed, we use the name of abstract class to create objects for easy understanding.   
* Since python is dynamic typed and doesn't need a type defined,we use the latest child object and pass it to relevant program,implement the logic when called.     
Ex:

```python
class test:
    @abstractmethod
    def fun(self):
        pass

class test2(test):
    def fun(self):
        print("hello")

mytestobject=test2()
mytestobject.fun()#calling the abstract method with child object
```

* Encapsulation is data hiding
* Abstraction is implementation hiding

### Abstract Class
Abstraction is a concept,Abstract Class is the actual code that creates abstraction.    

In python there is no abstract keyword to create a abstract class, like in java.    
We create a abstract class by extending the python **Abstract Base Class**.     
This abstract class can have 
1. [Abstract method](#abstract-method)
2. [Concrete method](#concrete-method)

Syntax:     
```python
from abc import ABC ,abstractmethod
class Parent(ABC):#abstract class+
    abstractmethods
    concretemethods
```

* We can't create an object of Abstract class or interface
* A class that inherits Abstract class or interface should implement or override the abstract methods
* If we don't override the methods,that class should be abstract as well


#### Abstract method
A method is called abstract method if it follows these rules.   
1. The method should be an empty method with **pass** inside it.    
2. method should be decorated with **@abstractmethod**      


* The child class should override this method,or an error is raised.  

Syntax:     
```python
from abc import ABC, abstractmethod
class Parent(ABC):
    @abstractmethod
    def iq(self):
        pass#empty method,abstract method
```
#### Concrete method
A normal method with logic in an abstract class is called a concrete method.    
Example:    
```python
from abc import ABC, abstractmethod
class Parent(ABC):
    def iq(self):
        print("hello")#concrete method.
```

### Interface
There is no Interface concept in Python,But we can create one.  
An abstract class with only abstract methods is called an Interface.    

Syntax:
```python
from abc import ABC, abstractmethod
class testinterface(ABC):
    @abstractmethodd
    def test1(self):
        pass
    
    @abstractmethodd
    def test2(self):
        pass
    
    @abstractmethodd
    def test3(self):
        pass
```



## Higher Order Programming



 Decorators
To understand Decorators we need to learn few concepts 
1. [NameSpace](#namespace)
2. [Scope](#scope)
3. [Nested Function](#nested-function)
4. [first class function](#first-class-functions)

Decorator is a powerful concept specific to python. 
We use Decorator to create better interface for our program.This is used to write simpler and cleaner code.     
We can write code without decorator but it will make our modules tightly coupled.       
But if we write code with decorator we can reuse those blocks code multiple times.  

* A decorator is a object that takes a function parameter as input,adds somelogic to it then returns a new function.
* Decorators are used for adding functionality to existing functions/methods.
* defining simply and not having to repeat function name three times,which is non pythonic

A decorator is used like in real life to decorate a present.    
We take existing method/function then perform operation before and after its execution.
Major uses:
1. Analysis,logging
2. Data validation and runtime checks
3. Creating new frameworks
4. 



Ex:         
```python
def uper(func):
    def inner():
        str1 = func()#copying result to a variable
        return str1.upper()
    return inner#returning inner reference

def printstr():
    return "good"

d = uper(printstr)#calls uper function with printstr as parameter
print(d())
```

Instead of using a separate method to use a nested function we use a decorator
Syntax:
```python
@decoratorclassname
def methodname():
    logic
```

* here the method is passed to the decorator method. 
* Can reuse it where ever we need to implement this.


### Function Decorator

### Class Decorator





### First Class Functions
In python functions are by default First Class Functions.       
A first class function have these properties.      

1. It is an object 
    Ex:     
    ```python
    def test():
        print("hello")

    test()#calling function
    x = test # passing test object address
    x()#calling the function at the address

2. Can be passed as parameter,here the address of function object is passed.
    Ex:            
    ```python
    def test():
        print("hello")
    def exam():
        print("Oh no")

    test()#calling function directly
    exam()

    def param(fun):#taking function address as a parameter
        fun()#calling function of parameter

    param(test)
    #will call param function and pass the test function address as parameter,
    #then inside the function we will call the test function
    param(exam)
    ```

3. Stored as a variable             
    Ex:     
    ```python
    def test():
        print("hello")
    
    x = test#storing function address
    x()#calling the function in the address
    ```

* can return a function address from another function,this is also called **Closure**   
* We use closure to take the inner function address and use it outside the outer function scope.           
    Ex:     
    ```python
    def test():
        def innertest():
            print("hello")
        return innertest
    
    x = test()#contains the address of innerfunction
    x()#call the inner function out of its scope.
    ```

### Nested Function
In python we can have a method inside a method.     
Which is not possible in C,C++,Java.Which is confusing for these language programmers.          
Since python functions are First Class Functions we can do this just like objects inside objects.   
Syntax:     
```python
def outerfun():
    logic
    def innerfun():
        logic
    innerfun()
    # can only call innerfun in its scope

outerfun()
```



<!-- ### magic methods
### property
## Input Output

## Modules -->
