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
The pattern we are searching for is *hello*
The deffinition of the regular expression is */hello/*
The **g** is a modifier that says check for the pattern globally

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


### Quantifiers

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
