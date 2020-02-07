### Data Types

JavaScript is a loosely typed or a dynamic language. Variables in JavaScript are not directly associated with any particular value type, and any variable can be assigned (and re-assigned) values of all types

- Seven data types that are primitives:
    - Boolean
    - Null
    - Undefined
    - Number
    - BigInt
    - String
    - Symbol
- and Object

### var, let y const

- _const:_ The identifier can't be changed or re-declared, is block scoped. (Not to be confused with immutable)
- _let:_ The identifier can be changed or re-declared, is block scoped.
- _var:_ The variable may or may not be reassigned, and the variable may or may not be used for an entire function, or just for the purpose of a block or loop.

### Difference between == and ===

- == Converts the operands to the same type before making the comparison.

```javascript
  '5' == 5 //true
```
- ===  Is a strict comparison, is only true if type and the contents match

```javascript
  '5' === 5 //false
   5 === 5 //true
```

### Spread operator (...)

It's for iterable objects to expand it into the list of arguments, with spread operator you could do:

- Copying an array
- Using an array as arguments
- Concatenating or combining arrays
- Using some math functions
- Adding an item to a list

```javascript
//Concatenating arrays
const vowels = ['a','i','u'];
const consonants = ['w','t','d'];
const letters = [...vowels,...consonants];
console.log(letters); // ['a','i','u','w','t','d']

//Math functions
const list = [1, 2000, 0, -3,6]
console.log(Math.min(list)) // NaN
console.log(Math.min(...list)) // -3

```

### for of & for in

- **for of** 

Creates a loop over iterable objects(arrays, strings). Use a variable to do an operation on each iteration, variable may be declared with const, let, or var.

```javascript
const iterable = [1,10,4]
for(let variable of iterable){
    variable+=1;
    console.log(variable)
}
// 2
// 11
// 5

// Itarating an string
const word = 'foo';

for (const letter of word) {
  console.log(letter);
}
// "f"
// "o"
// "o"
```

- **for in**

Use to iterate over the properties of an object, here variable is the key of the property and object[key] is the property, in the next example keys are shirt, pants and shoes, an the property of clothes[shirt] is white.

```javascript
const clothes = {
    shirt: 'white',
    pants: 'blue',
    shoes: 'black'
}

for(key in clothes){
    console.log(`Key: ${key} Property: ${clothes[key]}`);
}
//Key: shirt Property white
//Key: pants Property blue
//Key: shoes Property black

```
