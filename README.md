# Review: Arrays

## Learning Goals

- Review `Array`s and how to work with them
- Review `Array` methods

## Introduction

A 1-2 sentence summary of what will be covered.

## Review of Arrays

Array is a type of data structure - a way to store pieces of data that are
related in some way. Can then refer to the collection as a whole

examples

const firstDwarf = "Happy"; const secondDwarf = "Sleepy"; const thirdDwarf =
"Sneezy": ...

Arrays are also _ordered_: the array [1 2, 3] is not the same as the array [3,
1, 2]

Array elements can be of any data type: primitive types like strings or numbers,
or data structures, including arrays. When an array has another array stored
inside it, we refer to that as a _nested_ array.

example

Furthermore, while some languages do not allow arrays to contain elements of
different types, JavaScript has no such restriction. The following is valid in
JavaScript:

`const mixedArray = ["one", 2, ["three", 4], 6.0, {lastNumber: "seven"}]`;

It is difficult to imagine when an array like this would be useful, however, and
working with arrays like this could get confusing. In general, it's best to keep
your arrays simpler!

## Accessing and Updating Elements

To access an element in an array, we use bracket notation:

`myArray[index]`

The `index` indicates the position of the element we want to access. Remember:
arrays are indexed starting with 0, not 1, so the first element of an array is
accessed using `myArray[0]`, the second `myArray[1]`, and so forth. If `myArray`
has 5 elements, we can access the last element using `myArray[4]`. If we don't
happen to know the length of the array - or if its length might change - we can
get the last element using the `.length` property: myArray[myArray.length - 1].

To update the value of an element, we simply access the desired element using
bracket notation and then _assign_ that element to a new value:

`myArray[3] = "new value";`

## Array Methods

Need to wait to see what the array methods material looks like in Phase 0 before
writing this

| Method         | What it does                         | Arguments  | Destructive? | Return value                                |
| -------------- | ------------------------------------ | ---------- | ------------ | ------------------------------------------- |
| [.push()][]    | Add element(s) to end of array       | 1 or more  | Yes          | The length of the modified array            |
| [.unshift()][] | Add element(s) to beginning of array | 1 or more  | Yes          | The length of the modified array            |
| [.pop()][]     | Remove last element                  | 0          | Yes          | The removed element                         |
| [.shift()][]   | Remove first element                 | 0          | Yes          | The removed element                         |
| [.slice()][]   | Remove 0 or more elements            | 0, 1, or 2 | No           | A new array containing the removed elements |
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

## Conclusion

A short one or two paragraph summary of the contents of the lessons, recapping
the learning goals.

## Resources

- [MDN Arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
- [Resource Link 2](example.com)
