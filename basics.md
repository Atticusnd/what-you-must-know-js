## var, let y const

- _const:_ The identifier can't be changed or redeclared, is block scoped. (Not to be confused with immutable)
- _let:_ The identifier can be changed or redeclared, is block scoped.
- _var:_ The variable may or may not be reassigned, and the variable may or may not be used for an entire function, or just for the purpose of a block or loop.

## Difference between == and ===

- == Converts the operands to the same type before making the comparison.

```javascript
  '5' == 5 //true
```
- ===  Is a strict comparison, is only true if type and the contents match

```javascript
  '5' === 5 //false
   5 === 5 //true
```

### Spread operator

It's for iterable objects to expand it into the list of arguments, with spread operator you could do:

- Copying an array
- Using an array as arguments
- Concatenating or combining arrays
- Using some math functions
- Adding an item to a list
