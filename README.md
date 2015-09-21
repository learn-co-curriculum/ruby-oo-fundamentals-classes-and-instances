# Classes And Instances

## Objectives

1. What is a Ruby class and how does it create objects?
2. What is a Ruby instance?
3. Deeper dive into classes and objects.

## Defining a Class

Let's say we are building a dog walking app. Our app's users might be dog walkers and dog owners and they can use the app to manage the dog walks. Such an app would need to store information about a potentially large number of dogs. So, our program needs to have a way to bundle up and operate on all the information about a particular dog. And, our program needs to be able to do this again and again. And, once more, we'll need our program to be able to create *new* bundles of information regarding individual dogs every time a new dog is added to the app. 

How can we tell our Ruby program to deal with these dogs? Well, we can write a `Dog` class that produces individual dog objects, each of which contains all the information and behaviors of an individual dog. 

Let's do it!

```ruby
class Dog
  # some code to describe a dog
end
```

The `Dog` class is defined with the `class` keyword, followed by the class name and closed with an `end`. 

Class names begin with capital letters. If your class name contains two words, the name should be camel cased, like this: 

```ruby
class MyClass
	# some code all about your awesome class
end
```

Our `Dog` class will include a series of methods that describe the behaviors and attributes of an individual dog. Then, we can use the `Dog` class to create new dog entities, or objects. 

Let's write some code to give our dogs the ability to bark:

```ruby
class Dog
	def bark
		"Woof!"
	end
end
```

Now, every dog that we make using the `Dog` class will be able to have the `#bark` method called on it. 

## Instances of a Class

The word **instance** refers to the individual objects produced from the blueprint of a class. 

We can use our `Dog` class to create individual dogs. The individual dogs will share a set of similar attributes that are defined in the `Dog` class. But, each individual dog will have unique values for those attributes. 

How do we make instances of the `Dog` class? Read on...

### Creating Instances of a Class

So, we have our `Dog` class here:

```ruby
class Dog
	def bark
		"Woof!"
	end
end
```

It is the blueprint for creating individual dogs. Let's create some individual dogs, or *dog instances*. 

```ruby
fido = Dog.new
	=>#<Dog:0x007fa764a2b5a8> 
```

To **instantiate**, or create, a new instance of a class, we use the `#new` method, calling it on the class itself. 

Notice that the return value of calling the `#new` method is the new dog instance, or *object*, that we've just created. The string of letters and numbers is it's **object ID**. 

Notice that, above, we've set a variable, `fido`, equal to the result of `Dog.new`. What we've done here is set a variable equal to our instance of the `Dog` class, our dog object. Now we can operate on that dog instance by calling the methods we defined in the `Dog` class on the `fido` variable that points to it. 

### Operating on Instances of a Class

In basic Ruby, we learned to define methods that do things. For example:

```ruby
def hello_world
	puts "hello world"
end
```

Methods, however, operate on *objects*. The classes that we will learn to build produce objects, and we can define methods inside of those classes that can then be called on the instances, or objects, that the classes will produce. 

Our `Dog` class has one method, `#bark`, that can be called on any instance of that class. This method is therefore called an **instance method**. 

Let's play with our dog instance, Fido:

```ruby
fido.bark
  => "Woof!"
```

Objects respond to the methods that are called on them. When we call `fido.bark`, we are asking the instance of `Dog` to invoke the `#bark` method, the return value of which is the string `"Woof!"`

This is what is meant by the idea that object oriented programming creates living entities, made out of code. The objects we create respond to the questions we ask, by way of the methods we define in a class. They enact behaviors and talk back to you, the programmer. 

## Different Instances are Different Objects

Let's make another dog:

```ruby
snoopy = Dog.new
  => #<Dog:0x007fa764a224f8>
```
We can learn more about the objects we've created by using some handy tricks:

* The `#class` method can be called on an instance to learn the name of the class that produced it. 
* The `#inspect` method can be called on an instance of a class and will return the object's class name and object ID as a string. 
* The `#methods` method can be called on an instance of a class and will return all of the methods that are available to be called on that instance. 

Let's `#inspect` our two `Dog` instances. 

```ruby
fido.inspect
  =>"#<Dog:0x007fa764a2b5a8>" 
snoopy.inspect
  =>"#<Dog:0x007fa764a224f8>"
```

Notice that the two different instances of the `Dog` class have totally different object IDs. They are two different objects that live in two different locations in the memory of our computer. They are very similar in many ways. For example, they will both respond to the `#bark` method. This is because they were both produced from the `Dog` class. They were made using the blueprint provided by the code in that class. But, Snoopy is not Fido. Our two `Dog` instances are totally unique, different dogs. 

