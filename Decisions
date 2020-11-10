## P3.1.py

 Write a program that reads an integer and prints whether it is negative, zero, or positive.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
userInput = int(input("Enter an integer: "))

if userInput < 0:
    print("It's negative")

elif userInput == 0:
    print("It's zero")

else:
    print("It's positive")
```

</p>
</details>


***

## P3.2.py
#  Write a program that reads a floating­point number and prints “zero” if the number is zero. Otherwise, print “positive” or “negative”. Add “small” if the absolute valueof the number is less than 1, or “large” if it exceeds 1,000,000.


<details><summary>💾  Alternative solution </summary>
<p>

``` python
userInput = float(input("Enter a floating-point number: "))

if userInput == 0:
    print("It's zero")

elif userInput > 0:
    print("It's positive")

else:
    print("It's negative")

if userInput < 1:
    print("and small")
elif userInput > 1000000:
    print("and large")
```

</p>
</details>


***

## P3.3.py
 Write a program that reads an integer and prints how many digits the number has, by
 checking whether the number is ≥ 10, ≥ 100, and so on. (Assume that all integers are
 less than ten billion.) If the number is negative, first multiply it by –1.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
userInput = int(input("Enter an integer: "))

numDigits = 0

if userInput < 0:
    userInput *= -1


if userInput >= 10 and userInput < 100:
    numDigits = 2

elif userInput >= 100 and userInput < 1000:
    numDigits = 3

elif userInput >= 1000 and userInput < 10000:
    numDigits = 4

elif userInput >= 10000 and userInput < 100000:
    numDigits = 5

elif userInput >= 100000 and userInput < 1000000:
    numDigits = 6

elif userInput >= 1000000 and userInput < 10000000:
    numDigits = 7

elif userInput >= 10000000 and userInput < 100000000:
    numDigits = 8

elif userInput >= 100000000 and userInput < 1000000000:
    numDigits = 9

elif userInput >= 1000000000 and userInput < 10000000000:
    numDigits = 10

elif userInput >= 10000000000 and userInput < 100000000000:
    numDigits = 11

else:
    numDigits = "greater than 11(10 billion)"


print("The number of digits is:", numDigits)
```

</p>
</details>


***

## P3.4.py

Write a program that reads three numbers and prints “all the same” if they are all the
same, “all different” if they are all different, and “neither” otherwise.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
number1 = float(input("Enter number one: "))
number2 = float(input("Enter number two: "))
number3 = float(input("Enter number three: "))

if number1 == number2 and number2 == number3 :
    print("They're all the same")

elif number1 != number2 and number2 != number3 and number1 != number3:
    print("They're all different")

else:
    print("Neither")
```

</p>
</details>


***

## P3.5.py
Write a program that reads three numbers and prints “increasing” if they are
in increasing order, “decreasing” if they are in decreasing order, and “neither”
otherwise. Here, “increasing” means “strictly increasing”, with each value larger
than its predecessor. The sequence 3 4 4 would not be considered increasing.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
number1 = float(input("Enter number one: "))
number2 = float(input("Enter number two: "))
number3 = float(input("Enter number three: "))

if number1 < number2 < number3:
    print("Increasing")

elif number1 > number2 > number3:
    print("Decreasing")

else:
    print("Neither")
```

</p>
</details>


***

## P3.6.py
Repeat Exercise P3.5, but before reading the numbers, ask the user whether increas­
ing/decreasing should be “strict” or “lenient”. In lenient mode, the sequence 3 4 4 is
increasing and the sequence 4 4 4 is both increasing and decreasing

<details><summary>💾 Alternative solution </summary>
<p>

``` python
order = str(input("Strict or lenient?: "))

number1 = float(input("Enter number one: "))
number2 = float(input("Enter number two: "))
number3 = float(input("Enter number three: "))

if order == "strict" or order == "Strict":
    if number1 < number2 < number3:
        print("Increasing")

    elif number1 > number2 > number3:
        print("Decreasing")

    else:
        print("Neither")

elif order == "lenient" or order == "Lenient":
    if (number1 < number2 <= number3) or (number1 <= number2 < number3):
        print("Increasing")

    elif (number1 > number2 >= number3) or (number1 >= number2 > number3):
        print("Decreasing")

    elif number1 == number2 and number2 == number3:
        print("Increasing and decreasing")

    else:
        print("Neither")
```

