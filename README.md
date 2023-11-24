Your assignment is to write the following functions in the descriptions below - good luck!

## **difference**

- this function takes in two parameters and returns the difference of the two;

```jsx
difference(2, 2); // 0
difference(0, 2); // -2
```

```js
function difference(x, y) {
  return x - y;
}
```

## **product**

- this function takes in two parameters and returns the product of the two;

```jsx
product(2, 2); // 4
product(0, 2); // 0
```

```js
function product(x, y) {
  return x * y;
}
```

## **printDay**

- this function takes in one parameter (a number from 1-7) and returns the day of the week (1 is Sunday, 2 is Monday, 3 is Tuesday etc.). If the number is less than 1 or greater than 7, the function should return undefined;

```jsx
printDay(4); // "Wednesday"
printDay(41); // undefined
```

```js
function printDay(day) {
  switch (day) {
    case 1:
      return "Sunday";
    case 2:
      return "Monday";
    case 3:
      return "Tuesday";
    case 4:
      return "Wednesday";
    case 5:
      return "Thursday";
    case 6:
      return "Friday";
    case 7:
      return "Saturday";
    default:
      return undefined;
  }
}
```

## **lastElement**

- this function takes in one parameter (an array) and returns the last value in the array. It should return **_undefined_** if the array is empty.

```jsx
lastElement([1, 2, 3, 4]); // 4
lastElement([]); // undefined
```

```js
function lastElement(arr) {
  if (arr.length === 0) return undefined;
  return arr[arr.length - 1];
}
```

## **numberCompare**

- this function takes in two parameters (both numbers). If the first is greater than the second, this function returns “First is greater”. If the second number is greater than the first, the function returns “Second is greater”. Otherwise the function returns “Numbers are equal”

```jsx
numberCompare(1, 1); // "Numbers are equal"

numberCompare(2, 1); // "First is greater"

numberCompare(1, 2); // "Second is greater"
```

```js
function numberCompare(x, y) {
  if (x > y) {
    return "First is greater";
  } else if (y > x) {
    return "Second is greater";
  } else {
    return "Numbers are equal";
  }
}
```

## **singleLetterCount**

- this function takes in two parameters (two strings). The first parameter should be a word and the second should be a letter. The function returns the number of times that letter appears in the word. The function should be case insensitive (does not matter if the input is lowercase or uppercase). If the letter is not found in the word, the function should return 0.

```jsx
singleLetterCount("amazing", "A"); // 2
singleLetterCount("Rithm School", "o"); // 2
```

```js
function singleLetterCount(word, letter) {
  let letterCount = 0;
  for (char of word) {
    if (char.toLowerCase() === letter.toLowerCase()) {
      letterCount++;
    }
  }
  return letterCount;
}
```

## **multipleLetterCount**

- this function takes in one parameter (a string) and returns an object with the keys being the letters and the values being the count of the letter.

```jsx
multipleLetterCount("hello"); // {h:1, e: 1, l: 2, o:1}
multipleLetterCount("person"); // {p:1, e: 1, r: 1, s:1, o:1, n:1}
```

```js
function multipleLetterCount(word) {
  counts = {};
  for (char of word) {
    if (counts[char] === undefined) {
      counts[char] = 1;
    } else {
      counts[char] += 1;
    }
  }
  return counts;
}
```

## **arrayManipulation**

- this function should take in at most four parameters (an array, command, location, and value).

  - If the command is “remove” and the location is “end”, the function should remove the last value in the array and return the value removed. (In this case, the function only needs three arguments.)
  - If the command is “remove” and the location is “beginning”, the function should remove the first value in the array and return the value removed. (In this case, the function only needs three arguments.)
  - If the command is “add” and the location is “beginning”, the function should add the value (fourth parameter) to the beginning of the array and return the array.
  - If the command is “add” and the location is “end”, the function should add the value (fourth parameter) to the end of the array and return the array.

  ```jsx
  arrayManipulation([1, 2, 3], "remove", "end"); // 3

  arrayManipulation([1, 2, 3], "remove", "beginning"); // 1

  arrayManipulation([1, 2, 3], "add", "beginning", 20); // [20,1,2,3]

  arrayManipulation([1, 2, 3], "add", "end", 30); // [1,2,3,30]
  ```

  ```js
  function arrayManipulation(arr, cmd, loc, val) {
  if (cmd === 'remove') {
    if (loc === 'end') {
        return arr.pop();
    } else if (loc === 'beginning') {
        return arr.shift();
    }
  } else if (cmd === 'add') {
    if (loc === 'beginning') {
        arr.unshift(val);
        return arr;
    } else if (loc === 'end') {
        arr.push(val);
        return arr;
    }
  }
  ```

## **isPalindrome**

- A Palindrome is a word, phrase, number, or other sequence of characters which reads the same backward or forward. This function should take in one parameter and returns **_true_** or **_false_** if it is a palindrome. As a bonus, allow your function to ignore whitespace and capitalization so that **_isPalindrome(‘a man a plan a canal Panama’);_** returns **_true_**

```jsx
isPalindrome("testing"); // false

isPalindrome("tacocat"); // true

isPalindrome("hannah"); // true

isPalindrome("robert"); // false
```

```js
function isPalindrome(str) {
  return str.toLowerCase().split("").reverse().join("") === str.toLowerCase();
}
```

## **Bonus**

### **Rock / Paper / Scissor**

- using your knowledge so far, build a game of Rock/Paper/Scissor where through the use of the **_prompt_** function, a user can enter their choice and based on a random selection - they can either tie/win or lose against a computer.

```js
function rockPaperScissors() {
  let choices = ["rock", "paper", "scissors"];
  let user = prompt("Choose rock, paper, or scissors").toLowerCase();
  let bot = choices[Math.floor(Math.random() * choices.length)];

  if (!choices.includes(user)) {
    return "Invalid choice. Try again";
  }

  if (bot === user) {
    return "Tie";
  }
  if (bot === "rock" && user === "scissors") {
    return `You lose. (You: ${user}, Bot: ${bot})`;
  }
  if (bot === "paper" && user === "rock") {
    return `You lose. (You: ${user}, Bot: ${bot})`;
  }
  if (bot === "scissors" && user === "paper") {
    return `You lose. (You: ${user}, Bot: ${bot})`;
  }

  return `You win. (You: ${user}, Bot: ${bot})`;
}
```
