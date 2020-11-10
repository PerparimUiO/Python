## P4.1A.py
 Write programs with loops that compute
     a.  The sum of all even numbers between 2 and 100 (inclusive).
     b.  The sum of all squares between 1 and 100 (inclusive).
     c.  All powers of 2 from 2 0 up to 2 20 .
     d.  The sum of all odd numbers between  a and  b (inclusive), where  a and  b are
     inputs.
     e.  The sum of all odd digits of an input. (For example, if the input is 32677, the
     sum would be 3 + 7 + 7 = 17.)

<details><summary>💾 Alternative solution </summary>
<p>

``` python
sum = 0.0
for i in range(2, 101, 2):
    sum += i

print(sum)
```

</p>
</details>


***

## P4.1B.py

<details><summary>💾 Alternative solution </summary>
<p>

``` python
sum = 0.0

for i in range(1, 101):
    sum += i * i

print(sum)
```

</p>
</details>


***
## P4.1C.py

<details><summary>💾 Alternative solution </summary>
<p>

``` python
for i in range(21):
    print(2 ** i)
```

</p>
</details>


***

## P4.1D.py

<details><summary>💾 Alternative solution </summary>
<p>

``` python
sum = 0.0

a = int(input("Enter a: "))
b = int(input("Enter b:"))

for i in range(a, b):
    sum += i

print(sum)
```

</p>
</details>


***
## P4.1E.py

<details><summary>💾 Alternative solution </summary>
<p>

``` python
sum = 0.0
n = int(input("Enter a number: "))

numberDigits = len(str(n))

for i in range(numberDigits):
    digit = n % 10
    if digit % 2 != 0:
        sum += digit

    n = int(n / 10)

print(sum)
```

</p>
</details>


***

## P4.2A.py
 Write programs that read a sequence of integer inputs and print
    a.  The smallest and largest of the inputs.
    b.  The number of even and odd inputs.
    c.  Cumulative totals. For example, if the input is 1 7 2 9, the program should print
    1 8 10 19.
    d.  All adjacent duplicates. For example, if the input is 1 3 3 4 5 5 6 6 6 2, the
    program should print 3 5 6.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# imports
from sys import exit

list = []
stop = False
while not stop:
    inputN = str(input("Enter a number:(Stop/stop to stop): "))
    if inputN == "stop" or inputN == "Stop":
        stop = True

    else:
        if inputN.isdigit():
            inputN = int(inputN)
            list.append(inputN)

if not list:
    exit("List is empty")

print("Largest:", max(list))
print("Smallest:", min(list))
```

</p>
</details>


***
## P4.2B.py

<details><summary>💾 Alternative solution </summary>
<p>

``` python
numEven = 0
numOdd = 0

stop = False

while not stop:
    inputN = str(input("Enter a number:(Stop/stop to stop): "))

    if inputN == "Stop" or inputN == "stop":
        stop = True

    elif inputN.isdigit():
        inputN = int(inputN)
        if inputN % 2 == 0:
            numEven += 1
        else:
            numOdd += 1

print("Number of even numbers:", numEven)
print("Number of odd numbers:", numOdd)
```

</p>
</details>


***

## P4.2C.py

<details><summary>💾 Alternative solution </summary>
<p>

``` python
stop = False
sum = 0

print("Enter a series of number(Stop/stop to stop)")

while not stop:
    inputN = str(input("Input: "))

    if inputN == "stop" or inputN == "Stop":
        stop = True

    elif inputN.isdigit():
        inputN = int(inputN)
        sum += inputN
        print("Output:", sum)
```

</p>
</details>


***
## P4.3A.py
 Write programs that read a line of input as a string and print
     a.  Only the uppercase letters in the string.
     b.  Every second letter of the string.
     c.  The string, with all vowels replaced by an underscore.
     d.  The number of digits in the string.
     e.  The positions of all vowels in the string.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
inputString = str(input("Enter a string: "))

result = ""

for i in range(len(inputString)):
    if inputString[i].isupper():
        result += inputString[i]

print(result)
```

</p>
</details>


***

## P4.3B.py

<details><summary>💾 Alternative solution </summary>
<p>

``` python
inputString = str(input("Enter a string: "))
result = ""

for i in range(0, len(inputString), 2):
    result += inputString[i]

print(result)
```

