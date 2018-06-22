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