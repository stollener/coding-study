# Javascript Study Note

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

### Object

Collection of key-value pairs.

```javascript
let FCC_User = {
  username: 'awesome_coder',
  followers: 572,
  points: 1741,
  completedProjects: 15
};
let userData = FCC_User.followers;
// userData equals 572
let userData = FCC_User['followers']
// userData equals 572
```

Object can be nested.

```javascript
let nestedObject = {
  id: 28802695164,
  date: 'December 31, 2016',
  data: {
    totalUsers: 99,
    online: 80,
    onlineStatus: {
      active: 67,
      away: 13
    }
  }
};
```

'delete' can delete the key-value pair of the object.

```javascript
delete foods.bananas;
```

Check if an object has a property.

```javascript
users.hasOwnProperty('Alan');
'Alan' in users;
// both return true
```

Iterate the keys of an object.

```javascript
for (let user in users) {
  console.log(user);
};
// logs:
Alan
Jeff
Sarah
Ryan
```

Generate an Array of All Object Keys with Object.keys()


## Object Oriented Programming

**Properties and dot notation**

```javascript
let duck = {
  name: "Aflac",
  numLegs: 2
};
console.log(duck.name);
// This prints "Aflac" to the console
```

**Methods**

Methods are functions of objects.

```javascript
let duck = {
  name: "Aflac",
  numLegs: 2,
  sayName: function() {return "The name of this duck is " + duck.name + ".";}
};
duck.sayName();
// Returns "The name of this duck is Aflac."
```

'this' means object itself.

**Constructor**

Define properties and behaviors which belong to the new object.

```javascript
function Bird() {
  this.name = "Albert";
  this.color = "blue";
  this.numLegs = 2;
  // "this" inside the constructor always refers to the object being created
}

let blueBird = new Bird();

// Accept parameters
function Bird(name, color) {
  this.name = name;
  this.color = color;
  this.numLegs = 2;
}
```

**instanceof function**

Verify whether an object is instance of a constructor.

```javascript
let Bird = function(name, color) {
  this.name = name;
  this.color = color;
  this.numLegs = 2;
}

let crow = new Bird("Alexis", "black");

crow instanceof Bird; // => true
```

**Prototype properties**

```javascript
function Dog(name) {
  this.name = name;
  Dog.prototype.numLegs = 4;
}

// Set prototype to a new object
Bird.prototype = {
  numLegs: 2, 
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name);
  }
};
```

**Constructor property**

```javascript
function joinBirdFraternity(candidate) {
  if (candidate.constructor === Bird) {
    return true;
  } else {
    return false;
  }
}
```

Manually setting the prototype to a new object, deletes constructor property.
So you should include constructor property in it.

```javascript
Bird.prototype = {
  constructor: Bird, // define the constructor property
  numLegs: 2,
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name); 
  }
};
```

**Inheritance**

Inherit behaviors from a supertype

```javascript
function Animal() { }
Animal.prototype = {
  constructor: Animal, 
  eat: function() {
    console.log("nom nom nom");
  }
};
let duck = Object.create(Animal.prototype);
let beagle = Object.create(Animal.prototype);
duck.eat(); // Should print "nom nom nom"
beagle.eat(); // Should print "nom nom nom" 
```

Set the Child's Prototype to an Instance of the Parent

```javascript
function Animal() { }
Animal.prototype = {
  constructor: Animal,
  eat: function() {
    console.log("nom nom nom");
  }
};
function Dog() { }
Dog.prototype = Object.create(Animal.prototype);
let beagle = new Dog();
beagle.eat();  // Should print "nom nom nom"
```

To reset the inherited constructor property:

```javascript
Bird.prototype.constructor = Bird;
```

Add additional methods after inheritance

```javascript
Bird.prototype.fly = function() {
  console.log("I'm flying!");
};
```

A mixin allows other objects to use a collection of functions.

```javascript
let flyMixin = function(obj) {
  obj.fly = function() {
    console.log("Flying, wooosh!");
  }
};
// The flyMixin takes any object and gives it the fly method.
let plane = {
  model: "777",
  numPassengers: 524
};
flyMixin(plane);
```

Use Closure to Protect Properties Within an Object from Being Modified Externally

```javascript
function Bird() {
  let hatchedEgg = 10; // private property

  this.getHatchedEggCount = function() { // publicly available method that a bird object can use
    return hatchedEgg;
  };
}
let ducky = new Bird();
ducky.getHatchedEggCount(); // returns 10
```

Immediately Invoked Function Expression (IIFE)

```javascript
(function () {
  console.log("Chirp, chirp!");
})(); // this is an anonymous function expression that executes right away
// Outputs "Chirp, chirp!" immediately
```

Use an IIFE to Create a Module

```javascript
let motionModule = (function () {
  return {
    glideMixin: function (obj) {
      obj.glide = function() {
        console.log("Gliding on the water");
      };
    },
    flyMixin: function(obj) {
      obj.fly = function() {
        console.log("Flying, wooosh!");
      };
    }
  }
}) (); // The two parentheses cause the function to be immediately invoked

motionModule.glideMixin(duck);
duck.glide();
```

## Functional Programming