## Understanding Class

Think of a class like a factory that produces products on an assembly line. The factory produces a fleet of similar products, all based off of the same blueprint. A Ruby class is both the factory and the blueprint––it contains the instructions for creating new objects and it has the ability to create those objects.

So, in our current example, we have a `Dog` class that is capable of producing an infinite number of dogs. All of the dogs that our class produces will have the ability to bark. However, just like `fido` is not the same object as `snoopy`, the individual objects created by a class are just that––individual objects. 

This is how a Ruby class works. It contains code that acts as the "blueprint" for producing a fleet of *similar*, but unique, objects, as well as code to actually create each individual new object, or class instance.

## Understanding Objects

According to Miriam Webster, an object is

> ... a material thing that can be seen and touched.

In object oriented programming, however, an **object** is a structure that combines data and the procedures necessary to operate on that data. In other words, an object is a bundle of information and behavior, wrapped up into one discrete unit.

But you can't really see or touch a bundle of data, you might be thinking. Actually, you can, and you've been doing all along throughout this course! Let's revisit our earlier example to illustrate this point. 

The string `"hi"` can be operated on in a number of ways:

* `puts "hi"` will output the string to the terminal.
* `"hi".length` will return `2`, the length of the string.
* `"hi".reverse` will return `"ih"`.

And these are only a few examples of reading and manipulating the `"hi"` object. The `"hi"` string *contains information*––i.e. it's actual content––that we can read, and has behaviors, or *methods* that are attached to it, such as `#length` and `#reverse`. 

So, in fact, `"hi"`, is a bundle of data and behaviors that both see and touch, i.e. operate on. 

### Philosophy Break

Think of a class as an abstraction of all of the characteristics and behaviors that make up an individual object of a certain type. A class then produces these individual objects using the model provided by this abstract bundle of characteristics. 

The view of object oriented classes is nothing short of a realization of the Platonic Theory of Forms. A class can be thought of as a stand-in for Plato's abstract forms.

<img src="http://readme-pics.s3.amazonaws.com/160px-Plato_Silanion_Musei_Capitolini_MC1377.jpg" align="right" width="200" hspace="10">

> Forms are the archetypes or perfect models for all of the properties that are present in material objects. The forms are the perfect examples of the properties they instantiate...Material objects are images or copies of these more real objects. 
> 
> –– [David Banach](http://www.anselm.edu/homepage/dbanach/platform.htm)

A class (or a "form) is an archetype––a Toy class that produces individual toy objects is an abstract collection of properties and behaviors that make a thing a "toy". An instance of that class is the "material object" that is but an image or a copy of it's class. 
<br/>
<br>
For Plato, all of the objects of the material world were seen as copies of an ideal form which provided their mold. So, as object oriented programmers who define the forms and create their copies, we are really building up the very reality with which we interact. 

### Some Classes Already Exist

Let's return to our String example from earlier. Now we understand the `"hi"` is an object. It is also an instance of a class that is already defined in the Ruby language––the String class. 

Every time you create a new string by simply typing something like:

```ruby
"this is my new string"
```

The Ruby core library contains code that looks something like this: 

```ruby
class String

	def length
		# the code that gives this method it's functionality
	end
	
	etc...
end
```

So, the below code to create a new string that contains the characters `h` and `i`,  

```ruby
"hi"
 => "hi"
```
is exactly the same as:

```ruby
String.new("hi")
 => "hi"
```
Both of the code snippets above create a new instance of the String class. The first method of creating, or *instantiating*, a new string is called the **literal constructor**. The second method is called the **class constructor**. 

**Advanced:** You might notice that the `#new` method we are calling on the String class appears to be taking in an argument. We'll learn more about instantiating objects via `#new` and something called the `#initialize` method in an upcoming lesson.


## Conclusion: Objects as Metaphors
 
In object oriented programming, we treat our objects as representatives of real-world objects. We strive to write code that mirrors real-world environments and situations because we understand that our code is written to solve real-world problems. Our dog walking app is an example of this. Another example––if you're writing a program to play a game of tic tac toe, your code should mirror the real, solid, tangible elements of a game of tic tac toe. You could create a "board" class and a "player" class, which produce board and player objects respectively.

As we take a deeper dive into object orientation, we'll see that entire applications will be modeled on real-world situations and environments and we'll come to understand our code as a concrete, living entity that programmers and users can interact with. 
