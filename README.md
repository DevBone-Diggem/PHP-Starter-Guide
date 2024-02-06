# PHP Starters Syntax Guide

## Comments

Comments are very useful, they are like notes. Comments don't change the code at all, but they allow you to add descriptions of what the code does and communicate with other programmers working on the same code. You will see a few of them throughout this guide. There are a few ways to comment out lines, here are some examples:

```
// This is a comment

# This is also a comment

/*
    This is a multi-line comment
    Notice how all 3 lines are commented out in this example?
    Anything inside the comment container will be commented out
*/    
```

## Variables

Variables are used for data storage and usage. Variables are a key part of PHP and they are used frequently throughout the vast majority of PHP applications and programs. Declaring a variable is simple, you give it a name and a value. In PHP, variables are identified by a dollar sign "$" at the start. They can also contain different data types. Here are some examples:

```
$language = "php"; // String
$section = 2; // Integer
$phpVariablesAreCaseSensitive = true; // Boolean
```

Semicolons are a must in PHP, they indicate the end of a statement. IE: when your line of code ends. If you miss a semicolon, your entire program will not work.

PHP Variables are scoped globally and locally:
```
$global = "This is a global variable";

function localVarExample() {
    $local = "This is a local variable"; // and it is only defined within this function, if you call $local outside of the function, it will be undefined. 
}
```

## Echo/Print

Echo and Print are used to display/output data to the browser. 
Echo can take multiple parameters and does not have a return value:
```
echo "hello world!";
echo "hello ", "world!"; // both of these would display to your screen the same, but one uses multiple parameters.
```

Print can only take one parameter, and has a return value of 1, so it can be used in expressions as echo cannot.
```
print "hello world!";
```

echo has better performance, but print has uses that echo does not.

## Data Types

Data types are used for declaring different kinds of values, some of the most common data types are:

- Strings: A string of text. example: "words" 
- Integers: A number. example: 3
- Floats: A number with a decimal. example: 3.33
- Arrays: A variable that stores multiple values. example: `$food = array("Pasta", "Sandwich", "Rice")` 
- Booleans: True and False.
- Nulls: Represents no value

## Strings

Strings are lines of text. You can call them by surrounding them with quotation marks:

```
echo "string!";
echo 'string again!';
```

The difference between double quotes and single quotes is that double quotes act on special characters, for example, they can recognize a variable:

```
$example = "water";
echo "blue $example"; // this will print out "blue water". If I used single quotes, it would print out "blue $example", because it does not recognize I am calling a variable, it recognizes a dollar sign as a character, and then some text after it.
```

## Numbers

PHP has a few different ways it recognizes numbers. As we went over earlier, integers and floats are two different types. Here is a list of number recognition data types:

- Integers: A number. example: 10
- Floats: A number with a decimal. example 10.10
- Number Strings: Numbers within strings, PHP can recognize these using `is_numeric()` and will return true or false.
- Infinity: Any number with a value that is higher than the `PHP_FLOAT_MAX` is seen by PHP as infinite. PHP can recognize these using `is_finite()` and `is_infinite()`
- NaN: This means not a number. You guessed it, use `is_nan()` to check.

## Constants

Constants are variables that cannot be redefined, once they're defined that's that.
A constant is defined by using "const", or "define" with name, value, and case-sensitive declarations:
```
define("fruit", "Orange", true); 
// This would define the "fruit" constant as "Orange" and case insensitive. 
// Case sensitive is default, this is saying true to the constant being case insensitive. If you leave it blank and only declare the name and value, it will default to case sensitive.

const fruit = "Strawberry";
```

## Operators

Operators are used for operations in your code. There are many operators, here are some arithmetic ones:

| Operator | Description    | 
|----------|----------------|
| +        | Addition       |
| -        | Subtraction    |
| *        | Multiplication |
| /        | Division       |

And here are some comparison operators:

| Operator | Description              | 
|----------|--------------------------|
| ==       | Equal to                 |
| ===      | Identical to             |
| !=       | Not equal to             |
| !==      | Not identical to         |
| >        | Greater than             |
| <        | Less than                |
| >=       | Greater than or equal to |
| <=       | Less than or equal to    |

## If & Else & Elseif

if, else, and elseif statements are used to execute actions under certain conditions. if statements execute if the conditions are met, else is what executes if they aren't, and elseif is used for multiple conditions:

```
$queueTime = 5; // Let's say you are in a queue waiting for something, whether it be a customer service call, or a video game, or something else. 

if ($queueTime <= 10) {
    echo "Almost done!";
} 
// Since our "queueTime" variable is less than or equal to 10, our statement will execute. If it was bigger than 10, it would not.


if ($queueTime <= 10) {
    echo "Almost done!";
} else {
    echo "You've got a while to wait yet.";
}
// If "queueTime" was over 10, the else statement would execute instead. In the previous statement, if "queueTime" was over 10, nothing would happen.


if ($queueTime <= 10) {
    echo "Almost done!";
} elseif ($queueTime >= 20) {
    echo "It's going to be a very long wait.";
} else {
    echo "You've got a little longer to wait.";
}
// Now if queue time is greater than or equal to 20, our elseif statment will execute. This means that the else statement will only execute if the queue time is 11-19 minutes.
```

## Functions

PHP has a massive library of built-in functions. There are thousands, way too many to list here, they can be called very easily by entering the name of the function, and that's it. Let's have a look at how to make our own function:

```
function example() {
    echo "I am from a function!";
}

example();
// The "example" function is called here, this will print the message to the screen.
```

Functions are capable of doing many different things, this is a simple example. 

## Arrays

Arrays are variables that store multiple values, they are defined very similarly to variables, but with a couple slight changes:

```
$pets = array("Dog", "Cat", "Bird");
// Can you see the differences? An array is put in front of the values, and of course multiple values separated by comas are assigned instead of just one.
```

You can store many different data types in arrays, these include string values, integers, objects, and even functions:

```
$dataTypeParty = array("String", 23, ["Object", "Data"], exampleFunction);
```

When working with arrays, keep in mind that they start at 0:

```
$pets = array("Dog", "Cat", "Bird");

echo = $pets[1];
// Since the count starts at 0, this will print "Cat" to the browser.
```

## Loops

A loop is used to loop through a function and execute an action a multitude of times.
there are multiple types of loops, let's start with a while loop. A while loop executes its function until the specified parameter is no longer true.

```
$i = 0;

while ($i < 20) {
    echo "Hello world! <br>"; // <br> = line break in HTML
    $i++;
}
```

An easy way to understand this is by writing it out, this loop says "While i is less than 20, print "hello world!" to the browser, then increase i by 1". Since i is originally declared as 0, this loop will log "hello world!" to the console 20 times as it is not less than or equal to.

For loops are similar to while loops, but their parameters are different. A variable is declared within them, and so is the incremental increase of said variable. Lets make a for loop that functions identically to the above while loop to really see the differences:

```
for ($i = 0; $i < 20; $i++) {
    echo "Hello world! <br>";
}
```

