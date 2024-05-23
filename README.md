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
The following is a table listing the operators that can be used in C++,
their priorities (higher number -> higher priority), and their uses:

| Priority | Operator      | What it does                             |
|----------|---------------|------------------------------------------|
| 10       | `!`           | Logical negation   (unary)               |
| 10       | `~`           | Bitwise negation   (unary)               |
| 10       | `(type)`      | Casting            (unary)               |
| 10       | `++`          | Adding 1           (unary)               |
| 10       | `--`          | Subtracts by 1     (unary)               |
| 10       | `+`           | Conserves the sign (unary)               |
| 10       | `-`           | Changes the sign   (unary)               |
| 9        | `*`           | Multiplication                           |
| 9        | `/`           | Division                                 |
| 9        | `%`           | Modulo                                   |
| 8        | `+`           | Sum (binary)                             |
| 8        | `-`           | Subtraction (binary)                     |
| 7        | `>>`          | Console -> Code                          |
| 7        | `<<`          | Code -> Console                          |
| 6        | `<` or `<=`   | Less than, or, less or equal than        |
| 6        | `>` or `>=`   | Greater than, or, greater or equal than  |
| 5        | `==`          | Equal to (logic)                         |
| 5        | `!=`          | Different to (logic)                     |
| 4        | `&`           | Conjunction (bitwise)                    |
| 3        | `\|`          | Disjunction (bitwise)                    |
| 2        | `&&`          | Conjunction (logic)                      |
| 1        | `\|\|`        | Disjunction (logic)                      |
| 0        | `(operator)=` | Equivalent to doing `x = x (operator) y` |

### Controlling the code flow
**Quirky C++ Moment!:** In C++, the usual "True" or "False" values are not
represented by native keywords, but rather, by an integer. If the integer is
0, then it is **false**, else, it will be **true** (it is usually represented
with a singular 1 to economise memory).
#### Making logic statements
The following is a list with the logical operators that allow us to make 
complex logic statements:

| Code   | Logical Operator     | Extra tips                        |
|--------|----------------------|-----------------------------------|
| `&&`   | Conjunction, "and"   |                                   |
| `\|\|` | Disjunction, "or"    | Lower priority than `&&`          |
| `!`    | Negation, "not"      | Higher priority than `&&`, `\|\|` |
| `&`    | Bitwise conjunction  |                                   |
| `\|`   | Bitwise disjunction  |                                   |
| `~`    | Bitwise negation     |                                   |
| `^`    | Bitwise exclusive or |                                   |

**VERY IMPORTANT NOTE:** The difference with normal logical operators and
the bitwise ones, is that the bitwise ones only work with integers, and 
will compare the two integers bit by bit, instead of taking the whole integer
as a bit (`0` if its `0`, `1` otherwise). That is, when working with
bitwise operations, the results are not only 1s and 0s, but rather,
the result of operating each pair of bits. Take the following snippet of code 
as an example:
```
int i = 15, j = 22;
```
Bitwise, they are represented as follows:
```
i: 00000000000000000000000000001111
j: 00000000000000000000000000010110
```
Now:
```
int in_logical = i && j;
```
Bitwise the value is the following, since both numbers are nonzero:
```
in_logical : 00000000000000000000000000000001
```
Now, if we try:
```
int in_bit = i & j;
```
Bitwise the value is the following:
```
in_bit : 00000000000000000000000000000110
```
Meaning, the value is 6.

#### The "if" statement
To express a condition, we use the `if` keyword, which implies that if a 
condition is met, the next instruction will be executed:
```
/* You can write it like this */
if (logical_statement) instruction_to_do;

/* Or like this */
if (logical_statement) {
    instruction_to_do
    instruction_to_do
    ...
}
```
You can also use the keyword `else` to specify what to do if the condition
isn't met:
```
if (logical_statement) {
    set_of_instructions_condition_met
} else {
    set_of_instructions_condition_not_met
}
```
You can **nest** conditionals:
```
if (condition) {
    if (condition) {
        block_of_instructions
    } else {
        block_of_instructions
    }
} else {
    block_of_instructions
}
```
And you can **cascade** conditionals:
```
if (the_weather_is_good)
    go_for_a_walk();
else if (tickets_are_available)
    go_to_the_theater();
else if (table_is_available)
    go_for_lunch();
else
    play_chess_at_home();
```

