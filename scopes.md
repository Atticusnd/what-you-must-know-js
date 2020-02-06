## Scope: 

Is the accessibility of variables, functions, and objects in some particular part of your code during runtime. In other words, scope determines the visibility of variables and other resources in areas of your code, javascript has two types of scopes.

```
var animal1 = 'lion'; //This variable is in GLOBAL scope

function getAnimals(){ //This function is in GLOBAL scope
    var animal2 = 'elephant';//This variable is on local scope because is defined in the function
    console.log(animal1); // lion
    console.log(animal2); // elephant
}   

getAnimals();
```

_Global Scope:_ There is only one global scope, If element is declared outside all functions or curly braces, it can be used anywhere in your code. In node js, global scope is different if you define a variable as global, module will be local to that module.

_Local Scope:_ Variables that are usable only in a specific part of your code. there are two kinds of local scope:

- _Function Scope:_ When you declare a variable in a function you can access this variable only within the function. Lives as long as your functions are called and executed.

- _Block Scope:_ If you use curly braces ( {} ) in a condition (if, switch) or a loop (for, while), only if you declare a variable with let and const this variables will lives as long as the condition or loop is finished
```
var animal1 = 'tiger'; //This variable is on global scope, it doesn't matters if it's var, const or let

function getAnimals(){ //This function is on global scope
    var animal2 = 'elephant';//This variable is on local scope because is defined within a function
    
    if(animal2 === 'elephant'){ //this if defines the beginning of the block scope
        var animal3 = 'lion'; //This variable is defined on block scope, but you can use it out of the block because is a var
        let animal4 = 'zebra'; //This variable is defined on block scope
        const animal5 = 'shark'; //This variable is defined on block scope
        console.log(animal4); // zebra
    }//this curly brace defines the final of the block scope

    console.log(animal1); // tiger
    console.log(animal2); // elephant
    console.log(animal3); // lion
    console.log(animal4); // ReferenceError: animal4 is not defined, if you use let, animal4 only lives in the block
    console.log(animal5); // ReferenceError: animal4 is not defined, if you use const, animal5 only lives in the block
}   

getAnimals();
```
### Lexical Scope:

Javascript allowed to declare functions within others, in a nested group of functions, the inner functions have access to the variables and other resources of their parent scope.


### Closures:

Javascript allowed to declare functions within others, in a nested group of functions, the inner functions have access to the variables and other resources of their parent scope.
