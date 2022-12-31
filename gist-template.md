# **Regex Tutorial**

Here we will discuss the computer science behind using regular expressions to extract specific information from text.

## **Summary**

Regular expressions, often called regex for short, are extremely useful. They use specific sequences of ASCII or unicode characters to extract specific information from any text. Once you've learned the syntax, this tool can be used in most programming languages (JavaScript, Java, C#, C++, Python, and many more). In this tutorial, we will discuss how to use regex to match any email within text using the following expression: ```/^[a-zA-Z0-9.!#$%&’*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/```

>Here is a breakdown of this expression:

* ```[a-zA-Z0-9.!#$%&’*+/=?^_`{|}~-]``` looks for any combination of letters (a-z, no case sensitivities), with any combination of numbers (0-9), and any combination of these specified special characters (```! # $ % & ' * + / = ? ^ _ ` { | } ~ -```)
    * (`example_123`@email.com)
* `+@` matches "at least one" `@` symbol
    * (example_123`@`email.com)
* `[a-zA-Z0-9-]` then looks for another combination of letters and numbers (a-z, no case sensitivities, and 0-9), but no special characters this time
    * (example_123@`email`.com)
* `+(` looks for at lease one of the following group
* `?:\.` matches ONLY one `.`
    * (example_123@email`.`com)
* `[a-zA-Z0-9-]` follows the `.` resulting in another combination of letters and numbers (a-z, no case sensitivities, and 0-9)
    * (example_123@email.`com`)

>Below you will find additional details on the different syntax rules options for regular expressions.

## **Table of Contents**

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## **Regex Components**

### **Anchors**
>`^`

* indicates the beginning of a string.
* For example, `^The` will match all sentences that begin with the word `The`.

>`$`

* indicates the end of a string.
* For example, `end$` will match all sentences that end with the word `end`.
---

### **Quantifiers**
>`+`

* 1 or more times
* For example, `abc+` would result in `ab` followed by at least 1 `c`.

>`{x}`

* exactly x times
* For example, `abc{5}` would result in `ab` followed by 5 copies of `c`.

>`{x,y}`

* x to y times, `{3,5}` will match either 3 to 5 characters, but no more and no less.
* For example, `abc{3,5}` would result in `ab` followed by 3 to 5 copies of `c`.

>`{x,}`

* x or more times, or "at least" x times
* For example, `abc{2,}` would result in `ab` followed by 2 or more `c`'s.

>`*`

* 0 or more times, or any times. `*` is often referred to as the `wild card` because it encompasses all possibilities.
* For example, `ab(cd)` could match any sequence of `ab` followed by 0 or more copies of `cd`.

>`?`

* 0 or 1 times
* For example, `abc?` would result in one in `ab` followed by 0 or 1 `c`.   
---

### **Grouping Constructs**
>`(x)`

* Capturing Group: matches the x variable and remembers the match.
* For example, `/(blue)/` matches and remembers `blue` in blueberry.
---

### **Bracket Expressions**
>`[abc]`

* has either an `a`, `b`, or `c`.
* For example, `[a-zA-Z0-9]` will match any combination of `a` through `z` (no case sensitivities) and `0` through `9`.

>`[a-b-]`

* you can place a hyphen (`-`) as the first or last character in a range in order to add `-` to your class
* For example, `[a-zA-Z0-9-]` will match any combination of `a` through `z` (no case sensitivities), `0` through `9`, *AND* hyphens.
---

### **Character Classes**
>`.`

* matches any character

>`\d`

* matches a single digit 0 through 9

>`\D`

* matches a single non-numerical number

>`\w`

* matches a single word character (alphanumeric)

>`\s`

* matches a whitespace character, including tabs and line breaks
---

### **The OR Operator**
>`|`

* either or
* For example, `a(b|c)` matches `a` followed by either `b` or `c`.
---

### **Flags**
>`g` (global)

* does not return after the first match

>`m` (multi-line)

* when `^` and `$` are in used, it will match the start and end of a line instead of the entire string

>`i` (insensitive)

* makes the expression case-insensitive
---

### **Character Escapes**
>`\`

* to match a special character, you must us an escape sequence prefix
* For example, `\.` matches `.` (useful when searching for `.com` or `.edu`, etc)

>`\n`

* new line

>`\t`

* tab

>`\r`

* carriage return
---

## **Author**

### Shel Cloyd
[Github: shelcloyd](https://github.com/shelcloyd)
