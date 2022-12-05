# CSC 4330: Exam 2 (Revised)
By Vincent Kim
<br>CSC 4330: Programming Language Concepts
<br><br>

<i>Rules revised and analyzers redone in Python.<br>
You can run the analyzer here: https://replit.com/@VincentKim3/Test2Redo#main.py</i>

```txt
<program> --> INIT ':' <stmt> ';'
<stmt> --> <if_stmt> | <while_stmt> | <for_stmt> | <as_s> | <declaration>
<if_stmt> --> incase <bool> { <stmt> ';' }
<else_stmt> --> ifnot { <stmt> ';' }
<while_stmt> --> during <bool> { <stmt> ';' }
<for_stmt> --> for <bool> { <stmt> ';' }
<as_s> --> <vrbl> = <expression>
```

### Production Rules
```txt
E --> E + T
E --> E – T
E --> T
T --> T * F
T --> T / F
F --> +F
F --> -F
F --> a
F --> (E)
```

This should conform to the standards of LL grammer and therefore have no ambiguity.

### Precedence: Top (First) to Bottom (Last)
- Brackets
- Order
- Multiplication
- Division
- Addition
- Subtraction

### Operators
| Operator           | Regex | Token |
| ------------------ | ----- | ----- |
| Addition           | +     | PLUS  |
| Subtraction        | -     | MNUS  |
| Multiplication     | \*    | MULT  |
| Division           | /     | DIVS  |
| Open Parenthesis   | (     | STRP  |
| Closed Parenthesis | )     | ENDP  |
| Assignment         | =     | SIGN  |

### Relationals
| Relational               | Regex | Token |
| ------------------------ | ----- | ----- |
| Less Than                | <     | LESS  |
| Greater Than             | >     | MORE  |
| Less Than or Equal To    | <=    | LEEQ  |
| Greater Than or Equal To | >=    | MOEQ  |
| Equal To                 | :=    | EQTO  |
| Not Equal To             | /=    | NOEQ  |
| And                      | and   | AND   |
| Or                       | or    | OR    |
| Code Block Start         | :     | BLKS  |
| Code Block End           | ;     | BLKE  |

### Data Types
| Data Type | Token | Regex | Bytes |
| --------- | ----- | ----- | ----- |
| short     | SNUM  | \d+   | 2     |
| int       | INUM  | \d+   | 4     |
| long      | LNUM  | \d+   | 8     |

### Keywords
| Keyword  | Regex           | Token |
| -------- | --------------- | ----- |
| Variable | [a-z][A-Z]{6-8} | id    |
| While    | during          | DRNG  |
| Do       | exec            | EXEC  |
| For      | given           | GIVN  |
| Else     | ifnot           | IFNO  |
| Start    | init            | INIT  |
| End      | term            | TERM  |
