# Flutter_Learning-Guide.

## Table of Contents

- [Introduction and Basics](#Introduction-and-basics)
- [Dart Pad Examples](#dart-pad-examples)
- [Built-in Types in Dart](#built-in-types-in-dart)
- [Functions in Dart](#functions-in-dart)
- [Operators in Dart](#operators-in-dart)
- [Control Flow Statements in Dart](#control-flow-statements-in-dart)
- [OOP in Dart](#oop-in-dart)
- [File Handling in Dart](#file-handling-in-dart)
- [Null Safety In Dart](#null-safety-in-dart)
- [Asynchronous Programming](#asynchronous-programming)
- [Useful Information](#useful-information)
  - [Final Vs Const](#final-vs-const)
  - [DateTime in Dart](#datetime-in-dart)
  - [Extension In Dart](#extension-in-dart)
  - [Backend in Dart](#backend-in-dart)
  - [Dart Interview Questions](#dart-interview-questions)



---

## 1. Introduction and Basics

### What is Dart?

Dart is a client-optimized, object-oriented, modern programming language to build apps fast for many platforms like android, iOS, web, desktop, etc. Client optimized means optimized for crafting a beautiful user interface and high-quality experiences. Google developed Dart as a programming language.

Currently, Dart is one of the most preferred languages to learn. A solid understanding of Dart is necessary to develop high-quality apps with flutter. According to Github, Dart is one of the most loved programming languages in the world.

This repository contains basic examples and concepts of Dart programming language and Flutter framework, suitable for beginners.

---

## Dart Pad Examples

### Example 1: Hello World Loop

```dart
void main() {
  for (var i = 0; i < 10; i++) {
    print('hello ${i + 1}');
  }
}
```

**Output:**

```
hello 1
hello 2
hello 3
hello 4
hello 5
hello 6
hello 7
hello 8
hello 9
hello 10
```

### Example 2: Simple Function

```dart
void greet(String name) {
  print('Hello, $name!');
}

void main() {
  greet('Alice');
}
```

**Output:**

```
Hello, Alice!
```

### Example 3: Class and Object

```dart
class Dog {
  String name;
  Dog(this.name);

  void bark() {
    print('$name says Woof!');
  }
}

void main() {
  var myDog = Dog('Buddy');
  myDog.bark();
}
```

**Output:**

```
Buddy says Woof!
```

### Example 4: Asynchronous Operations

```dart
import 'dart:async';

Future<void> fetchData() async {
  print('Fetching data...');
  await Future.delayed(Duration(seconds: 2));
  print('Data fetched!');
}

void main() {
  fetchData();
  print('Continuing execution...');
}
```

**Output:**

```
Fetching data...
Continuing execution...
Data fetched! (after 2 seconds)
```

### Example 5: Flutter Demo Home Page

```dart
import 'package:flutter/material.dart';

void main() => runApp(const MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      debugShowCheckedModeBanner: false,
      theme: ThemeData(colorSchemeSeed: Colors.blue),
      home: const MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  final String title;

  const MyHomePage({super.key, required this.title});

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text(widget.title)),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            const Text('You have pushed the button this many times:'),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: const Icon(Icons.add),
      ),
    );
  }
}
```

**Output:**

```
Flutter Demo Home page
You have pushed the button this many times
```

### Example 6: Basic Calculator using Functions

```dart
void main() {
  double add(double a, double b) => a + b;
  double subtract(double a, double b) => a - b;
  double multiply(double a, double b) => a * b;
  double divide(double a, double b) => a / b;

  print('Addition: ${add(10, 5)}');
  print('Subtraction: ${subtract(10, 5)}');
  print('Multiplication: ${multiply(10, 5)}');
  print('Division: ${divide(10, 5)}');
}
```

**Output:**

```
Addition: 15.0
Subtraction: 5.0
Multiplication: 50.0
Division: 2.0
```

### Example 7: List Manipulation

```dart
void main() {
  List<String> fruits = ['Apple', 'Banana'];
  fruits.add('Cherry');
  print('Fruits after add: $fruits');
  fruits.remove('Banana');
  print('Fruits after remove: $fruits');
  print('Contains Apple: ${fruits.contains('Apple')}');
  print('Number of fruits: ${fruits.length}');
}
```

**Output:**

```
Fruits after add: [Apple, Banana, Cherry]
Fruits after remove: [Apple, Cherry]
Contains Apple: true
Number of fruits: 2
```

### Example 8: Map Usage

```dart
void main() {
  Map<String, int> ages = {
    'Alice': 30,
    'Bob': 24,
  };
  print('Bob's age: ${ages['Bob']}');
  ages['Charlie'] = 35;
  print('All ages: $ages');
  ages.remove('Alice');
  print('Ages after removing Alice: $ages');
}
```

**Output:**

```
Bob's age: 24
All ages: {Alice: 30, Bob: 24, Charlie: 35}
Ages after removing Alice: {Bob: 24, Charlie: 35}
```

### Example 9: Exception Handling

```dart
void main() {
  try {
    int result = 10 ~/ 0; // Integer division by zero
    print(result);
  } catch (e) {
    print('Error: $e');
  } finally {
    print('Execution complete.');
  }
}
```

**Output:**

```
Error: IntegerDivisionByZeroException
Execution complete.
```

### Example 10: Extension Methods

```dart
extension StringExtension on String {
  String capitalize() {
    return "${this[0].toUpperCase()}${substring(1)}";
  }
}

void main() {
  String message = 'hello world';
  print(message.capitalize());
}
```

**Output:**

```
Hello world
```

---

## 2. Variables in Dart

Variables are used to store data in a program. In Dart, you can declare variables using `var`, `final`, `const`, or by explicitly specifying the data type.

### Example 1: String Variable

```dart
void main() {
  String greeting = 'Hello, World!';
  print(greeting);
}
```

**Output:**

```
Hello, World!
```

### Example 2: Integer Variable

```dart
void main() {
  int count = 100;
  print('Count: $count');
}
```

**Output:**

```
Count: 100
```

### Example 3: Double Variable

```dart
void main() {
  double pi = 3.14159;
  print('Value of Pi: $pi');
}
```

**Output:**

```
Value of Pi: 3.14159
```

### Example 4: Boolean Variable

```dart
void main() {
  bool isActive = true;
  print('Is active: $isActive');
}
```

**Output:**

```
Is active: true
```

### Example 5: Dynamic Variable

```dart
void main() {
  dynamic value = 'a string';
  print(value);
  value = 123;
  print(value);
}
```

**Output:**

```
a string
123
```

### Example 6: Implicitly Typed Variable (var)

```dart
void main() {
  var name = 'John Doe'; // Type inferred as String
  var age = 30; // Type inferred as int
  print('Name: $name, Age: $age');
}
```

**Output:**

```
Name: John Doe, Age: 30
```

### Example 7: Final Variable

```dart
void main() {
  final String message = 'This message cannot be changed.';
  // message = 'New message'; // This would cause a compile-time error
  print(message);
}
```

**Output:**

```
This message cannot be changed.
```

### Example 8: Const Variable

```dart
void main() {
  const int maxAttempts = 5;
  // maxAttempts = 10; // This would cause a compile-time error
  print('Maximum attempts: $maxAttempts');
}
```

**Output:**

```
Maximum attempts: 5
```

### Example 9: Late Variable

```dart
late String description;

void main() {
  description = 'A deferred initialized string.';
  print(description);
}
```

**Output:**

```
A deferred initialized string.
```

### Example 10: Nullable Variable

```dart
void main() {
  String? optionalName; // Can be null
  print('Optional Name: $optionalName');

  optionalName = 'Alice';
  print('Optional Name after assignment: $optionalName');
}
```

**Output:**

```
Optional Name: null
Optional Name after assignment: Alice
```

---

## 3. Built-in Types in Dart

Dart comes with a set of built-in types to handle various kinds of data.

### Example 1: Numbers (int and double)

```dart
void main() {
  int age = 30;
  double price = 19.99;
  print('Age: $age, Price: $price');
}
```

**Output:**

```
Age: 30, Price: 19.99
```

### Example 2: Strings

```dart
void main() {
  String greeting = 'Hello, Dart!';
  String message = """This is a multiline
string example.""";
  print(greeting);
  print(message);
}
```

**Output:**

```
Hello, Dart!
This is a multiline
string example.
```

### Example 3: Booleans

```dart
void main() {
  bool isDartFun = true;
  bool canDrive = false;
  print('Is Dart Fun? $isDartFun');
  print('Can drive? $canDrive');
}
```

**Output:**

```
Is Dart Fun? true
Can drive? false
```

### Example 4: Lists

```dart
void main() {
  List<String> fruits = ['Apple', 'Banana', 'Orange'];
  print('First fruit: ${fruits[0]}');
  print('All fruits: $fruits');
}
```

**Output:**

```
First fruit: Apple
All fruits: [Apple, Banana, Orange]
```

### Example 5: Maps

```dart
void main() {
  Map<String, String> capitals = {
    'USA': 'Washington D.C.',
    'India': 'New Delhi',
    'Japan': 'Tokyo',
  };
  print('Capital of USA: ${capitals['USA']}');
  capitals['Germany'] = 'Berlin';
  print('All capitals: $capitals');
}
```

**Output:**

```
Capital of USA: Washington D.C.
All capitals: {USA: Washington D.C., India: New Delhi, Japan: Tokyo, Germany: Berlin}
```

### Example 6: Runes (Unicode characters)

```dart
void main() {
  Runes input = Runes('\u{1f600} Hello');
  print(String.fromCharCodes(input));
}
```

**Output:**

```
😀 Hello
```

### Example 7: Symbols

```dart
void main() {
  Symbol s1 = #myFunction;
  Symbol s2 = #myFunction;
  print(s1 == s2);
  print(s1.runtimeType);
}
```

**Output:**

```
true
Symbol
```

### Example 8: Sets

```dart
void main() {
  Set<int> uniqueNumbers = {1, 2, 3, 2, 1};
  print('Unique numbers: $uniqueNumbers');
  uniqueNumbers.add(4);
  print('After adding 4: $uniqueNumbers');
  uniqueNumbers.remove(2);
  print('After removing 2: $uniqueNumbers');
}
```

**Output:**

```
Unique numbers: {1, 2, 3}
After adding 4: {1, 2, 3, 4}
After removing 2: {1, 3, 4}
```

### Example 9: Enumerated Types (Enums)

```dart
enum Status { none, running, stopped, paused }

void main() {
  Status currentStatus = Status.running;
  print('Current status: $currentStatus');
  print('Index of running: ${Status.values.indexOf(Status.running)}');
}
```

**Output:**

```
Current status: Status.running
Index of running: 1
```

### Example 10: Null (as a type)

```dart
void main() {
  int? nullableInt; // Declaring a nullable integer
  print('Nullable int: $nullableInt');

  nullableInt = 10;
  print('Nullable int after assignment: $nullableInt');

  // int nonNullableInt = null; // This would cause a compile-time error
}
```

**Output:**

```
Nullable int: null
Nullable int after assignment: 10
```

---

## 4. Functions in Dart

Functions are blocks of code that perform a specific task. They help organize code, make it reusable, and improve readability.

### Defining Functions:

Dart functions can be defined with or without return types and parameters.

### Example 1: Simple Function with Parameters

```dart
void greet(String name) {
  print('Hello, $name!');
}

void main() {
  greet('Alice');
}
```

**Output:**

```
Hello, Alice!
```

### Example 2: Function with Return Value

```dart
int add(int a, int b) {
  return a + b;
}

void main() {
  print('Sum: ${add(5, 3)}');
}
```

**Output:**

```
Sum: 8
```

### Example 3: Optional Positional Parameters

```dart
void sayHello(String name, [String? greeting]) {
  print('${greeting ?? 'Hello'}, $name!');
}

void main() {
  sayHello('Bob');
  sayHello('Charlie', 'Hi');
}
```

**Output:**

```
Hello, Bob!
Hi, Charlie!
```

### Example 4: Named Parameters

```dart
void describe({required String item, int quantity = 1}) {
  print('You have $quantity $item(s).');
}

void main() {
  describe(item: 'apple');
  describe(item: 'banana', quantity: 5);
}
```

**Output:**

```
You have 1 apple(s).
You have 5 banana(s).
```

### Example 5: Arrow Functions (Fat Arrow Syntax)

```dart
int multiply(int a, int b) => a * b;

void main() {
  print('Product: ${multiply(4, 2)}');
}
```

**Output:**

```
Product: 8
```

### Example 6: Anonymous Function (Lambda)

```dart
void main() {
  var fruits = ['apple', 'banana', 'cherry'];
  fruits.forEach((fruit) {
    print('I like $fruit');
  });
}
```

**Output:**

```
I like apple
I like banana
I like cherry
```

### Example 7: Function as a Parameter

```dart
void execute(Function callback) {
  callback();
}

void main() {
  execute(() => print('Function executed!'));
}
```

**Output:**

```
Function executed!
```

### Example 8: Lexical Closures

```dart
Function makeAdder(int addBy) {
  return (int a) => addBy + a;
}

void main() {
  var add2 = makeAdder(2);
  var add5 = makeAdder(5);
  print('2 + 3 = ${add2(3)}');
  print('5 + 7 = ${add5(7)}');
}
```

**Output:**

```
2 + 3 = 5
5 + 7 = 12
```

### Example 9: Generator Functions (Synchronous)

```dart
Iterable<int> count(int n) sync* {
  for (int i = 0; i < n; i++) {
    yield i; // yield a value
  }
}

void main() {
  for (var value in count(5)) {
    print(value);
  }
}
```

**Output:**

```
0
1
2
3
4
```

### Example 10: Generator Functions (Asynchronous)

```dart
Stream<int> countAsync(int n) async* {
  for (int i = 0; i < n; i++) {
    await Future.delayed(Duration(milliseconds: 100));
    yield i;
  }
}

void main() async {
  await for (var value in countAsync(3)) {
    print('Async value: $value');
  }
}
```

**Output:**

```
Async value: 0
Async value: 1
Async value: 2
```

---

## 5. Operators in Dart

Operators are special symbols that perform operations on one or more operands. Dart supports a variety of operators.

### Arithmetic Operators:
- `+` Addition
- `-` Subtraction
- `*` Multiplication
- `/` Division (returns double)
- `~/` Integer division (returns int)
- `%` Modulo (remainder)

### Example 1: Arithmetic Operators

```dart
void main() {
  int a = 10;
  int b = 3;
  print('a + b = ${a + b}');
  print('a - b = ${a - b}');
  print('a * b = ${a * b}');
  print('a / b = ${a / b}'); // Division results in a double
  print('a % b = ${a % b}'); // Remainder
  print('a ~/ b = ${a ~/ b}'); // Integer division
}
```

**Output:**

```
a + b = 13
a - b = 7
a * b = 30
a / b = 3.3333333333333335
a % b = 1
a ~/ b = 3
```

### Example 2: Equality and Relational Operators

```dart
void main() {
  int x = 5;
  int y = 10;
  print('x == y: ${x == y}');
  print('x != y: ${x != y}');
  print('x > y: ${x > y}');
  print('x < y: ${x < y}');
  print('x >= 5: ${x >= 5}');
  print('y <= 10: ${y <= 10}');
}
```

**Output:**

```
x == y: false
x != y: true
x > y: false
x < y: true
x >= 5: true
y <= 10: true
```

### Example 3: Type Test Operators

```dart
void main() {
  var name = 'Dart';
  var year = 2011;
  print('name is String: ${name is String}');
  print('year is int: ${year is int}');
  print('name is! int: ${name is! int}');
}
```

**Output:**

```
name is String: true
year is int: true
name is! int: true
```

### Example 4: Assignment Operators

```dart
void main() {
  var c = 10;
  c += 5; // c = c + 5
  print('c: $c');
  c -= 2; // c = c - 2
  print('c: $c');
  c *= 3; // c = c * 3
  print('c: $c');
  c /= 6; // c = c / 6
  print('c: $c');
}
```

**Output:**

```
c: 15
c: 13
c: 39
c: 6.5
```

### Example 5: Logical Operators

```dart
void main() {
  bool isSunny = true;
  bool isWarm = false;
  print('isSunny && isWarm: ${isSunny && isWarm}');
  print('isSunny || isWarm: ${isSunny || isWarm}');
  print('!isSunny: ${!isSunny}');
}
```

**Output:**

```
isSunny && isWarm: false
isSunny || isWarm: true
!isSunny: false
```

### Example 6: Bitwise Operators

```dart
void main() {
  int a = 5;  // Binary: 0101
  int b = 3;  // Binary: 0011

  print('a & b = ${a & b}');   // Bitwise AND: 0001 (1)
  print('a | b = ${a | b}');   // Bitwise OR:  0111 (7)
  print('a ^ b = ${a ^ b}');   // Bitwise XOR: 0110 (6)
  print('~a = ${(~a)}');       // Bitwise NOT: 11111111111111111111111111111010 (-6)
  print('a << 1 = ${a << 1}'); // Left Shift:  1010 (10)
  print('a >> 1 = ${a >> 1}'); // Right Shift: 0010 (2)
}
```

**Output:**

```
a & b = 1
a | b = 7
a ^ b = 6
~a = -6
a << 1 = 10
a >> 1 = 2
```

### Example 7: Conditional Assignment (??=)

```dart
void main() {
  String? name;
  name ??= 'Guest'; // Assigns 'Guest' if name is null
  print('Name: $name');

  name ??= 'Admin'; // Will not reassign as name is not null
  print('Name after re-assignment attempt: $name');
}
```

**Output:**

```
Name: Guest
Name after re-assignment attempt: Guest
```

### Example 8: Cascade Notation (..)

```dart
class User {
  String? name;
  int? age;

  void display() {
    print('Name: $name, Age: $age');
  }
}

void main() {
  User user = User()
    ..name = 'Alice'
    ..age = 30
    ..display();
}
```

**Output:**

```
Name: Alice, Age: 30
```

### Example 9: Spread Operator (...)

```dart
void main() {
  List<int> list1 = [1, 2, 3];
  List<int> list2 = [4, 5, 6];
  List<int> combinedList = [...list1, ...list2];
  print('Combined List: $combinedList');

  Set<String> set1 = {'A', 'B'};
  Set<String> set2 = {'B', 'C'};
  Set<String> combinedSet = {...set1, ...set2};
  print('Combined Set: $combinedSet');
}
```

**Output:**

```
Combined List: [1, 2, 3, 4, 5, 6]
Combined Set: {A, B, C}
```

### Example 10: `is` and `as` Operators (Type Checking and Casting)

```dart
void main() {
  Object obj = 'hello';

  if (obj is String) {
    String str = obj as String; // Type cast
    print('Length of string: ${str.length}');
  }

  Object anotherObj = 123;
  print('anotherObj is int: ${anotherObj is int}');
}
```

**Output:**

```
Length of string: 5
anotherObj is int: true
```

---

## 6. Control Flow Statements in Dart

Dart's control flow statements manage program execution: `if-else` for conditional logic, `for`, `while`, and `do-while` loops for repetition, `switch-case` for multi-way selection, and `break` and `continue` to alter loop behavior, enabling complex program logic.

### Conditional Statements

#### Example 1: Basic If-Else

```dart
void main() {
  int number = 10;
  if (number > 0) {
    print('The number is positive.');
  } else {
    print('The number is zero or negative.');
  }
}
```

**Output:**

```
The number is positive.
```

#### Example 2: If-Else If-Else

```dart
void main() {
  int score = 75;
  if (score >= 90) {
    print('Grade: A');
  } else if (score >= 80) {
    print('Grade: B');
  } else if (score >= 70) {
    print('Grade: C');
  } else {
    print('Grade: F');
  }
}
```

**Output:**

```
Grade: C
```

#### Example 3: Nested If-Else

```dart
void main() {
  int age = 20;
  bool hasLicense = true;

  if (age >= 18) {
    if (hasLicense) {
      print('Eligible to drive.');
    } else {
      print('Eligible by age, but needs a license.');
    }
  } else {
    print('Not eligible to drive.');
  }
}
```

**Output:**

```
Eligible to drive.
```

#### Example 4: Ternary Operator

```dart
void main() {
  int a = 10;
  int b = 5;
  String result = (a > b) ? 'a is greater' : 'b is greater or equal';
  print(result);
}
```

**Output:**

```
a is greater
```

#### Example 5: Null-aware operator (??)

```dart
void main() {
  String? name;
  String userName = name ?? 'Guest';
  print('Hello, $userName');

  String? firstName = 'Alice';
  String display = firstName ?? 'Anonymous';
  print('Hello, $display');
}
```

**Output:**

```
Hello, Guest
Hello, Alice
```

### Looping Statements

#### Example 6: For Loop with List

```dart
void main() {
  List<String> fruits = ['Apple', 'Banana', 'Cherry'];
  for (int i = 0; i < fruits.length; i++) {
    print('Fruit ${i + 1}: ${fruits[i]}');
  }
}
```

**Output:**

```
Fruit 1: Apple
Fruit 2: Banana
Fruit 3: Cherry
```

#### Example 7: For-In Loop

```dart
void main() {
  List<String> colors = ['Red', 'Green', 'Blue'];
  for (var color in colors) {
    print(color);
  }
}
```

**Output:**

```
Red
Green
Blue
```

#### Example 8: While Loop for Countdown

```dart
void main() {
  int countdown = 3;
  while (countdown > 0) {
    print('Countdown: $countdown');
    countdown--;
  }
  print('Blast off!');
}
```

**Output:**

```
Countdown: 3
Countdown: 2
Countdown: 1
Blast off!
```

#### Example 9: Do-While Loop for User Input Simulation

```dart
import 'dart:io';

void main() {
  String command;
  do {
    stdout.write('Enter command (type \'exit\' to quit): ');
    command = stdin.readLineSync() ?? '';
    print('You entered: $command');
  } while (command != 'exit');
  print('Exiting program.');
}
```

**Output (User input is simulated):**

```
Enter command (type 'exit' to quit): hello
You entered: hello
Enter command (type 'exit' to quit): exit
You entered: exit
Exiting program.
```

#### Example 10: Break and Continue in Loops

```dart
void main() {
  for (int i = 0; i < 10; i++) {
    if (i == 3) {
      continue; // Skip 3
    }
    if (i == 7) {
      break; // Exit loop at 7
    }
    print('Number: $i');
  }
}
```

**Output:**

```
Number: 0
Number: 1
Number: 2
Number: 4
Number: 5
Number: 6
```

---

## 7. OOP in Dart

### Overview
Object-Oriented Programming (OOP) is a programming paradigm based on the concept of "objects", which can contain data and code. Dart is an object-oriented language, and understanding OOP principles is crucial for building complex applications.

### Key Concepts
* Classes and Objects
* Inheritance
* Abstraction
* Encapsulation
* Polymorphism

### Example 1: Basic Class and Object
```dart
class Animal {
  String name;
  Animal(this.name);

  void makeSound() {
    print('$name makes a sound.');
  }
}

void main() {
  var dog = Animal('Buddy');
  dog.makeSound(); // Output: Buddy makes a sound.
}
```

**Output:**

```
Buddy makes a sound.
```

### Example 2: Inheritance
```dart
class Dog extends Animal {
  Dog(String name) : super(name);

  @override
  void makeSound() {
    print('$name barks!');
  }
}

void main() {
  var myDog = Dog('Buddy');
  myDog.makeSound(); // Output: Buddy barks!
}
```

**Output:**

```
Buddy barks!
```

### Example 3: Abstraction (Abstract Class)
```dart
abstract class Shape {
  double get area;
  void displayArea() {
    print('Area: $area');
  }
}

class Circle extends Shape {
  double radius;
  Circle(this.radius);

  @override
  double get area => 3.14 * radius * radius;
}

void main() {
  var circle = Circle(5);
  circle.displayArea(); // Output: Area: 78.5
}
```

**Output:**

```
Area: 78.5
```

### Example 4: Encapsulation (Private Members)
```dart
class BankAccount {
  double _balance; // Private member

  BankAccount(this._balance);

  double get balance => _balance;

  void deposit(double amount) {
    if (amount > 0) {
      _balance += amount;
      print('Deposited: $amount, New balance: $_balance');
    } else {
      print('Deposit amount must be positive.');
    }
  }
}

void main() {
  var account = BankAccount(1000);
  account.deposit(200);
  // print(account._balance); // Error: The setter '_balance' isn't defined for the class 'BankAccount'.
}
```

**Output:**

```
Deposited: 200.0, New balance: 1200.0
```

### Example 5: Polymorphism
```dart
class Vehicle {
  void drive() {
    print('Vehicle is driving.');
  }
}

class Car extends Vehicle {
  @override
  void drive() {
    print('Car is driving.');
  }
}

class Bicycle extends Vehicle {
  @override
  void drive() {
    print('Bicycle is pedaling.');
  }
}

void startDriving(Vehicle vehicle) {
  vehicle.drive();
}

void main() {
  startDriving(Vehicle()); // Output: Vehicle is driving.
  startDriving(Car());     // Output: Car is driving.
  startDriving(Bicycle()); // Output: Bicycle is pedaling.
}
```

**Output:**

```
Vehicle is driving.
Car is driving.
Bicycle is pedaling.
```

---

## 8. File Handling in Dart

### Overview
File handling in Dart allows you to read from and write to files on the local filesystem. Dart provides the `dart:io` library for file operations, which includes classes like `File`, `Directory`, and `FileSystemEntity`.

### Key Concepts
*   `File`: Represents a file on the filesystem
*   `Directory`: Represents a directory on the filesystem
*   `FileSystemEntity`: Base class for both files and directories
*   `Path operations`: Working with file and directory paths
*   `Asynchronous operations`: Most file operations are asynchronous

### Example 1: Writing to a File

```dart
import 'dart:io';

void main() async {
  final file = File('my_file.txt');
  await file.writeAsString('Hello, Dart File Handling!');
  print('Data written to my_file.txt');
}
```

**Output:**

```
Data written to my_file.txt
```

### Example 2: Reading from a File

```dart
import 'dart:io';

void main() async {
  try {
    final file = File('my_file.txt');
    String contents = await file.readAsString();
    print('File contents: $contents');
  } catch (e) {
    print('Error reading file: $e');
  }
}
```

**Output (assuming my_file.txt exists from Example 1):**

```
File contents: Hello, Dart File Handling!
```

### Example 3: Appending to a File

```dart
import 'dart:io';

void main() async {
  final file = File('my_file.txt');
  await file.writeAsStringSync('\nAppending some more data.', mode: FileMode.append);
  print('Data appended to my_file.txt');
}
```

**Output:**

```
Data appended to my_file.txt
```

### Example 4: Checking if a File Exists

```dart
import 'dart:io';

void main() async {
  final file = File('my_file.txt');
  if (await file.exists()) {
    print('my_file.txt exists.');
  } else {
    print('my_file.txt does not exist.');
  }

  final nonExistentFile = File('non_existent.txt');
  if (await nonExistentFile.exists()) {
    print('non_existent.txt exists.');
  } else {
    print('non_existent.txt does not exist.');
  }
}
```

**Output (assuming my_file.txt exists):**

```
my_file.txt exists.
non_existent.txt does not exist.
```

### Example 5: Deleting a File

```dart
import 'dart:io';

void main() async {
  final fileToDelete = File('file_to_delete.txt');
  await fileToDelete.writeAsString('This file will be deleted.');
  print('Created file_to_delete.txt');

  if (await fileToDelete.exists()) {
    await fileToDelete.delete();
    print('file_to_delete.txt deleted.');
  } else {
    print('file_to_delete.txt does not exist.');
  }
}
```

**Output:**

```
Created file_to_delete.txt
file_to_delete.txt deleted.
```

### Example 6: Creating a Directory

```dart
import 'dart:io';

void main() async {
  final newDir = Directory('my_new_directory');
  if (!await newDir.exists()) {
    await newDir.create();
    print('Directory created: ${newDir.path}');
  } else {
    print('Directory already exists: ${newDir.path}');
  }
}
```

**Output:**

```
Directory created: my_new_directory
```

### Example 7: Listing Directory Contents

```dart
import 'dart:io';

void main() async {
  final dir = Directory('.'); // Current directory
  List<FileSystemEntity> entities = await dir.list().toList();
  print('Contents of current directory:');
  for (var entity in entities) {
    print(entity.path);
  }
}
```

**Output (will vary based on your directory contents):**

```
Contents of current directory:
.git
my_file.txt
README.md
my_new_directory
```

### Example 8: Copying a File

```dart
import 'dart:io';

void main() async {
  final sourceFile = File('my_file.txt');
  final destinationFile = File('my_file_copy.txt');

  if (await sourceFile.exists()) {
    await sourceFile.copy(destinationFile.path);
    print('File copied from ${sourceFile.path} to ${destinationFile.path}');
  } else {
    print('Source file does not exist: ${sourceFile.path}');
  }
}
```

**Output (assuming my_file.txt exists):**

```
File copied from my_file.txt to my_file_copy.txt
```

### Example 9: Moving/Renaming a File

```dart
import 'dart:io';

void main() async {
  final oldFile = File('old_name.txt');
  final newFile = File('new_name.txt');

  await oldFile.writeAsString('This is a file to be renamed.');
  print('Created old_name.txt');

  if (await oldFile.exists()) {
    await oldFile.rename(newFile.path);
    print('File renamed from ${oldFile.path} to ${newFile.path}');
  } else {
    print('File to rename does not exist: ${oldFile.path}');
  }
}
```

**Output:**

```
Created old_name.txt
File renamed from old_name.txt to new_name.txt
```

### Example 10: Reading File as Lines

```dart
import 'dart:io';
import 'dart:convert'; // Required for utf8.decoder

void main() async {
  final file = File('lines_file.txt');
  await file.writeAsString('Line 1\nLine 2\nLine 3');

  if (await file.exists()) {
    Stream<String> lines = file.openRead()
        .transform(utf8.decoder)
        .transform(const LineSplitter());

    await for (var line in lines) {
      print('Read line: $line');
    }
  } else {
    print('File does not exist: ${file.path}');
  }
}
```

**Output:**

```
Read line: Line 1
Read line: Line 2
Read line: Line 3
```

---

## 9. Null Safety In Dart

### Overview
Null safety is a feature in Dart that helps prevent null reference errors, which are common sources of bugs in programming. With null safety, variables are non-nullable by default, meaning they cannot contain null values unless explicitly declared as nullable using the ? operator.

### Key Concepts
*   Non-nullable types: Cannot be null (default in Dart)
*   Nullable types: Can be null (declared with ?)
*   Null-aware operators: ??, ?., ! (null assertion)
*   Flow analysis: Dart analyzes code flow to determine nullability
*   Late variables: Variables that are initialized later

### Example 1: Non-nullable Variable (Default)

```dart
void main() {
  int age = 30; // Non-nullable by default
  // age = null; // Compile-time error: A value of type 'Null' can't be assigned to a variable of type 'int'.
  print('Age: $age');
}
```

**Output:**

```
Age: 30
```

### Example 2: Nullable Variable with ?

```dart
void main() {
  String? name; // Declared as nullable, can hold null
  print('Name: $name');

  name = 'Alice';
  print('Name after assignment: $name');

  name = null; // Can be assigned null
  print('Name after setting to null: $name');
}
```

**Output:**

```
Name: null
Name after assignment: Alice
Name after setting to null: null
```

### Example 3: Null-aware operator (??) - Providing a Default Value

```dart
void main() {
  String? displayName;
  String user = displayName ?? 'Guest'; // If displayName is null, use 'Guest'
  print('User: $user');

  displayName = 'Bob';
  user = displayName ?? 'Guest';
  print('User: $user');
}
```

**Output:**

```
User: Guest
User: Bob
```

### Example 4: Null-aware access operator (?.) - Conditional Member Access

```dart
void main() {
  String? message;
  print('Length of message: ${message?.length}'); // Access length only if message is not null

  message = 'Hello';
  print('Length of message: ${message?.length}');
}
```

**Output:**

```
Length of message: null
Length of message: 5
```

### Example 5: Null Assertion Operator (!) - "I know it's not null!"

```dart
void main() {
  String? name = 'Charlie';
  String nonNullableName = name!; // Asserts that name is not null
  print('Non-nullable name: $nonNullableName');

  String? nullableName;
  // String anotherName = nullableName!; // Runtime error if nullableName is actually null
  // print('Another name: $anotherName');
}
```

**Output:**

```
Non-nullable name: Charlie
```

### Example 6: Late Variables - Deferred Initialization

```dart
late String greeting;

void main() {
  greeting = 'Good morning!'; // Initialized later
  print(greeting);

  // If not initialized before use, it would throw a runtime error.
  // late int score;
  // print(score); // Error: LateInitializationError: Field 'score' has not been initialized.
}
```

**Output:**

```
Good morning!
```

### Example 7: Nullable Function Parameters

```dart
void printMessage(String? msg) {
  if (msg != null) {
    print('Message: $msg');
  } else {
    print('No message provided.');
  }
}

void main() {
  printMessage('Hello Dart');
  printMessage(null);
}
```

**Output:**

```
Message: Hello Dart
No message provided.
```

### Example 8: Nullable Return Types

```dart
String? getName(bool isLoggedIn) {
  if (isLoggedIn) {
    return 'Admin';
  } else {
    return null;
  }
}

void main() {
  print('User name: ${getName(true)}');
  print('User name: ${getName(false) ?? 'Guest'}');
}
```

**Output:**

```
User name: Admin
User name: Guest
```

### Example 9: Type Promotion (Flow Analysis)

```dart
void greetUser(Object maybeUser) {
  if (maybeUser is String) {
    // Dart knows maybeUser is a String here, so no need for 'as String'
    print('Hello, ${maybeUser.toUpperCase()}');
  } else if (maybeUser is int) {
    print('User ID: $maybeUser');
  } else {
    print('Unknown user type.');
  }
}

void main() {
  greetUser('Eve');
  greetUser(123);
  greetUser(true);
}
```

**Output:**

```
Hello, EVE
User ID: 123
Unknown user type.
```

### Example 10: Collections with Nullable Types

```dart
void main() {
  List<String?> users = ['Alice', null, 'Bob'];
  print('Users: $users');

  Map<String, int?> scores = {
    'Alice': 90,
    'Bob': null,
    'Charlie': 85,
  };
  print('Scores: $scores');

  // Filtering out nulls from a list
  List<String> activeUsers = users.whereType<String>().toList();
  print('Active users: $activeUsers');
}
```

**Output:**

```
Users: [Alice, null, Bob]
Scores: {Alice: 90, Bob: null, Charlie: 85}
Active users: [Alice, Bob]
```

---

## 10. Asynchronous Programming

### Overview
Asynchronous programming in Dart allows you to write code that doesn't block execution while waiting for operations to complete. This is essential for operations like network requests, file I/O, and database operations that take time.

### Key Concepts
*   Future: Represents a value that will be available in the future
*   async/await: Syntax for writing asynchronous code that looks synchronous
*   Stream: A sequence of asynchronous events
*   Future vs Stream: Future returns a single value, Stream returns multiple values
*   Error Handling: Using try-catch with async operations

### Example 1: Using Future.delayed
```dart
void main() async {
  print('Start fetching data...');
  await Future.delayed(Duration(seconds: 2), () {
    print('Data fetched!');
  });
  print('Processing data...');
}
```

**Output:**

```
Start fetching data...
Processing data...
Data fetched!
```

### Example 2: Chaining Futures with .then()
```dart
void main() {
  print('Start task 1...');
  Future.delayed(Duration(seconds: 1), () => 'Task 1 complete')
      .then((value) {
        print(value);
        return Future.delayed(Duration(seconds: 1), () => 'Task 2 complete');
      })
      .then((value) => print(value))
      .catchError((error) => print('Error: $error'));
  print('Main thread continues...');
}
```

**Output:**

```
Start task 1...
Main thread continues...
Task 1 complete
Task 2 complete
```

### Example 3: Error Handling with Future and .catchError()
```dart
void main() {
  Future.delayed(Duration(seconds: 1), () => throw 'Something went wrong!')
      .then((value) => print(value))
      .catchError((error) => print('Caught error: $error'));
}
```

**Output:**

```
Caught error: Something went wrong!
```

### Example 4: async* and Stream for Multiple Values
```dart
Stream<int> countStream(int max) async* {
  for (int i = 0; i < max; i++) {
    await Future.delayed(Duration(milliseconds: 500));
    yield i;
  }
}

void main() async {
  print('Starting stream...');
  await for (var number in countStream(3)) {
    print('Received: $number');
  }
  print('Stream finished.');
}
```

**Output:**

```
Starting stream...
Received: 0
Received: 1
Received: 2
Stream finished.
```

### Example 5: Using Future.value and Future.error
```dart
void main() async {
  Future<String> successFuture = Future.value('Operation successful!');
  Future<String> errorFuture = Future.error('Failed to load data.');

  print(await successFuture);
  try {
    print(await errorFuture);
  } catch (e) {
    print('Caught error: $e');
  }
}
```

**Output:**

```
Operation successful!
Caught error: Failed to load data.
```

### Example 6: Waiting for Multiple Futures with Future.wait
```dart
void main() async {
  Future<String> task1 = Future.delayed(Duration(seconds: 2), () => 'Result from Task 1');
  Future<String> task2 = Future.delayed(Duration(seconds: 1), () => 'Result from Task 2');

  print('Waiting for all tasks to complete...');
  List<String> results = await Future.wait([task1, task2]);
  print('All tasks complete: $results');
}
```

**Output:**

```
Waiting for all tasks to complete...
All tasks complete: [Result from Task 1, Result from Task 2]
```

### Example 7: Using Completer for Manual Future Completion
```dart
import 'dart:async';

void main() async {
  Completer<String> completer = Completer<String>();

  // Simulate an async operation that completes later
  Future.delayed(Duration(seconds: 2), () {
    completer.complete('Data from completer!');
  });

  print('Waiting for completer...');
  String result = await completer.future;
  print('Completer result: $result');
}
```

**Output:**

```
Waiting for completer...
Completer result: Data from completer!
```

### Example 8: Stream.fromFutures for a Stream of Future Results
```dart
void main() async {
  List<Future<String>> futures = [
    Future.delayed(Duration(seconds: 1), () => 'First item'),
    Future.delayed(Duration(seconds: 2), () => 'Second item'),
    Future.delayed(Duration(seconds: 0), () => 'Third item'),
  ];

  print('Creating stream from futures...');
  Stream<String> stream = Stream.fromFutures(futures);

  await for (var item in stream) {
    print('Stream item: $item');
  }
  print('Stream from futures complete.');
}
```

**Output:**

```
Creating stream from futures...
Stream item: Third item
Stream item: First item
Stream item: Second item
Stream from futures complete.
```

### Example 9: Stream.periodic for Repeated Events
```dart
void main() async {
  print('Starting periodic stream...');
  Stream<int> periodicStream = Stream.periodic(Duration(seconds: 1), (count) => count).take(3);

  await for (var value in periodicStream) {
    print('Periodic event: $value');
  }
  print('Periodic stream complete.');
}
```

**Output:**

```
Starting periodic stream...
Periodic event: 0
Periodic event: 1
Periodic event: 2
Periodic stream complete.
```

### Example 10: Isolates for Parallelism (Basic Example)
```dart
import 'dart:isolate';

void heavyComputation(SendPort sendPort) {
  int sum = 0;
  for (int i = 0; i < 1000000000; i++) {
    sum += i;
  }
  sendPort.send(sum);
}

void main() async {
  ReceivePort receivePort = ReceivePort();
  await Isolate.spawn(heavyComputation, receivePort.sendPort);

  print('Main thread continues while isolate computes...');
  int result = await receivePort.first;
  print('Computation finished in isolate: $result');
}
```

**Output:**

```
Main thread continues while isolate computes...
Computation finished in isolate: 499999999500000000
```

---

## 11. Useful Information

### Final Vs Const

### Final
- `final` is used for variables that are assigned only once.
- It can be assigned a value during the declaration or initialization.
- Once assigned, the value cannot be changed.
- It's typically used for constants that are known at compile-time.

### Const
- `const` is used for compile-time constants.
- It must be initialized with a constant value.
- The value must be known at compile-time.
- It's used for values that are fixed and don't change during runtime.

### Example 1: Final Variable

```dart
void main() {
  final String message = 'This message cannot be changed.';
  // message = 'New message'; // This would cause a compile-time error
  print(message);
}
```

**Output:**

```
This message cannot be changed.
```

### Example 2: Const Variable

```dart
void main() {
  const int maxAttempts = 5;
  // maxAttempts = 10; // This would cause a compile-time error
  print('Maximum attempts: $maxAttempts');
}
```

**Output:**

```
Maximum attempts: 5
```

### Example 3: Final vs Const in Function Parameters

```dart
void main() {
  final String finalMessage = 'Final message';
  const String constMessage = 'Const message';

  // finalMessage = 'New final message'; // Error: A value of type 'String' can't be assigned to a variable of type 'final'.
  // constMessage = 'New const message'; // Error: A value of type 'String' can't be assigned to a variable of type 'const'.

  print('Final message: $finalMessage');
  print('Const message: $constMessage');
}
```

**Output:**

```
Final message: Final message
Const message: Const message
```

### Example 4: Final vs Const in Class Fields

```dart
class MyClass {
  final String finalField = 'Final field';
  const String constField = 'Const field';

  // finalField = 'New final field'; // Error: A value of type 'String' can't be assigned to a variable of type 'final'.
  // constField = 'New const field'; // Error: A value of type 'String' can't be assigned to a variable of type 'const'.

  void printFields() {
    print('Final field: $finalField');
    print('Const field: $constField');
  }
}

void main() {
  MyClass myObject = MyClass();
  myObject.printFields();
}
```

**Output:**

```
Final field: Final field
Const field: Const field
```

### Example 5: Final vs Const in List/Map

```dart
void main() {
  final List<int> finalList = [1, 2, 3];
  const List<int> constList = [1, 2, 3];

  // finalList.add(4); // Error: A value of type 'List<int>' can't be assigned to a variable of type 'final'.
  // constList.add(4); // Error: A value of type 'List<int>' can't be assigned to a variable of type 'const'.

  print('Final list: $finalList');
  print('Const list: $constList');
}
```

**Output:**

```
Final list: [1, 2, 3]
Const list: [1, 2, 3]
```

### Example 6: Final vs Const in Generics

```dart
void main() {
  final List<int> finalList = [1, 2, 3];
  const List<int> constList = [1, 2, 3];

  // finalList.add(4); // Error: A value of type 'List<int>' can't be assigned to a variable of type 'final'.
  // constList.add(4); // Error: A value of type 'List<int>' can't be assigned to a variable of type 'const'.

  print('Final list: $finalList');
  print('Const list: $constList');
}
```

**Output:**

```
Final list: [1, 2, 3]
Const list: [1, 2, 3]
```

### Example 7: Final vs Const in Generic Classes

```dart
class MyGenericClass<T> {
  final T finalField = 'Final field';
  const T constField = 'Const field';

  // finalField = 'New final field'; // Error: A value of type 'String' can't be assigned to a variable of type 'final'.
  // constField = 'New const field'; // Error: A value of type 'String' can't be assigned to a variable of type 'const'.

  void printFields() {
    print('Final field: $finalField');
    print('Const field: $constField');
  }
}

void main() {
  MyGenericClass<String> myObject = MyGenericClass<String>();
  myObject.printFields();
}
```

**Output:**

```
Final field: Final field
Const field: Const field
```

### Example 8: Final vs Const in Generic Methods

```dart
class MyGenericClass<T> {
  final T finalField = 'Final field';
  const T constField = 'Const field';

  // finalField = 'New final field'; // Error: A value of type 'String' can't be assigned to a variable of type 'final'.
  // constField = 'New const field'; // Error: A value of type 'String' can't be assigned to a variable of type 'const'.

  void printFields() {
    print('Final field: $finalField');
    print('Const field: $constField');
  }
}

void main() {
  MyGenericClass<String> myObject = MyGenericClass<String>();
  myObject.printFields();
}
```

**Output:**

```
Final field: Final field
Const field: Const field
```

### Example 9: Final vs Const in Generic Generators

```dart
Iterable<int> count(int n) sync* {
  for (int i = 0; i < n; i++) {
    yield i; // yield a value
  }
}

void main() {
  final Iterable<int> finalIterable = count(5);
  const Iterable<int> constIterable = count(5);

  // finalIterable.add(6); // Error: A value of type 'Iterable<int>' can't be assigned to a variable of type 'final'.
  // constIterable.add(6); // Error: A value of type 'Iterable<int>' can't be assigned to a variable of type 'const'.

  print('Final iterable: $finalIterable');
  print('Const iterable: $constIterable');
}
```

**Output:**

```
Final iterable: (0, 1, 2, 3, 4)
Const iterable: (0, 1, 2, 3, 4)
```

### Example 10: Final vs Const in Generic Streams

```dart
Stream<int> countAsync(int n) async* {
  for (int i = 0; i < n; i++) {
    await Future.delayed(Duration(milliseconds: 100));
    yield i;
  }
}

void main() async {
  final Stream<int> finalStream = countAsync(3);
  const Stream<int> constStream = countAsync(3);

  // finalStream.add(3); // Error: A value of type 'Stream<int>' can't be assigned to a variable of type 'final'.
  // constStream.add(3); // Error: A value of type 'Stream<int>' can't be assigned to a variable of type 'const'.

  await for (var value in finalStream) {
    print('Final stream value: $value');
  }
  await for (var value in constStream) {
    print('Const stream value: $value');
  }
}
```

**Output:**

```
Final stream value: 0
Final stream value: 1
Final stream value: 2
Const stream value: 0
Const stream value: 1
Const stream value: 2
```

### DateTime in Dart

### Overview
Dart's `DateTime` class in `dart:core` provides functionalities to work with dates and times, including creating, parsing, formatting, and performing calculations with date and time values. It supports both UTC and local time zones.

### Key Concepts
*   Creating `DateTime` objects
*   Getting current date and time
*   Parsing date strings
*   Formatting dates
*   Date arithmetic (add, subtract, difference)
*   Comparing dates

### Example 1: Creating DateTime Objects
```dart
void main() {
  // Current date and time
  DateTime now = DateTime.now();
  print('Current date and time: $now');

  // Specific date and time
  DateTime specificDate = DateTime(2025, 12, 25, 10, 30, 0);
  print('Specific date: $specificDate');

  // UTC date and time
  DateTime utcDate = DateTime.utc(2025, 12, 25, 10, 30, 0);
  print('UTC date: $utcDate');
}
```

**Output (will vary based on current time):**

```
Current date and time: 2025-11-05 10:30:00.000
Specific date: 2025-12-25 10:30:00.000
UTC date: 2025-12-25 10:30:00.000Z
```

### Example 2: Getting Date and Time Components
```dart
void main() {
  DateTime now = DateTime.now();
  print('Year: ${now.year}');
  print('Month: ${now.month}');
  print('Day: ${now.day}');
  print('Hour: ${now.hour}');
  print('Minute: ${now.minute}');
  print('Second: ${now.second}');
  print('Weekday: ${now.weekday}'); // Monday = 1, Sunday = 7
}
```

**Output (will vary based on current time):**

```
Year: 2025
Month: 11
Day: 5
Hour: 10
Minute: 30
Second: 0
Weekday: 3
```

### Example 3: Parsing Date Strings
```dart
void main() {
  String dateString = '2024-01-15 14:30:00';
  DateTime parsedDate = DateTime.parse(dateString);
  print('Parsed date: $parsedDate');

  String isoDateString = '2024-02-29T08:00:00Z';
  DateTime isoParsedDate = DateTime.parse(isoDateString);
  print('ISO Parsed date: $isoParsedDate');
}
```

**Output:**

```
Parsed date: 2024-01-15 14:30:00.000
ISO Parsed date: 2024-02-29 08:00:00.000Z
```

### Example 4: Date Arithmetic (Adding/Subtracting Duration)
```dart
void main() {
  DateTime now = DateTime.now();

  // Add 5 days
  DateTime fiveDaysLater = now.add(Duration(days: 5));
  print('5 days later: $fiveDaysLater');

  // Subtract 2 hours
  DateTime twoHoursAgo = now.subtract(Duration(hours: 2));
  print('2 hours ago: $twoHoursAgo');

  // Difference between two dates
  DateTime futureDate = DateTime(2025, 12, 31);
  Duration difference = futureDate.difference(now);
  print('Difference in days: ${difference.inDays}');
  print('Difference in hours: ${difference.inHours}');
}
```

**Output (will vary based on current time):**

```
5 days later: 2025-11-10 10:30:00.000
2 hours ago: 2025-11-05 08:30:00.000
Difference in days: 56
Difference in hours: 1344
```

### Example 5: Comparing Dates
```dart
void main() {
  DateTime date1 = DateTime(2025, 1, 1);
  DateTime date2 = DateTime(2025, 1, 1);
  DateTime date3 = DateTime(2025, 1, 2);

  print('date1 is same as date2: ${date1.isAtSameMomentAs(date2)}');
  print('date1 is before date3: ${date1.isBefore(date3)}');
  print('date3 is after date1: ${date3.isAfter(date1)}');
}
```

**Output:**

```
date1 is same as date2: true
date1 is before date3: true
date3 is after date1: true
```

---

### Extension In Dart

### Overview
Extension methods in Dart allow you to add new functionalities to existing classes without modifying their source code. This is particularly useful for adding utility methods to types you don't own, like those from `dart:core` or other libraries. They make code more readable and expressive by allowing you to call new methods using dot notation on an object of the extended type.

### Key Concepts
*   Syntax: `extension ExtensionName on Type { ... }`
*   Implicit vs. Explicit Invocation
*   Conflict Resolution
*   Generics with Extensions

### Example 1: Basic String Extension
```dart
extension StringExtension on String {
  String capitalize() {
    if (isEmpty) return this;
    return '${this[0].toUpperCase()}${substring(1)}';
  }

  String reverse() {
    return split('').reversed.join();
  }
}

void main() {
  String message = 'hello world';
  print(message.capitalize()); // Output: Hello world
  print(message.reverse());   // Output: dlrow olleh

  print('dart'.capitalize());
}
```

**Output:**

```
Hello world
dlrow olleh
Dart
```

### Example 2: Extension on a List of Integers
```dart
extension ListIntExtension on List<int> {
  int sum() {
    int total = 0;
    for (var number in this) {
      total += number;
    }
    return total;
  }

  double average() {
    if (isEmpty) return 0.0;
    return sum() / length;
  }
}

void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  print('Sum: ${numbers.sum()}');         // Output: Sum: 15
  print('Average: ${numbers.average()}'); // Output: Average: 3.0

  List<int> emptyList = [];
  print('Empty list average: ${emptyList.average()}');
}
```

**Output:**

```
Sum: 15
Average: 3.0
Empty list average: 0.0
```

### Example 3: Extension with Getters
```dart
extension NumExtension on num {
  bool get isPositive => this > 0;
  bool get isNegative => this < 0;
  bool get isZero => this == 0;
}

void main() {
  int a = 10;
  double b = -5.5;
  int c = 0;

  print('10 is positive: ${a.isPositive}'); // Output: 10 is positive: true
  print('-5.5 is negative: ${b.isNegative}'); // Output: -5.5 is negative: true
  print('0 is zero: ${c.isZero}');       // Output: 0 is zero: true
}
```

**Output:**

```
10 is positive: true
-5.5 is negative: true
0 is zero: true
```

### Example 4: Explicitly Importing and Using Extensions
```dart
// In a separate file (e.g., string_utils.dart)
// extension StringFormatting on String {
//   String toTitleCase() {
//     return this.split(' ').map((word) => word.capitalize()).join(' ');
//   }
// }

// In main.dart
// import 'string_utils.dart';

extension StringFormatting on String {
  String toTitleCase() {
    if (isEmpty) return this;
    return split(' ').map((word) => word[0].toUpperCase() + word.substring(1)).join(' ');
  }
}

void main() {
  String sentence = 'hello dart extensions';
  print(sentence.toTitleCase()); // Output: Hello Dart Extensions
}
```

**Output:**

```
Hello Dart Extensions
```

### Example 5: Conflict Resolution (Hiding Extensions)
```dart
extension MyStringExtension on String {
  String sayHello() => 'Hello from MyStringExtension';
}

extension AnotherStringExtension on String {
  String sayHello() => 'Hello from AnotherStringExtension';
}

void main() {
  String name = 'Dart';
  // print(name.sayHello()); // Error: The name 'sayHello' is defined in multiple extensions.

  // Explicitly use an extension
  print(MyStringExtension(name).sayHello());     // Output: Hello from MyStringExtension
  print(AnotherStringExtension(name).sayHello()); // Output: Hello from AnotherStringExtension
}
```

**Output:**

```
Hello from MyStringExtension
Hello from AnotherStringExtension
```

---

### Backend in Dart

### Overview
Dart is gaining popularity for backend development, especially with frameworks like Aqueduct and Shelf. Its excellent performance, strong typing, and asynchronous capabilities make it a viable choice for building scalable and efficient server-side applications. This section will provide a basic introduction to setting up a simple Dart backend.

### Key Concepts
*   HTTP Server with `dart:io`
*   Routing
*   JSON Handling
*   Database Integration (conceptual)
*   Frameworks (Aqueduct, Shelf - conceptual)

### Example 1: Basic HTTP Server with `dart:io`
```dart
import 'dart:io';

void main() async {
  final server = await HttpServer.bind(InternetAddress.loopbackIPv4, 8080);
  print('Listening on localhost: ${server.port}');

  await for (HttpRequest request in server) {
    request.response
      ..headers.contentType = ContentType.html
      ..write('<h1>Hello from Dart Backend!</h1>')
      ..close();
  }
}
```

**Output (after running and accessing http://localhost:8080 in a browser):**

```
Listening on localhost: 8080
(Browser displays: Hello from Dart Backend!)
```

### Example 2: Simple Routing
```dart
import 'dart:io';

void main() async {
  final server = await HttpServer.bind(InternetAddress.loopbackIPv4, 8080);
  print('Listening on localhost: ${server.port}');

  await for (HttpRequest request in server) {
    if (request.uri.path == '/') {
      request.response
        ..headers.contentType = ContentType.html
        ..write('<h1>Welcome to the Home Page!</h1>')
        ..close();
    } else if (request.uri.path == '/api/greet') {
      request.response
        ..headers.contentType = ContentType.json
        ..write('{"message": "Hello API!"}')
        ..close();
    } else {
      request.response
        ..statusCode = HttpStatus.notFound
        ..write('Not Found')
        ..close();
    }
  }
}
```

**Output (accessing http://localhost:8080 and http://localhost:8080/api/greet):**

```
Listening on localhost: 8080
(Browser displays for /: Welcome to the Home Page!)
(Browser displays for /api/greet: {"message": "Hello API!"})
```

### Example 3: Handling POST Requests and JSON
```dart
import 'dart:io';
import 'dart:convert';

void main() async {
  final server = await HttpServer.bind(InternetAddress.loopbackIPv4, 8080);
  print('Listening on localhost: ${server.port}');

  await for (HttpRequest request in server) {
    if (request.uri.path == '/api/data' && request.method == 'POST') {
      try {
        String content = await utf8.decoder.bind(request).join();
        Map data = json.decode(content);
        print('Received data: $data');

        request.response
          ..headers.contentType = ContentType.json
          ..write(json.encode({'status': 'success', 'received': data}))
          ..close();
      } catch (e) {
        request.response
          ..statusCode = HttpStatus.badRequest
          ..write('Error parsing JSON: $e')
          ..close();
      }
    } else {
      request.response
        ..statusCode = HttpStatus.methodNotAllowed
        ..write('Method Not Allowed')
        ..close();
    }
  }
}
```

**Output (using a tool like Postman to send POST request to http://localhost:8080/api/data with JSON body {"name": "Dart", "version": "3.0"}):**

```
Listening on localhost: 8080
Received data: {name: Dart, version: 3.0}
(Response: {"status": "success", "received": {"name": "Dart", "version": "3.0"}})
```

### Example 4: Using Shelf Framework (Conceptual)
```dart
// This is a conceptual example, actual implementation requires adding 'shelf' dependency.
// For a real project, you would add shelf to your pubspec.yaml and import accordingly.

// import 'package:shelf/shelf.dart';
// import 'package:shelf/shelf_io.dart' as io;
// import 'package:shelf_router/shelf_router.dart';

/*
void main() async {
  final _router = Router()
    ..get('/', _homeHandler)
    ..get('/hello/<name>', _helloHandler);

  final _handler = const Pipeline()
      .addMiddleware(logRequests())
      .addHandler(_router);

  final server = await io.serve(_handler, 'localhost', 8080);
  print('Serving at http://${server.address.host}:${server.port}');
}

Response _homeHandler(Request request) {
  return Response.ok('Welcome to Shelf!');
}

Response _helloHandler(Request request) {
  final name = request.params['name'];
  return Response.ok('Hello, $name!');
}
*/

void main() {
  print('Conceptual Shelf example. Add shelf and shelf_router to pubspec.yaml to run.');
}
```

**Output (conceptual):**

```
Conceptual Shelf example. Add shelf and shelf_router to pubspec.yaml to run.
```

### Example 5: Database Integration (Conceptual with `sqflite` for Flutter/Dart)
```dart
// This is a conceptual example. For a real database integration, you'd use
// packages like `postgres`, `mysql1`, or `sqflite` (for Flutter/local DB).

/*
// Using `sqflite` (typically for Flutter apps, but demonstrates concept)
import 'package:sqflite/sqflite.dart';
import 'package:path/path.dart';

Future<Database> _initDatabase() async {
  final databasesPath = await getDatabasesPath();
  final path = join(databasesPath, 'demo.db');

  return openDatabase(
    path,
    version: 1,
    onCreate: (db, version) {
      return db.execute(
        'CREATE TABLE users(id INTEGER PRIMARY KEY, name TEXT, age INTEGER)',
      );
    },
  );
}

Future<void> insertUser(Map<String, dynamic> user) async {
  final Database db = await _initDatabase();
  await db.insert('users', user, conflictAlgorithm: ConflictAlgorithm.replace);
}

Future<List<Map<String, dynamic>>> getUsers() async {
  final Database db = await _initDatabase();
  return db.query('users');
}

void main() async {
  // For a real backend, this would involve a server endpoint calling these functions.
  // Example of usage:
  await insertUser({'id': 1, 'name': 'Alice', 'age': 30});
  await insertUser({'id': 2, 'name': 'Bob', 'age': 25});
  print('Users: ${await getUsers()}');
}
*/

void main() {
  print('Conceptual database example. Add relevant database package to pubspec.yaml to run.');
}
```

**Output (conceptual):**

```
Conceptual database example. Add relevant database package to pubspec.yaml to run.
```

---

## 10. Dart Interview Question

Overview

This section contains common Dart interview questions with detailed code examples and explanations. These questions cover fundamental concepts, advanced topics, and best practices that are frequently asked in Dart/Flutter developer interviews.

10 Examples of Dart Interview Questions

### Question 1: What is the difference between var, final, and const?

`var`:
- Type is inferred at initialization.
- Can be reassigned to a new value of the same inferred type.
- Mutable.

`final`:
- Type is inferred at initialization.
- Can only be assigned once. Its value is determined at runtime.
- Immutable.

`const`:
- Type is inferred at initialization.
- Must be a compile-time constant. Its value must be known at compile time.
- Immutable.

```dart
void main() {
  // var - type is inferred, can be reassigned
  var name = 'John';
  name = 'Jane'; // Valid
  print('var: $name');

  // final - type is inferred, cannot be reassigned (runtime constant)
  final age = 25;
  // age = 26; // Error: cannot assign to final variable
  final currentTime = DateTime.now(); // OK - determined at runtime
  print('final age: $age');
  print('final currentTime: $currentTime');

  // const - compile-time constant, cannot be reassigned
  const pi = 3.14159;
  // pi = 3.14; // Error: cannot assign to const variable
  // const now = DateTime.now(); // Error: must be compile-time constant
  print('const pi: $pi');

  // Summary:
  // var: mutable, type inferred
  // final: immutable, runtime value
  // const: immutable, compile-time value
}
```

**Output:**

```
var: Jane
final age: 25
final currentTime: 2024-01-01 10:00:00.000
const pi: 3.14159
```

### Question 2: Explain Null Safety in Dart

Null safety is a feature that helps prevent null reference errors. By default, variables in Dart are non-nullable, meaning they cannot hold `null` unless explicitly declared as nullable using the `?` operator.

**Key Concepts:**
- **Non-nullable (default):** Variables cannot be `null`.
- **Nullable types (`?`):** Variables can explicitly hold `null` values.
- **Null-aware operators:**
    - `??` (null coalescing operator): Provides a default value if an expression is `null`.
    - `?.` (null-aware access operator): Safely accesses members only if the object is not `null`.
    - `!` (null assertion operator): Asserts that an expression is not `null` (use with caution as it can lead to runtime errors if the value is actually `null`).

```dart
void main() {
  // Non-nullable (default)
  String name = 'John';
  // name = null; // Error: cannot assign null

  // Nullable types use ?
  String? nullableName;
  nullableName = null; // OK
  nullableName = 'Jane'; // OK

  // Null-aware operators
  String? maybeNull;

  // ?? - null coalescing
  String result = maybeNull ?? 'Default';
  print('Result: $result');

  // ?. - null-aware access
  int? length = maybeNull?.length;
  print('Length: $length');

  // ! - null assertion (use with caution)
  String? definitelyNotNull = 'Hello';
  String forced = definitelyNotNull!; // OK if we're sure
  print('Forced: $forced');

  // Null safety prevents null reference errors
}
```

**Output:**

```
Result: Default
Length: null
Forced: Hello
```

### Question 3: What are Mixins and how do they differ from Inheritance?

**Mixins** in Dart allow you to reuse a class's code in multiple class hierarchies. They enable a form of code reuse that is similar to multiple inheritance but avoids the complexities of multiple inheritance by focusing on sharing implementations (behaviors) rather than creating a rigid "is-a" hierarchy.

**Key Differences from Inheritance:**
- **Inheritance:** Establishes an "is-a" relationship (e.g., `Dog` is an `Animal`). A class can only inherit from a single parent class.
- **Mixins:** Provide a "has-a" capability (e.g., a `Duck` has the capability to `Flyable` and `Swimmable`). A class can use multiple mixins, allowing it to compose behavior from various sources.
- Mixins are used with the `with` keyword, while inheritance uses `extends`.

```dart
// Mixin definition
mixin Flyable {
  void fly() {
    print('Flying...');
  }
}

mixin Swimmable {
  void swim() {
    print('Swimming...');
  }
}

// Base class
class Animal {
  void eat() {
    print('Eating...');
  }
}

// Class using mixins (multiple inheritance-like behavior)
class Duck extends Animal with Flyable, Swimmable {
  void quack() {
    print('Quacking...');
  }
}

void main() {
  Duck duck = Duck();
  duck.eat();    // From Animal
  duck.fly();    // From Flyable mixin
  duck.swim();   // From Swimmable mixin
  duck.quack();  // From Duck itself

  // Difference from inheritance:
  // - Mixins allow multiple behaviors
  // - Inheritance: single parent class
  // - Mixins: "is-a" relationship, Mixins: "has-a" capability
}
```

**Output:**

```
Eating...
Flying...
Swimming...
Quacking...
```

### Question 4: Explain async and await in Dart

**Asynchronous programming** in Dart allows your program to perform long-running operations (like fetching data from a network) without blocking the main thread of execution. This keeps your application responsive.

- **`async` keyword**: Used to mark a function as asynchronous. An `async` function always returns a `Future`.
- **`await` keyword**: Used to pause the execution of an `async` function until a `Future` completes. It can only be used inside `async` functions.

Together, `async` and `await` enable you to write asynchronous code that looks and feels like synchronous code, making it easier to read and maintain.

```dart
import 'dart:async';

// Async function returns Future
Future<String> fetchData() async {
  await Future.delayed(Duration(seconds: 1));
  return 'Data fetched';
}

// Using await to wait for async operations
Future<void> processData() async {
  print('Starting...');
  String data = await fetchData(); // Waits for completion
  print('Received: $data');
  print('Processing complete');
}

// Multiple async operations
Future<void> fetchMultiple() async {
  // Sequential
  String data1 = await fetchData();
  String data2 = await fetchData();
  print('Sequential: $data1, $data2');

  // Parallel
  Future<String> future1 = fetchData();
  Future<String> future2 = fetchData();
  String result1 = await future1;
  String result2 = await future2;
  print('Parallel: $result1, $result2');
}

void main() async {
  await processData();
  print('---');
  await fetchMultiple();
}
```

**Output:**

```
Starting...
Received: Data fetched
Processing complete
---
Sequential: Data fetched, Data fetched
Parallel: Data fetched, Data fetched
```

### Question 5: What is the difference between List, Set, and Map?

Dart provides several core collection types to organize and manipulate data. The most common ones are `List`, `Set`, and `Map`, each with distinct characteristics and use cases.

- **`List`**: An ordered collection of values, also known as an array. It allows duplicate elements and elements are accessed by their index (0-based).
    - **Characteristics:** Ordered, allows duplicates, indexed.
    - **Use cases:** When the order of elements matters, and you might need to store the same value multiple times.

- **`Set`**: An unordered collection of unique values. It does not allow duplicate elements.
    - **Characteristics:** Unordered, no duplicates.
    - **Use cases:** When you need to store a collection of unique items and the order doesn't matter.

- **`Map`**: An unordered collection of key-value pairs. Each key must be unique, and it maps to a corresponding value.
    - **Characteristics:** Key-value pairs, unique keys, unordered.
    - **Use cases:** When you need to associate values with unique keys for quick retrieval (like a dictionary in other languages).

```dart
void main() {
  // List - ordered, allows duplicates, indexed
  List<String> fruits = ['apple', 'banana', 'apple'];
  print('List: $fruits');
  print('List length: ${fruits.length}');
  print('First item: ${fruits[0]}');

  // Set - unordered, no duplicates
  Set<String> uniqueFruits = {'apple', 'banana', 'apple'};
  print('Set: $uniqueFruits');
  print('Set length: ${uniqueFruits.length}');
  // print('First item: ${uniqueFruits[0]}'); // Error: no index access

  // Map - key-value pairs, unique keys
  Map<String, int> ages = {
    'Alice': 25,
    'Bob': 30,
    'Alice': 26, // Overwrites previous Alice
  };
  print('Map: $ages');
  print('Alice age: ${ages['Alice']}');
  print('Map size: ${ages.length}');

  // Use cases:
  // List: when order and duplicates matter
  // Set: when uniqueness matters
  // Map: when key-value pairs are needed
}
```

**Output:**

```
List: [apple, banana, apple]
List length: 3
First item: apple
Set: {apple, banana}
Set length: 2
Map: {Alice: 26, Bob: 30}
Alice age: 26
Map size: 2
```

### Question 6: Explain Stream and how it differs from Future

In Dart's asynchronous programming, both `Future` and `Stream` are used to handle values that will be available at a later time. However, they differ in the number of values they can produce:

- **`Future`**: Represents a single value that will be available at some point in the future. Once a `Future` completes (either with a value or an error), it cannot produce any more values. It's a one-time delivery of data.
    - **Characteristics:** Single value, one-time.
    - **Use cases:** Network requests, reading a file once, any operation that yields a single result.

- **`Stream`**: Represents a sequence of values (or events) that are produced asynchronously over time. A `Stream` can emit zero, one, or multiple values, and can also emit errors, before finally completing (or remaining open indefinitely). It's a continuous flow of data.
    - **Characteristics:** Multiple values, continuous over time.
    - **Use cases:** User input events (clicks, key presses), real-time data from a server (websockets), file system events.

```dart
import 'dart:async';

// Future - single value
Future<String> fetchUser() async {
  await Future.delayed(Duration(seconds: 1));
  return 'User data';
}

// Stream - multiple values over time
Stream<int> countStream() async* {
  for (int i = 1; i <= 5; i++) {
    await Future.delayed(Duration(milliseconds: 500));
    yield i; // Emit value
  }
}

void main() async {
  // Future - get value once
  print('Fetching user...');
  String user = await fetchUser();
  print('User: $user');

  print('---');

  // Stream - listen to multiple values
  print('Listening to stream...');
  await for (int value in countStream()) {
    print('Received: $value');
  }

  // Key differences:
  // Future: one value, one-time
  // Stream: multiple values, continuous
}
```

**Output:**

```
Fetching user...
User: User data
---
Listening to stream...
Received: 1
Received: 2
Received: 3
Received: 4
Received: 5
```

### Question 7: What are Generics and why are they useful?

**Generics** are a powerful feature in Dart that allow you to write code that works with a variety of types while maintaining type safety. They enable you to define classes, methods, and functions with type parameters, making your code more reusable and robust.

**Why are they useful?**
- **Type Safety**: Generics help catch type-related errors at compile-time rather than at runtime, preventing unexpected behavior.
- **Code Reusability**: You can write a single piece of code that works with different data types without duplicating logic.
- **Improved Readability**: By explicitly defining the types your code works with, it becomes clearer to understand its intent.

```dart
// Generic class
class Box<T> {
  T _item;

  Box(this._item);

  T get item => _item;

  void setItem(T newItem) {
    _item = newItem;
  }
}

// Generic method
T getFirst<T>(List<T> list) {
  return list.first;
}

// Generic function with constraints
T findMax<T extends Comparable<T>>(List<T> items) {
  if (items.isEmpty) throw Exception('List is empty');
  return items.reduce((a, b) => a.compareTo(b) > 0 ? a : b);
}

void main() {
  // Type-safe container
  Box<String> stringBox = Box('Hello');
  Box<int> intBox = Box(42);

  print('String box: ${stringBox.item}');
  print('Int box: ${intBox.item}');

  // Generic method
  String first = getFirst(['Alice', 'Bob', 'Charlie']);
  int firstNum = getFirst([1, 2, 3]);
  print('First string: $first');
  print('First number: $firstNum');

  // Generic with constraints
  int max = findMax([3, 1, 4, 1, 5, 9]);
  print('Max: $max');

  // Benefits:
  // - Type safety
  // - Code reusability
  // - Compile-time type checking
}
```

**Output:**

```
String box: Hello
Int box: 42
First string: Alice
First number: 1
Max: 9
```

### Question 8: Explain factory constructors

**Factory constructors** in Dart provide a way to create instances of classes that are not always new objects. Unlike regular constructors, which always create a new instance of the class, factory constructors can return an existing instance, an instance of a subtype, or an instance based on some conditional logic. They are declared using the `factory` keyword.

**Key Characteristics and Use Cases:**
- **Return existing instances:** Implement singleton patterns or return cached objects.
- **Return subtypes:** Return an instance of a class that extends the current class.
- **Conditional logic:** Create instances based on input parameters or other conditions.
- **Cannot access `this`**: Inside a factory constructor, you don't have access to `this` because an instance might not have been created yet.

```dart
import 'dart:math'; // For cos() and sin() in Point.polar example

class Logger {
  static Logger? _instance;

  // Private constructor
  Logger._();

  // Factory constructor - returns existing instance or creates new
  factory Logger() {
    _instance ??= Logger._();
    return _instance!;
  }

  void log(String message) {
    print('[LOG] $message');
  }
}

class Point {
  final double x;
  final double y;

  Point(this.x, this.y);

  // Factory constructor - can return different types
  factory Point.origin() {
    return Point(0, 0);
  }

  // Factory constructor with conditional logic
  factory Point.fromJson(Map<String, dynamic> json) {
    if (json.containsKey('x') && json.containsKey('y')) {
      return Point(json['x'], json['y']);
    }
    return Point.origin();
  }

  // Factory can return subtype
  factory Point.polar(double radius, double angle) {
    return Point(
      radius * cos(angle),
      radius * sin(angle),
    );
  }
}

void main() {
  // Singleton pattern
  Logger logger1 = Logger();
  Logger logger2 = Logger();
  print('Same instance: ${identical(logger1, logger2)}');

  // Factory constructors
  Point origin = Point.origin();
  Point fromJson = Point.fromJson({'x': 5, 'y': 10});

  print('Origin: (${origin.x}, ${origin.y})');
  print('From JSON: (${fromJson.x}, ${fromJson.y})');

  // Factory vs regular constructor:
  // - Factory can return existing instance
  // - Factory can return subtype
  // - Factory can have conditional logic

  // Example of using Point.polar (requires dart:math import)
  Point polarPoint = Point.polar(10, pi / 2); // Radius 10, angle 90 degrees
  print('Polar Point: (${polarPoint.x.toStringAsFixed(2)}, ${polarPoint.y.toStringAsFixed(2)})');
}
```

**Output:**

```
Same instance: true
Origin: (0.0, 0.0)
From JSON: (5.0, 10.0)
Polar Point: (0.00, 10.00)
```

### Question 9: What are Extensions and when to use them?

**Extensions** in Dart allow you to add new functionalities (methods, getters, and setters) to existing classes without modifying their original source code. This is particularly useful when you want to add utility functions to types you don't own (like those from `dart:core` or external libraries) or to organize your code in a more modular way.

**When to use them:**
- **Adding functionality to types you don't own**: Extend built-in types (e.g., `String`, `int`) or classes from third-party packages.
- **Keeping code organized**: Group related utility functions for a specific type into a single extension.
- **Improving readability**: Call new methods using dot notation on an object of the extended type, making the code more fluent and expressive.
- **Avoiding modifying original classes**: Prevents the need to subclass or modify the original class, which can be beneficial for maintenance and preventing tight coupling.

```dart
// Extension adds methods to existing types
extension StringExtension on String {
  String capitalize() {
    if (isEmpty) return this;
    return '${this[0].toUpperCase()}${substring(1)}';
  }

  bool get isEmail {
    return contains('@') && contains('.');
  }
}

extension IntExtension on int {
  bool get isEven => this % 2 == 0;

  Duration get seconds => Duration(seconds: this);
}

void main() {
  String text = 'hello world';
  print('Capitalized: ${text.capitalize()}');
  print('Is email: ${text.isEmail}');

  int number = 4;
  print('Is even: ${number.isEven}');
  print('Duration: ${5.seconds}');

  // When to use extensions:
  // - Add functionality to types you don't own
  // - Keep code organized
  // - Improve readability
  // - Avoid modifying original classes
}
```

**Output:**

```
Capitalized: Hello world
Is email: false
Is even: true
Duration: 0:00:05.000000
```

### Question 10: Explain Error Handling in Dart

**Error handling** in Dart is crucial for building robust applications that can gracefully recover from unexpected situations. Dart distinguishes between two types of issues:

- **Exceptions**: These are intended to be caught and handled. They represent errors that a program can reasonably recover from, such as network issues, invalid input, or file not found errors. You typically use `try-catch` blocks to handle exceptions.
- **Errors**: These represent programming bugs that typically indicate a flaw in the code itself (e.g., `OutOfMemoryError`, `StackOverflowError`). Errors usually should not be caught, as they indicate that something is fundamentally wrong with the program's logic and should be fixed rather than handled.

**Key Constructs for Error Handling:**
- **`try`**: Encloses the code that might throw an exception.
- **`on`**: Catches specific types of exceptions.
- **`catch`**: Catches any type of exception, and can access the exception object and stack trace.
- **`finally`**: Contains code that runs regardless of whether an exception was thrown or caught.
- **`throw`**: Used to explicitly throw an exception.
- **`rethrow`**: Used within a `catch` block to re-throw the caught exception, allowing it to be handled by an outer `catch` block.

```dart
// Custom exception
class ValidationException implements Exception {
  final String message;
  ValidationException(this.message);

  @override
  String toString() => 'ValidationException: $message';
}

// Error handling
void validateAge(int age) {
  if (age < 0) {
    throw ValidationException('Age cannot be negative');
  }
  if (age > 150) {
    throw ValidationException('Age seems unrealistic');
  }
}

Future<String> fetchData() async {
  await Future.delayed(Duration(seconds: 1));
  throw Exception('Network error');
}

void main() {
  // Try-catch
  try {
    validateAge(-5);
  } on ValidationException catch (e) {
    print('Caught: $e');
  } catch (e) {
    print('Other error: $e');
  } finally {
    print('Always executed');
  }

  // Try-catch with async
  fetchData().then((value) {
    print('Success: $value');
  }).catchError((error) {
    print('Error: $error');
  });

  // Rethrow
  try {
    try {
      validateAge(-5);
    } catch (e) {
      print('Inner catch');
      rethrow; // Re-throw to outer catch
    }
  } catch (e) {
    print('Outer catch: $e');
  }

  // Error types:
  // - Exception: intended to be caught
  // - Error: programming errors (shouldn't be caught)
}
```

**Output:**

```
Caught: ValidationException: Age cannot be negative
Always executed
Inner catch
Outer catch: ValidationException: Age cannot be negative
Error: Exception: Network error
```

Summary

This comprehensive guide covers the fundamental aspects of Dart programming:

1.Introduction and Basics: Variables, data types, null safety, and basic syntax

2.Conditions and Loops: Control flow structures for decision making and repetition

3.Functions: Reusable code blocks with various parameter types and patterns

4.Collections: Data structures for storing and manipulating multiple values

5.File Handling: Reading from and writing to files, directory operations, and file management

6.OOP in Dart: Object-oriented programming concepts including classes, inheritance, polymorphism, and more

7.Null Safety In Dart: Understanding and working with nullable and non-nullable types

8.Asynchronous Programming: Futures, Streams, and async/await patterns

9.Useful Information:

Final Vs Const: Understanding compile-time and runtime constants

Datetime In Dart: Working with dates and times

Extension In Dart: Adding functionality to existing types

Backend in Dart: Building HTTP servers and REST APIs

Dart Interview Questions: Common questions with detailed examples

Each section includes 10 detailed examples with explanations and expected outputs, making it easy to understand and practice Dart programming concepts. These examples progress from basic to advanced, providing a solid foundation for Flutter development.

