***
## P6.1
 Write a program that initializes a list with ten random integers
  and then prints four
 lines of output, containing
 •	 Every element at an even index.
 •	 Every even element.
 •	 All elements in reverse order.
 •	 Only the first and last element.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# IMPORTS
from random import randint

# PROGRAM RUN
list = []
for i in range(10):
    randomN = randint(-99, 99)
    list.append(randomN)


print("Elements at an even index")
for i in range(0, len(list), 2):
    print(list[i])

print("Every even element")
for element in list:
    if element % 2 == 0:
        print(element)

print("All elements in reversed order")
for i in range(len(list) - 1, -1, -1):
    print(list[i])

print("Only the first and last element")
print(list[0], list[-1])
```

</p>
</details>

***
## P6.2
 Write a program that reads numbers and adds them to a list if they aren’t already
 contained in the list. When the list contains ten numbers, the program displays the
 contents and quits.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# PROGRAM RUN

list = []

print("Enter numbers: ")
while len(list) < 11:
    try:
        inputN = float(input())
        if inputN not in list:
            list.append(inputN)

    except ValueError:
        print("Not a number")


print("List contents")
for element in list:
    print(element)
```

</p>
</details>

******
## P6.3
 Write a program that adds all numbers from 2 to 10,000 to a list.
 Then remove the multiples of 2 (but not 2), multiples of 3 (but not 3),
 and so on, up to the multiples of 100. Print the remaining values.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def fillList(list):
    for i in range(2, 10001):
        list.append(i)

    return list

def removeMultiples(list):
    # for i in range(len(list) - 1, -1, -1):
    #     number = list[i]
    #     pop = False
    #     for j in range(100, 1, -1):
    #         if number != j:
    #             pop = True
    #             break
    #
    #     if pop == True:
    #         list.remove(number)

    for i in range(10000, 1, -1):
        remove = False
        for j in range(100, 1, -1):
            if i != j and i % j == 0:
                remove = True
        if remove == True:
            list.remove(i)

    return list

# main
def main():
    exampleList = []
    exampleList = fillList(exampleList)

    print("Before")
    print(exampleList)

    print("After")
    print(removeMultiples(exampleList))

# PROGRAM RUN
main()
```

</p>
</details>

***
## P6.4A
 Write list functions that carry out the following tasks for a list of integers. For each
 function, provide a test program.
     a.	 Swap the first and last elements in the list.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def swapFirst_and_Last(list):
    # bubble sort
    temp = list[0]
    list[0] = list[-1]
    list[-1] = temp

    return temp

# main
def main():
    exampleList = [ 5, 6, 7, 4]
    print("Before the swap")
    print(exampleList)

    swapFirst_and_Last(exampleList)

    print("After the swap")
    print(exampleList)

# PROGRAM RUN
main()
```

</p>
</details>

******
## P6.4B
 Write list functions that carry out the following tasks for a list of integers. For each
 function, provide a test program.
     b.	 Shift all elements by one to the right and move the last element into the first
 position. For example, 1 4 9 16 25 would be transformed into 25 1 4 9 16

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def shift(list):
    replace = 1
    for i in range(len(list)):
        tempSwap = list[i]
        list[i] = list[i - replace]
        list[i - replace] = tempSwap
        replace += 1


# main
def main():
    exampleList = [ 1, 4, 9, 16, 25 ]

    shift(exampleList)

    print(exampleList)

# PROGRAM RUN
main()
```

</p>
</details>

***
## P6.4C
 Write list functions that carry out the following tasks for a list of integers. For each
 function, provide a test program.
     c.	 Replace all even elements with 0.


<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def replaceEven_with_Null(list):
    for i in range(len(list)):
        if list[i] % 2 == 0:
            list[i] = 0

    return list

# main
def main():
    exampleList = [ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

    replaceEven_with_Null(exampleList)
    print("Even numbers replaced with 0")
    print(exampleList)

# PROGRAM RUN
main()
```

</p>
</details>

