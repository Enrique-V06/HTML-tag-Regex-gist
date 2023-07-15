# HTML tag Regex Tutorial

This tutorial aims to explain the uses, implementation and every section of the Regular Expression (REGEX) for matching and HTML tag.

## Summary

A REGEX is a sequence of characters that defines a search pattern mainly for string matching, similar to the FIND and REPLACE operations.

An example of this in a real world application would be whenever you search somenthing online the search engine of the webpage you use would search it´s own database for any article, link, video, movie, etc. that matches your input in the search box and would return any findings that match your searched "keywords".

For this tutorial in particular we will be looking into the HTML tag REGEX code:

`/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`

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

Anchors help us define where our string begins and where it ends, thus signaling the elements of the string to search, for the case of the regex at hand the symbol `^` known as caret helps us identify the begining of the string, where we will have the algorithm match the position rather than the character.

The same applies to the dollar sign `$` which symbolizes the end of our string. 

So returning to our HTML tag regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` , this results in us having the open and closing tags at the start and at the end of the string.

### Quantifiers

Quantifiers help us specify how many instances of a charater, group or character class must be present in the input for us to receive a match, quantifiers have the capacity of being *greedy*, meaning the quantifier will try to match an elemtn as many times as possible, or *lazy*, meaning the quantifier will try to match the element as few times as possible. Below is a list of some quantifiers: 

* `*`   this quantifier maintains the search must match 0 or more times.

* `+`   this quantifier maintains that the search must match one or more of the characters set in the algorithm, characters placed to the left of the symbol are expected to match at least once, examples:
    * N+ : in this example the quantifier applies for a search for `N`
    * day+ : in this example the quantifier applies only to the letter `y` in the word and not to the entire word.

* `?`   this quantifier indicates that the search must match 0 or 1 times, however it is considered optional, when used after another quantifier it makes the other quantifier lazy

* `{n}`     this quantifier indicates that the algorithm is set to match exactly n times

* `{n,}`    this quantifiers indicate that the algorith must match at least n times

* `{n,m}`   this quantifier indicate that the algorithm must match between *n* and *m* times

### Grouping Constructs

Grouping constructs represent the subexpressions of a regular expression and capture the substrings of an input.

* `(abc){3}` if we desired to group a selective pattern, we can introduce them between parentheses and include a numeric counter besides it. This example would search for the match of `abcabcabc` because the first group was denoted as `(abc)` and we included the need for it to repeat three times as `{3}`.

* For non-capturing parentheses groups, the regex would look similarly `(?:abc){3}` or `(?:ABC`.

### Bracket Expressions

A regular expression surrounded by square brackets is considered a bracket expression meant to match a single character or element. 
An example of a bracket expression would be `[a-d]`

### Character Classes

A character class defines a set of characters, any one of which can occur in an input string for a match to succeed. 
Some examples are:

* `\w` This will match any word character such as `[a-z0-9_]`, but will only match lowercase character without accent marks.

* `\W` This matches any character that is not a word character such as `[A-Za-z0-9_]`

* `\d` sets the search to match any digitized character such as `0-9`

* `\D` sets the search for non-digitized characters

* `\p` sets the match for a character in the specific unicode category

* `[A-Z]` utilizing the hyphen between the two characters creates a range for the search criteria

* `'` is a wildcard and will accept any input

* `\s` This will match any whitespace character

* `\S` This matches any non-white-space characters

### The OR Operator

* `|`
    * This operator acts like a Boolean OR. It causes a match of the expression before or after the `|` and can be utilized inside a group or on a whole expression. In terms of order, it causes the search-string to look for a match of either what precedes or follows after the `|`. 
    Example:
    `a|b` the algorith will search for either `a` or `b`

### Flags

Regular expressions may have flags that affect the search.

There are only 6 of them in JavaScript:

* `i`   With this flag the search is case-insensitive: no difference between A and a

* `g`   this flag the search looks for all matches, without it – only the first match is returned

* `m`   Multiline mode 

* `s`   Enables “dotall” mode, that allows a dot . to match newline character \n 

* `u`   Enables full Unicode support. The flag enables correct processing of surrogate pairs

* `y`   “Sticky” mode: searching at the exact position in the text 

### Character Escapes

Regex uses the backslash symbol (`\`) for two purposes:

* for metacharacters such as `\d` (digit), `\D` (non-digit), `\s` (space), `\S` (non-space), `\w` (word), `\W` (non-word).
* to escape special regex characters, e.g., `\.` for ., `\+` for +, `\*` for *, `\?` for ?

You also need to write `\\` for `\` in regex to avoid ambiguity.

Regex also recognizes `\n` for newline, `\t` for tab, etc.


## Author

This was done by Enrique Vazquez, check out my [Github](https://github.com/Enrique-V06)
