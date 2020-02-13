## Arrays

This is a summary about the most popular functions for arrays.

### Filter

This method creates a new array with all elements that fulfilled by the filter, filter is a callback, if it's better for you, you can declare the function outside. The elements that keep in the new array are those that returns true.

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

### Reduce 

This function returns one value that is result of the operations that is executed by a reducer function, this is saved by accumulator across each iteration throughout the array, and ultimately becomes the final, single resulting value, Reduce has four arguments:

- Accumulator (acc): Their responsibility is remember the value after each iteration.
- Current Value (cur): Current element that is processed by the reducer
- Current Index (idx): The index of the current element being processed in the array
- Source Array (src): The array that will be reduced

```javascript
const numbers = [3,3,3,3];

const reduceResult = numbers.reduce((accumulator, currentValue, currentIndex, array) =>{
  return accumulator + currentValue
});

console.log(reduceResult); // 12

```
There is a variant of this method where reducer goes right to left, it has same properties and arguments, you can use it as 

```javascript
   array.reduceRight();
```

### Reverse

This method The first array element becomes the last, and the last array element becomes the first.

```javascript
const numbers = [1,2,3,4,5];
numbers.reverse();
console.log(numbers);//[5,4,3,2,1]
```

### Shift

This method removes the first element and returns that element;

```javascript
const colors = ['red','blue','green','yellow','black'];
colors.shift();
console.log(colors); //[ 'blue', 'green', 'yellow', 'black' ]
```

### Slice 

Returns an new array thats is a copy of some part of the original array, parameters are:

-  Begin: Index(number) where portion of array that will be copied begin
-  End: Index(number) before witch to end the extraction, this is a little tricky but an example is if you use array.slice(1,4), this function will returns an array of 3 elements the elements that start an index 1, index 2 and index 3, see this example:

```javascript 
const colors = ['red','blue','green','yellow','black'];
const newArray = colors.slice(1,4)
console.log(newArray); //[ 'blue', 'green', 'yellow' ]

```
  
### Unshift        

This method adds one or more elements to the beginning of the array and returns the new length.

```javascript
const colors = ['red','blue','green','yellow','black'];
colors.unshift('purple', 'white');
console.log(colors); //['purple','white','red','blue','green','yellow','black']
```

### Splice 

You can change or removing elements in an array, using arguments: index, numbers of elements to delete, element to add.

```javascript
const colors = ['red','blue','green','yellow','black'];
// This change is on index 1, second parameter is 0 so won't remove any element an add a new one with value gray
colors.splice(1, 0, 'gray');
console.log(colors);

colors.splice(5, 1, 'white');
// Replaces 1 element at index 5
console.log(colors);
```

### Sort 

This method returns the sorted array, by default the sort order is ascending and convert every element to string and the comparator use UTF-16 code units values to sort, you can add a function to specifies to define the sort order. You must use the first and second element to compare as parameters.
The algorithm used on this implementation for Mozilla is MergeSort In Chrome's v8 source code, it uses QuickSort and InsertionSort, for smaller arrays.

```javascript
//ascending order for strings
const colors = ['red','blue','green','yellow','black'];
colors.sort();
console.log(colors); //[ 'black', 'blue', 'green', 'red', 'yellow' ]

//descending order
const numbers = [1,8,13,0,-32,51,2];
numbers.sort((a,b)=>{
   return b - a;
});
console.log(numbers); //[ 51, 13,   8, 2, 1,  0, -32 ]

//sorting objects
const values = [
   {value: 3},
   {value: 6},
   {value: 8},
   {value: 1}
];
values.sort((a,b)=>{
   return a.value - b.value;
});

console.log(values); //[ { value: 1 }, { value: 3 }, { value: 6 }, { value: 8 } ]

```