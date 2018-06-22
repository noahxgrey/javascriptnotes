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
