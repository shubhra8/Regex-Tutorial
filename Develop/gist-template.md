# REGEX Tutorial

It is mainly used for searching and manipulating text strings. In simple words, you can easily search the pattern and replace them with the matching pattern with the help of regular expression.The following REGEX is an example that looks for the string to match the general makeup of an email address.

## Summary

This regex tutorial will explore the regex of matching an email address.For this regex, each component has a specific responsibility to make sure or verify that the user enters an email address in the correct format which in this case begins with characters followed by @ symbol and, lastly, the domain.
/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

There are two characters that can be considered anchors. These are the ^ and $ characters. The ^ anchor marks the beginning of the string while the $ marks the end of the string. In the matching email regex, the string is sandwiched between a ^ and $.

### Quantifiers

Quantifiers indicate that the preceding token must be matched a certain number of times. A quantifire can be greedy or lazy that is explained below
abc* matches a string that has ab followed by zero or more
abc+ matches a string that has ab followed by one or more
abc? matches a string that has ab followed by zero or one
abc{2} matches a string that has ab followed by 2
abc{2,} matches a string that has ab followed by 2 or more
abc{2,5} matches a string that has ab followed by 2 up to 5
a(bc)* matches a string that has a followed by zero or more copies of the sequence
a(bc){2,5} matches a string that has a followed by 2 up to 5 copies of the sequence
Each of these quantifiers can be made lazy by adding the ? symbol after it, meaning it will match as few occurrences as possible.
There, we have the quantifier {3,16}. This means that we want to find the preceding string pattern a minimum of 3 times and a maximum of 16 times. Because our bracket expression ([a-z0-9_-]) will match any string that includes any combination of lowercase letters between a and z, any number between 0 and 9, and the special characters of an underscore or a hyphen, this quantifier means that this string has to be between 2 and 6 characters.

### Grouping Constructs

Grouping constructs use parentheses (()) to group different parts of the string together to check and make sure they are fulfilling the requirements set for them. You can see the way the matching email regex is broken into three grouping constructs below.
([a-z0-9_\.-]+)

([\da-z\.-]+)

([a-z\.]{2,6})

### Bracket Expressions

Anything inside of the set of square brackets ([]) will represent the chararcters that are being matched. In the matching email regex, there are three different bracket expressions as you can see below.

[a-z0-9_\.-]

[\da-z\.-]

[a-z\.]

[abc] matches a string that
has either an a or a b or a c -> is the same as a|b|c
[a-c] same as previous
[a-fA-F0-9] a string that represents a single hexadecimal digit, case insensitively
[0-9]% a string that has a character from 0 to 9 before a % sign
[^a-za-z] a string that has not a letter from a to z or from A to Z. In this case the ^ is used as negation of the expression

### Character Classes

Character classes match a character from a specific set. There are a number of predefined character classes and you can also define your own sets.

[ABC] Characters inside brakets will match any character in the set.
[^abc] Adding a caret will match any character that is not in the set.
[A-Z] Add a dash between two characters will select a Range.
\d matches a single character that is a digit
\w matches a word character (alphanumeric character plus underscore)
\s matches a whitespace character (includes tabs and line breaks)
\p matches a character in the specified unicode category
. matches any character

Use the . operator carefully since often class or negated character class (which we’ll cover next) are faster and more precise.

\d, \w and \s also present their negations with \D, \W and \S respectively.

For example, \D will perform the inverse match with respect to that obtained with \d.

\D matches a single non-digit character
In order to be taken literally, you must escape the characters ^.[$()|\*+?{\with a backslash \ as they have special meaning.

\$\d matches a string that has a $ before one digit -> Try it!
Notice that you can match also non-printable characters like tabs \t, new-lines \n, carriage returns \r.

### The OR Operator

| Acts like a boolean OR. Matches the expression before or after the |. It can operate within a group, or on a whole expression. The patterns will be tested in order. Just as in java will match either set of characters. It will look for this OR that.

### Flags

A regex usually comes within this form /abc/, where the search pattern is delimited by two slash characters /. At the end we can specify a flag with these values (we can also combine them each other):

g (global) does not return after the first match, restarting the subsequent searches from the end of the previous match
m (multi-line) when enabled ^ and $ will match the start and end of a line, instead of the whole string
i (insensitive) makes the whole expression case-insensitive (for instance /aBc/i would match AbC)

## Author

Author name-Shubhra Salunke
Github Profile-https://github.com/shubhra8/
