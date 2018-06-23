# Fundamentals 2
## Strings

#### Concantenate is a fancy programming word that means "join together." Joining together strings in JavaScript uses the plus(`+`) operator, the same one we use to add numbers together. EX:
```javascript
let one = "Hello";
let two = "how are you?";
let joined = one + two;
joined;
```
### JavaScript String Methods
#### String Length -- `let sln = text.length;`
#### `indexOf()` method returns the position of the first occurrence of a specified text in a string. 
#### `lastIndexOf()` method returns the position of the last occurrence.
#### `search()` method searches a string for a specified value and returns the position of the math.
#### `indexOf()` and `search()` are not the same. `search()` cannot take a second start position argument.

### 3 methods for extracting a part of a string.
- slice(start, end)
- substring(start, end)
- substr(start, length)

### `slice()`
#### Extracts a part of a string and returns the extracted part in a new string. Takes two parameters: the start and end position.
```javascript
let string = "Apple, Banana, Kiwi";
string.slice(7, 13); // Banana
string.slice(-12, -6); // counts backwards
string.slice(7); // will slice from 7 --> out
```
### `substring()`
#### Similar to slice, but cannot have negative indexes.

### `substr()`
#### Similar to slice, except the second parameter specifies the length.
```javascript
string.slice(7, 6); // Banana
```

### `replace()`
#### Replaces a specified value with another value in a string.
```javascript
let string = "Please visit Microsoft";
string.replace("Microsoft", "W3Schools"); // "Please visit W3Schools"
```
#### This will only change the first occurence of the word. To replace all matches use `(/Microsoft/g, "W3Schools");`

#### Converting to upper and lower case
```javascript
toUpperCase();
toLowerCase();
```
#### `concat();` joins two or more strings
```javascript
let a = "Hello";
let b = "World";
a.concat(" ", b);
```

### Extracting string characters
#### `charAt();` returns the character at a specified position in a string. 
#### `charCodeAt();` returns the unicode of the character at a specific position

#### A string can be converted to an array with the `split();` method.
```javascript
let txt = "a, b, c, d, e"; // string
txt.split(","); // splits on commas
txt.split(" "); // splits on spaces
txt.split("|"); // splits on pipe
```

### A `method` is a bit of functionality that is built into the language or into specific data types.


## Conditionals

#### Comparison examples
- greater/less than: `a > b, a < b`
- greater/less than or equals to: `a >= b, a <= b`
- equality is `a == b`
- not equals is `a != b`

#### Boolean is the result. True means "yes", "correct" or "the truth." False means "no", "false" or "a lie." EX:
```javascript
alert(2 > 1); // true (correct)
alert(2 == 1); // false (wrong)
alert(2 != 1); //true (correct)
```

#### String comparison -- to see which string is greater than the other. EX:
```javascript
alert("7" > "A"); // true (because 7's place # is higher)
alert("Glow" > "Glee") // true (Glow: 5678, Glee: 5643. # is higher)
```
#### Lexicographic order is a generalization of the way words are alphabetically ordered based on the alphabetical order.

#### Comparison of different types -- when compared values belong to different types.
```javascript 
alert("2" > 1); // true, string "2" becomes a number 2
alert("01", == 1); // true, string "01" becomes a number 1
alert(true == 1); // true, true becomes 1
alert(false == 0); // true, false becomes 0
```

#### Strict equality -- a regular  equality (`==`) check has a problem. It cannot differ 0 from false.
```javascript
alert(0 == false); // true
alert("" == false); // true
```
#### That's because operands of different types are converted to a number by the equality operator `==`. An empty string becomes a zero. A strict equality operator `===` checks the equality without the type conversion. 
```javascript
alert(0 === false); // false, types are different.
```
#### Strict non-equality: `!==`

#### Comparison with null and undefined.
```javascript
null === undefined // false, each of them belongs to a separate type
null == undefined // true, they equqal each other but not any other value
// null becomes 0 and undefined becomes NaN
alert(null > 0); // false, comparisons convert null to a number
alert(null == 0); // false, equality check works without conversions
alert(null >= 0); // true, null and undefined equal each other and nothing else.
```

#### An incomprable undefined -- the value undefined cannot participate in comparisons at all. Undefined always gets converted to NaN. 

#### Dictionary Comparisons
```javascript
("2" > "12"); // true, first character of "2" is greater than first character of "12". 2 > 1
```

### Logical Operators

#### `||(OR)`
#### Typically, logical `OR` is meant to manipulate bollean values only. Four possible combos:
```javascript
result = a||b;
alert(true||true); // true
alert(false||true); // true
alert(true||false); // true
alert(false||false); // true
//Result is always true except for the case when both operands are false. If an operand is not a boolean, it is converted to one.
if (1||0) {
    alert("truthy!");
} // Most of the time, OR is used in an if statement
let hour = 9;
if(hour < 10 || hour > 18) {
    alert("The office is closed");
}
// OR seeks the first truthy value. 
```
#### The OR operator does the following
1. Evaluates operands left to right
2. For each operand, converts it to a boolean. If the result is true, then stop and return to the original value.
3. If all other operands have been accused, return the last opperand.


