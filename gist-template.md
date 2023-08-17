# Regular Expression Tutorial

A regular expression, or regex for short, provides a way to search or match text defined by a specific pattern. A regex pattern is powerful in that it provides more flexible and dynamic searchability of text as opposed to being limited to exact matching. This tutorial will break down an example of a regex pattern and provide understanding of each component. 


## Summary

The regex pattern to be examined in this tutorial will be one that matches a hex value. The regex pattern is as follows: 

```/^#?([a-f0-9]{6}|[a-f0-9]{3})$/```

We will breakdown each component in detail later, but at a high level, the regex pattern above will match any text that meets the following criteria:

• The string starts with an optional '#' character.

• The rest of the string consists of a total of 6 or 3 characters that is any combination of the characters 'a-f' (lowercase) and/or '0-9'.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)


## Regex Components

The regex example above is considered a literal so it is wrapped between the slash '/' character. We will now takr a look at the components of the regex pattern.

### Anchors

The characters '^' and '$' are called **anchors**.

The '^' character signifies a string that starts with the text that comes after it, while the '$' character signifies a string that ends with the text that precedes it. In our example above, the pattern will match any string that starts with an optional '#' character (we will discuss why it is optional later) and ends with a 6 or 3 character-long text that includes character 'a-f' and/or '0-9'.

### Quantifiers

Quantifiers in a regex pattern are a way to limit or specify the number of matches in a pattern. In our example, we have three instances of quantifiers: ?, {6}, and {3}. They mean the following:

• ? - This will match a pattern zero or one time (think of it as a pattern that may or may not occur, optional)

• { n } - This will match a pattern exactly n number of times.

There are more examples of quantifiers i.e. { n, }, { n, x }, +, etc., but our example only covers the two noted above. Using what we've just learned, we now understand why the '#' symbol is optional. The ? character behind it means it will match any pattern where the '#' occurs zero or one time, so it is completely optional. The {6} and {3} quantifiers will match a pattern exactly 6 or 3 characters long that only consists of characters a-f and/or 0-9.

### Grouping Constructs

Grouping constructs in a regex pattern allow us to break a string into sections where certain groups of text can be matched and are defined by parentheses '()'. This was needed in our example because it allowed us to separate the OR ('|') operation (will discuss in detail later) from the rest of the regex pattern. For our example, the grouping construct was used to set the conditional matching of either the 6-length character or the 3-length character after the matching of the optional '#' character. If not for the grouping, the entire regex pattern would've been considered for conditional matching and the '#" character would've been included for the condition. Grouping constructs (or 'capture groups') can be referenced by a numbered backreference. (i.e. '\1' for the first capture group)

### Bracket Expressions

Bracket expressions are denoted by square brackets '[]' and can represent any character(s) or range of characters that we want to include. Our example uses the bracket expression '[a-f0-9]', which means that the pattern will match any character between a-f (lowercase) and any number between 0-9.

### Character Classes

Character classes define a set of characters that can be matched and bracket expressions are an example of character classes. Other examples include (but are not limited to):

• '.' - the dot character is a wildcard character that will match any character except the newline character '\n'.

• \d - this character will match any number and is equivalent to the bracket expression [0-9].

• \w - this character matches any alphanumeric character and the underscore character. This is equivalent to the bracket expression [A-Za-z0-9].

### The OR Operator

The OR operator '|' is used when we want our expression to have multiple options to match between. In our example, we used the OR operator to match the character class [a-f0-9] with either 3 total characters or 6 total characters. Either case will be matched. The OR operator is not limited to choosing between two cases. Multiple cases can be included and the options separated between the OR symbol '|' are acceptable for matching.

## Author

[Joshua Williams](https://github.com/codehashira28)
