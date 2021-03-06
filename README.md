# Javascript-Definitive-Guide
A great book to get for extensive deep understanding  and have a solid foundation of JavaScript advanced concepts.
JavaScript: The Definitive Guide it is the bible for JavaScript programmers—a programmer's guide and comprehensive reference to the core language and to the client-side JavaScript APIs defined by web browsers.

> "A must-have reference for expert JavaScript programmers...well-organized and detailed."
—Brendan Eich, creator of JavaScript, CTO of Mozilla

The Summary below is only for certain Javascript key concepts which can also assist you either for interview questions or when you need to find a quick reference while coding. 

## Chapter 6 - Understanding Objects

### What is an Object in Javascript?
Is a fundamental datatype, unordered collection of properties and composite values.
An Object aggregates multiple values (primitive values or other objects) and allows you to store and retrieve those values by name.
In addition to maintaining its own set of properties, a JavaScript object also inherits the properties of another object, known as its **“prototype”**. The methods of an object are typically inherited properties, and this **“prototypal inheritance”** is a key feature of JavaScript. The most common things to do with objects are **create**, **set**, **query**, **delete**, **test**, and **enumerate** their Properties.

Great, so what is a __Property__? 
 - A **Property** has a __name__ and a __value__.
 - A property __name__ may be any string, including the empty string, but no object may have two properties with the same name. 
 - The __value__ may be any JavaScript value, even a getter or a setter function (or both). 
 - Also each __Property__ has associated values called __Property Attributes__:
      - __The Writable Attribute__ specifies whether the value of the property can be set.
      - __The Enumerable Attribute__ specifies whether the property name is returned by a for/in loop.
      - __The Configurable Attribute__ specifies whether the property can be deleted and whether its attributes can be altered.

## What do I need to know about Objects in Javascript:
 1. **Mutable** - objects are mutable and are manipulated by reference rather than by value; If the variable x refers to an object, and the code var y = x; is executed, the variable y holds a reference to the same object, not a copy of that object. Any modifications made to the object through the variable y are also visible through the variable x.
 2. **In Javascript there are 3 board Categories of Objects and 2 types of properties**:
 
### Those 3 Categories of Objects are:
   - **Native Object** - object or class of objects defined by the ECMAScript specification like Arrays, Functions, Dates, and regular expressions (for example) are native objects.
   
   - **Host Object** - Object defined by the host environment (such as a web browser) within which the JavaScript interpreter is embedded. *The HTMLElement objects that represent the structure of a web page in client-side JavaScript are host objects*.
   
   - **User-defined Object** - any object created by the execution of JavaScript code.
    
### Those 2 Categories of Properties are:
   - **Own Property** - a property defined directly on an Object.
   
   - **Inherited Property** - a property defined by an Object’s prototype object.
 3.  **Multiple ways to instantiate an Object**: 
   
   - There are a couple of ways to create, or instantiate, objects. The first is to use the **new operator with a constructor**. (A constructor is simply a function that uses new to create an object—any function can be a constructor.) 

```javascript
    //this code instantiates a generic object and stores a reference to it in object:
    var object = new Object();
```
 
## Some commune Questions regarding Objects in Javascript
### Is a Javascript Object Dynamic?
Yes, JavaScript objects are dynamic—properties and can usually be added, deleted, used to simulate the static objects and “structs” of statically typed languages and they can represent sets of strings. 

### So Everything in Javascript is an Object?
Almost, everything is an Object except the primitive values: String, Number, True, False, Null, Undefined. 
And even though strings, numbers, and booleans are not objects, they behave like immutable objects


### Prototypes - What are Prototypes? 
Every JavaScript object has a second JavaScript object. This second object is known as a prototype, and the first object inherits properties from the prototype. A Prototype is simply a reference to another object. Almost all objects are given a non-null value for this property, at the time of their creation. 
```javascript
var myObject = {
    a: 2
};

myObject.a; // 2
```

Objects created by object literals have the same prototype object, and we can refer to this prototype object in JavaScript code as Object.prototype. Object.prototype is one of the rare objects that has no prototype: it does not inherit any properties. All of the built-in constructors (and most user-defined constructors) have a prototype that inherits from Object.prototype. For example, Date.prototype inherits properties from Object.prototype, so a Date object created by new Date() inherits properties from both Date.prototype and Object.prototype. This linked series of prototype objects is known as a prototype chain. An explanation of how property inheritance works is in Inheritance (see section below).


### Inheritance
JavaScript objects have a set of “own properties,” and they also inherit a set of properties from their prototype object. To understand this, we must consider property access in more detail. 

### We can query the Prototype of an Object by using the prototype Attribute since every object has associated prototype, class, and extensible attributes.
What is an Object Prototype Attribute?  - An object’s prototype attribute specifies the object from which it inherits properties.
The prototype attribute is set when an object is created. To determine whether one object is the prototype of (or is part of the prototype chain of) another object, use the isPrototypeOf() method. For example:

```javascript
var p = {x:1};                    // Define a prototype object.
var o = Object.create(p);         // Create an object with that prototype.
p.isPrototypeOf(o)                // => true: o inherits from p
Object.prototype.isPrototypeOf(o) // => true: p inherits from Object.prototype
```