#### `&&(AND)`
#### In classical programming, AND returns true if both operands are truthy and false otherwise.
```javascript
result = a&&b;
alert(true&&true); // true
alert(false&&true); // false
alert(true&&false); // false
alert(false&&false); // false
// AND seeks the first falsy value. 
let hour = 12;
let minute = 30;
if(hour == 12 && minute == 30) {
    alert("Time is 12:30");
}
```
#### The AND operator does the following:
1. Evaluates left to right
2. For each operand, converts to boolean. If false, stop & return original value.
3. If all other operands have been assessed (i.e. all were truthy) return last operand.
```javascript
// If the first operand is truthy, AND returns the second operand
alert(1 && 0); // 0
alert(1 && 5); // 5
// If the first operand is falsy, AND returns is. The 2nd operand is ignored
alert(null && 5); // null
alert(0 && "no matter what"); // 0
```
#### We can also pass several values in a row. First falsy one is returned.
```javascript
alert(1 && 2 && null && 3); // null
```
#### When all values are truthy, the last value is returned
```javascript
alert(1 && 2 && 3); // 3
```
#### `AND&&` executes before `OR||`. The precedence of the AND operator is higher than OR, so it executes before OR. In the code below, `1 && 0` is calculated first.
```javascript
alert(5 || 1 && 0); // 5
```
#### Just like `OR`, the `AND` operator can some times replace if.
```javascript
let x = 1;
(x > 0) && alert("Greater than zero!");
// The action in the right part of && would execute only if the evaluation reaches it. That is: only is x > 0 is true. same as:
let x = 1;
if (x > 0) {
    alert("Greater than zero!");
} // this way is more readable. 
```


#### `!(NOT)`
#### The operator accepts a single argument and does the following:
1. Converts the operand to boolean type: true/false
2. Returns an inverse value:
```javascript
alert(!true); // false
alert(!0); // true
// A double NOT !! is sometimes used for converting a value to boolean type
alert(!!"non-empty string"); // true
alert(!! null); // false
```


### Conditional Statements
- Use `if` to specify a block of code to be executed if condition is true
- Use `else` to specify a block of code to be executed if same condition is false
- Use `else if` to specify a new condition to test if first condition is false
- Use `switch` to specify many alternative blocks to be executed

#### `if` statement
#### Use to specify a block of JavaScript code to be executed if a condition is true
```javascript
// syntax
if(condition) {
    block of code to be executed if true
}
```

#### `else` statement
#### Use to specify a block of code to be executed if a condition is false
```javascript
// syntax
if(condition) {
    block of code to be executed if true
} else {
    block of code to be executed if false
}
```

#### `else if` statement
#### Use to specify a new condition if the first condition is false
```javascript
// syntax
if(condition 1) {
    block of code to be executed if 1 is true
} else if(condition 2) {
    block of code to be executed if 2 is true
} else {
    block of code to be executed if 1 & 2 are false
}
```

#### `switch` statements
```javascript
// syntax
switch(expression){
    case choice 1:
    run this code
    break;

    case choice 2:
    run this code instead
    break;
    // include as many cases as you like

    default:
    actually just run this code
}
```

#### Explanation
1. The ketyword `switch` followed by `()`
2. An expression/value inside `()`
3. Keyword `case` followed by a choice that the expression could be
4. Some code to run if the choice matches the expression
5. A `break` statement followed by `;`
6. The keyword `default`. Option that runs if none of the choices match.

#### Ternary Operator -- a small bit of syntax that tests a condition and returns one value/expression if it is true, and another if it is false -- this can be useful in some situations, takes up less code than if..else. 

#### Booleans
#### A number 0, an empty string " ", null, undefined, and NaN become false. "Falsy" values. All other values are true.

#### Ternary operator is so you can write if/else statements simpler &  shorter
```javascript
// syntax
let result = condition? value 1: value 2
// The condition is evaluted, if it's truthy then value 1 is returned, otherwise -- value 2. Multiple ?'s
let age = prompt("age?", 18);
let message = (age < 3)? "Hi baby!":
            (age < 18)? "Hello!":
            (age < 100)? "Greetings!":
            "What an unusual age!";
alert(message);
```
#### The first question mark checks whether age < 3. If true, returns "Hi, baby!" Otherwise, checks for age < 18. If true returns "Hello!" Otherwise, checks age < 100. If true returns "Greetings!" Otherwise, returns "What an unusual age!" Sometimes the ? mark is used as a replacement for if. Not recommended.
