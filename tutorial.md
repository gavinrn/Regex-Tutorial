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

An Anchor is essentially a way to find information from the **start-of-the-line** or the **end-of-the-line**. Here is a list of names stored in a string template literal.
```
let string = `
Marry Jane
John Doe
Jane Doe
John Smith
Jane Smith
John Wayne
Jane Wayne
John Lennon
Jane Lennon
`;
```
I want to know how many People are in the Smith family, and I want to know how many people have the first name John in this list. How would I go about getting that information?
```
let regex = /Smith$/gm;
```
Voilà, I have created a regular expression *"filter"* that looks for a line that ends with **Smith** our given last name that I am looking for. 
```
let result = string.match(regex);
console.log(result); // returns [ 'Smith', 'Smith' ]
```
I have now figured out that there are two Smiths in the list. Now I will try and find out how many Johns there are on the list 
```
let RegExp = /^John/gm;
```
Creating my regular expression *"filter"*
```
let result2 = string.match(RegExp); // Match the fitler against the string
console.log(result2); // return [ 'John', 'John', 'John', 'John' ]
```
I have now determined that there are 4 Johns inside the given string list.

The key takeaway here being that the ```^``` and ```$``` starting and stoping symbols respectively, you can search large sets of string and filter out words that can begin or end with a given pattern. 


### Quantifiers
Generally speaking, when you are talking about quantifers you are refering to the quantity of preceding charecters with respect to the pattern. A little unintuitive admitingly, but if you were to for example want to measure the *number* of charecters in a string you would use a quantifier. 
```
const  = "REEE REEEEEEEEEEEE REE REEEEE EEEE";
const RegExp = /RE{4,}/g; // Notice how I didn't enclose the *RE* in parenthese because we're only measuring the E
console.log(scream.match(RegExp)); // Returns [ 'REEEEEEEEEEEE', 'REEEEE' ]
```
An interesting point is that given the string and the RegExp, it check for a R and 4 OR MORE E's. The {4,} (I'll call it the 4 or more Quantifier) is an example of how you would go about trying to find duplicate charecters for a given array. However there are several more quantifiers, the ```*``` matches zero or more occurences of a charecter, the ```+``` matches one or more. 

The keytakeaway here is being that quantifiers are used to find information related to quantities of charecters preceeding a given pattern.

### OR Operator
The OR operator is similiar to javascript native or operator, but applied to this context of regular expressions. For example
```
let string = `
Marry Jane
John Doe
Jane Doe
John Smith
Jane Smith
John Wayne
Jane Wayne
John Lennon
Jane Lennon
`;
```
Here we have our familiar list of names, previously we had to separate the regular expression to find both the names that start with John and end with Smith. Howerver using the OR Operator we now have the power to combine our filter into one regular expression
```
let regex = /^John|Smith$/gm;
```
We keep the Anchor syntax the same howerver we let compiler know we want names that start with John OR names that end with Smith 
```
let result = string.match(regex);
console.log(result); // returns [ 'John', 'John', 'Smith', 'Smith', 'John', 'John' ]
```
The OR operator by itself is a bit underwhelming, but when combined with other operators like the example above, it can provide limitless possibilities to express the kind of information you are looking for.

### Character Classes
Here is where things can get a little confusing. Charecter Classes are used to match charecters from a provided set. The syntax is ```[]``` closed brackets. 
```
let regex = /[aeiou]/g;
let string = "The quick brown fox jumps over the lazy dog"

result = string.match(regex);
console.log(result); // returns all the vowels in the string
```
### Flags
I've been using flags the whole time but here is the demo. There are a few different types of flags but the most common ones are the ones I have used already. the ```g``` flag means global, 
meaning that scan the entire string. There has also been another one the ```m``` flag which mean multi line.
```
let string = `
Marry Jane
John Doe
Jane Doe
John Smith
Jane Smith
John Wayne
Jane Wayne
John Lennon
Jane Lennon
`;
let regex = /Smith$/gm;
```
In this previous example we were trying to find how many people had the last name Smith, but in order to fufil that requirement, I had to use two flags both ```g``` and ```m```. 
I stated that I want you to search **globaly** for the Smith last name, and I want you to check **every line**. 
There is also the ```i``` flag which basically makes it so that the regular expression is case-insensitive. There are more flags but these are the most common ones.

