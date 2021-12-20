# Email Regex

In this tutorial, I will be covering what a Regex (Regular Expression) is in programming, and include a specific example. Regex are a series of characters that are used to match character combinations in strings. In JavaScript, regex function as objects. They are commonly used as text processing and manipulation, and by forming search patterns with regex, we can make it easy and efficient to search for data.

## Summary

The regex covered in this tutorial allows for email validation. This email regex comprises of a group of characters that are typical of the standard email address. Email validation is an important part of the UX of a web application, and ensuring only valid information is inputted in web forms and sent to the server is vital. 

Matching an Email: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Character Escapes](#character-escapes)
- [Author](#author)

## Regex Components

### Anchors

We'll start this tutorial by highlighting the anchors of a regex. The anchors signify the beginning and end of the expression, also known as Start of Line and End of Line anchors. Without clear start and end points, we wouldn't be able to easily identify the beginning or end of the expression. In our email regex, the anchors are highlighted below:

`/^`([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})`$/`

As we can see, the anchors for this expressions are `/^` and `$/`.

### Quantifiers

Next up is quantifiers. Quantifiers establish how many instances of a character, group, or character class must be present to validate the string - they are used to determine how many characters are expected, and are signified by the `*,+,?,{}` characters in an expression. Quantifiers such as `*` and `+` are considered 'greedy' by default. This means that they will try to match as many characters in the string as possible. The `?` character found after a quantifier makes it 'non-greedy', as it will stop searching the string as soon as it finds a match. In our email regex, we have the `+`, and `{}` quantifiers. The `+` quantifier indicates that the expression can have as many of the preceding characters that are wrapped in [ ] as wanted, and the `{2,6}` quantifier signifies a range of between 2 and 6 characters in the preceding group of characters wrapped in [ ]. These are highlighted below:

/^([a-z0-9_\.-]`+`)@([\da-z\.-]`+`)\.([a-z\.]`{2,6}`)$/

### Grouping Constructs

Grouping constructs, also known as capturing groups, are denoted by parentheses `()`. These create a sub-expression by inserting an expression inside the parentheses. Quantifiers can even be applied to the sub-expression, and as such the quantifier will now apply to the whole sub-expression. Think of the maths expression `2(4a + 3)`, in which the 2x is applied to both values inside the parentheses. The same idea applies to grouping constructs. We have a number of sub-expression in our email regex:

/^`(`[a-z0-9_\.-]+`)`@`(`[\da-z\.-]+`)`\.`(`[a-z\.]{2,6}`)`$/

### Bracket Expressions

Bracket expressions in our regular expression indicate the beginning and end of a character class or quantifier statement. In our email regex example, the square brackets `[]` are used to define the bracket expressions.

/^(`[`a-z0-9_\.-`]`+)@(`[`\da-z\.-`]`+)\.(`[`a-z\.`]`{2,6})$/

### Character Classes

Character classes are nestled inside a bracket expression [ ]. They are components within our regex that tells us what types of characters to expect in our string. Any of the characters found inside the square brackets of the regex are valid. As highlighted below, `a-z0-9_\.-` means that any letter, any number, and the special characters `_.-` are valid; `\da-z\.-` represents that one or more digits, letters between a-z, periods, and hyphens can be used; the last domain `a-z\.` again means that any letter, and periods are valid.

/^([`a-z0-9_\.-`]+)@([`\da-z\.-`]+)\.([`a-z\.`]{2,6})$/

### The OR Operator

The OR operator is not found in our example email expression, but it is denoted by the symbol `|`. This operator to match characters or expressions on either side of the `|` but not both. For example, `1|4` will match EITHER 1 or 4 from the input string, but not both.

### Character Escapes

Finally, we end with characters escapes. These help to 'escape' a character that would usually have special meaning inside an expression. The backslash `\` defines this, and the special character is prepended by the backslash. In our email regex, we can see that the backslash has been used to escape the period `\.` to ensure that the period is read as a general character, and not a special character as it is used in normal coding. 

/^([a-z0-9_`\`.-]+)@([\da-z`\`.-]+)\.([a-z`\`.]{2,6})$/

## Author

Amelia Hooper

Amelia is a Biotechnology graduate currently working as a Laboratory Assistant. She is wanting to broaden her skillset by undertaking the Monash Coding Bootcamp to complete a certificate in full-stack development. 

GitHub: [ahooper00](https://github.com/ahooper00)