# Fundamentals 1
## Numbers
#### You can divide, multiply, and subtract numeric strings, but addition does not work. If you add a number and a string, the result will be a string. 
#### EX:
```javascript
let x = 10;
let y = 20;
let z = x + y; // z will be 30 ( a number)

let x = "10";
let y = 20;
let z = x + y; // z will be "1020" (a string)
```
- (+) Addition
- (-) Subtraction
- (*) Multiplication 
- (/) Division
- (%) Remainder
- (++) Increment
- (--) Decrement 

### 100 (operand) + (operator) 50 (operand)

- Integers: whole numbers
- Floating Point Numbers (floats): have decimal points
- Doubles: type of floating point number that have greater precision than the standard
- Binary: the lowest level language--0's and 1's
- Octal: Base 8, uses 0-7 in each column
- Hexadecimal: Base 16, uses 0-9 and a-f
- Decimal: Base 10 (0-9)

#### Assignment Operators - operators that assign a value to a variable
##### += Addition Assignment: Adds value on the right to value on the left. EX: 
```javascript
x = 3; x += 4;
// shortcut for x = 3; x = x + 4;
```

##### -= Subtraction Assignment: Subtracts value on the right to value on the left. EX:
```javascript
x = 6; x -= 3;
// shortcut for x = 6; x = x - 3;
```

##### *= Multiplication Assignment: Multiplies value on the right to value on the left. EX:
```javascript
x = 2; x *= 3; 
// shortcut for x = 2; x = x * 3;
```

##### /= Division Assignment: Divides value on the right to value on the left. EX:
```javascript
x = 10; x /= 5; 
// shortcut for x = 10; x = x / 5;
```

##### === Strict Equality (tests whether identical)
```javascript 
5 === 2 + 4 // false
```
##### !== Strict Non-Equality (tests whether not identical)
```javascript
5 !== 2 + 3 // false
```
### Booleans (true/false)
- display the correct text label on a button depending on whether a feature is turned on or off
- display a game over message if a game is over or a victory message if the game has been won
- display the correct seasonal greeting depending what holiday season it is
- zoom a map in or out depending on what zoom level is selected

#### An operator is unary if it has a single operand
```javascript
let x = 1;
```
#### An operator is binary if it has two operands
```javascript
let x = 1, y = 3;
```

#### If either operand is a string, then it converts the other to a string as well. ONLY applies to addition. 
```javascript
alert(2 + 2 + "1"); // alert brings up an alert box on the page. it would result in "41". first the code adss 2 + 2, then adds 4 to the string "1" to result in "41"
```

#### The operator "+" applied to a single value doesn't do anything, but if the operand is not a number, then it is converted into one
```javascript
let apples = "2";
let oranges = "3";
alert(+apples + +oranges); // 5
```

#### Parenthesis override any predence
```javascript
let a = 1;
let b = 2;
let c = 3 - (a = b + 1);
alert(a); // 3
alert (c); // 0
```

#### The result of a % b is the remainder of the integer division of a by b
```javascript
alert(5 % 2); // 1
alert(8 % 3); // 2
alert(6 % 3); // 0
```

### Exponentiation
- For a number b, the result of a ** b is a multiplied by itself b times
```javascript
alert (2 ** 2); // 4 (2 * 2)
alert(2 ** 3); // 8 (2 * 2 * 2)
alert(2 ** 4); // 16 (2 * 2 * 2 * 2)
```

### Bitwise Operators
- Treat arguments as 32-bit integer numbers and work on the level of their binary representation. Not JavaScript specific.

#### List of operators:
- AND (&)
- OR (|)
- XOR (^)
- NOT (~)
- LEFT SHIFT (<<)
- RIGHT SHIFT (>>)
- ZERO-FILL RIGHT SHIFT (>>>)

#### The comma operator allows us to evaluate several expressions dividing them with a comma. Each of them is evaluated, but the result of only the last one is returned.
```javascript
let a = (1 + 2, 3 + 4);
alert(a); // 7
```

