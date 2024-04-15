#  C++ Notebook
My notes for C++!

## _The basics_
### Keywords
The following is a list of keywords; words that cannot be used to name
variables or others, since they are reserved for the C++ language:

| Keyword    | What it does | Keyword     | What it does |
|------------|--------------|-------------|--------------|
| `and`      | ???          | `namespace` | ???          |
| `asm`      | ???          | `not`       | ???          |
| `auto`     | ???          | `private`   | ???          |
| `bitand`   | ???          | `public`    | ???          |
| `bitor`    | ???          | `register`  | ???          |
| `bool`     | ???          | `sizeof`    | ???          |
| `break`    | ???          | `switch`    | ???          |
| `char`     | ???          | `throw`     | ???          |
| `const`    | ???          | `try`       | ???          |
| `continue` | ???          | `typeid`    | ???          |
| `default`  | ???          | `union`     | ???          |
| `delete`   | ???          | `unsigned`  | ???          |
| `do`       | ???          | `virtual`   | ???          |
| `else`     | ???          | `void`      | ???          |
| `export`   | ???          | `volatile`  | ???          |
| `float`    | ???          | `wchart_t`  | ???          |
| `goto`     | ???          | `xor`       | ???          |
| `int`      | ???          | `xor_eq`    | ???          |


### Variablewise
We have the following ways to designate variables in our programs. 
Note that every variable must be preceded by its type.
```
int i, j, k
int n = 1, m
float particles, sand_grains
```

### Input and Output
To print text on the console, we can use `cout` and the operator `<<` 
like so:
```
cout << "I love you, this world, and everyone in it!"
cout << "I love " << "sweet things!" # The arguments are passed from left to right
```
To take an input into our program, we can use `cin` and the operator `>>`:
```
int plates
cin >> plates
```
### Data Types
| Data Type | Description                     | Extra tips                |
|-----------|---------------------------------|---------------------------|
| `char`    | For singular characters         | Can only store [-128,127] |
| `int`     | For integers                    |                           |
| `float`   | For floats (real numbers)       |                           |
| `double`  | For bigger floats               |                           |

### Modifiers
| Modifier   | What it does              | Extra tips                             |
|------------|---------------------------|----------------------------------------|
| `short`    | For smaller numbers       | Cannot be used with `char` or `float`  |
| `long`     | For larger numbers        | Cannot be used with `char`             |
| `unsigned` | For positive numbers ONLY |                                        |

### Operators


## _The intermediates_
### Data Structures

## _The hard ones_
### Header file names
For now, you must know that every program you code, must contain the 
following lines:
```
#include <iostream>
using namespace std;
int main(void) {
    ... /* Here goes your code */
    return 0
}
```

### Libraries

## _The curiosities and extra tips_
* You can use `\n` in the middle of a `string` to make a jump in line. 