******
## P6.4D
 Write list functions that carry out the following tasks for a list of integers. For each
 function, provide a test program.
     d.	 Replace each element except the first and last by the larger of its two neighbors.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def replaceList_exceptFirstLast(list):
    for i in range(1, len(list) - 1):
        larger = list[i - 1]
        if larger < list[i + 1]:
            larger = list[i + 1]

        list[i] = larger

    return list

# main
def main():
    exampleList = [ 5, 10, 15, 20, 31, -5, 1, 2 ]
    print("List before")
    print(exampleList)

    replaceList_exceptFirstLast(exampleList)
    print("List after replacing")
    print(exampleList)

# PROGRAM RUN
main()

```

</p>
</details>

***
## P6.4E
 Write list functions that carry out the following tasks for a list of integers. For each
 function, provide a test program.
     e.	 Remove the middle element if the list length is odd, or the middle two elements
     if the length is even.

<details><summary>💾 Alternative solution </summary>
<p>

``` python


# FUNCTIONS
def removeMidElement(list):
    lenList = len(list)
    halfLen = lenList // 2

    if lenList % 2 == 0:
        list.pop(halfLen - 1)
        list.pop(halfLen)

    else:
        list.pop(halfLen)

    return list

# main
def main():
    exampleList = [ 5, 10, 20, 11, -2, -56, 1 ]
    print("Before")
    print(exampleList)

    print("After removing the middle element(s)")
    removeMidElement(exampleList)
    print(exampleList)

# PROGRAM RUN
main()
```

</p>
</details>

******
## P6.4F
 Write list functions that carry out the following tasks for a list of integers. For each
 function, provide a test program.
     f.	 Move all even elements to the front, otherwise preserving the order of the
     elements.
<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def moveEvenToFront(list):
    start = 0
    for i in range(len(list)):
        if list[i] % 2 == 0:
            # more efficient way without using a temp variable
            list[start], list[i] = list[i], list[start]
            start += 1

    return list
# main
def main():
    exampleList = [ 5, 10, 12, -5, -3, 8, 17 ]

    print("Before")
    print(exampleList)

    print("After moving even at front")
    moveEvenToFront(exampleList)
    print(exampleList)

# PROGRAM RUN
main()
```

</p>
</details>

***
## P6.4G
 Write list functions that carry out the following tasks for a list of integers. For each
 function, provide a test program.
     g.	 Return the second-largest element in the list.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def secondLargest(list):
    largestElement = max(list)

    # fixes cases where largest element appears multiple times
    while largestElement in list:
        list.remove(largestElement)

    return max(list)

# main
def main():
    exampleList = [ 10, 15, -5, 60, -84, 60, 60, 25 ]
    print("List")
    print(exampleList)

    print("Second largest:", secondLargest(exampleList))

# PROGRAM RUN
main()
```

</p>
</details>

******
## P6.4H
 Write list functions that carry out the following tasks for a list of integers. For each
 function, provide a test program.
     h.	 Return true if the list is currently sorted in increasing order.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def is_sorted(list):
    sortedBool = False


    for i in range(0, len(list) - 1):
        if list[i] < list[i + 1]:
            sortedBool = True

        else:
            return False

    return sortedBool

# main
def main():
    exampleListUnSorted = [ 5, 6, 1, 7 ]
    exampleListSorted = [ 1, 2, 3, 4 ]

    print("Unsorted list", exampleListUnSorted)
    print("Sorted list", exampleListSorted)

    print("Test unsorted: ", is_sorted(exampleListUnSorted))
    print("Test sorted: ", is_sorted(exampleListSorted))

# PROGRAM RUN
main()
```

</p>
</details>

***
## P6.4I
 Write list functions that carry out the following tasks for a list of integers. For each
 function, provide a test program.
     i.	 Return true if the list contains two adjacent duplicate elements.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def twoAdjacent(list):
    for i in range(len(list) - 1):
        if list[i] == list[i + 1]:
            return True

    return False

