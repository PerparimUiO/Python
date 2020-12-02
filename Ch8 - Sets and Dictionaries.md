## P8.1
 Write a new version of the program intname.py
 from Chapter 5 to use a dictionary
 instead of if statements.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
def main():
    value = int(input("Please enter a positive integer < 1000: "))
    print(intName(value))


def int_name(number):
    part = number   # The part that still needs to be converted.
    name = ""   # The name of the number.

    if part >= 100:
        name = digitName(part // 100) + " hundred"
        part = part % 100

    if part >= 20:
        name = name + " " + tensName(part)
        part = part % 10
    elif part >= 10:
        name = name + " " + teenName(part)
        part = 0

    if part > 0:
        name = name + " " + digitName(part)
    return name


def digit_name(digit):
    digits = {1: "one", 2: "two", 3: "three", 4: "four", 5:
              "five", 6: "six", 7: "seven", 8: "eight", 9: "nine"}
    return digits[digit]


def teen_name(number):
    numbers = {
        10: "ten", 11: "eleven", 12: "twelve", 13: "thirteen", 14: "fourteen",
        15: "fifteen", 16: "sixteen", 17: "seventeen", 18: "eighteen", 19: "nineteen"}
    return numbers[number]


def tens_name(number):
    numbers = {90: "ninety", 80: "eighty", 70: "seventy", 60:
               "sixty", 50: "fifty", 40: "forty", 30: "thirty", 20: "twenty"}
    return numbers[number]


# Start the program.
if __name__ == '__main__':
    main()
```

</p>
</details>

***
## P8.2
 Write a program that counts how often each word occurs in a text file.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# IMPORTS
from sys import argv
 
# FUNCTIONS
def clean(string):
    output_string = ""
    for char in string:
        if char.isalpha():
            output_string += char
    return output_string.lower()


def count_words(filename):
    output_dictionary = {}
    with open(filename, "r") as file:
        for line in file:
            words = line.split()
            word_times = 1
            for word in words:
                word = clean(word)
                if word in output_dictionary:
                    word_times += 1
                output_dictionary[word] = word_times

    return output_dictionary


def print_dictionary(dictionary):
    for key in sorted(dictionary):
        print("{}: {}".format(key, dictionary[key]))


# main
def main():
    words = count_words(argv[1])
    print_dictionary(words)


# PROGRAM RUN
if __name__ == "__main__":
    main()
```

</p>
</details>

***
## P8.9
 Write a program that asks a user to type in two strings and that prints
 •    the characters that occur in both strings.
 •    the characters that occur in one string but not the other.
 •    the letters that don’t occur in either string.
 Use the set function to turn a string into a set of characters.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def shared_characters(string_a, string_b):
    string_a = set(string_a)
    string_b = set(string_b)
    return ", ".join(sorted(string_a.intersection(string_b)))


def unique_characters(string_a, string_b):
    string_a = set(string_a)
    string_b = set(string_b)
    return ", ".join(sorted(string_a.difference(string_b).union(string_b.difference(string_a))))


def non_occurring_letters(string_a, string_b):
    alphabet = set("abcdefghijklomnopqrstuvwxyz")
    string_a = set(string_a)
    string_b = set(string_b)
    return ", ".join(sorted(alphabet - string_a.union(string_b)))


# main
def main():
    string_a = str(input("Enter the first string: "))
    string_b = str(input("Enter the second string: "))
    print("Shared characters:")
    print(shared_characters(string_a, string_b))
    print("Unique characters")
    print(unique_characters(string_a, string_b))
    print("Non-occuring alphabet letters:")
    print(non_occurring_letters(string_a, string_b))


# PROGRAM RUN
if __name__ == "__main__":
    main()
   
# Unit test for P8.9


# IMPORTS
import P8_9
import unittest


# main
class StringSetsTest(unittest.TestCase):
    def setUp(self):
        self.dummy_a = "abra"
        self.dummy_b = "kadabra"

    def test_shared_characters(self):
        self.assertEqual("a, b, r", P8_9.shared_characters(self.dummy_a, self.dummy_b))

    def test_unique_characters(self):
        self.assertEqual("d, k", P8_9.unique_characters(self.dummy_a, self.dummy_b))

    def test_non_occurring_characters(self):
        self.assertEqual("c, e, f, g, h, i, j, l, m, n, o, p, q, s, t, u, v, w, x, y, z", P8_9.non_occurring_letters(self.dummy_a, self.dummy_b))


# PROGRAM RUN
if __name__ == '__main__':
    unittest.main()
```

</p>
</details>

***
## P8.10
 Write a program that reads in two files and prints out,
 in sorted order, all words that are common to both of them.

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# IMPORTS
from pprint import pprint


# FUNCTIONS
def clean(string):
    output_string = ""
    for char in string:
        if char.isalpha():
            output_string += char
    return output_string.lower()


def file_contents_to_set(filename):
    output = set()
    opened_file = open(filename, "r")

    for line in opened_file:
        words = line.split()
        for word in words:
            word_cleaned = clean(word)
            if word_cleaned != "":
                output.add(word_cleaned)
    opened_file.close()
    return output


def common_words(set_a, set_b):
    return set_a.intersection(set_b)


# main
def main():
    file_a = str(input("Enter file a's filename: "))
    file_b = str(input("Enter file b's filename: "))

    set_a = file_contents_to_set(file_a)
    set_b = file_contents_to_set(file_b)

    pprint(common_words(set_a, set_b), indent=4)


# PROGRAM RUN
if __name__ == "__main__":
    main()
    
# Unit test for P8.10


# IMPORTS
import P8_10
import unittest
from os import remove


# main
class FilesCommonWordsTest(unittest.TestCase):
    def setUp(self):
        opened_file = open("test_file_a", "w")
        opened_file.write("marry had a little lamb")
        opened_file.close()

        opened_file = open("test_file_b", "w")
        opened_file.write("And everywhere that Marry went, the lamb was sure to go.")
        opened_file.close()

    def test_file_contents_to_set_a(self):
        expected = {"a", "had", "lamb", "little", "marry"}
        self.assertSetEqual(expected, P8_10.file_contents_to_set("test_file_a"))

    def test_file_contets_to_set_b(self):
        expected = {"and", "everywhere", "go", "lamb", "marry", "sure", "that", "the", "to", "was", "went"}
        self.assertSetEqual(expected, P8_10.file_contents_to_set("test_file_b"))

    def test_common_words(self):
        set_a = P8_10.file_contents_to_set("test_file_a")
        set_b = P8_10.file_contents_to_set("test_file_b")
        expected = {"lamb", "marry"}
        self.assertSetEqual(expected, P8_10.common_words(set_a, set_b))

    def tearDown(self):
        remove("test_file_a")
        remove("test_file_b")


# PROGRAM RUN
if __name__ == '__main__':
    unittest.main()
```

</p>
</details>

***
## P8.18
 Given a dictionary
 gradeCounts = { "A": 8, "D": 3, "B": 15, "F": 2, "C": 6 }
 write the Python statement(s) to print:
 
   a.   all the keys.
   b.   all the values.
   c.   all the key and value pairs.
   d.   all of the key and value pairs in key order.
   e.   the average value.
  
 f.   a chart similar to the following in which each row contains a key followed by a
 number of asterisks equal to the key’s data value. The rows should be printed in
 key order, as shown below.
 A: ********
 B: ***************
 C: ******
 D: ***
 F: **

<details><summary>💾 Alternative solution </summary>
<p>

``` python
# FUNCTIONS
def print_keys(dictionary):
    keys = []
    for key in sorted(dictionary.keys()):
        keys.append(key)
    return "\n".join(keys)


def print_values(dictionary):
    values = []
    for value in dictionary.values():
        values.append(value)
    values = list(map(str, sorted(values)))
    return "\n".join(values)


def print_pairs(dictionary):
    pairs = []
    for key in sorted(dictionary):
        pairs.append((key, dictionary[key]))
    pairs.sort()
    return "\n".join(map(str, pairs))


def print_average_value(dictionary):
    total = 0
    sum = 0
    for value in dictionary.values():
        total += 1
        sum += value
    return sum / total


def print_bar_charts(dictionary):
    output_bars = []
    for key in sorted(dictionary):
        bar_chart = "*" * dictionary[key]
        output_bars.append("{}: {}".format(key, bar_chart))
    return "\n".join(output_bars)


# main
def main():
    grade_counts = {"A": 8, "D": 3, "B": 15, "F": 2, "C": 6}
    print(print_keys(dictionary))


# PROGRAM RUN
if __name__ == "__main__":
    main()
    
# Unit test for R8.18

# IMPORTS
import R8_18
import unittest


# main
class Print_Dictionary_Tests(unittest.TestCase):
    def setUp(self):
        self.dummy_dictionary = {"A": 8, "D": 3, "B": 15, "F": 2, "C": 6}

    def test_print_keys(self):
        self.assertEqual("A\nB\nC\nD\nF", R8_18.print_keys(self.dummy_dictionary))

    def test_print_values(self):
        self.assertEqual("2\n3\n6\n8\n15", R8_18.print_values(self.dummy_dictionary))

    def test_print_pairs_sorted(self):
        self.assertEqual("('A', 8)\n('B', 15)\n('C', 6)\n('D', 3)\n('F', 2)", R8_18.print_pairs(self.dummy_dictionary))

    def test_print_average_value(self):
        self.assertEqual((8+3+15+2+6)/5, R8_18.print_average_value(self.dummy_dictionary))

    def test_print_bar_charts(self):
        self.assertEqual("A: ********\nB: ***************\nC: ******\nD: ***\nF: **", R8_18.print_bar_charts(self.dummy_dictionary))


# PROGRAM RUN
if __name__ == '__main__':
    unittest.main()
```

</p>
</details>

***
