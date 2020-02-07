## Arrays

This is a summary about the most popular functions for arrays.

**Filter**

This method creates a new array with all elements that fulfilled by the filter, filter is a callback, if it's better for you, you can declare the function outside. The elements that keep in the new array are those that returned true.

```javascript
const fruits = ['banana', 'apple', 'pineapple', 'watermelon', 'berry', 'cherry'];

const result = fruits.filter(element => element.includes('apple'));

console.log(result);

//[ 'apple', 'pineapple' ]


const numbers = [12,4,5,86,43,26,7];

function isPair(number){
   return number % 2 === 0; //Returns the integer remainder of dividing the two operands.
}
const pairNumbers = numbers.filter(isPair);
console.log(pairNumbers);

//[ 12, 4, 86, 26 ]
```
