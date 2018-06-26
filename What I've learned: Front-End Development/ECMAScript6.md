# What I've learned: ECMAScript6

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

* Object literal declarations using simple fields
```javascript
// ES5
const getMousePosition = (x, y) => ({
  x: x,
  y: y
});
// ES6
const getMousePosition = (x, y) => ({ x, y });
```

* Concise Declarative Functions with ES6
```javascript
const person = {
  name: "Taylor",
  sayHello() {
    return `Hello! My name is ${this.name}.`;
  }
};
```

* Class & constructor
```javascript
class SpaceShuttle {
  constructor(targetPlanet){
    this.targetPlanet = targetPlanet;
  }
}
const zeus = new SpaceShuttle('Jupiter');
```

* Getter & Setter
```javascript
class Book {
  constructor(author) {
    this._author = author;
  }
  // getter
  get writer(){
    return this._author;
  }
  // setter
  set writer(updatedAuthor){
    this._author = updatedAuthor;
  }
}
const lol = new Book('anonymous');
console.log(lol.writer);
lol.writer = 'wut';
console.log(lol.writer);
```

* import from other files
```javascript
import { function } from "file_path_goes_here"
// We can also import variables the same way!
const capitalizeString = (string) => {
  return string.charAt(0).toUpperCase() + string.slice(1);
}
const foo = "bar";
export { capitalizeString, foo }
// export from the source file is needed.
import * as myMathModule from "math_functions";
myMathModule.add(2,3);
myMathModule.subtract(5,3);
// import all the contents
```
