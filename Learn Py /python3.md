# Python 3 

> ## Data Types

python has : int, float (both with no size restriction),string, tuple (both are immutable : once defined then cannot be changed), dictionary, Sets.
tho some of are not considered as an data types but in real time we used them to resolve many mathematical problems.\

and talking about integers, python provides the flexibility here! we can have the integer of any size but python store same reassigned variable integer in diff memory location! 

Suppose define

```py
x = 25
id(x)

x=121
id(x)
```
so in above both of the cases the id will be diff! why?? python do not know about what size of int you are reassigning so it create a new location in memory!!

**floating point representation:**

number can be represented in term of power of 10. taking example a=12400 now here this can be represented as `124 * 10^2` or `124 * E2` and it can be further represented as 124E2. or in more mathematical term the 124 is mantissa and 2 is exponent.

```py
x=23.45

#decimal point will get eliminated and can be written as 2345/100 or more clearly
#2345 * 10^-2 or 2345 E -2
```

for boolean we have True and False as constants! beside mathematical use we aint we complex numbers.

<hr>

Literals!! Direct data written in the program or used in the program is called literals!! and if permantly set the value to that literals then it can be called as constants!!

**Base Conversion Functions:**

Python have some build in functions for base conversion!! bin(int) -> binary,
oct(int) -> octal, hex(int) -> hexadecimal, int(str) -> decimal

**Type conversion:**

functions available: 
1. int()
2. float()
3. bool()
4. complex()
5. str()

**Loops:**

"Else" in python can be used in many ways!!

**With While loop:**

```py
while <condition>:
  s1
  s2
else:
  s3
```

So conditionally it get executed! tho i dont find any benifit using this! in many condition the while may stop without the condition getting false! so in such cases it will be useful!!

**for loops:**

range(start, stop, step) can be used with for loops to iterate over!! stop is not inclusive here! start is inclusive!

**for in loop:**

```py

for item in sequence:
  s1
  s2
```

so it work as an iterator!!

<hr>

### Strings

we can access string with the positive indices as well as the negative indices (reverse).

```py
s='hello'
l = len(s)
```

""" """ strings can be used to define multiline comments! python support double as well as single quotes!!

String Slicing: 

```py

s='hello world'
#strings are immutable so you can actually change any value here by dooing s[0]='l'
```

Slicing can help in such cases! 

s[start:stop:steps] can be used to slice!!  it's same as range function!

here as well the stop is not inclusive!

```py
s='hello'
s[0:2:2]
s[-1:-3]
```

so above example shows that we can use the -ve indices as well!!

we can also we IN and NOT IN operators to check if string s present in string s1.

dir(str) can list out all the methods related to the string class!!

Methods:

1. find(substring, start, end)
2. rfind(substring, start, end) : direction changed
3. index(substring, start, end) : slightly differ (it will hit the error if substring not present)
4. rindex(substring, start, end)
5. count(substring, start, end)
6. ljust(width, fillchar) : string will left justify
7. rjust(width, fillchar) : string align to right
8. center(width,fillchar)
9. zfill(width)
10. lstrip(chars:optional) : striping the spaces if chars not mentioned (data cleaning purpose)
11. rstrip(chars:optional)
12. strip(chars)
13. replace(oldstring, newstring, count)
14. join(iterable) : join with seperator mentioned "ab".join('a') result "aaba"
15. split(seperator,maxsplit)
16. rsplit(seperator, maxsplit) 
17. splitlines(keepends) : linewise split
18. startswith(prefix,start,end)
19. endswith(suffix,start,end)
20. removeprefix(prefix)
21. removesuffix(suffix)
22. partition(seperator)
23. rpartition(seperator)


For an ASCII code `ord(char)`!! and to get character use `chr(number)`.

<hr>

### List

List can store anything!! it is possible because the indices are referance! list is mutable!

indexing and slicing is same as strings! L[start : end : steps].

inserting anywhere is possible!! 

````py

L[0:0] = [10]

#inserting 10 at 0th location and all othere elements will get shifted to right
#you can insert more than one element

L[3:3] = [10,12,12]
````

Giving range will modify/delete the existing elements!  append function can be used to push from back!!

```py

l = [1,2,3,4]

l.extend([1,1,1])

#this can be used to extend the list l
#if used string inside extend it will split it as an array of characters
```

to create shallow copy!! use list.copy() function!!

function to remove the elements from list!! 

1. pop()
2. remove()
3. clear()
4. del()

pop(index:optional) so if index not mentioned bydefault it will take last element to be poped.

remove(element:required) so it will remove the specific element from the list

clear() will empty the list totally!

del is similar to pop!! for example if wanted to remove from index 2! 

```py
del l[2]

#also we can use slicing to delete the range

del l[1:4]
```

#### Sorting!!

Methods:

1. index(element, start, end)
2. count(element)
3. reverse()
4. sort(*, key=None, reverse=false)

we can mentioned key as argument so w.r.t that it will sort the things out!! 

like if we have list of strings and we wanted to sort it by the length of strings then we mention `l.sort(key=len)`. 
while sorting strings only with no key it will take the asicii values in consideration!!

**list comprehentions**

so suppose you have an iterable to be added in list so here list comprehensions will work smoothly!!

```py
L = [iterable]

#comprehensions

L = [expression for item in iterable]
```

for example:

```py

L = [x**2  for x in range(1,5)]

L1 = [x.lower() for x in 'pytHON']
```

<hr>

### Tuple

The data type is immutable!! 

```py
t = (1,2,3,4,5,6)
```
 It can have duplicates and take any data type!!

````py
t1 = (1,2,34,4)

t2 = tuple([1,2,3,4,54])

t3= ()

#below is not valid as if we are writing the number we can use braces!!!
t4 = (3)  #wrong
t4= (3,) #right
#so when you only have 1 number in tuple add , after it

````

**Tuple comprehension**

There are some minor changes w.r.t to list comprehension!!

```py
T = tuple(iterable) #correct
```

so suppose you wanted to unpack each element and wanted to do like below:

```py
T = (iterable) #wrong
```

so here we'll mention!!

```py
T = (exp for item in iterable) #wrong
```

But this wont work in python it will create a generator object! it still needs to be unpacked!! so we have to mentioned * at front!! and as we are making tuple  we have to add the ( _ ) braces as well!! what if there is single element in the iterable, so to handle that we'll have to add , as well!!

```py
T = ( *(expression for item in iterable), )
```


we can access tuple elements using indexing and as well as slicing works on tuple same as list!!

packing and unpacking also works here!! *can be used to unpack the multiple values for exaple:

```py
t = 1,2,3,4,5

# if you assign multiple values to one varible it will pack it and make a tuple so above expression work

a,b,*c = t

# so here a = 1, b = 2 and c = [3,4,5] so here * will be used to unpack multiple values
```

<hr>

### Sets
can be defined as: 

```py

s = {1,2,3}

s = set([1,2,3,4])

s = set('python')

# you cant define set as s={} or empty in curly braces!! there must be least one value
s4 = {5}
```

the {} empty braces it think as a dictionary! so there must be least one element to define it as a set!!

the sets are not ordered!! 

you can use the function add to add the items in the set!! you can add the strings, integers, tuple !! so it accept any type of values !!  but  list is now allowed it will give error unhashable type: 'list'!! because the lists are immutable to it cannot be hashed because of change in values!! So set only can have the mutable data types!

remove(element) will remove the specific element!! pop() function will remove the last value but as it do not have indices so you wont have control over which value will be getting deleted!!

**sets Internals**

The technique used to store the element in set is hashing!! Sets use hashing in python! 


