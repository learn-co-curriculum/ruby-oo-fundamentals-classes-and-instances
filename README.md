# Ruby Intro To Classes And Instances

## Outline

1. What's an object? The things in our program. In Ruby, every expression returns an object. An object is an entity that contains all the data about itself and all the logic need to accomplish a job. It's a metaphor for the thing itself, a model, a representation of an entity in our code. Objects are also individuals, each object is unique by definition, even if they represent the same "canonical" entity. The string "Hello" is different than another string "Hello", each string is a unique object, even though they have the same character values and when compared by == are equal (but when compared with === are not - show that).

## About Classes

2. Where do objects come from? All objects are born from a factory for those kind of objects, like a String factory vs a Number factory vs a Car factory vs a Dog factory vs a Baby factory. These factories for objects, that can spawn or birth new individuals of itself, new instances of itself, are called Classes. Classes represent the ideal of the object, capital A Atom, not a particular atom, but atoms in general, capable of making actual new atoms according to the canonical defintion. Classes are Plato's Ideal Form in programming.

A. Class definition syntax.
B. Class as a factory example (new).
C. Class constructors for primitives like Strings. Show the String class is predefined.

cover
`class Person; end` the syntax of defining a class. Capital Letters. CamelCase constants for class names. indenting the class body (point out what the class body is)

Person.new - you're calling new on the class - calling a method on an objet, asking the class to give you a new instance.

`Person.new`
`Dog.new`
`Baby.new`

assign to variables - leads to - besides bringing them to life, what can you do with an isntance, what is an instance.


## About Instances

3. When a class makes a new individual of itself, we call that thing an instance. fido vs Dog. north_west vs Baby. Each instance has it's own memory and data and classes birth instances. The class is not just a factory for the instance but also a blue print, it defines with instances of it can do. An empty class can do nothing special. But we can add behavoir via methods. And we can even do way more.

look at ruby object notation and explain that - memory address, unique identifiers for this piece of data on your computer.

`person.class` that you can ask an object about the parent class.
`person.methods` objects respond to methods/messages, they know about themselves, their data and methods.

## Metaphors and Tangible / Tactile Objects

OO and Classes and instances gives us objects with which to model the world and manifestations of those models we can play with. I can write this - won't be long because lots of that idea is in a different readme, but let's re-express it.
