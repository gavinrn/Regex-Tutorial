# Regular Expression Tutorial

Hi my name is Gavin and this is my regular expression tutorial. What is a regular expression? Essentialy it is a filter that is imposed on a given string or dataset to find information. 

## Summary

For these examples we will be using the Javascript programming languages, howerver the concpet of regular expressions is not limited to javascript. In fact, lanagues such as Perl, Python, Ruby, Java, .NET, and many more languages have their forms of regular expressions. 

**An example of a regular expression**
```
let pattern = /hello/g;
let str = "hello world hello";
let matches = str.match(pattern);
console.log(matches); // prints ["hello", "hello"] to the console.
```
The pattern we are searching for is *hello*.
 The deffinition of the regular expression is */hello/*.
 The **g** is a modifier that says check for the pattern globally.

Every Regualr expression in javascript follows this syntax **/pattern/modifier(s);**


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

When you think of an anchor, you think of a big hunk of metal that helps the ship *stop*, once the ship is in place. Anchors in the context of regular expressions are similar. 
```
let pattern = /^anchor/gm;
let str = `water
water
water
anchorHere
dontanchor`;
let matches = str.match(pattern);
let index = str.search(pattern);
console.log(index); // 18
console.log(matches); // [ 'anchor' ] note that we are using a templete literal not a string
```

Using the ```^``` and ```$``` starting and stoping symbols respectively, you can search large sets of string and filter out words that can begin or end with a given patern. 


### Quantifiers
Generally speaking, when you are talking about quantifers you are refering to the quantity of preceding charecters with respect to the pattern. A little unintuitive admitingly, but if you were to for example want to measure the *number* of charecters in a string you would use a quantifier. 
```
const  = "REEE REEEEEEEEEEEE REE REEEEE EEEE";
const RegExp = /RE{4,}/g; // Notice how I didn't enclose the *RE* in parenthese because we're only measuring the E
console.log(scream.match(RegExp)); // Returns [ 'REEEEEEEEEEEE', 'REEEEE' ]
```
An interesting point is that given the string and the RegExp, it check for a R and 4 OR MORE E's. The {4,} (I'll call it the 4 or more Quantifier) is an example of how you would go about trying to find duplicate charecters for a given array. 

### OR Operator


### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
