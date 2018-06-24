# ECMAScript6 Cheat Sheet

### Destructuring Assignment

* Destructure object elements, and assign them to the variables.
```javascript
var voxel = {x: 3.6, y: 7.4, z: 6.54 };
const { x, y, z } = voxel;  // x = 3.6, y = 7.4, z = 6.54
const { x : a, y : b, z : c } = voxel // a = 3.6, b = 7.4, c = 6.54
```

* Destructure array elements.
```javascript
const [a, b,,, c] = [1, 2, 3, 4, 5, 6];
console.log(a, b, c); // 1, 2, 5
```

* With the rest operator
```javascript
const [a, b, ...arr] = [1, 2, 3, 4, 5, 7];
console.log(a, b); // 1, 2
console.log(arr); // [3, 4, 5, 7]
```
