# Section 2 — Short Response

Write your responses directly in this file. Follow markdown formatting guidelines. Check the rubric.md file to see how your short responses will be graded. 

As a quick guide, check the following before submitting:
- [] Answered all parts of every question
- [] No typos or grammar mistakes (use grammarly!)
- [] Accurately uses relevant technical terminology
- [] Uses markdown to enhance readability (preview in VS Code with Command/Control + Shift + V)
- [] Responses are concise and easy to comprehend

---

## Question 1

In your own words, explain what does _encapsulation_ refer to? Why is this concept beneficial when programming? 

Provide a code snippet to illustrate _encapsulation_.

## Response 1

---Encapsulation refers to the idea that when using Object-Oriented Programming, we use multiple methods and data to allow access to some of the object’s internal state. This is not to exploit raw data and to utilize public methods to create a new interface. This is helpful because it allows the user to implement different methods that are beneficial to various parts of the code, without altering the entirety of the outside code. 

```js

class Person {

 #age; // private field

 constructor(name, age) {
   this.name = name;
   this.#age = age; 
 }

 getAge() {
   return this.#age;
 }

 setAge(newAge) {
   if (newAge > 0) {      
     this.#age = newAge;
   }
 }
}

const p = new Person("Alex", 20);

p.setAge(20);

console.log(p.getAge()); 

console.log(p.#age);  
```

## Question 2

Explain what the `this` keyword is. Why is the `this` keyword useful?

In the code snippet below, what does `this` refer to?

```js
class Counter {
	constructor() {
		this.count = 0;
	}
  increment() {
    this.count++;
  }
}

const counterA = new Counter();
const counterB = new Counter();

counterA.increment();
counterA.increment();
counterA.increment();

counterB.increment();

console.log(counterA.count);
console.log(counterB.count);
```

## Response 2
---
In JavaScript, “this” is a keyword used as a reference for what is executing/running the code. That means that “this” keyword is useful because it intends to give the class or function the ability to create various independent objects, that dont allow for them all to be stored as the same values(every object has storage of individualized data).


In the code snippet “this” keyword refers to the first object created, which is the Counter object that is being created. The “this” keyword when you are calling on counterA.increment(), “this” keyword refers directly to counterA. The “this” keyword when you are calling on counterB.increment() inside the method, the “this” keyword refers directly to the counterB. Thus, meaning that since counterA was called 3 times the counterA.count will log 3 into the terminal, and since counterB was only called 1 time, it will log 1 into the terminal after 3 is logged.

## Question 3

In your own words, explain what **polymorphism** means in OOP. Provide an example in code that demonstrates polymorphism.

## Response 3

---
Polymorphism is the concept that multiple objects can share the same method name yet have different versions of how the code behaves. Polymorphism allows us to create code that can collaborate with many types of objects, but have individualized responses.
```js
class Pet {
 speak() {
   return "pet makes a sound";
 }
}

class Dog extends Pet {
 speak() {
   return "Woof";
 }
}

class Cat extends Pet {
 speak() {
   return "Meow";
 }
}

class Bird extends Pet {
 speak() {
   return "Chirp";
 }
}
```

## Question 4

You're building a game where players can raise different digital pets: Cats, Dogs, and Birds. All pets have have a `name`, `energy` level, and `happiness` level and can all `sleep`. Cats have the ability to `hunt`, dogs have the ability to `chase`, and birds have the ability to `fly`.

**Part A:** Describe in words how you would use inheritance to organize these classes.

**Part B:** Explain one advantage of using inheritance here instead of creating three completely separate classes.


## Response 4

Part A:

I would start by creating my first parent class called “Pet” that will hold all of the collaborative behaviors and properties. The properties that would be shared are “name”, “energy”, and “happiness”, while the only shared behavior in this code would be “sleeping”. Next, I would start creating child classes of “Cat”, “Dog”, “Bird”, which all extend the Parent class “Pet class”. Because each child class has its own ability, I would then add the desired method for the pet. So, cats will have the “hunt()” method implemented, dogs will have the “chase()” method, and the birds  will get the “fly()”  method implemented inside of those desired classes. Every class is acting on its own behavior, but the same shared code lives throughout all of the classes through inheritance.

Part B: 


One advantage of using inheritance is that it will always help with keeping your code reusable and accessible. Inheritance truly helps with writing less code, so it's easier to manipulate your code into doing what you want with less code and through a set system. Inheritance helps minimize the amount of code to write because the Parent class stores all of your code for you, so it doesn't have to be repeated every time you want to create a new child class. It also allows for cleaner/more concise code, making it easy to read.