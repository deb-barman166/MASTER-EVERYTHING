# 🎯 Dart — The Ultimate Master Guide
### From Zero to 0.01% Expert — Every Concept, Flutter Secret, Async Trick & Hidden Power

> 📘 **The most complete Dart guide ever written — beginner to elite.**
>
> 🎯 *Who is this for?* Anyone who wants to go from writing Dart to **mastering** it — the language powering Flutter, the world's most popular cross-platform UI framework.
> ⏱️ *Time to complete:* Self-paced — days to months
> 🛠️ *What you'll gain:* Every syntax rule, OOP pattern, async model, sound null safety secret, and 0.01% hidden trick that separates an elite Dart developer from the rest.

---

## Table of Contents

1. [🧠 What is Dart?](#1-what-is-dart-super-simple)
2. [🌍 Why Dart Exists & Dominates](#2-why-dart-exists--dominates)
3. [🧱 Core Fundamentals](#3-core-fundamentals-beginner-level)
4. [⚙️ Complete Language System Breakdown](#4-complete-language-system-breakdown)
5. [🔄 Real-World Workflow](#5-real-world-workflow)
6. [🧪 Hands-on Practice Projects](#6-hands-on-practice-projects)
7. [⚠️ Common Mistakes](#7-common-mistakes)
8. [🔥 Pro Tips & Hidden Tricks](#8-pro-tips--hidden-tricks)
9. [🚀 Advanced Concepts](#9-advanced-concepts-expert-level)
10. [💀 0.01% Hidden Secrets](#10-001-hidden-secrets-ultra-elite)
11. [🗺️ Complete Roadmap](#11-complete-roadmap)
12. [🧩 Bonus Deep Insights](#12-bonus-deep-insights)
13. [📌 Summary & Cheat Sheet](#13-summary-quick-revision--cheat-sheet)

---

## 🧠 1. What is Dart? (Super Simple)

### The 12-Year-Old Explanation

Imagine you want to build an app that works perfectly on an iPhone, an Android phone, a Windows computer, a Mac, a Linux machine, AND inside a web browser — all from the same code. That sounds impossible, right? Well, that's exactly what **Dart** enables through the **Flutter** framework.

Dart was created by **Lars Bak** and **Kasper Lund** at Google and first appeared in 2011. At first it was meant to replace JavaScript in browsers — that didn't happen. But then in 2018, Google released **Flutter**, a UI toolkit built entirely on Dart, and everything changed. Flutter became the #1 cross-platform framework in the world, used by millions of developers to build apps for every platform from a single Dart codebase.

Dart looks familiar if you know Java, JavaScript, C#, or Kotlin — it has a C-style syntax that most programmers can pick up in hours. But underneath it has clever features: **sound null safety** (no more null crashes!), **isolates** for true parallelism, **async/await** built into the core, and a fast just-in-time (JIT) compiler for development plus an ahead-of-time (AOT) compiler for production.

### Real-Life Analogy

💡 **Think of it like this:**
Programming languages are like different car models — each one built for a specific purpose. JavaScript is a universal city car that runs everywhere but gets messy on long journeys. Java is a reliable corporate sedan — well-tested, slightly boring. Swift is a sports car built exclusively for Apple roads.

**Dart is a cross-country SUV** — equally capable on city streets (web), mountain roads (mobile), and highways (desktop). It was designed specifically so you never have to switch vehicles. One car, every terrain, and it's genuinely fun to drive.

### One-Line Definition

> **Dart** is a client-optimized, compiled, strongly typed, garbage-collected programming language developed by Google with sound null safety, isolate-based concurrency, and first-class async support — powering Flutter, the world's most popular cross-platform UI framework.

---

## 🌍 2. Why Dart Exists & Dominates

### The Problem It Solved

Before Flutter and Dart, "cross-platform mobile development" was a painful compromise. React Native used JavaScript bridges that made performance sluggish. Xamarin used C# but had poor platform integration. Every solution either sacrificed performance, developer experience, or native integration.

Dart's AOT compilation means Flutter compiles directly to native machine code — **no bridge, no interpreter, no virtual machine at runtime**. The result is 60fps (or 120fps) rendering indistinguishable from native apps. Dart's JIT compiler enables Flutter's legendary hot reload — change your code and see results in milliseconds without restarting.

### Where Dart Dominates in 2025

| Domain                          | How Dart Is Used                                                           |
|---------------------------------|----------------------------------------------------------------------------|
| Mobile (iOS + Android)          | Flutter — single codebase, native performance, #1 cross-platform framework |
| Web (Flutter Web)               | Dart compiled to JavaScript + WebAssembly                                  |
| Desktop (Windows/macOS/Linux)   | Flutter Desktop — native desktop apps from Flutter code                   |
| Backend / CLI                   | Dart servers (Shelf, Dart Frog), CLI tools with dart:io                   |
| Game Development                | Flame — 2D game engine built on Flutter/Dart                               |
| TV / Smart Displays             | Flutter on Google TV, automotive systems                                   |
| Enterprise Apps                 | Google Ads, Google Pay, Alibaba (Xianyu) — billions of users              |
| Package Ecosystem               | pub.dev — 40,000+ packages for Dart and Flutter                            |

### Why YOU Should Learn It Deeply

1. **Flutter is the #1 cross-platform framework** — one Dart codebase deploys everywhere.
2. **The job market is enormous** — Flutter/Dart developers are in massive demand globally.
3. **Sound null safety is a revelation** — Dart's system teaches you to think more carefully about data validity.
4. **WebAssembly future** — Dart + Wasm is the fastest web runtime available.
5. **Dart is genuinely elegant** — the language design, combined with Flutter's reactive model, is one of the most productive stacks ever created.

---

## 🧱 3. Core Fundamentals (Beginner Level)

---

### Concept 1: Setup, Hello World & The Dart Toolchain

```dart
// ── INSTALLATION ────────────────────────────────────────────────────────────
// Option 1: Flutter SDK (includes Dart):
//   https://docs.flutter.dev/get-started/install
//   flutter --version  →  also shows Dart version
// Option 2: Dart SDK standalone:
//   https://dart.dev/get-dart
//   dart --version

// ── RUNNING DART ────────────────────────────────────────────────────────────
// dart run file.dart          ← Run a Dart file
// dart compile exe file.dart  ← Compile to native executable
// dart compile js file.dart   ← Compile to JavaScript
// dart compile wasm file.dart ← Compile to WebAssembly
// dart run                    ← Run the project
// dart test                   ← Run all tests
// dart format .               ← Format all Dart files
// dart analyze                ← Static analysis + lint
// dart fix --apply            ← Auto-fix common issues
// dart pub get                ← Install dependencies
// dart pub upgrade            ← Upgrade dependencies
// dart pub publish            ← Publish to pub.dev

// ── YOUR FIRST DART PROGRAM ─────────────────────────────────────────────────
void main() {
  print('Hello, World!');
  print('Pi = ${3.14159.toStringAsFixed(4)}');

  var name = 'Aryan';
  var age  = 17;
  final String city = 'Kolkata';
  const int maxSize = 1000;

  var multiline = '''
  Hello, $name!
  You are $age years old.
  Living in $city.
  ''';

  print(multiline);
  print('2 + 2 = ${2 + 2}');

  // Raw strings — no escape sequences:
  var rawPath = r'C:\Users\Aryan\Documents';
  print(rawPath);  // C:\Users\Aryan\Documents
}

// ── PUBSPEC.YAML ─────────────────────────────────────────────────────────────
/*
name: my_app
description: My awesome Dart application
version: 1.0.0

environment:
  sdk: '>=3.3.0 <4.0.0'

dependencies:
  http: ^1.1.0
  path: ^1.8.3

dev_dependencies:
  test: ^1.24.0
  lints: ^3.0.0
*/
```

---

### Concept 2: Variables, Types & Sound Null Safety

```dart
void main() {
  // ── BUILT-IN TYPES ────────────────────────────────────────────────────────
  int    integer = 42;           // 64-bit signed
  double decimal = 3.14159;      // 64-bit IEEE 754
  num    flexible = 42;          // int OR double
  String text     = 'Hello';
  bool   flag     = true;

  // Number literals:
  int hex    = 0xFF;             // 255
  double sci = 1.5e10;           // 15000000000.0
  int big    = 1_000_000;        // underscores allowed

  // ── NULL SAFETY ──────────────────────────────────────────────────────────
  // Non-nullable — CANNOT be null:
  String name = 'Aryan';
  // name = null;  // ❌ COMPILE ERROR

  // Nullable — CAN be null:
  String? nullableName = null;  // ✅

  // Safe operations on nullable types:
  String? maybe = getMaybeName();

  // 1. Null check — promotes type inside block:
  if (maybe != null) {
    print(maybe.length);  // maybe is String here, not String?
  }

  // 2. Safe call ?. — returns null if receiver is null:
  print(maybe?.length);         // int?
  print(maybe?.toUpperCase());  // String?

  // 3. Null coalescing ?? — provide default:
  String display = maybe ?? 'Unknown';
  int len = maybe?.length ?? 0;

  // 4. Null coalescing assignment ??=:
  String? config;
  config ??= 'default';

  // 5. Bang operator ! — assert non-null (throws if null!):
  String forced = maybe!;  // Only use when 100% certain

  // 6. late — initialized before first use, but declared now:
  late String lateVar;
  lateVar = 'initialized';
  print(lateVar);

  // ── VAR, FINAL, CONST ─────────────────────────────────────────────────────
  var inferred = 42;             // Type locked at declaration
  final now    = DateTime.now(); // Set once at runtime
  const pi     = 3.14159;        // Compile-time constant — deeply immutable

  final list1 = [1, 2, 3];
  list1.add(4);   // ✅ final list — reference fixed, contents mutable

  const list2 = [1, 2, 3];
  // list2.add(4); // ❌ const list — contents immutable

  // ── TYPE CONVERSIONS ──────────────────────────────────────────────────────
  int i = 42;
  double d   = i.toDouble();
  int back   = d.toInt();          // truncates
  String s   = i.toString();
  int? safe  = int.tryParse('42'); // null on failure
  int strict = int.parse('42');    // throws on failure

  // ── TYPE CHECKING ─────────────────────────────────────────────────────────
  print(42 is int);     // true
  print(42 is num);     // true — int is subtype of num
  print(null is String?); // true
  print(null is String);  // false
}

String? getMaybeName() => null;
```

---

### Concept 3: Operators, Control Flow & Collections

```dart
import 'dart:collection';

void main() {
  // ── KEY OPERATORS ─────────────────────────────────────────────────────────
  int x = 10;
  print(x ~/ 3);       // 3   — integer division
  print(x % 3);        // 1   — modulo
  x ??= 100;           // assign if null

  // Cascade .. — chain on same object:
  final buf = StringBuffer()
    ..write('Hello')
    ..write(', ')
    ..writeln('World!');

  // Spread ... and null-aware spread ...?:
  var list1 = [1, 2, 3];
  List<int>? maybe;
  var combined = [0, ...list1, ...?maybe, 4]; // [0,1,2,3,4]

  // Collection if and for (Dart's unique power!):
  bool showExtras = true;
  var nav = [
    'Home',
    if (showExtras) 'Settings',
    if (showExtras) ...['A', 'B'],
    for (var i in [1, 2, 3]) 'Item$i',
  ];

  // ── SWITCH EXPRESSION (Dart 3.0+) ────────────────────────────────────────
  int score = 87;
  final grade = switch (score) {
    >= 90 => 'A',
    >= 80 && < 90 => 'B',
    >= 70 => 'C',
    _ => 'F',
  };

  // If-case pattern matching (Dart 3.0+):
  Object value = (42, 'hello');
  if (value case (int n, String s) when n > 0) {
    print('Positive int $n with string $s');
  }

  // ── LIST OPERATIONS ───────────────────────────────────────────────────────
  var nums = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3];

  nums.map((n) => n * 2).toList();
  nums.where((n) => n > 4).toList();
  nums.reduce((a, b) => a + b);          // 39
  nums.fold<int>(0, (acc, n) => acc + n); // 39
  nums.every((n) => n > 0);             // true
  nums.any((n) => n > 8);               // true
  nums.expand((n) => [n, n * 10]).toList();
  nums.take(3).toList();
  nums.skip(3).toList();
  nums.sort((a, b) => b - a);            // Sort descending in-place
  nums.toSet().toList();                 // Remove duplicates
  nums.sublist(2, 5);                   // [4,1,5]

  // ── MAP OPERATIONS ────────────────────────────────────────────────────────
  var map = {'name': 'Aryan', 'age': 17};
  map['email'] = 'a@b.com';
  map.putIfAbsent('score', () => 100);
  map.remove('age');
  map.update('name', (v) => v.toString().toUpperCase());
  map.forEach((k, v) => print('$k: $v'));
  final upper = map.map((k, v) => MapEntry(k.toUpperCase(), v));

  // ── RECORDS (Dart 3.0+) ───────────────────────────────────────────────────
  ({String name, int age}) user = (name: 'Aryan', age: 17);
  print(user.name);   // 'Aryan'
  print(user.age);    // 17

  (double, double, double) triple = computeStats([1.0, 2.0, 3.0, 4.0, 5.0]);
  var (min, max, avg) = triple;  // Destructuring!
  print('$min $max $avg');       // 1.0 5.0 3.0
}

(double, double, double) computeStats(List<double> data) {
  data.sort();
  return (data.first, data.last, data.reduce((a, b) => a + b) / data.length);
}
```

---

### Concept 4: Functions — Every Feature

```dart
// ── PARAMETER TYPES ─────────────────────────────────────────────────────────
// Named parameters with required/optional:
void createUser({
  required String name,
  required String email,
  int age = 0,
  bool isActive = true,
}) => print('$name $email $age $isActive');

// Positional optional parameters:
String repeat(String s, [int times = 1, String sep = '']) =>
    List.filled(times, s).join(sep);

// Varargs:
int sumAll(List<int> nums) => nums.fold(0, (a, b) => a + b);

// ── EXTENSION METHODS ────────────────────────────────────────────────────────
extension StringUtils on String {
  bool get isPalindrome {
    final c = toLowerCase().replaceAll(RegExp(r'[^a-z0-9]'), '');
    return c == c.split('').reversed.join();
  }

  String truncate(int max, {String ellipsis = '...'}) =>
      length <= max ? this : '${substring(0, max - ellipsis.length)}$ellipsis';

  String capitalize() =>
      isEmpty ? this : this[0].toUpperCase() + substring(1);
}

extension IntUtils on int {
  bool get isPrime {
    if (this < 2) return false;
    for (var i = 2; i * i <= this; i++) if (this % i == 0) return false;
    return true;
  }
  Duration get seconds => Duration(seconds: this);
  Duration get ms => Duration(milliseconds: this);
}

// ── GENERATORS ──────────────────────────────────────────────────────────────
// Synchronous generator — Iterable<T>:
Iterable<int> fibonacci() sync* {
  int a = 0, b = 1;
  while (true) {
    yield a;
    final t = a + b; a = b; b = t;
  }
}

// Asynchronous generator — Stream<T>:
Stream<int> countDown(int from) async* {
  for (var i = from; i >= 0; i--) {
    await Future.delayed(const Duration(milliseconds: 100));
    yield i;
  }
}

void main() {
  createUser(name: 'Aryan', email: 'a@b.com');
  print(repeat('Hi', 3, '-'));    // Hi-Hi-Hi
  print('racecar'.isPalindrome);  // true
  print(42.isPrime);              // false
  print(fibonacci().take(10).toList());
  // [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
}
```

---

🧪 **Mini Task 1:**
> Write `mostFrequent<T>(List<T> list) -> T?` that returns the most frequently occurring element (null if empty). Use a `Map<T, int>` for counting. Test with `[1, 2, 2, 3, 3, 3]` → `3`.

🧪 **Mini Task 2:**
> Write `paginate<T>(List<T> items, int pageSize) -> List<List<T>>` that splits a list into pages. Test `paginate([1..10], 3)` → `[[1,2,3],[4,5,6],[7,8,9],[10]]`.

---

## ⚙️ 4. Complete Language System Breakdown

---

### Part 1: Classes, Mixins & Advanced OOP

```dart
// ── CLASSES ───────────────────────────────────────────────────────────────────
class BankAccount {
  final String accountNumber;
  String owner;
  double _balance;
  static int _totalAccounts = 0;
  static const double overdraftLimit = -500.0;

  // Generative constructor with initializer list:
  BankAccount({
    required this.owner,
    required this.accountNumber,
    double initialBalance = 0.0,
  }) : _balance = initialBalance {
    _totalAccounts++;
    if (_balance < overdraftLimit) {
      throw ArgumentError('Initial balance below overdraft limit');
    }
  }

  // Named constructors:
  BankAccount.empty(String owner) :
    this(owner: owner, accountNumber: _generateId());

  // Factory constructor — can return subtypes:
  factory BankAccount.fromJson(Map<String, dynamic> json) => BankAccount(
    owner: json['owner'] as String,
    accountNumber: json['accountNumber'] as String,
    initialBalance: (json['balance'] as num).toDouble(),
  );

  // Getters:
  double get balance => _balance;
  bool get isOverdrawn => _balance < 0;
  String get displayBalance => '₹${_balance.toStringAsFixed(2)}';
  static int get totalAccounts => _totalAccounts;

  // Methods returning this for method chaining:
  BankAccount deposit(double amount) {
    if (amount <= 0) throw ArgumentError('Must be positive');
    _balance += amount;
    return this;
  }

  BankAccount withdraw(double amount) {
    if (_balance - amount < overdraftLimit) throw StateError('Insufficient funds');
    _balance -= amount;
    return this;
  }

  @override
  String toString() => 'BankAccount($owner: $displayBalance)';

  @override
  bool operator ==(Object other) =>
    other is BankAccount && accountNumber == other.accountNumber;

  @override
  int get hashCode => accountNumber.hashCode;

  static String _generateId() =>
    'ACC${DateTime.now().millisecondsSinceEpoch % 1000000}';
}

// ── INHERITANCE ──────────────────────────────────────────────────────────────
class SavingsAccount extends BankAccount {
  final double interestRate;

  SavingsAccount({
    required String owner,
    required String accountNumber,
    double initialBalance = 0.0,
    this.interestRate = 0.05,
  }) : super(owner: owner, accountNumber: accountNumber,
             initialBalance: initialBalance);

  void applyInterest() => deposit(balance * interestRate);

  @override
  BankAccount withdraw(double amount) {
    if (balance - amount < 500) throw StateError('Min balance ₹500 required');
    return super.withdraw(amount);
  }
}

// ── ABSTRACT CLASSES ─────────────────────────────────────────────────────────
abstract class Shape {
  double get area;
  double get perimeter;
  String describe() =>
    '${runtimeType}: area=${area.toStringAsFixed(2)}, '
    'perimeter=${perimeter.toStringAsFixed(2)}';
}

class Circle extends Shape {
  final double radius;
  Circle({required this.radius});

  @override double get area => 3.14159 * radius * radius;
  @override double get perimeter => 2 * 3.14159 * radius;
}

class Rectangle extends Shape {
  final double width, height;
  Rectangle({required this.width, required this.height});

  @override double get area => width * height;
  @override double get perimeter => 2 * (width + height);
}

// ── MIXINS ────────────────────────────────────────────────────────────────────
mixin Serializable {
  Map<String, dynamic> toJson();
  String toJsonString() => toJson().entries
      .map((e) => '"${e.key}": "${e.value}"').join(', ');
}

mixin Timestamps {
  DateTime? createdAt;
  DateTime? updatedAt;
  void markCreated() => createdAt = DateTime.now();
  void markUpdated() => updatedAt = DateTime.now();
}

mixin Auditable {
  final _log = <String>[];
  List<String> get auditLog => List.unmodifiable(_log);
  void audit(String action) => _log.add('${DateTime.now()}: $action');
}

class User with Serializable, Timestamps, Auditable {
  final String id, name, email;
  User({required this.id, required this.name, required this.email}) {
    markCreated();
    audit('Created');
  }
  @override
  Map<String, dynamic> toJson() => {'id': id, 'name': name, 'email': email};
}

// ── SEALED CLASSES (Dart 3.0+) ────────────────────────────────────────────────
sealed class NetworkResult<T> {}

class NetworkSuccess<T> extends NetworkResult<T> {
  final T data;
  const NetworkSuccess(this.data);
}

class NetworkFailure<T> extends NetworkResult<T> {
  final String message;
  final int? statusCode;
  const NetworkFailure(this.message, {this.statusCode});
}

class NetworkLoading<T> extends NetworkResult<T> {
  const NetworkLoading();
}

// Exhaustive switch — compiler verifies all cases are covered:
String describe<T>(NetworkResult<T> result) => switch (result) {
  NetworkSuccess(data: final d)         => 'Success: $d',
  NetworkFailure(message: final m)      => 'Error: $m',
  NetworkLoading()                      => 'Loading...',
};

// ── ENHANCED ENUMS (Dart 2.17+) ──────────────────────────────────────────────
enum Planet {
  mercury(3.303e+23, 2.4397e6),
  venus  (4.869e+24, 6.0518e6),
  earth  (5.976e+24, 6.37814e6),
  mars   (6.421e+23, 3.3972e6);

  final double mass;
  final double radius;
  const Planet(this.mass, this.radius);

  static const double G = 6.67430e-11;
  double get surfaceGravity => G * mass / (radius * radius);
  double weightOn(double earthWeight) => earthWeight * surfaceGravity / 9.81;
}

void main() {
  final account = BankAccount(
    owner: 'Aryan', accountNumber: 'ACC001', initialBalance: 1000)
    ..deposit(500)
    ..withdraw(200);
  print(account); // BankAccount(Aryan: ₹1300.00)

  print(describe(NetworkSuccess(42)));
  print(describe(const NetworkLoading<String>()));

  for (final p in Planet.values) {
    print('${p.name}: ${p.weightOn(75).toStringAsFixed(2)} kg');
  }
}
```

---

### Part 2: Generics & Pattern Matching

```dart
// ── GENERIC RESULT TYPE ───────────────────────────────────────────────────────
class Result<T> {
  final T? _value;
  final String? _error;
  final bool isSuccess;

  const Result._ok(T v) : _value = v, _error = null, isSuccess = true;
  const Result._err(String e) : _value = null, _error = e, isSuccess = false;

  factory Result.ok(T value) = Result._ok;
  factory Result.err(String error) = Result._err;

  T get value => isSuccess ? _value as T : throw StateError('Is failure: $_error');
  String get error => !isSuccess ? _error! : throw StateError('Is success');

  Result<R> map<R>(R Function(T) f) =>
    isSuccess ? Result.ok(f(_value as T)) : Result.err(_error!);

  Result<R> flatMap<R>(Result<R> Function(T) f) =>
    isSuccess ? f(_value as T) : Result.err(_error!);

  T getOrElse(T def) => isSuccess ? (_value as T) : def;

  void when({
    required void Function(T) ok,
    required void Function(String) err,
  }) => isSuccess ? ok(_value as T) : err(_error!);
}

// ── GENERIC CACHE ────────────────────────────────────────────────────────────
class Cache<K, V> {
  final _store = <K, ({V value, DateTime expiry})>{};
  final Duration ttl;
  Cache({required this.ttl});

  void set(K key, V value) =>
    _store[key] = (value: value, expiry: DateTime.now().add(ttl));

  V? get(K key) {
    final e = _store[key];
    if (e == null) return null;
    if (DateTime.now().isAfter(e.expiry)) { _store.remove(key); return null; }
    return e.value;
  }

  void clear() => _store.clear();
}

// ── PATTERN MATCHING (Dart 3.0+) ─────────────────────────────────────────────
void patternExamples() {
  // List patterns:
  var list = [1, 2, 3];
  switch (list) {
    case [int a, int b, int c]:
      print('Three ints: $a, $b, $c');
    case [int first, ...]:
      print('Starts with: $first');
  }

  // Map patterns:
  Map<String, dynamic> json = {'name': 'Aryan', 'age': 17};
  if (json case {'name': String name, 'age': int age}) {
    print('$name is $age');
  }

  // Object patterns:
  Object shape = Circle(radius: 5.0);
  switch (shape) {
    case Circle(radius: > 10):  print('Large circle');
    case Circle(radius: final r): print('Circle r=$r');
    case Rectangle(width: final w, height: final h): print('Rect $w×$h');
  }

  // For-in with patterns:
  final entries = {'a': 1, 'b': 2};
  for (var MapEntry(key: k, value: v) in entries.entries) {
    print('$k = $v');
  }
}

void main() {
  Result.ok(42)
    .map((n) => n * 2)
    .when(ok: (v) => print('Result: $v'), err: (e) => print('Error: $e'));

  final cache = Cache<String, String>(ttl: const Duration(minutes: 5));
  cache.set('user:1', 'Aryan');
  print(cache.get('user:1'));  // 'Aryan'

  patternExamples();
}
```

---

### Part 3: Asynchronous Programming — Complete Model

```dart
import 'dart:async';

// ── FUTURE API ────────────────────────────────────────────────────────────────
Future<String> fetchUser(int id) async {
  await Future.delayed(const Duration(milliseconds: 100));
  if (id <= 0) throw ArgumentError('Invalid ID: $id');
  return 'User$id';
}

// ── PARALLEL EXECUTION ────────────────────────────────────────────────────────
Future<void> parallelDemo() async {
  // Sequential — waits for each:
  final u1 = await fetchUser(1);
  final u2 = await fetchUser(2);

  // Parallel — both at once:
  final [a, b] = await Future.wait([fetchUser(1), fetchUser(2)]);
  print('$a, $b');

  // Future.any — first to complete wins:
  final fast = await Future.any([
    Future.delayed(const Duration(seconds: 2), () => 'slow'),
    Future.delayed(const Duration(seconds: 1), () => 'fast'),
  ]);
  print(fast);  // 'fast'

  // Timeout:
  final result = await fetchUser(1).timeout(
    const Duration(seconds: 5),
    onTimeout: () => 'Timed out',
  );
}

// ── STREAMS ───────────────────────────────────────────────────────────────────
Stream<int> counter(int max) async* {
  for (var i = 1; i <= max; i++) {
    await Future.delayed(const Duration(milliseconds: 50));
    yield i;
  }
}

Future<void> streamDemo() async {
  // await for:
  await for (final n in counter(5)) {
    print('Count: $n');
  }

  // Stream operators:
  await counter(10)
      .where((n) => n.isEven)
      .map((n) => n * n)
      .take(3)
      .forEach(print);  // 4, 16, 36

  // listen with subscription:
  final sub = counter(100).listen(
    (data) => print('Data: $data'),
    onError: (e) => print('Error: $e'),
    onDone: () => print('Done!'),
    cancelOnError: false,
  );
  await Future.delayed(const Duration(milliseconds: 200));
  await sub.cancel();

  // Broadcast stream — multiple listeners:
  final ctrl = StreamController<int>.broadcast();
  ctrl.stream.listen((v) => print('L1: $v'));
  ctrl.stream.listen((v) => print('L2: $v'));
  ctrl.add(42);
  await ctrl.close();
}

// ── COMPLETER — create Future manually ────────────────────────────────────────
Future<T> withTimeout<T>(
  Future<T> future,
  Duration timeout, {
  required T Function() onTimeout,
}) {
  final completer = Completer<T>();
  final timer = Timer(timeout, () {
    if (!completer.isCompleted) completer.complete(onTimeout());
  });
  future
    .then((v) { timer.cancel(); if (!completer.isCompleted) completer.complete(v); })
    .catchError((e, s) { timer.cancel(); if (!completer.isCompleted) completer.completeError(e, s); });
  return completer.future;
}

// ── ZONES ─────────────────────────────────────────────────────────────────────
void zoneDemo() {
  runZonedGuarded(
    () async {
      await Future.error('Something went wrong');
    },
    (error, stack) => print('Zone caught: $error'),
  );
}

void main() async {
  await parallelDemo();
  await streamDemo();
  zoneDemo();
}
```

---

### 📊 Full Dart System Overview Table

| Feature             | Dart Mechanism                              | Key Insight                                          |
|---------------------|---------------------------------------------|------------------------------------------------------|
| Null safety         | Sound null safety — T vs T? compile-time    | Compiler proves no null dereference — entire class of bugs gone |
| Memory             | Generational garbage collection             | Short-lived objects (Flutter frames) collected cheaply |
| Async model         | Isolates + async/await + Streams            | Single-threaded event loop per isolate              |
| Concurrency         | Isolates — no shared memory                 | Message passing only — no race conditions possible  |
| Generics            | Reified at runtime (not erased!)            | `is List<int>` works — unlike Java's type erasure   |
| Collections         | Collection if/for — declarative building    | Build Lists, Maps, Sets with inline conditions/loops|
| Pattern matching    | switch expressions, if-case, destructuring  | Dart 3.0+ — exhaustive, type-safe, powerful         |
| Records             | Anonymous value types `(T1, T2)`            | Zero-cost multiple return values, destructuring     |
| Extension methods   | Add methods to ANY existing type            | Reads like built-in, compiles to static calls       |
| Compilation         | JIT (dev, hot reload) + AOT (prod, fast)    | Best of both worlds — fast dev + fast prod          |

---

## 🔄 5. Real-World Workflow

---

### 🟢 Beginner Workflow: HTTP Client with JSON

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

// ── DATA MODEL ────────────────────────────────────────────────────────────────
class Post {
  final int id;
  final int userId;
  final String title;
  final String body;

  const Post({
    required this.id,
    required this.userId,
    required this.title,
    required this.body,
  });

  factory Post.fromJson(Map<String, dynamic> json) => Post(
    id:     json['id']     as int,
    userId: json['userId'] as int,
    title:  json['title']  as String,
    body:   json['body']   as String,
  );

  Map<String, dynamic> toJson() => {
    'id': id, 'userId': userId, 'title': title, 'body': body,
  };

  @override
  String toString() => 'Post($id: "$title")';
}

// ── API CLIENT ────────────────────────────────────────────────────────────────
class ApiException implements Exception {
  final String message;
  final int? statusCode;
  const ApiException(this.message, {this.statusCode});
  @override
  String toString() => 'ApiException($statusCode): $message';
}

class JsonApiClient {
  final String baseUrl;
  final http.Client _client;
  final Duration _timeout;

  JsonApiClient({
    required this.baseUrl,
    http.Client? client,
    Duration timeout = const Duration(seconds: 30),
  })  : _client = client ?? http.Client(),
        _timeout = timeout;

  Future<dynamic> get(String path) async {
    final res = await _client
        .get(Uri.parse('$baseUrl$path'), headers: {'Accept': 'application/json'})
        .timeout(_timeout);
    return _handle(res);
  }

  Future<dynamic> post(String path, Map<String, dynamic> body) async {
    final res = await _client
        .post(
          Uri.parse('$baseUrl$path'),
          headers: {
            'Content-Type': 'application/json',
            'Accept': 'application/json',
          },
          body: jsonEncode(body),
        )
        .timeout(_timeout);
    return _handle(res);
  }

  dynamic _handle(http.Response res) {
    if (res.statusCode >= 200 && res.statusCode < 300) {
      return jsonDecode(res.body);
    }
    throw ApiException('Request failed', statusCode: res.statusCode);
  }

  void dispose() => _client.close();
}

// ── REPOSITORY ────────────────────────────────────────────────────────────────
class PostRepository {
  final JsonApiClient _api;
  final _cache = <int, Post>{};

  PostRepository(this._api);

  Future<List<Post>> getAll() async {
    final data = await _api.get('/posts') as List<dynamic>;
    return data.map((j) => Post.fromJson(j as Map<String, dynamic>)).toList();
  }

  Future<Post?> getById(int id) async {
    if (_cache.containsKey(id)) return _cache[id];
    try {
      final json = await _api.get('/posts/$id') as Map<String, dynamic>;
      final post = Post.fromJson(json);
      _cache[id] = post;
      return post;
    } on ApiException catch (e) {
      if (e.statusCode == 404) return null;
      rethrow;
    }
  }
}

void main() async {
  final client = JsonApiClient(baseUrl: 'https://jsonplaceholder.typicode.com');
  final repo = PostRepository(client);

  try {
    final post = await repo.getById(1);
    print(post);
  } catch (e) {
    print('Error: $e');
  } finally {
    client.dispose();
  }
}
```

---

### 🔵 Professional Workflow: Clean Architecture Flutter App

```dart
// Clean Architecture: Data → Domain → Presentation

// ── DOMAIN LAYER ──────────────────────────────────────────────────────────────
abstract interface class UserRepository {
  Future<Result<List<UserEntity>>> getAll();
  Future<Result<UserEntity>> getById(int id);
  Future<Result<UserEntity>> create({required String name, required String email});
  Future<Result<void>> delete(int id);
}

class UserEntity {
  final int id;
  final String name;
  final String email;
  final DateTime createdAt;

  const UserEntity({
    required this.id,
    required this.name,
    required this.email,
    required this.createdAt,
  });
}

// Use cases:
class GetAllUsersUseCase {
  final UserRepository _repo;
  GetAllUsersUseCase(this._repo);
  Future<Result<List<UserEntity>>> call() => _repo.getAll();
}

class CreateUserUseCase {
  final UserRepository _repo;
  CreateUserUseCase(this._repo);

  Future<Result<UserEntity>> call({required String name, required String email}) {
    if (name.isEmpty) return Future.value(Result.err('Name is required'));
    if (!email.contains('@')) return Future.value(Result.err('Invalid email'));
    return _repo.create(name: name, email: email);
  }
}

// ── DATA LAYER ────────────────────────────────────────────────────────────────
class UserModel {
  final int id;
  final String name;
  final String email;

  const UserModel({required this.id, required this.name, required this.email});

  factory UserModel.fromJson(Map<String, dynamic> j) => UserModel(
    id: j['id'] as int,
    name: j['name'] as String,
    email: j['email'] as String,
  );

  UserEntity toEntity() => UserEntity(
    id: id, name: name, email: email, createdAt: DateTime.now(),
  );
}

class UserRepositoryImpl implements UserRepository {
  final JsonApiClient _api;
  UserRepositoryImpl(this._api);

  @override
  Future<Result<List<UserEntity>>> getAll() async {
    try {
      final data = await _api.get('/users') as List<dynamic>;
      final users = data
          .map((j) => UserModel.fromJson(j as Map<String, dynamic>).toEntity())
          .toList();
      return Result.ok(users);
    } catch (e) {
      return Result.err(e.toString());
    }
  }

  @override
  Future<Result<UserEntity>> getById(int id) async {
    try {
      final j = await _api.get('/users/$id') as Map<String, dynamic>;
      return Result.ok(UserModel.fromJson(j).toEntity());
    } catch (e) {
      return Result.err(e.toString());
    }
  }

  @override
  Future<Result<UserEntity>> create({required String name, required String email}) async {
    try {
      final j = await _api.post('/users', {'name': name, 'email': email})
          as Map<String, dynamic>;
      return Result.ok(UserModel.fromJson(j).toEntity());
    } catch (e) {
      return Result.err(e.toString());
    }
  }

  @override
  Future<Result<void>> delete(int id) async {
    try {
      await _api.get('/users/$id');
      return Result.ok(null);
    } catch (e) {
      return Result.err(e.toString());
    }
  }
}

// ── PRESENTATION LAYER ────────────────────────────────────────────────────────
// (ViewModel / BLoC — framework-agnostic version)
class UserListController {
  final GetAllUsersUseCase _getAll;
  final CreateUserUseCase _create;

  final _stateController = StreamController<UserListState>.broadcast();
  Stream<UserListState> get state => _stateController.stream;

  UserListController(this._getAll, this._create);

  Future<void> loadUsers() async {
    _stateController.add(const UserListState.loading());
    final result = await _getAll();
    result.when(
      ok: (users) => _stateController.add(UserListState.loaded(users)),
      err: (msg) => _stateController.add(UserListState.error(msg)),
    );
  }

  Future<void> addUser(String name, String email) async {
    final result = await _create(name: name, email: email);
    result.when(
      ok: (_) => loadUsers(),
      err: (msg) => _stateController.add(UserListState.error(msg)),
    );
  }

  void dispose() => _stateController.close();
}

sealed class UserListState {
  const UserListState();
  const factory UserListState.loading() = _Loading;
  const factory UserListState.loaded(List<UserEntity> users) = _Loaded;
  const factory UserListState.error(String message) = _Error;
}

class _Loading extends UserListState { const _Loading(); }
class _Loaded extends UserListState {
  final List<UserEntity> users;
  const _Loaded(this.users);
}
class _Error extends UserListState {
  final String message;
  const _Error(this.message);
}

void main() async {
  final api = JsonApiClient(baseUrl: 'https://jsonplaceholder.typicode.com');
  final repo = UserRepositoryImpl(api);
  final ctrl = UserListController(
    GetAllUsersUseCase(repo),
    CreateUserUseCase(repo),
  );

  ctrl.state.listen((state) => switch (state) {
    _Loading()            => print('Loading...'),
    _Loaded(users: var u) => print('Loaded ${u.length} users'),
    _Error(message: var m)=> print('Error: $m'),
  });

  await ctrl.loadUsers();
  api.dispose();
  ctrl.dispose();
}
```

---

## 🧪 6. Hands-on Practice Projects

---

### 🟢 Beginner Project: Expression Evaluator

```dart
import 'dart:math';

abstract class Expr { num evaluate(); }

class Number extends Expr {
  final num value;
  Number(this.value);
  @override num evaluate() => value;
}

class BinaryOp extends Expr {
  final Expr left, right;
  final String op;
  BinaryOp(this.left, this.op, this.right);

  @override
  num evaluate() => switch (op) {
    '+' => left.evaluate() + right.evaluate(),
    '-' => left.evaluate() - right.evaluate(),
    '*' => left.evaluate() * right.evaluate(),
    '/' => left.evaluate() / right.evaluate(),
    '^' => pow(left.evaluate(), right.evaluate()),
    _   => throw ArgumentError('Unknown op: $op'),
  };
}

class Parser {
  late String _src;
  int _pos = 0;

  num parse(String expr) {
    _src = expr.replaceAll(' ', '');
    _pos = 0;
    return _expr().evaluate();
  }

  Expr _expr() {
    var left = _term();
    while (_pos < _src.length && (_c == '+' || _c == '-')) {
      final op = _eat(); left = BinaryOp(left, op, _term());
    }
    return left;
  }

  Expr _term() {
    var left = _power();
    while (_pos < _src.length && (_c == '*' || _c == '/')) {
      final op = _eat(); left = BinaryOp(left, op, _power());
    }
    return left;
  }

  Expr _power() {
    var base = _primary();
    if (_pos < _src.length && _c == '^') { _eat(); base = BinaryOp(base, '^', _power()); }
    return base;
  }

  Expr _primary() {
    if (_c == '(') { _eat(); final e = _expr(); _eat(); return e; }
    if (_c == '-') { _eat(); return BinaryOp(Number(0), '-', _primary()); }
    return _number();
  }

  Expr _number() {
    final start = _pos;
    while (_pos < _src.length && RegExp(r'[\d.]').hasMatch(_c)) _pos++;
    return Number(num.parse(_src.substring(start, _pos)));
  }

  String get _c => _pos < _src.length ? _src[_pos] : '';
  String _eat() => _src[_pos++];
}

void main() {
  final p = Parser();
  for (final expr in ['2 + 3 * 4', '(2 + 3) * 4', '2 ^ 10', '-5 + 3']) {
    print('$expr = ${p.parse(expr)}');
  }
  // 2 + 3 * 4 = 14.0
  // (2 + 3) * 4 = 20.0
  // 2 ^ 10 = 1024.0
  // -5 + 3 = -2.0
}
```

✅ **You've succeeded when:** All expressions evaluate with correct operator precedence, parentheses, and negative numbers.

---

### 🔵 Intermediate Project: Reactive Observable State

```dart
import 'dart:async';

class Observable<T> {
  T _value;
  final _ctrl = StreamController<T>.broadcast();

  Observable(this._value);

  T get value => _value;
  Stream<T> get stream => _ctrl.stream;

  set value(T v) {
    _value = v;
    _ctrl.add(v);
  }

  Observable<R> map<R>(R Function(T) f) {
    final out = Observable<R>(f(_value));
    stream.listen((v) => out.value = f(v));
    return out;
  }

  Observable<T> where(bool Function(T) pred) {
    final out = Observable<T>(_value);
    stream.listen((v) { if (pred(v)) out.value = v; });
    return out;
  }

  static Observable<R> combine2<A, B, R>(
    Observable<A> a, Observable<B> b, R Function(A, B) fn) {
    final out = Observable<R>(fn(a.value, b.value));
    a.stream.listen((_) => out.value = fn(a.value, b.value));
    b.stream.listen((_) => out.value = fn(a.value, b.value));
    return out;
  }

  StreamSubscription<T> listen(void Function(T) fn,
      {bool immediate = true}) {
    if (immediate) fn(_value);
    return stream.listen(fn);
  }

  void dispose() => _ctrl.close();
}

void main() async {
  final count = Observable<int>(0);
  final doubled = count.map((n) => n * 2);
  final isPositive = count.map((n) => n > 0);
  final label = Observable.combine2(
    count, isPositive,
    (n, pos) => pos ? 'Positive: $n' : 'Non-positive: $n',
  );

  final unsub = label.listen((msg) => print('Label: $msg'));
  count.value = 5;   // Label: Positive: 5
  count.value = -3;  // Label: Non-positive: -3
  unsub.cancel();
  count.value = 10;  // No output

  print('Doubled: ${doubled.value}'); // Doubled: 20
  count.dispose();
  doubled.dispose();
  label.dispose();
}
```

---

### 🔴 Advanced Project: Isolate Worker Pool

```dart
import 'dart:isolate';
import 'dart:async';

typedef WorkFn<I, O> = O Function(I input);

class IsolatePool<I, O> {
  final int size;
  final WorkFn<I, O> work;
  final _workers = <_IsolateWorker<I, O>>[];
  final _free = <_IsolateWorker<I, O>>[];
  final _queue = <({I input, Completer<O> completer})>[];

  IsolatePool({required this.size, required this.work});

  Future<void> init() async {
    for (var i = 0; i < size; i++) {
      final w = await _IsolateWorker.spawn(work, i);
      _workers.add(w); _free.add(w);
    }
  }

  Future<O> run(I input) {
    final c = Completer<O>();
    if (_free.isNotEmpty) _dispatch(_free.removeLast(), input, c);
    else _queue.add((input: input, completer: c));
    return c.future;
  }

  Future<List<O>> runAll(List<I> inputs) => Future.wait(inputs.map(run));

  void _dispatch(_IsolateWorker<I, O> w, I input, Completer<O> c) {
    w.process(input).then((result) {
      c.complete(result);
      _free.add(w);
      if (_queue.isNotEmpty) {
        final next = _queue.removeAt(0);
        _dispatch(_free.removeLast(), next.input, next.completer);
      }
    }).catchError((e, s) {
      c.completeError(e, s);
      _free.add(w);
    });
  }

  Future<void> dispose() async {
    for (final w in _workers) await w.kill();
  }
}

class _IsolateWorker<I, O> {
  final SendPort _send;
  final Isolate _iso;

  _IsolateWorker._(this._send, this._iso);

  static Future<_IsolateWorker<I, O>> spawn<I, O>(WorkFn<I, O> fn, int id) async {
    final init = ReceivePort();
    final iso = await Isolate.spawn(_entry<I, O>, (init.sendPort, fn));
    final send = await init.first as SendPort;
    init.close();
    return _IsolateWorker._(send, iso);
  }

  static void _entry<I, O>((SendPort, WorkFn<I, O>) args) {
    final (caller, fn) = args;
    final recv = ReceivePort();
    caller.send(recv.sendPort);
    recv.listen((msg) {
      if (msg is (I, SendPort)) {
        final (input, reply) = msg;
        try { reply.send(fn(input)); }
        catch (e, s) { reply.send(_Err(e, s)); }
      }
    });
  }

  Future<O> process(I input) {
    final reply = ReceivePort();
    _send.send((input, reply.sendPort));
    return reply.first.then((v) {
      reply.close();
      if (v is _Err) throw v.error;
      return v as O;
    });
  }

  Future<void> kill() async { _iso.kill(); }
}

class _Err { final Object error; _Err(this.error, StackTrace _); }

bool _isPrime(int n) {
  if (n < 2) return false;
  for (var i = 2; i * i <= n; i++) if (n % i == 0) return false;
  return true;
}

void main() async {
  final pool = IsolatePool<int, bool>(size: 4, work: _isPrime);
  await pool.init();

  final nums = List.generate(50, (i) => i + 2);
  final results = await pool.runAll(nums);
  final primes = [for (var i = 0; i < nums.length; i++) if (results[i]) nums[i]];
  print('Primes 2-51: $primes');

  await pool.dispose();
}
```

🔥 **Challenge:** Add task cancellation via `CancelToken`, priority ordering, and progress reporting through a `Stream<double>`.

---

## ⚠️ 7. Common Mistakes

---

### ❌ Mistake 1: Using `!` Everywhere — Defeating Null Safety

```dart
// ❌ WRONG — crashes at runtime if null:
String? getName() => null;
void process() {
  final name = getName()!;          // Throws if null!
  print(name.toUpperCase());
}

// ✅ RIGHT — handle null explicitly:
void processGood() {
  final name = getName();
  if (name != null) print(name.toUpperCase()); // Promoted

  // Or with defaults:
  final display = getName() ?? 'Anonymous';
  print(display.toUpperCase());
}

// ✅ RIGHT — null-aware chaining:
void processChain() {
  final len = getName()?.length ?? 0;
  print('Length: $len');
}
```

---

### ❌ Mistake 2: Fire-and-Forget Async — Silent Errors

```dart
// ❌ WRONG — Future discarded, errors silently lost:
void save(String data) {
  writeToFile(data);  // Returns Future<void> — ignored!
}

// ❌ WRONG — missing await:
Future<void> bad() async {
  final result = fetchData();  // Missing await!
  print(result);               // Prints Future instance!
}

// ✅ RIGHT — always await:
Future<void> saveGood(String data) async {
  await writeToFile(data);
}

// ✅ RIGHT — explicit fire-and-forget:
void logEvent(String event) {
  sendToAnalytics(event).catchError((e) => print('Log error: $e'));
}

Future<void> writeToFile(String d) async {}
Future<String> fetchData() async => 'data';
Future<void> sendToAnalytics(String e) async {}
```

---

### ❌ Mistake 3: Modifying a Collection While Iterating

```dart
// ❌ WRONG — ConcurrentModificationError:
void bad() {
  final list = [1, 2, 3, 4, 5];
  for (final item in list) {
    if (item.isEven) list.remove(item); // ❌ Crash!
  }
}

// ✅ RIGHT — use removeWhere or iterate a copy:
void good() {
  var list = [1, 2, 3, 4, 5];
  list.removeWhere((n) => n.isEven);    // Safe single-pass

  // Or create new list:
  list = list.where((n) => n.isOdd).toList();
}
```

---

### ❌ Mistake 4: `dynamic` Instead of Generics

```dart
// ❌ WRONG — loses type safety:
List<dynamic> getItems() => [1, 'hello', true];
void bad() {
  final items = getItems();
  final n = items[0] as int; // Manual cast everywhere!
}

// ✅ RIGHT — use generics:
List<T> wrap<T>(T a, T b) => [a, b];

// ✅ RIGHT — use proper models for JSON:
class Item {
  final int id;
  Item({required this.id});
  factory Item.fromJson(Map<String, dynamic> j) => Item(id: j['id'] as int);
}
```

---

### ❌ Mistake 5: Inefficient String Concatenation in Loops

```dart
// ❌ WRONG — O(n²) — new String every iteration:
String build(List<String> items) {
  var result = '';
  for (final item in items) result += '$item\n';
  return result;
}

// ✅ RIGHT — StringBuffer: O(n):
String buildGood(List<String> items) {
  final buf = StringBuffer();
  for (final item in items) buf.writeln(item);
  return buf.toString();
}

// ✅ SIMPLEST — join:
String buildBest(List<String> items) => items.join('\n');
```

---

### ❌ Mistake 6: Not Using `const` for Immutable Objects

```dart
// ❌ WRONG — new object allocated every call:
Duration getDelay() => Duration(seconds: 5);

// ✅ RIGHT — const reuses same object:
const delay = Duration(seconds: 5);

// In Flutter — const widgets are cached and not rebuilt:
// ❌ Widget build(...) => Text('Hello');      // Rebuilt every time
// ✅ Widget build(...) => const Text('Hello'); // Cached forever
```

---

## 🔥 8. Pro Tips & Hidden Tricks

---

### 💎 Tip 1: Cascade Operator — Builder Pattern Made Easy

```dart
// .. chains multiple operations on the SAME object, returns the object:
final nums = <int>[]
  ..addAll([5, 3, 1, 4, 2])
  ..sort()
  ..removeWhere((n) => n.isEven);
// [1, 3, 5]

// Null-aware cascade ?.. — does nothing if receiver is null:
String? msg;
msg?..trim()..toUpperCase();  // No-op

// Complex initialization:
class Config {
  String host = 'localhost';
  int port = 5432;
  bool ssl = false;
  Map<String, String> tags = {};
}

final config = Config()
  ..host = 'db.production.com'
  ..port = 5433
  ..ssl = true
  ..tags['env'] = 'prod'
  ..tags['region'] = 'ap-south';

// The cascade pattern makes APIs incredibly fluent:
final html = StringBuffer()
  ..writeln('<!DOCTYPE html>')
  ..writeln('<html>')
  ..writeln('  <body>')
  ..writeln('    <h1>Hello Dart!</h1>')
  ..writeln('  </body>')
  ..writeln('</html>');
print(html);
```

---

### 💎 Tip 2: Collection `if`/`for` — Declarative Building

```dart
// Build collections with inline conditions and loops:
bool isAdmin = true;
bool isPremium = false;
List<String> extras = ['Analytics', 'Reports'];

final menu = [
  'Home',
  'Profile',
  if (isAdmin) 'Admin Panel',
  if (isPremium) ...extras,        // Spread conditional
  for (var i = 1; i <= 3; i++) 'Section $i',
];
// ['Home', 'Profile', 'Admin Panel', 'Section 1', 'Section 2', 'Section 3']

// Build identity maps:
final routes = {
  '/home': HomePage.new,
  '/profile': ProfilePage.new,
  if (isAdmin) '/admin': AdminPage.new,
  for (final section in ['a', 'b', 'c']) '/section/$section': () => SectionPage(section),
};

// Build complex UI trees in Flutter declaratively:
// final children = [
//   const Header(),
//   for (final user in users) UserCard(user: user),
//   if (isLoading) const Spinner(),
//   if (users.isEmpty && !isLoading) const EmptyState(),
//   const Footer(),
// ];

class HomePage {}
class ProfilePage {}
class AdminPage {}
class SectionPage { SectionPage(String s); }
```

---

### 💎 Tip 3: Extension Types — Zero-Cost Wrappers (Dart 3.3+)

```dart
// Extension types give type safety at zero runtime cost!
// They ARE the underlying type at runtime — no wrapping object.

extension type UserId(int value) implements int {
  bool get isValid => value > 0;
  String get display => 'User#$value';
}

extension type ProductId(int value) implements int {}

extension type Email(String value) implements String {
  static final _re = RegExp(r'^[\w+.-]+@[\w-]+\.\w+$');
  bool get isValid => _re.hasMatch(value);
  String get domain => value.split('@').last;
}

extension type Celsius(double value) {
  Fahrenheit toFahrenheit() => Fahrenheit(value * 9 / 5 + 32);
  String display() => '${value.toStringAsFixed(1)}°C';
}

extension type Fahrenheit(double value) {
  Celsius toCelsius() => Celsius((value - 32) * 5 / 9);
  String display() => '${value.toStringAsFixed(1)}°F';
}

void processOrder(UserId user, ProductId product) {
  print('Order for ${user.display}, product #$product');
}

void main() {
  final userId = UserId(42);
  final email  = Email('aryan@example.com');

  print(userId.isValid);   // true
  print(email.domain);     // 'example.com'
  processOrder(userId, ProductId(123));

  // Type safety — COMPILE ERRORS:
  // processOrder(ProductId(42), userId);  // ❌ Wrong order!
  // processOrder(42, 123);               // ❌ Raw ints rejected!

  final temp = Celsius(100.0);
  print(temp.toFahrenheit().display()); // 212.0°F
}
```

---

### 💎 Tip 4: `sealed`, `interface`, `final`, `base` Class Modifiers

```dart
// Dart 3.0+ class modifiers give fine-grained control:

// sealed — exhaustive pattern matching, all subtypes in same library:
sealed class AppState {}
class AppLoading extends AppState {}
class AppSuccess extends AppState { final String data; AppSuccess(this.data); }
class AppError extends AppState { final String msg; AppError(this.msg); }

// Compiler verifies exhaustiveness:
String render(AppState s) => switch (s) {
  AppLoading()               => 'Loading...',
  AppSuccess(data: final d)  => 'Success: $d',
  AppError(msg: final m)     => 'Error: $m',
};  // No default needed!

// interface — can only be implemented, not extended:
interface class HttpClient {
  Future<String> get(String url);
}

// base — can only be extended, not implemented (ensures base logic runs):
base class BaseRepository {
  Future<void> save(Object e) async { print('Saving...'); }
}

// final — can't be extended OR implemented outside this library:
final class ImmutableConfig {
  final String host;
  final int port;
  const ImmutableConfig({required this.host, required this.port});
}

// mixin class — usable as both mixin and class:
mixin class Disposable {
  bool _disposed = false;
  bool get isDisposed => _disposed;
  void dispose() { _disposed = true; onDispose(); }
  void onDispose() {}
}

class Service with Disposable {
  @override
  void onDispose() => print('Service disposed');
}
```

---

### 💎 Tip 5: `dart:isolate` — True Parallelism

```dart
import 'dart:isolate';

// Dart is single-threaded per isolate.
// For true parallel CPU work: use isolates!

// Simplest API — Isolate.run() (Dart 2.19+):
Future<void> isolateRun() async {
  final result = await Isolate.run(() {
    // Runs in separate isolate — true parallelism!
    return List.generate(100000, (i) => i + 1)
        .where((n) {
          if (n < 2) return false;
          for (var i = 2; i * i <= n; i++) if (n % i == 0) return false;
          return true;
        })
        .length;
  });
  print('Primes up to 100000: $result');
}

// Parallel chunks:
Future<void> parallelChunks() async {
  final ranges = [(2, 25000), (25001, 50000), (50001, 75000), (75001, 100000)];

  final counts = await Future.wait(
    ranges.map((r) => Isolate.run(() {
      var count = 0;
      for (var n = r.$1; n <= r.$2; n++) {
        var isPrime = n >= 2;
        for (var i = 2; i * i <= n; i++) { if (n % i == 0) { isPrime = false; break; } }
        if (isPrime) count++;
      }
      return count;
    })),
  );

  print('Total: ${counts.reduce((a, b) => a + b)}');
}

// SendPort/ReceivePort for streaming results:
Future<void> streamingIsolate() async {
  final recv = ReceivePort();
  await Isolate.spawn((SendPort port) {
    for (var n = 2; n <= 50; n++) {
      bool p = true;
      for (var i = 2; i * i <= n; i++) if (n % i == 0) { p = false; break; }
      if (p) port.send(n);
    }
    port.send(null); // Done
  }, recv.sendPort);

  await for (final msg in recv) {
    if (msg == null) break;
    print('Prime: $msg');
  }
  recv.close();
}

void main() async {
  await isolateRun();
  await parallelChunks();
  await streamingIsolate();
}
```

---

## 🚀 9. Advanced Concepts (Expert Level)

---

### Advanced Concept 1: Code Generation with build_runner

```dart
// Dart ecosystem uses code generation heavily for:
// - JSON serialization (json_serializable)
// - Immutable data classes (freezed)
// - Dependency injection (injectable + get_it)
// - Route generation (auto_route, go_router)
// - Database ORM (drift, floor)

// ── json_serializable ─────────────────────────────────────────────────────────
// pubspec.yaml:
//   dependencies: json_annotation: ^4.8.1
//   dev_dependencies: json_serializable: ^6.7.1, build_runner: ^2.4.0
//
// Then run: dart run build_runner build

// user.dart:
import 'package:json_annotation/json_annotation.dart';
part 'user.g.dart'; // Generated by build_runner

@JsonSerializable(explicitToJson: true)
class UserDto {
  final int id;

  @JsonKey(name: 'full_name')
  final String name;

  final String email;

  @JsonKey(fromJson: _dateFromString, toJson: _dateToString)
  final DateTime createdAt;

  @JsonKey(includeIfNull: false)
  final String? avatarUrl;

  const UserDto({
    required this.id,
    required this.name,
    required this.email,
    required this.createdAt,
    this.avatarUrl,
  });

  // These are generated — you don't write them:
  factory UserDto.fromJson(Map<String, dynamic> json) => _$UserDtoFromJson(json);
  Map<String, dynamic> toJson() => _$UserDtoToJson(this);

  static DateTime _dateFromString(String s) => DateTime.parse(s);
  static String _dateToString(DateTime d) => d.toIso8601String();
}

// ── freezed — immutable classes with copyWith, pattern matching ────────────────
// pubspec.yaml:
//   dependencies: freezed_annotation: ^2.4.1
//   dev_dependencies: freezed: ^2.4.5

import 'package:freezed_annotation/freezed_annotation.dart';
part 'state.freezed.dart';

@freezed
class PageState<T> with _$PageState<T> {
  const factory PageState.initial()                    = _Initial<T>;
  const factory PageState.loading()                    = _Loading<T>;
  const factory PageState.success({required T data})   = _Success<T>;
  const factory PageState.error({required String msg}) = _Error<T>;
}

// Usage — pattern matching with when():
void handleState(PageState<List<String>> state) {
  state.when(
    initial: () => print('Start'),
    loading: () => print('Loading...'),
    success: (data) => print('Items: ${data.length}'),
    error: (msg) => print('Error: $msg'),
  );

  // Or maybeWhen (only handle some cases):
  state.maybeWhen(
    success: (data) => print(data),
    orElse: () => print('Not success'),
  );
}

// ── injectable + get_it (DI) ──────────────────────────────────────────────────
import 'package:injectable/injectable.dart';

@injectable
class NetworkService {
  Future<String> fetch(String url) async => 'data from $url';
}

@injectable
class UserService {
  final NetworkService _network;
  UserService(this._network);  // Injected automatically!

  Future<String> getUser(int id) => _network.fetch('/users/$id');
}

// Placeholder part directives (would be real files in actual project):
// ignore_for_file: unused_import
```

---

### Advanced Concept 2: Custom Lint with analysis_options.yaml

```dart
// ── analysis_options.yaml ─────────────────────────────────────────────────────
/*
include: package:flutter_lints/flutter.yaml

analyzer:
  strong-mode:
    implicit-casts: false
    implicit-dynamic: false
  exclude:
    - '**.g.dart'
    - '**.freezed.dart'
  errors:
    missing_required_param: error
    missing_return: error
    dead_code: warning
    unused_import: error
    invalid_use_of_protected_member: error

linter:
  rules:
    # Avoid errors:
    - avoid_dynamic_calls
    - avoid_returning_null_for_void
    - cancel_subscriptions
    - close_sinks
    - literal_only_boolean_expressions

    # Style & readability:
    - prefer_const_constructors
    - prefer_const_declarations
    - prefer_final_fields
    - prefer_final_in_for_each
    - prefer_final_locals
    - prefer_single_quotes
    - prefer_expression_function_bodies
    - unnecessary_const
    - unnecessary_new
    - use_named_constants

    # Flutter-specific:
    - use_key_in_widget_constructors
    - sized_box_for_whitespace
    - prefer_const_constructors_in_immutables
    - avoid_unnecessary_containers
    - use_decorated_box
*/

// ── SOUND NULL SAFETY DEEP DIVE ───────────────────────────────────────────────
class NullSafetyDeep {
  // Type promotion — Dart narrows type after checks:
  void promoteDemo(String? maybe) {
    // maybe is String? here
    if (maybe == null) return;
    // maybe is now String — promoted!
    print(maybe.length); // No ? needed

    // Promotion lost after reassignment:
    // maybe = possiblyNull(); // Back to String?
  }

  // Late — proven initialized before use:
  late final String _cache;

  Future<void> initialize() async {
    final data = await loadData();
    _cache = data; // Set exactly once
  }

  String get cached => _cache; // Safe — set in initialize()

  // Null-aware spread for combining nullable lists:
  List<int> merge(List<int>? a, List<int>? b) => [...?a, ...?b];

  Future<String> loadData() async => 'loaded';
}
```

---

### Advanced Concept 3: Dart FFI — Calling C Libraries

```dart
import 'dart:ffi';
import 'dart:io';

// Dart FFI — call native C code directly from Dart
// Used for: platform integrations, performance-critical algorithms,
// wrapping existing C/C++ libraries

// Define C function signatures:
typedef NativeSqrt = Double Function(Double);
typedef DartSqrt   = double Function(double);

typedef NativeStrlen = Size Function(Pointer<Utf8>);
typedef DartStrlen   = int Function(Pointer<Utf8>);

void ffiDemo() {
  // Open system math library:
  final lib = DynamicLibrary.open(
    Platform.isMacOS ? 'libm.dylib' :
    Platform.isLinux ? 'libm.so.6' :
    'msvcrt.dll',
  );

  // Look up and call sqrt from C:
  final sqrt = lib.lookupFunction<NativeSqrt, DartSqrt>('sqrt');
  print(sqrt(144.0)); // 12.0 — native C call!

  // Allocate native memory:
  final ptr = calloc<Int32>();
  ptr.value = 42;
  print(ptr.value); // 42
  calloc.free(ptr); // Must free!

  // Work with arrays in native memory:
  final arr = calloc<Double>(5);
  for (var i = 0; i < 5; i++) arr[i] = i * i.toDouble();
  final view = arr.asTypedList(5); // Dart view — zero copy!
  print(view); // [0.0, 1.0, 4.0, 9.0, 16.0]
  calloc.free(arr);
}

// Define a C struct in Dart:
final class Vec2 extends Struct {
  @Double() external double x;
  @Double() external double y;
}

// Native struct operations — directly manipulates memory layout!
void structDemo() {
  final vec = calloc<Vec2>();
  vec.ref.x = 3.0;
  vec.ref.y = 4.0;
  final magnitude = dart.math.sqrt(vec.ref.x * vec.ref.x + vec.ref.y * vec.ref.y);
  print('Magnitude: $magnitude'); // 5.0
  calloc.free(vec);
}

import 'dart:math' as dart.math;
```

---

### ⚡ Performance & Optimization Table

| Technique                            | Impact   | When to Use                                         |
|--------------------------------------|----------|-----------------------------------------------------|
| `const` constructors and literals    | Very High | Widgets, configs — reuse same instance, avoid GC    |
| `Isolate.run()` for CPU work         | Very High | Any CPU work > 16ms (one Flutter frame)             |
| `StringBuffer` for concatenation     | High     | Loop-based string building — avoid O(n²)            |
| `Float64List`/`Int32List` typed data | Very High | Numerical computation — avoid boxing overhead       |
| Lazy generators `sync*`/`async*`    | High     | Large/infinite sequences — avoid materializing      |
| `Expando<T>` for associated data     | Medium   | Add data to objects without modifying their class   |
| `dart:collection` specialized types  | Medium   | `LinkedHashMap`, `SplayTreeMap`, `Queue` as needed  |
| Record types for multiple returns    | Low      | Zero-cost multiple return values                    |
| `collection:if` and `for`           | Medium   | Cleaner code AND avoids temporary list allocations  |
| Profile with DevTools timeline       | Critical | Find real bottlenecks — don't guess, measure!       |

---

## 💀 10. 0.01% Hidden Secrets — Ultra Elite

---

### 🔮 Secret 1: `Expando` — Attach State to Objects Without Subclassing

```dart
// Expando attaches external properties to ANY object
// WITHOUT modifying the class — uses WEAK references (won't prevent GC!)

class Node {
  final String value;
  Node(this.value);
  @override String toString() => 'Node($value)';
}

// External metadata storage:
final Expando<int>      _depth   = Expando('depth');
final Expando<bool>     _visited = Expando('visited');
final Expando<List<Node>> _kids  = Expando('children');

extension NodeExt on Node {
  int  get depth    => _depth[this]   ?? 0;
  set  depth(int d)  => _depth[this]   = d;
  bool get visited  => _visited[this]  ?? false;
  set  visited(bool v) => _visited[this] = v;
  List<Node> get children => _kids[this] ??= [];
  void addChild(Node c) => children.add(c);
}

void bfsWithExpando(Node root) {
  final queue = [root..depth = 0];
  while (queue.isNotEmpty) {
    final node = queue.removeAt(0);
    if (node.visited) continue;
    node.visited = true;
    print('${'  ' * node.depth}${node.value}');
    for (final child in node.children) {
      child.depth = node.depth + 1;
      queue.add(child);
    }
  }
}

void main() {
  final root = Node('root');
  final a = Node('A'), b = Node('B'), c = Node('C'), d = Node('D');
  root..addChild(a)..addChild(b);
  a..addChild(c)..addChild(d);
  bfsWithExpando(root);
  // root
  //   A
  //   B
  //     C
  //     D
}

// Real use cases:
// - Memoization caches that don't prevent GC
// - Graph algorithms (visited, distance, predecessor)
// - Adding metadata to third-party classes you can't modify
// - Test spies/stubs without modifying production code
```

---

### 🔮 Secret 2: Zone Customization — Intercept ALL Async Operations

```dart
import 'dart:async';

// Zones customize how ALL async code runs in a scope
// Flutter uses this for error handling — you can too!

void productionZone() {
  // Catch ALL uncaught errors — even from async callbacks deep in call stack:
  runZonedGuarded(
    () async {
      // All async errors in this zone are caught:
      Future.delayed(const Duration(milliseconds: 100), () {
        throw Exception('Async error from timer!');
      });

      await Future.delayed(const Duration(milliseconds: 200));
      throw Exception('Direct async error!');
    },
    (error, stack) {
      // This catches BOTH errors above:
      print('[ERROR] $error');
      // In Flutter: FlutterError.reportError or Sentry.captureException
    },
  );
}

// Performance monitoring zone:
Zone createMonitoredZone() {
  final Map<String, int> stats = {};

  return Zone.current.fork(
    specification: ZoneSpecification(
      scheduleMicrotask: (self, parent, zone, fn) {
        stats['microtasks'] = (stats['microtasks'] ?? 0) + 1;
        parent.scheduleMicrotask(zone, fn);
      },
      createTimer: (self, parent, zone, d, fn) {
        stats['timers'] = (stats['timers'] ?? 0) + 1;
        return parent.createTimer(zone, d, () { fn(); });
      },
      print: (self, parent, zone, line) {
        parent.print(zone, '[${DateTime.now().millisecondsSinceEpoch}] $line');
      },
    ),
    zoneValues: {'_stats': stats},
  );
}

// Zone-local values (like thread-local storage):
void zoneLocalValues() {
  final requestIdKey = Object();

  final zone = Zone.current.fork(
    zoneValues: {requestIdKey: 'req-${DateTime.now().millisecondsSinceEpoch}'},
  );

  zone.run(() async {
    // Available ANYWHERE in this zone's execution:
    final requestId = Zone.current[requestIdKey];
    print('Request: $requestId'); // Always has the ID, even 10 levels deep

    await Future.delayed(const Duration(milliseconds: 100));
    // Still has the ID after awaiting!
    print('After await: ${Zone.current[requestIdKey]}');
  });
}

void main() {
  productionZone();
  zoneLocalValues();
}
```

---

### 🔮 Secret 3: `dart:typed_data` — High-Performance Numeric Operations

```dart
import 'dart:typed_data';
import 'dart:math';

// TypedLists store UNBOXED native values — dramatically faster than List<double>!

void typedDataPerformance() {
  const n = 1000000;

  // ❌ List<double> — each double is a heap object (boxing):
  final listTime = Stopwatch()..start();
  final boxed = List<double>.generate(n, (i) => i.toDouble());
  double sum1 = 0;
  for (final v in boxed) sum1 += v;
  listTime.stop();

  // ✅ Float64List — native unboxed storage (8 bytes each, no objects):
  final arrayTime = Stopwatch()..start();
  final typed = Float64List(n);
  for (var i = 0; i < n; i++) typed[i] = i.toDouble();
  double sum2 = 0;
  for (var i = 0; i < n; i++) sum2 += typed[i];
  arrayTime.stop();

  print('List<double>: ${listTime.elapsedMilliseconds}ms');
  print('Float64List: ${arrayTime.elapsedMilliseconds}ms'); // ~5-10× faster!

  // Typed lists for ALL numeric types:
  final ints    = Int32List(100);   // int32 — C int
  final longs   = Int64List(100);   // int64 — C long
  final floats  = Float32List(100); // float
  final doubles = Float64List(100); // double
  final bytes   = Uint8List(1024);  // uint8 — for binary data

  // ByteData — structured binary parsing:
  final bd = ByteData(16);
  bd.setInt32(0, 0x48454C4C, Endian.big);   // 'HELL'
  bd.setInt32(4, 0x4F000000, Endian.big);   // 'O\0\0\0'
  bd.setFloat64(8, 3.14159265358979, Endian.little);

  print(String.fromCharCodes([bd.getUint8(0), bd.getUint8(1),
    bd.getUint8(2), bd.getUint8(3)])); // 'HELL'
  print(bd.getFloat64(8, Endian.little).toStringAsFixed(5)); // '3.14159'

  // View same buffer as different types (zero-copy!):
  final buf = Float64List(4).buffer;
  final asFloat64 = Float64List.view(buf); // 4 doubles
  final asInt32   = Int32List.view(buf);   // 8 int32s — same memory!
  asFloat64[0] = 1.0;
  // asInt32[0] and asInt32[1] now hold the IEEE 754 bits of 1.0!
}

// Matrix multiplication — Float64List vs List<List<double>>:
Float64List matMul(Float64List a, Float64List b, int n) {
  final result = Float64List(n * n);
  for (var i = 0; i < n; i++) {
    for (var k = 0; k < n; k++) {
      final aik = a[i * n + k];
      if (aik == 0.0) continue;  // Optimization for sparse matrices
      for (var j = 0; j < n; j++) {
        result[i * n + j] += aik * b[k * n + j];
      }
    }
  }
  return result;
}

// SIMD — process 4 floats simultaneously:
void simdExample() {
  final a = Float32x4(1.0, 2.0, 3.0, 4.0);
  final b = Float32x4(5.0, 6.0, 7.0, 8.0);
  final sum  = a + b;        // [6, 8, 10, 12] — 4 additions at once!
  final prod = a * b;        // [5, 12, 21, 32]
  print('x=${sum.x}, y=${sum.y}, z=${sum.z}, w=${sum.w}');

  // Int32x4 for integer SIMD:
  final ia = Int32x4(1, 2, 3, 4);
  final ib = Int32x4(4, 3, 2, 1);
  final isum = ia + ib;      // [5, 5, 5, 5]
}

void main() {
  typedDataPerformance();
  simdExample();
}
```

---

### 🔮 Secret 4: Proc Curry and Functional Pipeline with `Function`

```dart
// Dart supports first-class functions — build functional pipelines:

// Curry — partially apply a function:
Function curry(Function fn) {
  final params = (fn as dynamic).toString()
      .split('=>').first.split(',').length;

  List<dynamic> args = [];
  dynamic curried(dynamic arg) {
    args = [...args, arg];
    return args.length >= params ? Function.apply(fn, args) : curried;
  }
  return curried;
}

// Type-safe curry for 2-argument functions:
R Function(B) curry2<A, B, R>(R Function(A, B) fn, A a) => (b) => fn(a, b);

// Compose functions left-to-right:
T Function(A) compose<A, B, T>(T Function(B) g, B Function(A) f) =>
    (a) => g(f(a));

// Pipeline using extension:
extension Pipeline<T> on T {
  R pipe<R>(R Function(T) fn) => fn(this);
}

void pipelineExamples() {
  // Simple composition:
  final addOne = (int n) => n + 1;
  final double2 = (int n) => n * 2;
  final square = (int n) => n * n;

  final process = compose(compose(square, double2), addOne);
  print(process(3));  // (3+1)*2^2 = 64... wait: addOne(3)=4, double2(4)=8, square(8)=64

  // Pipeline with extension:
  final result = 'hello world dart'
      .pipe((s) => s.split(' '))
      .pipe((words) => words.map((w) => w[0].toUpperCase() + w.substring(1)))
      .pipe((words) => words.join(' '));
  print(result);  // 'Hello World Dart'

  // Partial application:
  final multiply = (int a, int b) => a * b;
  final triple = curry2(multiply, 3);
  final double3 = curry2(multiply, 2);

  print([1, 2, 3, 4, 5].map(triple).toList());  // [3, 6, 9, 12, 15]
  print([1, 2, 3, 4, 5].map(double3).toList()); // [2, 4, 6, 8, 10]

  // Memoization:
  Map<A, R> memoize<A, R>(R Function(A) fn) {
    final cache = <A, R>{};
    return cache..[A] = fn as dynamic; // Pattern for memoize
  }

  // Real memoize:
  T Function(A) memo<A, T>(T Function(A) fn) {
    final cache = <A, T>{};
    return (a) => cache.putIfAbsent(a, () => fn(a));
  }

  final memoFib = memo<int, int>((n) => n < 2 ? n : n - 1 + (n - 2));
  print(memoFib(10));  // Computed and cached

  // Retry higher-order function:
  Future<T> Function(A) withRetry<A, T>(
    Future<T> Function(A) fn, {
    int maxAttempts = 3,
    Duration delay = const Duration(seconds: 1),
  }) => (a) async {
    for (var attempt = 1; attempt <= maxAttempts; attempt++) {
      try { return await fn(a); }
      catch (e) {
        if (attempt == maxAttempts) rethrow;
        await Future.delayed(delay * attempt); // Exponential backoff
      }
    }
    throw StateError('Unreachable');
  };

  final fetchWithRetry = withRetry(
    (String url) async => 'fetched: $url',
    maxAttempts: 3,
  );
  fetchWithRetry('https://api.example.com').then(print);
}

void main() { pipelineExamples(); }
```

---

### 🔮 Secret 5: `TracePoint` Equivalent — `dart:developer` Instrumentation

```dart
import 'dart:developer' as dev;
import 'dart:async';

// dart:developer — production-grade observability tools

void developerToolsDemo() async {
  // Timeline events — visible in Flutter DevTools performance view:
  dev.Timeline.startSync('MyOperation');
  // ... do work ...
  dev.Timeline.finishSync();

  // Async timeline events:
  final task = dev.Flow.begin(id: 1);
  Future(() {
    dev.Timeline.startSync('AsyncPart', flow: dev.Flow.step(1));
    // ... work ...
    dev.Timeline.finishSync();
  }).then((_) {
    dev.Flow.end(1);
  });

  // Instant events (no duration):
  dev.Timeline.instantSync('CacheHit', arguments: {'key': 'user:42'});

  // timelineTask — wraps async operations:
  final timelineTask = dev.TimelineTask();
  timelineTask.start('FetchUser', arguments: {'id': 42});
  await Future.delayed(const Duration(milliseconds: 100));
  timelineTask.finish(arguments: {'status': 'success'});

  // Logging — structured, visible in DevTools console:
  dev.log(
    'User created',
    name: 'UserService',
    level: 800,  // WARNING level
    error: null,
    stackTrace: StackTrace.current,
  );

  // Debugger breakpoints in code:
  dev.debugger(when: true, message: 'Check this value');

  // Post event to DevTools service:
  dev.postEvent('UserAction', {'action': 'login', 'userId': 42});

  // Inspect — shows object in DevTools inspector:
  final user = {'name': 'Aryan', 'age': 17};
  dev.inspect(user);

  // registerExtension — custom DevTools service extension:
  dev.registerExtension('ext.myApp.getStats', (method, params) async {
    return dev.ServiceExtensionResponse.result('{"users": 42, "sessions": 100}');
  });
}

// UserTiming — Web Performance API equivalent:
class Stopwatch2 {
  final String label;
  final _start = Stopwatch()..start();

  Stopwatch2(this.label);

  void lap(String event) {
    dev.Timeline.instantSync('$label.$event',
      arguments: {'elapsed_ms': _start.elapsedMilliseconds});
  }

  void done() {
    _start.stop();
    dev.Timeline.instantSync('$label.done',
      arguments: {'total_ms': _start.elapsedMilliseconds});
  }
}

void main() async {
  await developerToolsDemo();
}
```

---

### 🔮 Secret 6: `dart:isolate` Ports Advanced — Bidirectional Communication

```dart
import 'dart:isolate';
import 'dart:async';

// Full bidirectional communication protocol between isolates:

enum MessageType { request, response, error, close }

class IsolateMessage {
  final int id;
  final MessageType type;
  final dynamic payload;

  IsolateMessage({required this.id, required this.type, required this.payload});
}

class IsolateChannel {
  final SendPort _send;
  final ReceivePort _recv;
  final Map<int, Completer<dynamic>> _pending = {};
  int _nextId = 0;

  IsolateChannel._(this._send, this._recv) {
    _recv.listen(_onMessage);
  }

  static Future<IsolateChannel> connect(void Function(IsolateChannel) handler) async {
    final recv = ReceivePort();
    final iso = await Isolate.spawn(_worker, (recv.sendPort, handler));

    final sendPort = await recv.first as SendPort;
    return IsolateChannel._(sendPort, recv);
  }

  static void _worker((SendPort, void Function(IsolateChannel)) args) {
    final (callerPort, handler) = args;
    final recv = ReceivePort();
    callerPort.send(recv.sendPort);

    // Create channel from worker side:
    // In real implementation, bidirectional setup here
    handler(IsolateChannel._(callerPort, recv));
  }

  Future<T> call<T>(String method, dynamic args) {
    final id = _nextId++;
    final completer = Completer<T>();
    _pending[id] = completer as Completer<dynamic>;

    _send.send(IsolateMessage(
      id: id, type: MessageType.request, payload: {'method': method, 'args': args}));

    return completer.future;
  }

  void _onMessage(dynamic msg) {
    if (msg is! IsolateMessage) return;
    final completer = _pending.remove(msg.id);
    if (completer == null) return;

    if (msg.type == MessageType.response) {
      completer.complete(msg.payload);
    } else if (msg.type == MessageType.error) {
      completer.completeError(msg.payload);
    }
  }

  void dispose() => _recv.close();
}

void main() async {
  // Usage example:
  final result = await Isolate.run(() {
    // Any computation here runs in parallel isolate:
    return List.generate(10000, (i) => i)
        .where((n) {
          for (var i = 2; i * i <= n; i++) if (n % i == 0) return false;
          return n >= 2;
        })
        .toList();
  });
  print('Found ${result.length} primes');
}
```

---

### 🔮 Secret 7: Sound Null Safety Internals — Flow Analysis

```dart
// Dart's flow analysis is more powerful than most developers realize:

class FlowAnalysisDemo {
  // 1. Promotion through control flow:
  void promote1(String? s) {
    if (s == null) throw ArgumentError('s must not be null');
    // s is String here — promoted after exception path
    print(s.length);
  }

  // 2. Promotion through assignment:
  void promote2(String? s) {
    s ??= 'default';  // After this, s is String (non-nullable)
    print(s.length);  // No ? needed
  }

  // 3. Promotion lost across closures:
  void closureCapture(String? s) {
    if (s != null) {
      // s is promoted here
      Future(() {
        // ❌ s is NOT promoted in closure — might be reassigned between now and execution
        // print(s.length);
        print(s?.length); // Must use ?. again
      });
    }
  }

  // 4. Never type — proves unreachable:
  Never assertUnreachable(String msg) => throw AssertionError(msg);

  int divide(int a, int b) {
    if (b == 0) assertUnreachable('b must not be 0');
    return a ~/ b;  // Dart knows this line is only reached if b != 0
  }

  // 5. Required named params can't be null:
  void process({required String name}) {
    // name is String, not String? — required ensures non-null
    print(name.length);
  }

  // 6. Late final — one-time assignable, always non-null:
  late final String _value;

  void setOnce(String v) {
    _value = v; // Can only be called once!
  }

  String get theValue => _value; // Non-null after setOnce()

  // 7. Definite assignment — compiler tracks all paths:
  String getGrade(int score) {
    String grade; // Not initialized!
    if (score >= 90) grade = 'A';
    else if (score >= 80) grade = 'B';
    else if (score >= 70) grade = 'C';
    else grade = 'F';
    return grade; // ✅ Compiler knows grade is ALWAYS assigned
  }
}
```

---

### 🔮 Secret 8: `dart:mirrors` — Runtime Reflection (Dart CLI Only)

```dart
import 'dart:mirrors';

// dart:mirrors is NOT available in Flutter (AOT) — Dart CLI/server only
// Use code generation (build_runner) for Flutter instead!

class Entity {
  int id;
  String name;
  DateTime? createdAt;

  Entity({required this.id, required this.name, this.createdAt});

  String greet(String message) => '$message, $name!';
}

// Generic serializer using reflection:
Map<String, dynamic> serialize(Object obj) {
  final mirror = reflect(obj);
  final classMirror = reflectClass(obj.runtimeType);

  return Map.fromEntries(
    classMirror.declarations.entries
        .where((e) => e.value is VariableMirror)
        .map((e) {
          final name = MirrorSystem.getName(e.key);
          final value = mirror.getField(e.key).reflectee;
          return MapEntry(name, value?.toString());
        }),
  );
}

// Generic instantiation from Map:
T deserialize<T>(Map<String, dynamic> data) {
  final cm = reflectClass(T);
  final constructor = cm.declarations.values
      .whereType<MethodMirror>()
      .firstWhere((m) => m.isConstructor && m.parameters.isNotEmpty);

  final args = constructor.parameters.map((p) {
    final name = MirrorSystem.getName(p.simpleName);
    return data[name];
  }).toList();

  return cm.newInstance(const Symbol(''), args).reflectee as T;
}

// Call method by name:
dynamic callMethod(Object obj, String methodName, List<dynamic> args) {
  final mirror = reflect(obj);
  return mirror.invoke(Symbol(methodName), args).reflectee;
}

void main() {
  final e = Entity(id: 1, name: 'Aryan', createdAt: DateTime.now());

  // Serialize:
  print(serialize(e)); // {id: 1, name: Aryan, createdAt: ...}

  // Call method dynamically:
  final result = callMethod(e, 'greet', ['Hello']);
  print(result); // 'Hello, Aryan!'

  // List all methods:
  final classMirror = reflectClass(Entity);
  for (final decl in classMirror.declarations.values) {
    if (decl is MethodMirror && !decl.isConstructor) {
      print('Method: ${MirrorSystem.getName(decl.simpleName)}');
    }
  }
}
```

---

### 🔮 Secret 9: `interface class` and Protocol-Like Design (Dart 3.0+)

```dart
// Dart 3.0 class modifiers enable fine-grained API design:

// interface class — implementers MUST provide every method (like Java interface):
interface class Comparable2<T> {
  int compareTo(T other);
  bool operator <(T other) => compareTo(other) < 0;
  bool operator >(T other) => compareTo(other) > 0;
  bool operator <=(T other) => compareTo(other) <= 0;
  bool operator >=(T other) => compareTo(other) >= 0;
}

// base class — provides implementation that CAN'T be bypassed:
base class Observable2<T> {
  T _value;
  final _listeners = <void Function(T)>[];

  Observable2(this._value);

  T get value => _value;

  void addListener(void Function(T) fn) => _listeners.add(fn);
  void removeListener(void Function(T) fn) => _listeners.remove(fn);

  set value(T newVal) {
    _value = newVal;
    for (final fn in _listeners) fn(newVal); // Can't be bypassed!
  }
}

// Combining modifiers for powerful constraints:
abstract final class Singleton {
  // abstract: has abstract members
  // final: can't be extended or implemented outside this library
  static final _instances = <Type, Singleton>{};

  Singleton._();

  factory Singleton.of<T extends Singleton>(T Function() create) {
    return _instances.putIfAbsent(T, create) as T;
  }
}

// mixin class — flexible reuse:
mixin class JsonMixin {
  Map<String, dynamic> toJson();  // Subclasses must implement

  String toJsonString() {
    final buf = StringBuffer('{');
    var first = true;
    for (final e in toJson().entries) {
      if (!first) buf.write(',');
      buf.write('"${e.key}":');
      if (e.value is String) buf.write('"${e.value}"');
      else buf.write(e.value);
      first = false;
    }
    buf.write('}');
    return buf.toString();
  }
}

class Config with JsonMixin {
  final String host;
  final int port;
  Config({required this.host, required this.port});

  @override
  Map<String, dynamic> toJson() => {'host': host, 'port': port};
}

void main() {
  final cfg = Config(host: 'localhost', port: 5432);
  print(cfg.toJsonString()); // {"host":"localhost","port":5432}
}
```

---

### 🔮 Secret 10: `Uint8List` and Binary Protocol Parsing

```dart
import 'dart:typed_data';
import 'dart:convert';

// Parse and build binary protocols — network packets, file formats, etc.

class BinaryWriter {
  final _buffer = BytesBuilder();

  void writeUint8(int value) => _buffer.addByte(value & 0xFF);
  void writeUint16(int value) {
    _buffer.addByte((value >> 8) & 0xFF);
    _buffer.addByte(value & 0xFF);
  }
  void writeUint32(int value) {
    for (var shift = 24; shift >= 0; shift -= 8) _buffer.addByte((value >> shift) & 0xFF);
  }
  void writeFloat64(double value) {
    final bd = ByteData(8)..setFloat64(0, value, Endian.big);
    _buffer.add(bd.buffer.asUint8List());
  }
  void writeString(String s) {
    final bytes = utf8.encode(s);
    writeUint16(bytes.length);
    _buffer.add(bytes);
  }
  void writeBytes(Uint8List bytes) {
    writeUint32(bytes.length);
    _buffer.add(bytes);
  }

  Uint8List build() => _buffer.toBytes();
}

class BinaryReader {
  final ByteData _bd;
  int _pos = 0;

  BinaryReader(Uint8List bytes) : _bd = bytes.buffer.asByteData();

  int readUint8() => _bd.getUint8(_pos++);
  int readUint16() {
    final v = _bd.getUint16(_pos, Endian.big);
    _pos += 2; return v;
  }
  int readUint32() {
    final v = _bd.getUint32(_pos, Endian.big);
    _pos += 4; return v;
  }
  double readFloat64() {
    final v = _bd.getFloat64(_pos, Endian.big);
    _pos += 8; return v;
  }
  String readString() {
    final len = readUint16();
    final bytes = Uint8List.view(_bd.buffer, _pos, len);
    _pos += len;
    return utf8.decode(bytes);
  }
  Uint8List readBytes() {
    final len = readUint32();
    final bytes = Uint8List.view(_bd.buffer, _pos, len);
    _pos += len;
    return bytes;
  }
  bool get hasMore => _pos < _bd.lengthInBytes;
}

// Custom protocol message:
class Message {
  final int version;
  final String type;
  final double timestamp;
  final String payload;

  const Message({
    required this.version,
    required this.type,
    required this.timestamp,
    required this.payload,
  });

  Uint8List serialize() {
    final w = BinaryWriter()
      ..writeUint8(version)
      ..writeString(type)
      ..writeFloat64(timestamp)
      ..writeString(payload);
    return w.build();
  }

  factory Message.deserialize(Uint8List bytes) {
    final r = BinaryReader(bytes);
    return Message(
      version:   r.readUint8(),
      type:      r.readString(),
      timestamp: r.readFloat64(),
      payload:   r.readString(),
    );
  }

  @override
  String toString() =>
    'Message(v=$version, type=$type, ts=$timestamp, payload=$payload)';
}

void main() {
  final msg = Message(
    version: 1, type: 'LOGIN',
    timestamp: DateTime.now().millisecondsSinceEpoch.toDouble(),
    payload: '{"userId": 42, "token": "abc123"}',
  );

  final bytes = msg.serialize();
  print('Serialized: ${bytes.length} bytes');

  final parsed = Message.deserialize(bytes);
  print(parsed);
}
```

---

## 🗺️ 11. Complete Roadmap

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — FOUNDATION (Week 1-3)
├── Week 1: Setup, null safety, types, variables (final/const/late/var)
├── Week 2: Functions, lambdas, extension methods, collections
└── Week 3: Classes, mixins, abstract, enums, cascade operator
    └── Project: CLI todo app, text processor, JSON parser

PHASE 2 — DART IDIOMS (Week 4-7)
├── Week 4: Generics, records, pattern matching (Dart 3.0+)
├── Week 5: Async/await deeply — Futures, Streams, Completers
├── Week 6: Isolates, dart:typed_data, dart:io for CLI/server
└── Week 7: Sealed classes, class modifiers, extension types (Dart 3.3+)
    └── Project: CLI calculator, reactive state machine, isolate pool

PHASE 3 — FLUTTER DEVELOPMENT (Week 8-12)
├── Week 8:  Flutter basics — widgets, State, StatelessWidget, StatefulWidget
├── Week 9:  Navigation (GoRouter), layouts, animations, themes
├── Week 10: State management — Riverpod/BLoC/Provider patterns
├── Week 11: Networking, JSON, local storage (SharedPrefs, SQLite/drift)
└── Week 12: Testing — unit, widget, integration tests with mocking
    └── Project: Full Flutter app with auth + REST API + local caching

PHASE 4 — ADVANCED DART (Month 4-5)
├── Month 4: Code generation (build_runner, json_serializable, freezed)
├── Month 5: Dart FFI, dart:developer, performance profiling, DevTools
    └── Project: Published pub.dev package OR production Flutter app

PHASE 5 — EXPERT / 0.01% (Month 6+)
├── Dart compiler internals — AOT vs JIT, tree shaking, Wasm
├── Custom lint rules, build system customization
├── Flutter engine deep dive — rendering pipeline, Skia/Impeller
├── Dart on server (Dart Frog, Shelf) + shared Flutter/server code
└── Contribute to dart-lang or flutter/packages
    └── Project: Full-stack Dart app — Flutter frontend + Dart server sharing models
```

---

### 🏁 Milestone Checklist

- [ ] I understand why null safety matters and never use `!` without justification
- [ ] I write all immutable values with `final` or `const` by default
- [ ] I use `async`/`await` correctly and always handle errors
- [ ] I know when to use `Future` vs `Stream` vs `Isolate`
- [ ] I understand Dart's single-threaded event loop model
- [ ] I can build a complex Flutter UI with proper state management
- [ ] I use `sealed` classes for exhaustive state machines
- [ ] I know collection `if`/`for` and use them in Flutter widget trees
- [ ] I have published a package to pub.dev
- [ ] I understand the difference between JIT and AOT compilation
- [ ] I've profiled a Flutter app with DevTools and fixed a jank issue
- [ ] I use records for multiple return values instead of maps
- [ ] I've written unit tests, widget tests, and integration tests
- [ ] I understand isolates and use `Isolate.run()` for heavy CPU work

---

## 🧩 12. Bonus Deep Insights

---

### 🔮 Mental Model: "Dart Is Designed for UI — Everything Reflects That"

Every major design decision in Dart traces back to one purpose: **building smooth, responsive user interfaces**.

- **JIT for development** → Hot reload in milliseconds. Change widget code and see instantly.
- **AOT for production** → Zero startup lag, deterministic performance.
- **Single-threaded event loop** → No UI thread vs background thread — your widget code never races with itself.
- **Isolates for CPU work** → Heavy computation never blocks the 60fps rendering loop.
- **Sound null safety** → No NullPointerException crashes in production.
- **const widgets** → Identical widget subtrees reuse the same object — no GC pressure.
- **Generational GC** → Flutter creates and destroys millions of widget objects per second. Dart's GC is tuned for this exact pattern.

When you understand Dart through this lens, every "quirk" becomes intentional elegance.

---

### 🤫 Deep Insight 1: The Event Loop — Why Dart Async Works

Dart is single-threaded per isolate but handles thousands of concurrent operations. How?

```
Dart Event Loop:

Event Queue:  [tap] [network response] [timer] [frame callback]
                ↓
           Event Handler
           runs to completion
                ↓
Microtask Queue: [then callbacks] [Future.value] [scheduleMicrotask]
   (drains COMPLETELY before next event)
                ↓
           next event...
```

**Key rules:**
1. Microtasks (`.then()`, `Future.value()`) run before the next event
2. Event loop never preempts — a long synchronous operation BLOCKS everything
3. `await` suspends the current function but does NOT block the event loop
4. Only `Isolate.run()` gives true parallelism

This is why `await Future.delayed(Duration.zero)` can "yield" back to the event loop — it schedules a microtask, giving other events a chance to run.

---

### 🤫 Deep Insight 2: Dart's Generics Are Reified — Unlike Java

In Java, `List<String>` and `List<Integer>` are both `List` at runtime — type information is erased. In Dart, types are **reified** — preserved at runtime:

```dart
// This WORKS in Dart, FAILS in Java at runtime:
void printType<T>(List<T> list) {
  print(list is List<int>);   // true if T is int
  print(list is List<String>); // true if T is String
  print(T);                    // Prints the actual type name
}

printType<int>([1, 2, 3]);    // true, false, int
printType<String>(['a', 'b']); // false, true, String
```

This enables real runtime type checking, better error messages, and the ability to use type parameters in `is` checks — something impossible in Java without workarounds.

---

### 🤫 Deep Insight 3: Why Flutter Chose Dart Over JavaScript and Others

Flutter's team evaluated many languages before choosing Dart:

1. **Not JavaScript** — No JIT warm-up lag, sound type system, no `undefined` vs `null`, better performance
2. **Not TypeScript** — Same JS performance issues, runtime type erasure
3. **Not Kotlin** — JVM startup overhead, no web/iOS targets at the time
4. **Not Swift** — Apple-only at the time, no web compilation
5. **Dart won because:**
   - JIT + AOT in one language (unique)
   - Google owned it — could customize the compiler
   - No browser sandbox restrictions
   - Clean async model for reactive UI
   - Fast object allocation and GC (generational) for millions of widgets

---

### 🧠 The Big Picture — Dart in 2025 and Beyond

```
Dart's evolution:
  2011: Dart 1.0 — meant to replace JavaScript in Chrome
  2013: Dart compile-to-JS focus — pragmatic pivot
  2018: Flutter beta — everything changes!
  2020: Dart 2.12 — Sound null safety — huge upgrade
  2021: Dart 2.13+ — Type aliases, FFI improvements
  2022: Dart 2.17 — Enhanced enums, super parameters
  2023: Dart 3.0 — Patterns, records, class modifiers — biggest release ever
  2024: Dart 3.3 — Extension types, inline classes, Wasm GA
  2025: Dart 3.x+ — Native interop improvements, compile-time metaprogramming

Dart ecosystem in 2025:
  Mobile:  Flutter (iOS + Android) — #1 cross-platform
  Web:     Flutter Web + Wasm — fastest web UI framework
  Desktop: Flutter Desktop (Windows, macOS, Linux)
  Server:  Dart Frog, Shelf, Jaspr
  Games:   Flame engine
  CLI:     dart:io, process_run, args package

Flutter package ecosystem:
  State:    Riverpod, BLoC, GetX, Provider, MobX
  Network:  Dio, http, Retrofit
  Database: drift, isar, hive, sqflite, supabase
  UI:       Material 3, Cupertino, FluentUI, custom
  Auth:     firebase_auth, local_auth, oauth2
  Media:    camera, video_player, just_audio, image_picker
  Testing:  mockito, mocktail, golden_toolkit, integration_test
  DevTools: Flutter DevTools, Dart DevTools, very_good_analysis

The future:
  ✅ Wasm compilation GA — Dart in browser at near-native speed
  ✅ Dart Native Interop — improved C/Swift/Kotlin FFI
  ✅ Flutter GPU API — direct GPU access for games/graphics
  ✅ Dart Macros (experimental) — compile-time metaprogramming
  ✅ Pattern matching evolution — more powerful with each release
  ✅ Smaller binary sizes through improved tree shaking
```

---

## 📌 13. Summary (Quick Revision & Cheat Sheet)

---

### Core Concepts (1-line each)

| Concept              | What It Means                                                             |
|----------------------|---------------------------------------------------------------------------|
| Null safety          | `T` never null; `T?` can be null — compiler proves no NPE at compile time |
| `final` vs `const`   | `final` = set once at runtime; `const` = compile-time, deeply immutable  |
| `late`               | Non-nullable var initialized after declaration — Dart tracks it's set     |
| Cascade `..`         | Chain multiple operations on same object — returns the object             |
| Collection if/for    | Build Lists/Maps/Sets with inline conditions/loops — only in Dart!       |
| Isolates             | True parallelism — no shared memory, message passing only                |
| `async`/`await`      | Sugar over Future — suspends without blocking the event loop              |
| Streams              | Multiple async values over time — like async `Iterable`                  |
| sealed class         | Closed hierarchy — `switch` is exhaustive, compiler verifies all cases   |
| Records              | `(Type1, Type2)` — anonymous value types, zero-cost multiple returns     |
| Extension types      | `extension type T(U)` — zero-cost type wrapper, type-safe at compile time|
| Generics             | Reified at runtime — `is List<int>` works, unlike Java's type erasure    |

---

### The 10 Things to Remember

1. ✅ **`final` by default** — only `var` when mutation is genuinely needed
2. ✅ **Never `!` without certainty** — prefer `??`, `?.`, `if (x != null)` or `guard` pattern
3. ✅ **Always `await` your Futures** — unawaited futures swallow errors silently
4. ✅ **`Isolate.run()` for any CPU work > 16ms** — protects the 60fps rendering loop
5. ✅ **`const` constructors wherever possible** — reduces GC pressure, especially in Flutter
6. ✅ **`StringBuffer` for loop string building** — avoids O(n²) concatenation
7. ✅ **`sealed` classes for state machines** — compiler checks exhaustiveness
8. ✅ **Records for multiple return values** — cleaner than custom classes for simple data
9. ✅ **Use `where()` instead of iteration + `remove()`** — never modify while iterating
10. ✅ **Profile before optimizing** — use Flutter DevTools timeline before guessing

---

### Quick Reference Cheat Sheet

```dart
// ── VARIABLES ──────────────────────────────────────────────────────────────────
var name    = 'Aryan';         // Inferred type, reassignable
final now   = DateTime.now();  // Set once at runtime
const pi    = 3.14159;         // Compile-time constant
late String deferred;          // Set before first use

// ── NULL SAFETY ────────────────────────────────────────────────────────────────
String? maybe;
maybe?.length            // null if maybe is null
maybe ?? 'default'       // 'default' if null
maybe ??= 'value';       // Assign if null
maybe!.length            // Throws if null — use rarely!
if (maybe != null) { maybe.length; }  // Promoted to String

// ── TYPES ─────────────────────────────────────────────────────────────────────
int     i = 42;           double  d = 3.14;
String  s = 'text';       bool    b = true;
List<int> l = [1,2,3];   Map<String,int> m = {'a':1};
Set<String> st = {'x'};  (int, String) rec = (1, 'a');

// ── STRING INTERPOLATION ──────────────────────────────────────────────────────
'Hello, $name!'           // Simple variable
'Sum: ${1 + 2}'           // Expression
r'Raw: \n is literal'     // Raw string — no escapes

// ── COLLECTIONS ────────────────────────────────────────────────────────────────
[1,2,3].map((n) => n*2).toList()          // [2,4,6]
[1,2,3].where((n) => n>1).toList()        // [2,3]
[1,2,3].reduce((a,b) => a+b)              // 6
[1,2,3].fold(0, (acc,n) => acc+n)        // 6
[1,2,3].every((n) => n>0)                // true
[1,2,3].any((n) => n>2)                  // true
[1,2,3].expand((n) => [n,n]).toList()    // [1,1,2,2,3,3]
[3,1,2]..sort()                          // [1,2,3] in-place
{...[1,2,3], ...[4,5,6]}                // {1,2,3,4,5,6} — spread
[1, if (true) 2, for(var i in [3,4]) i] // [1,2,3,4]

// ── MAP OPERATIONS ──────────────────────────────────────────────────────────
m['key']                         // Null if missing
m['key'] = value;                // Set
m.putIfAbsent('k', () => 0);    // Add if absent
m.update('k', (v) => v+1);      // Update existing
m.remove('key');                 // Remove
m.entries.map((e) => ...);      // Iterate entries

// ── FUNCTIONS ──────────────────────────────────────────────────────────────
// Named params:
void f({required String a, int b = 0}) {}
f(a: 'x', b: 1);

// Positional optional:
void g(String a, [int b = 0]) {}
g('x');  g('x', 1);

// Lambdas:
var fn = (int n) => n * 2;
var fn2 = (int n) { return n * 2; };
list.map((n) => n * 2);
list.forEach(print);   // Method reference

// Extension methods:
extension on String {
  bool get isPalindrome => this == split('').reversed.join();
}

// Generators:
Iterable<int> gen() sync* { yield 1; yield 2; yield 3; }
Stream<int> aGen() async* { yield 1; await Future.delayed(1.ms); yield 2; }

// ── CLASSES ──────────────────────────────────────────────────────────────────
class MyClass extends Parent with MixinA, MixinB implements Interface {
  final String name;                  // Immutable field
  String _private = '';              // Private (file-level)
  static int count = 0;              // Class variable

  MyClass({required this.name});     // Generative constructor
  MyClass.named() : this(name: ''); // Named constructor
  factory MyClass.create() => MyClass(name: ''); // Factory

  String get upper => name.toUpperCase(); // Getter
  set label(String v) => _private = v;    // Setter

  @override String toString() => 'MyClass($name)';
}

// ── ASYNC ──────────────────────────────────────────────────────────────────
// Future:
Future<String> fetch() async {
  await Future.delayed(Duration(seconds: 1));
  return 'done';
}
final result = await fetch();
final [a, b] = await Future.wait([fetch(), fetch()]); // Parallel!

// Stream:
Stream<int> count(int n) async* {
  for (var i = 0; i < n; i++) { yield i; await Future.delayed(50.ms); }
}
await for (final v in count(5)) { print(v); }
await count(10).where((n) => n.isEven).forEach(print);

// Error handling:
try {
  await fetch();
} on NetworkException catch (e) {
  print(e.message);
} catch (e, stack) {
  print('$e\n$stack');
} finally {
  print('cleanup');
}

// ── PATTERN MATCHING (Dart 3.0+) ──────────────────────────────────────────────
final grade = switch (score) { >= 90 => 'A', >= 80 => 'B', _ => 'F' };

switch (value) {
  case [int a, int b]: print('Two ints: $a, $b');
  case {'name': String n}: print('Has name: $n');
  case Circle(radius: > 10): print('Big circle');
  case (int n, String s): print('Record: $n, $s');
}

if (value case [int first, ...]) { print('List starting with $first'); }

// ── SEALED CLASSES ────────────────────────────────────────────────────────────
sealed class State {}
class Loading extends State {}
class Success extends State { final String data; Success(this.data); }
class Error extends State { final String msg; Error(this.msg); }

// Exhaustive switch — compiler ensures all cases:
String render(State s) => switch (s) {
  Loading()             => 'Loading...',
  Success(data: var d)  => 'Success: $d',
  Error(msg: var m)     => 'Error: $m',
};

// ── RECORDS ───────────────────────────────────────────────────────────────────
(int, String) pair = (42, 'hello');
print(pair.$1); print(pair.$2);       // Positional
({String name, int age}) user = (name: 'Aryan', age: 17);
print(user.name); print(user.age);   // Named

// ── CLASS MODIFIERS (Dart 3.0+) ───────────────────────────────────────────────
// sealed   — all subtypes in same library, exhaustive switch
// abstract — has abstract members
// interface — implementors only, no extending
// base — extenders only, no implementing
// final — no extending or implementing from outside
// mixin class — usable as both mixin and class

// ── ISOLATES ─────────────────────────────────────────────────────────────────
final result = await Isolate.run(() {
  // CPU-heavy work here — true parallelism!
  return computeSomethingExpensive();
});

// ── COMMON DART IDIOMS ────────────────────────────────────────────────────────
// Cascade:
final list = <int>[]..addAll([1,2,3])..sort()..removeWhere((n)=>n.isEven);

// Null-safe patterns:
final user = getUser();
final name = user?.name ?? 'Guest';
user?.let((u) => print(u.name));     // Extension method

// Pagination (real implementation):
List<List<T>> paginate<T>(List<T> items, int size) => [
  for (var i = 0; i < items.length; i += size)
    items.sublist(i, (i + size).clamp(0, items.length)),
];

// ── PUBSPEC ESSENTIALS ──────────────────────────────────────────────────────
// dart pub get / upgrade / add <pkg> / remove <pkg>
// dart run build_runner build --delete-conflicting-outputs
// dart test
// dart analyze && dart format .
// flutter run / build apk / build ios / build web
```

---

### What's Next?

After mastering Dart deeply, your natural paths:

- 📘 **Flutter Mastery** — Custom painters, animations, complex layouts, platform channels
- 📘 **Riverpod / BLoC** — Enterprise-grade state management patterns for large Flutter apps
- 📘 **Dart Frog / Shelf** — Full-stack Dart — share models between Flutter frontend and Dart backend
- 📘 **Flame Game Engine** — Build 2D games with Flutter/Dart — full game loop, physics, collision
- 📘 **Flutter + WebAssembly** — Dart/Wasm for maximum web performance
- 📘 **Dart Embedded** — Dart on microcontrollers — the frontier of Dart development

---

> 💬 *"We designed Dart to be familiar, but not boring — productive, but not at the cost of correctness."*
> — Dart team, Google

> 💬 *"The best thing about Flutter is that it forced Dart to become great. And Dart, in turn, made Flutter possible."*
> — The Flutter Community

> 💬 *"Dart's sound null safety is the most impactful correctness feature I've seen in any language — it eliminates an entire category of production crashes."*
> — Flutter developers worldwide

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: Dart — Complete Language Mastery | Version: 2.0 (Complete)*
*Sections: 13 | Level: Beginner → 0.01% Elite*
