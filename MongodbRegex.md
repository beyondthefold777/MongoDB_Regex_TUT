
# MongoDB Regex Tutorial

Regular expressions (regex) are powerful tools for pattern matching and searching within strings. In MongoDB, regex can be used to query documents based on string patterns. This tutorial will guide you through the various components of regex and how to use them in MongoDB queries.

## Summary

This tutorial will cover the basics of regular expressions and how to use them in MongoDB queries. We will explore anchors, quantifiers, grouping constructs, bracket expressions, character classes, the OR operator, flags, and character escapes. Here's a sample regex to get started:

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Anchors

Anchors are used to match a position within the string. The most common anchors are ^ (start of the string) and $ (end of the string).


```javascript
db.collection.find({ field: { $regex: /^start/ } });
db.collection.find({ field: { $regex: /end$/ } });
```
 
 ## Quantifiers
Quantifiers specify how many instances of the previous element are required. Common quantifiers include `*` (zero or more), `+` (one or more), and `?` (zero or one).
 ```
db.collection.find({ field: { $regex: /colou?r/ } });
```

### Grouping Constructs

Grouping constructs are used to apply quantifiers to multiple characters or to capture subpatterns for back-references. They are created using parentheses `()`.

`db.collection.find({  field:  {  $regex:  /(abc)+/  }  });`

### Bracket Expressions

Bracket expressions, or character sets, define a set of characters that can match a single character in the input string. They are enclosed in square brackets `[]`.

`db.collection.find({  field:  {  $regex:  /[aeiou]/  }  });`

### Character Classes

Character classes match a specific type of character. For example, `\d` matches any digit, and `\w` matches any word character (alphanumeric and underscore).

`db.collection.find({  field:  {  $regex:  /\d+/  }  });`
