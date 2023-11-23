---
title: MIT DS Class Intro to Python
date: YYYY-MM-DD
notebook: https://colab.research.google.com/drive/1NzBtacgQV0rhzEPrwBFlCxsMolzZmxpV#scrollTo=plc_ocWV6mg_
Video: https://olympus.mygreatlearning.com/mentorship_recordings/217758
summary: Brief summary or description of the class
tags:
  - DataScience
  - Math
  - MIT
  - ML
  - Python
  - AI
references: 
type: MITClassNotes
---


>[!info] Printing Statements

```py

print("Insert what you want printed here.")
```

>[!info] Data Types[
Python data types documentation](https://docs.python.org/3/library/datatypes.html)

4 Data Types for this course to focus on 
Integer
Float
String
Boolean

f string for print
[py doc](https://docs.python.org/3/tutorial/inputoutput.html#:~:text=To%20use%20formatted%20string%20literals,to%20variables%20or%20literal%20values.)
```py
year = 2016
event = 'Referendum'
f'Results of the {year} {event}'
'Results of the 2016 Referendum'
```

F String and Round example from class [[Python Resources]]
```py
  
saftey_incidents = 44
saftey_percent = round(float(saftey_incidents/total_employees)* 100,2)
total_employees = 1568
print(f"The percentage of safety incidents is %{saftey_percent}.")

#output
#The percentage of safety incidents is %2.81.
```


>[!info] Data Structures 
>[!info] LISTS
>
>
```py
#Data Structures section in Pre Class

car_type_1 ='Sedan'
car_type_2 ='Hatchback'
car_type_3 ='SUV'
car_type_4 ='MUV'

variable_name =[car_type_1,car_type_2,car_type_3,car_type_4]
print(variable_name)
```
```py 
#Indexing in a list
variable_name[0]

variable_name[1]

variable_name[2]

variable_name[3]

```
[[Python Resources]]

>[!info] List Slicing


```py
list =[1,2,3,4.5.6]
list[1:3]
list[0:5:2]
```

>[!info] Tuple

A tuple is an unchangeable list, this means a tuple is [immutable ](https://www.google.com/search?q=define%3A+immutable&sca_esv=581724701&rlz=1C5MACD_enUS1073US1074&biw=1012&bih=1245&sxsrf=AM9HkKnHI1HbpAASsU8wVYXAH6TEVd1HMQ%3A1699803572521&ei=tPFQZcW5H5euptQP17G38AQ&ved=0ahUKEwjF44Lh5b6CAxUXl4kEHdfYDU4Q4dUDCBA&uact=5&oq=define%3A+immutable&gs_lp=Egxnd3Mtd2l6LXNlcnAiEWRlZmluZTogaW1tdXRhYmxlMggQABiKBRiRAjILEAAYigUYsQMYkQIyBRAAGIAEMgUQABiABDIFEAAYgAQyBhAAGAcYHjIFEAAYgAQyCBAAGAcYHhgPMgUQABiABDIIEAAYBxgeGA9I7g9QAFi_C3AAeAGQAQCYAVqgAagEqgEBN7gBA8gBAPgBAcICChAAGA0YgAQYsQPCAgcQABgNGIAE4gMEGAAgQYgGAQ&sclient=gws-wiz-serp)
example where you can use a tuple - long and lat pairs 
it's a safety mechanisms- you can't edit it.  like example above you would never edit long and lat together.  The coordinates are both needed or they mean nothing. 


>[!info] Differences between Tuple and List
** A tuple is unchangeable **
** Tuples are defined in parentheses, lists are in square brackets) **.
**Tuples are faster then lists for performance with look ups**
[more info](https://www.w3schools.com/python/python_tuples.asp#:~:text=Tuples%20are%20used%20to%20store,which%20is%20ordered%20and%20unchangeable.)

Example: 
```py
thistuple = ("apple", "banana", "cherry")  
print(thistuple)
```

>[!info] Dictionary
>Dictionaries are Python’s implementation of a data structure that is more generally known as an associative array. A dictionary consists of a collection of key-value pairs. Each key-value pair maps the key to its associated value.

You can define a dictionary by enclosing a comma-separated list of key-value pairs in curly braces (`{}`). A colon (`:`) separates each key from its associated value
[link to class example](https://colab.research.google.com/drive/1NzBtacgQV0rhzEPrwBFlCxsMolzZmxpV#scrollTo=1T-fwYXnKpgp&line=6&uniqifier=1)
```py
person ={

'name':'Alice',

'age': 25,

'city': 'New York'

}

print(person['name'])
```


>[!info] Comparison Operators 

1:37 Intro to Python

```py
sales_last_month = {'SUV': 10000,

'Hatchback': 20000,

'Sedan': 120000,

'EV': 1500}

  
# should return FALSE
sales_last_month['SUV'] > sales_last_month['Hatchback']

```


>[!info] Conditional Statements

@ it's core Making a decision
IF /ELSE statements and ELIF statements 

```py
weather = 'raining'

if weather == 'raining':
	print("Do not play tennis today")

```
[location in colab](https://colab.research.google.com/drive/1NzBtacgQV0rhzEPrwBFlCxsMolzZmxpV#scrollTo=cWWapbOHq1WT&line=1&uniqifier=1)

var = 'value'

If var == 'value':
	do x
else:
	do y
vs

ELIF
---------------------
number_to_compare = 10

if number_to_compare >2:

print('Number greater then 2')

elif number_to_compare >5:

print('Number is greater then 5')

else:

print('Number is greater then 10 ')


-----------------------------------------------------
>[!info] for loop