# main
def main():
    exampleListTrue = [ 5, 7, 7, 1, 2, 3 ]
    exampleListFalse = [ 5, 6, 7, 1, 2, 3]
    print("List, expected True", exampleListTrue)
    print("List, expected False", exampleListFalse)

    print("2 adjacent duplicates list True:", twoAdjacent(exampleListTrue))
    print("2 adjacent duplicates list False:", twoAdjacent(exampleListFalse))

# PROGRAM RUN
main()
```

</p>
</details>

******
## P6.4J
 Write list functions that carry out the following tasks for a list of integers. For each
 function, provide a test program.
     i.	 Return true if the list contains two adjacent duplicate elements.
     j.	 Return true if the list contains duplicate elements
            (which need not be adjacent).

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
# reuse from P6.4-I
def twoAdjacent(list):
    for i in range(len(list) - 1):
        if list[i] == list[i + 1]:
            return True

    return False

def duplicates(list):
    boolTwoAdjacent = twoAdjacent(list)

    for i in range(len(list)):
        if list.count(list[i]) > 1 and boolTwoAdjacent == False:
            return True

    return False

# main
def main():
    exampleListFalse = [ 5, 7, 7, 1, 2, 3 ]
    exampleListTrue = [ 5, 6, 7, 1, 2, 7 ]

    print("List expected False:", exampleListFalse)
    print("List expected True:", exampleListTrue)

    print("Test expected False:", duplicates(exampleListFalse))
    print("Test expected True:", duplicates(exampleListTrue))

# PROGRAM RUN
main()

```

</p>
</details>

***
## P6.5
 Modify the largest.py program in Section 6.3 to
 mark both the smallest and the largest elements.
 The modified author code to solve the problem
  This program reads a sequence of values and prints them,
  marking the largest and smallest values.


<details><summary>💾 Alternative solution </summary>
<p>

``` python
# Create an empty list.
values = []

# Read the input values.
print("Please enter values, Q to quit:")
userInput = input("")
while userInput.upper() != "Q" :
   values.append(float(userInput))
   userInput = input("")

# Find the largest value.
largest = values[0]
for i in range(1, len(values)) :
   if values[i] > largest :
      largest = values[i]

# Find the smallest value.
smallest = values[0]
for i in range(1, len(values)) :
    if values[i] < smallest :
        smallest = values[i]


# Print all values, marking the largest and smallest.
for element in values :
   print(element, end="")
   if element == largest :
      print(" <== largest value", end="")
   elif element == smallest :
       print(" <== smallest value", end="")

   print()
```

</p>
</details>

******
## P6.6
 Write a function sumWithoutSmallest that computes the sum of a list of values, except
 for the smallest one, in a single loop. In the loop, update the sum and the smallest
 value. After the loop, return the difference.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def sum_without_smallest(list):
    sumOutput = 0
    smallest = min(list)
    for element in list:
        sumOutput += element

    sumOutput -= smallest
    return sumOutput

# main
def main():
    exampleList = [ 1, 2, 3, 4, 5, 6, 7, 8, 9 ]
    print("List", exampleList)
    # unneeded but makes it easier to check the output
    print("Smallest:", min(exampleList))
    print("Sum w/ smallest:", sum(exampleList))
    print("Sum w/o  smallest:", sum_without_smallest(exampleList))

# PROGRAM RUN
main()
```

</p>
</details>

***
## P6.7
 Write a function removeMin that removes the minimum value from a list without using
 the min function or remove method.
<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def removeMin(list):
    minElement = list[0]
    minElement_position = 0

    # find min element
    for i in range(len(list)):
        if list[i] < minElement:
            minElement = list[i]
            minElement_position = i

    # replace and re-arrange the elements
    for i in range(minElement_position, len(list) - 1):
        list[i] = list[i + 1]

    return list

# main
def main():
    exampleList = [ 6, 5, 2, 1, 5, 7 ]
    print("List", exampleList)

    print("List without min element")
    print(removeMin(exampleList))

# PROGRAM RUN
main()
```

