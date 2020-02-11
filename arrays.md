## Arrays

This is a summary about the most popular functions for arrays.

### Filter

This method creates a new array with all elements that fulfilled by the filter, filter is a callback, if it's better for you, you can declare the function outside. The elements that keep in the new array are those that returned true.

```javascript

//Example with function declared in filter
const fruits = ['banana', 'apple', 'pineapple', 'watermelon', 'berry', 'cherry'];

const result = fruits.filter(element => element.includes('apple'));

console.log(result);

//[ 'apple', 'pineapple' ]
```
```javascript
//Example with function outside filter
const numbers = [12,4,5,86,43,26,7];

function isPair(number){
   return number % 2 === 0; //Returns the integer remainder of dividing the two operands.
}
const pairNumbers = numbers.filter(isPair);
console.log(pairNumbers);

//[ 12, 4, 86, 26 ]
```

### Foreach

Executes a provided function for each array element, ypu can get the index for the this method is cleaner and easier to use than a classical for loop, but this implementation is slower than map and you can't use generators function.

```javascript
const colors = ['red','blue','green','yellow','black'];

colors.forEach((element, index)=>{
   console.log(`Index ${index} is ${element}`)
});

```

### Includes

This method returns true or false when some element is included in array, is case sensitive for strings, you can add a parameter where search will begin.

```javascript
const numbers = [2,6,1,8,4,3];
numbers.includes(4); // true

const colors = ['red','blue','green','yellow','black'];
colors.includes('green'); // true
colors.includes('green',4); // false, second parameter is where search will begin

```

### Map


Creates a new array that it changes each element in the array from left to right invoking a callback function.

```javascript
const numbers = [2,6,1,8,4,3];

const square = numbers.map((element)=>{
   return element * element; 
});

console.log(`Original ${numbers}`);
console.log(`After map ${square}`);

```

### Pop

This method removes the last element from an array and returns that element.

```javascript

const colors = ['red','blue','green','yellow','black'];
colors.pop();
console.log(colors); // [ 'red', 'blue', 'green', 'yellow' ]

```

### Push

This method adds one or more elements to the end of an array and returns the new length of the array.

```javascript

const colors = ['red','blue','green','yellow','black'];
colors.push('gray');
console.log(colors); // [ 'red', 'blue', 'green', 'yellow', 'black', 'gray' ]

```

