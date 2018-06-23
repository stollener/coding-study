# ECMAScript6 Cheat Sheet

### Destructuring Assignment
* Destructure object elements, and assign them to the variables.
```javascript
var voxel = {x: 3.6, y: 7.4, z: 6.54 };
const { x, y, z} = voxel;  // x = 3.6, y = 7.4, z = 6.54
const { x : a, y : b, z : c } = voxel // a = 3.6, b = 7.4, c = 6.54
```