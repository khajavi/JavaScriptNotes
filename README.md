# JavaScriptNotes

## Constructors

* built-in constructors: `Object`, `Array`, `Function`

```javascript
function Student() {
	// empty
}

var student1 = new Student();
var student2 = new Student'

console.log(student1 instanceof Student);			 //true
console.log(student1.constructor === Student);	 //true
```

```javascript
function Student(name) {
	this.name = name;
	this.printName = function() {
		console.log(this.name);
	};
}
```

```javascript
function Student(name) {
	Object.defineProperty(this, "name", {
		get: function() {
			return name;
		}, 
		set: function(newName) {
			name = newName;
		},
		enumerable: true,
		configurable: true
	});

	this.printName = function() {
		console.log(this.name);
	};
}
```

risk of changing global object:

```javascript
var student = Person("Milad");		// when constructor called without new
console.log(name); 		// "Milad"
```

## Prototypes

```javascript
var book = {
	title: "JavaScript Book"
};

console.log("hasOwnProperty" in book);		//true
console.log(book.hasOwnProperty("hasOwnProperty"));		//false
console.log(Object.prototype.hasOwnProperty("hasOwnProperty")); 		//true
```

```javascript
var object = {};
var prototype = Object.getPrototypeOf(object);

console.log(prototype === Object.prototype); 		//true
```
