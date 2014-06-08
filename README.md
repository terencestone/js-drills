# Javascript Drills

These drills are designed as an introduction to the Javascript language.

## Functions

### Rectangle

In this drill, write a number of functions that calculate certain properies of a
rectangle object. A rectangle object is just a Javascript object with two
properties, `width` and `height`. Here's an example:

```javascript
var rectangle = {width: 10, height: 20};
```

A few sample rectangle objects have been included in the tests.

Here are the functions you'll need to write to get the tests to pass.

1. `area(rectangle)`, which returns the area of the rectangle
2. `perimeter(rectangle)`, which returns the perimeter of the rectangle
3. `diagonal(rectangle)`, which returns the length of the rectangle's diagonal
4. `isSquare(rectangle)`, which returns `true` if the rectangle is a square
and `false` otherwise

You may want to read this article on rectangle diagonals:
http://www.mathopenref.com/rectanglediagonals.html


### Triangle
Write a function `validTriangle` which takes as its input three
non-negative numbers.  It should return `true` if the three numbers could
form the side lengths of a triangle and `false` otherwise.

The arguments don't correspond to specific sides.  Don't worry about
handling negative inputs: garbage in, garbage out.

For example:

```javascript
validTriangle(0,0,0) # => false, because a triangle can't have 0-length sides

validTriangle(1,1,1) # => true, an equilateral triangle

validTriangle(3,4,5) # => true, a right triangle
validTriangle(4,3,5) # => true, the same right triangle
validTriangle(5,3,4) # => true, the same right triangle

validTriangle(10, 10, 100) #=> false, no such triangle exists
```

You might want to read this [Wikipedia article about Pythagorean triples](http://en.wikipedia.org/wiki/Pythagorean_triple).

## Collections

### Average
Add four instance methods to Javascript's `Array`:

1. `total`, which returns the total of all the values in the array
2. `mean`, which returns the mean of the array
3. `median`, which returns the median of the array
4. `mode`, which returns an object representing the mode(s) of the
   array with the property being the mode and the value being the frequency

Since you haven't covered extending built-in JavaScript objects, we've
provided the shells of each method for you.  All you have to do is make them
work.

### Pad
Add a method `pad` to Javascript's `Array`. The method should accept a minimum
size (non-negative integer) and an optional pad value as arguments.

If the array's length is less than the minimum size, `pad` should
return a new array padded with the pad value up to the minimum size.

For example:

```javascript
[1,2,3].pad(5);           // [1,2,3,null,null]
[1,2,3].pad(5, 'apple')   // [1,2,3,'apple','apple']
```

If the minimum size is less than or equal to the length of the array, it
should just return the array.

That is, `[1,2,3].pad(3)` should return `[1,2,3]`.

`myArray.pad(0)` should always return an array equal to `myArray`.

`pad` should always return a **new object**, i.e., it should not modify the original
array.

## Loops

### Count Between
Write a function `countBetween` which takes three arguments as input:

1. An `Array` of integers
2. An integer lower bound
3. An integer upper bound

`countBetween` should return the number of integers in the `Array` that
are between the two bounds, **including the bounds**.

It should return 0 if the `Array` is empty.

Some examples:

```javascript
countBetween([1, 2, 3], 0, 100);      // => 3
countBetween([-10, 1, 2], 0, 100);    // => 2
countBetween([10, 20, 30], 10, 30);   // => 3
countBetween([], -100, 100);          // => 0
countBetween([0], 0, 0);              // => 1
```

### Factorial
Write a `factorial` function which takes as its input a non-negative integer
and calculates the factorial of that number.

The factorial of a number is the product of all integers from 1 up to that
number.  For example:

```javascript
factorial(5) // 120 (5 * 4 * 3 * 2 * 1 == 120)
```

The factorial of 0 is defined to be 1.

See the Wikipedia article on the factorial:
http://en.wikipedia.org/wiki/Factorial) for more information.

### Longest String
Write a function `longestString` which takes as its input an `Array` of
`Strings` and returns the longest `String` in the `Array`.

For example:

```javascript
longestString(['cat', 'applesauce', 'apples']); // => "applesauce"
```

If the input `Array` is empty `longestString` should return `null`.

### Times Table
Implement a function called `timesTable` which takes as its input an
integer and prints out a times table with that number of rows.

The numbers can be separated by any spaces or tabs, but each row must be on a
new line.  This means it's ok if the columns don't line up.

For example, `timesTable(5)` should print the following out to the screen:

```
1  2  3  4  5
2  4  6  8  10
3  6  9  12 15
4  8  12 16 20
5  10 15 20 25
```

Again, you don't need to worry about the spacing between columns.

Hint: You'll need two loops, one nested in the other

## Objects & Classes

### Guessing Game
Create a `GuessingGame` constructor function which is initialized with an
integer called `answer`.

Define an instance method `guess` which takes an integer called `guess`
as its input. `guess` should return the string `'high'` if the `guess` is
larger than the `answer`, `'correct'` if the `guess` is equal to the `answer`,
and `'low'` if the `guess` is lower than the `answer`.

Define an instance method `isSolved` which returns `true` if the
most recent `guess` was correct and `false` otherwise.

For example:

```javascript
var game = new GuessingGame(10);

game.isSolved();   // => false

game.guess(5);     // => 'low'
game.guess(20);    // => 'high'
game.isSolved();   // => false

game.guess(10);    // => 'correct'
game.isSolved()    // => true
```