</p>
</details>


***

## P3.7.py

 Write a program that reads in three integers and prints “in order” if they are sorted in
 ascending or descending order, or “not in order” otherwise. For example,
     1 2 5 in order
     1 5 2 not in order
     5 2 1 in order
     1 2 2 in order

<details><summary>💾 Alternative solution </summary>
<p>

``` python
number1 = float(input("Enter number one: "))
number2 = float(input("Enter number two: "))
number3 = float(input("Enter number three: "))

if (number1 < number2 < number3) or (number1 > number2 > number3)\
    or (number1 <= number2 < number3) or (number1 < number2 <= number3)\
    or (number1 >= number2 > number3) or (number1 > number2 >= number3):
      print("In order")

else:
    print("Not in order")

```

</p>
</details>


***

## P3.8.py

 Write a program that reads four integers and prints “two pairs” if the input consists
 of two matching pairs (in some order) and “not two pairs” otherwise. For example,
     1 2 2 1 two pairs
     1 2 2 3 not two pairs
     2 2 2 2 two pairs

<details><summary>💾 Alternative solution </summary>
<p>

``` python
number1 = int(input("Enter number one: "))
number2 = int(input("Enter number two: "))
number3 = int(input("Enter number three: "))
number4 = int(input("Enter number four: "))

if number1 == number4 and number2 == number3:
    print("Two pairs")

elif number1 == number2 and number3 == number4:
    print("Two pairs")

elif number1 == number2 and number1 == number3 and number1 == number4:
    print("Two pairs")

else:
    print("Not two pairs")

```

</p>
</details>


***

## P3.9.py

 Write a program that reads a temperature value and the letter C for Celsius or F for
 Fahrenheit. Print whether water is liquid, solid, or gaseous at the given temperature
 at sea level.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
type = str(input("Enter the temperature type, C for celsius or F for fahrenheit: "))
temperature = float(input("Enter the temperature: "))

if type == "C":
    if temperature >= 0 and temperature < 100:
        print("Water is liquid.")

    elif temperature >= 100:
        print("Water is gaseous.")

    else:
        print("Water is solid.")

elif type == "F":
    if temperature >= 32 and temperature < 132:
        print("Water is liquid.")

    elif temperature >= 132:
        print("Water is gaseous.")

    else:
        print("Water is solid.")
```

</p>
</details>


***

## P3.10.py

  The boiling point of water drops by about one degree Celsius for every 300 meters
 (or 1,000 feet) of altitude. Improve the program of Exercise P3.9 to allow the user to
 supply the altitude in meters or feet.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
FREEZE_CELSIUS = 0
FREEZE_FAHRENHEIT = 32
boil_celsius = 100
boil_fahrenheit = 212

temperature = float(input("Enter the temperature: "))
type = str(input("Enter C for celsius or F for fahrenheit: "))
altitude = float(input("Enter the altitude above sea level: "))
units = str(input("Enter M for meters or F for feet: "))

if type == "C":
    if units == "M":
        boil_celsius -= (altitude / 300)

    else:
        boil_celsius -= (altitude / 1000)

    if temperature <= FREEZE_CELSIUS:
        print("Solid")

    elif temperature >= boil_celsius:
        print("Gas")

    else:
        print("Liquid")

else:
    if units == "M":
        boil_fahrenheit -= (altitude / 300)

    else:
        boil_fahrenheit -= (altitude / 1000)

    if temperature <= FREEZE_FAHRENHEIT:
        print("Solid")

    elif temperature >= boil_fahrenheit:
        print("Gas")

    else:
        print("Liquid")
```

</p>
</details>


***

## P3.

<details><summary>💾 Alternative solution </summary>
<p>

``` python

```

</p>
</details>


***

## P3.

<details><summary>💾 Alternative solution </summary>
<p>

``` python

```

</p>
</details>


***
