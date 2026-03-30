# ☕ Java — The Ultimate Master Guide
### From Zero to 0.01% Expert — Every Concept, Pattern, Secret & Hidden Power

> 📘 **The most complete Java guide ever written — beginner to elite.**
>
> 🎯 *Who is this for?* Anyone who wants to go from writing Java to **thinking** in Java.
> ⏱️ *Time to complete:* Self-paced — days to months
> 🛠️ *What you'll gain:* Every technique, pattern, hidden secret, and elite knowledge that separates a 0.01% Java developer from the rest.

---

## Table of Contents

1. [🧠 What is Java?](#1-what-is-java-super-simple)
2. [🌍 Why Java Exists & Dominates](#2-why-java-exists--dominates)
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

## 🧠 1. What is Java? (Super Simple)

### The 12-Year-Old Explanation

Imagine you wrote a letter in English. An English speaker can read it anywhere in the world — in India, in Germany, in Brazil — as long as they know English. The paper doesn't matter, the pen doesn't matter, the country doesn't matter. Only the language matters.

**Java is like that for computer programs.**

You write Java code once on your computer — a Windows PC, a Mac, a Linux server. Java takes your code and compiles it into a special in-between language called **bytecode**. That bytecode can run on ANY computer that has the **Java Virtual Machine (JVM)** installed. Windows, Mac, Linux, Android phones, ATMs, smart TVs, satellites — all can run the same Java bytecode.

This is Java's legendary promise: **"Write Once, Run Anywhere."**

Java was created by **James Gosling** at Sun Microsystems in 1995. It was originally designed for interactive television set-top boxes, but it quickly became the dominant language for enterprise software, Android apps, and large-scale backend systems. Today it is one of the top 3 most used programming languages on Earth.

### Real-Life Analogy

💡 **Think of it like this:**
Programming languages are like cars. Python is a friendly hatchback — easy to drive, perfect for city trips. C++ is an F1 race car — insanely fast but only expert drivers can handle it safely. JavaScript is a motorcycle — quick and agile on the web.

**Java is a commercial airliner.** It is not the fastest vehicle, but it carries 500 passengers safely across the Pacific Ocean every single day, on schedule, with full redundancy, for 30 years without crashing. It is the language of scale, reliability, and enterprise.

### One-Line Definition

> **Java** is a statically-typed, object-oriented, compiled-to-bytecode language designed for portability, reliability, and performance at massive scale — running everywhere from Android phones to Wall Street trading systems.

---

## 🌍 2. Why Java Exists & Dominates

### The Problem It Solved

Before Java, writing software for multiple platforms was a nightmare. You had to rewrite your program in C for Windows, recompile for Linux, write it again for Mac. Each platform had its own quirks, its own bugs, its own libraries.

Java solved this with the JVM — a virtual machine that abstracts away the operating system. Your Java code compiles to bytecode that the JVM executes. The JVM handles the platform differences. You write once, the JVM runs it everywhere.

Java also introduced automatic **garbage collection** — the JVM manages memory automatically, eliminating entire categories of bugs (use-after-free, memory leaks, buffer overflows) that plagued C and C++ programs.

### Where Java Dominates in 2025

| Domain                       | How Java Is Used                                                     |
|------------------------------|----------------------------------------------------------------------|
| Enterprise Backend           | Spring Boot — powers banking, insurance, telecom systems             |
| Android Development          | Kotlin (JVM language) + Java — every Android app                     |
| Big Data                     | Hadoop, Spark, Kafka, Flink — all written in Java                    |
| Financial Systems            | High-frequency trading, risk engines at Goldman Sachs, JPMorgan      |
| Cloud Microservices          | Spring Cloud, Quarkus, Micronaut on AWS/GCP/Azure                   |
| Scientific Computing         | MATLAB-like tools, bioinformatics frameworks                         |
| DevOps Tooling               | Jenkins, Gradle, Maven — all Java                                    |
| Game Development             | Minecraft is written in Java                                         |
| Embedded Systems             | Smart cards, set-top boxes, IoT devices                              |
| Search Engines               | Elasticsearch and Apache Lucene are pure Java                        |

### Why YOU Should Learn It Deeply

1. **Highest-paying backend language** — Java enterprise developers consistently command top salaries globally.
2. **Android is Java/Kotlin on JVM** — every Android app runs on the JVM.
3. **Forces you to think in OOP** — Java's strict object-oriented model builds a foundation that makes every other language easier.
4. **Massive ecosystem** — Spring, Hibernate, Maven, Gradle — mastering these opens enterprise doors.
5. **The hidden depths are enormous** — JVM internals, JIT compilation, GC tuning, concurrency — this language has decades of accumulated wisdom to mine.

---

## 🧱 3. Core Fundamentals (Beginner Level)

> 🎯 *Goal: Build an unshakeable foundation. Every concept here is critical.*

---

### Concept 1: Java Program Structure

Every Java program has a specific structure. Nothing runs without this foundation.

```java
// File: HelloWorld.java
// Rule: File name MUST match the public class name EXACTLY (case-sensitive)

public class HelloWorld {               // Class declaration

    public static void main(String[] args) {  // Entry point — program starts here
        System.out.println("Hello, World!"); // Print to console + newline
        System.out.print("No newline");      // Print without newline
        System.out.printf("Name: %s, Age: %d%n", "Aryan", 17); // Formatted print
    }
}

/*
  Compile:  javac HelloWorld.java  → produces HelloWorld.class (bytecode)
  Run:      java HelloWorld        → JVM executes the bytecode

  Keywords explained:
  public    → accessible from anywhere
  class     → defines a class (blueprint)
  static    → belongs to the class, not an instance
  void      → returns nothing
  main      → special method name — JVM looks for this to start
  String[]  → array of String objects
  args      → command-line arguments passed when running
*/
```

---

### Concept 2: Variables, Data Types & Literals

Java is **statically typed** — every variable has a declared type that never changes.

```java
public class DataTypes {
    public static void main(String[] args) {

        // ── PRIMITIVE TYPES (stored by value, live on stack) ────────────────

        // Integer types:
        byte   b  = 127;           // 8-bit  : -128 to 127
        short  s  = 32767;         // 16-bit : -32,768 to 32,767
        int    i  = 2_147_483_647; // 32-bit : ~-2.1B to 2.1B (most common)
        long   l  = 9_223_372_036_854_775_807L; // 64-bit (note: L suffix!)

        // Floating-point types:
        float  f  = 3.14f;         // 32-bit (note: f suffix!) — ~7 decimal digits
        double d  = 3.141592653589793; // 64-bit — ~15 decimal digits (prefer this)

        // Other primitives:
        char   c  = 'A';           // 16-bit Unicode character
        char   c2 = '\u0041';      // Same as 'A' — Unicode escape
        boolean flag = true;       // true or false

        // ── REFERENCE TYPES (stored as reference, live on heap) ─────────────

        String name = "Aryan";     // String is an object, not a primitive
        int[]  nums = {1, 2, 3};   // Array (object)
        Object obj  = null;        // null = no reference

        // ── LITERALS ────────────────────────────────────────────────────────

        int decimal     = 42;
        int hex         = 0x2A;    // 42 in hexadecimal
        int octal       = 052;     // 42 in octal
        int binary      = 0b101010;// 42 in binary
        int readable    = 1_000_000; // Underscore for readability (Java 7+)
        long bigNum     = 100_000_000L;
        double sci      = 1.5e-10; // Scientific notation

        // ── VAR — local type inference (Java 10+) ───────────────────────────
        var message = "Hello";     // Compiler infers String
        var count   = 42;          // Compiler infers int
        var list    = new java.util.ArrayList<String>(); // Infers type
        // var is ONLY for local variables — never for fields or parameters
    }
}
```

---

### Concept 3: Operators — Every Kind

```java
public class Operators {
    public static void main(String[] args) {

        // ── ARITHMETIC ───────────────────────────────────────────────────────
        int a = 10, b = 3;
        System.out.println(a + b);   // 13
        System.out.println(a - b);   // 7
        System.out.println(a * b);   // 30
        System.out.println(a / b);   // 3  ← INTEGER division! Truncates!
        System.out.println(a % b);   // 1  (remainder)
        System.out.println((double) a / b);  // 3.333... ← Cast to double first

        // ── INCREMENT / DECREMENT ────────────────────────────────────────────
        int x = 5;
        System.out.println(x++);  // 5 — post-increment: use THEN increment
        System.out.println(x);    // 6
        System.out.println(++x);  // 7 — pre-increment: increment THEN use
        System.out.println(x--);  // 7 — post-decrement

        // ── ASSIGNMENT OPERATORS ─────────────────────────────────────────────
        x += 5;   // x = x + 5
        x -= 3;   // x = x - 3
        x *= 2;   // x = x * 2
        x /= 4;   // x = x / 4
        x %= 3;   // x = x % 3
        x &= 0xFF; // Bitwise AND assignment

        // ── COMPARISON ───────────────────────────────────────────────────────
        System.out.println(a == b);  // false — equality
        System.out.println(a != b);  // true  — inequality
        System.out.println(a > b);   // true
        System.out.println(a < b);   // false
        System.out.println(a >= b);  // true
        System.out.println(a <= b);  // false

        // ── LOGICAL ─────────────────────────────────────────────────────────
        boolean t = true, f = false;
        System.out.println(t && f);  // false — AND (short-circuit)
        System.out.println(t || f);  // true  — OR  (short-circuit)
        System.out.println(!t);      // false — NOT

        // ── BITWISE ─────────────────────────────────────────────────────────
        int p = 0b1010;  // 10
        int q = 0b1100;  // 12
        System.out.println(p & q);   // 0b1000 = 8  (AND)
        System.out.println(p | q);   // 0b1110 = 14 (OR)
        System.out.println(p ^ q);   // 0b0110 = 6  (XOR)
        System.out.println(~p);      // -11 (NOT — flips all bits)
        System.out.println(p << 1);  // 20 (left shift = multiply by 2)
        System.out.println(p >> 1);  // 5  (signed right shift = divide by 2)
        System.out.println(p >>> 1); // 5  (unsigned right shift — fills 0)

        // ── TERNARY ─────────────────────────────────────────────────────────
        int max = (a > b) ? a : b;     // condition ? valueIfTrue : valueIfFalse
        String grade = (max >= 90) ? "A" : (max >= 80) ? "B" : "C";

        // ── instanceof ──────────────────────────────────────────────────────
        Object obj = "Hello";
        if (obj instanceof String s) { // Pattern matching (Java 16+)
            System.out.println(s.toUpperCase()); // s is already cast!
        }
    }
}
```

---

### Concept 4: Control Flow — Every Form

```java
public class ControlFlow {
    public static void main(String[] args) {

        // ── IF / ELSE IF / ELSE ──────────────────────────────────────────────
        int score = 85;
        if (score >= 90) {
            System.out.println("A");
        } else if (score >= 80) {
            System.out.println("B");
        } else if (score >= 70) {
            System.out.println("C");
        } else {
            System.out.println("F");
        }

        // ── SWITCH STATEMENT (traditional) ───────────────────────────────────
        String day = "Monday";
        switch (day) {
            case "Monday":
            case "Tuesday":
            case "Wednesday":
            case "Thursday":
            case "Friday":
                System.out.println("Weekday");
                break;  // MUST have break or falls through!
            case "Saturday":
            case "Sunday":
                System.out.println("Weekend");
                break;
            default:
                System.out.println("Unknown");
        }

        // ── SWITCH EXPRESSION (Java 14+) — modern, no fall-through bugs! ─────
        String result = switch (day) {
            case "Monday", "Tuesday", "Wednesday", "Thursday", "Friday" -> "Weekday";
            case "Saturday", "Sunday" -> "Weekend";
            default -> "Unknown";
        };

        // Switch expression with blocks:
        int numLetters = switch (day) {
            case "Monday", "Friday", "Sunday" -> 6;
            case "Tuesday"                    -> 7;
            case "Thursday", "Saturday"       -> 8;
            case "Wednesday"                  -> 9;
            default -> {
                System.out.println("Unknown day: " + day);
                yield 0;  // yield returns value from block
            }
        };

        // ── FOR LOOP ─────────────────────────────────────────────────────────
        for (int i = 0; i < 5; i++) {
            System.out.print(i + " ");  // 0 1 2 3 4
        }

        // ── ENHANCED FOR (for-each) ──────────────────────────────────────────
        int[] numbers = {1, 2, 3, 4, 5};
        for (int n : numbers) {
            System.out.print(n + " ");
        }

        // ── WHILE LOOP ───────────────────────────────────────────────────────
        int count = 0;
        while (count < 5) {
            System.out.print(count++ + " ");
        }

        // ── DO-WHILE LOOP (runs at least once!) ──────────────────────────────
        int num = 10;
        do {
            System.out.println("Runs at least once: " + num);
            num++;
        } while (num < 5);  // condition is false, but body ran once

        // ── BREAK, CONTINUE, LABELED ─────────────────────────────────────────
        outer:
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                if (i == 1 && j == 1) break outer;    // Exit OUTER loop
                if (j == 2)           continue;        // Skip to next iteration
                System.out.println(i + "," + j);
            }
        }
    }
}
```

---

### Concept 5: Methods — Complete Guide

```java
public class Methods {

    // ── METHOD ANATOMY ───────────────────────────────────────────────────────
    // accessModifier returnType methodName(paramType paramName, ...) { body }

    public static int add(int a, int b) {
        return a + b;
    }

    // Multiple return paths:
    public static String classify(int n) {
        if (n > 0) return "positive";
        if (n < 0) return "negative";
        return "zero";
    }

    // Void — returns nothing:
    public static void printGreeting(String name) {
        System.out.println("Hello, " + name + "!");
        // No return statement needed (or use bare "return;" to exit early)
    }

    // ── VARARGS — variable number of arguments ───────────────────────────────
    public static int sum(int... numbers) {  // Treated as int[] inside
        int total = 0;
        for (int n : numbers) total += n;
        return total;
    }
    // Call: sum(1), sum(1,2,3), sum(1,2,3,4,5) — all valid

    // ── METHOD OVERLOADING — same name, different parameters ─────────────────
    public static double multiply(double a, double b) { return a * b; }
    public static int    multiply(int a, int b)       { return a * b; }
    public static String multiply(String s, int n)    { return s.repeat(n); }

    // ── RECURSION ────────────────────────────────────────────────────────────
    public static long factorial(int n) {
        if (n <= 1) return 1;           // Base case
        return n * factorial(n - 1);    // Recursive case
    }

    public static int fibonacci(int n) {
        if (n <= 1) return n;
        return fibonacci(n - 1) + fibonacci(n - 2);
    }

    // ── PASS BY VALUE vs REFERENCE ───────────────────────────────────────────
    // Java is ALWAYS pass-by-value. For objects, the VALUE is the reference.
    public static void changeInt(int x) {
        x = 99;  // Original NOT changed — primitives are copied
    }

    public static void changeArray(int[] arr) {
        arr[0] = 99;  // Original IS changed — reference copied, same object
        arr = new int[]{1,2,3}; // This does NOT change original — new reference
    }

    public static void main(String[] args) {
        System.out.println(add(3, 4));          // 7
        System.out.println(sum(1, 2, 3, 4, 5)); // 15
        System.out.println(factorial(10));       // 3628800

        int[] arr = {1, 2, 3};
        changeArray(arr);
        System.out.println(arr[0]); // 99 — first element changed
    }
}
```

---

### Concept 6: Arrays — Complete Toolkit

```java
import java.util.Arrays;

public class ArrayGuide {
    public static void main(String[] args) {

        // ── DECLARATION & INITIALIZATION ────────────────────────────────────
        int[] nums;              // Declaration (no memory allocated)
        nums = new int[5];       // Allocation (default values: 0 for int)
        int[] scores = {90, 85, 92, 78, 95};  // Declaration + initialization
        int[] filled = new int[]{1, 2, 3};     // Explicit form

        // Default values: int/long/short/byte → 0, double/float → 0.0,
        //                 boolean → false, char → '\u0000', Object → null

        // ── ACCESS AND MODIFY ────────────────────────────────────────────────
        scores[0] = 100;              // Set first element
        int last = scores[scores.length - 1]; // Last element

        // ── ITERATION ────────────────────────────────────────────────────────
        for (int i = 0; i < scores.length; i++) {
            System.out.println("Index " + i + ": " + scores[i]);
        }
        for (int score : scores) {  // Enhanced for — simpler
            System.out.println(score);
        }

        // ── ARRAYS UTILITY CLASS ─────────────────────────────────────────────
        Arrays.sort(scores);                        // Sort in-place
        int idx = Arrays.binarySearch(scores, 92); // Binary search (requires sorted)
        int[] copy = Arrays.copyOf(scores, scores.length);  // Full copy
        int[] part = Arrays.copyOfRange(scores, 1, 4);      // Copy indices 1-3
        Arrays.fill(scores, 0);                     // Fill all with 0
        System.out.println(Arrays.toString(scores)); // "[0, 0, 0, 0, 0]"
        boolean equal = Arrays.equals(scores, copy); // Compare element-by-element

        // ── 2D ARRAYS ────────────────────────────────────────────────────────
        int[][] matrix = new int[3][4];  // 3 rows, 4 columns
        int[][] preset = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        System.out.println(preset[1][2]);  // 6 — row 1, col 2

        // ── JAGGED ARRAYS (rows of different lengths) ────────────────────────
        int[][] jagged = new int[3][];
        jagged[0] = new int[]{1};
        jagged[1] = new int[]{2, 3};
        jagged[2] = new int[]{4, 5, 6};

        // Print 2D array:
        for (int[] row : preset) {
            System.out.println(Arrays.toString(row));
        }
        System.out.println(Arrays.deepToString(preset)); // [[1, 2, 3], [4, 5, 6], ...]
    }
}
```

---

### Concept 7: Strings — Deep Dive

```java
public class StringGuide {
    public static void main(String[] args) {

        // String is IMMUTABLE — every "modification" creates a new object
        String s = "Hello, Java!";

        // ── ESSENTIAL METHODS ────────────────────────────────────────────────
        System.out.println(s.length());           // 12
        System.out.println(s.charAt(0));          // 'H'
        System.out.println(s.indexOf("Java"));    // 7
        System.out.println(s.lastIndexOf('a'));    // 10
        System.out.println(s.substring(7));       // "Java!"
        System.out.println(s.substring(7, 11));   // "Java" (end exclusive)
        System.out.println(s.toUpperCase());      // "HELLO, JAVA!"
        System.out.println(s.toLowerCase());      // "hello, java!"
        System.out.println(s.trim());             // Remove leading/trailing whitespace
        System.out.println(s.strip());            // Like trim() but Unicode-aware (Java 11+)
        System.out.println(s.replace("Java", "Python")); // "Hello, Python!"
        System.out.println(s.replaceAll("[aeiou]", "*")); // Regex replace
        System.out.println(s.contains("Java"));  // true
        System.out.println(s.startsWith("Hello"));// true
        System.out.println(s.endsWith("!"));      // true
        System.out.println(s.isEmpty());          // false
        System.out.println(s.isBlank());          // false (Java 11+)
        System.out.println(s.repeat(2));          // "Hello, Java!Hello, Java!" (Java 11+)

        // Splitting:
        String csv = "one,two,three,four";
        String[] parts = csv.split(",");          // ["one", "two", "three", "four"]
        String[] limited = csv.split(",", 2);     // ["one", "two,three,four"]

        // Joining:
        String joined = String.join(", ", "one", "two", "three"); // "one, two, three"
        String fromArray = String.join("-", parts);

        // Converting:
        int num = Integer.parseInt("42");          // String → int
        double pi = Double.parseDouble("3.14");    // String → double
        String fromInt = String.valueOf(42);       // int → String
        String fromInt2 = Integer.toString(42, 2); // int → binary String: "101010"

        // ── COMPARISON ────────────────────────────────────────────────────────
        String a = "hello";
        String b = "hello";
        String c = new String("hello");

        System.out.println(a == b);            // true (string pool — same object!)
        System.out.println(a == c);            // false (new creates new object)
        System.out.println(a.equals(c));       // true  — ALWAYS use equals()!
        System.out.println(a.equalsIgnoreCase("HELLO")); // true
        System.out.println(a.compareTo(b));    // 0 (lexicographic comparison)

        // ── STRING BUILDER — mutable string for concatenation in loops ────────
        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < 5; i++) {
            sb.append(i).append(", "); // Chaining works!
        }
        sb.deleteCharAt(sb.length() - 1); // Remove last char
        sb.insert(0, "Numbers: ");        // Insert at position
        sb.reverse();                     // Reverse
        System.out.println(sb.toString());

        // ── TEXT BLOCKS (Java 15+) ────────────────────────────────────────────
        String json = """
                {
                    "name": "Aryan",
                    "age": 17,
                    "city": "Kolkata"
                }
                """;  // Preserves indentation relative to closing """

        // ── FORMATTED STRINGS (Java 15+) ─────────────────────────────────────
        String formatted = "Name: %s, Age: %d, GPA: %.2f".formatted("Aryan", 17, 9.8);
    }
}
```

---

🧪 **Mini Task 1:**
> Write a method `isPalindrome(String s)` that returns `true` if the string is a palindrome (ignoring case and non-alphanumeric characters). Test with: `"racecar"`, `"A man, a plan, a canal: Panama"`, `"hello"`.
> ✅ *Expected: Uses StringBuilder.reverse() or two-pointer technique.*

🧪 **Mini Task 2:**
> Write a method `countWords(String sentence)` that returns a `Map<String, Integer>` counting how many times each word appears. Convert to lowercase, ignore punctuation.

---

## ⚙️ 4. Complete Language System Breakdown

> 🎯 *Goal: Understand ALL of Java's machinery — nothing hidden.*

---

### Part 1: Object-Oriented Programming — Java's Core

Java is *deeply* object-oriented. Everything (except primitives) is an object. Mastering OOP in Java is mastering Java itself.

```java
// ── CLASSES & OBJECTS ────────────────────────────────────────────────────────

public class BankAccount {

    // ── FIELDS (instance variables) ──────────────────────────────────────────
    private String accountNumber;  // private = only accessible within this class
    private String owner;
    private double balance;

    // Class variable — shared across ALL instances:
    private static int totalAccounts = 0;

    // Constant:
    public static final double INTEREST_RATE = 0.035;

    // ── CONSTRUCTORS ─────────────────────────────────────────────────────────
    // Default constructor (if no constructor defined, Java provides this implicitly):
    // public BankAccount() {}

    // Parameterized constructor:
    public BankAccount(String accountNumber, String owner, double initialBalance) {
        if (initialBalance < 0) throw new IllegalArgumentException("Balance cannot be negative");
        this.accountNumber = accountNumber;  // 'this' disambiguates field vs param
        this.owner = owner;
        this.balance = initialBalance;
        totalAccounts++;
    }

    // Constructor chaining with this():
    public BankAccount(String accountNumber, String owner) {
        this(accountNumber, owner, 0.0);  // MUST be first statement
    }

    // ── METHODS ──────────────────────────────────────────────────────────────
    public void deposit(double amount) {
        if (amount <= 0) throw new IllegalArgumentException("Deposit must be positive");
        this.balance += amount;
    }

    public void withdraw(double amount) {
        if (amount <= 0)          throw new IllegalArgumentException("Amount must be positive");
        if (amount > this.balance) throw new IllegalStateException("Insufficient funds");
        this.balance -= amount;
    }

    public void transfer(BankAccount target, double amount) {
        this.withdraw(amount);
        target.deposit(amount);
    }

    // ── GETTERS & SETTERS ─────────────────────────────────────────────────────
    public String getAccountNumber() { return accountNumber; }
    public String getOwner()         { return owner; }
    public double getBalance()       { return balance; }
    public static int getTotalAccounts() { return totalAccounts; }

    // ── toString, equals, hashCode ────────────────────────────────────────────
    @Override
    public String toString() {
        return String.format("BankAccount{owner='%s', balance=%.2f}", owner, balance);
    }

    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;               // Same object
        if (!(obj instanceof BankAccount other)) return false; // Type check + cast
        return accountNumber.equals(other.accountNumber); // Compare by account number
    }

    @Override
    public int hashCode() {
        return accountNumber.hashCode();
        // hashCode must be consistent with equals!
    }
}

// ── USAGE ─────────────────────────────────────────────────────────────────────
BankAccount acc1 = new BankAccount("ACC001", "Aryan", 1000.0);
BankAccount acc2 = new BankAccount("ACC002", "Priya");

acc1.deposit(500);
acc1.transfer(acc2, 200);
System.out.println(acc1);   // BankAccount{owner='Aryan', balance=1300.00}
System.out.println(BankAccount.getTotalAccounts()); // 2
```

---

### Part 2: Inheritance, Polymorphism, and the IS-A Relationship

```java
// ── BASE CLASS ────────────────────────────────────────────────────────────────
public abstract class Shape {
    protected String color;

    public Shape(String color) {
        this.color = color;
    }

    // Abstract method — no body, MUST be overridden by subclasses:
    public abstract double area();
    public abstract double perimeter();

    // Concrete method — subclasses inherit this:
    public void describe() {
        System.out.printf("%s: area=%.2f, perimeter=%.2f%n",
            getClass().getSimpleName(), area(), perimeter());
    }

    // final method — CANNOT be overridden:
    public final String getColor() { return color; }
}

// ── SUBCLASSES ────────────────────────────────────────────────────────────────
public class Circle extends Shape {
    private double radius;

    public Circle(String color, double radius) {
        super(color);           // MUST call super constructor first
        this.radius = radius;
    }

    @Override  // Annotation verifies this is actually overriding
    public double area()      { return Math.PI * radius * radius; }

    @Override
    public double perimeter() { return 2 * Math.PI * radius; }
}

public class Rectangle extends Shape {
    private double width, height;

    public Rectangle(String color, double width, double height) {
        super(color);
        this.width = width;
        this.height = height;
    }

    @Override
    public double area()      { return width * height; }

    @Override
    public double perimeter() { return 2 * (width + height); }

    // ADD new method not in parent:
    public double diagonal()  { return Math.sqrt(width*width + height*height); }
}

public class Square extends Rectangle {
    public Square(String color, double side) {
        super(color, side, side);  // Square IS-A Rectangle
    }
    // Inherits everything from Rectangle
}

// ── POLYMORPHISM ─────────────────────────────────────────────────────────────
public class PolymorphismDemo {
    public static void main(String[] args) {
        // Compile-time type = Shape, Runtime type = specific class
        Shape[] shapes = {
            new Circle("red", 5),
            new Rectangle("blue", 4, 6),
            new Square("green", 3)
        };

        // Polymorphic method calls — correct method called at runtime:
        for (Shape s : shapes) {
            s.describe();         // Calls overridden method for each type
        }

        // Casting:
        Shape s = new Circle("red", 5);
        if (s instanceof Circle c) {    // Pattern matching instanceof (Java 16+)
            System.out.println("Radius: " + c.radius); // c is already cast!
        }

        // instanceof BEFORE Java 16:
        if (s instanceof Circle) {
            Circle c2 = (Circle) s;   // Explicit cast — ClassCastException if wrong!
            System.out.println("Radius: " + c2.radius);
        }
    }
}
```

---

### Part 3: Interfaces & Abstract Classes

```java
// ── INTERFACE — pure contract, no state ────────────────────────────────────
public interface Drawable {
    // All methods are implicitly public abstract (unless default/static)
    void draw();
    void resize(double factor);

    // Default method — has implementation (Java 8+):
    default void drawWithBorder() {
        System.out.println("Drawing border...");
        draw();
    }

    // Static method in interface (Java 8+):
    static Drawable createEmpty() {
        return () -> System.out.println("Empty drawable");
    }

    // Private method (Java 9+) — helper for default methods:
    private void helper() { /* ... */ }

    // Constants (implicitly public static final):
    int DEFAULT_SIZE = 100;
}

public interface Serializable {
    byte[] serialize();
    static <T> T deserialize(byte[] data, Class<T> type) { return null; }
}

// ── Class implementing MULTIPLE interfaces (Java doesn't support multiple inheritance of classes):
public class SVGShape implements Drawable, Serializable, Cloneable {
    private String path;

    @Override
    public void draw()                { System.out.println("Drawing SVG: " + path); }

    @Override
    public void resize(double factor) { /* scale path */ }

    @Override
    public byte[] serialize()         { return path.getBytes(); }

    @Override
    protected Object clone() throws CloneNotSupportedException {
        return super.clone();
    }
}

// ── ABSTRACT CLASS — partial implementation, can have state ──────────────────
public abstract class Vehicle {
    protected String brand;
    protected int year;
    protected double speed = 0;

    public Vehicle(String brand, int year) {
        this.brand = brand;
        this.year = year;
    }

    // Abstract — must override:
    public abstract void startEngine();
    public abstract double fuelEfficiency(); // km per liter

    // Concrete with business logic:
    public void accelerate(double kmh) {
        speed += kmh;
        System.out.printf("%s accelerating to %.1f km/h%n", brand, speed);
    }

    public void brake() { speed = Math.max(0, speed - 10); }
}

/*
  Abstract Class vs Interface:
  ┌────────────────────────────┬────────────────────────────────────────┐
  │ Abstract Class             │ Interface                              │
  ├────────────────────────────┼────────────────────────────────────────┤
  │ Can have constructors      │ No constructors                        │
  │ Can have instance fields   │ Only constants (static final)          │
  │ Single inheritance only    │ A class can implement many             │
  │ Can have any access mods   │ Methods implicitly public              │
  │ Use for IS-A + shared code │ Use for HAS-A capability contract      │
  └────────────────────────────┴────────────────────────────────────────┘
*/
```

---

### Part 4: Java Collections Framework

```java
import java.util.*;
import java.util.stream.*;

public class CollectionsGuide {

    public static void main(String[] args) {

        // ── LIST — ordered, allows duplicates ─────────────────────────────────

        // ArrayList — backed by dynamic array, O(1) get, O(n) insert middle
        List<String> list = new ArrayList<>();
        list.add("Aryan");
        list.add("Priya");
        list.add(0, "Zara");     // Insert at index
        list.remove("Priya");    // By value
        list.remove(0);          // By index
        Collections.sort(list);  // Sort in-place
        Collections.reverse(list);
        System.out.println(list.get(0)); // Get by index
        System.out.println(list.contains("Aryan")); // true
        System.out.println(list.indexOf("Aryan"));  // index

        // LinkedList — O(1) add/remove head/tail, O(n) random access
        LinkedList<Integer> linked = new LinkedList<>();
        linked.addFirst(1);
        linked.addLast(2);
        linked.offer(3);         // Add to end (queue operation)
        linked.poll();           // Remove from front (queue operation)
        linked.push(0);          // Add to front (stack operation)
        linked.pop();            // Remove from front (stack operation)

        // Immutable lists (Java 9+):
        List<String> immutable = List.of("A", "B", "C");
        List<String> copy = List.copyOf(list); // Immutable copy

        // ── SET — no duplicates ────────────────────────────────────────────────

        // HashSet — O(1) operations, NO guaranteed order
        Set<String> hashSet = new HashSet<>();
        hashSet.add("banana");
        hashSet.add("apple");
        hashSet.add("banana");   // Ignored — duplicate
        System.out.println(hashSet.size()); // 2

        // LinkedHashSet — maintains insertion order
        Set<String> linkedSet = new LinkedHashSet<>(Arrays.asList("c", "a", "b"));
        // Iterates: c, a, b

        // TreeSet — sorted order, O(log n) operations
        Set<String> treeSet = new TreeSet<>(Arrays.asList("banana", "apple", "cherry"));
        // Iterates: apple, banana, cherry

        Set<Integer> s1 = new HashSet<>(Arrays.asList(1, 2, 3, 4));
        Set<Integer> s2 = new HashSet<>(Arrays.asList(3, 4, 5, 6));
        Set<Integer> union = new HashSet<>(s1); union.addAll(s2);     // {1,2,3,4,5,6}
        Set<Integer> inter = new HashSet<>(s1); inter.retainAll(s2);  // {3,4}
        Set<Integer> diff  = new HashSet<>(s1); diff.removeAll(s2);   // {1,2}

        // ── MAP — key-value pairs ──────────────────────────────────────────────

        // HashMap — O(1) operations, NO guaranteed order
        Map<String, Integer> grades = new HashMap<>();
        grades.put("Aryan", 98);
        grades.put("Priya", 92);
        grades.put("Bob", 85);

        grades.get("Aryan");              // 98
        grades.getOrDefault("Alice", 0);  // 0 — safe get
        grades.putIfAbsent("Bob", 100);   // Won't overwrite existing
        grades.computeIfAbsent("Alice", k -> k.length());  // Compute if missing
        grades.merge("Aryan", 2, Integer::sum); // Aryan's grade + 2 = 100

        for (Map.Entry<String, Integer> entry : grades.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }

        // LinkedHashMap — maintains insertion order
        Map<String, Integer> ordered = new LinkedHashMap<>();

        // TreeMap — sorted by key, O(log n)
        Map<String, Integer> sorted = new TreeMap<>();
        TreeMap<String, Integer> treeMap = new TreeMap<>(grades);
        System.out.println(treeMap.firstKey()); // alphabetically first
        System.out.println(treeMap.floorKey("N")); // greatest key ≤ "N"

        // Immutable maps (Java 9+):
        Map<String, Integer> immutableMap = Map.of("a", 1, "b", 2, "c", 3);
        Map<String, Integer> moreEntries  = Map.ofEntries(
            Map.entry("key1", 1),
            Map.entry("key2", 2)
        );

        // ── QUEUE & DEQUE ─────────────────────────────────────────────────────

        Queue<String> queue = new ArrayDeque<>(); // Prefer over LinkedList for Queue
        queue.offer("first");   // Add (returns false if full, unlike add() which throws)
        queue.peek();           // View head without removing (null if empty)
        queue.poll();           // Remove head (null if empty)

        Deque<String> deque = new ArrayDeque<>(); // Double-ended queue
        deque.offerFirst("front");
        deque.offerLast("back");
        deque.peekFirst();
        deque.pollLast();

        // PriorityQueue — min-heap by default:
        PriorityQueue<Integer> pq = new PriorityQueue<>();
        pq.offer(30); pq.offer(10); pq.offer(20);
        while (!pq.isEmpty()) System.out.print(pq.poll() + " "); // 10 20 30

        // Max-heap with comparator:
        PriorityQueue<Integer> maxPQ = new PriorityQueue<>(Comparator.reverseOrder());

        // ── UTILITY METHODS ───────────────────────────────────────────────────
        Collections.shuffle(list);
        Collections.min(list);
        Collections.max(list);
        Collections.frequency(list, "Aryan");
        Collections.unmodifiableList(list); // Unmodifiable view
    }
}
```

---

### Part 5: Exception Handling — Complete System

```java
import java.io.*;
import java.nio.file.*;

public class ExceptionHandling {

    // ── EXCEPTION HIERARCHY ────────────────────────────────────────────────
    /*
       Throwable
       ├── Error (Don't catch — JVM problems: OutOfMemoryError, StackOverflowError)
       └── Exception
           ├── RuntimeException (Unchecked — don't need to declare or catch)
           │   ├── NullPointerException
           │   ├── ArrayIndexOutOfBoundsException
           │   ├── ClassCastException
           │   ├── IllegalArgumentException
           │   ├── IllegalStateException
           │   └── ArithmeticException
           └── Checked Exceptions (Must declare with throws OR catch)
               ├── IOException
               ├── FileNotFoundException
               ├── SQLException
               └── ParseException
    */

    // ── CHECKED EXCEPTION — must handle ──────────────────────────────────────
    public static String readFile(String path) throws IOException {
        return Files.readString(Path.of(path));  // Throws checked IOException
    }

    // ── CUSTOM EXCEPTIONS ─────────────────────────────────────────────────────
    public static class InsufficientFundsException extends Exception {
        private final double shortfall;

        public InsufficientFundsException(double shortfall) {
            super("Insufficient funds. Shortfall: ₹" + shortfall);
            this.shortfall = shortfall;
        }

        public double getShortfall() { return shortfall; }
    }

    // Unchecked custom exception:
    public static class InvalidAgeException extends RuntimeException {
        public InvalidAgeException(int age) {
            super("Invalid age: " + age + ". Must be between 0 and 150.");
        }
    }

    public static void main(String[] args) {

        // ── TRY-CATCH-FINALLY ──────────────────────────────────────────────────
        try {
            int[] arr = new int[5];
            arr[10] = 1;              // ArrayIndexOutOfBoundsException
            int x = 10 / 0;          // ArithmeticException — never reached
        } catch (ArrayIndexOutOfBoundsException e) {
            System.err.println("Array error: " + e.getMessage());
        } catch (ArithmeticException e) {
            System.err.println("Math error: " + e.getMessage());
        } catch (Exception e) {
            // Catch-all — always put LAST (catches most specific first)
            System.err.println("Unknown error: " + e.getClass().getSimpleName());
            e.printStackTrace(); // Print full stack trace — useful for debugging
        } finally {
            System.out.println("Always executes — for cleanup"); // Runs even if exception!
        }

        // ── MULTI-CATCH (Java 7+) ────────────────────────────────────────────
        try {
            // ...
        } catch (NullPointerException | IllegalArgumentException e) {
            System.err.println("Null or illegal arg: " + e.getMessage());
        }

        // ── TRY-WITH-RESOURCES (Java 7+) — auto-closes resources ─────────────
        try (
            var reader = new BufferedReader(new FileReader("file.txt"));
            var writer = new FileWriter("output.txt")
        ) {
            String line;
            while ((line = reader.readLine()) != null) {
                writer.write(line.toUpperCase() + "\n");
            }
        } catch (IOException e) {
            System.err.println("IO error: " + e.getMessage());
        }
        // reader and writer are automatically closed even if exception occurs!

        // ── EXCEPTION CHAINING ────────────────────────────────────────────────
        try {
            try {
                Integer.parseInt("not a number");
            } catch (NumberFormatException e) {
                throw new RuntimeException("Failed to parse config", e); // Wrap cause
            }
        } catch (RuntimeException e) {
            System.err.println(e.getMessage());
            System.err.println("Caused by: " + e.getCause().getMessage());
        }

        // ── ASSERT ────────────────────────────────────────────────────────────
        int age = 25;
        assert age >= 0 && age <= 150 : "Invalid age: " + age;
        // Enable with: java -ea MyProgram
    }
}
```

---

### Part 6: Generics — Type-Safe Everything

```java
import java.util.function.*;

public class Generics {

    // ── GENERIC CLASS ─────────────────────────────────────────────────────────
    public static class Pair<A, B> {
        private final A first;
        private final B second;

        public Pair(A first, B second) {
            this.first = first;
            this.second = second;
        }

        public A getFirst()  { return first; }
        public B getSecond() { return second; }

        public Pair<B, A> swap() { return new Pair<>(second, first); }

        @Override
        public String toString() { return "(" + first + ", " + second + ")"; }
    }

    // ── GENERIC METHODS ──────────────────────────────────────────────────────
    public static <T extends Comparable<T>> T max(T a, T b) {
        return a.compareTo(b) >= 0 ? a : b;
    }

    public static <T> void swap(T[] arr, int i, int j) {
        T temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

    public static <T> java.util.List<T> repeat(T item, int times) {
        var list = new java.util.ArrayList<T>();
        for (int i = 0; i < times; i++) list.add(item);
        return list;
    }

    // ── BOUNDED TYPE PARAMETERS ───────────────────────────────────────────────
    // T extends SomeClass AND Interface1 AND Interface2
    public static <T extends Number & Comparable<T>> T clamp(T value, T min, T max) {
        if (value.compareTo(min) < 0) return min;
        if (value.compareTo(max) > 0) return max;
        return value;
    }

    // ── WILDCARDS ─────────────────────────────────────────────────────────────
    // ? — unknown type
    // ? extends T — upper bound (read-only: can GET T, can't ADD)
    // ? super T   — lower bound (write: can ADD T, can only GET Object)

    // Upper bounded wildcard — accepts List<Integer>, List<Double>, etc:
    public static double sumOfList(java.util.List<? extends Number> list) {
        return list.stream().mapToDouble(Number::doubleValue).sum();
    }

    // Lower bounded wildcard — accepts List<Integer>, List<Number>, List<Object>:
    public static void addNumbers(java.util.List<? super Integer> list) {
        for (int i = 0; i < 5; i++) list.add(i);
    }

    public static void main(String[] args) {
        Pair<String, Integer> p = new Pair<>("Aryan", 17);
        System.out.println(p);              // (Aryan, 17)
        System.out.println(p.swap());       // (17, Aryan)

        System.out.println(max(10, 20));    // 20
        System.out.println(max("apple", "banana")); // banana
        System.out.println(clamp(15, 1, 10)); // 10

        java.util.List<Integer> ints = java.util.Arrays.asList(1, 2, 3);
        java.util.List<Double>  dbls = java.util.Arrays.asList(1.1, 2.2, 3.3);
        System.out.println(sumOfList(ints)); // Works! Integer extends Number
        System.out.println(sumOfList(dbls)); // Works! Double extends Number
    }
}
```

---

### 📊 Full Java System Overview Table

| Feature               | Java Mechanism                                       | Key Insight                                           |
|-----------------------|------------------------------------------------------|-------------------------------------------------------|
| Memory model          | Stack (primitives, references) + Heap (objects)      | All objects on heap; GC manages heap automatically    |
| Type system           | Static, strong, nominally typed                      | Types checked at compile time; no implicit coercion   |
| Inheritance           | Single class inheritance, multiple interface impl    | extends one class; implements many interfaces         |
| Polymorphism          | Runtime dynamic dispatch via vtable                  | Method called depends on object's actual runtime type |
| Generics              | Type erasure — removed at compile time               | Generics are compile-time only; no generic arrays     |
| Concurrency           | Threads + JVM memory model + java.util.concurrent    | Synchronized, volatile, locks, atomic operations      |
| Garbage Collection    | Generational GC (Young + Old gen + Metaspace)        | G1GC default; ZGC/Shenandoah for low-latency          |
| Lambdas               | Functional interfaces + anonymous inner classes      | Lambda is just syntax sugar for SAM interfaces        |
| Streams               | Lazy evaluation pipeline over collections/sequences  | Intermediate ops lazy; terminal op triggers execution |
| Modules (Java 9+)     | module-info.java declares dependencies/exports       | Strong encapsulation beyond packages                  |

---

## 🔄 5. Real-World Workflow

---

### 🟢 Beginner Workflow: Build a Student Management System

```java
import java.util.*;
import java.util.stream.*;

// Student.java
public record Student(
    String id,
    String name,
    int age,
    double gpa,
    String department
) implements Comparable<Student> {

    // Compact constructor for validation:
    public Student {
        if (gpa < 0 || gpa > 10) throw new IllegalArgumentException("Invalid GPA: " + gpa);
        if (age < 10 || age > 100) throw new IllegalArgumentException("Invalid age: " + age);
        id = Objects.requireNonNull(id, "ID cannot be null");
        name = Objects.requireNonNull(name, "Name cannot be null");
    }

    public boolean isHonors() { return gpa >= 9.0; }

    @Override
    public int compareTo(Student other) {
        return Double.compare(other.gpa, this.gpa); // Descending by GPA
    }
}

// StudentRepository.java
public class StudentRepository {
    private final Map<String, Student> students = new HashMap<>();

    public void add(Student student) {
        if (students.containsKey(student.id())) {
            throw new IllegalStateException("Student ID already exists: " + student.id());
        }
        students.put(student.id(), student);
    }

    public Optional<Student> findById(String id) {
        return Optional.ofNullable(students.get(id));
    }

    public List<Student> findByDepartment(String dept) {
        return students.values().stream()
            .filter(s -> s.department().equalsIgnoreCase(dept))
            .sorted()
            .collect(Collectors.toList());
    }

    public Map<String, Double> averageGpaByDepartment() {
        return students.values().stream()
            .collect(Collectors.groupingBy(
                Student::department,
                Collectors.averagingDouble(Student::gpa)
            ));
    }

    public List<Student> getTopN(int n) {
        return students.values().stream()
            .sorted()
            .limit(n)
            .collect(Collectors.toList());
    }

    public OptionalDouble getHighestGpa() {
        return students.values().stream()
            .mapToDouble(Student::gpa)
            .max();
    }

    public long countHonorsStudents() {
        return students.values().stream()
            .filter(Student::isHonors)
            .count();
    }
}

// Main.java
public class Main {
    public static void main(String[] args) {
        StudentRepository repo = new StudentRepository();

        repo.add(new Student("S001", "Aryan",  17, 9.8, "CSE"));
        repo.add(new Student("S002", "Priya",  18, 9.2, "CSE"));
        repo.add(new Student("S003", "Rahul",  17, 8.5, "ECE"));
        repo.add(new Student("S004", "Sneha",  19, 9.5, "CSE"));
        repo.add(new Student("S005", "Vikram", 18, 7.8, "ME"));

        System.out.println("Top 3 students:");
        repo.getTopN(3).forEach(s ->
            System.out.printf("  %s: %.1f GPA%n", s.name(), s.gpa())
        );

        System.out.println("\nAverage GPA by department:");
        repo.averageGpaByDepartment().entrySet().stream()
            .sorted(Map.Entry.<String, Double>comparingByValue().reversed())
            .forEach(e -> System.out.printf("  %s: %.2f%n", e.getKey(), e.getValue()));

        System.out.println("\nHonors students: " + repo.countHonorsStudents());

        repo.findById("S001").ifPresent(s ->
            System.out.println("\nFound: " + s.name() + " (" + s.department() + ")")
        );
    }
}
```

---

### 🔵 Professional Workflow: Spring Boot REST API

```java
// pom.xml dependencies: spring-boot-starter-web, spring-boot-starter-data-jpa, h2

// Product.java — JPA Entity
@Entity
@Table(name = "products")
public class Product {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(nullable = false)
    @NotBlank(message = "Name is required")
    private String name;

    @Column(nullable = false)
    @DecimalMin(value = "0.0", inclusive = false, message = "Price must be positive")
    private BigDecimal price;

    @Column
    private String description;

    @Enumerated(EnumType.STRING)
    private Category category;

    // JPA requires no-args constructor:
    protected Product() {}

    public Product(String name, BigDecimal price, String description, Category category) {
        this.name = name;
        this.price = price;
        this.description = description;
        this.category = category;
    }

    // Getters, setters...
}

// ProductRepository.java
@Repository
public interface ProductRepository extends JpaRepository<Product, Long> {
    List<Product> findByCategory(Category category);
    List<Product> findByPriceBetween(BigDecimal min, BigDecimal max);
    List<Product> findByNameContainingIgnoreCase(String keyword);

    @Query("SELECT p FROM Product p WHERE p.price = (SELECT MIN(p2.price) FROM Product p2)")
    Optional<Product> findCheapest();
}

// ProductService.java
@Service
@Transactional
public class ProductService {
    private final ProductRepository repo;

    public ProductService(ProductRepository repo) { this.repo = repo; }

    @Transactional(readOnly = true)
    public List<Product> getAll() { return repo.findAll(); }

    @Transactional(readOnly = true)
    public Product getById(Long id) {
        return repo.findById(id)
            .orElseThrow(() -> new ResourceNotFoundException("Product not found: " + id));
    }

    public Product create(Product product)      { return repo.save(product); }
    public void    delete(Long id)              { repo.deleteById(id); }

    public Product update(Long id, Product updated) {
        Product existing = getById(id);
        existing.setName(updated.getName());
        existing.setPrice(updated.getPrice());
        return repo.save(existing);
    }
}

// ProductController.java
@RestController
@RequestMapping("/api/products")
@Validated
public class ProductController {
    private final ProductService service;

    public ProductController(ProductService service) { this.service = service; }

    @GetMapping
    public ResponseEntity<List<Product>> getAll() {
        return ResponseEntity.ok(service.getAll());
    }

    @GetMapping("/{id}")
    public ResponseEntity<Product> getById(@PathVariable Long id) {
        return ResponseEntity.ok(service.getById(id));
    }

    @PostMapping
    public ResponseEntity<Product> create(@Valid @RequestBody Product product) {
        Product created = service.create(product);
        URI location = URI.create("/api/products/" + created.getId());
        return ResponseEntity.created(location).body(created);
    }

    @PutMapping("/{id}")
    public ResponseEntity<Product> update(
            @PathVariable Long id,
            @Valid @RequestBody Product product) {
        return ResponseEntity.ok(service.update(id, product));
    }

    @DeleteMapping("/{id}")
    public ResponseEntity<Void> delete(@PathVariable Long id) {
        service.delete(id);
        return ResponseEntity.noContent().build();
    }
}
```

---

## 🧪 6. Hands-on Practice Projects

---

### 🟢 Beginner Project: Library Management System

**Goal:** Build a console-based library system using OOP, Collections, and File I/O.
**Estimated Time:** 3-4 hours

```java
import java.util.*;
import java.io.*;
import java.nio.file.*;
import java.time.*;

public class LibrarySystem {

    record Book(String isbn, String title, String author,
                int year, boolean isAvailable) {
        Book withAvailability(boolean available) {
            return new Book(isbn, title, author, year, available);
        }
    }

    record BorrowRecord(String isbn, String memberId, LocalDate borrowDate, LocalDate dueDate) {
        boolean isOverdue() { return LocalDate.now().isAfter(dueDate); }
        long daysOverdue()  { return isOverdue() ? ChronoUnit.DAYS.between(dueDate, LocalDate.now()) : 0; }
    }

    static class Library {
        private final Map<String, Book>         books    = new LinkedHashMap<>();
        private final Map<String, BorrowRecord> borrowed = new HashMap<>();
        private static final int BORROW_DAYS = 14;

        public void addBook(Book book) {
            books.put(book.isbn(), book);
            System.out.println("✅ Added: " + book.title());
        }

        public void borrowBook(String isbn, String memberId) {
            Book book = books.get(isbn);
            if (book == null) throw new NoSuchElementException("Book not found: " + isbn);
            if (!book.isAvailable()) throw new IllegalStateException("Book already borrowed!");

            books.put(isbn, book.withAvailability(false));
            LocalDate due = LocalDate.now().plusDays(BORROW_DAYS);
            borrowed.put(isbn, new BorrowRecord(isbn, memberId, LocalDate.now(), due));
            System.out.printf("📚 Borrowed '%s' by %s. Due: %s%n", book.title(), memberId, due);
        }

        public void returnBook(String isbn) {
            BorrowRecord record = borrowed.remove(isbn);
            if (record == null) throw new IllegalStateException("Book not borrowed!");

            books.put(isbn, books.get(isbn).withAvailability(true));
            if (record.isOverdue()) {
                System.out.printf("⚠️ Overdue by %d days! Fine: ₹%d%n",
                    record.daysOverdue(), record.daysOverdue() * 5);
            } else {
                System.out.println("✅ Returned successfully!");
            }
        }

        public List<Book> searchByAuthor(String author) {
            return books.values().stream()
                .filter(b -> b.author().toLowerCase().contains(author.toLowerCase()))
                .sorted(Comparator.comparing(Book::title))
                .toList();
        }

        public void printReport() {
            long available = books.values().stream().filter(Book::isAvailable).count();
            System.out.printf("%n📊 Library Report:%n");
            System.out.printf("  Total books: %d | Available: %d | Borrowed: %d%n",
                books.size(), available, borrowed.size());
            System.out.println("  Overdue:");
            borrowed.values().stream()
                .filter(BorrowRecord::isOverdue)
                .forEach(r -> System.out.printf("    ISBN: %s, Member: %s, Overdue: %d days%n",
                    r.isbn(), r.memberId(), r.daysOverdue()));
        }
    }

    public static void main(String[] args) {
        Library lib = new Library();
        lib.addBook(new Book("978-0", "Clean Code",      "Robert Martin", 2008, true));
        lib.addBook(new Book("978-1", "Effective Java",  "Joshua Bloch",  2018, true));
        lib.addBook(new Book("978-2", "Design Patterns", "GoF",           1994, true));

        lib.borrowBook("978-0", "MEM001");
        lib.borrowBook("978-1", "MEM002");
        lib.returnBook("978-0");

        System.out.println("\nSearch 'Joshua':");
        lib.searchByAuthor("Joshua").forEach(b ->
            System.out.println("  " + b.title() + " (" + (b.isAvailable() ? "available" : "borrowed") + ")")
        );

        lib.printReport();
    }
}
```

✅ **You've succeeded when:** The system correctly handles borrowing, returning, overdue fines, and searching — with no bugs when adding 50+ books.

---

### 🔵 Intermediate Project: Multithreaded File Processor

```java
import java.util.concurrent.*;
import java.util.concurrent.atomic.*;
import java.util.*;
import java.io.*;
import java.nio.file.*;

public class FileProcessor {

    record ProcessingResult(String filename, int lineCount, int wordCount, long processingTimeMs) {}

    static class FileAnalyzer implements Callable<ProcessingResult> {
        private final Path file;

        FileAnalyzer(Path file) { this.file = file; }

        @Override
        public ProcessingResult call() throws Exception {
            long start = System.currentTimeMillis();
            List<String> lines = Files.readAllLines(file);
            int wordCount = lines.stream()
                .mapToInt(line -> line.isBlank() ? 0 : line.split("\\s+").length)
                .sum();
            long elapsed = System.currentTimeMillis() - start;
            return new ProcessingResult(file.getFileName().toString(),
                lines.size(), wordCount, elapsed);
        }
    }

    public static void processDirectory(Path dir) throws Exception {
        List<Path> files = Files.walk(dir)
            .filter(p -> p.toString().endsWith(".txt"))
            .toList();

        int cores = Runtime.getRuntime().availableProcessors();
        ExecutorService executor = Executors.newFixedThreadPool(cores);

        List<Future<ProcessingResult>> futures = files.stream()
            .map(FileAnalyzer::new)
            .map(executor::submit)
            .toList();

        AtomicInteger totalWords = new AtomicInteger();
        AtomicInteger totalLines = new AtomicInteger();

        System.out.println("Processing " + files.size() + " files on " + cores + " threads...");

        for (Future<ProcessingResult> future : futures) {
            try {
                ProcessingResult result = future.get(30, TimeUnit.SECONDS);
                totalWords.addAndGet(result.wordCount());
                totalLines.addAndGet(result.lineCount());
                System.out.printf("  %-30s %5d lines, %7d words (%dms)%n",
                    result.filename(), result.lineCount(), result.wordCount(), result.processingTimeMs());
            } catch (TimeoutException e) {
                System.err.println("File processing timed out!");
                future.cancel(true);
            }
        }

        executor.shutdown();
        executor.awaitTermination(1, TimeUnit.MINUTES);

        System.out.printf("%nTotal: %d lines, %d words%n",
            totalLines.get(), totalWords.get());
    }
}
```

---

### 🔴 Advanced Project: Event-Driven Order Processing System

```java
import java.util.*;
import java.util.concurrent.*;
import java.util.function.*;

// Event system
public class OrderProcessingSystem {

    // Domain events
    sealed interface OrderEvent permits
        OrderCreated, OrderPaid, OrderShipped, OrderCancelled {}

    record OrderCreated  (String orderId, String customerId, double amount)    implements OrderEvent {}
    record OrderPaid     (String orderId, String paymentId, double amount)     implements OrderEvent {}
    record OrderShipped  (String orderId, String trackingId, String carrier)   implements OrderEvent {}
    record OrderCancelled(String orderId, String reason)                       implements OrderEvent {}

    // Event bus
    static class EventBus {
        private final Map<Class<?>, List<Consumer<OrderEvent>>> handlers = new ConcurrentHashMap<>();
        private final BlockingQueue<OrderEvent> eventQueue = new LinkedBlockingQueue<>();
        private final ExecutorService executor = Executors.newSingleThreadExecutor();

        public EventBus() {
            executor.submit(() -> {
                while (!Thread.currentThread().isInterrupted()) {
                    try {
                        OrderEvent event = eventQueue.take();
                        dispatch(event);
                    } catch (InterruptedException e) {
                        Thread.currentThread().interrupt();
                    }
                }
            });
        }

        @SuppressWarnings("unchecked")
        public <T extends OrderEvent> void subscribe(Class<T> type, Consumer<T> handler) {
            handlers.computeIfAbsent(type, k -> new CopyOnWriteArrayList<>())
                    .add(e -> handler.accept((T) e));
        }

        public void publish(OrderEvent event) {
            eventQueue.offer(event);
        }

        private void dispatch(OrderEvent event) {
            handlers.getOrDefault(event.getClass(), List.of())
                    .forEach(h -> h.accept(event));
        }

        public void shutdown() { executor.shutdownNow(); }
    }

    public static void main(String[] args) throws InterruptedException {
        EventBus bus = new EventBus();

        // Subscribe handlers:
        bus.subscribe(OrderCreated.class, e ->
            System.out.printf("[INVENTORY] Reserve items for order %s (₹%.2f)%n",
                e.orderId(), e.amount()));

        bus.subscribe(OrderCreated.class, e ->
            System.out.printf("[EMAIL] Send confirmation to customer %s%n", e.customerId()));

        bus.subscribe(OrderPaid.class, e ->
            System.out.printf("[FULFILLMENT] Process payment %s for order %s%n",
                e.paymentId(), e.orderId()));

        bus.subscribe(OrderShipped.class, e ->
            System.out.printf("[NOTIFICATION] Order %s shipped via %s. Tracking: %s%n",
                e.orderId(), e.carrier(), e.trackingId()));

        bus.subscribe(OrderCancelled.class, e ->
            System.out.printf("[REFUND] Process refund for order %s. Reason: %s%n",
                e.orderId(), e.reason()));

        // Publish events:
        bus.publish(new OrderCreated("ORD-001", "CUST-42", 2499.99));
        Thread.sleep(100);
        bus.publish(new OrderPaid("ORD-001", "PAY-789", 2499.99));
        Thread.sleep(100);
        bus.publish(new OrderShipped("ORD-001", "TRK-12345", "FedEx"));

        Thread.sleep(500);
        bus.shutdown();
    }
}
```

🔥 **Challenge:** Add persistence — save all events to a file (event sourcing), and replay them on startup to reconstruct state.

---

## ⚠️ 7. Common Mistakes

---

### ❌ Mistake 1: Using `==` to Compare Strings

```java
// ❌ WRONG — compares references, not content:
String a = new String("hello");
String b = new String("hello");
if (a == b) {  // FALSE — different objects in heap!
    System.out.println("Equal");
}

// ✅ RIGHT — use equals():
if (a.equals(b)) {     // TRUE — compares content
    System.out.println("Equal");
}

// ✅ Null-safe comparison:
if ("hello".equals(a)) { }           // Won't throw NPE even if a is null
if (Objects.equals(a, b)) { }        // Handles both nulls gracefully
```

---

### ❌ Mistake 2: Integer Auto-unboxing NullPointerException

```java
// ❌ WRONG — Integer can be null, int cannot:
Map<String, Integer> map = new HashMap<>();
int count = map.get("missing");  // NullPointerException! get() returns null

// ✅ RIGHT — use getOrDefault or check first:
int count1 = map.getOrDefault("missing", 0);
Integer count2 = map.get("missing");
if (count2 != null) {
    int value = count2; // Safe unbox
}
```

---

### ❌ Mistake 3: ConcurrentModificationException

```java
List<String> list = new ArrayList<>(Arrays.asList("a", "b", "c", "d"));

// ❌ WRONG — modifying list while iterating:
for (String s : list) {
    if (s.equals("b")) list.remove(s);  // ConcurrentModificationException!
}

// ✅ RIGHT — use removeIf():
list.removeIf(s -> s.equals("b"));

// ✅ RIGHT — use Iterator.remove():
Iterator<String> iter = list.iterator();
while (iter.hasNext()) {
    if (iter.next().equals("b")) iter.remove();
}

// ✅ RIGHT — collect to new list:
list = list.stream().filter(s -> !s.equals("b")).collect(java.util.stream.Collectors.toList());
```

---

### ❌ Mistake 4: Mutable Objects in HashMap Keys

```java
// ❌ WRONG — key changes after insertion breaks the map:
List<String> key = new ArrayList<>(Arrays.asList("a", "b"));
Map<List<String>, Integer> map = new HashMap<>();
map.put(key, 1);
key.add("c");  // Mutated the key! hashCode changed!
System.out.println(map.get(key));  // null — cannot find it anymore!

// ✅ RIGHT — use immutable keys:
List<String> immutableKey = List.of("a", "b");  // or Collections.unmodifiableList()
map.put(immutableKey, 1);  // Safe — cannot be mutated
```

---

### ❌ Mistake 5: Catching `Exception` or `Throwable` Too Broadly

```java
// ❌ WRONG — catches InterruptedException, OutOfMemoryError, everything:
try {
    Thread.sleep(1000);
    processData();
} catch (Exception e) {
    e.printStackTrace();  // Swallows InterruptedException silently!
}

// ✅ RIGHT — catch specifically, handle properly:
try {
    Thread.sleep(1000);
} catch (InterruptedException e) {
    Thread.currentThread().interrupt();  // Restore interrupt flag!
    throw new RuntimeException("Processing interrupted", e);
}
try {
    processData();
} catch (DataProcessingException e) {
    log.error("Processing failed", e);
    // Handle or rethrow
}
```

---

### ❌ Mistake 6: String Concatenation in Loops

```java
// ❌ WRONG — creates O(n²) String objects in heap!
String result = "";
for (int i = 0; i < 10000; i++) {
    result += i + ",";  // New String object EVERY iteration!
}

// ✅ RIGHT — use StringBuilder: O(n) amortized
StringBuilder sb = new StringBuilder();
for (int i = 0; i < 10000; i++) {
    sb.append(i).append(',');
}
String result2 = sb.toString();

// ✅ EVEN BETTER — use String.join or Stream:
String result3 = java.util.stream.IntStream.range(0, 10000)
    .mapToObj(Integer::toString)
    .collect(java.util.stream.Collectors.joining(","));
```

---

### ❌ Mistake 7: Not Closing Resources (Pre Java 7)

```java
// ❌ WRONG — resource leak if exception thrown:
FileInputStream fis = null;
try {
    fis = new FileInputStream("file.txt");
    // ... use fis
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (fis != null) {  // Verbose, easy to forget
        try { fis.close(); } catch (IOException e) { }
    }
}

// ✅ RIGHT — try-with-resources (Java 7+):
try (var fis = new FileInputStream("file.txt")) {
    // ... use fis
    // Automatically closed even if exception thrown!
} catch (IOException e) {
    e.printStackTrace();
}
```

---

## 🔥 8. Pro Tips & Hidden Tricks

---

### 💎 Tip 1: The Stream API — Functional Data Processing

```java
import java.util.*;
import java.util.stream.*;
import java.util.function.*;

public class StreamMastery {

    record Employee(String name, String dept, double salary, int yearsExp) {}

    public static void main(String[] args) {
        List<Employee> employees = List.of(
            new Employee("Aryan",  "Engineering", 85000, 3),
            new Employee("Priya",  "Engineering", 95000, 6),
            new Employee("Rahul",  "Marketing",   65000, 4),
            new Employee("Sneha",  "Engineering", 90000, 5),
            new Employee("Vikram", "Marketing",   72000, 7),
            new Employee("Anita",  "HR",          58000, 2)
        );

        // Filter + Map + Collect:
        List<String> seniorEngineers = employees.stream()
            .filter(e -> e.dept().equals("Engineering"))
            .filter(e -> e.yearsExp() >= 5)
            .map(Employee::name)
            .sorted()
            .collect(Collectors.toList());
        System.out.println("Senior Engineers: " + seniorEngineers);

        // Statistics:
        DoubleSummaryStatistics salaryStats = employees.stream()
            .mapToDouble(Employee::salary)
            .summaryStatistics();
        System.out.printf("Salary — Min: %.0f, Max: %.0f, Avg: %.0f%n",
            salaryStats.getMin(), salaryStats.getMax(), salaryStats.getAverage());

        // GroupBy:
        Map<String, List<Employee>> byDept = employees.stream()
            .collect(Collectors.groupingBy(Employee::dept));

        // GroupBy with downstream collector:
        Map<String, Double> avgSalaryByDept = employees.stream()
            .collect(Collectors.groupingBy(
                Employee::dept,
                Collectors.averagingDouble(Employee::salary)
            ));
        avgSalaryByDept.forEach((dept, avg) ->
            System.out.printf("  %s: ₹%.0f%n", dept, avg));

        // Partitioning:
        Map<Boolean, List<Employee>> partitioned = employees.stream()
            .collect(Collectors.partitioningBy(e -> e.salary() > 75000));
        System.out.println("High salary: " + partitioned.get(true).stream()
            .map(Employee::name).toList());

        // FlatMap — flatten nested lists:
        List<List<Integer>> nested = List.of(List.of(1,2,3), List.of(4,5), List.of(6,7,8,9));
        List<Integer> flat = nested.stream()
            .flatMap(Collection::stream)
            .collect(Collectors.toList()); // [1,2,3,4,5,6,7,8,9]

        // Reduce:
        double totalSalary = employees.stream()
            .mapToDouble(Employee::salary)
            .reduce(0, Double::sum);

        // Optional from stream:
        Optional<Employee> highestPaid = employees.stream()
            .max(Comparator.comparingDouble(Employee::salary));
        highestPaid.ifPresent(e -> System.out.println("Highest paid: " + e.name()));

        // Collecting to custom map:
        Map<String, Double> nameSalaryMap = employees.stream()
            .collect(Collectors.toMap(Employee::name, Employee::salary));

        // String joining:
        String names = employees.stream()
            .map(Employee::name)
            .collect(Collectors.joining(", ", "[", "]"));
        System.out.println(names);

        // Parallel stream (use for CPU-bound ops on large datasets):
        double parallelSum = employees.parallelStream()
            .mapToDouble(Employee::salary)
            .sum();
    }
}
```

---

### 💎 Tip 2: Functional Interfaces & Lambdas

```java
import java.util.function.*;

public class FunctionalJava {
    public static void main(String[] args) {

        // Built-in functional interfaces:
        Function<String, Integer>     strLen    = String::length;      // T → R
        BiFunction<String, String, String> concat = String::concat;    // T,U → R
        Predicate<String>             isEmpty   = String::isEmpty;     // T → boolean
        Consumer<String>              printer   = System.out::println; // T → void
        Supplier<String>              greeting  = () -> "Hello!";      // () → T
        UnaryOperator<String>         shout     = s -> s.toUpperCase(); // T → T
        BinaryOperator<Integer>       add       = Integer::sum;        // T,T → T

        // Function composition:
        Function<String, String> trimAndShout = ((Function<String, String>) String::trim)
            .andThen(shout);
        System.out.println(trimAndShout.apply("  hello  ")); // "HELLO"

        // Predicate composition:
        Predicate<String> notEmpty  = isEmpty.negate();
        Predicate<String> longEnough = s -> s.length() >= 3;
        Predicate<String> valid = notEmpty.and(longEnough);

        List.of("", "hi", "hello", "a").stream()
            .filter(valid)
            .forEach(System.out::println); // "hello"

        // Method references — 4 types:
        Function<String, String>    f1 = String::toUpperCase;   // Instance method (unbound)
        Runnable                    f2 = System.out::println;   // Instance method (bound)
        Function<String, Integer>   f3 = Integer::parseInt;     // Static method
        Supplier<ArrayList<String>> f4 = ArrayList::new;        // Constructor

        // Closures — lambdas capture effectively-final variables:
        String prefix = "Hello, ";  // effectively final
        Function<String, String> greet = name -> prefix + name + "!";
        System.out.println(greet.apply("Aryan")); // "Hello, Aryan!"
    }
}
```

---

### 💎 Tip 3: Records, Sealed Classes, and Pattern Matching (Modern Java)

```java
// ── RECORDS (Java 16+) — immutable data classes ───────────────────────────
record Point(double x, double y) {
    // Compact constructor:
    Point {
        if (Double.isNaN(x) || Double.isNaN(y))
            throw new IllegalArgumentException("NaN not allowed");
    }

    // Custom method:
    double distanceTo(Point other) {
        return Math.sqrt(Math.pow(x - other.x, 2) + Math.pow(y - other.y, 2));
    }

    // Static factory method:
    static Point origin() { return new Point(0, 0); }
}
// Record auto-generates: constructor, getters (x(), y()), equals, hashCode, toString

// ── SEALED CLASSES (Java 17+) — exhaustive type hierarchies ──────────────
sealed interface Shape permits Circle, Rectangle, Triangle {}

record Circle   (Point center, double radius) implements Shape {}
record Rectangle(Point topLeft, double width, double height) implements Shape {}
record Triangle (Point a, Point b, Point c)  implements Shape {}

// ── PATTERN MATCHING WITH SWITCH (Java 21+) ──────────────────────────────
static double area(Shape shape) {
    return switch (shape) {
        case Circle c    -> Math.PI * c.radius() * c.radius();
        case Rectangle r -> r.width() * r.height();
        case Triangle t  -> {
            // Heron's formula:
            double ab = t.a().distanceTo(t.b());
            double bc = t.b().distanceTo(t.c());
            double ca = t.c().distanceTo(t.a());
            double s = (ab + bc + ca) / 2;
            yield Math.sqrt(s * (s-ab) * (s-bc) * (s-ca));
        }
        // Compiler verifies EXHAUSTIVENESS — no default needed!
    };
}

// Guarded patterns:
static String classify(Object obj) {
    return switch (obj) {
        case Integer i when i < 0    -> "negative integer: " + i;
        case Integer i when i == 0   -> "zero";
        case Integer i               -> "positive integer: " + i;
        case String s when s.isBlank()-> "blank string";
        case String s                -> "string: " + s;
        case null                    -> "null";
        default                      -> "other: " + obj.getClass().getSimpleName();
    };
}
```

---

### 💎 Tip 4: Optional — Null-Safe Code

```java
import java.util.Optional;

public class OptionalMastery {

    record User(String id, String name, String email) {}
    record Address(String street, String city, String country) {}

    static Optional<User>    findUser(String id)          { return Optional.empty(); }
    static Optional<Address> findAddress(String userId)   { return Optional.empty(); }

    public static void main(String[] args) {

        // Creating Optionals:
        Optional<String> present = Optional.of("value");        // Must be non-null
        Optional<String> empty   = Optional.empty();
        Optional<String> nullable= Optional.ofNullable(null);   // Can be null

        // Consuming:
        present.ifPresent(System.out::println);
        present.ifPresentOrElse(
            v -> System.out.println("Found: " + v),
            ()  -> System.out.println("Not found")
        );

        // Transforming:
        Optional<Integer> length = present.map(String::length); // Optional<Integer>
        Optional<String>  upper  = present.map(String::toUpperCase);
        Optional<String>  flat   = present.flatMap(v ->
            v.length() > 3 ? Optional.of(v) : Optional.empty()); // Flattens nested Optional

        // Filtering:
        Optional<String> filtered = present.filter(s -> s.length() > 3);

        // Getting with fallback:
        String val1 = present.orElse("default");
        String val2 = present.orElseGet(() -> computeDefault()); // Lazy!
        String val3 = present.orElseThrow(() -> new NoSuchElementException("No value"));

        // Chaining for deep navigation (replaces nested null checks):
        String city = findUser("123")
            .flatMap(u -> findAddress(u.id()))
            .map(Address::city)
            .orElse("City not found");

        // Stream integration:
        Optional.of("hello")
            .stream()  // Optional → Stream of 0 or 1 elements
            .filter(s -> !s.isBlank())
            .forEach(System.out::println);
    }

    static String computeDefault() { return "computed default"; }
}
```

---

### 💎 Tip 5: Concurrency Done Right

```java
import java.util.concurrent.*;
import java.util.concurrent.atomic.*;
import java.util.concurrent.locks.*;

public class ConcurrencyMastery {

    // ── EXECUTORSERVICE ────────────────────────────────────────────────────
    public static void executorDemo() throws Exception {
        ExecutorService pool = Executors.newFixedThreadPool(4);

        // Submit Callable (returns result):
        Future<Integer> future = pool.submit(() -> {
            Thread.sleep(1000);
            return 42;
        });

        System.out.println("Working...");
        System.out.println("Result: " + future.get(2, TimeUnit.SECONDS));

        pool.shutdown();
    }

    // ── COMPLETABLEFUTURE — async pipelines ───────────────────────────────
    public static void completableFutureDemo() throws Exception {
        CompletableFuture<String> cf = CompletableFuture
            .supplyAsync(() -> fetchUserFromDB("U1"))         // Async
            .thenApply(user -> user.toUpperCase())             // Transform
            .thenApply(user -> "Hello, " + user)              // Transform again
            .exceptionally(err -> "Error: " + err.getMessage()) // Error handling
            .thenCompose(msg ->                                // Flat map
                CompletableFuture.supplyAsync(() -> msg + "!"))
            .whenComplete((result, err) ->
                System.out.println("Done: " + result));       // Side effect

        // Combine multiple async results:
        CompletableFuture<String> user    = CompletableFuture.supplyAsync(() -> fetchUserFromDB("U1"));
        CompletableFuture<String> profile = CompletableFuture.supplyAsync(() -> fetchProfile("P1"));

        CompletableFuture<String> combined = user.thenCombine(profile,
            (u, p) -> u + " - " + p);

        // Wait for ALL:
        CompletableFuture.allOf(user, profile, combined).join();

        // First to complete:
        CompletableFuture<String> first = CompletableFuture.anyOf(user, profile)
            .thenApply(Object::toString);
    }

    // ── ATOMIC VARIABLES ──────────────────────────────────────────────────
    public static void atomicDemo() {
        AtomicInteger counter = new AtomicInteger(0);
        AtomicReference<String> ref = new AtomicReference<>("initial");
        AtomicLong    longVal = new AtomicLong(0L);

        counter.incrementAndGet();    // Thread-safe increment
        counter.addAndGet(5);         // Thread-safe add
        counter.compareAndSet(6, 10); // CAS — atomic compare and swap

        // Better than synchronized for simple counters:
        LongAdder adder = new LongAdder(); // Faster than AtomicLong under contention
        adder.increment();
        System.out.println(adder.sum());
    }

    // ── REENTRANTLOCK ─────────────────────────────────────────────────────
    public static class SafeCounter {
        private int count = 0;
        private final ReentrantLock lock = new ReentrantLock(true); // fair lock

        public void increment() {
            lock.lock();
            try {
                count++;
            } finally {
                lock.unlock(); // ALWAYS in finally!
            }
        }

        public int getCount() { return count; }
    }

    private static String fetchUserFromDB(String id) {
        try { Thread.sleep(100); } catch (InterruptedException e) { Thread.currentThread().interrupt(); }
        return "User_" + id;
    }

    private static String fetchProfile(String id) {
        try { Thread.sleep(200); } catch (InterruptedException e) { Thread.currentThread().interrupt(); }
        return "Profile_" + id;
    }
}
```

---

## 🚀 9. Advanced Concepts (Expert Level)

---

### Advanced Concept 1: JVM Memory Model & Garbage Collection

```java
/*
   JVM Memory Layout:
   ┌─────────────────────────────────────────────────────────────┐
   │  HEAP                                                        │
   │  ┌──────────────────────┐  ┌──────────────────────────────┐ │
   │  │  Young Generation    │  │   Old Generation (Tenured)   │ │
   │  │  ┌────┐ ┌────┐ ┌───┐│  │   (long-lived objects)       │ │
   │  │  │Eden│ │ S0 │ │S1 ││  │                              │ │
   │  │  └────┘ └────┘ └───┘│  └──────────────────────────────┘ │
   │  └──────────────────────┘                                   │
   │  ┌───────────────────────────────────────────────────────┐  │
   │  │  Metaspace (class definitions, method metadata)       │  │
   │  └───────────────────────────────────────────────────────┘  │
   └─────────────────────────────────────────────────────────────┘
   ┌───────────────────────────────────────────────────────────────┐
   │  Thread Stacks (one per thread — stack frames)                │
   │  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐          │
   │  │  Thread 1    │ │  Thread 2    │ │  Thread 3    │          │
   │  └──────────────┘ └──────────────┘ └──────────────┘          │
   └───────────────────────────────────────────────────────────────┘

   GC Algorithms:
   - Serial GC:       Single thread. Use for small apps.
   - Parallel GC:     Multi-thread, stop-the-world. Throughput-focused.
   - G1GC (default):  Generational + region-based. Balanced.
   - ZGC:             Ultra-low latency (<1ms pauses). Java 15+.
   - Shenandoah:      Concurrent GC, low latency. RedHat.
*/

// JVM flags for GC tuning:
// java -Xms512m -Xmx4g         → Initial and max heap size
// java -XX:+UseG1GC            → Use G1 GC
// java -XX:+UseZGC             → Use ZGC (Java 15+)
// java -XX:MaxGCPauseMillis=200 → Target max GC pause
// java -verbose:gc              → Print GC events
// java -XX:+PrintGCDetails      → Detailed GC logging

// Reference types — control GC behavior:
import java.lang.ref.*;

Object obj = new Object();
WeakReference<Object>   weak   = new WeakReference<>(obj);  // GC'd when only weak refs
SoftReference<Object>   soft   = new SoftReference<>(obj);  // GC'd under memory pressure
PhantomReference<Object> phantom = new PhantomReference<>(obj, new ReferenceQueue<>());

obj = null;  // Remove strong reference
System.gc(); // Suggest GC (no guarantee)
System.out.println(weak.get()); // null — object was collected!

// Memory leak patterns to avoid:
// 1. Static collections that grow forever
// 2. Unclosed streams/connections
// 3. Listeners not removed
// 4. ThreadLocal values not removed
// 5. Inner class holding reference to outer class
```

---

### Advanced Concept 2: Reflection — Runtime Introspection

```java
import java.lang.reflect.*;
import java.lang.annotation.*;

public class ReflectionMastery {

    @Retention(RetentionPolicy.RUNTIME)
    @Target(ElementType.METHOD)
    @interface Test {
        String description() default "";
        boolean disabled()  default false;
    }

    @Retention(RetentionPolicy.RUNTIME)
    @Target(ElementType.FIELD)
    @interface Inject {
        String value() default "";
    }

    static class Calculator {
        @Inject("operandA")
        private double operandA = 0;

        @Test(description = "Test addition")
        public double add(double a, double b) { return a + b; }

        @Test(description = "Test subtraction")
        public double subtract(double a, double b) { return a - b; }

        @Test(description = "This test is disabled", disabled = true)
        public void disabledTest() {}

        private String secretMethod() { return "secret!"; }
    }

    // Minimal test runner using reflection:
    public static void runTests(Class<?> clazz) throws Exception {
        Object instance = clazz.getDeclaredConstructor().newInstance();

        for (Method method : clazz.getDeclaredMethods()) {
            Test testAnnotation = method.getAnnotation(Test.class);
            if (testAnnotation == null) continue;
            if (testAnnotation.disabled()) {
                System.out.println("⏭️  SKIP: " + testAnnotation.description());
                continue;
            }
            try {
                method.setAccessible(true);
                if (method.getParameterCount() == 2) {
                    method.invoke(instance, 3.0, 4.0);
                } else {
                    method.invoke(instance);
                }
                System.out.println("✅ PASS: " + testAnnotation.description());
            } catch (Exception e) {
                System.out.println("❌ FAIL: " + testAnnotation.description() + " — " + e.getCause());
            }
        }
    }

    public static void main(String[] args) throws Exception {
        // Inspect class:
        Class<?> clazz = Calculator.class;
        System.out.println("Class: " + clazz.getName());
        System.out.println("Methods: " + Arrays.toString(clazz.getMethods()));

        // Access private field:
        Calculator calc = new Calculator();
        Field field = Calculator.class.getDeclaredField("operandA");
        field.setAccessible(true);  // Bypass access control!
        field.set(calc, 42.0);
        System.out.println("operandA: " + field.get(calc));

        // Call private method:
        Method secret = Calculator.class.getDeclaredMethod("secretMethod");
        secret.setAccessible(true);
        System.out.println(secret.invoke(calc));  // "secret!"

        // Run tests:
        runTests(Calculator.class);
    }
}
```

---

### Advanced Concept 3: Java NIO.2 — Modern File I/O

```java
import java.nio.file.*;
import java.nio.file.attribute.*;
import java.nio.charset.*;
import java.io.*;

public class NIOGuide {

    public static void main(String[] args) throws IOException {

        // ── PATH ──────────────────────────────────────────────────────────────
        Path home     = Path.of(System.getProperty("user.home"));
        Path file     = home.resolve("documents").resolve("notes.txt");
        Path relative = Path.of("src", "main", "java", "App.java");
        Path absolute = relative.toAbsolutePath();
        Path parent   = file.getParent();
        Path filename = file.getFileName();

        System.out.println("Parent:   " + parent);
        System.out.println("Filename: " + filename);
        System.out.println("Exists:   " + Files.exists(file));

        // ── READING ───────────────────────────────────────────────────────────
        String content = Files.readString(file);                      // Entire file
        byte[] bytes   = Files.readAllBytes(file);
        List<String> lines = Files.readAllLines(file, StandardCharsets.UTF_8);

        try (var stream = Files.lines(file)) {                        // Lazy stream
            stream.filter(l -> !l.isBlank()).forEach(System.out::println);
        }

        // ── WRITING ───────────────────────────────────────────────────────────
        Files.writeString(file, "Hello, NIO!");                       // Overwrite
        Files.writeString(file, "\nAppended!", StandardOpenOption.APPEND);
        Files.write(file, bytes, StandardOpenOption.CREATE_NEW);
        Files.write(file, lines, StandardCharsets.UTF_8);

        // ── DIRECTORY OPERATIONS ─────────────────────────────────────────────
        Path dir = Path.of("mydir");
        Files.createDirectories(dir);  // Create + parent dirs
        Files.createTempDirectory("prefix");

        // Walk directory tree:
        try (var stream = Files.walk(dir)) {
            stream.filter(Files::isRegularFile)
                  .filter(p -> p.toString().endsWith(".java"))
                  .forEach(System.out::println);
        }

        // Glob matching:
        try (var stream = Files.newDirectoryStream(dir, "*.{java,class}")) {
            for (Path p : stream) System.out.println(p);
        }

        // ── COPY, MOVE, DELETE ────────────────────────────────────────────────
        Files.copy(file, dir.resolve("copy.txt"), StandardCopyOption.REPLACE_EXISTING);
        Files.move(file, dir.resolve("moved.txt"), StandardCopyOption.ATOMIC_MOVE);
        Files.delete(file);
        Files.deleteIfExists(file); // No exception if doesn't exist

        // ── WATCH SERVICE — monitor directory for changes ─────────────────────
        try (WatchService watcher = FileSystems.getDefault().newWatchService()) {
            dir.register(watcher,
                StandardWatchEventKinds.ENTRY_CREATE,
                StandardWatchEventKinds.ENTRY_MODIFY,
                StandardWatchEventKinds.ENTRY_DELETE);

            WatchKey key;
            while ((key = watcher.take()) != null) {
                for (WatchEvent<?> event : key.pollEvents()) {
                    System.out.printf("Event: %s on %s%n",
                        event.kind().name(), event.context());
                }
                key.reset();
            }
        }
    }
}
```

---

### ⚡ Performance Optimization Table

| Technique                           | Impact   | When to Use                                          |
|-------------------------------------|----------|------------------------------------------------------|
| `StringBuilder` over `+` in loops   | Very High| Any string building in loops                         |
| `ArrayList` presize constructor      | Medium   | When approximate size is known: `new ArrayList<>(n)` |
| `HashMap` load factor tuning         | Medium   | High-traffic maps: `new HashMap<>(capacity, 0.75f)`  |
| Parallel Streams                     | High     | CPU-bound on collections > 10,000 elements           |
| `int[]` over `List<Integer>`         | High     | Numeric computation — avoids boxing overhead         |
| `EnumSet`/`EnumMap` for enum keys    | High     | Bit vector implementation — fastest possible         |
| Object pooling (connection pools)    | Very High| Database/HTTP connections — avoid creation cost      |
| `record` over POJO                   | Medium   | Eliminates boilerplate, enables value semantics      |
| JVM flag `-server`                   | High     | Enable aggressive JIT optimizations                  |
| `final` fields/classes/methods       | Medium   | Enables JIT devirtualization optimization            |

---

## 💀 10. 0.01% Hidden Secrets — Ultra Elite

---

### 🔮 Secret 1: The Java Memory Model and `volatile`

```java
public class MemoryModel {
    // Without volatile — this can loop forever!
    // The JVM may cache 'running' in a register on thread 1
    // and never see the update from thread 2.
    private static volatile boolean running = true;
    //                     ↑ volatile guarantees visibility across threads

    /*
       The Java Memory Model (JMM) defines "happens-before" relationships:
       - Actions in a thread HAPPEN-BEFORE each other (within that thread)
       - unlock HAPPENS-BEFORE subsequent lock on same monitor
       - write to volatile HAPPENS-BEFORE all subsequent reads of that volatile
       - Thread.start() HAPPENS-BEFORE any action in the started thread
       - All actions HAPPEN-BEFORE Thread.join() on that thread
       - Transitivity: if A hb B and B hb C, then A hb C

       volatile guarantees:
       1. VISIBILITY — writes immediately visible to all threads
       2. ORDERING — no reordering around volatile reads/writes
       But NOT atomicity! volatile long/double reads are not atomic on 32-bit JVMs.
    */

    public static void main(String[] args) throws InterruptedException {
        Thread worker = new Thread(() -> {
            int i = 0;
            while (running) {  // Reads volatile — sees updated value
                i++;
            }
            System.out.println("Stopped at: " + i);
        });

        worker.start();
        Thread.sleep(1000);
        running = false;  // Volatile write — immediately visible to worker
        worker.join();
    }
}
```

---

### 🔮 Secret 2: `sun.misc.Unsafe` — The JVM's Nuclear Option

```java
import sun.misc.Unsafe;
import java.lang.reflect.Field;

/*
   Unsafe gives direct access to:
   - Allocate/free memory without GC
   - Read/write arbitrary memory addresses
   - CAS (compare-and-swap) operations
   - Object field manipulation bypassing access control
   - Park/unpark threads directly

   THIS IS WHAT java.util.concurrent uses internally!
*/
public class UnsafeDemo {
    private static Unsafe getUnsafe() throws Exception {
        Field f = Unsafe.class.getDeclaredField("theUnsafe");
        f.setAccessible(true);
        return (Unsafe) f.get(null);
    }

    public static void main(String[] args) throws Exception {
        Unsafe unsafe = getUnsafe();

        // Allocate off-heap memory (not managed by GC!):
        long address = unsafe.allocateMemory(1024);
        unsafe.putLong(address, 42L);
        System.out.println(unsafe.getLong(address)); // 42
        unsafe.freeMemory(address); // Must free manually!

        // Create an object WITHOUT calling constructor:
        class Secret {
            private final String value = "initialized";
            Secret() { throw new RuntimeException("Can't create me!"); }
        }
        Secret s = (Secret) unsafe.allocateInstance(Secret.class);
        // No constructor called! s.value is null (default)
        System.out.println(s.value); // null

        // Field offset — used by AtomicInteger internally:
        class Counter { volatile int count = 0; }
        Counter c = new Counter();
        long offset = unsafe.objectFieldOffset(Counter.class.getDeclaredField("count"));
        boolean swapped = unsafe.compareAndSwapInt(c, offset, 0, 1); // CAS!
        System.out.println("CAS success: " + swapped + ", count: " + c.count);
    }
}
```

---

### 🔮 Secret 3: `invokedynamic` and Method Handles

```java
import java.lang.invoke.*;

/*
   invokedynamic is the bytecode instruction added in Java 7 for dynamic dispatch.
   It powers: lambdas, string concatenation (Java 9+), pattern matching, Groovy/Kotlin/Scala.
   
   Method Handles are like typed, performant function pointers.
   They are FASTER than reflection after JIT warmup.
*/
public class MethodHandleDemo {

    public static void main(String[] args) throws Throwable {
        MethodHandles.Lookup lookup = MethodHandles.lookup();

        // Method handle to String.length():
        MethodType type = MethodType.methodType(int.class);
        MethodHandle length = lookup.findVirtual(String.class, "length", type);
        int len = (int) length.invoke("Hello, Method Handles!"); // 22

        // Static method handle:
        MethodHandle parseInt = lookup.findStatic(Integer.class, "parseInt",
            MethodType.methodType(int.class, String.class));
        int num = (int) parseInt.invoke("42"); // 42

        // Constructor handle:
        MethodHandle ctor = lookup.findConstructor(StringBuilder.class,
            MethodType.methodType(void.class, String.class));
        StringBuilder sb = (StringBuilder) ctor.invoke("Hello");

        // Binding (currying):
        MethodHandle bound = length.bindTo("fixed string");
        System.out.println(bound.invoke()); // Always 12

        // Filtering arguments:
        MethodHandle upper = lookup.findVirtual(String.class, "toUpperCase",
            MethodType.methodType(String.class));
        MethodHandle filtered = MethodHandles.filterArguments(
            length, 0,
            upper  // Apply toUpperCase before length
        );
        System.out.println(filtered.invoke("hello")); // 5

        // VarHandle — typed field access with memory semantics:
        class Container { volatile int value = 0; }
        VarHandle vh = MethodHandles.lookup().findVarHandle(
            Container.class, "value", int.class);
        Container c = new Container();
        vh.set(c, 42);                              // Plain write
        vh.setVolatile(c, 100);                     // Volatile write
        int v = (int) vh.compareAndExchange(c, 100, 200); // CAS
        System.out.println("CAS result: " + v + ", value: " + c.value);
    }
}
```

---

### 🔮 Secret 4: ClassLoaders — How Java Loads Classes

```java
/*
   ClassLoader hierarchy:
   Bootstrap ClassLoader (JVM built-in, loads rt.jar/java.base)
       ↑ parent
   Platform ClassLoader (loads JDK modules)
       ↑ parent
   Application ClassLoader (loads classpath: your code)
       ↑ parent
   Custom ClassLoaders (you can create these!)

   Class Loading follows "parent delegation":
   1. Ask parent to load first
   2. Only load yourself if parent can't find it
   This prevents malicious code from replacing java.lang.Object!
*/

import java.net.*;
import java.io.*;

public class ClassLoaderDemo {

    // Dynamic class loading — load a plugin at runtime!
    public static Class<?> loadPlugin(String jarPath, String className) throws Exception {
        URL jarURL = new File(jarPath).toURI().toURL();
        URLClassLoader loader = new URLClassLoader(
            new URL[]{jarURL},
            ClassLoaderDemo.class.getClassLoader() // Parent
        );
        return loader.loadClass(className);
    }

    // Isolating class versions — load the same class twice in different loaders:
    public static void isolationDemo() throws Exception {
        URL[] urls = {new File("mylib.jar").toURI().toURL()};

        ClassLoader loader1 = new URLClassLoader(urls, null); // null parent = bootstrap only
        ClassLoader loader2 = new URLClassLoader(urls, null);

        Class<?> class1 = loader1.loadClass("com.example.Service");
        Class<?> class2 = loader2.loadClass("com.example.Service");

        System.out.println(class1 == class2);        // false — different class objects!
        System.out.println(class1.equals(class2));   // false
        // You can run two incompatible versions of a library simultaneously!
    }

    public static void main(String[] args) {
        // Inspect the classloader hierarchy:
        ClassLoader cl = ClassLoaderDemo.class.getClassLoader();
        while (cl != null) {
            System.out.println(cl.getClass().getName());
            cl = cl.getParent();
        }
        System.out.println("Bootstrap (null)");

        // Every class knows its loader:
        System.out.println(String.class.getClassLoader()); // null = bootstrap
        System.out.println(ClassLoaderDemo.class.getClassLoader()); // app classloader
    }
}
```

---

### 🔮 Secret 5: Java Agents — Bytecode Instrumentation

```java
/*
   A Java Agent is a JAR that hooks into the JVM startup and can:
   - TRANSFORM classes as they are loaded (bytecode manipulation)
   - Measure memory/time (profilers use this)
   - Add logging/tracing to every method (APM tools)
   - Mock final classes in tests (Mockito uses agents)

   This is how: JProfiler, YourKit, Jacoco, Mockito, Spring AOP work!
*/

// agent/src/main/java/MyAgent.java
import java.lang.instrument.*;
import java.security.ProtectionDomain;

public class MyAgent {

    // Called before main() when -javaagent:agent.jar is passed:
    public static void premain(String args, Instrumentation inst) {
        System.out.println("Agent loaded! Args: " + args);

        // Register a class transformer:
        inst.addTransformer(new TimingTransformer(), true);

        // Redefine an already-loaded class:
        // inst.redefineClasses(new ClassDefinition(MyClass.class, newBytecode));
    }

    // Can also be loaded into running JVM:
    public static void agentmain(String args, Instrumentation inst) {
        premain(args, inst);
    }
}

class TimingTransformer implements ClassFileTransformer {
    @Override
    public byte[] transform(ClassLoader loader, String className,
            Class<?> classBeingRedefined, ProtectionDomain domain, byte[] bytecode) {
        // Use ASM or Javassist to modify bytecode here!
        // Add timing code around every method entry/exit
        // This is what gives profilers their method timing data
        return bytecode; // Return null to leave unchanged
    }
}

// Run with: java -javaagent:agent.jar=arg1=value MyApp
```

---

### 🔮 Secret 6: The `String` Pool and `intern()`

```java
public class StringPoolSecrets {
    public static void main(String[] args) {
        // String literals are automatically in the pool:
        String a = "hello";
        String b = "hello";
        System.out.println(a == b);          // true — same pool object!

        // String.intern() — add to pool and return canonical reference:
        String c = new String("hello").intern();
        System.out.println(a == c);          // true — c now points to pool object!

        // Performance trick: intern strings used as Map keys
        // HashMap key comparison uses == shortcut before .equals()
        // Interned strings → faster lookups!
        Map<String, Integer> map = new HashMap<>();
        String key1 = "user-123".intern();  // In pool
        String key2 = "user-123".intern();  // Same object from pool
        System.out.println(key1 == key2);   // true

        // String.format vs StringBuilder vs + vs formatted():
        // Benchmark on hot paths:
        // 1. + with literals → compiler concatenates at compile time
        // 2. + with variables → creates StringBuilder internally (Java 9+: invokedynamic)
        // 3. String.format() → slow (regex parsing on every call!)
        // 4. StringBuilder.append() → fastest for many concatenations
        // 5. String.formatted() → same as String.format() but as instance method

        // Compact Strings (Java 9+):
        // Strings containing only Latin-1 chars are stored as byte[] instead of char[]
        // Halves memory for ASCII strings — transparent optimization!

        // String deduplication in G1GC:
        // JVM flag: -XX:+UseStringDeduplication
        // G1GC finds duplicate String content on heap and merges them
    }
}
```

---

### 🔮 Secret 7: Sealed Interfaces as Type-Safe Discriminated Unions

```java
// Advanced use of sealed classes for algebraic data types (like Rust's enum)

public class ResultType {

    // A Result type — either success with value, or failure with error
    sealed interface Result<T> permits Result.Success, Result.Failure {

        record Success<T>(T value) implements Result<T> {}
        record Failure<T>(String message, Throwable cause) implements Result<T> {
            Failure(String message) { this(message, null); }
        }

        // Factory methods:
        static <T> Result<T> success(T value) { return new Success<>(value); }
        static <T> Result<T> failure(String msg) { return new Failure<>(msg); }
        static <T> Result<T> failure(String msg, Throwable cause) {
            return new Failure<>(msg, cause);
        }

        // Operations:
        default boolean isSuccess() { return this instanceof Success; }

        default <R> Result<R> map(java.util.function.Function<T, R> fn) {
            return switch (this) {
                case Success<T>  s -> success(fn.apply(s.value()));
                case Failure<T>  f -> failure(f.message(), f.cause());
            };
        }

        default T getOrElse(T defaultValue) {
            return switch (this) {
                case Success<T> s -> s.value();
                case Failure<T> f -> defaultValue;
            };
        }

        default Result<T> recover(java.util.function.Function<String, T> recovery) {
            return switch (this) {
                case Success<T> s -> this;
                case Failure<T> f -> success(recovery.apply(f.message()));
            };
        }
    }

    static Result<Integer> parseInteger(String s) {
        try {
            return Result.success(Integer.parseInt(s));
        } catch (NumberFormatException e) {
            return Result.failure("Not a valid integer: " + s, e);
        }
    }

    public static void main(String[] args) {
        Result<Integer> r1 = parseInteger("42");
        Result<Integer> r2 = parseInteger("abc");

        r1.map(n -> n * 2)
          .map(n -> "Result: " + n)
          .getOrElse("Failed");  // "Result: 84"

        int val = r2.recover(msg -> -1).getOrElse(0);  // -1
        System.out.println(val);

        // Pattern match on result:
        switch (r1) {
            case Result.Success<Integer> s -> System.out.println("Got: " + s.value());
            case Result.Failure<Integer> f -> System.err.println("Error: " + f.message());
        }
    }
}
```

---

### 🔮 Secret 8: Project Loom — Virtual Threads (Java 21)

```java
import java.util.concurrent.*;

/*
   Virtual threads (Project Loom) are:
   - Lightweight threads managed by the JVM (not the OS)
   - Can create MILLIONS of them (vs ~thousands of OS threads)
   - Block cheaply — JVM unmounts from carrier thread while waiting for I/O
   - Drop-in replacement for normal threads in most code
   - Makes thread-per-request model viable again (vs reactive/async)
*/
public class VirtualThreads {

    public static void main(String[] args) throws Exception {

        // Create a virtual thread:
        Thread vt = Thread.ofVirtual().start(() ->
            System.out.println("Virtual thread: " + Thread.currentThread())
        );
        vt.join();

        // Create with name:
        Thread.ofVirtual().name("my-virtual-thread").start(() -> {
            System.out.println(Thread.currentThread().isVirtual()); // true
        }).join();

        // ExecutorService with virtual threads:
        try (var executor = Executors.newVirtualThreadPerTaskExecutor()) {
            // Create 1 MILLION virtual threads — impossible with OS threads!
            var futures = new java.util.ArrayList<Future<Long>>();
            for (int i = 0; i < 1_000_000; i++) {
                futures.add(executor.submit(() -> {
                    Thread.sleep(1000); // Block — JVM unmounts, carrier thread freed
                    return Thread.currentThread().threadId();
                }));
            }
            System.out.println("Submitted 1M tasks. Waiting...");
            futures.get(0).get(); // Wait for first
        }
        System.out.println("Done!");

        // Spring Boot 3.2+ can use virtual threads automatically:
        // spring.threads.virtual.enabled=true
    }
}
```

---

### 🔮 Secret 9: JIT Compilation Tricks — Influence the Optimizer

```java
/*
   The JVM JIT (Just-In-Time) compiler optimizes "hot" code.
   Understanding JIT helps write faster Java:

   Tiered Compilation:
   Level 0: Interpreted
   Level 1: C1 compiled (fast compile, minimal optimization)
   Level 2: C1 compiled (limited profiling)
   Level 3: C1 compiled (full profiling)  ← most code runs here
   Level 4: C2 compiled (aggressive optimization after profiling)

   JIT Optimizations:
   - Inlining: small methods inlined at call site (avoids call overhead)
   - Dead code elimination: unreachable code removed
   - Loop unrolling: loop body repeated to reduce branch overhead
   - Escape analysis: objects that don't escape allocated on stack (no GC!)
   - Devirtualization: virtual method calls replaced with direct calls
   - Intrinsics: methods replaced with CPU-specific instructions
*/

public class JITTricks {

    // ✅ Mark performance-critical loops to help JIT:
    // -XX:+PrintCompilation to see what gets compiled
    // -XX:+UnlockDiagnosticVMOptions -XX:+PrintInlining to see inlining

    // JIT-friendly: simple, hot, small methods get inlined:
    private static boolean isEven(int n) { return (n & 1) == 0; }  // Likely inlined

    // Object escape analysis — this object may be stack-allocated!
    public static int noEscape() {
        int[] arr = new int[10];  // Doesn't escape this method
        for (int i = 0; i < 10; i++) arr[i] = i;
        return arr[5];  // JIT may allocate arr on stack — zero GC pressure!
    }

    // Loop optimizations:
    public static long sumArray(long[] arr) {
        long sum = 0;
        for (long v : arr) sum += v;  // JIT may SIMD-vectorize this!
        return sum;
    }

    // JMH (Java Microbenchmark Harness) — proper benchmarking:
    // @Benchmark — prevents dead code elimination
    // @Warmup    — JIT warms up properly before measurement
    // @Fork      — fresh JVM for each run
    // Never use System.currentTimeMillis() for micro-benchmarks!
}
```

---

### 🔮 Secret 10: Annotation Processing — Compile-Time Code Generation

```java
import javax.annotation.processing.*;
import javax.lang.model.*;
import javax.lang.model.element.*;
import javax.tools.*;
import java.io.*;
import java.util.Set;

/*
   Annotation processors run at COMPILE TIME and can:
   - Generate new Java source files
   - Validate code structure
   - Generate boilerplate (Lombok uses this!)
   - Build service loader files

   This is how Lombok, MapStruct, Dagger, AutoValue, and Room work!
*/

@SupportedAnnotationTypes("com.example.Builder")
@SupportedSourceVersion(SourceVersion.RELEASE_21)
public class BuilderProcessor extends AbstractProcessor {

    @Override
    public boolean process(Set<? extends TypeElement> annotations, RoundEnvironment roundEnv) {
        for (TypeElement annotation : annotations) {
            for (Element element : roundEnv.getElementsAnnotatedWith(annotation)) {
                if (element.getKind() != ElementKind.CLASS) continue;

                TypeElement classElement = (TypeElement) element;
                String className = classElement.getSimpleName().toString();
                String packageName = processingEnv.getElementUtils()
                    .getPackageOf(classElement).getQualifiedName().toString();

                // Generate Builder source code:
                try {
                    JavaFileObject file = processingEnv.getFiler()
                        .createSourceFile(packageName + "." + className + "Builder");
                    try (PrintWriter out = new PrintWriter(file.openWriter())) {
                        out.println("package " + packageName + ";");
                        out.println("public class " + className + "Builder {");
                        // Generate builder methods for each field...
                        out.println("}");
                    }
                } catch (IOException e) {
                    processingEnv.getMessager().printMessage(
                        Diagnostic.Kind.ERROR, e.getMessage(), element);
                }
            }
        }
        return true;
    }
}
```

---

## 🗺️ 11. Complete Roadmap

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — FOUNDATION (Week 1-3)
├── Week 1: Syntax, data types, operators, control flow, methods, arrays
├── Week 2: OOP fundamentals — classes, objects, constructors, inheritance, polymorphism
└── Week 3: Interfaces, abstract classes, exceptions, String mastery
    └── Project: Simple banking system or library management console app

PHASE 2 — CORE JAVA (Week 4-7)
├── Week 4: Collections Framework — List, Set, Map, Queue, iterators, Comparable/Comparator
├── Week 5: Generics, enums, annotations, nested classes, varargs
├── Week 6: Functional Java — lambdas, Stream API, Optional, method references
└── Week 7: File I/O with NIO.2, JDBC basics, JSON (Jackson/Gson)
    └── Project: Student management system with file persistence

PHASE 3 — ADVANCED JAVA (Week 8-12)
├── Week 8:  Multithreading — Thread, Runnable, synchronized, volatile, locks
├── Week 9:  java.util.concurrent — ExecutorService, CompletableFuture, atomic, concurrent collections
├── Week 10: Modern Java features — records, sealed classes, pattern matching (Java 17-21)
├── Week 11: JVM internals — memory model, GC, class loading, reflection
└── Week 12: Build tools (Maven/Gradle), unit testing (JUnit 5, Mockito)
    └── Project: Multithreaded file processor or event-driven order system

PHASE 4 — ENTERPRISE JAVA (Month 4-6)
├── Month 4: Spring Boot — REST APIs, Spring Data JPA, Spring Security, testing
├── Month 5: Microservices — Spring Cloud, Docker, Kubernetes, message queues (Kafka)
└── Month 6: Performance tuning — JVM profiling, GC tuning, virtual threads (Loom)
    └── Project: Full microservices application deployed with Docker

PHASE 5 — EXPERT / 0.01% (Month 7+)
├── JVM bytecode (javap), ASM bytecode manipulation
├── Java agents and instrumentation
├── Method handles and invokedynamic
├── GraalVM native compilation
├── Contribute to OpenJDK or major open source Java project
└── Project: Build and publish a library/framework on Maven Central
```

---

### 🏁 Milestone Checklist

- [ ] I can write, compile, and run a Java program from memory
- [ ] I understand the difference between heap and stack, primitive and reference types
- [ ] I can design a class hierarchy with proper inheritance and interfaces
- [ ] I understand the Collections Framework and choose the right data structure
- [ ] I can write type-safe code using generics
- [ ] I can process data using the Stream API fluently
- [ ] I understand multithreading — race conditions, deadlocks, and how to avoid them
- [ ] I've built a Spring Boot REST API with JPA and tests
- [ ] I understand the JVM memory model, GC, and can tune JVM flags
- [ ] I can use reflection to inspect and modify code at runtime
- [ ] I understand how lambdas work internally (invokedynamic + functional interfaces)
- [ ] I've profiled and optimized a Java application
- [ ] I understand virtual threads and Project Loom

---

## 🧩 12. Bonus Deep Insights

---

### 🔮 Mental Model: "Java is a Contract Language"

Java's design philosophy is built on contracts at every level:

- **Types are contracts** — a `String` guarantees certain methods; a `Comparable` guarantees ordering; an `Iterable` guarantees iteration.
- **Access modifiers are contracts** — `private` is a contract: "this is internal, not for you"; `public` is a contract: "this is the stable API."
- **Interfaces are contracts** — implementing `List` is a contract to fulfill all `List` behaviors.
- **Checked exceptions are contracts** — `throws IOException` is a contract: "I might fail this way, you must handle it."
- **The JVM specification is a contract** — any JVM implementation that passes the TCK (Technology Compatibility Kit) guarantees your code runs identically.

Java's verbosity IS the contracts being explicit. When you write a class in Java, you are writing a specification for a component. That's why enterprise systems trust it.

---

### 🤫 Deep Insight 1: Type Erasure — The Generics Lie

```java
// At runtime, ALL of these are the same type: ArrayList
List<String>  strings = new ArrayList<>();
List<Integer> ints    = new ArrayList<>();
List<Object>  objects = new ArrayList<>();

System.out.println(strings.getClass() == ints.getClass()); // TRUE!
// Both are just ArrayList.class at runtime — generics are ERASED!

// Consequences:
// 1. Cannot do: new T()
// 2. Cannot do: new T[10]
// 3. Cannot do: obj instanceof List<String>  — only obj instanceof List
// 4. Cannot overload by generic type: void process(List<String> vs List<Integer>) — same erasure!
// 5. Cannot catch generic exception types

// Workaround — type token:
public <T> T deserialize(String json, Class<T> type) {
    // Use type at runtime — works because Class<T> is not erased
}

// How Gson handles this — TypeToken:
Type listType = new TypeToken<List<String>>(){}.getType();
// The anonymous subclass retains the generic type at runtime via getGenericSuperclass()
```

---

### 🤫 Deep Insight 2: The Cost of Autoboxing

```java
// Autoboxing converts int ↔ Integer — looks harmless, isn't
// Cache: Integer.valueOf(-128 to 127) — reuses cached objects!
Integer a = 127;
Integer b = 127;
System.out.println(a == b);  // true — cached!

Integer c = 128;
Integer d = 128;
System.out.println(c == d);  // false — new objects!
System.out.println(c.equals(d)); // true — ALWAYS use equals()

// Performance: avoid boxing in hot loops!
long sum = 0L;
Long boxedSum = 0L;
for (int i = 0; i < 10_000_000; i++) {
    sum += i;      // Fast — no boxing
    boxedSum += i; // SLOW — unbox boxedSum, add, rebox each iteration!
}

// Use primitive streams:
long streamSum = java.util.stream.LongStream.range(0, 10_000_000).sum(); // No boxing!
// vs:
long streamSumSlow = java.util.stream.Stream.iterate(0L, n -> n + 1)
    .limit(10_000_000).reduce(0L, Long::sum); // Boxing happens!
```

---

### 🤫 Deep Insight 3: Java Is Not Pure OOP

Despite being called "object-oriented," Java has these non-OOP elements:

1. **Primitive types** — `int`, `long`, `boolean`, etc. are NOT objects. They can't call methods, can't be null, don't extend Object.
2. **Static methods/fields** — belong to classes, not instances. True OOP has no concept of "class-level" state.
3. **`null`** — a billion-dollar mistake. In true OOP, everything is an object. `null` breaks that.
4. **Arrays** — `int[]` is an object but has no methods beyond `.length`. It's a primitive hybrid.
5. **Operators** — operators like `+`, `-`, `*` are not methods (unlike in Kotlin/Python). You can't override `+` for your own class.

Java 21+ moves closer to "pure" OOP with records, sealed types, and pattern matching — borrowing from functional languages while keeping the JVM foundation.

---

### 🧠 The Big Picture — Java in the Modern Ecosystem

```
The JVM Ecosystem (not just Java!):
  Java    → The original, most mature, dominant in enterprise
  Kotlin  → JetBrains' Java successor — concise, null-safe, coroutines
  Scala   → Functional + OOP hybrid, Akka, Spark use this
  Clojure → Lisp on JVM — dynamic, immutable-first
  Groovy  → Dynamic typing on JVM, Gradle build scripts
  Ceylon  → Modern type-safe (mostly extinct now)
  All share: JVM, GC, JIT, libraries, tools — interoperable!

Java Version Timeline:
  Java 8  (2014): Lambdas, Streams, Optional, DateTime API — revolutionary
  Java 11 (2018): LTS, String methods, var in lambdas, HTTP Client
  Java 17 (2021): LTS, sealed classes, records, pattern matching preview
  Java 21 (2023): LTS, virtual threads (Loom), pattern matching stable, sequenced collections
  Java 25 (2025): Value objects (Valhalla), ahead-of-time compilation improvements

Where Java is going:
  Project Loom    → Virtual threads — million concurrent connections
  Project Valhalla → Value types — eliminate boxing, stack allocation of objects
  Project Amber   → Smaller features: data classes, records, pattern matching
  Project Panama  → Foreign function & memory API — call C/C++ without JNI
  GraalVM        → Native compilation — Java with startup time < 100ms
```

---

## 📌 13. Summary (Quick Revision & Cheat Sheet)

---

### Core Concepts (1-line each)

| Concept                | What It Means                                                                    |
|------------------------|----------------------------------------------------------------------------------|
| Write Once Run Anywhere| Bytecode compiled once runs on any JVM — OS/hardware independent                |
| Static typing          | All variable types declared at compile time — type errors caught before running  |
| Garbage Collection     | JVM automatically reclaims memory — no malloc/free                               |
| Pass by Value          | Java always passes copies — for objects, the copy is the reference               |
| Type Erasure           | Generic types removed at compile time — `List<String>` = `List` at runtime       |
| Checked Exceptions     | Must be declared with `throws` or caught — compile-time safety                   |
| Autoboxing             | Automatic int ↔ Integer conversion — convenient but has performance cost         |
| JIT Compilation        | Hot code compiled to native machine code at runtime — gets faster over time      |
| Volatile               | Ensures visibility of variable across threads — not atomicity                    |
| Virtual Threads        | JVM-managed threads — millions possible, cheap blocking (Java 21+)               |

---

### The 10 Things to Remember

1. ✅ **Always use `.equals()` for String comparison** — `==` compares references
2. ✅ **Use `StringBuilder` for string building in loops** — `+` is O(n²)
3. ✅ **Always close resources with try-with-resources** — prevents leaks
4. ✅ **Use `Optional` instead of returning `null`** — forces callers to handle absence
5. ✅ **Prefer `interface` over `abstract class`** — allows multiple implementation
6. ✅ **Override `hashCode` whenever you override `equals`** — contract requirement
7. ✅ **Restore the interrupt flag when catching `InterruptedException`** — don't swallow it
8. ✅ **Don't modify collections while iterating** — use `removeIf()` or collect new
9. ✅ **Use `final` fields for immutability** — thread-safe by default
10. ✅ **Profile before optimizing** — JIT makes guesses unreliable; measure everything

---

### Quick Reference Cheat Sheet

```java
// ── DATA TYPES QUICK REF ──────────────────────────────────────────────────
byte(8)  short(16)  int(32)  long(64)L  float(32)f  double(64)  char(16)  boolean
// Wrapper classes: Byte Short Integer Long Float Double Character Boolean

// ── STRING METHODS ────────────────────────────────────────────────────────
s.length()           s.charAt(i)          s.indexOf(c)         s.lastIndexOf(c)
s.substring(i)       s.substring(i, j)    s.toUpperCase()      s.toLowerCase()
s.trim()             s.strip()            s.replace(old, new)  s.replaceAll(regex, rep)
s.split(regex)       s.contains(sub)      s.startsWith(pre)    s.endsWith(suf)
s.equals(t)          s.equalsIgnoreCase() s.compareTo(t)       s.isEmpty()
s.isBlank()          s.repeat(n)          s.formatted(args)    String.join(sep, elems)
String.valueOf(x)    Integer.parseInt(s)  Double.parseDouble(s)

// ── COLLECTIONS ───────────────────────────────────────────────────────────
new ArrayList<>()    new LinkedList<>()   new ArrayDeque<>()
new HashSet<>()      new LinkedHashSet<>() new TreeSet<>()
new HashMap<>()      new LinkedHashMap<>() new TreeMap<>()
List.of(...)         Set.of(...)          Map.of(k1,v1, k2,v2)  // Immutable
Collections.sort(list)   Collections.shuffle(list)   Collections.reverse(list)
Collections.unmodifiableList(list)

// ── STREAM QUICK REF ──────────────────────────────────────────────────────
stream()  parallelStream()
.filter(pred)    .map(fn)        .flatMap(fn)      .distinct()
.sorted()        .sorted(comp)   .limit(n)         .skip(n)
.peek(action)    .mapToInt(fn)   .mapToLong(fn)    .mapToDouble(fn)
// Terminals:
.collect(Collectors.toList())       .collect(Collectors.toUnmodifiableList())
.collect(Collectors.toSet())        .collect(Collectors.joining(sep))
.collect(Collectors.groupingBy(fn)) .collect(Collectors.counting())
.collect(Collectors.averagingDouble(fn))
.forEach(action)   .count()    .findFirst()   .findAny()
.anyMatch(pred)    .allMatch(pred)  .noneMatch(pred)
.min(comp)         .max(comp)       .reduce(identity, acc)
.toList()  // Java 16+ — unmodifiable

// ── FUNCTIONAL INTERFACES ─────────────────────────────────────────────────
Function<T,R>       t -> r        .apply(t)       .andThen(f).compose(f)
BiFunction<T,U,R>   (t,u) -> r   .apply(t,u)
Predicate<T>        t -> bool     .test(t)        .and().or().negate()
Consumer<T>         t -> void     .accept(t)      .andThen(c)
Supplier<T>         () -> t       .get()
UnaryOperator<T>    t -> t        .apply(t)
BinaryOperator<T>   (t,t) -> t   .apply(t,t)
Runnable            () -> void    .run()
Callable<T>         () throws -> t .call()

// ── MODERN JAVA (17-21) ───────────────────────────────────────────────────
record Point(int x, int y) {}       // Immutable data class
sealed interface Shape permits Circle, Rect {}  // Exhaustive hierarchy
var name = "Aryan";                 // Type inference (local only)
if (obj instanceof String s) {}     // Pattern matching instanceof
switch (shape) { case Circle c -> ...; case Rect r -> ...; }  // Pattern switch
"Text with %s".formatted("args")    // Formatted strings
List.copyOf(list)                   // Unmodifiable copy
Map.copyOf(map)
Stream.toList()                     // Unmodifiable list (Java 16+)
Thread.ofVirtual().start(() -> {})  // Virtual thread (Java 21)

// ── CONCURRENCY ESSENTIALS ────────────────────────────────────────────────
Thread t = new Thread(runnable); t.start(); t.join();
ExecutorService ex = Executors.newFixedThreadPool(n);
Future<T> f = ex.submit(callable); f.get(); f.cancel(true);
ex.shutdown(); ex.awaitTermination(1, TimeUnit.MINUTES);
CompletableFuture.supplyAsync(supplier).thenApply(fn).exceptionally(fn).join();
CompletableFuture.allOf(cf1, cf2, cf3).join();
new AtomicInteger(0); .incrementAndGet(); .compareAndSet(exp, update);
synchronized(lock) {} ; volatile field; ReentrantLock lock = new ReentrantLock();

// ── IMPORTANT JVM FLAGS ───────────────────────────────────────────────────
-Xms512m             Initial heap size
-Xmx4g               Maximum heap size
-XX:+UseG1GC         Use G1 garbage collector
-XX:+UseZGC          Use Z GC (ultra-low latency, Java 15+)
-verbose:gc          Print GC events
-XX:+PrintCompilation See JIT compilation
-ea                  Enable assertions
-javaagent:agent.jar Attach Java agent
```

---

### What's Next? Domain-Specific Java Paths

After mastering Java deeply, your path forward depends on your goal:

- 📘 **Spring Boot + Microservices** — Build production REST APIs, integrate with databases, Kafka, Redis
- 📘 **Kotlin** — JVM language with null safety, coroutines, and Python-like conciseness
- 📘 **Android Development** — Kotlin + Jetpack Compose for modern Android apps
- 📘 **Apache Kafka** — Distributed event streaming for high-throughput data pipelines
- 📘 **Apache Spark** — Large-scale data processing in Java/Scala
- 📘 **GraalVM** — Compile Java to native binaries with <100ms startup
- 📘 **JVM Internals** — Bytecode, ASM, Java agents, JVM tuning
- 📘 **Design Patterns** — Gang of Four patterns implemented in Java (Builder, Factory, Observer, Strategy, etc.)

---

> 💬 *"Java is to JavaScript what Car is to Carpet."*
> — Chris Heilmann (humorous note on their unrelated natures)

> 💬 *"The best thing about Java is its community. The worst thing about Java is that it has too much community input."*
> — Linus Torvalds

> 💬 *"Write code that is easy to delete, not easy to extend. Java makes deletion visible — all those types tell you what you're about to remove."*

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: Java — Complete Language Mastery | Version: 1.0*
*Sections: 13 | Level: Beginner → 0.01% Elite*
