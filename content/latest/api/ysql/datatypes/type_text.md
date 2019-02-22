---
title: TEXT
summary: String of Unicode characters
description: Character Types
menu:
  latest:
    identifier: api-ysql-datatypes-text
    parent: api-ysql-datatypes
aliases:
  - /latest/api/ysql/datatypes/text
isTocNested: true
showAsideToc: true
---

## Synopsis
Character types are used to specify data of a string of Unicode characters.

## Syntax
```
type_specification ::= TEXT | VARCHAR

text_literal ::= "'" [ '' | letter ...] "'"
```

Where 

- `TEXT` and `VARCHAR` are aliases.
- Single quote must be escaped as ('').
- `letter` is any character except for single quote (`[^']`).

## Semantics

- Columns of type `TEXT` or `VARCHAR` can be part of the `PRIMARY KEY`.
- The length of `TEXT` string is virtually unlimited.
- Currently, value of type character datatype are neither convertible nor comparable to non-text datatypes. This restriction will be removed.

## See Also

[Data Types](..#datatypes)
