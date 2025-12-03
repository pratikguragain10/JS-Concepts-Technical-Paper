# Technical Paper on JavaScript Concepts

---

## 1. Different Datatypes in JavaScript

- JavaScript supports dynamic typing—variables can store any type.

- A particular kind of data item, as defined by the values it can take.

- Primary Data Types:
    - Number
    - String
    - Boolean
    - Null
    - Undefined
    - Symbol
    - BigInt
    - Object (Arrays, Functions, Dates)

- Simple Example

    ``` javascript

        let age = 21;            // number
        let name = "Pratik";     // string
        let isActive = true;     // boolean
        let data = null;         // null
        let x;                   // undefined
        let user = {id: 1};      // object
    ```

- Real-Life Example

    - Like storage boxes—each can hold a different type of item (text, number, object).

---

## 2. Scopes in JavaScript

- Global Scope : accessible anywhere.
- Function Scope : variables declared inside a function.
- Block Scope : variables within { } (if, loops).

- Simple Example

    ``` javascript

        let a = 10;  // global
        function test(){
            let b = 20; // function scope
            if(true){
                let c = 30; // block scope
            }
        }

    ```

---

## 3. let vs var vs const

| Feature |	var | let | const |
| ------- | --- | --- | ----- |
| Scope | Function | Block | Block |
| Redeclare | Allowed |	Not allowed | Not allowed |
| Reassign | Allowed | Allowed | Not allowed |

---


## 4. Why We Must Not Use var

- Causes unexpected issues because it ignores block scope and allows redeclaration.

- Simple Example

    ``` javascript

        if(true){
            var x = 10;
        }
        console.log(x);  // 10 (not safe)

    ```

---

## 5. Why Using Global Variables Is Bad

- Hard to debug & maintain
- Can be unintentionally overwritten
- Reduces modularity

---

## 6. Truthy & Falsy Values

- Falsy Values:

    - A falsy value is a value that is considered false when encountered in a Boolean context.
    - 0, "", null, undefined, false, NaN

- Truthy Values:

    - In JavaScript, a truthy value is a value that is considered true when encountered in a Boolean context.
    - Everything else (e.g., "Hello", [], {}, 1)

- Simple Example

    ``` javascript

        if("") console.log("true");  // will NOT run

    ```

--- 

## 7. Function Hoisting

- Function declarations are hoisted, function expressions aren’t.

- Simple Example

    ``` javascript

        greet();  // works
        function greet(){
            console.log("Hello");
        }

    ```

---

## 8. What Happens When a Function Has No Return

- Returns undefined implicitly.

- Simple Example

    ``` javascript

        function add(a, b){
            const sum = a + b;
        }
        console.log(add(2,3)); // undefined
    ```

---

## 9. Different Ways of Declaring Functions

-   ``` javascript

        function normal() {}
        const expr = function() {}
        const arrow = () => {}
    ```

---

## 10. Pass by Value vs Pass by Reference

- Pass by Value

    - When a variable is passed by value, a copy of the actual value is passed to the function. 
    - Any changes made to the parameter inside the function do not affect the original variable.
    
    ``` javascript

        let a = 10;
        let b = a;
        b = 20;
        console.log(a); // 10

    ```

- Pass by Reference

    - When a variable is passed by reference, a reference to the actual data is passed. 
    - This means changes made to the parameter inside the function affect the original variable.

    ``` javascript

        let obj1 = { age: 21 };
        let obj2 = obj1;
        obj2.age = 30;
        console.log(obj1.age); // 30

    ```

---

## 11. Different Types of Loops

 -   ``` javascript

        for(let i=0;i<5;i++) {}
        for(let index in array) {}
        for(let value of array) {}
        array.forEach(item => {})
        while(condition) {}

     ```

---

## 12. MDN Documentation

- Always refer to MDN Web Docs for accurate JS references.

- Link: https://developer.mozilla.org

---

## 13. Popular Array Utility Methods

- Utility Methods

    - Utility methods in JavaScript are reusable functions designed to perform common, specific tasks, often simplifying complex operations       and improving code readability and maintainability.

      | Method | Mutable? | Example |
      | ------ | -------- | ------- |
      | pop() | Yes | arr.pop() |
      | push() | Yes	| arr.push(4) |
      | concat() | No | arr.concat(arr2) |
      | slice() |	No | arr.slice(1,3) |
      | splice() | Yes | arr.splice(1,1) |
      | join() | No | arr.join('-') |
      | flat() | No |	arr.flat(2) |

    - ``` javascript

         Finding
         arr.find(x => x > 5)
         arr.indexOf(10)
         arr.includes(3)
         arr.findIndex(x => x.name === "Sam")

         Higher Order
         arr.forEach(x => console.log(x))
         arr.filter(x => x>5)
         arr.map(x => x*2)
         arr.reduce((acc,val) => acc + val, 0)
         arr.sort((a,b) => a-b)

         Chaining
         nums.filter(n => n>5).map(n => n*2).reduce((a,b) => a+b)  

     ```
---

## 14. Popular String Methods

| Method |	Mutable? | Example |
| ------ | --------- | -------- |
| trim() |	No | " hi ".trim() |
| split() |	No | "a,b,c".split(",") |
| toUpperCase() | No | str.toUpperCase() |
| replace() | No | str.replace("a","b") |

---

## 15. Popular Object Methods

- In JavaScript, object methods are functions that are stored as properties within an object.

- Simple Example

   ``` javascript

        Object.keys(obj)      // immutable
        Object.values(obj)
        Object.entries(obj)
        Object.assign({},obj) // immutable copy

   ```

---

## 16. When to Use forEach vs map, filter, reduce

