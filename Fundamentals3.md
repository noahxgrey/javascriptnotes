# Fundamentals 3
## Functions
#### Functions are reusable blocks of code

#### Functions vs Methods
#### Built in browser functions are methods. The two words are largely interchangeable. To actually use a function after it has been defined, you've got to run it. This is donw by including the name of the function in the code somewhere followed by parenthesis.
```javascript
function myFunction() // define
myFunction() // call/run
```

#### Anonymous Function: function(). Won't do anything on its own. Used generally along with an event handler.

#### Some functions require parameters to be specified when you are invoking them -- these are values that need to be included inside the function parenthesis, which it needs to do its job properly.

#### Function scope and conflicts
#### scope -- when you create a function, the variables and other things defined inside the function are inside their own separate scope, meaning they are locked away in their own separate compartments, unreachable from inside other functions or from code outside the functions. Top level outside all of your functions is called the global scope. Values defined inside the global scope are accessible from everywhere in the code.

#### Return values -- values returned by the function when it completes

#### squared() -- returns the square of the #
#### cubed() -- returns the cube of the #
#### factorial() -- returns the factorial(ex: 5! = 5 * 4 * 3 * 2 * 1 = 120) of the #
#### parameter - the values in the ()
```javascript
function ask(question, yes, no)
// text of the question
// function to run if yes
// function to run if no
```

#### Function Declaration -- a function, declared as a separate statement
#### Function Expression -- a function, created inside an expression or inside another syntax construct
```javascript
// Functin Declaration Syntax
function sayHi() {
    alert("Hello");
}
// Function Expression Syntax
let sayHi = function() {
    alert("Hello");
}; // a function expression is used inside a statement. ; is recommended at the end of statements
// Meaning is the same. Both say "create a function & put it into the variable sayHi.
```

#### The idea is that we pass a function and expect it to be "called back" later if necessary. 

#### A function is a value representing an "action"
#### A function expression is created when the execution reaches it and is usable from then on. Ex: Once the execution flow passes to the right side of the assignment (let sum = function) now the function is created and can be called on.

#### A function declaration is usable in the whole script/code block. When JavaScript prepares to run the script, it first looks for function declarations in it and creates the functions. After all are processed, the execution goes on.

#### When to choose function delcaration vs expression?
#### Function declaration is the first to consider. If that does not work, than expression should be used.

#### Arrow Functions
```javascript
// syntax
let func = (argument1, argument 2, ... argN) => expression
// this creates a function that has arguments, evaluates the expression on the right side with their use and returns result.
let sum = (a, b) => a + b;
alert(sum(1, 2)); // 3
// Taking arguments from the left of => and evaluated the right side expression
```