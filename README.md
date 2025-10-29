# Flutter_Learning-Guide

## Table of Contents

- [Introduction and Basics](#1-introduction-and-basics)
- [Dart Pad Examples](#dart-pad-examples)
- [Variables in Dart](#2-variables-in-dart)
- [Built-in Types in Dart](#3-built-in-types-in-dart)
- [Functions in Dart](#4-functions-in-dart)
- [Operators in Dart](#5-operators-in-dart)
- [Control Flow Statements in Dart](#6-control-flow-statements-in-dart)

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

### Example 1: If-Else Statement

```dart
void main() {
  int temperature = 25;
  if (temperature > 30) {
    print('It\'s hot outside!');
  } else if (temperature > 20) {
    print('It\'s warm.');
  } else {
    print('It\'s cool.');
  }
}
```

**Output:**

```
It's warm.
```