# JS Generators

**Generator** is a type of *iterator*.
it has .next() method which returns two things *{ value , done }*

 - value :- it can be anything e.g. object , string , number etc.
 - done :- it is boolean value. which indicate the iteration is over or not.

```sh
 someIterator.next()
 // { value : something,done:false }
 someIterator.next()
 // { value : anotherThing,done:false }
 someIterator.next()
 // { value : undefind , done:true }
``` 
  
***generator*** functions return generator objects.

> function* defines a generator function
```sh
function* genFunction() {
	yield "hello world"
} 

let genObject = genFunction();
//Generator{}

genObject.next();
//{ value: "hello world", done: false }

genObject.next();
//{ value: undefined, done:true }
```

> *yield* will decide what to put inside the value property while returning.

for example
```sh
function* logGenerator() {
	console.log("running ...")
	yield 'paused';
	console.log("running again.. ")
	return 'stopped';
}

let logObj = logGenerator();
logObj.next(); //running...
// {value: 'paused' , done: false}
logObj.next(); //running again..
// {value: 'stopped', done: true}
```

> here next function will run until it finds yield keyword
> next time when it called it runs after previous yield keyword.

**generators** are also a *iterable*
```sh
function* abcs(){
	yield 'a'
	yield 'b'
	yield 'c'
	yield 'd'
}
for(let char of abcs() {
	console.log(char.toUpperCase());
}
//A
//B
//C
//D

[...abcs()] // ["a","b","c","d"]
```

# What is the main use of generators ?!!

for simple word we can use simple array or string then why should we use generators over array and specially iterators.

***"main purpose of  generators is to define custom iterables"***

**Features of Generators :-**

 - lazy evaluation and infinite sequences.
 

> lazy evaluation :- it means it gives value whenever we call the next method
> infinite sequence :- let's we have ss