### Grouping and Capturing
When talking about Grouping and Capturing it is refering to specific parts of a pattern. The syntax for grouping and capturing is ```()``` parentheses.
```
let regex = /(\d{3})-(\d{3})-(\d{4})/; // Phone number format 000-000-0000
```
Ok that's a lot, let disect it. The first part of the code is is just the declaration ```/ /``` then we move on to our first part ```\d{3}```. ```\d``` is refering to a digit. 
So we are telling the compiler that we want a digit, the ```{3}``` is a quantifier, meaning that we want 3 digits and only 3 digits. 
Then there is a dash in the code, followed by a second grouping of 3 digits, a dash, and then a grouping of 4 digits, represeting the format of a phone number.

### Bracket Expressions
Here is where things can get a little confusing. Charecter Classes are also commonly refered to as Bracket Expressions. The syntax is ```[]``` closed brackets. Let's use a slighty differnt version of the previous charecter class example.
```
let regex = /[^aeiou]/g;
let string = "The quick brown fox jumps over the lazy dog"

result = string.match(regex);
console.log(result); // returns all the charecters that are not vowels in the string
```
As you can see the syntax and concept is basically the same, however you can also use the ```^``` char inside of the bracket do indicate that you don't want the following charecters in your regular expression.
### Greedy and Lazy Match
Greedy and Lazy Match are both terms used to the methods in which the information from regular expressions is being handeled. 
The most common way is Greedy, meaning that you are trying to find the most matches as possible given the circumstances provided in your regular expression. 
The symbols associated with these styles of regular expressions are commonly denoted as ```+``` meaning greedy and ```?``` meaning lazy. 
You could write an expression like ```/A\d.+/``` which would mean that your regular expression is going to find a capital A and any length of numbers preceeding it, and return all the numbers regardless of the length, hence it being greedy. 
However if you were to write ```/A\d.+?/``` it is looking for a lazy way to do things, so it will return the absolute minimum. 
It will return a capital A, a digit, and any char. Those are the only requirements hence they are lazy. 

### Boundaries
Generally boudaries are just to specify what you are looking for in regular expressions. An example of of boudary in a regular expression would be ```/\bthe\b/``` meaning that we set a boundary on the. It is the most specific type of boundary as it will only return the no acceptions. While a more lose type of boundary would be the captial B ```/\Bthe\b/``` meaning that it would return someting like "other" because it contain the word the inside of it. 

### Back-references
Back referencing basically means you are checking for patterns inside of the given regular expression. For example, if you are checking for a repeating numbers
```
const regex = /(\d{3})-(\d{3})-\1/;
const str1 = '123-134-123';
const str2 = '543-765-322';

console.log(regex.test(str1)); // true
console.log(regex.test(str2)); // false
```
You could use a back reference to check if the expression that was just referenced shows up again

### Look-ahead and Look-behind
This is probably the most advanced regex expression, it is basically when you take a regular expression,
then looks ahead or behind for another given regular expression, and given the expression could be tasked at either looking if something is there, 
or if something is not there. Here is an example 
```
/Note(?=Book)/
```
This regular expression is only going to look for Note if it is imediately followed by *book*. There are 4 different version of the look-ahead or look-behind. 
There is a look-ahead positive and negative, meaning that you can look for things that are there or not there, 
hence they are postive and negative, the same applies for looking behind. 

## Author

Hello I'm Gavin and this is my Javascript Regular Expression tutorial, 
I hope you found it to be somewhat helpful. Here is my github [gavinrn](www.github.com/gavinrn)
