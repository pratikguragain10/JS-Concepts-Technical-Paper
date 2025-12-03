# Technical Paper on JavaScript Concepts

---

## 1. Different Datatypes in JavaScript

- JavaScript supports dynamic typing—variables can store any type.

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

    - 0, "", null, undefined, false, NaN

- Truthy Values:

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

    ``` javascript

        function normal() {}
        const expr = function() {}
        const arrow = () => {}
        
    ```

---

## 10. Pass by Value vs Pass by Reference

- Pass by Value
    
    ``` javascript

        let a = 10;
        let b = a;
        b = 20;
        console.log(a); // 10

    ```

- Pass by Reference

    ``` javascript

        let obj1 = { age: 21 };
        let obj2 = obj1;
        obj2.age = 30;
        console.log(obj1.age); // 30

    ```

---

## 11. Different Types of Loops

    ``` javascript

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
| Method | Mutable? | Example |
| ------ | -------- | ------- |
| pop() | Yes | arr.pop() |
| push() | Yes	| arr.push(4) |
| concat() | No | arr.concat(arr2) |
| slice() |	No | arr.slice(1,3) |
| splice() | Yes | arr.splice(1,1) |
| join() | No | arr.join('-') |
| flat() | No |	arr.flat(2) |

    ``` javascript

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

- Mutable: modifies original push, pop, splice, sort

- Immutable: returns new value map, filter, concat, slice

## 18. Error Handling

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
| throw "Message" |	throw new Error("Message") |
| throws string | throws error object (best practice)|

--- 

## 19. Spread Operator

    ``` javascript

        let arr2 = [...arr1]

    ```

---

## 20. Template Literals

    ``` javascript

        let msg = `Hello ${name}`

    ```

---

## 21. Default Parameters

    ``` javascript

        function greet(name="guest"){}

    ```

---

## 22. Destructuring

    ``` javascript

        const {name, age} = person

    ```

---

## 23. Closures

    ``` javascript

        function outer(){
            let x = 10;
        return function inner(){ console.log(x); }
        }

    ```

---

## 24. Arrow vs Regular Functions
    | Arrow | Regular |
    | ----- | ------- |
    | No this binding |	Own this |
    | Short syntax | Longer |

---

## 25. === vs ==

    ``` javascript

        0 == false   // true
        0 === false  // false

    ```

---

## 26. null vs undefined
    | null | undefined |
    | ---- | --------- |
    | intentional empty | not assigned |

---

## 27. Modules

    ``` javascript

        module.exports = add;
        const add = require("./math")

    ```

---

## 28. Console Methods

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

    ``` javascript

        function execute(fn){ fn(); }
        execute(() => console.log("run"));

    ```

---

## 31. Named vs Anonymous Functions

    ``` javascript

        function named(){}
        const anon = function(){}

    ```

---

## 32. Variable Number of Arguments

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