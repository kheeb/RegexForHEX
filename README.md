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
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

Anchor: ^
Code Snipet: `/^#`

Description:

Anchors themselves do not match a regular expression; anchors assert a rule of the string based on the following characters or matching pattern next to the anchor itself. 

Example: `^Test` indicates that the string must start with `Test`

The ^ anchor indicates that the beginning of a string has to match the character #, which is how the expression will distinguish a hexadecimal number from a decimal number. Due to the next anchor, we will find that this octothorp (#) is optional.

Anchor: $

Code Snippet: `$/`

Description: This character matches to the end of the string. Like the ^ anchor, the $ anchor also checks if a string matches a pattern, but this anchor confirms the pattern matches the end of the string rather than the beginning.

Example: `test$` indicates that the string must end with `test`.

In the case of matching HEX values, the string must match the 3 or 6 character pattern of a HEX value prior to the $ anchor. This character pattern will be elaborated upon in the section on Quantifiers. 

### Quantifiers

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

Kara Heeb is a full stack developer interested in building applications focused on user experience and mobile friendly design. When not coding, Kara enjoys musical theatre, plant based cooking, and hanging out with her cat, Oliver.

GitHub profile: https://github.com/kheeb
