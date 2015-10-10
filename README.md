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

```
function Student(name) {
	this.name = name;
	this.printName = function() {
		console.log(this.name);
	};
}
```

```
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

```
var student = Person("Milad");		// when constructor called without new
console.log(name); 		// "Milad"
```



