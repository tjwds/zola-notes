+++
title="Semicolon style"
date=2021-04-18
+++

We software developers have become incredibly attuned to the types of opinions which can lead to what the industry refers to as "holy wars."  I don't need to list any examples, because you already have one in the front of your mind, but here's one:  Windows vs. macOS.

Some of these opinions are merely personal, like the terminal-based interactive editor of choice.  Others, however, impact the folks around you.  These are mostly questions of code style, though it can expand into other fields as well.  When these opinions can become decrees, I watch most developers settle into a pattern of "anything is fine as long as it's not offensive and we somehow standardize it in a preferably automated way (though we all know that my opinion is clearly correct)."

This is why we end up with multiple conflicting code style libraries, even in languages that have code style baked into the syntax itself.

JavaScript does not have the luxury of having unification baked into the language.  There are so many considerations when looking at JavaScript code style:  which devices do we want this code to run on?  how will we transform it?  which tool will we use to standardize the code style, and which set of rules will we apply with that tool?

I have come bearing a great gift that will firmly end all of these conversations, which is a single golden rule:

**All lines of JavaScript code must be exactly 80 characters long, with leading and trailing whitespace replaced by semicolons.**

By following this rule, nothing else matters.  Who cares if a line should end in a semicolon?  It will end in several semicolons.  Who cares if final element in an array has a trailing comma?  Look at all those semicolons.  Should an if block's curly brace exist on the same line as the conditional?  It must, otherwise the proceeding block will always be executed!

Here is a toy example:

```javascript
const fizzBuzz = (limit) => {;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;;;;for (let num = 1; num <= limit; num++) {;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;;;;;;;;if (num % 15 === 0) {;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;;;;;;;;;;;;console.log('FizzBuzz');;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;;;;;;;;} else if (num % 5 === 0) {;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;;;;;;;;;;;;console.log('Buzz');;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;;;;;;;;} else if (num % 3 === 0) {;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;;;;;;;;;;;;console.log('Fizz');;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;;;;;;;;} else {;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;;;;;;;;;;;;console.log(num);;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;;;;;;;;};;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;;;;};;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
};;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
fizzBuzz(100);;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
```

The logical next step is to create rules for js code formatters to enforce this style.  Thank you for volunteering.