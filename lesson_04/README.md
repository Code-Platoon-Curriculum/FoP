# JavaScript Crash Course for Python Developers

## Table of Contents
1. [Getting Started](#getting-started)
2. [Output and Display](#output-and-display)
3. [Variables and Assignment](#variables-and-assignment)
4. [Data Types](#data-types)
5. [Input and User Interaction](#input-and-user-interaction)
6. [String Operations](#string-operations)
7. [Type Casting and Conversion](#type-casting-and-conversion)
8. [Data Structures](#data-structures)
9. [Control Flow](#control-flow)
10. [Functions](#functions)
11. [Key Differences Summary](#key-differences-summary)

## Getting Started

### Running Code

**Python:**
```python
# Run in terminal: python filename.py
# Or in interactive shell: python
print("Hello World")
```

**JavaScript:**
```javascript
// Run in browser console, Node.js, or HTML file
// In browser: F12 → Console tab
// In Node.js: node filename.js
console.log("Hello World");
```

**Key Difference:** JavaScript can run in browsers (client-side) or Node.js (server-side), while Python typically runs server-side or in desktop applications.

## Output and Display

### Basic Output

**Python:**
```python
print("Hello World")
print("Name:", "Alice", "Age:", 25)
print("Score:", 95, sep=" - ")
```

**JavaScript:**
```javascript
console.log("Hello World");
console.log("Name:", "Alice", "Age:", 25);
// JavaScript automatically adds spaces between arguments
```

**Key Differences:**
- Python: `print()` function
- JavaScript: `console.log()` function
- JavaScript doesn't have a direct equivalent to Python's `sep` parameter

### Formatted Output

**Python:**
```python
name = "Alice"
age = 25
print(f"My name is {name} and I'm {age} years old")
print("My name is {} and I'm {} years old".format(name, age))
```

**JavaScript:**
```javascript
let name = "Alice";
let age = 25;
console.log(`My name is ${name} and I'm ${age} years old`); // Template literals
console.log("My name is " + name + " and I'm " + age + " years old"); // Concatenation
```

**Key Differences:**
- Python: f-strings `f"text {variable}"` or `.format()`
- JavaScript: Template literals `\`text ${variable}\`` (note the backticks!)

## Variables and Assignment

### Basic Assignment

**Python:**
```python
# Snake_case convention
user_name = "Alice"
user_age = 25
is_student = True
```

**JavaScript:**
```javascript
// camelCase convention
let userName = "Alice";    // Block-scoped, can be reassigned
const userAge = 25;        // Block-scoped, cannot be reassigned
var isStudent = true;      // Function-scoped (avoid in modern JS)
```

**Key Differences:**
- Python: No declaration keywords needed
- JavaScript: Use `let` (mutable) or `const` (immutable)
- Python: snake_case naming
- JavaScript: camelCase naming

### Variable Scope

**Python:**
```python
def my_function():
    local_var = "I'm local"
    global global_var
    global_var = "I'm global"

global_var = "Original"
```

**JavaScript:**
```javascript
function myFunction() {
    let localVar = "I'm local";        // Block scope
    const anotherLocal = "Also local"; // Block scope
}

let globalVar = "I'm global";  // Global scope
const CONSTANT = "I never change";
```

## Data Types

### Basic Types

**Python:**
```python
# Numbers
integer_num = 42
float_num = 3.14

# Strings
text = "Hello"
multiline = """This is
a multiline
string"""

# Boolean
is_true = True
is_false = False

# None
nothing = None

# Check type
print(type(integer_num))  # <class 'int'>
```

**JavaScript:**
```javascript
// Numbers (all numbers are floating point)
let integerNum = 42;
let floatNum = 3.14;

// Strings
let text = "Hello";
let multiline = `This is
a multiline
string`;

// Boolean
let isTrue = true;
let isFalse = false;

// Undefined and Null
let nothing = null;
let notDefined = undefined;

// Check type
console.log(typeof integerNum);  // "number"
```

**Key Differences:**
- Python: Separate `int` and `float` types
- JavaScript: Only one `number` type
- Python: `True`/`False`/`None` (capitalized)
- JavaScript: `true`/`false`/`null`/`undefined` (lowercase)
- JavaScript has both `null` and `undefined`

## Input and User Interaction

### Getting User Input

**Python:**
```python
name = input("Enter your name: ")
age = input("Enter your age: ")
age = int(age)  # Convert string to integer
```

**JavaScript (Browser):**
```javascript
let name = prompt("Enter your name:");
let age = prompt("Enter your age:");
age = parseInt(age);  // Convert string to integer
```

**JavaScript (Node.js):**
```javascript
const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

rl.question('Enter your name: ', (name) => {
    rl.question('Enter your age: ', (age) => {
        age = parseInt(age);
        console.log(`Hello ${name}, you are ${age} years old`);
        rl.close();
    });
});
```

**Key Differences:**
- Python: `input()` always returns a string
- JavaScript: Browser uses `prompt()`, Node.js requires readline module
- JavaScript input handling is more complex, especially in Node.js

## String Operations

### String Manipulation

**Python:**
```python
text = "Hello World"
print(text.lower())           # hello world
print(text.upper())           # HELLO WORLD
print(text.replace("World", "Python"))  # Hello Python
print(len(text))              # 11
print(text[0])                # H
print(text[-1])               # d
print(text[0:5])              # Hello
```

**JavaScript:**
```javascript
let text = "Hello World";
console.log(text.toLowerCase());     // hello world
console.log(text.toUpperCase());     // HELLO WORLD
console.log(text.replace("World", "JavaScript")); // Hello JavaScript
console.log(text.length);            // 11
console.log(text[0]);                // H
console.log(text[text.length - 1]);  // d (no negative indexing)
console.log(text.substring(0, 5));   // Hello
console.log(text.slice(0, 5));       // Hello
```

### String Concatenation

**Python:**
```python
first = "Hello"
second = "World"
result = first + " " + second
result = f"{first} {second}"
result = " ".join([first, second])
```

**JavaScript:**
```javascript
let first = "Hello";
let second = "World";
let result = first + " " + second;
result = `${first} ${second}`;       // Template literals
result = [first, second].join(" ");  // Array join
```

**Key Differences:**
- Python: Negative indexing supported (`text[-1]`)
- JavaScript: No negative indexing, use `text.length - 1`
- Python: `len()` function
- JavaScript: `.length` property

## Type Casting and Conversion

### Converting Between Types

**Python:**
```python
# String to number
num_str = "42"
num = int(num_str)
float_num = float("3.14")

# Number to string
num = 42
str_num = str(num)

# Boolean conversion
bool_val = bool(1)    # True
bool_val = bool("")   # False
```

**JavaScript:**
```javascript
// String to number
let numStr = "42";
let num = parseInt(numStr);
let floatNum = parseFloat("3.14");
let num2 = Number("42");  // Alternative method

// Number to string
let num = 42;
let strNum = num.toString();
let strNum2 = String(num);

// Boolean conversion
let boolVal = Boolean(1);     // true
let boolVal2 = Boolean("");   // false
let boolVal3 = !!"text";      // true (double negation trick)
```

**Key Differences:**
- Python: `int()`, `float()`, `str()`, `bool()`
- JavaScript: `parseInt()`, `parseFloat()`, `Number()`, `String()`, `Boolean()`
- JavaScript has more conversion methods and automatic type coercion

## Data Structures

### Lists/Arrays

**Python:**
```python
# Lists
fruits = ["apple", "banana", "orange"]
fruits.append("grape")
fruits.insert(1, "kiwi")
fruits.remove("banana")
print(len(fruits))
print(fruits[0])

# List comprehension
squares = [x**2 for x in range(5)]
```

**JavaScript:**
```javascript
// Arrays
let fruits = ["apple", "banana", "orange"];
fruits.push("grape");           // Add to end
fruits.unshift("kiwi");         // Add to beginning
fruits.splice(1, 1);            // Remove 1 item at index 1
console.log(fruits.length);
console.log(fruits[0]);

// Array methods
let squares = Array.from({length: 5}, (_, i) => i * i);
// Or using map
let squares2 = [0, 1, 2, 3, 4].map(x => x * x);
```

### Dictionaries/Objects

**Python:**
```python
# Dictionary
person = {
    "name": "Alice",
    "age": 25,
    "city": "New York"
}

person["email"] = "alice@email.com"
print(person["name"])
print(person.get("phone", "Not available"))

# Dictionary methods
print(person.keys())
print(person.values())
```

**JavaScript:**
```javascript
// Objects
let person = {
    name: "Alice",
    age: 25,
    city: "New York"
};

person.email = "alice@email.com";  // Dot notation
person["phone"] = "123-456-7890";  // Bracket notation
console.log(person.name);
console.log(person.phone || "Not available");

// Object methods
console.log(Object.keys(person));
console.log(Object.values(person));
```

### Sets

**Python:**
```python
# Set
unique_nums = {1, 2, 3, 4, 4, 5}  # {1, 2, 3, 4, 5}
unique_nums.add(6)
unique_nums.remove(1)
print(len(unique_nums))
```

**JavaScript:**
```javascript
// Set
let uniqueNums = new Set([1, 2, 3, 4, 4, 5]);  // Set {1, 2, 3, 4, 5}
uniqueNums.add(6);
uniqueNums.delete(1);
console.log(uniqueNums.size);
```

**Key Differences:**
- Python: `list`, `dict`, `set` with various methods
- JavaScript: `Array`, `Object`, `Set` with different method names
- JavaScript arrays have different methods (`push`/`pop` vs `append`/`remove`)

## Control Flow

### Conditional Statements

**Python:**
```python
age = 18
if age >= 18:
    print("Adult")
elif age >= 13:
    print("Teenager")
else:
    print("Child")

# Ternary operator
status = "Adult" if age >= 18 else "Minor"
```

**JavaScript:**
```javascript
let age = 18;
if (age >= 18) {
    console.log("Adult");
} else if (age >= 13) {
    console.log("Teenager");
} else {
    console.log("Child");
}

// Ternary operator
let status = age >= 18 ? "Adult" : "Minor";
```

### Loops

**Python:**
```python
# For loop
for i in range(5):
    print(i)

# For loop with list
fruits = ["apple", "banana", "orange"]
for fruit in fruits:
    print(fruit)

# While loop
count = 0
while count < 5:
    print(count)
    count += 1
```

**JavaScript:**
```javascript
// For loop
for (let i = 0; i < 5; i++) {
    console.log(i);
}

// For...of loop (similar to Python's for...in)
let fruits = ["apple", "banana", "orange"];
for (let fruit of fruits) {
    console.log(fruit);
}

// While loop
let count = 0;
while (count < 5) {
    console.log(count);
    count++;
}
```

**Key Differences:**
- Python: `for item in iterable`, `range()` function
- JavaScript: C-style `for` loop, `for...of` for arrays
- JavaScript requires parentheses in conditionals and curly braces (mostly)

## Functions

### Basic Functions

**Python:**
```python
def greet(name, age=25):
    return f"Hello {name}, you are {age} years old"

def add_numbers(a, b):
    return a + b

result = greet("Alice")
sum_result = add_numbers(5, 3)
```

**JavaScript:**
```javascript
// Function declaration
function greet(name, age = 25) {
    return `Hello ${name}, you are ${age} years old`;
}

// Function expression
const addNumbers = function(a, b) {
    return a + b;
};

// Arrow function (ES6)
const multiply = (a, b) => a * b;
const square = x => x * x;  // Single parameter, no parentheses needed

let result = greet("Alice");
let sumResult = addNumbers(5, 3);
```

### Advanced Function Concepts

**Python:**
```python
# Lambda functions
square = lambda x: x * x
numbers = [1, 2, 3, 4, 5]
squared = list(map(square, numbers))

# List comprehension alternative
squared = [x * x for x in numbers]
```

**JavaScript:**
```javascript
// Arrow functions (similar to lambda)
const square = x => x * x;
let numbers = [1, 2, 3, 4, 5];
let squared = numbers.map(square);

// Or inline
let squared2 = numbers.map(x => x * x);

// Filter and reduce
let evens = numbers.filter(x => x % 2 === 0);
let sum = numbers.reduce((acc, x) => acc + x, 0);
```

**Key Differences:**
- Python: `def` keyword, `lambda` for anonymous functions
- JavaScript: Multiple ways to define functions (declaration, expression, arrow)
- JavaScript arrow functions are more concise than Python lambdas

## Key Differences Summary

### Syntax Differences
| Aspect | Python | JavaScript |
|--------|--------|------------|
| **Statement termination** | New line | Semicolon (optional but recommended) |
| **Code blocks** | Indentation | Curly braces `{}` |
| **Comments** | `# comment` | `// comment` or `/* comment */` |
| **Variable declaration** | `variable = value` | `let variable = value` |
| **String quotes** | `"text"` or `'text'` | `"text"` or `'text'` or `` `template` `` |

### Naming Conventions
| Type | Python | JavaScript |
|------|--------|------------|
| **Variables** | `snake_case` | `camelCase` |
| **Functions** | `snake_case` | `camelCase` |
| **Constants** | `UPPER_CASE` | `UPPER_CASE` or `camelCase` |
| **Classes** | `PascalCase` | `PascalCase` |

### Type System
| Aspect | Python | JavaScript |
|--------|--------|------------|
| **Type checking** | Dynamic, runtime | Dynamic, runtime |
| **Type conversion** | Explicit | Automatic + explicit |
| **Equality** | `==` and `is` | `==` (loose) and `===` (strict) |

### Common Gotchas for Python Developers

1. **Semicolons**: While optional, it's good practice to use them
2. **Curly Braces**: Always use `{}` for code blocks, even single statements
3. **Variable Declaration**: Always use `let` or `const`, avoid `var`
4. **Equality**: Use `===` instead of `==` to avoid type coercion surprises
5. **Array Indexing**: No negative indexing like Python
6. **Case Sensitivity**: JavaScript is case-sensitive (`True` vs `true`)

### Practice Exercises

Try converting these Python snippets to JavaScript:

1. **List Processing**:
```python
numbers = [1, 2, 3, 4, 5]
evens = [x for x in numbers if x % 2 == 0]
doubled = [x * 2 for x in evens]
print(doubled)
```

2. **Dictionary Manipulation**:
```python
students = [
    {"name": "Alice", "grade": 85},
    {"name": "Bob", "grade": 92},
    {"name": "Charlie", "grade": 78}
]

for student in students:
    if student["grade"] >= 80:
        print(f"{student['name']} passed with {student['grade']}")
```

3. **Function with Default Parameters**:
```python
def calculate_total(price, tax_rate=0.08, discount=0):
    discounted_price = price * (1 - discount)
    total = discounted_price * (1 + tax_rate)
    return round(total, 2)
```

This crash course covers the essential JavaScript concepts you need to get started. Remember that JavaScript's flexibility can be both powerful and confusing coming from Python, so stick to modern best practices (ES6+) and always use `let`/`const` for variable declarations!