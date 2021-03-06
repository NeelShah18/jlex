jlex
====
A lexical analyzer for Java source code written in Python

## Example
### Code
```python
from jlex.lexer import lex
from jlex.type import Type

tokens = lex(input)

for token in tokens:
    if token.type not in [Type.SPACE, Type.NEW_LINE, Type.BLOCK_COMMENT, Type.LINE_COMMENT]:
        print(token)
```

### Input
```java
public class Example {

    public static void main(String[] args) {
        System.out.println("Hello world!");
    }
}
```

### Output
| Type              | Value          | 
|-------------------|----------------| 
| PUBLIC            | public         | 
| CLASS             | class          | 
| IDENTIFIER        | Example        | 
| OPEN_CURLY_BRACE  | {              | 
| PUBLIC            | public         | 
| STATIC            | static         | 
| VOID              | void           | 
| IDENTIFIER        | main           | 
| OPEN_PAREN        | (              | 
| STRING            | String         | 
| OPEN_BRACE        | [              | 
| CLOSE_BRACE       | ]              | 
| IDENTIFIER        | args           | 
| CLOSE_PAREN       | )              | 
| OPEN_CURLY_BRACE  | {              | 
| IDENTIFIER        | System         | 
| POINT             | .              | 
| IDENTIFIER        | out            | 
| POINT             | .              | 
| IDENTIFIER        | println        | 
| OPEN_PAREN        | (              | 
| STRING_LITERAL    | "Hello world!" | 
| CLOSE_PAREN       | )              | 
| SEMICOLON         | ;              | 
| CLOSE_CURLY_BRACE | }              | 
| CLOSE_CURLY_BRACE | }              | 