</p>
</details>

******
## P6.8
 Compute the alternating sum of all elements in a list. For example, if your pro­gram
 
     reads the input
     1  4  9  16  9  7  4  9  11

     then it computes
     1 – 4 + 9 – 16 + 9 – 7 + 4 – 9 + 11 = –2
<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def alternatingSum(list):
    outputSum = 0

    for i in range(len(list)):
        if i % 2 == 0:
            outputSum += list[i]

        else:
            outputSum -= list[i]

    return outputSum

# main
def main():
    exampleList = [ 1, 4, 9, 16, 9, 7, 4, 9, 11 ]
    print("List", exampleList)

    print("Alternating sum, expected -2:", alternatingSum(exampleList))

# PROGRAM RUN
main()

```

</p>
</details>

***
## P6.11
 Write a function def equals(a, b) that checks whether two lists have the same
 elements in the same order.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def equals(listA, listB):
    if len(listA) < len(listB) or len(listA) > len(listB):
        return False

    equalBool = False

    for i in range(len(listA)):
        if listA[i] == listB[i]:
            equalBool = True

        else:
            return False

    return equalBool

# main
def main():
    exampleListA = [ 10, 15, 20, 34, 5 ]
    exampleListB = [ 15, 23, 21, 15, 2 ]
    exampleListC = [ 15, 23, 21, 15, 2 ]
    print("The lists: A, B, C =>", exampleListA, exampleListB, exampleListC)
    print("Are A and B equal:", equals(exampleListA, exampleListB))
    print("Are A and C equal:", equals(exampleListA, exampleListC))
    print("Are B and C equal:", equals(exampleListB, exampleListC))


# PROGRAM RUN
main()
```

</p>
</details>

******
## P6.16
 Write a program that generates a sequence of 20 random values between 0 and 99 in
 a list, prints the sequence, sorts it, and prints the sorted sequence. Use the list sort
 method.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# IMPORTS
from random import randint

# FUNCTIONS
def generateSequence(list):
    for i in range(20):
        list.append(randint(0, 99))

    list.sort()
    return list

# main
def main():
    exampleList = []
    exampleList = generateSequence(exampleList)
    print(exampleList)

# PROGRAM RUN
main()
```

</p>
</details>

***
## P6.17
 Write a program that produces ten random permutations of the numbers 1 to 10. To
 generate a random permutation, you need to fill a list with the numbers 1 to 10 so
 that no two entries of the list have the same contents. You could do it by brute force,
 by generating random values until you have a value that is not yet in the list. But that
 is inefficient. Instead, follow this algorithm.
     Make a second list and fill it with the numbers 1 to 10.
     Repeat 10 times
          Pick a random element from the second list.
          Remove it and append it to the permutation list.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# IMPORTS
from random import randint

# FUNCTIONS
def generateSecondList(list):
    for i in range(1, 11):
        list.append(i)

    return list

def generatePermutationList(permList, secList):
    for i in range(10):
        randN = randint(0, len(secList) - 1)
        randN = secList[randN]
        permList.append(randN)

    return permList

# main
def main():
    permutationList = []
    secondList = []
    secondList = generateSecondList(secondList)

    permutationList = generatePermutationList(permutationList, secondList)
    print(permutationList)
# PROGRAM RUN
main()
```

</p>
</details>

******
## P6.28
 Write a function
 def appendList(a, b)
 that appends one list after another. For example, if a is
          1  4  9  16
 and b is
          9  7  4  9  11
 then append returns a new list containing the values
         1  4  9  16  9  7  4  9  11

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def appendList(listA, listB):
    for i in range(len(listB)):
        listA.append(listB[i])

    return listA

# main
def main():
    exampleA = [ 1, 4, 9, 16 ]
    exampleB = [ 9, 7, 4, 9, 11 ]
    print("List A", exampleA)
    print("List B", exampleB)

    print("Appended")
    print(appendList(exampleA, exampleB))

# PROGRAM RUN
main()
```
</p>
</details>

