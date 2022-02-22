# RegexForHEX

## Summary
This tutorial explains how the regular expression for matching HEX values operates. Within the description below, each component of the expression will be broken down to define what each character's function is and how this expression matches HEX values step by step with its anchors, quantifiers, OR Operator, grouping and capturing, and bracket expressions.

Regex for matching HEX values:
`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)

## Regex Components

### Anchors

Anchor: ^
Code Snippet: `/^#`

Description: Anchors themselves do not match a regular expression; anchors assert a rule of the string based on the following characters or matching pattern next to the anchor itself. 

Example: `^Test` indicates that the string must start with `Test`

The ^ anchor indicates that the beginning of a string has to match the character #, which is how the expression will distinguish a hexadecimal number from a decimal number. Due to the next anchor, we will find that this octothorp (#) is optional.


Anchor: $

Code Snippet: `$/`

Description: This character matches to the end of the string. Like the ^ anchor, the $ anchor also checks if a string matches a pattern, but this anchor confirms the pattern matches the end of the string rather than the beginning.

Example: `test$` indicates that the string must end with `test`.

In the case of matching HEX values, the string must match the 3 or 6 character pattern of a HEX value prior to the $ anchor. This character pattern will be elaborated upon in the section on Quantifiers. 


### Quantifiers

Quantifier: ?

Code Snippet: `/^#?`

Description: The ? character implies a boolean value: true or false, 0 or 1. Usually this makes the symbol preceding the ? optional.

Example: This symbol could be used to distinguish between spelling differences in British and American English (such as colour and color). The regex would check for colou?r, with the u being optional since it precedes the ? quantifier.

For matching HEX values in this regex, the quantifier ? tells us that the preceding # is optional, therefore the octothorp may or may not appear in the beginning of the string.


Quantifier: {}

Code Snippet: `[a-f0-9]{6}`
Code Snippet: `[a-f0-9]{3}`

Description: This quantifier specifies how many times the preceding pattern matches. Typically, the quantifiers are greedy, which means the regex will match as many occurances of the indicated pattern as possible. If a ? character is appended, then the quantifier becomes lazy, meaning that the regex would match as few patterns as possible. Within this regex, the quantifier is greedy.

Example: `7{3}` indicates that 7 must be repeated 3 times. The matching string must be 777.

In this regex, {6} requires that there be 6 instances of the string in the bracket expression before it, meaning that this quantifier allows exactly 6 characters in a string composed of any characters a-f and/or integers between 0-9. The {3} indicates that there are 3 instances of the string in that preceding bracket expression, implying that this quantifier will allow exactly 3 characters in the string that contain characters between a-f and/or integers between 0-9.


### Grouping Constructs

Grouping and Capturing: ()

Code Snippet `([a-f0-9]{6}|[a-f0-9]{3})`

Description: The () groups the regular expression contained between them. This grouping will treat multiple characters as a single unit. This is useful for when a developer may desire to extract information within other programming languages into an array. Values can be accessed using an index on the results of that match.

Example: (test){3} will match testtesttest. The unit of characters 'test' would have to repeat 3 times due to the quantifier. 

Within this regular expression, the grouped expression is a bracket expression, which is further explained below. The end string anchor $ is applied to this grouping in this regex.


### Bracket Expressions

Bracket Expression: []

Code Snippet: `[a-f0-9]`

Description: Bracket expressions look to match a specific pattern of characters defined inside the brackets, such as symbols, alphabetic, numeric, or special characters. Typically a hyphen is used when describing a range of characters, such as `[a-z]`.

Example: [a-c 1-3] indicates that the string must include at least 1 character that is between a-c (a, b, or c) or 1-3 (1, 2, or 3).

Within this regex, the bracket expression [] requires the matching string to have any lowercase character between a-f or any integer between 0-9.


### Character Classes

Code Snippet: `a-f0-9`

Description: Character classes look to match only the defined character set. Hyphens may be used to define a range of characters so that many characters may be searched for. More than one range may be used as well, as seen within this snippet. 

Example: The character class `0-9` matches a single digit between 0 and 9. The digit could be 0, 1, 2, 3, 4, 5, 6, 7, 8, 9.

In this regex, the character class consists of lower case alphabetic characters a-f (abcdef) and integers between 0-9 (0123456789).

### The OR Operator

OR Operator: |

Code Snippet: `[a-f0-9]{6}|[a-f0-9]{3}`

Description: The | indicator is a boolean that matches the expression either before or after it.

Example: 2|4 indicates that either 2 or 4 or both integers are allowed within the string, therefore 222, 444, 242, 424, 224, 442, 422, or 244 are accepted as matching patterns.

In this regex, a matching pattern may contain a string of 6 characters that are lowercase a-f and/or integers 0-9 OR a string of 3 characters that are lowercase a-f and/or integers 0-9. For a string to match, it must have either 6 or 3 characters with the specific parameters set within the bracket expressions. Anything that does not have 6 or 3 characters following these parameters will not match.


## Author

Kara Heeb is a full stack developer interested in building applications focused on user experience and mobile friendly design. When not coding, Kara enjoys musical theatre, plant based cooking, and hanging out with her cat, Oliver.

GitHub profile: https://github.com/kheeb
