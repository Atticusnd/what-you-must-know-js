## Scope: 

Is the accessibility of variables, functions, and objects in some particular part of your code during runtime. In other words, scope determines the visibility of variables and other resources in areas of your code, javascript has two types of scopes.

```javascript
var animal1 = 'lion'; //This variable is in GLOBAL scope

function getAnimals(){ //This function is in GLOBAL scope
    var animal2 = 'elephant';//This variable is on local scope because is defined in the function
    console.log(animal1); // lion
    console.log(animal2); // elephant
}   

getAnimals();
```

**Global Scope:** There is only one global scope, If element is declared outside all functions or curly braces, it can be used anywhere in your code. In node js, global scope is different if you define a variable as global, module will be local to that module.

**Local Scope:** Variables that are usable only in a specific part of your code. there are two kinds of local scope:

- **Function Scope:** When you declare a variable in a function you can access this variable only within the function. Lives as long as your functions are called and executed.

- **Block Scope:** If you use curly braces ( {} ) in a condition (if, switch) or a loop (for, while), only if you declare a variable with let and const this variables will lives as long as the condition or loop is finished
```javascript
var animal1 = 'tiger'; //This variable is on global scope, it doesn't matters if it's var, const or let

function getAnimals(){ //This function is on global scope
    var animal2 = 'elephant';//This variable is on local scope because is defined within a function
    
    if(animal2 === 'elephant'){ //this if defines the beginning of the block scope
        var animal3 = 'lion'; //This variable is defined on block scope, but you can use it out of the block because is a var
        let animal4 = 'zebra'; //This variable is defined on block scope
        const animal5 = 'shark'; //This variable is defined on block scope
        console.log(animal4); // zebra
    }//this curly brace defines the final of the block scope

    console.log(animal1); // tiger is printed because animal1 is on the global scope
    console.log(animal2); // elephant is printed because animal2 is part of the local scope
    console.log(animal3); // lion is printed because animal3 is declared as var in the block scope, and this block scope is within in the local scope
    console.log(animal4); // ReferenceError: animal4 is not defined, if you use let, animal4 only lives in the block
    console.log(animal5); // ReferenceError: animal4 is not defined, if you use const, animal5 only lives in the block
}   

getAnimals();
```
### Lexical Scope:

Javascript allowed to declare functions within others, in a nested group of functions, the inner functions have access to the variables and other resources of their parent scope.

```javascript
function outerFunction () {
  const outer = `outer function!`

  function innerFunction() {
    const inner = `inner function!`
    console.log(outer) //outer function!, it has access to outer because was declare on parent's scope
  }

  console.log(inner) // Error, inner is not defined, only inner function has accessibility to their variables
}
```
### Closures:

