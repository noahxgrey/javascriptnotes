# Fundamentals 4
## Array
#### A global object that is used in the construction of arrays
```javascript
let fruits = ["Apple", "Banana"];
fruits; // <-- to call variable
```
#### Described as "list-like objects"; single objects that contain multiple values stored in a list.
#### If you call `fruits[0];` it will return "Apple." You can replace an item by `fruits[0] = "grapes";`
```javascript
variable.length; // returns length of array
myArray.push(""); // adds string in parenthesis to array at the end
myArray.pop(); // removes last string in array
myArray.unshift(""); // adds string to the beginning of array
myArray.shift(); // removes first word in array
text.Content // gets text of that element
```

#### `concat()` method creates a new array by merging existing arrays
```javascript
let myGirls = ["Cecille", "Lone"];
let myBoys = ["Emil", "Tobias", "Linus"];
let myChildren = myGirls.concat(myBoys);
```


## Loops
#### A loop has one or more of the following features
- Counter (Initalizer) which is initalized with a certain value; starting point of the loop (ex: "Start: I have no food)
- An exit condition -- the criteria under which the loop stops. usually the counter reaching a certain value. (ex: "Have I got enough food?" lets say he needs 10 portions of food to feed his family)
- Iterator -- increments the counter by a small amount on each successive loop, until it reaches the exit condition. (ex: the farmer collects 2 portions of food/hr. Once reached 10 portions, he can stop collecting and go home.)

```javascript
//pseudo code
loop(food = 0; foodNeeded = 10) {
    if(food = foodNeeded) {
        exit loop; // we have enough
    } else {
        food += 2; // spend an hour collecting
        // loop then runs again
    }
}
//standard loop syntax
for(initalizer; exit-condition; final-expression){
    // code to run
}
// initalizer is a variable set to a number
// exit-condition is an expression featuring a comparison operator, defines when loop should stop
// final-expression is always evaluated (ran) each time the loop has gone through a full iteration. usually serves to increment or decrement the counter variable to bring it closer to the exit
let cats = ["Bill", "Jeff", "Pete", "Biggles", "Jasmin"];
let info = "My cats are called ";
let para = document.querySelector('p');

for(let i = 0; i < cats.length; i++) {
    info += cats[i] + ", "; // equivalent to info = info + cats[i] + ", ";
    }

para.textContent - info;
// Output: My cats are called Bill, Jeff, Pete, Biggles, Jasmin,
```
#### Explanation:
1) The iterator `(i)` starts at `(0) (let i = 0)`
2) It has been told to run until it is no longer smaller than the length of the cats array. The exit condition shows the condition under which the loop will still run. While `i < cats.length` is still true, the lop will run.
3) Inside the loop, we concantenate the current loop item (`cats[i]` is `cats[whatever i is at the time]`) along with a comma and a space onto the end of the info variable. So:
    - During the first tun, `i = 0`, so `cats[0] + ", "` will be concantenated onto info
    - During the second run, `i = 1`, so `cats[1] + ", "` will be concanted and so on
4) When `i = cats.length`, the loop will stop and the browser will continue

#### The final output sentence isn't well formed. Insert conditional inside code
```javascript
if(i === cats.length - 1) {
    info += "and" + cats[1] + ".";
} else {
    info += cats[i] + ", ";
}
```

### Exiting Loops with Break
#### If you want to exit a loop before all the iterations have been completed, you can use the break statemet.
```javascript
let contacts = ["Chris: #", "Sarah: #", "Bill: #", "Mary: #", "Diane: #"];
let para = document.querySelector("p");
let input = document.querySelector("input");
let btn = document.querySelector("btn");

btn.addEventListener("click", function() {
    let searchName = input.value;
    input.value = "";
    input.focus();
    for(let i = 0; i < contacts.length; i++) {
        let splitContact = contacts[i].split(":");
        if(splitContact[0] === searchName) {
            para.textContent = splitContact[0] + "'s number is "+splitContact[1] + ".";
            break;
        } else {
            para.textContent = "Contact not found.";
        }
    }
});
``` 
#### Explanation
1) Variable definitions - an array of contact info with each item being a string containing a name and a phone number separated by a colon
2) Next, we attach an event listener to `btn`, so that when it is pressed, some code is run to perform the search and return the results.
3) We store the value entered into the text input in a variable called `searchName` before then emptying the text input and focusing it again, ready for the next search.
4) The loop
    1) We start the counter at `0`, run the loop until the counter is no longer less than `contact.length`, and increment `i` by 1.
    2) Inside the loop we first split the current contact `(contacts[i])` at the colon character, and store the resulting two values in an array called `splitContact`
    3) We then use a conditional statement to test whether `splitContact[0]` (the contact's name) is equal to the inputted `searchName`. If it is, we enter a string into the paragraph to report what the contacts number is, and we use a break to end the loop.
5) After `(contacts.length - 1)` interactions, if the contact name does not match the entered search, the paragraph text is set to "contact not found." and the loop continues iterating.

### Skiping Iterations with Continue
#### The continue statement works in a similar manner to break, but instead of breaking out of the loop entirely, it skips to the next iteration of the loop
```javascript
let num = input.value;

for(let i = 1; i <= num; i++) {
    let sqRoot = Math.sqrt(i);
    if(Math.floor(sqRoot) !== sqRoot) {
        continue;
    }
    para.textContent += i + "";
}
```
#### Explanation
1) In this case, the input should be a number `(num)`. The `for` loop is given a counter starting at 1, an exit condition that says that loop will stop when the counter becomes bigger than the input number, and an iterator that adds 1 to the counter each time.
2) Inside the loop, we find the square root of each number using `Math.sqrt(i)`, then check whether the square root is an integer by testing whether it is the same as itself when it has been rounded down to the nearest integer.
3) If the square root and the rounded down square root do not equal each other `(!==)`, it means that the square root is not an integer, so we are not interested in it. In such a case, we use the `continue` statement to skip on to the next loop iteration without recording the number anywhere.
4) If the square root IS an integer, we skip past the `if` block entirely so the continue statement is not executed; instead, we concantenate the current `i` value plus a space on to the end of the paragraph content.