# Classes And Instances

## Objectives

1. What is a Ruby object?
2. What is a Ruby class and how does it create objects?
3. What is a Ruby instance?

## Ruby Objects Represent Real Objects

Let's begin with a brief experiment. Open up IRB and execute the following code:

```ruby
greeting = "hi"
greeting === "hi"
```	

The return value of that second line of code should be `false`. What? (you might be wondering.) Didn't we *just* set the `greeting` variable equal to the string `"hi"`? So why is that equality operator returning `false` when we compare `greeting` to a string, `"hi"`? 

Well, the string `"hi"` that `greeting` points to is a *different object* entirely. 

### What is an Object?

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

## Classes and Instances

In object oriented programming, objects are created by making new instances of a class. 

### What's a Class?

Think of a class like a factory that produces products on an assembly line. The factory produces a fleet of similar products, all based off of the same blueprint. A Ruby class is both the factory and the blueprint––it contains the instructions for creating new objects and it has the ability to create those objects. 

Let's say we have a toy factory that produces thousands of toy cars. All of the toy cars have four wheels and the same shape. All of the toy cars can be wheeled around when kids play with them. If the factory produces two blue toy cars using it's toy car blueprint, the two toys will look alike and function in the same way, but they are still two different toys, two different objects. 

This is how a Ruby class works. It contains code that acts as the "blueprint" for producing a fleet of similar objects, as well as code for creating each individual new object, also called an *instance* of a class. 

#### Philosophy Break

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

### Creating Instances of a Class

Let's return, once again, to our example from earlier. Now we can understand that the string, `"hi"`, that the `greeting` variable refers to, and the second string, `"hi"`, are *two different instances of the String class*. Just like the two different, but identical, blue toy cars made from the same blueprint. 

Let's take a closer look:

The Ruby core library contains code that looks something like this: 

```ruby
class String

	def length
		# the code that gives this method it's functionality
	end
end
```

The String class is pre-defined for us. So, every time we create a string, by typing `"some stuff"`, we are creating a *new instance of the String class*.  

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

### Writing Our Own Class

We've seen that some classes come pre-defined, like the String class. Let's define our own class using the toy example from above to help us get familiar with the syntax of building classes and instantiating objects. 

#### Defining a Class

A class is defined with the following: 

```ruby
class Toy
	# this called the class body, it's where you define the methods that you want to give your class and it's instances. 
end
```

Class names begin with capital letters. If your class name contains two words, the name should be camel cased, like this: 

```ruby
class MyClass

end
```

#### Creating Instances with the `#new` Method

When a class makes a new individual object using it's blueprint, we call that object an **instance of the class the produced it**. To instantiate a new instance of a class, we use the `#new` method, calling it on the class itself. Let's give that a shot on the `Toy` class we've just defined. 

```ruby
Toy.new
  => #<Toy:0x007fe88934ec88> 
```
Notice that the return value of the `#new` methods it the new toy instance, or *object*, that we've just created. The string of letters and numbers is it's object ID. 

#### Operating on Instances of a Class

In basic Ruby, we learned to define methods that do things. For example:

```ruby
def hello_world
	puts "hello world"
end
```

Methods, however, operate on *objects*. The classes that we will learn to build produce objects, and we can define methods inside of those classes that can then be called on the instances that the classes will produce. 

Let's give our `Toy` class some methods before we move on. That way we'll have something to play around with. 

```ruby
class Toy

	def number_of_wheels
		4
	end
	
	def play_with_toy
		puts "VROOOOOM!"
	end
```

Okay, now we're ready to create a new `Toy` instance. 

```ruby
toy_car = Toy.new
```

Notice that we've set a variable, `toy_car`, equal to the result of `Toy.new`. What we've done here is set a variable equal to our instance of the `Toy` class, our toy object. Now we can operate on that toy instance by calling it's various methods on the `toy_car` variables that points to it. 

Let's play with our new toy car:

```ruby
toy_car.number_of_wheels
  => 4
toy_car.play_with_toy
	=> "VROOOOOM!"
```

Objects respond to the methods that are called on them. When we call `toy_car.number_of_wheels`, we are asking the instance of `Toy` how many wheels it has and it is responding with `4`, the return value of that particular method. 

This is what is meant by the idea that object oriented programming creates living entities, made out of code. The objects we create respond to the questions we ask, by way of the methods we define in a class. They enact behaviors and talk back to you, the programmer. 

#### Different Instances are Different Objects

Let's make another toy car:

```ruby
second_toy_car = Toy.new
	=> #<Toy:0x007fe88933e7e8> 
```
We can learn more about the objects we've created by using some handy tricks:

* The `#class` method can be called on an instance to learn the name of the class that produced it. 
* The `#inspect` method can be called on an instance of a class and will return the object's class name and object ID as a string. 
* The `#methods` method can be called on an instance of a class and will return all of the methods that are available to be called on that instance. 

Let's `#inspect` our two `Toy` instances. 

```ruby
toy_car.inspect
  =>"#<Toy:0x007fe88934ec88>" 
second_toy_car.inspect
  =>"#<Toy:0x007fe88933e7e8>"
```

Notice that the two different instances of the `Toy` class have totally different object IDs. They are two different object that live in two different locations in the memory of our computer. 

## Conclusion: Objects as Metaphors
 
In object oriented programming, we treat our objects as representatives of real-world objects. We strive to write code that mirrors real-world environments and situations because we understand that our code is written to solve real-world problems. If you're writing a program to play a game of tic tac toe, your code should mirror the real, solid, tangible elements of a game of tic tac toe. You should create a "board" object and a "player" object.

As we take a deeper dive into object orientation, we'll see that entire applications will be modeled on real-world situations and environments and we'll come to understand our code as a concrete, living entity that programmers and users can interact with. 
