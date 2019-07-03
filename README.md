# Strings Lab 1

## Question 1

Write code that prints out all the numbers from 1 to 10 as a single string.
(Hint: the `String()` function can convert an Int to a String)

```
var range = 1...10

for n in range {
print(String("\(n)"), terminator:" ")
}

```
***
## Question 2

Write code that prints out all the even numbers from 5 to 51 as a single string.
```
var range = 5...51

for n in range where n % 2 == 0{
print(String("\(n)"), terminator:" ")
}
```

***
## Question 3

Write code that prints out every number ending in 4 between 1 and 60 as a single string.
```
var range = 1...60

for n in range where n % 10 == 4{
print(String("\(n)"), terminator:" ")
}
```
***
## Question 4

Print each character in the string `"Hello world!"`

```
var string = "Hello world!"

for letter in string {
print(letter)
}
```
***
## Question 5

Print out the last character in the string below.  You cannot use the Character literal "!" (i.e you must access `myStringSeven`'s characters).

`let myStringSeven = "Hello world!"`

```

var lastChar = (myStringSeven.last)

print(lastChar)

```
***
## Question 6

Write code that switches on a string, given the following conditions:
- If the string's length is even, print out every character.
- If the string's length is odd, print out every other character.

```
var string = "turtle"

if string.count % 2 == 0 {
for n in string {
print(n)
}
}else{
for (index, character) in string.enumerated() {
if index % 2 == 1 {
print(character)
}
}
}

```
string.enumerated returns a sequence of pairs (n,x) where n represents a consecutive integer starting at zero and x represents the element/character that corresponds to that index's integer. As an example:
```
for (n, x) in "Turtle".enumerated() {
print("\(n): '\(x)'")
}
// Prints "0: 'T'"
// Prints "1: 'u'"
// Prints "2: 'r'"
// Prints "3: 't'"
// Prints "4: 'l'"
// Prints "5: 'e'"
```
The code checks if the string is even by evaulating its character count and seeing if, when divided by 2, has a remainder of 0. If it does, the characters of the string are printed using a for loop that goes one by one through the characters in the word and lists them. If not, a for loop is run using string.enumerated and if the value is an odd number, defined by modulo two equals to one (in this case, 1, 3, 5), those characters corresponding to the indexes are printed.
***
## Question 7

Initialize a String with a character. Show that it is a Character, and not another String, that you're using to initialize it.

```
var chars = [Character]("hi")
var charString = String(chars)

print(charString)

```

***
## Question 8

Build five pairs of **canonically equivalent** strings, the first of each being a pre-composed character and the second being one that uses combinable unicode scalars. Show that they are equivalent.

```
var combinableUnicode1 = "\u{0061}\u{0301}"
var precomposed1 = "á"
print (precomposed1 == combinableUnicode1)
//true

var combinableUnicode2 = "\u{006e}\u{0303}"
var precomposed2 = "ñ"
print (precomposed2 == combinableUnicode2)
//true


var combinableUnicode3 = "\u{006f}\u{0308}"
var precomposed3 = "ö"
print (precomposed3 == combinableUnicode3)
//true

var combinableUnicode4 = "\u{0063}\u{0327}"
var precomposed4 = "ç"
print (combinableUnicode4 == precomposed4)
//true

var combinableUnicode5 = "\u{0065}\u{0302}"
var precomposed5 = "ê"
print (combinableUnicode5 == precomposed5)
//true
```

***
## Question 9

**Using only Unicode**, print out `"HELLO WORLD!"`
```
var helloWorld = "\u{0048}\u{0045}\u{004C}\u{004C}\u{004f}\u{0020}\u{0057}\u{004f}\u{0052}\u{004c}\u{0044}\u{0021}"

print(helloWorld)
```
***
## Question 10

**Using only Unicode**, print out your name.

```
var unicodeCombinedName = "\u{0041}\u{006e}\u{0074}\u{0068}\u{006f}\u{006e}\u{0079}"
var unicodePrecomposedName = "Anthony"

print(unicodeCombinedName == unicodePrecomposedName)
```

***
## Question 11

**Using only Unicode**, print out `"HELLO WORLD!"` in another language.
```
var spanishGreeting = "\u{0048}\u{006f}\u{006C}\u{0061}\u{0020}\u{004D}\u{0075}\u{006E}\u{0064}\u{006f}\u{0021}"

print(spanishGreeting)

```


***
## Question 12

Print the below flower box using the following information.

- The unicode number for ⚘ is U-2698
- The top and bottom of the box are represented by dashes and the rows are |
- Use the terminator argument in your print statements to print on the same line.
- Hint: It may be useful to try printing out a box of just one character to start then work your way from there.

```swift
Flower Box:
- - - - - - - - - - -
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
- - - - - - - - - - -
```
```
let s = String(repeating: "\u{002d}\u{20}", count: 11)

print(s)

for _ in 1...7 {
for _ in 1...5 {
print("\u{007c}", "\u{2698}", terminator:" ")
}
print("\u{007c}")
}
print(s)



```
***
## Question 13

Write a program that sets up a chess board using Unicode.

```swift
Chess Board:
♖ ♘ ♗ ♕ ♔ ♗ ♘ ♖
♙ ♙ ♙ ♙ ♙ ♙ ♙ ♙




♟ ♟ ♟ ♟ ♟ ♟ ♟ ♟
♜ ♞ ♝ ♛ ♚ ♝ ♞ ♜
```
```swift
var firstThreeWhite = "\u{265c}\u{20}\u{265e}\u{20}\u{2657}\u{20}"
let whitePawns = String(repeating: "\u{2659}\u{20}", count: 8)
print(firstThreeWhite + "\u{2655}\u{20}\u{265A}" + String(firstThreeWhite.reversed()))
print(whitePawns)
print("")
print("")
print("")
print("")
var firstThreeBlack = "\u{2656}\u{20}\u{2658}\u{20}\u{2657}\u{20}"
let blackPawns = String(repeating: "\u{265f}\u{20}", count: 8)
print(blackPawns)
print(firstThreeBlack + "\u{265b}\u{20}\u{265a}" + String(firstThreeBlack.reversed()))


```
***
## Question 14

You are given a string stored in the variable `aString`. Create new string named `replacedString` that contains the characters of the original string with all the occurrences of the character `"e"` replaced by `"\*"`.

```swift
var aString = "Replace the letter e with *"
```

Example:

Input:
`var aString = "Replace the letter e with *"`

Expected values:
`replacedString = "R*plac* th* l*tt*r * with *"`
```swift
var replaced = ""

for b in aString {
if b == "e" {
replaced.append("*")
}else{
replaced.append(b)
}
}
print(replaced)
```
An empty string is created and given the name "replaced". A for loop is then run so that we can comb through each of the characters. If one of the characters is equal to "e", then the empty string is appended with the asterisk. The else statement encompasses all other letters that aren't e and simply appends them to the empty string as they are. The final string, after having been appended to, is then printed.
***
## Question 15

You are given a string stored in variable `aString`. Create a new string called `reverse` that contains the original string in reverse order. Print the reversed string.

```swift
var aString = "this string has 29 characters"
var reverse = String(aString.reversed())
```
***
## Question 16

You are given a string stored in variable `aString`. Print `true` if `aString` is a palindrome, and `false` otherwise. A **palindrome** is a string which reads the same backward or forward.

```swift
let aString = "anutforajaroftuna"

var reverse = String(aString.reversed())

if aString == reverse {
print("True")
}else {
print("False")
}

```
***
## Question 17

You are given a string stored in variable `problem`. Write code so that you print each word of the string on a new line.

```swift
-
var problem = "split this string into words and print them on separate lines"

let stringOfWords = problem.components(separatedBy: " ")

for word in stringOfWords {
print(word)
}
```
***
## Question 18

You are given a string stored in variable `problem`. Write code that prints the longest word in the string.

```swift
var problem = "find the longest word in the problem description"

var stringOfWords = problem.components(separatedBy: " ")
var longestWord = ""
for word in stringOfWords {
if word.count > longestWord.count {
longestWord = word
}}
print("The longest word is: \(longestWord)")
```
***
## Question 19

Given a string in English, create a tuple containing the number of vowels and consonants.

```swift
let vowels = "aeiou"
let consonants = "bcdfghjklmnpqrstvwxyz"
let input = "Count how many vowels I have!"
```
```
var vowelCounter = 0
var consonantsCounter = 0

for i in input {
if (vowels.contains("\(i)")) || (vowels.uppercased().contains("\(i)"))  {
vowelCounter += 1
}else {
consonantsCounter += 1
}}
print("Vowels: \(vowelCounter)",",", "Consonants: \(consonantsCounter)")

```

***
## Question 20

Given a string of words separated by a `" "`. Write code that prints out the length of the last word.

If there is no last word print out `"No last word"`.

Example:
Input: `"How are you doing this Monday?"`

Output: `7`

```
let problem = "How are you doing this Monday?"
let stringOfWords = problem.components(separatedBy: " ")
let lastIndex = stringOfWords.endIndex
let indexBeforeEnd = stringOfWords.index(before: lastIndex)
print(stringOfWords[indexBeforeEnd].count)
```
This works because the stringOfWords variable breaks up the problem string into its components. "How are you doing this Monday?" then becomes an array containing the words ["How", "are", "you", doing", "this", "Monday?"]. This step is essential for being able to manipulate and keep track of the elements within the string.
The next line, lastIndex, is created so that we can get the final index of the array. However, because of how computer store the data, this is not equivalent to the last element in the array. The final index will be one value lesser than total # of array elements. Therefore, in order to get the data of the actual last word, another variable is created called indexBeforeEnd which uses the index of the lastIndex and looks at the index of the element right before it. This will be the final word. It then has its character length checked.
***

