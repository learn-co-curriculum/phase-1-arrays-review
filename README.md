# Review: Arrays

## Learning Goals

- Review `Array`s and how to work with them
- Review some of JavaScript's `Array` methods

## Introduction

In this lesson, we will briefly review JavaScript arrays, including what they
are and how to access and update elements. We will also discuss some built-in
JavaScript methods that help us interact with and modify arrays.

## Review of Arrays

An array is a type of data structure that enables you to store multiple pieces
of data that are related to each other. It allows us to refer to that collection
as a whole, rather than item by item. For example, while we could store each of
the seven dwarves in a separate variable, it makes more sense to store them in
an array:

```js
const dwarves = [ "Happy", "Sleepy", "Sneezy", "Grumpy", "Bashful", "Dopey", "Doc" ];
```

Using an array makes it possible to refer to the dwarves collectively, using the
variable name, and also reflects the fact that the elements go together, that
they are a set.

Arrays are also _ordered_: the array `[1 2, 3]` is not the same as the array
`[3, 1, 2]`. While the elements in our `dwarves` array don't have any obvious
inherent order (age? length of beard?), we can imagine other collections that
do, for example, the months of the year or the elements in the periodic table.

Array elements can be of any data type: primitive types like strings or numbers,
or data structures, including arrays. When an array has another array stored
inside it, we refer to that as a _nested_ array.

```js
const nestedArray = [1, 2, [3, 4], 5];
```

This array has _four_ elements: `1`, `2`, `[3, 4]` and `5`. The third element is
an array that has 2 elements.

While there is no limit to the amount of nesting an array can contain, they can
get to be very difficult to work with very quickly, so a good guideline is to
try to avoid nesting arrays more than one level deep.

Some languages do not allow arrays to contain elements of different types, but
JavaScript has no such restriction. The following is valid in JavaScript:

```js
const mixedArray = ["one", 2, ["three", 4], 6.0, { lastNumber: "seven" }];
```

It is difficult to imagine when an array like this would be useful, however, and
working with arrays like this could get confusing. In general, it's best to keep
your arrays simpler!

## Accessing and Updating Elements

To access an element in an array, we use bracket notation: `myArray[index]`. The
`index` indicates the position of the element we want to access.

Remember: arrays are indexed starting with 0, not 1, so the first element of an
array is accessed using `myArray[0]`, the second `myArray[1]`, and so forth. If
`myArray` has 5 elements, we access the last element using `myArray[4]`.

If we don't happen to know the length of the array - or if its length might
change - we can get the last element dynamically using the `.length` property:
`myArray[myArray.length - 1]`.

To update the value of an element, we simply access the desired element using
bracket notation and then _assign_ a new value to it:

`myArray[3] = "new value";`

## Array Methods

The table below shows information about JavaScript array methods that can be
used to modify arrays. These methods were covered in detail in [Software
Engineering Prep][array-methods]. You can review that lesson or use the MDN
documentation for the methods, linked below, to refresh your memory about how to
use each of them.

[array-methods]:
  https://github.com/learn-co-curriculum/phase-0-intro-to-js-2-array-methods

| Method         | What it does                         | Arguments  | Destructive? | Return value                                |
| -------------- | ------------------------------------ | ---------- | ------------ | ------------------------------------------- |
| [.push()][]    | Add element(s) to end of array       | 1 or more  | Yes          | The length of the modified array            |
| [.unshift()][] | Add element(s) to beginning of array | 1 or more  | Yes          | The length of the modified array            |
| [.pop()][]     | Remove last element                  | 0          | Yes          | The removed element                         |
| [.shift()][]   | Remove first element                 | 0          | Yes          | The removed element                         |
| [.slice()][]   | Return a subset of the elements      | 0, 1, or 2 | No           | A new array containing the sliced elements  |
| [.splice()][]  | Remove, add or replace elements      | 1 or more  | Yes          | A new array containing the removed elements |

[.push()]:
  https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push
[.unshift()]:
  https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift
[.pop()]:
  https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop
[.shift()]:
  https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift
[.slice()]:
  https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice
[.splice()]:
  https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice

If you check out the [MDN Array documentation][MDN Arrays], you'll see the full
list of Array methods that are built into JavaScript on the left. Included in
the list are the methods above, a number of _iterator methods_ that we'll learn
about a bit later in this course, and quite a few more. We encourage you to
explore these methods to get a sense for what you can do with arrays. Below are
a few that we find particularly helpful.

### Array.prototype.includes()

This method checks whether the value passed as an argument is included in the
array and returns `true` or `false`:

```js
const nums = [1, 2, 3];
nums.includes(2);
// => true
```

### Array.prototype.join()

This method allows you to join the elements of an array into a string. If you
don't pass an argument, the method will separate the elements with commas by
default:

```js
const nums = [1, 2, 3];
nums.join();
// => "1,2,3"
```

Optionally, you can pass a separator as an argument; the separator must be a
string value:

```js
nums.join(" ");
// => "1 2 3"
```

### Array.prototype.reverse()

As you might except, `reverse()` reverses the order of the elements in the
array:

```js
const nums = [1, 2, 3];
nums.reverse();
// => [3, 2, 1]
```

**Note**: The `reverse()` method modifies the array _in place_, i.e., it is
destructive. If you want to preserve the original array, you will need to create
a new variable to contain the reversed array:

```js
const nums = [1, 2, 3];
const reversedNums = nums.reverse();
console.log(reversedNums);
// => [3, 2, 1]
```

### Array.prototype.concat()

This method enables you to combine two or more arrays into one. The method is
called on one array, and the array or arrays to be added are passed as
arguments:

```js
const nums = [1, 2, 3];
const moreNums = [4, 5, 6];
const combinedNums = nums.concat(moreNums);
console.log(combinedNums);
// => [1, 2, 3, 4, 5, 6]
```

Note that the `concat` method creates a new array so if we want to retain a
reference to it, we need to assign it to a variable.

## Conclusion

In this lesson, we've reviewed what arrays are and how to access and manipulate
their contents. We've also reviewed some of the array methods that can be used
to modify arrays. In the next lesson, we will learn about another very powerful
tool we can use to manipulate arrays: the spread operator.

## Resources

- [MDN Arrays][]

[MDN Arrays]:
  (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
