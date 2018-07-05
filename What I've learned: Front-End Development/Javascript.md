# Javascript

## Basic Data Structure

### Array

**Add elements**
- Array.push(element) : add element to the end of the array
- Array.unshift(element) : add element to the beginning of the array

**Remove elements**
- Array.pop() : remove element at the end of the array
- Array.shift() : remove element at the beginning of the array
- Array.splice(starting_element, how_many, optional_alternative_elements) : remove any number of consecutive elements

**Copy array**
- Array.slice(starting_element, until_element) : Extract elements from the array (original array is untouched)

**Spread operator(ES6)**
```javascript
let thisArray = [true, true, undefined, false, null];
let thatArray = [...thisArray];
// thatArray equals [true, true, undefined, false, null]
// thisArray remains unchanged, and is identical to thatArray

// Combine arrays
let thisArray = ['sage', 'rosemary', 'parsley', 'thyme'];
let thatArray = ['basil', 'cilantro', ...thisArray, 'coriander'];
// thatArray now equals ['basil', 'cilantro', 'sage', 'rosemary', 'parsley', 'thyme', 'coriander']
```

**Test array**
- Array.indexOf(element) : if element exists return index, else return -1

