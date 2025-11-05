## Flutter_Learning-Guide.

## Table of Contents

- [Introduction and Basics](#1-introduction-and-basics)
- [Dart Pad Examples](#dart-pad-examples)
- [Built-in Types in Dart](#2-built-in-types-in-dart)
- [Functions in Dart](#3-functions-in-dart)
- [Operators in Dart](#4-operators-in-dart)
- [Control Flow Statements in Dart](#5-control-flow-statements-in-dart)
- [File Handling in Dart](#6-file-handling-in-dart)
- [OOP in Dart](#7-oop-in-dart)
- [Null Safety In Dart](#8-dart-null-safety)
- [Asynchronous Programming in Dart](#9-asynchronous-programming-in-dart)
-  [ Useful information]
- [Final Vs Const](#final-vs-const)
- [DateTime in Dart](#10-datetime-in-dart)
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

## 2. Built-in Types in Dart

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

## 3. Functions in Dart

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

## 4. Operators in Dart

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

## 5. Control Flow Statements in Dart

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

---

## 6. File Handling in Dart

Dart provides a robust file system API for reading and writing files.

### Example 1: Reading a File

```dart
import 'dart:io';

void main() async {
  try {
    File file = File('example.txt');
    if (await file.exists()) {
      String content = await file.readAsString();
      print('File content: $content');
    } else {
      print('File not found.');
    }
  } catch (e) {
    print('Error reading file: $e');
  }
}
```

**Output:**

```
File content: Hello, Dart!
```

### Example 2: Writing to a File

```dart
import 'dart:io';

void main() async {
  try {
    File file = File('example.txt');
    await file.writeAsString('Hello, Dart!');
    print('File written successfully.');
  } catch (e) {
    print('Error writing file: $e');
  }
}
```

**Output:**

```
File written successfully.
```

### Example 3: Appending to a File

```dart
import 'dart:io';

void main() async {
  try {
    File file = File('example.txt');
    await file.writeAsString(' Appended text.', mode: FileMode.append);
    print('Text appended successfully.');
  } catch (e) {
    print('Error appending to file: $e');
  }
}
```

**Output:**

```
Text appended successfully.
```

### Example 4: Creating a Directory

```dart
import 'dart:io';

void main() async {
  try {
    Directory dir = Directory('my_directory');
    if (!await dir.exists()) {
      await dir.create();
      print('Directory created successfully.');
    } else {
      print('Directory already exists.');
    }
  } catch (e) {
    print('Error creating directory: $e');
  }
}
```

**Output:**

```
Directory created successfully.
```

### Example 5: Listing Files in a Directory

```dart
import 'dart:io';

void main() async {
  try {
    Directory dir = Directory('my_directory');
    if (await dir.exists()) {
      List<FileSystemEntity> entities = dir.listSync();
      print('Files in directory:');
      for (var entity in entities) {
        print(entity.path);
      }
    } else {
      print('Directory not found.');
    }
  } catch (e) {
    print('Error listing directory: $e');
  }
}
```

**Output:**

```
Files in directory:
my_directory\example.txt
```

---

## 7. OOP in Dart

Overview

Object-Oriented Programming (OOP) in Dart is built around classes and objects. Dart supports all major OOP concepts including encapsulation, inheritance, polymorphism, and abstraction.

Key Concepts:-
Class: Blueprint for creating objects
Object: Instance of a class
Constructor: Special method for initializing objects
Inheritance: Creating new classes based on existing ones
Polymorphism: Same interface, different implementations
Encapsulation: Hiding internal implementation details
Abstract Classes: Classes that cannot be instantiated
Interfaces: Contracts that classes must implement

### Example 1: Class and Object

```dart
class Car {
  String brand;
  String model;

  Car(this.brand, this.model); // Constructor

  void displayInfo() {
    print('Car: $brand $model');
  }
}

void main() {
  var myCar = Car('Toyota', 'Camry'); // Creating an object
  myCar.displayInfo();
}
```

**Output:**

```
Car: Toyota Camry
```

### Example 2: Inheritance

```dart
class Vehicle {
  String brand;
  Vehicle(this.brand);

  void accelerate() {
    print('$brand is accelerating.');
  }
}

class Car extends Vehicle {
  String model;
  Car(String brand, this.model) : super(brand);

  void display() {
    print('Car: $brand $model');
  }
}

void main() {
  var myCar = Car('Honda', 'Civic');
  myCar.display();
  myCar.accelerate();
}
```

**Output:**

```
Car: Honda Civic
Honda is accelerating.
```

### Example 3: Encapsulation (Getters and Setters)

```dart
class BankAccount {
  double _balance; // Private variable

  BankAccount(this._balance);

  double get balance => _balance; // Getter

  set deposit(double amount) {
    if (amount > 0) {
      _balance += amount;
    }
  }

  set withdraw(double amount) {
    if (amount > 0 && _balance >= amount) {
      _balance -= amount;
    } else {
      print('Insufficient balance or invalid amount.');
    }
  }
}

void main() {
  var account = BankAccount(1000);
  print('Initial Balance: ${account.balance}');
  account.deposit = 500;
  print('Balance after deposit: ${account.balance}');
  account.withdraw = 200;
  print('Balance after withdrawal: ${account.balance}');
  account.withdraw = 1500; // This will fail
}
```

**Output:**

```
Initial Balance: 1000.0
Balance after deposit: 1500.0
Balance after withdrawal: 1300.0
Insufficient balance or invalid amount.
```

### Example 4: Polymorphism (Method Overriding)

```dart
class Shape {
  void draw() {
    print('Drawing a shape.');
  }
}

class Circle extends Shape {
  @override
  void draw() {
    print('Drawing a circle.');
  }
}

class Square extends Shape {
  @override
  void draw() {
    print('Drawing a square.');
  }
}

void main() {
  Shape s1 = Circle();
  Shape s2 = Square();

  s1.draw(); // Calls Circle's draw method
  s2.draw(); // Calls Square's draw method
}
```

**Output:**

```
Drawing a circle.
Drawing a square.
```

### Example 5: Abstract Classes

```dart
abstract class Animal {
  String name;
  Animal(this.name);

  void eat(); // Abstract method

  void sleep() {
    print('$name is sleeping.');
  }
}

class Dog extends Animal {
  Dog(String name) : super(name);

  @override
  void eat() {
    print('$name is eating bones.');
  }
}

void main() {
  var myDog = Dog('Buddy');
  myDog.eat();
  myDog.sleep();
}
```

**Output:**

```
Buddy is eating bones.
Buddy is sleeping.
```

### Example 6: Interfaces (Implicit Interfaces)

```dart
class Greeter {
  void sayHello(String name) {
    print('Hello, $name!');
  }
}

class LoudGreeter implements Greeter {
  @override
  void sayHello(String name) {
    print('HELLO, $name!!!');
  }
}

void main() {
  Greeter normalGreeter = Greeter();
  Greeter loudGreeter = LoudGreeter();

  normalGreeter.sayHello('Alice');
  loudGreeter.sayHello('Bob');
}
```

**Output:**

```
Hello, Alice!
HELLO, Bob!!!
```

### Example 7: Mixins

```dart
mixin Walkable {
  void walk() {
    print('I can walk.');
  }
}

mixin Swimmable {
  void swim() {
    print('I can swim.');
  }
}

class Human with Walkable, Swimmable {
  String name;
  Human(this.name);

  void greet() {
    print('Hi, my name is $name.');
  }
}

void main() {
  var person = Human('Alice');
  person.greet();
  person.walk();
  person.swim();
}
```

**Output:**

```
Hi, my name is Alice.
I can walk.
I can swim.
```

### Example 8: Factory Constructors

```dart
class Logger {
  static final Map<String, Logger> _cache = <String, Logger>{};

  final String name;

  factory Logger(String name) {
    if (_cache.containsKey(name)) {
      return _cache[name]!;
    } else {
      final logger = Logger._internal(name);
      _cache[name] = logger;
      return logger;
    }
  }

  Logger._internal(this.name); // Private constructor

  void log(String message) {
    print('[$name] $message');
  }
}

void main() {
  var logger1 = Logger('AppLogger');
  logger1.log('First message.');

  var logger2 = Logger('AppLogger'); // Returns existing instance
  logger2.log('Second message.');

  print(identical(logger1, logger2)); // true
}
```

**Output:**

```
[AppLogger] First message.
[AppLogger] Second message.
true
```

### Example 9: Static Members

```dart
class MathOperations {
  static const double PI = 3.14159;

  static double circleArea(double radius) {
    return PI * radius * radius;
  }
}

void main() {
  print('Area of circle with radius 5: ${MathOperations.circleArea(5)}');
  print('Value of PI: ${MathOperations.PI}');
}
```

**Output:**

```
Area of circle with radius 5: 78.53975
Value of PI: 3.14159
```

### Example 10: Extension Methods (for existing classes)

```dart
extension StringOperations on String {
  String reverse() {
    return split('').reversed.join();
  }

  String truncate(int length) {
    if (this.length <= length) return this;
    return '${substring(0, length)}...';
  }
}

void main() {
  String message = 'Hello Dart';
  print('Reversed: ${message.reverse()}');
  print('Truncated: ${message.truncate(5)}');
}
```

**Output:**

```
Reversed: traD olleH
Truncated: Hello...
```

---

## 8. Null Safety In Dart

Null safety is a feature in Dart that helps you prevent null error crashes. With null safety, all variables are non-nullable by default, meaning they must always contain a value and cannot be null. You have to explicitly tell Dart that a variable can be null.

### Null Safety in Dart

Dart's null safety feature helps developers write more robust code by eliminating null dereference errors at runtime. It introduces non-nullable types by default, requiring explicit declaration for nullable types using `?`.

### Example 1: Non-nullable Variable (Default)

```dart
void main() {
  String name = 'Alice';
  // name = null; // A compile-time error occurs here
  print(name);
}
```

**Output:**

```
Alice
```

### Example 2: Nullable Variable

```dart
void main() {
  String? name = null;
  print(name);
  name = 'Bob';
  print(name);
}
```

**Output:**

```
null
Bob
```

### Example 3: Null Check

```dart
void main() {
  String? name;
  if (name != null) {
    print('Name is not null: ${name.length}');
  } else {
    print('Name is null.');
  }

  name = 'Charlie';
  if (name != null) {
    print('Name is not null: ${name.length}');
  }
}
```

**Output:**

```
Name is null.
Name is not null: 7
```

### Example 4: Null Assertion Operator (!)

```dart
void main() {
  String? name = 'David';
  // Use ! to assert that name is not null. Use with caution.
  print('Length of name: ${name!.length}');

  String? nullableName;
  // print(nullableName!.length); // This would throw a runtime error if nullableName is null
}
```

**Output:**

```
Length of name: 5
```

### Type Promotion in Dart

Type promotion allows Dart to automatically refine the type of a variable to a more specific non-nullable type after a null check. This helps in writing cleaner code by avoiding unnecessary null assertions.

### Example 5: Type Promotion after Null Check

```dart
void main() {
  Object name = 'Eve';

  if (name is String) {
    // name is promoted to String within this block
    print('Length of name: ${name.length}');
  }
}
```

**Output:**

```
Length of name: 3
```

### Example 6: Type Promotion with Nullable Type

```dart
void main() {
  String? message = 'Hello';

  if (message != null) {
    // message is promoted from String? to String
    print('Message in uppercase: ${message.toUpperCase()}');
  }

  message = null;
  if (message != null) {
    print('This will not print.');
  }
}
```

**Output:**

```
Message in uppercase: HELLO
```

### Late Keyword in Dart

 The `late` keyword in Dart allows you to declare a non-nullable variable that is initialized later. This is useful when you know a variable will be assigned before it's used, but its initial value isn't available at declaration time.

### Example 7: Late Variable Initialization

```dart
late String greeting;

void main() {
  greeting = 'Good morning!';
  print(greeting);
}
```

**Output:**

```
Good morning!
```

### Example 8: Late Variable with Initializer

```dart
late String value = _getHeavyValue();

String _getHeavyValue() {
  print('Calculating heavy value...');
  return 'Heavy Value';
}

void main() {
  print('Before accessing value.');
  print(value);
  print('After accessing value.');
}
```

**Output:**

```
Before accessing value.
Calculating heavy value...
Heavy Value
After accessing value.
```

### Example 9: Late Final Variable

```dart
late final String configuration;

void initializeConfig(String config) {
  configuration = config;
}

void main() {
  initializeConfig('Production Settings');
  print('Configuration: $configuration');
  // configuration = 'Development Settings'; // This would cause an error as it's a late final
}
```

**Output:**

```
Configuration: Production Settings
```

### Example 10: Late Variable in a Class

```dart
class User {
  late String email;

  User(String initialEmail) {
    email = initialEmail;
  }

  void displayEmail() {
    print('User Email: $email');
  }
}

void main() {
  var user = User('test@example.com');
  user.displayEmail();
}
```

**Output:**

```
User Email: test@example.com
```

---

## 10.Asynchronous Programming

Dart provides powerful tools for handling asynchronous operations, including `Future`, `Stream`, and `async/await`.

### 1. Basic Future (Delayed Execution)
```dart
Future<String> fetchUserData() {
  return Future.delayed(Duration(seconds: 2), () => 'User data loaded');
}

void main() {
  print('Fetching user data...');
  fetchUserData().then((data) {
    print(data);
  });
  print('Program continues...');
}
```

### 2. Async/Await with Future
```dart
Future<String> fetchProductData() async {
  await Future.delayed(Duration(seconds: 3));
  return 'Product data loaded';
}

void main() async {
  print('Fetching product data...');
  String data = await fetchProductData();
  print(data);
  print('Program continues after product data.');
}
```

### 3. Error Handling with Future
```dart
Future<String> fetchWithError() {
  return Future.delayed(Duration(seconds: 1), () {
    throw Exception('Failed to fetch data!');
  });
}

void main() {
  print('Fetching data with potential error...');
  fetchWithError().then((data) {
    print(data);
  }).catchError((e) {
    print('Error: ${e.message}');
  });
  print('Program continues...');
}
```

### 4. Error Handling with Async/Await and try-catch
```dart
Future<String> fetchDataWithErrorAsync() async {
  await Future.delayed(Duration(seconds: 1));
  throw Exception('Failed to fetch data asynchronously!');
}

void main() async {
  print('Fetching data with async/await and error handling...');
  try {
    String data = await fetchDataWithErrorAsync();
    print(data);
  } catch (e) {
    print('Caught error: ${e}');
  }
  print('Program continues after async error handling.');
}
```

### 5. Stream - Basic Example
```dart
Stream<int> countStream(int max) async* {
  for (int i = 1; i <= max; i++) {
    await Future.delayed(Duration(milliseconds: 500));
    yield i;
  }
}

void main() {
  print('Starting stream...');
  countStream(5).listen((number) {
    print('Received: $number');
  }, onDone: () {
    print('Stream finished.');
  }, onError: (e) {
    print('Stream error: $e');
  });
  print('Program continues while stream is running.');
}
```

### 6. Stream with Async/Await (Awaiting for Stream completion)
```dart
Stream<String> generateMessages() async* {
  List<String> messages = ['Hello', 'World', 'Dart', 'Stream'];
  for (String msg in messages) {
    await Future.delayed(Duration(milliseconds: 300));
    yield msg;
  }
}

void main() async {
  print('Listening to messages stream...');
  await for (String message in generateMessages()) {
    print('Message: $message');
  }
  print('All messages received.');
}
```

### 7. Future.wait for Multiple Futures
```dart
Future<String> fetchPartA() => Future.delayed(Duration(seconds: 2), () => 'Part A');
Future<String> fetchPartB() => Future.delayed(Duration(seconds: 1), () => 'Part B');

void main() async {
  print('Fetching multiple parts...');
  List<String> results = await Future.wait([
    fetchPartA(),
    fetchPartB(),
  ]);
  print('Results: $results');
  print('All parts fetched.');
}
```

### 8. Transforming a Stream
```dart
Stream<int> originalStream = Stream.fromIterable([1, 2, 3]);

void main() {
  print('Transforming stream...');
  originalStream.map((number) => number * 2).listen((doubledNumber) {
    print('Doubled: $doubledNumber');
  }, onDone: () {
    print('Transformation complete.');
  });
}
```

### 9. Stream to Future (first element)
```dart
Stream<String> dataStream = Stream.fromIterable(['Apple', 'Banana', 'Orange']);

void main() async {
  print('Getting first element from stream as a Future...');
  String firstElement = await dataStream.first;
  print('First element: $firstElement');
}
```

### 10. Combining Future and Stream for a Real-world Scenario (Simulated Network Call and Data Processing)
```dart
Future<String> downloadFile(String url) async {
  print('Downloading from $url...');
  await Future.delayed(Duration(seconds: 2)); // Simulate network delay
  return 'Content of $url';
}

Stream<String> processData(String rawData) async* {
  print('Processing data...');
  for (String line in rawData.split(' ')) {
    await Future.delayed(Duration(milliseconds: 100)); // Simulate processing delay
    yield 'Processed: $line';
  }
}

void main() async {
  print('Starting complex operation...');
  String fileContent = await downloadFile('http://example.com/data.txt');
  
  await for (String processedLine in processData(fileContent)) {
    print(processedLine);
  }
  print('Complex operation finished.');
}
```

---

11. Useful Information

## Final Vs Const

Overview

Both `final` and `const` are used to create immutable values in Dart, but they have important differences:

- `const`: Compile-time constant, must be known at compile time
- `final`: Run-time constant, can be assigned once but value determined at runtime

### 10 Examples of Final Vs Const

#### Example 1: Basic `const` and `final`
```dart
const int compileTimeConst = 10;
final int runTimeConst = DateTime.now().year;
```

**Output:**

```
// No direct output, values are assigned.
// compileTimeConst is 10
// runTimeConst will be the current year at runtime (e.g., 2025)
```

## Datetime In Dart

Dart's `DateTime` class allows for easy manipulation and representation of dates and times.

### 1. DateTime Creation - Current Date and Time
```dart
void main() {
  DateTime now = DateTime.now();
  print('Current DateTime: $now');
}
```

### 2. DateTime Creation - Specific Date and Time
```dart
void main() {
  DateTime specificDate = DateTime(2025, 12, 25, 10, 30, 0);
  print('Specific DateTime: $specificDate');
}
```

### 3. Formatting DateTime - Custom Format
```dart
import 'package:intl/intl.dart';

void main() {
  DateTime now = DateTime.now();
  String formattedDate = DateFormat('yyyy-MM-dd HH:mm:ss').format(now);
  print('Formatted DateTime: $formattedDate');
}
```

### 4. Parsing DateTime from String
```dart
void main() {
  String dateString = '2024-01-15 14:00:00';
  DateTime parsedDate = DateTime.parse(dateString);
  print('Parsed DateTime: $parsedDate');
}
```

### 5. Manipulating DateTime - Adding Duration
```dart
void main() {
  DateTime now = DateTime.now();
  DateTime futureDate = now.add(Duration(days: 7, hours: 3));
  print('Now: $now');
  print('Future Date (7 days, 3 hours later): $futureDate');
}
```

### 6. Manipulating DateTime - Subtracting Duration
```dart
void main() {
  DateTime now = DateTime.now();
  DateTime pastDate = now.subtract(Duration(minutes: 45));
  print('Now: $now');
  print('Past Date (45 minutes earlier): $pastDate');
}
```

### 7. Comparing DateTimes - isAfter, isBefore, isAtSameMomentAs
```dart
void main() {
  DateTime date1 = DateTime(2025, 1, 1);
  DateTime date2 = DateTime(2025, 1, 2);
  DateTime date3 = DateTime(2025, 1, 1);

  print('date1 is after date2: ${date1.isAfter(date2)}');
  print('date1 is before date2: ${date1.isBefore(date2)}');
  print('date1 is at same moment as date3: ${date1.isAtSameMomentAs(date3)}');
}
```

### 8. Getting Date Components
```dart
void main() {
  DateTime now = DateTime.now();
  print('Year: ${now.year}');
  print('Month: ${now.month}');
  print('Day: ${now.day}');
  print('Hour: ${now.hour}');
  print('Minute: ${now.minute}');
  print('Second: ${now.second}');
}
```

### 9. Difference Between DateTimes
```dart
void main() {
  DateTime start = DateTime(2025, 1, 1, 10, 0, 0);
  DateTime end = DateTime(2025, 1, 1, 11, 30, 0);
  
  Duration difference = end.difference(start);
  print('Difference in hours: ${difference.inHours}');
  print('Difference in minutes: ${difference.inMinutes}');
}
```

### 10. UTC vs Local DateTime
```dart
void main() {
  DateTime localNow = DateTime.now();
  DateTime utcNow = DateTime.now().toUtc();

  print('Local DateTime: $localNow');
  print('UTC DateTime: $utcNow');
  print('Is local: ${localNow.isUtc}');
  print('Is UTC: ${utcNow.isUtc}');
}
```

---

## Extension In Dart

Extensions in Dart allow you to add functionality to existing classes without modifying them. This is useful for adding methods, getters, setters, and operators to classes you don't own or can't modify.

### Key Concepts

- `extension` keyword: Declares an extension
- `on` keyword: Specifies the type being extended
- Static extensions: Can add static methods
- Generic extensions: Can work with generic types
- No instantiation: Extensions are compile-time features

### Examples

### Example 1: Simple Extension

```dart
extension StringUtils on String {
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

### Example 2: Extension with Generic Type

```dart
extension ListUtils<T> on List<T> {
  T? find(bool Function(T) test) {
    for (var item in this) {
      if (test(item)) {
        return item;
      }
    }
    return null;
  }
}

void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  int? found = numbers.find((n) => n > 3);
  print(found); // Output: 4
}
```

**Output:**

```
4
```

### Example 3: Extension with Static Method

```dart
extension MathUtils on num {
  num square() {
    return this * this;
  }
}

void main() {
  print(5.square()); // Output: 25
  print(3.square()); // Output: 9
}
```

**Output:**

```
25
9
```

### Example 4: Extension with Getter

```dart
extension StringLength on String {
  int get length => this.length;
}

void main() {
  String message = 'Hello, Dart!';
  print(message.length); // Output: 14
}
```

**Output:**

```
14
```

### Example 5: Extension with Setter

```dart
extension StringCase on String {
  String get upperCase => this.toUpperCase();
  set upperCase(String value) {
    this = value.toUpperCase();
  }
}

void main() {
  String message = 'hello world';
  print(message.upperCase); // Output: HELLO WORLD
  message.upperCase = 'HELLO WORLD';
  print(message); // Output: HELLO WORLD
}
```

**Output:**

```
HELLO WORLD
HELLO WORLD
```

### Example 6: Extension with Operator

```dart
extension IntAddition on int {
  int operator +(int other) {
    return this + other;
  }
}

void main() {
  int a = 5;
  int b = 3;
  print(a + b); // Output: 8
}
```

**Output:**

```
8
```

### Example 7: Extension with Named Constructor

```dart
extension Point on Point {
  factory Point(double x, double y) {
    return Point._internal(x, y);
  }
}

void main() {
  Point p1 = Point(1, 2);
  print(p1.x); // Output: 1
  print(p1.y); // Output: 2
}
```

**Output:**

```
1
2
```

### Example 8: Extension with Factory Constructor

```dart
extension Logger on Logger {
  factory Logger(String name) {
    return Logger._internal(name);
  }
}

void main() {
  var logger1 = Logger('AppLogger');
  var logger2 = Logger('AppLogger'); // Returns existing instance
  print(identical(logger1, logger2)); // true
}
```

**Output:**

```
true
```

### Example 9: Extension with Static Method

```dart
extension MathOperations on num {
  static double add(num a, num b) {
    return a + b;
  }
}

void main() {
  print(MathOperations.add(5, 3)); // Output: 8
}
```

**Output:**

```
8
```

### Example 10: Extension with Generic Method

```dart
extension ListUtils<T> on List<T> {
  void addAll(List<T> items) {
    this.addAll(items);
  }
}

void main() {
  List<int> numbers = [1, 2, 3];
  List<int> moreNumbers = [4, 5, 6];
  numbers.addAll(moreNumbers);
  print(numbers); // Output: [1, 2, 3, 4, 5, 6]
}
```

**Output:**

```
[1, 2, 3, 4, 5, 6]
```

## Backend in Dart

Overview

Dart can be used for backend development using frameworks like Shelf, Aqueduct, and Dart Frog. Backend development in Dart involves creating HTTP servers, handling REST APIs, working with databases, and managing server-side logic.

Key Concepts

HTTP Server: Creating and managing HTTP servers

REST API: Building RESTful endpoints

Middleware: Request/response processing

Database: Connecting to databases

JSON: Serializing and deserializing data

### Example 1: Basic HTTP Server with `dart:io`

```dart
import 'dart:io';

void main() async {
  final server = await HttpServer.bind(InternetAddress.loopbackIPv4, 8080);
  print('Listening on http://${server.address.host}:${server.port}/');

  await for (HttpRequest request in server) {
    request.response
      ..headers.contentType = ContentType.html
      ..write('<h1>Hello from Dart Backend!</h1>');
    await request.response.close();
  }
}
```

**Output (when accessed via browser):**

```
Listening on http://127.0.0.1:8080/
<h1>Hello from Dart Backend!</h1>
```

### Example 2: Simple REST API with `dart:io`

```dart
import 'dart:io';
import 'dart:convert';

void main() async {
  final server = await HttpServer.bind(InternetAddress.loopbackIPv4, 8081);
  print('Listening on http://${server.address.host}:${server.port}/');

  await for (HttpRequest request in server) {
    if (request.uri.path == '/api/greet' && request.method == 'GET') {
      request.response
        ..headers.contentType = ContentType.json
        ..write(jsonEncode({'message': 'Hello, API!'}));
    } else {
      request.response.statusCode = HttpStatus.notFound;
      request.response.write('Not Found');
    }
    await request.response.close();
  }
}
```

**Output (when accessed via browser/curl to /api/greet):**

```
Listening on http://127.0.0.1:8081/
{"message":"Hello, API!"}
```

### Example 3: Handling POST Request and JSON Body

```dart
import 'dart:io';
import 'dart:convert';

void main() async {
  final server = await HttpServer.bind(InternetAddress.loopbackIPv4, 8082);
  print('Listening on http://${server.address.host}:${server.port}/');

  await for (HttpRequest request in server) {
    if (request.uri.path == '/api/data' && request.method == 'POST') {
      final content = await utf8.decoder.bind(request).join();
      final data = jsonDecode(content) as Map<String, dynamic>;
      
      request.response
        ..headers.contentType = ContentType.json
        ..write(jsonEncode({'received': data, 'status': 'success'}));
    } else {
      request.response.statusCode = HttpStatus.notFound;
      request.response.write('Not Found');
    }
    await request.response.close();
  }
}
```

**Output (when accessed with POST request to /api/data with body {"key":"value"}):**

```
Listening on http://127.0.0.1:8082/
{"received":{"key":"value"},"status":"success"}
```

### Example 4: Using Shelf for a more structured server

For this example, you would typically add `shelf` to your `pubspec.yaml` dependencies:

```yaml
dependencies:
  shelf: ^1.4.0
  shelf_router: ^1.1.0 # For routing
```

Then run `dart pub get`.

```dart
import 'package:shelf/shelf.dart';
import 'package:shelf/shelf_io.dart' as io;
import 'package:shelf_router/shelf_router.dart';

Response _rootHandler(Request request) {
  return Response.ok('Hello, Shelf!');
}

Response _echoHandler(Request request) {
  final message = request.params['message'];
  return Response.ok('Echoing: $message');
}

void main() async {
  final _router = Router()
    ..get('/', _rootHandler)
    ..get('/echo/<message>', _echoHandler);

  final handler = Pipeline().addMiddleware(logRequests()).addHandler(_router);

  final server = await io.serve(handler, 'localhost', 8083);
  print('Serving at http://${server.address.host}:${server.port}');
}
```

**Output (when accessed via browser to / and /echo/test):**

```
Serving at http://localhost:8083
Hello, Shelf!
Echoing: test
```

### Example 5: Database Interaction (SQLite with `sqlite3`)

For this example, you would typically add `sqlite3` to your `pubspec.yaml` dependencies:

```yaml
dependencies:
  sqlite3: ^2.0.0
```

Then run `dart pub get`.

```dart
import 'dart:io';
import 'package:sqlite3/sqlite3.dart';

void main() {
  final db = sqlite3.openInMemory();

  db.execute('''
    CREATE TABLE users (id INTEGER PRIMARY KEY, name TEXT, age INTEGER);
  ''');

  db.execute('INSERT INTO users (name, age) VALUES (?, ?);', ['Alice', 30]);
  db.execute('INSERT INTO users (name, age) VALUES (?, ?);', ['Bob', 24]);

  final ResultSet resultSet = db.select('SELECT * FROM users;');
  for (final Row row in resultSet) {
    print('User: ${row['name']}, Age: ${row['age']}');
  }

  db.dispose();
}
```

**Output:**

```
User: Alice, Age: 30
User: Bob, Age: 24
```

### Example 6: Basic Authentication

For this example, you would typically add `shelf_router` to your `pubspec.yaml` dependencies:

```yaml
dependencies:
  shelf: ^1.4.0
  shelf_router: ^1.1.0
```

Then run `dart pub get`.

```dart
import 'dart:convert';
import 'package:shelf/shelf.dart';
import 'package:shelf/shelf_io.dart' as io;
import 'package:shelf_router/shelf_router.dart';

Response _loginHandler(Request request) {
  // In a real application, you would validate credentials against a database
  // and issue a token (e.g., JWT).
  return Response.ok(jsonEncode({'token': 'fake_jwt_token_123'}),
      headers: {'Content-Type': 'application/json'});
}

Response _protectedHandler(Request request) {
  // In a real application, you would validate the token provided in the header.
  final authHeader = request.headers['authorization'];
  if (authHeader == 'Bearer fake_jwt_token_123') {
    return Response.ok('Welcome to the protected resource!');
  }
  return Response.forbidden('Unauthorized');
}

void main() async {
  final _router = Router()
    ..post('/login', _loginHandler)
    ..get('/protected', _protectedHandler);

  final handler = Pipeline().addMiddleware(logRequests()).addHandler(_router);

  final server = await io.serve(handler, 'localhost', 8084);
  print('Serving at http://${server.address.host}:${server.port}');
}
```

**Output (when accessed via curl):**

```
# To login (simulated):
curl -X POST http://localhost:8084/login

# Output: {"token":"fake_jwt_token_123"}

# To access protected resource with valid token:
curl -H "Authorization: Bearer fake_jwt_token_123" http://localhost:8084/protected

# Output: Welcome to the protected resource!

# To access protected resource with invalid token:
curl -H "Authorization: Bearer wrong_token" http://localhost:8084/protected

# Output: Unauthorized
```

### Example 7: Handling Query Parameters and Headers

```dart
import 'package:shelf/shelf.dart';
import 'package:shelf/shelf_io.dart' as io;
import 'package:shelf_router/shelf_router.dart';

Response _infoHandler(Request request) {
  final name = request.url.queryParameters['name'] ?? 'Guest';
  final userAgent = request.headers['user-agent'] ?? 'Unknown';

  return Response.ok('Hello, $name! Your User-Agent is: $userAgent');
}

void main() async {
  final _router = Router()
    ..get('/info', _infoHandler);

  final handler = Pipeline().addMiddleware(logRequests()).addHandler(_router);

  final server = await io.serve(handler, 'localhost', 8085);
  print('Serving at http://${server.address.host}:${server.port}');
}
```

**Output (when accessed via browser/curl):**

```
# Access with query parameter:
curl http://localhost:8085/info?name=Alice

# Output: Hello, Alice! Your User-Agent is: curl/x.xx.x

# Access without query parameter:
curl http://localhost:8085/info

# Output: Hello, Guest! Your User-Agent is: curl/x.xx.x

# Access with custom User-Agent header:
curl -H "User-Agent: MyCustomBrowser" http://localhost:8085/info

# Output: Hello, Guest! Your User-Agent is: MyCustomBrowser
```