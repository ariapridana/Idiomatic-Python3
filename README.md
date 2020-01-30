# Idiomatic-Python3

This is a partial notes from "writing Idiomatic Python" Book By Jeff Knupp

## IF Statements

#### Chain comparisons to make if statements more concise
```
if x <= y <= z:
  return True
```
#### Avoid repeating variable name in compound if statement
```
name = 'Tom'
is_generic_name = name in ('Tom','Dick','Harry')
```
#### Avoid comparing directly to True,False, or None
```
result = True
if result:
  print("Its True")
```
#### Use if and else as a short tenary operation replacement
```
foo = True
value = 1 if foo else 0
print(value)
```
## For Loops
#### Use the enumerate function in loops instead of creating an "index" variable
```
my_container = ['Larry', 'Moe', 'Curly']
for index, element in enumerate(my_container):
    print('{} {}'.format(index, element))
```
#### Use the "in" keyword to iterate over an iterable
```
my_list = ['Larry', 'Moe', 'Curly']
for element in my_list:
    print(element)
```
## Functions
#### Use return to evaluate expressions in addition to return values
```
def all_equal(a, b, c):
    return a == b == c
```
## Variables
#### Use multiple assignment to condense variables all set to the same value
```
x = y = z = 'foo'
```
#### Avoid using a temporary variable when performing a swap of two values
```
foo = 'Foo'
bar = 'Bar'
(foo, bar) = (bar, foo)
```
## List
#### Use a list comprehension to create a transformed version of an existing list
```
some_other_list = range(10)
some_list = [element + 5 for element in some_other_list if is_prime(element)]
```
#### Prefer list comprehensions to the built-in map() and filter() functions
```
the_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
odd_numbers_times_two = [n * 2 for n in the_list if n % 2 == 1]
```
#### Use the built-in function "sum" to calculate the sum of a list of values
```
the_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
the_sum = sum(the_list)
```
#### Use all to determine if all elements of an iterable are True
```
def contains_zero(iterable):
    return not all(iterable)
```
## Dictionary
#### Use the default parameter of dict.get to provide default values
```
log_severity = configuration.get('severity', 'Info')
```
#### Use a dict comprehension to build a dict clearly and efficiently 
```
user_email = {user.name: user.email for user in users_list if user.email}
```
## Set
#### Use a set comprehension to generate sets concisely
```
users_first_names = {user.first_name for user in users}
```
#### Use sets to eliminate duplicate entries from Iterable containers
```
duplicate_data = ['1','1','2','3','1','1']
non_duplicate_data = set(duplicate_data)
```