| Method | Use Case |
| ------ | -------- |
| forEach |	side effects (logging, pushing) |
| map | create new array |
| filter | keep matching values |
| reduce | single output (sum, group) |

---

## 17. Mutable vs Immutable

- Mutable: Mutable objects are those whose state or content can be modified after they are created. 
           This means you can change their properties, values, or elements without creating a new object in memory. 

- Immutable: Immutable values are those whose content cannot be changed after they are created. 
             Any operation that appears to "modify" an immutable value actually results in the creation of a new value, leaving the                      original unchanged.

## 18. Error Handling

- Error handling in JavaScript allows managing unexpected issues during code execution, preventing crashes, and improving user experience.

- Simple Example

     ``` javascript

        try{
            throw new Error("Invalid input");
        }
        catch(error){
            console.error(error.message);
        }

     ```

  | throw | vs | throw new Error |
  | ----- | -- | --------------- |
  | throw "Message" |	 | throw new Error("Message") |
  | throws string | | throws error object (best practice)|

--- 

## 19. Spread Operator

- The spread operator in JavaScript, denoted by three dots (...), is a powerful syntax used to expand or "spread out" the elements of an iterable (like an array or string) or the properties of an object into places where multiple elements or properties are expected. 

- Simple Example

     ``` javascript

        let arr2 = [...arr1]

     ```

---

## 20. Template Literals

- Template literals, also known as template strings, are a feature in JavaScript (introduced in ES6/ES2015) that provide an enhanced way to work with strings compared to traditional string concatenation.

- Enclosed by Backticks: Template literals are defined using backticks (`` ` ``) instead of single or double quotes.

- Embedded Expressions (Interpolation): You can embed variables or JavaScript expressions directly within a template literal using the syntax ${expression}. The expression inside the curly braces will be evaluated and its result inserted into the string.

- Simple Example

     ``` javascript

        let msg = `Hello ${name}`

     ```

---

## 21. Default Parameters

- Default parameters in JavaScript allow you to initialize function parameters with default values if no value or undefined is passed for those parameters when the function is called.

- Simple Example

   ``` javascript

        function greet(name="guest"){}

   ```

---

## 22. Destructuring

- It allows you to unpack values from arrays or properties from objects into distinct variables. 
- It provides a more concise and readable way to extract data compared to traditional methods.

- Simple Example

     ``` javascript

        const {name, age} = person

     ```

---

## 23. Closures

- A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). 
- In other words, a closure gives a function access to its outer scope.

- Simple Example

    ``` javascript

        function outer(){
            let x = 10;
        return function inner(){ console.log(x); }
        }

    ```

---

## 24. Arrow vs Regular Functions

 - Normal Function: Uses the function keyword.
 - Arrow Function: Uses the => syntax, often more concise, especially for single-expression functions.

    | Arrow | Regular |
    | ----- | ------- |
    | No this binding |	Own this |
    | Short syntax | Longer |

---

## 25. === vs ==

- '==' : Before comparing values, the == operator attempts to convert one or both operands to a common type if their types differ.
- '===' : The === operator compares values without attempting any type conversions.

- Example

    ``` javascript

        0 == false   // true
        0 === false  // false

    ```

---

## 26. null vs undefined

- Undefined indicates that a variable has been declared but has not yet been assigned a value, or that a property of an object does not exist.
- Null represents the intentional absence of any object value.

  | null | undefined |
  | ---- | --------- |
  | intentional empty | not assigned |

---

## 27. Modules

- JavaScript modules provide a standardized way to organize and structure code into reusable, independent units. 
- This modular approach enhances code maintainability, reusability, and overall project organization, especially in larger applications.

- Example

    ``` javascript

        module.exports = add;
        const add = require("./math")

    ```

---

## 28. Console Methods

- The console object in JavaScript provides various methods for interacting with the browser's debugging console. 
- These methods are essential for debugging, logging information, and analyzing code execution.

- Simple Example

     ``` javascript

        console.log(), console.error(), console.warn(), console.table()

     ```

---

## 29. Best Practices

- Meaningful variable names
- Consistent indentation
- Avoid long functions
- Avoid global vars

---

## 30. Passing Functions to Functions

- In JavaScript, functions are "first-class citizens," meaning they can be treated like any other value, such as a number or a string. 
- This allows you to pass functions as arguments to other functions, a powerful concept known as callbacks or higher-order functions.

- Simple Example

    ``` javascript

        function execute(fn){ fn(); }
        execute(() => console.log("run"));

    ```

---

## 31. Named vs Anonymous Functions

- An anonymous function is something that is declared without an identification.
- Named functions are simply a way of referring to a function that employs the function keyword followed by a name that can be used as a callback to that function.

- Simple Example

    ``` javascript

        function named(){}
        const anon = function(){}

    ```

---

## 32. Variable Number of Arguments

- The "variable names" for arguments passed to a function are referred to as parameters. 
- These parameters are defined within the parentheses of a function declaration.

- Simple Example

    ``` javascript

        function sum(...nums){}

    ```

---

## 33. Debugging Strategies

- Use breakpoints
- console logging
- isolate logic
- read stack trace daily

---

## References

- https://developer.mozilla.org/en-US/docs/Glossary/Truthy
- https://www.geeksforgeeks.org/javascript/pass-by-value-and-pass-by-reference-in-javascript/
- https://developer.mozilla.org
- https://medium.com/@abhishekmaran/7-essential-javascript-utility-functions-for-your-web-projects-3f9227e0b4f7
- https://www.geeksforgeeks.org/javascript/javascript-string-methods/
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Closures
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions
- https://www.geeksforgeeks.org/javascript/difference-between-anonymous-and-named-functions-in-javascript/