</p>
</details>


***
## P4.3C.py

<details><summary>💾 Alternative solution </summary>
<p>

``` python
inputString = str(input("Enter a string: "))
outputString = ""
# saving time writing long statements
vowels = ('a','e','i','o','u','A','E','I','O','U')

for i in range(len(inputString)):
    if inputString[i] in vowels:
        outputString += "_"

    else:
        outputString += inputString[i]

print(outputString)
```

</p>
</details>


***

## P4.3D.py

<details><summary>💾 Alternative solution </summary>
<p>

``` python
inputString = str(input("Enter a string: "))
numDigits = 0

for i in range(len(inputString)):
    if inputString[i].isdigit():
        numDigits += 1

print("Number of digits:", numDigits)
```

</p>
</details>


***
## P4.3E.py

<details><summary>💾 Alternative solution </summary>
<p>

``` python
inputString = str(input("Enter a string: "))
positions = ""
# saving time writing long statements
vowels = ('a','e','i','o','u','A','E','I','O','U')

for i in range(len(inputString)):
    if inputString[i] in vowels:
            positions += str(i) + "-"


# fix for the last dash in the positions string
positions = positions[:-1]
print(positions)
```

</p>
</details>


***

## P4.4.py
Complete the program in How To 4.1 on page 182. Your program should read twelve
temperature values and print the month with the highest temperature.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
temperatures = []
maxTemperatureMonth = 1

for i in range(13):
    temperatureInput = float(input("Enter a temperature: "))
    temperatures.append(temperatureInput)

maxTemperature = max(temperatures)

# could be implemented in the previous loop but this is more readable
for i in range(13):
    if maxTemperature == temperatures[i]:
        maxTemperatureMonth = i

print("Max temperature month:", maxTemperatureMonth)
print("Max temperature:", maxTemperature)
```

</p>
</details>


***
## P4.5.py
 Write a program that reads a set of floating-point values. Ask the user to enter the
 values, then print
     • the average of the values.
     • the smallest of the values.
     • the largest of the values.
     • the range, that is the difference between the smallest and largest.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
inputN = float(input("Enter a number(0 to stop): "))
total = 0
count = 0
min = inputN
max = inputN

while inputN != 0.0:
    total += inputN
    count += 1

    if inputN < min:
        min = inputN

    if inputN > max:
        max = inputN

    inputN = float(input("Enter a number(0 to stop): "))


if count == 0:
    print("No numbers entered")

else:
    average = total / count
    print("Average", average)
    print("Smallest:", min)
    print("Biggest:", max)
    range = max - min
    print("Range between smallest and biggest:", range)
```

</p>
</details>


***

## P4.6.py
 Translate the following pseudocode for finding the minimum value from a set of
 inputs into a Python program.
 `    Set a Boolean variable "first" to true.
     While another value has been read successfully
         If first is true
             Set the minimum to the value.
             Set first to false.
         Else if the value is less than the minimum
             Set the minimum to the value.
     Print the minimum. `

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# imports
from sys import exit


first = True

try:
    inputN = float(input("Enter a number: "))

except ValueError:
    print("Not a number")
    exit()

minN = inputN

while True:
    try:
        inputN = float(input("Enter a number: "))

    except ValueError:
        break

    if first == True:
        minN = inputN
        first = False

    elif inputN < minN:
        minN = inputN

print("Minimum value", minN)
```

</p>
</details>

***
## P4.

<details><summary>💾 Alternative solution </summary>
<p>

``` python

```

</p>
</details>

***
## P4.

<details><summary>💾 Alternative solution </summary>
<p>

``` python

```

</p>
</details>

***
v
## P4.

<details><summary>💾 Alternative solution </summary>
<p>

``` python

```

</p>
</details>

***
v
## P4.

<details><summary>💾 Alternative solution </summary>
<p>

``` python

```

</p>
</details>

***
## P4.

<details><summary>💾 Alternative solution </summary>
<p>

``` python

```

</p>
</details>

***
## P4.

<details><summary>💾 Alternative solution </summary>
<p>

``` python

```

</p>
</details>

***
## P4.

<details><summary>💾 Alternative solution </summary>
<p>

``` python

```

</p>
</details>

***
## P4.

<details><summary>💾 Alternative solution </summary>
<p>

``` python

```

</p>
</details>

***