#### Case and Switch
If it occurs the case where your cascaded `if`s are too long, it is often
useful to use the following syntactic **candy**. The case and switch is
used to summarise and make more readable a code with cascaded `if`s. 
```
switch(i) {
case 1: cout << "Only one?" << endl; break;
case 2: cout << "I want more" << endl; break;
case 3: cout << "Not bad" << endl; break;
case 4: cout << "OK"<< endl;
}

/* In the following case, the program will print OK if i is 3 or 4 */
/* And, it has a default case that triggers when i is none of the cases */

switch(i) {
case 1: cout << "Only one?" << endl; break;
case 2: cout << "I want more" << endl; break;
case 3: 
case 4: cout << "OK" << endl; break;
default: cout << "Don't care"  << endl;
}
```


#### The "while", the "do" and the "for" statements
To `while` keyword works as an `if` statement. The difference is that the
code block that is inside a while block will be repeated until the condition
is not met. For example:
```
while(cat_is_tired) {
    sleep;
    eat;
}
```
There is ACTUALLY another loop statement. This is the `do`, and it has a 
few differences with the `while`statement.
* The `do` statement does its body of instructions at least once, even if
the condition isn't met. The `while` statement does not.
* In the `while` statement, the condition is checked before the body; in the
`do` statement, the condition is checked after the body. 

The structure of a `do` statement is as follows:
```
/* Like this */
do
  statement;

while(condition);

/* Or like this */ 
do {
  statement_1;
  statement_2;
  :
  :
  statement_n;
} while(condition);
```
Finally, there is good-old `for` statement. This statement is useful
at times when we need to **count** how many times a loop is made, instead
of checking if a condition is met. The structure is as follows:
```
for(initialization; checking; modifying) {
  /* the body goes here */
}

/* Real example */
for(i = 0; i < 100; i++) {
  /* the body goes here */ 
  
/* An example of an infinte loop */
for(;;) { /* If you ommit an argument, it will replace it with a 1 */
    cout << "I love you!"  
}
```
#### Spicing Loops UPPPP
**Syntactic candies** are additions to programming languages that don't
augment the expressiveness of the language, but rather, make the programmers
work a little easier. For loops, we have TWO (yummy) of these candies.
* The `break` instruction: It stops executing the current body of the loop 
and exits the loop, continuing with the program.
* The `continue` instruction: It stops executing the body of the loop and 
jumps to its end, as if it already completed all of its instructions, 
checking immediately the condition again. 


## _The intermediates_
### Data Structures
#### Arrays (Vectors)
Arrays in C++ are multi-value variables that allow us to store multiple values
in a single variable. To use them, check the following snippet of code:
```
/* To create an array*/ 
int array[5] /* The number in brackets refers to the size of the array */

/* Indexing a value in the array: 
The enumeration of positions inside the array starts at 0, meaning , the 
first element is at the 0 position */
array[0] = 11

/* To initialize an array*/
int vector[5] = {0,1,2,3,4};

/* Initiating an array without a size will make the compiler 
assume that the size is the same as the initializer */
int vector[] = {0,1,2,3,4,5,6};  

/* Making a vector of vectors, a matrix! (two dimensional array) */
int chessboard[8][8];

```

#### Structures
A structure contains any number of elements of any type. Once you've declared
a structure, you can create structured variables based off of it. Each of these
variables will contain each of said elements declared in the structure. 
Proper declarations of a structure:
```
struct STUDENT {
  string name;
  float time;
  int recent_chapter;
};

struct DATE {
     int year, month, day;
} DateOfBirth, Visits[100];

DATE current_date;
```
Now, to declare structured variables: 
```
struct STUDENT stdnt;
STUDENT stdnt2;
```
You can also initialize structures as soon as they are declared. Note that
unfilled fields, meaning, having an initializer with less elements than 
fields in a structure, will make the compiler fill up those assignations with
a `0`:
```
struct DATE date = { 2012, 12, 21 };
STUDENT he = { "Bond", 3.5, 4, 2012, 12, 21};
STUDENT she = { "Mata Hari", 12., 12, { 2012 }  };
```
To manipulate the data within the structures, the following operation is 
usually called a selector (the dot):
```
stdnt.time = 1.5;

float t;

t = stdnt.time;
```
**Notes**:
- The tag name of the structure is usually written in ALL CAPS for readability.
- A structure maybe a field of another structure. 
- However, a structure cannot be a field of itself. 
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