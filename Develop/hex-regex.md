# RegEx Explanation - Matching Hex Codes

A regex, or regular expression, is a sequence of characters that enables you to validate that your provided text matches your entered requirements. In this tutorial, we will break down how you can use regex to match Hex Values.

## Summary

Hex codes, formally known as hexadecimal codes, are codes which identify colours which can be used across web and graphic design. They are written in a base-16 format, which requires 16 valid characters - composed of the characters between 0 and 9, and A - F.

To understand how to match hex codes via regex, we will break down this example expression: /^#?([a-f0-9]{6}|[a-f0-9]{3})$/.

We will describe its anchors, bracket expressions, quantifiers, OR operator, character classes, grouping and capturing and its greedy/lazy matching. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)


## Regex Components

### Anchors

Anchors refer to the beginning or end of the string which we are looking to match with our regex.

 In our demo regex, ^ is used to indicate the start of a string, while $ is used to indicate that the end of a string. Therefore, as our demo regex reads '^#', our regex is checking that the text being validated begins with a '#'. Inversely, the end of our regex specifies '([a-f0-9]{6}|[a-f0-9]{3})$', which checks whether the text we are validating ends with either the [a-f0-9] or the [a-f0-9] specification.

### Bracket Expressions

Bracket expressions define character sets which must be matched by the text being checked. This is also known as a positive character group, as it checks that the defined characters is present in the text being matched - as opposed to a negative character group, which checks that the character group is not present in the text being matched.

Additionally, hyphens ('-') can be used within bracket expressions to express an allowed range (e.g 1-3).

In regard to our demo regex, the bracket expressions are [a-f0-9] and, again, [a-f0-9]. Using the aforementioned hyphen, these bracket expressions set the match pattern for characters - allowing them to be either letters between a and f, and/or numbers between 0 and 9. 

### Quantifiers

There are three quantifiers in our demo regex: ? + {6} + {3}. 

Quantifiers define the limits of the text/string being validated, either within the scope of the entire string or within a part of it.

The ? in our demo regex dictates that the text/string must match the pattern 1, or 0 times, and no more. 

{6} + {3} are instances of the {n} quantifier. {n} checks that the text matches the pattern n amount of times exactly. As such, the first instance in our demo checks that the text matches the pattern exactly 6 times, whilst the latter checks that the text matches the pattern exactly 3 times. In practice, this means that [a-f0-9]{6} checks for characters, which follow the pattern of being either a letter of a-f, or a number between 0-9, six times. In other words, it checks for a 6 character string, composed of letters from a-f and/or numbers between 0-9. Similarly, [a-f0-9]{3} checks for a string of three characters following the aforementioned pattern.

The ?, in our demo, occurs before the group which includes the {n} quantifiers - /^#?([a-f0-9]{6}|[a-f0-9]{3})$/. This indicates that the match pattern to find a 6 or 3 character string should only be matched once.

### OR Operator

OR operators specify that the expression should check for two or more options, allowing the text to pass the match test if it satisfies one of the provided options.

The OR operator is written as '|', and can be seen in our demo regex between the two [a-f0-9]{6}|[a-f0-9]{3} bracket expressions. 

As such, with our demo regex, we are specifying that either a 6 character string which matches the pattern or a 3 character string which matches the pattern will satisfy the match check.

### Character Classes

A character class can be used in a regex to specify a certain class of characters which can appear in a string to satisfy a match. For example, using '\s' will check for any whites-space characters (e.g spaces or tab breaks). 

Bracket expressions are also considered character classes, as they specify the set of characters which are set as a standard for matching: e.g. [a-f0-9] is a positive character class, as it searches for letters between a and f, and numbers between 0-9.

### Grouping and Capturing

Grouping can be used to segment requirements needing to be specified in a regex. They are defined by parentheses (()).

The regex will look to capture what is inside the group - which, in simple terms, means the regex will capture the character sequence inside the group for later reuse. However, a regex can be made non-capturing, by placing '?:' before the character set inside the grouping parentheses. 

Looking back at our demo regex, the grouping occurs within the following parentheses ([a-f0-9]{6}|[a-f0-9]{3}). This is a capturing grouping, which defines a single requirement - that a 6 or 3 character long string, composed of letters between a-f and/or letters 0-9, is necessary for a match.

### Greedy and Lazy Match



## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
