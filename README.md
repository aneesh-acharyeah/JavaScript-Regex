# JavaScript Regular Expression Cheat Sheet

Welcome to the JavaScript Regular Expression Cheat Sheet! This guide will help you understand and use regular expressions (regex) in JavaScript effectively. Whether you’re a beginner or experienced, this cheat sheet is designed to provide clear examples and explanations.

---

## Table of Contents

- [Introduction to Regex](#introduction-to-regex)
- [Regex Syntax](#regex-syntax)
- [Metacharacters](#metacharacters)
- [Character Classes](#character-classes)
- [Quantifiers](#quantifiers)
- [Anchors](#anchors)
- [Grouping and Capturing](#grouping-and-capturing)
- [Flags](#flags)
- [Examples](#examples)
- [Useful Links](#useful-links)

---

## Introduction to Regex

Regular Expressions (regex) are patterns used to match character combinations in strings. They are incredibly powerful for pattern matching and text manipulation.

### What is Regex in JavaScript?
In JavaScript, regular expressions are objects that describe a pattern of characters. They are used with string methods like `match()`, `replace()`, `test()`, and `split()`.

---

## Regex Syntax

### Basic Syntax

- **Literals**: Characters like `a`, `1`, or `#` that match themselves.
- **Metacharacters**: Special characters with specific meanings like `.`, `*`, `?`, etc.
  
---

## Metacharacters

Metacharacters are symbols that have special meanings when used in regular expressions.

| **Symbol** | **Meaning**                            | **Example**                              |
|------------|----------------------------------------|------------------------------------------|
| `.`        | Matches any character except newline   | `/a.b/` matches `acb`, `axb`, etc.       |
| `\`        | Escape special characters              | `/\./` matches a literal dot (`.`)       |
| `^`        | Matches the beginning of a string      | `/^abc/` matches `"abc"` at the start    |
| `$`        | Matches the end of a string            | `/abc$/` matches `"abc"` at the end      |
| `|`        | OR operator                            | `/a|b/` matches `a` or `b`               |

---

## Character Classes

Character classes define sets of characters that can be matched.

| **Class**   | **Description**                 | **Example**                                  |
|-------------|---------------------------------|----------------------------------------------|
| `\d`        | Matches any digit (0-9)         | `/\d/` matches `1`, `2`, `3`, etc.           |
| `\D`        | Matches any non-digit character | `/\D/` matches `a`, `b`, `A`, etc.           |
| `\w`        | Matches any word character      | `/\w/` matches `a`, `b`, `1`, `_`, etc.      |
| `\W`        | Matches any non-word character  | `/\W/` matches `!`, `@`, `#`, etc.           |
| `\s`        | Matches any whitespace character| `/\s/` matches space, tab, newline, etc.     |
| `\S`        | Matches any non-whitespace character | `/\S/` matches `a`, `1`, etc.          |

---

## Quantifiers

Quantifiers specify the number of times a character or group should appear.

| **Quantifier** | **Description**                | **Example**                           |
|----------------|--------------------------------|---------------------------------------|
| `*`            | Matches 0 or more of the preceding character | `/a*/` matches `a`, `aa`, `aaa`, etc.  |
| `+`            | Matches 1 or more of the preceding character | `/a+/` matches `a`, `aa`, etc.         |
| `?`            | Matches 0 or 1 of the preceding character | `/a?/` matches `a` or an empty string  |
| `{n}`          | Matches exactly n occurrences   | `/a{3}/` matches `aaa`                 |
| `{n,}`         | Matches n or more occurrences    | `/a{2,}/` matches `aa`, `aaa`, etc.    |
| `{n,m}`        | Matches between n and m occurrences | `/a{2,4}/` matches `aa`, `aaa`, `aaaa` |

---

## Anchors

Anchors are used to specify the position in the string where a match should occur.

| **Anchor** | **Description**                              | **Example**                              |
|------------|----------------------------------------------|------------------------------------------|
| `^`        | Matches the start of the string              | `/^hello/` matches `"hello"` at the start |
| `$`        | Matches the end of the string                | `/world$/` matches `"world"` at the end  |

---

## Grouping and Capturing

Parentheses `()` are used to group expressions and capture matched text.

| **Syntax**        | **Description**                         | **Example**                             |
|-------------------|-----------------------------------------|-----------------------------------------|
| `()`              | Capturing group                         | `/(abc)/` matches `"abc"` and captures it |
| `(?:)`            | Non-capturing group                     | `/(?:abc)/` matches `"abc"` but does not capture it |
| `\1`, `\2`, etc.  | Backreferences to captured groups       | `/(\d)\1/` matches repeated digits like `11`, `22`, etc. |

---

## Flags

Flags modify the behavior of the regular expression.

| **Flag** | **Description**                                | **Example**                                 |
|----------|------------------------------------------------|---------------------------------------------|
| `g`      | Global match (matches all occurrences)        | `/a/g` matches all occurrences of `a`       |
| `i`      | Case-insensitive match                        | `/a/i` matches `a`, `A`                    |
| `m`      | Multiline matching (affects `^` and `$`)      | `/^abc/m` matches `abc` at the start of each line |
| `s`      | Dot matches newline (`.` can match `\n`)      | `/a.b/s` matches `a\nb`                    |
| `u`      | Matches Unicode characters                    | `/\u{1F600}/u` matches 😀                   |

---

## Examples

1. **Match an Email Address**:

   ```javascript
   const regex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
   const email = "example@example.com";
   console.log(regex.test(email)); // true


2. **Match a Phone Number**:

   ```javascript
   const regex = /^\d{3}-\d{3}-\d{4}$/;
   const phone = "123-456-7890";
   console.log(regex.test(phone)); // true

3. **Extract Dates**:
   
   ```javascript
    const regex = /(\d{4})-(\d{2})-(\d{2})/;
    const date = "2024-11-23";
    const match = date.match(regex);
    console.log(match[0]); // 2024-11-23
    console.log(match[1]); // 2024


## Useful Links

Here are some useful resources to learn and master JavaScript regular expressions:

- [MDN Web Docs - Regular Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) 
  ![MDN](https://img.shields.io/badge/MDN-Regular_Expressions-blue)
  
- [Regex101 - Interactive Regex Tester](https://regex101.com/)
  ![Regex101](https://img.shields.io/badge/Regex101-Interactive_Tester-orange)
  
- [Regular Expressions Cheatsheet](https://www.rexegg.com/regex-quickstart.html)
  ![RexEgg](https://img.shields.io/badge/RexEgg-Quickstart-green)

- [Regexr - Online Regex Tool](https://regexr.com/)
  ![Regexr](https://img.shields.io/badge/Regexr-Online_Tool-red)
  
- [Regex Tutorial on W3Schools](https://www.w3schools.com/js/js_regexp.asp) 
  ![W3Schools](https://img.shields.io/badge/W3Schools-Regex_Tutorial-purple)


