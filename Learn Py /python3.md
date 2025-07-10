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



