# 🐘 PHP — The Ultimate Master Guide
### From Zero to 0.01% Expert — Every Concept, Pattern, Secret & Hidden Power

> 📘 **The most complete PHP guide ever written — beginner to elite.**
>
> 🎯 *Who is this for?* Anyone who wants to go from writing PHP to **mastering** PHP.
> ⏱️ *Time to complete:* Self-paced — days to months
> 🛠️ *What you'll gain:* Every syntax rule, OOP pattern, security technique, performance trick, and 0.01% hidden secret that separates an elite PHP developer from the rest.

---

## Table of Contents

1. [🧠 What is PHP?](#1-what-is-php-super-simple)
2. [🌍 Why PHP Exists & Still Dominates](#2-why-php-exists--still-dominates)
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

## 🧠 1. What is PHP? (Super Simple)

### The 12-Year-Old Explanation

Imagine you visit a website like Facebook or WordPress. When you type in your username and password and press Login, something on the server has to check your credentials, look up your profile in a database, and build a custom page just for you. That "something" — for billions of web pages — is **PHP**.

PHP stands for **PHP: Hypertext Preprocessor** (yes, it's a recursive acronym — a joke by its creator). It was invented by **Rasmus Lerdorf** in 1994, originally as a set of Perl scripts to track visits to his online resume. He called it "Personal Home Page Tools."

Over 30 years later, PHP runs on **77% of all websites** where the server-side language is known — including WordPress, Facebook (originally), Wikipedia, Slack (originally), Etsy, and millions more. It powers the internet more than any other server-side language by sheer volume.

PHP is a **server-side** language — it runs on the web server, not in the browser. When a user visits a PHP-powered page, the server runs the PHP code, generates HTML, and sends that HTML to the browser. The browser never sees the PHP — only its output.

### Real-Life Analogy

💡 **Think of it like this:**
A restaurant has a menu (HTML — what customers see). When you order a custom meal, the waiter takes your order to the kitchen. The **kitchen is PHP** — it takes your request, checks the pantry (database), mixes ingredients (logic), and prepares a complete meal (HTML page) that gets sent out to you.

The customer (browser) only ever sees the plated dish. They never see the kitchen. PHP lives in the kitchen — invisible, essential, incredibly productive.

### One-Line Definition

> **PHP** is an open-source, server-side scripting language designed for web development, capable of generating dynamic HTML, interacting with databases, managing files, handling sessions, and building complete web applications and APIs.

---

## 🌍 2. Why PHP Exists & Still Dominates

### The Problem It Solved

In 1994, building dynamic web pages required compiling C programs or writing complex CGI scripts — accessible only to experienced system programmers. Rasmus Lerdorf created PHP to let ordinary developers add dynamic behavior to HTML pages with simple embedded code.

The genius was the **low barrier to entry**: drop a `.php` file on any shared web host, write some `<?php ... ?>` tags, and you have a working dynamic page. No compilation, no deployment pipeline, no server configuration.

### Where PHP Dominates in 2025

| Domain                        | How PHP Is Used                                                        |
|-------------------------------|------------------------------------------------------------------------|
| Content Management            | WordPress powers 43% of ALL websites on the internet                  |
| E-commerce                    | Magento, WooCommerce, OpenCart — trillions in annual transactions      |
| Web Frameworks                | Laravel, Symfony, CodeIgniter — full production applications           |
| API Backends                  | REST and GraphQL APIs serving mobile and SPA frontends                 |
| Enterprise Applications       | Drupal, TYPO3 — government, university, corporate portals              |
| SaaS Products                 | Mailchimp, Hootsuite, Slack (early), Etsy — built on PHP               |
| Wikipedia                     | MediaWiki is pure PHP — serving 1.7 billion unique visitors/month     |
| Facebook (historical)         | PHP was Facebook's original language — they built their own compiler   |
| Hosting Industry              | Every shared host supports PHP out of the box — zero barrier           |
| Education                     | #1 language taught for web development in universities worldwide       |

### Why YOU Should Master It Deeply

1. **The largest web ecosystem** — WordPress alone has 60,000+ plugins, all PHP.
2. **Laravel is one of the most elegant frameworks ever built** — modern PHP is beautiful.
3. **Massive job market** — PHP developers are in extremely high demand globally.
4. **PHP 8.x is fast** — JIT compilation brings PHP within 10-20% of Go for many workloads.
5. **The hidden depths reward mastery** — Fibers, typed properties, match expressions, named arguments — modern PHP is a completely different language from PHP 5.

---

## 🧱 3. Core Fundamentals (Beginner Level)

> 🎯 *Goal: Build an unshakeable foundation. Every concept here is critical.*

---

### Concept 1: PHP Syntax, Setup & Your First Script

```php
<?php
// Every PHP file starts with <?php
// The closing ?> is optional in pure PHP files (and recommended to omit it)

// Running PHP:
// 1. Web server: Apache/Nginx with php-fpm
// 2. CLI: php script.php
// 3. Built-in dev server: php -S localhost:8000

// Comments:
// Single-line comment
# Also single-line comment (shell style)
/* Multi-line
   comment */

/** PHPDoc comment
 *  @param string $name The person's name
 *  @return string Greeting message
 */

// Output:
echo "Hello, World!\n";          // Most common — outputs a string
print "Hello!\n";                // Same as echo but returns 1 (slower)
echo "Hello", " ", "World";     // echo accepts multiple args (print doesn't)

// var_dump — debug output with type info:
var_dump(42);                    // int(42)
var_dump("hello");               // string(5) "hello"
var_dump(true);                  // bool(true)
var_dump(null);                  // NULL
var_dump([1, 2, 3]);            // array(3) { [0]=> int(1) ... }

// print_r — human-readable structure:
print_r([1, 'a' => 2, 'b' => 3]);
// Array ( [0] => 1 [a] => 2 [b] => 3 )

// var_export — PHP-parseable output:
var_export(['key' => 'value']); // array ( 'key' => 'value', )
```

```bash
# Install PHP (Ubuntu):
sudo apt install php php-cli php-fpm php-mysql php-xml php-mbstring

# Check version:
php --version

# Start built-in development server:
php -S localhost:8000 -t public/

# Run a script:
php script.php

# Interactive REPL:
php -a
```

---

### Concept 2: Variables, Data Types & Type System

```php
<?php

// ── VARIABLES — always start with $ ───────────────────────────────────────
$name = "Aryan";          // String
$age  = 17;               // Integer
$gpa  = 9.8;              // Float
$isStudent = true;        // Boolean
$nothing   = null;        // Null

// Variable variables (rarely used but exists):
$varName = "hello";
$$varName = "world";      // Creates $hello = "world"
echo $hello;              // "world"

// ── DATA TYPES ────────────────────────────────────────────────────────────

// 4 SCALAR types:
$int    = 42;             // Integer: -2^63 to 2^63-1 (64-bit)
$hex    = 0x1A;           // Hex: 26
$oct    = 0755;           // Octal: 493
$bin    = 0b11001;        // Binary: 25
$under  = 1_000_000;      // Underscores for readability (PHP 7.4+)
$float  = 3.14;
$sci    = 1.5e3;          // 1500.0
$str    = "Hello";
$bool   = true;           // true, false (case-insensitive but write lowercase)

// 4 COMPOUND types:
$arr  = [1, 2, 3];        // Array (also: array(1, 2, 3) — old syntax)
$obj  = new stdClass();   // Object
// callable, iterable      — special compound types

// 2 SPECIAL types:
$nul  = null;             // No value
// resource               — file handles, DB connections, etc.

// ── TYPE CHECKING ─────────────────────────────────────────────────────────
var_dump(is_int($int));       // true
var_dump(is_float($float));   // true
var_dump(is_string($str));    // true
var_dump(is_bool($bool));     // true
var_dump(is_null($nul));      // true
var_dump(is_array($arr));     // true
var_dump(is_numeric("42"));   // true (string that looks like number)
var_dump(gettype($int));       // "integer"

// ── TYPE JUGGLING (PHP is loosely typed by default) ───────────────────────
var_dump("5" + 3);         // int(8)  — string coerced to int
var_dump("5" . 3);         // string(2) "53" — . is string concat
var_dump(true + true);     // int(2)
var_dump("2 apples" + 5);  // int(7)  — leading numeric string
var_dump("apples" + 5);    // int(5)  — non-numeric string = 0

// ── TYPE CASTING ──────────────────────────────────────────────────────────
$x = "42.7 is a number";
var_dump((int)$x);         // int(42)
var_dump((float)$x);       // float(42.7)
var_dump((string)42);      // string(2) "42"
var_dump((bool)"");        // bool(false) — empty string is falsy
var_dump((bool)"0");       // bool(false) — "0" is also falsy!
var_dump((array)"hello");  // array(1) { [0]=> string(5) "hello" }

// intval(), floatval(), strval() — explicit conversions:
$n = intval("0xFF", 16);   // 255 — convert hex string

// settype() — convert in place:
$val = "42";
settype($val, "integer");
var_dump($val);            // int(42)

// ── STRICT TYPES (declare at top of file — PHP 7+) ───────────────────────
// declare(strict_types=1);
// With strict_types, PHP enforces exact types in function parameters
// MUST be the very first line after <?php
```

---

### Concept 3: Strings — Complete Mastery

```php
<?php

$name = "Aryan";
$age  = 17;

// ── STRING TYPES ──────────────────────────────────────────────────────────

// Double quotes — variable interpolation + escape sequences:
$greeting = "Hello, $name! You are $age years old.";
$complex  = "Value: {$name}'s score";     // Curly braces for complex expressions
$escaped  = "Tab:\t Newline:\n Quote:\""; // Escape sequences work

// Single quotes — NO interpolation, NO escape sequences (except \\ and \'):
$literal  = 'Hello, $name';   // Literal "$name" — no substitution
$single   = 'It\'s fine';     // Only \' and \\ work

// Heredoc — like double-quoted, indentation support (PHP 7.3+):
$text = <<<EOT
    Hello, $name!
    You are $age years old.
    EOT;  // Closing marker can be indented (PHP 7.3+)

// Nowdoc — like single-quoted, no interpolation:
$raw = <<<'EOT'
    Hello, $name!  (no interpolation)
    EOT;

// ── STRING FUNCTIONS — EXHAUSTIVE REFERENCE ─────────────────────────────

// Length:
strlen("Hello");                  // 5 (bytes, not characters!)
mb_strlen("Hello 🌍");            // 7 (characters — USE THIS for Unicode)

// Case:
strtolower("HELLO");              // "hello"
strtoupper("hello");              // "HELLO"
ucfirst("hello world");           // "Hello world"
ucwords("hello world");           // "Hello World"
mb_strtolower("HÉLLO");           // "héllo" — Unicode-safe

// Trimming:
trim("  hello  ");                // "hello"
ltrim("  hello  ");               // "hello  "
rtrim("  hello  ");               // "  hello"
trim("***hello***", "*");         // "hello" — custom chars

// Searching:
strpos("hello world", "world");   // 6 (first occurrence)
strrpos("hello world", "o");      // 7 (last occurrence)
strpos("hello", "xyz");           // false — not found!
str_contains("hello world", "world"); // true (PHP 8.0+)
str_starts_with("hello", "he");       // true (PHP 8.0+)
str_ends_with("hello", "lo");         // true (PHP 8.0+)

// Replacement:
str_replace("world", "PHP", "hello world");  // "hello PHP"
str_ireplace("WORLD", "PHP", "hello World"); // Case-insensitive
str_replace(["a","e","i"], "*", "aryan");   // Replace multiple: "*ry*n"
substr_replace("hello world", "PHP", 6, 5); // "hello PHP"

// Extraction:
substr("hello world", 6);         // "world"
substr("hello world", 6, 3);      // "wor"
substr("hello world", -5);        // "world" — negative = from end
mb_substr("Hello 🌍", 6, 1);      // "🌍" — Unicode-safe

// Splitting & Joining:
explode(",", "a,b,c");             // ["a", "b", "c"]
explode(",", "a,b,c", 2);          // ["a", "b,c"] — limit to 2 parts
implode(", ", ["a", "b", "c"]);    // "a, b, c"
str_split("hello", 2);             // ["he", "ll", "o"] — split into chunks

// Counting:
substr_count("hello world", "l");  // 3
str_word_count("Hello World");     // 2

// Formatting:
sprintf("Name: %s, Age: %d, GPA: %.2f", "Aryan", 17, 9.8);
// "Name: Aryan, Age: 17, GPA: 9.80"
printf("Hello, %s!\n", "World");  // Print formatted
number_format(1234567.891, 2, '.', ','); // "1,234,567.89"
money_format('%.2n', 1234.5);     // Locale-aware (deprecated — use NumberFormatter)

// Padding:
str_pad("5", 3, "0", STR_PAD_LEFT);   // "005"
str_pad("hi", 10, "-", STR_PAD_BOTH); // "----hi----"

// Repetition:
str_repeat("ab", 3);              // "ababab"

// Reversing:
strrev("hello");                   // "olleh"

// Comparison:
strcmp("hello", "hello");          // 0 (equal)
strcasecmp("HELLO", "hello");      // 0 (case-insensitive equal)
similar_text("hello", "world", $percent); // $percent = similarity %

// Encoding:
htmlspecialchars("<script>alert('XSS')</script>"); // &lt;script&gt;...
htmlspecialchars_decode("&lt;b&gt;");              // "<b>"
strip_tags("<p>Hello</p>");                         // "Hello"
htmlentities("café");                              // "caf&eacute;"
urlencode("hello world");                          // "hello+world"
rawurlencode("hello world");                       // "hello%20world"
base64_encode("binary data");                      // base64 string
base64_decode("YmluYXJ5IGRhdGE=");                // "binary data"

// Hashing:
md5("password");                   // 32-char hex (NEVER use for passwords!)
sha1("data");                      // 40-char hex
hash("sha256", "data");            // sha256 hex string
password_hash("secret", PASSWORD_BCRYPT); // Secure password hashing
password_verify("secret", $hash);  // Verify password

// Regular expressions:
preg_match('/^\d+$/', "123");       // 1 (matches)
preg_match('/^(\w+)@(\w+)\.(\w+)$/', "user@example.com", $matches);
preg_match_all('/\d+/', "I have 3 cats and 2 dogs", $matches); // [["3","2"]]
preg_replace('/\s+/', ' ', "hello   world");  // "hello world"
preg_split('/[\s,]+/', "one two,three");       // ["one","two","three"]
```

---

### Concept 4: Arrays — PHP's Most Powerful Data Structure

```php
<?php

// PHP arrays are actually ordered maps (like Python's OrderedDict):
// They can be indexed, associative, or mixed!

// ── INDEXED ARRAYS ────────────────────────────────────────────────────────
$fruits = ["apple", "banana", "cherry"];
$fruits = array("apple", "banana", "cherry"); // Old syntax — equivalent

echo $fruits[0];    // "apple"
echo $fruits[1];    // "banana"
$fruits[] = "date"; // Append: adds at next numeric index

// ── ASSOCIATIVE ARRAYS ────────────────────────────────────────────────────
$person = [
    "name"  => "Aryan",
    "age"   => 17,
    "city"  => "Kolkata",
    "skills" => ["Python", "PHP", "Go"],
];

echo $person["name"];   // "Aryan"
$person["grade"] = "XI"; // Add new key

// ── MIXED ARRAYS ──────────────────────────────────────────────────────────
$mixed = [0 => "zero", "one" => 1, 2 => "two", "three" => 3];

// ── MULTIDIMENSIONAL ARRAYS ───────────────────────────────────────────────
$students = [
    ["name" => "Aryan",  "gpa" => 9.8],
    ["name" => "Priya",  "gpa" => 9.2],
    ["name" => "Rahul",  "gpa" => 8.9],
];
echo $students[0]["name"]; // "Aryan"

// ── ARRAY FUNCTIONS — COMPLETE REFERENCE ──────────────────────────────────

// ADDING/REMOVING:
array_push($fruits, "elderberry");        // Add to end (use $arr[] = val instead)
array_pop($fruits);                       // Remove + return last
array_unshift($fruits, "avocado");        // Add to beginning (SLOW — reindexes)
array_shift($fruits);                     // Remove + return first (SLOW — reindexes)
array_splice($fruits, 1, 2);              // Remove 2 elements at index 1
array_splice($fruits, 1, 0, ["x", "y"]); // Insert without removing

// SEARCHING:
in_array("banana", $fruits);             // true/false membership test
in_array("banana", $fruits, true);       // Strict type check
array_search("banana", $fruits);         // Returns key or false
array_key_exists("name", $person);       // true
isset($person["name"]);                  // true (also false if null)
array_keys($person);                     // ["name", "age", "city", "skills"]
array_values($fruits);                   // Re-indexed numeric array
array_column($students, "name");         // ["Aryan", "Priya", "Rahul"]
array_column($students, "gpa", "name");  // ["Aryan"=>9.8, "Priya"=>9.2, ...]

// SORTING:
sort($fruits);                           // Sort values, reset keys
rsort($fruits);                          // Reverse sort values
asort($person);                          // Sort values, KEEP keys (assoc)
arsort($person);                         // Reverse sort values, keep keys
ksort($person);                          // Sort by KEY
krsort($person);                         // Reverse sort by key
usort($students, fn($a, $b) => $b["gpa"] <=> $a["gpa"]); // Custom sort
uasort($arr, fn($a, $b) => $a - $b);     // Custom sort, keep keys
uksort($arr, fn($a, $b) => strcmp($a, $b)); // Sort by key with custom fn
array_multisort($gpas, SORT_DESC, $students); // Sort multiple arrays together

// TRANSFORMATION:
array_map(fn($x) => $x * 2, [1,2,3]);    // [2, 4, 6]
array_map(null, [1,2,3], [4,5,6]);        // [[1,4],[2,5],[3,6]] — zip!
array_filter([1,2,3,4,5], fn($x) => $x % 2 === 0); // [1=>2, 3=>4]
array_filter([0, "", null, false, 1, "a"]);          // Removes falsy values
array_reduce([1,2,3,4,5], fn($carry, $item) => $carry + $item, 0); // 15

// SLICING & COMBINING:
array_slice($fruits, 1, 3);             // 3 elements starting at index 1
array_slice($fruits, 1, 3, true);       // Preserve keys
array_chunk($fruits, 2);                // Split into chunks of 2
array_merge($arr1, $arr2);             // Merge (numeric keys reset, string keys overwrite)
array_replace($defaults, $overrides);  // Overwrite keys
$arr1 + $arr2;                         // Union (KEEPS left side keys)
array_combine($keys, $values);         // Create assoc array from 2 arrays
array_zip_key($keys, $values);         // Alias

// UNIQUE & COUNTING:
array_unique([1,2,2,3,3,3]);          // [0=>1, 1=>2, 3=>3]
array_count_values(["a","b","a","c","b","a"]); // ["a"=>3,"b"=>2,"c"=>1]
count($fruits);                        // Number of elements
count($students, COUNT_RECURSIVE);     // Count all recursively

// SET OPERATIONS:
array_intersect($a, $b);              // Values in both
array_intersect_key($a, $b);          // Keys in both
array_diff($a, $b);                   // Values in $a but not $b
array_diff_key($a, $b);              // Keys in $a but not $b

// FLIPPING & FILLING:
array_flip(["a"=>"x","b"=>"y"]);     // ["x"=>"a","y"=>"b"]
array_fill(0, 5, "default");         // ["default","default","default","default","default"]
array_fill_keys(["a","b","c"], 0);   // ["a"=>0,"b"=>0,"c"=>0]
range(1, 10);                        // [1,2,3,4,5,6,7,8,9,10]
range('a', 'z');                     // ['a','b',...,'z']
range(0, 1, 0.1);                    // [0, 0.1, 0.2, ..., 1.0]

// RANDOM:
shuffle($arr);                       // Randomly shuffle (in-place)
array_rand($arr);                    // Random key
array_rand($arr, 3);                 // Array of 3 random keys

// COMPACT & EXTRACT:
$name = "Aryan"; $age = 17;
$data = compact("name", "age");      // ["name"=>"Aryan","age"=>17]
extract($data);                      // Creates $name and $age variables

// WALKING:
array_walk($arr, function(&$value, $key) {
    $value = strtoupper($value);     // Modify in place
});
array_walk_recursive($nested, fn(&$v) => $v = trim($v));
```

---

### Concept 5: Control Flow

```php
<?php

// ── IF / ELSEIF / ELSE ───────────────────────────────────────────────────
$score = 87;

if ($score >= 90) {
    echo "A";
} elseif ($score >= 80) {     // Note: elseif (not else if) — both work
    echo "B";
} elseif ($score >= 70) {
    echo "C";
} else {
    echo "F";
}

// Ternary operator:
$grade = $score >= 50 ? "Pass" : "Fail";

// Null coalescing (PHP 7+):
$username = $_GET["user"] ?? "Guest";          // Use "Guest" if null/undefined
$display  = $user["name"] ?? $user["email"] ?? "Unknown"; // Chain

// Null coalescing assignment (PHP 7.4+):
$config["debug"] ??= false;   // Assign only if null or not set

// Elvis operator (short ternary):
$name = $user["name"] ?: "Anonymous";  // Use right if left is falsy

// Match expression (PHP 8.0+) — strict comparison, no fallthrough:
$status = 2;
$label = match($status) {
    1       => "Active",
    2, 3    => "Pending",   // Multiple values per arm!
    4       => "Inactive",
    default => "Unknown",
};

// Match with no-match exception:
try {
    $result = match($status) { 1 => "one", 2 => "two" };
} catch (\UnhandledMatchError $e) {
    echo "No match found";
}

// ── SWITCH ────────────────────────────────────────────────────────────────
switch ($score) {
    case 100:
        echo "Perfect!";
        break;
    case 90:
    case 91:
        echo "Excellent";
        break;
    default:
        echo "Other";
}

// ── FOR LOOPS ─────────────────────────────────────────────────────────────
for ($i = 0; $i < 5; $i++) {
    echo $i;
}

// ── WHILE ─────────────────────────────────────────────────────────────────
$n = 1;
while ($n <= 10) {
    echo $n;
    $n++;
}

// ── DO-WHILE (runs at least once) ─────────────────────────────────────────
$count = 0;
do {
    $count++;
} while ($count < 5);

// ── FOREACH — the most used loop in PHP ───────────────────────────────────
$fruits = ["apple", "banana", "cherry"];
foreach ($fruits as $fruit) {
    echo $fruit;
}

foreach ($fruits as $index => $fruit) {
    echo "$index: $fruit\n";
}

// Modify by reference:
foreach ($fruits as &$fruit) {
    $fruit = strtoupper($fruit);
}
unset($fruit); // CRITICAL: unset reference after foreach!

// Nested:
$matrix = [[1,2,3], [4,5,6], [7,8,9]];
foreach ($matrix as $row) {
    foreach ($row as $cell) {
        echo "$cell ";
    }
}

// ── LOOP CONTROL ──────────────────────────────────────────────────────────
for ($i = 0; $i < 10; $i++) {
    if ($i === 3) continue;  // Skip iteration
    if ($i === 7) break;     // Exit loop
    echo $i;
}

// Break/continue with numeric argument (break N levels):
for ($i = 0; $i < 3; $i++) {
    for ($j = 0; $j < 3; $j++) {
        if ($j === 1) break 2;  // Break BOTH loops!
        echo "$i,$j ";
    }
}

// ── INCLUDE / REQUIRE ─────────────────────────────────────────────────────
include 'header.php';          // Include (warning if not found)
include_once 'config.php';     // Include only once
require 'database.php';        // Include (fatal error if not found)
require_once 'functions.php';  // Require only once — use this most often!
```

---

🧪 **Mini Task 1:**
> Write a function `isPalindrome(string $s): bool` that returns true if the string reads the same forwards and backwards (ignore case and non-alphanumeric characters). Test: `isPalindrome("A man a plan a canal Panama")` → `true`.
> ✅ *Use: `preg_replace`, `strtolower`, `strrev`*

🧪 **Mini Task 2:**
> Write a function `groupBy(array $items, string $key): array` that groups an array of associative arrays by a specified key. Test: group students by their department.

---

## ⚙️ 4. Complete Language System Breakdown

> 🎯 *Goal: Understand ALL of PHP's machinery — nothing hidden.*

---

### Part 1: Functions — Every Form and Feature

```php
<?php

// ── BASIC FUNCTION ────────────────────────────────────────────────────────
function greet(string $name): string {
    return "Hello, $name!";
}

// ── TYPE DECLARATIONS (PHP 7+) ────────────────────────────────────────────
function add(int $a, int $b): int {
    return $a + $b;
}

// Nullable types:
function findUser(?int $id): ?string {  // ? means can be null
    if ($id === null) return null;
    return "User $id";
}

// Union types (PHP 8.0+):
function process(int|string $input): int|string {
    return $input;
}

// Intersection types (PHP 8.1+):
function save(Countable&Iterator $collection): void { }

// Return type void:
function logMessage(string $msg): void {
    echo $msg;
    // No return allowed (or bare return)
}

// never return type (PHP 8.1+) — function always throws or exits:
function abort(int $code): never {
    http_response_code($code);
    exit;
}

// ── DEFAULT PARAMETERS ────────────────────────────────────────────────────
function power(float $base, int $exp = 2): float {
    return $base ** $exp;
}
echo power(3);    // 9.0
echo power(3, 3); // 27.0

// Default must be expressions, not variables:
const DEFAULT_LIMIT = 10;
function query(int $limit = DEFAULT_LIMIT): array { return []; }

// ── VARIADIC FUNCTIONS ────────────────────────────────────────────────────
function sumAll(int ...$numbers): int {
    return array_sum($numbers);
}
echo sumAll(1, 2, 3, 4, 5);  // 15

// Spread operator — unpack array into arguments:
$nums = [1, 2, 3];
echo sumAll(...$nums);         // 6

// Named arguments (PHP 8.0+) — GAME CHANGER:
function createUser(string $name, int $age = 18, string $role = "user"): array {
    return compact("name", "age", "role");
}
createUser(name: "Aryan", role: "admin", age: 17); // Any order!
// No need to remember parameter order — use names!

// ── RETURNING MULTIPLE VALUES ─────────────────────────────────────────────
function divmod(int $a, int $b): array {
    return [intdiv($a, $b), $a % $b];
}
[$quotient, $remainder] = divmod(17, 5);  // Destructuring!
echo "$quotient remainder $remainder";   // "3 remainder 2"

// ── REFERENCES ────────────────────────────────────────────────────────────
function increment(int &$value): void {
    $value++;   // Modifies the original variable!
}
$x = 5;
increment($x);
echo $x;   // 6

// ── ANONYMOUS FUNCTIONS (Closures) ───────────────────────────────────────
$multiply = function(int $x, int $y): int {
    return $x * $y;
};
echo $multiply(3, 4);  // 12

// Closures capture variables with use:
$factor = 10;
$multiplyByFactor = function(int $x) use ($factor): int {
    return $x * $factor;
};
echo $multiplyByFactor(5); // 50

// Capture by reference:
$counter = 0;
$increment = function() use (&$counter): void {
    $counter++;
};
$increment(); $increment();
echo $counter; // 2

// ── ARROW FUNCTIONS (PHP 7.4+) — short closures ──────────────────────────
// Automatically capture outer variables (NO 'use' keyword needed!):
$multiplier = 3;
$triple = fn(int $x) => $x * $multiplier; // $multiplier auto-captured!
echo $triple(5);  // 15

// Arrow functions in array operations:
$numbers = [1, 2, 3, 4, 5];
$squared  = array_map(fn($n) => $n ** 2, $numbers);         // [1,4,9,16,25]
$evens    = array_filter($numbers, fn($n) => $n % 2 === 0); // [2,4]
$sum      = array_reduce($numbers, fn($carry, $n) => $carry + $n, 0); // 15

// ── FIRST-CLASS CALLABLES (PHP 8.1+) ─────────────────────────────────────
function double(int $n): int { return $n * 2; }

$fn = double(...);           // Create callable from named function
$fn = strlen(...);           // From built-in function
$fn = $obj->method(...);     // From method
$fn = ClassName::static(...);// From static method

$result = array_map(strtoupper(...), ["hello", "world"]); // ["HELLO","WORLD"]
```

---

### Part 2: Object-Oriented Programming — Complete System

```php
<?php
declare(strict_types=1);

// ── CLASS BASICS ─────────────────────────────────────────────────────────
class BankAccount {
    // Properties with types (PHP 7.4+):
    private int $id;
    private string $owner;
    private float $balance;
    protected array $transactions = [];
    public static int $totalAccounts = 0;

    // Class constants:
    const OVERDRAFT_LIMIT = -500.00;
    const VERSION = "2.0";

    // Constructor:
    public function __construct(
        private readonly int $accountNumber,  // Promoted property (PHP 8.0+) + readonly
        string $owner,
        float $initialBalance = 0.0
    ) {
        $this->id = ++self::$totalAccounts;
        $this->owner = $owner;
        $this->balance = $initialBalance;
    }

    // Getters:
    public function getBalance(): float { return $this->balance; }
    public function getOwner(): string  { return $this->owner; }

    // Business logic:
    public function deposit(float $amount): self {
        if ($amount <= 0) {
            throw new \InvalidArgumentException("Deposit amount must be positive");
        }
        $this->balance += $amount;
        $this->transactions[] = ["type" => "deposit", "amount" => $amount, "balance" => $this->balance];
        return $this;  // Fluent interface — method chaining!
    }

    public function withdraw(float $amount): self {
        if ($amount <= 0) {
            throw new \InvalidArgumentException("Withdrawal amount must be positive");
        }
        if ($this->balance - $amount < self::OVERDRAFT_LIMIT) {
            throw new \RuntimeException("Overdraft limit exceeded");
        }
        $this->balance -= $amount;
        $this->transactions[] = ["type" => "withdrawal", "amount" => $amount, "balance" => $this->balance];
        return $this;
    }

    // Static factory method:
    public static function create(string $owner, float $balance = 0.0): self {
        return new self(rand(100000, 999999), $owner, $balance);
    }

    // Magic methods:
    public function __toString(): string {
        return "BankAccount({$this->owner}: ₹{$this->balance})";
    }

    public function __clone() {
        // Reset transactions when cloning:
        $this->transactions = [];
    }

    public function __debugInfo(): array {
        return ["owner" => $this->owner, "balance" => $this->balance];
    }
}

// Fluent interface / method chaining:
$account = BankAccount::create("Aryan", 1000.0);
$account->deposit(500.0)
        ->deposit(200.0)
        ->withdraw(100.0);
echo $account; // "BankAccount(Aryan: ₹1600)"

// ── INHERITANCE ───────────────────────────────────────────────────────────
class SavingsAccount extends BankAccount {
    private float $interestRate;

    public function __construct(
        int $accountNumber,
        string $owner,
        float $balance,
        float $interestRate = 0.05  // 5% annual
    ) {
        parent::__construct($accountNumber, $owner, $balance);
        $this->interestRate = $interestRate;
    }

    public function applyInterest(): self {
        $interest = $this->getBalance() * $this->interestRate;
        $this->deposit($interest);
        return $this;
    }

    // Override parent method:
    public function withdraw(float $amount): self {
        // Savings accounts: minimum balance of ₹500
        if ($this->getBalance() - $amount < 500) {
            throw new \RuntimeException("Savings account minimum balance is ₹500");
        }
        return parent::withdraw($amount);
    }
}

// ── ABSTRACT CLASSES ──────────────────────────────────────────────────────
abstract class Shape {
    abstract public function area(): float;
    abstract public function perimeter(): float;

    // Concrete method in abstract class:
    public function describe(): string {
        return sprintf(
            "%s: area=%.2f, perimeter=%.2f",
            get_class($this),
            $this->area(),
            $this->perimeter()
        );
    }
}

class Circle extends Shape {
    public function __construct(private float $radius) {}

    public function area(): float      { return M_PI * $this->radius ** 2; }
    public function perimeter(): float { return 2 * M_PI * $this->radius; }
}

class Rectangle extends Shape {
    public function __construct(
        private float $width,
        private float $height
    ) {}

    public function area(): float      { return $this->width * $this->height; }
    public function perimeter(): float { return 2 * ($this->width + $this->height); }
}

// ── INTERFACES ────────────────────────────────────────────────────────────
interface Serializable {
    public function serialize(): string;
    public static function deserialize(string $data): static;
}

interface Cacheable {
    public function getCacheKey(): string;
    public function getTTL(): int;
}

// Implement multiple interfaces:
class User implements Serializable, Cacheable {
    public function __construct(
        private int $id,
        private string $name,
        private string $email
    ) {}

    public function serialize(): string {
        return json_encode(["id" => $this->id, "name" => $this->name, "email" => $this->email]);
    }

    public static function deserialize(string $data): static {
        $d = json_decode($data, true);
        return new static($d["id"], $d["name"], $d["email"]);
    }

    public function getCacheKey(): string { return "user:{$this->id}"; }
    public function getTTL(): int { return 3600; }
}

// ── TRAITS — horizontal code reuse ────────────────────────────────────────
trait Timestamps {
    private ?\DateTimeImmutable $createdAt = null;
    private ?\DateTimeImmutable $updatedAt = null;

    public function touch(): void {
        $now = new \DateTimeImmutable();
        $this->createdAt ??= $now;
        $this->updatedAt = $now;
    }

    public function getCreatedAt(): ?\DateTimeImmutable { return $this->createdAt; }
    public function getUpdatedAt(): ?\DateTimeImmutable { return $this->updatedAt; }
}

trait SoftDelete {
    private bool $deleted = false;
    private ?\DateTimeImmutable $deletedAt = null;

    public function delete(): void {
        $this->deleted = true;
        $this->deletedAt = new \DateTimeImmutable();
    }

    public function restore(): void {
        $this->deleted = false;
        $this->deletedAt = null;
    }

    public function isDeleted(): bool { return $this->deleted; }
}

class Post {
    use Timestamps, SoftDelete;   // Use multiple traits!

    public function __construct(
        private string $title,
        private string $content
    ) {
        $this->touch();
    }
}

$post = new Post("My First Post", "Content here...");
$post->delete();
echo $post->isDeleted() ? "Deleted" : "Active"; // "Deleted"

// ── ENUMS (PHP 8.1+) — the game changer ──────────────────────────────────
// Pure enum:
enum Status {
    case Active;
    case Inactive;
    case Pending;
}

// Backed enum (has a scalar value):
enum Color: string {
    case Red   = 'red';
    case Green = 'green';
    case Blue  = 'blue';

    // Methods on enums!
    public function label(): string {
        return match($this) {
            Color::Red   => '🔴 Red',
            Color::Green => '🟢 Green',
            Color::Blue  => '🔵 Blue',
        };
    }

    public function rgb(): array {
        return match($this) {
            Color::Red   => [255, 0, 0],
            Color::Green => [0, 255, 0],
            Color::Blue  => [0, 0, 255],
        };
    }
}

$color = Color::Red;
echo $color->value;   // "red"
echo $color->name;    // "Red"
echo $color->label(); // "🔴 Red"

// From value:
$green = Color::from("green");    // Color::Green
$maybe = Color::tryFrom("purple"); // null (no exception)

// Enums in match:
$msg = match($color) {
    Color::Red   => "Stop",
    Color::Green => "Go",
    Color::Blue  => "Cool",
};

// ── READONLY PROPERTIES & CLASSES (PHP 8.1/8.2) ───────────────────────────
class Point {
    public function __construct(
        public readonly float $x,
        public readonly float $y,
        public readonly float $z = 0.0
    ) {}
}

$p = new Point(1.0, 2.0);
// $p->x = 3.0;  // Error! Cannot modify readonly property

// Readonly class (PHP 8.2+):
readonly class Coordinate {
    public function __construct(
        public float $lat,
        public float $lng
    ) {}
}
```

---

### Part 3: Error Handling & Exceptions

```php
<?php

// ── EXCEPTION HIERARCHY ───────────────────────────────────────────────────
// Throwable
//   ├── Error (PHP engine errors)
//   │   ├── TypeError
//   │   ├── ValueError
//   │   ├── ArithmeticError
//   │   │   └── DivisionByZeroError
//   │   ├── ParseError
//   │   └── UnhandledMatchError (PHP 8.0)
//   └── Exception (application exceptions)
//       ├── RuntimeException
//       │   ├── OverflowException
//       │   ├── UnderflowException
//       │   ├── OutOfRangeException
//       │   └── UnexpectedValueException
//       ├── LogicException
//       │   ├── BadFunctionCallException
//       │   ├── BadMethodCallException
//       │   ├── DomainException
//       │   ├── InvalidArgumentException
//       │   └── OutOfBoundsException
//       └── ... your custom exceptions

// ── CUSTOM EXCEPTIONS ─────────────────────────────────────────────────────
class UserNotFoundException extends \RuntimeException {
    public function __construct(
        private int $userId,
        string $message = "",
        int $code = 404,
        ?\Throwable $previous = null
    ) {
        parent::__construct(
            $message ?: "User with ID {$userId} not found",
            $code,
            $previous
        );
    }

    public function getUserId(): int { return $this->userId; }
}

class ValidationException extends \LogicException {
    private array $errors;

    public function __construct(array $errors) {
        $this->errors = $errors;
        parent::__construct("Validation failed: " . implode(", ", $errors));
    }

    public function getErrors(): array { return $this->errors; }
}

// ── TRY/CATCH/FINALLY ─────────────────────────────────────────────────────
function processUser(int $id): array {
    try {
        if ($id <= 0) {
            throw new \InvalidArgumentException("ID must be positive");
        }
        if ($id > 1000) {
            throw new UserNotFoundException($id);
        }
        return ["id" => $id, "name" => "User $id"];

    } catch (UserNotFoundException $e) {
        // Specific exception first:
        echo "User not found: " . $e->getUserId() . "\n";
        return [];

    } catch (\InvalidArgumentException | \RangeException $e) {
        // Multiple types in one catch (PHP 8.0+):
        echo "Input error: " . $e->getMessage() . "\n";
        return [];

    } catch (\Throwable $e) {
        // Catches ANY error or exception (use as last resort):
        echo "Unexpected error: " . $e->getMessage() . "\n";
        throw $e; // Re-throw!

    } finally {
        // ALWAYS runs, even if exception thrown or return called:
        echo "Processing complete for ID: $id\n";
    }
}

// ── ERROR HANDLING ────────────────────────────────────────────────────────
// Set custom error handler:
set_error_handler(function(int $errno, string $errstr, string $file, int $line): bool {
    // Convert PHP errors to exceptions:
    if (!(error_reporting() & $errno)) {
        return false; // Error is suppressed by @ operator
    }
    throw new \ErrorException($errstr, 0, $errno, $file, $line);
});

// Set exception handler (last resort):
set_exception_handler(function(\Throwable $e): void {
    error_log($e->getMessage() . "\n" . $e->getTraceAsString());
    http_response_code(500);
    echo json_encode(["error" => "Internal server error"]);
    exit(1);
});

// Restore handlers:
restore_error_handler();
restore_exception_handler();
```

---

### Part 4: Modern PHP Features (8.0, 8.1, 8.2, 8.3)

```php
<?php
declare(strict_types=1);

// ── PHP 8.0 FEATURES ──────────────────────────────────────────────────────

// Named arguments:
str_pad(string: "hello", length: 10, pad_string: "-", pad_type: STR_PAD_BOTH);

// Nullsafe operator ?->:
$city = $user?->getAddress()?->getCity()?->getName();
// No null checks needed! Returns null if any step is null.

// Match expression:
$label = match(true) {
    $score >= 90 => "A",
    $score >= 80 => "B",
    default      => "F",
};

// Union types and mixed type:
function process(int|float|string $value): int|float {
    return is_string($value) ? strlen($value) : $value;
}
function accepts(mixed $data): void {}  // mixed = any type

// Attributes (annotations):
#[\Attribute(\Attribute::TARGET_CLASS | \Attribute::TARGET_METHOD)]
class Route {
    public function __construct(
        public readonly string $path,
        public readonly string $method = 'GET'
    ) {}
}

#[Route('/users', 'GET')]
#[Route('/api/v1/users', 'GET')]
class UserController {
    #[Route('/users/{id}', 'GET')]
    public function show(int $id): array { return []; }
}

// Read attributes via reflection:
$ref = new \ReflectionClass(UserController::class);
$attrs = $ref->getAttributes(Route::class);
foreach ($attrs as $attr) {
    $route = $attr->newInstance();
    echo "{$route->method} {$route->path}\n";
}

// Constructor promotion:
class Product {
    public function __construct(
        public readonly int $id,
        public readonly string $name,
        public float $price,
        private bool $available = true
    ) {}  // Properties declared AND assigned — no boilerplate!
}

// ── PHP 8.1 FEATURES ──────────────────────────────────────────────────────

// Enums (covered above)
// Readonly properties (covered above)
// Fibers (PHP's coroutines):

$fiber = new \Fiber(function(): string {
    $value = \Fiber::suspend("first");   // Pause and send "first" to caller
    $value2 = \Fiber::suspend("second"); // Pause again
    return "final";
});

$result1 = $fiber->start();       // "first" — runs until first suspend
$result2 = $fiber->resume("A");   // "second" — resumes, "A" is $value
$result3 = $fiber->resume("B");   // null — resumes, fiber ends, "B" is $value2
$return  = $fiber->getReturn();   // "final"

// Intersection types:
function process2(Iterator&Countable $collection): void {}

// never return type:
function redirect(string $url): never {
    header("Location: $url");
    exit;
}

// Array unpacking with string keys (PHP 8.1+):
$defaults = ["color" => "red", "size" => "medium"];
$overrides = ["color" => "blue"];
$merged = [...$defaults, ...$overrides]; // ["color"=>"blue","size"=>"medium"]

// ── PHP 8.2 FEATURES ──────────────────────────────────────────────────────

// Readonly classes:
readonly class Money {
    public function __construct(
        public int $amount,
        public string $currency
    ) {}
}

// Disjunctive Normal Form (DNF) types:
function processData((Iterator&Countable)|array $data): void {}

// Constants in traits:
trait HasVersion {
    const VERSION = "1.0.0";
}

// ── PHP 8.3 FEATURES ──────────────────────────────────────────────────────

// Typed constants in classes:
class Config {
    const string VERSION = "8.3";
    const int TIMEOUT = 30;
}

// #[\Override] attribute:
class ParentClass {
    public function someMethod(): void {}
}
class ChildClass extends ParentClass {
    #[\Override]
    public function someMethod(): void {}  // Compile-time check!
}

// json_validate():
$isValid = json_validate('{"name": "Aryan"}');  // true
$isValid = json_validate('{invalid}');           // false

// array_find() (PHP 8.4):
$result = array_find([1,2,3,4,5], fn($n) => $n > 3); // 4 — first match
```

---

### 📊 Full PHP System Overview Table

| Feature               | PHP Mechanism                              | Key Insight                                           |
|-----------------------|--------------------------------------------|-------------------------------------------------------|
| Type system           | Dynamic with optional strict typing        | `declare(strict_types=1)` enforces at function calls  |
| Execution model       | Shared-nothing (each request = new process)| No shared state between requests (by default)         |
| OOP                   | Classes, interfaces, traits, enums         | Multiple interface impl; traits for horizontal reuse  |
| Error model           | Errors + Exceptions (both extend Throwable)| `set_error_handler` to convert errors → exceptions    |
| Memory management     | Reference counting + cycle collector       | `unset()` on reference loops prevents memory leaks    |
| Sessions              | Server-side files or custom handlers       | `session_start()` — cookies for session ID            |
| Autoloading           | PSR-4 via Composer + spl_autoload_register | One class per file, namespace matches directory       |
| Namespaces            | `namespace Vendor\Package\SubPackage;`     | Avoids naming collisions across libraries             |
| Generators            | `yield` — lazy iteration                   | Memory-efficient sequence generation                  |
| Reflection            | `ReflectionClass`, `ReflectionMethod`      | Inspect and manipulate code at runtime                |

---

## 🔄 5. Real-World Workflow

---

### 🟢 Beginner Workflow: Dynamic Website with MySQL

```php
<?php
// config.php — Database configuration
define('DB_HOST', 'localhost');
define('DB_NAME', 'myapp');
define('DB_USER', 'root');
define('DB_PASS', 'password');

// db.php — PDO connection (ALWAYS use PDO, never mysql_* functions!)
function getDB(): PDO {
    static $pdo = null;
    if ($pdo === null) {
        $dsn = "mysql:host=" . DB_HOST . ";dbname=" . DB_NAME . ";charset=utf8mb4";
        $pdo = new PDO($dsn, DB_USER, DB_PASS, [
            PDO::ATTR_ERRMODE            => PDO::ERRMODE_EXCEPTION,
            PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
            PDO::ATTR_EMULATE_PREPARES   => false,  // IMPORTANT for security!
        ]);
    }
    return $pdo;
}

// users.php — CRUD operations with prepared statements:
function getUsers(int $limit = 10, int $offset = 0): array {
    $sql = "SELECT id, username, email, created_at FROM users 
            ORDER BY created_at DESC LIMIT :limit OFFSET :offset";
    $stmt = getDB()->prepare($sql);
    $stmt->execute([":limit" => $limit, ":offset" => $offset]);
    return $stmt->fetchAll();
}

function getUserById(int $id): ?array {
    $stmt = getDB()->prepare("SELECT * FROM users WHERE id = :id");
    $stmt->execute([":id" => $id]);
    return $stmt->fetch() ?: null;
}

function createUser(string $username, string $email, string $password): int {
    $hash = password_hash($password, PASSWORD_BCRYPT, ["cost" => 12]);
    $stmt = getDB()->prepare(
        "INSERT INTO users (username, email, password_hash, created_at) 
         VALUES (:username, :email, :hash, NOW())"
    );
    $stmt->execute([":username" => $username, ":email" => $email, ":hash" => $hash]);
    return (int)getDB()->lastInsertId();
}

function updateUser(int $id, array $data): bool {
    $allowed = ["username", "email"];  // Whitelist updatable fields
    $fields = array_filter(array_keys($data), fn($k) => in_array($k, $allowed));
    if (empty($fields)) return false;

    $setParts = array_map(fn($f) => "$f = :$f", $fields);
    $sql = "UPDATE users SET " . implode(", ", $setParts) . " WHERE id = :id";

    $params = array_intersect_key($data, array_flip($allowed));
    $params["id"] = $id;

    return getDB()->prepare($sql)->execute($params);
}

function deleteUser(int $id): bool {
    $stmt = getDB()->prepare("DELETE FROM users WHERE id = :id");
    return $stmt->execute([":id" => $id]);
}

// login.php — Session-based authentication:
session_start();
session_regenerate_id(true);  // Prevent session fixation!

function login(string $email, string $password): bool {
    $stmt = getDB()->prepare("SELECT * FROM users WHERE email = :email");
    $stmt->execute([":email" => $email]);
    $user = $stmt->fetch();

    if (!$user || !password_verify($password, $user["password_hash"])) {
        return false;
    }

    // Regenerate session ID on login:
    session_regenerate_id(true);
    $_SESSION["user_id"]   = $user["id"];
    $_SESSION["username"]  = $user["username"];
    $_SESSION["logged_in"] = true;
    return true;
}

function isLoggedIn(): bool {
    return isset($_SESSION["logged_in"]) && $_SESSION["logged_in"] === true;
}

function requireLogin(): void {
    if (!isLoggedIn()) {
        header("Location: /login.php");
        exit;
    }
}

function logout(): void {
    $_SESSION = [];
    if (isset($_COOKIE[session_name()])) {
        setcookie(session_name(), "", time() - 3600, "/");
    }
    session_destroy();
}
```

---

### 🔵 Professional Workflow: Laravel-Style MVC

```php
<?php
// Modern PHP with Composer PSR-4 autoloading
// composer.json: {"require": {"php": "^8.2"}, "autoload": {"psr-4": {"App\\": "src/"}}}

// src/Model/User.php
namespace App\Model;

use App\Database\QueryBuilder;

class User {
    private function __construct(
        public readonly int $id,
        public readonly string $username,
        public readonly string $email,
        public readonly \DateTimeImmutable $createdAt
    ) {}

    public static function fromArray(array $data): self {
        return new self(
            id: (int)$data["id"],
            username: $data["username"],
            email: $data["email"],
            createdAt: new \DateTimeImmutable($data["created_at"])
        );
    }

    public function toArray(): array {
        return [
            "id"         => $this->id,
            "username"   => $this->username,
            "email"      => $this->email,
            "created_at" => $this->createdAt->format("Y-m-d H:i:s"),
        ];
    }
}

// src/Repository/UserRepository.php
namespace App\Repository;

use App\Model\User;
use PDO;

class UserRepository {
    public function __construct(private PDO $db) {}

    public function findAll(int $page = 1, int $perPage = 15): array {
        $offset = ($page - 1) * $perPage;
        $stmt = $this->db->prepare(
            "SELECT * FROM users ORDER BY id DESC LIMIT :limit OFFSET :offset"
        );
        $stmt->execute([":limit" => $perPage, ":offset" => $offset]);
        return array_map(User::fromArray(...), $stmt->fetchAll());
    }

    public function findById(int $id): ?User {
        $stmt = $this->db->prepare("SELECT * FROM users WHERE id = :id");
        $stmt->execute([":id" => $id]);
        $data = $stmt->fetch();
        return $data ? User::fromArray($data) : null;
    }

    public function findByEmail(string $email): ?User {
        $stmt = $this->db->prepare("SELECT * FROM users WHERE email = :email");
        $stmt->execute([":email" => $email]);
        $data = $stmt->fetch();
        return $data ? User::fromArray($data) : null;
    }

    public function save(array $data): User {
        $stmt = $this->db->prepare(
            "INSERT INTO users (username, email, password_hash, created_at)
             VALUES (:username, :email, :hash, NOW())"
        );
        $stmt->execute([
            ":username" => $data["username"],
            ":email"    => $data["email"],
            ":hash"     => password_hash($data["password"], PASSWORD_BCRYPT, ["cost" => 12]),
        ]);
        return $this->findById((int)$this->db->lastInsertId());
    }
}

// src/Controller/UserController.php
namespace App\Controller;

use App\Repository\UserRepository;
use App\Validation\UserValidator;

class UserController {
    public function __construct(
        private UserRepository $users,
        private UserValidator $validator
    ) {}

    public function index(): array {
        $page = max(1, (int)($_GET["page"] ?? 1));
        $users = $this->users->findAll($page);
        return array_map(fn($u) => $u->toArray(), $users);
    }

    public function show(int $id): array {
        $user = $this->users->findById($id);
        if (!$user) {
            http_response_code(404);
            return ["error" => "User not found"];
        }
        return $user->toArray();
    }

    public function store(array $data): array {
        $errors = $this->validator->validate($data);
        if (!empty($errors)) {
            http_response_code(422);
            return ["errors" => $errors];
        }

        if ($this->users->findByEmail($data["email"])) {
            http_response_code(409);
            return ["error" => "Email already registered"];
        }

        $user = $this->users->save($data);
        http_response_code(201);
        return $user->toArray();
    }
}
```

---

## 🧪 6. Hands-on Practice Projects

---

### 🟢 Beginner Project: Contact Form with Validation & Email

```php
<?php
// contact.php — Secure contact form processor
declare(strict_types=1);

function validateContactForm(array $data): array {
    $errors = [];

    // Name:
    $name = trim($data["name"] ?? "");
    if (empty($name)) {
        $errors["name"] = "Name is required";
    } elseif (strlen($name) < 2 || strlen($name) > 100) {
        $errors["name"] = "Name must be 2-100 characters";
    }

    // Email:
    $email = trim($data["email"] ?? "");
    if (empty($email)) {
        $errors["email"] = "Email is required";
    } elseif (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
        $errors["email"] = "Invalid email address";
    }

    // Subject:
    $subject = trim($data["subject"] ?? "");
    if (empty($subject)) {
        $errors["subject"] = "Subject is required";
    } elseif (strlen($subject) > 200) {
        $errors["subject"] = "Subject too long (max 200 chars)";
    }

    // Message:
    $message = trim($data["message"] ?? "");
    if (empty($message)) {
        $errors["message"] = "Message is required";
    } elseif (strlen($message) < 10) {
        $errors["message"] = "Message too short (min 10 chars)";
    } elseif (strlen($message) > 5000) {
        $errors["message"] = "Message too long (max 5000 chars)";
    }

    return $errors;
}

function sanitizeInput(string $input): string {
    return htmlspecialchars(strip_tags(trim($input)), ENT_QUOTES, "UTF-8");
}

function rateLimitCheck(string $ip): bool {
    $key = "contact_" . md5($ip);
    $attempts = apcu_fetch($key) ?: 0;  // APCu cache
    if ($attempts >= 5) {
        return false;  // Too many attempts
    }
    apcu_store($key, $attempts + 1, 3600); // Reset after 1 hour
    return true;
}

// CSRF protection:
session_start();
if (empty($_SESSION["csrf_token"])) {
    $_SESSION["csrf_token"] = bin2hex(random_bytes(32));
}

if ($_SERVER["REQUEST_METHOD"] === "POST") {
    // CSRF check:
    if (!hash_equals($_SESSION["csrf_token"], $_POST["csrf_token"] ?? "")) {
        http_response_code(403);
        die("Invalid CSRF token");
    }

    // Rate limiting:
    if (!rateLimitCheck($_SERVER["REMOTE_ADDR"])) {
        http_response_code(429);
        die("Too many requests. Please try again later.");
    }

    $errors = validateContactForm($_POST);

    if (empty($errors)) {
        $name    = sanitizeInput($_POST["name"]);
        $email   = sanitizeInput($_POST["email"]);
        $subject = sanitizeInput($_POST["subject"]);
        $message = sanitizeInput($_POST["message"]);

        // Send email using mail() or PHPMailer:
        $headers = [
            "From"         => "noreply@example.com",
            "Reply-To"     => $email,
            "Content-Type" => "text/html; charset=UTF-8",
            "MIME-Version" => "1.0",
            "X-Mailer"     => "PHP/" . PHP_VERSION,
        ];

        $body = "
            <h2>New Contact Form Submission</h2>
            <p><strong>From:</strong> {$name} ({$email})</p>
            <p><strong>Subject:</strong> {$subject}</p>
            <p><strong>Message:</strong></p>
            <p>{$message}</p>
        ";

        $sent = mail(
            "admin@example.com",
            "Contact Form: " . $subject,
            $body,
            implode("\r\n", array_map(fn($k, $v) => "$k: $v", array_keys($headers), $headers))
        );

        if ($sent) {
            header("Location: /contact?success=1");
            exit;
        }
    }
}
?>
<!DOCTYPE html>
<html lang="en">
<head><meta charset="UTF-8"><title>Contact</title></head>
<body>
    <?php if (!empty($errors)): ?>
        <div class="errors">
            <?php foreach ($errors as $field => $error): ?>
                <p><?= htmlspecialchars($field) ?>: <?= htmlspecialchars($error) ?></p>
            <?php endforeach; ?>
        </div>
    <?php endif; ?>

    <form method="POST" action="/contact.php">
        <input type="hidden" name="csrf_token" value="<?= $_SESSION["csrf_token"] ?>">
        <input type="text" name="name" value="<?= htmlspecialchars($_POST["name"] ?? "") ?>">
        <input type="email" name="email" value="<?= htmlspecialchars($_POST["email"] ?? "") ?>">
        <input type="text" name="subject" value="<?= htmlspecialchars($_POST["subject"] ?? "") ?>">
        <textarea name="message"><?= htmlspecialchars($_POST["message"] ?? "") ?></textarea>
        <button type="submit">Send Message</button>
    </form>
</body>
</html>
```

---

### 🔵 Intermediate Project: REST API with JWT Authentication

```php
<?php
// api/index.php — REST API with JWT auth
declare(strict_types=1);

// Simple JWT implementation:
class JWT {
    public static function encode(array $payload, string $secret): string {
        $header  = self::base64url(json_encode(["alg" => "HS256", "typ" => "JWT"]));
        $payload = self::base64url(json_encode($payload));
        $sig     = self::base64url(hash_hmac("sha256", "$header.$payload", $secret, true));
        return "$header.$payload.$sig";
    }

    public static function decode(string $token, string $secret): array {
        $parts = explode(".", $token);
        if (count($parts) !== 3) throw new \InvalidArgumentException("Invalid token");

        [$header, $payload, $sig] = $parts;
        $expected = self::base64url(hash_hmac("sha256", "$header.$payload", $secret, true));

        if (!hash_equals($expected, $sig)) {
            throw new \RuntimeException("Invalid signature");
        }

        $data = json_decode(base64_decode(strtr($payload, "-_", "+/")), true);
        if (isset($data["exp"]) && $data["exp"] < time()) {
            throw new \RuntimeException("Token expired");
        }
        return $data;
    }

    private static function base64url(string $data): string {
        return rtrim(strtr(base64_encode($data), "+/", "-_"), "=");
    }
}

// Router:
class Router {
    private array $routes = [];

    public function add(string $method, string $pattern, callable $handler): void {
        $regex = preg_replace("/\{(\w+)\}/", "(?P<$1>[^/]+)", $pattern);
        $this->routes[] = compact("method", "pattern", "regex", "handler");
    }

    public function dispatch(string $method, string $path): void {
        foreach ($this->routes as $route) {
            if ($route["method"] !== $method) continue;
            if (!preg_match("#^{$route["regex"]}$#", $path, $matches)) continue;

            $params = array_filter($matches, "is_string", ARRAY_FILTER_USE_KEY);
            header("Content-Type: application/json");
            $result = ($route["handler"])($params);
            echo json_encode($result);
            return;
        }

        http_response_code(404);
        echo json_encode(["error" => "Route not found"]);
    }
}

// Middleware:
function requireAuth(): array {
    $auth = $_SERVER["HTTP_AUTHORIZATION"] ?? "";
    if (!preg_match("/^Bearer (.+)$/", $auth, $matches)) {
        http_response_code(401);
        echo json_encode(["error" => "Missing authorization token"]);
        exit;
    }
    try {
        return JWT::decode($matches[1], $_ENV["JWT_SECRET"] ?? "secret");
    } catch (\Throwable $e) {
        http_response_code(401);
        echo json_encode(["error" => $e->getMessage()]);
        exit;
    }
}

// Bootstrap router:
$router = new Router();

$router->add("GET", "/api/users", function(): array {
    requireAuth();
    $stmt = getDB()->query("SELECT id, username, email FROM users LIMIT 20");
    return $stmt->fetchAll();
});

$router->add("GET", "/api/users/{id}", function(array $params): array {
    requireAuth();
    $stmt = getDB()->prepare("SELECT id, username, email FROM users WHERE id = :id");
    $stmt->execute([":id" => (int)$params["id"]]);
    $user = $stmt->fetch();
    if (!$user) { http_response_code(404); return ["error" => "User not found"]; }
    return $user;
});

$router->add("POST", "/api/auth/login", function(): array {
    $body = json_decode(file_get_contents("php://input"), true);
    // Validate credentials, then:
    $token = JWT::encode([
        "sub" => 1,
        "email" => $body["email"],
        "iat" => time(),
        "exp" => time() + 3600,
    ], $_ENV["JWT_SECRET"] ?? "secret");
    return ["token" => $token, "expires_in" => 3600];
});

$method = $_SERVER["REQUEST_METHOD"];
$path   = parse_url($_SERVER["REQUEST_URI"], PHP_URL_PATH);
$router->dispatch($method, $path);
```

---

### 🔴 Advanced Project: Async Processing with Queue Worker

```php
<?php
// queue/Worker.php — Background job processing
declare(strict_types=1);

namespace App\Queue;

interface Job {
    public function handle(): void;
    public function onFailure(\Throwable $e): void;
    public function getMaxAttempts(): int;
}

class EmailJob implements Job {
    public function __construct(
        private string $to,
        private string $subject,
        private string $body
    ) {}

    public function handle(): void {
        // Send email via PHPMailer/Symfony Mailer:
        echo "Sending email to {$this->to}\n";
        // ... actual email sending logic
    }

    public function onFailure(\Throwable $e): void {
        error_log("EmailJob failed: " . $e->getMessage());
    }

    public function getMaxAttempts(): int { return 3; }
}

class RedisQueue {
    private \Redis $redis;

    public function __construct(string $host = "127.0.0.1", int $port = 6379) {
        $this->redis = new \Redis();
        $this->redis->connect($host, $port);
    }

    public function push(string $queue, Job $job): void {
        $payload = serialize($job);
        $this->redis->lpush($queue, $payload);
    }

    public function pop(string $queue, int $timeout = 5): ?Job {
        $result = $this->redis->brpop($queue, $timeout);
        if (!$result) return null;
        return unserialize($result[1]);
    }
}

class Worker {
    public function __construct(
        private RedisQueue $queue,
        private string $queueName = "default"
    ) {}

    public function run(): void {
        echo "Worker started on queue: {$this->queueName}\n";
        pcntl_async_signals(true);
        pcntl_signal(SIGTERM, function() { exit(0); });
        pcntl_signal(SIGINT, function() { exit(0); });

        while (true) {
            $job = $this->queue->pop($this->queueName);
            if (!$job) continue;

            $this->process($job);
        }
    }

    private function process(Job $job, int $attempt = 1): void {
        try {
            $job->handle();
        } catch (\Throwable $e) {
            $job->onFailure($e);
            if ($attempt < $job->getMaxAttempts()) {
                sleep(2 ** $attempt);  // Exponential backoff
                $this->process($job, $attempt + 1);
            } else {
                error_log("Job permanently failed after {$attempt} attempts");
            }
        }
    }
}

// Usage:
$queue = new RedisQueue();
$queue->push("emails", new EmailJob("aryan@example.com", "Welcome!", "Hello!"));

// Worker runs in separate process:
// php worker.php
$worker = new Worker($queue, "emails");
$worker->run();
```

---

## ⚠️ 7. Common Mistakes

---

### ❌ Mistake 1: SQL Injection — Using String Concatenation

```php
// ❌ NEVER DO THIS — SQL injection vulnerability:
$id = $_GET["id"];
$query = "SELECT * FROM users WHERE id = $id";
// If id = "1 OR 1=1", returns ALL users!
// If id = "1; DROP TABLE users; --", destroys your database!
$result = mysqli_query($conn, $query);

// ✅ ALWAYS use prepared statements with PDO:
$stmt = $pdo->prepare("SELECT * FROM users WHERE id = :id");
$stmt->execute([":id" => (int)$_GET["id"]]);
$user = $stmt->fetch();
```

---

### ❌ Mistake 2: XSS — Outputting Unescaped User Data

```php
// ❌ WRONG — Cross-Site Scripting vulnerability:
echo "Hello, " . $_GET["name"];
// If name = "<script>steal(document.cookie)</script>", JS executes!

// ✅ ALWAYS escape output:
echo "Hello, " . htmlspecialchars($_GET["name"] ?? "", ENT_QUOTES, "UTF-8");

// ✅ Create a helper:
function e(string $s): string {
    return htmlspecialchars($s, ENT_QUOTES | ENT_SUBSTITUTE, "UTF-8");
}
echo "Hello, " . e($_GET["name"] ?? "");
```

---

### ❌ Mistake 3: Storing Passwords Insecurely

```php
// ❌ NEVER store plain text or MD5/SHA1 passwords:
$hash = md5($password);        // Crackable in seconds
$hash = sha1($password);       // Also crackable
$hash = md5(md5($password));   // Still terrible

// ✅ ALWAYS use password_hash():
$hash = password_hash($password, PASSWORD_BCRYPT, ["cost" => 12]);
// Or: PASSWORD_ARGON2ID (stronger, recommended for new projects)
$hash = password_hash($password, PASSWORD_ARGON2ID);

// ✅ ALWAYS verify with password_verify():
if (password_verify($inputPassword, $storedHash)) {
    // Login successful
}

// ✅ Rehash if algorithm changes:
if (password_needs_rehash($hash, PASSWORD_ARGON2ID)) {
    $hash = password_hash($password, PASSWORD_ARGON2ID);
    // Update hash in database
}
```

---

### ❌ Mistake 4: Using `==` Instead of `===`

```php
// ❌ PHP's loose comparison causes SHOCKING bugs:
var_dump(0 == "foo");     // true! (PHP 7) / false (PHP 8 — fixed!)
var_dump(0 == "");        // true!
var_dump("1" == "01");    // true!
var_dump(100 == "1e2");   // true!
var_dump(null == false);  // true!
var_dump("" == false);    // true!
var_dump(null == "");     // true!
var_dump("0" == false);   // true!
var_dump("0" == null);    // false!  ← Mind-bending inconsistency!

// ✅ ALWAYS use === (strict comparison):
var_dump(0 === "foo");    // false
var_dump("1" === "01");   // false
var_dump(null === false); // false

// ✅ Especially critical in security checks:
if ($token === $_SESSION["csrf_token"]) { } // NOT ==
if (hash_equals($expected, $actual)) { }   // Timing-safe comparison for hashes
```

---

### ❌ Mistake 5: Not Using `declare(strict_types=1)`

```php
// ❌ Without strict_types — silent type coercion:
function calculateTax(float $amount, int $rate): float {
    return $amount * $rate / 100;
}
calculateTax("broken", "also broken"); // Silently converts to 0.0 and 0!

// ✅ With declare(strict_types=1) at top of file:
declare(strict_types=1);
calculateTax("broken", "also broken"); // Fatal error: must be float!
```

---

### ❌ Mistake 6: Forgetting to `unset()` After `foreach` by Reference

```php
// ❌ Classic PHP gotcha:
$arr = [1, 2, 3];
foreach ($arr as &$value) {
    $value *= 2;
}
// After loop, $value is still a REFERENCE to $arr[2]!

foreach ($arr as $value) {  // Now $value is an alias for $arr[2]
    echo $value;             // Last element gets overwritten each iteration!
}
// $arr = [2, 4, 4]  ← Last element is 4, not 6!

// ✅ ALWAYS unset after foreach by reference:
foreach ($arr as &$value) {
    $value *= 2;
}
unset($value);  // Break the reference!
```

---

### ❌ Mistake 7: Using `@` Error Suppression Operator

```php
// ❌ The @ operator hides errors — including critical ones:
$result = @file_get_contents($url);  // Hides "failed to open stream" — WHY?
$conn   = @mysql_connect(...);       // Hides connection errors

// ✅ Handle errors explicitly:
$result = file_get_contents($url);
if ($result === false) {
    throw new \RuntimeException("Failed to fetch: $url");
}

// Or use try-catch with error_reporting:
try {
    $result = file_get_contents($url);
} catch (\ErrorException $e) {
    // Handle properly
}
```

---

## 🔥 8. Pro Tips & Hidden Tricks

---

### 💎 Tip 1: Generators — Lazy Sequences for Memory Efficiency

```php
<?php

// Without generators — loads EVERYTHING into memory:
function getAllRowsBad(): array {
    $rows = [];
    $stmt = getDB()->query("SELECT * FROM huge_table"); // 10M rows = 10GB RAM!
    while ($row = $stmt->fetch()) {
        $rows[] = $row;
    }
    return $rows;
}

// With generators — processes one row at a time:
function getAllRows(): \Generator {
    $stmt = getDB()->query("SELECT * FROM huge_table");
    while ($row = $stmt->fetch()) {
        yield $row;  // Pauses here, returns one row, resumes next iteration
    }
}

// Usage:
foreach (getAllRows() as $row) {
    processRow($row);  // Never more than ONE row in memory at a time!
}

// Generator with keys:
function indexedValues(): \Generator {
    yield "first"  => 1;
    yield "second" => 2;
    yield "third"  => 3;
}

// Generator send() — two-way communication:
function accumulator(): \Generator {
    $total = 0;
    while (true) {
        $value = yield $total;  // Yield current total, receive next value
        if ($value === null) break;
        $total += $value;
    }
}

$gen = accumulator();
$gen->current();    // Initialize (run to first yield) → 0
$gen->send(10);     // Send 10, get new total → 10
$gen->send(20);     // Send 20, get new total → 30
$gen->send(5);      // → 35

// yield from — delegate to sub-generator:
function inner(): \Generator {
    yield 1;
    yield 2;
    return "inner result";
}

function outer(): \Generator {
    $result = yield from inner();  // $result = "inner result"
    yield 3;
    yield 4;
}

foreach (outer() as $v) echo $v . " "; // 1 2 3 4

// File reading without loading into memory:
function readLargeFile(string $path, int $chunkSize = 4096): \Generator {
    $handle = fopen($path, "rb");
    try {
        while (!feof($handle)) {
            yield fread($handle, $chunkSize);
        }
    } finally {
        fclose($handle);  // Always closes even if generator abandoned!
    }
}
```

---

### 💎 Tip 2: `SPL` — Standard PHP Library Hidden Gems

```php
<?php

// ── SplStack — LIFO stack ─────────────────────────────────────────────────
$stack = new \SplStack();
$stack->push("first");
$stack->push("second");
$stack->push("third");
echo $stack->top();   // "third"
echo $stack->pop();   // "third"

// ── SplQueue — FIFO queue ─────────────────────────────────────────────────
$queue = new \SplQueue();
$queue->enqueue("task1");
$queue->enqueue("task2");
echo $queue->dequeue();  // "task1"

// ── SplMinHeap / SplMaxHeap — priority queues ─────────────────────────────
$heap = new \SplMinHeap();
$heap->insert(5);
$heap->insert(1);
$heap->insert(3);
echo $heap->extract();  // 1 (minimum first)
echo $heap->extract();  // 3
echo $heap->extract();  // 5

// ── SplDoublyLinkedList ───────────────────────────────────────────────────
$list = new \SplDoublyLinkedList();
$list->push("c");
$list->unshift("a");  // Add to beginning
$list->push("d");
foreach ($list as $item) echo "$item "; // a c d

// ── SplFixedArray — faster than regular arrays for numeric indexes ─────────
$arr = new \SplFixedArray(1000);
$arr[0] = "hello";
echo $arr->getSize();  // 1000 — fixed size, more memory efficient

// ── ArrayObject — array-like object ──────────────────────────────────────
$obj = new \ArrayObject(["a" => 1, "b" => 2]);
$obj->append(3);
$obj["c"] = 4;
echo count($obj);  // 4

// ── SplFileInfo — file system operations ─────────────────────────────────
$file = new \SplFileInfo("/path/to/file.txt");
echo $file->getExtension();   // "txt"
echo $file->getBasename();    // "file.txt"
echo $file->getFilename();    // "file"
echo $file->getSize();        // size in bytes
echo $file->isReadable() ? "readable" : "not readable";

// ── RecursiveDirectoryIterator — walk directories ─────────────────────────
$dir = new \RecursiveDirectoryIterator("./src");
$iter = new \RecursiveIteratorIterator($dir, \RecursiveIteratorIterator::SELF_FIRST);
$filter = new \RegexIterator($iter, '/\.php$/');

foreach ($filter as $file) {
    echo $file->getPathname() . "\n";  // All .php files recursively
}

// ── SplObserver / SplSubject — built-in Observer pattern ─────────────────
class EventSystem implements \SplSubject {
    private \SplObjectStorage $observers;
    private string $event;

    public function __construct() {
        $this->observers = new \SplObjectStorage();
    }

    public function attach(\SplObserver $observer): void {
        $this->observers->attach($observer);
    }

    public function detach(\SplObserver $observer): void {
        $this->observers->detach($observer);
    }

    public function notify(): void {
        foreach ($this->observers as $observer) {
            $observer->update($this);
        }
    }

    public function trigger(string $event): void {
        $this->event = $event;
        $this->notify();
    }

    public function getEvent(): string { return $this->event; }
}
```

---

### 💎 Tip 3: `DateTimeImmutable` — Safe Date Handling

```php
<?php

// ✅ ALWAYS use DateTimeImmutable (not DateTime which mutates!):
$now  = new \DateTimeImmutable();
$date = new \DateTimeImmutable("2025-03-29");
$date = new \DateTimeImmutable("2025-03-29 10:30:00", new \DateTimeZone("Asia/Kolkata"));

// Parse any format:
$date = \DateTimeImmutable::createFromFormat("d/m/Y", "29/03/2025");

// Arithmetic (returns NEW object — original unchanged):
$tomorrow  = $now->modify("+1 day");
$nextWeek  = $now->add(new \DateInterval("P1W"));   // P = period, W = weeks
$lastMonth = $now->sub(new \DateInterval("P1M"));   // M = months
$later     = $now->setTime(15, 30, 0);              // Set to 3:30 PM today

// Formatting:
echo $now->format("Y-m-d H:i:s");         // "2025-03-29 10:30:00"
echo $now->format("d F Y");               // "29 March 2025"
echo $now->format("U");                   // Unix timestamp
echo $now->format(\DateTime::ATOM);       // ISO 8601

// Comparison:
$d1 = new \DateTimeImmutable("2025-01-01");
$d2 = new \DateTimeImmutable("2025-12-31");
var_dump($d1 < $d2);   // true
var_dump($d1 == $d2);  // false

// Difference:
$diff = $d1->diff($d2);
echo $diff->days;       // 364
echo $diff->months;     // 11
echo $diff->y;          // 0 (years)
echo ($diff->invert ? "-" : "+");  // Direction of diff

// Timezone conversion:
$utc    = new \DateTimeImmutable("now", new \DateTimeZone("UTC"));
$ist    = $utc->setTimezone(new \DateTimeZone("Asia/Kolkata"));
echo $ist->format("H:i T");  // "XX:XX IST"

// Carbon (popular library — extends DateTimeImmutable):
// composer require nesbot/carbon
// $now = \Carbon\Carbon::now();
// echo $now->diffForHumans(); // "2 days ago"
```

---

### 💎 Tip 4: PHP's `filter_*` Functions — Built-in Validation

```php
<?php

// filter_var — validate and sanitize:
filter_var("test@example.com", FILTER_VALIDATE_EMAIL);  // "test@example.com" or false
filter_var("https://example.com", FILTER_VALIDATE_URL); // URL or false
filter_var("192.168.1.1", FILTER_VALIDATE_IP);          // IP or false
filter_var("192.168.1.1", FILTER_VALIDATE_IP, FILTER_FLAG_IPV4); // IPv4 only
filter_var("42", FILTER_VALIDATE_INT);                  // 42 or false
filter_var("42", FILTER_VALIDATE_INT, ["options" => ["min_range" => 1, "max_range" => 100]]);
filter_var("3.14", FILTER_VALIDATE_FLOAT);
filter_var("1", FILTER_VALIDATE_BOOLEAN);               // true
filter_var("yes", FILTER_VALIDATE_BOOLEAN);             // true
filter_var("false", FILTER_VALIDATE_BOOLEAN);           // false

// Sanitization:
filter_var("<h1>Hello</h1>", FILTER_SANITIZE_SPECIAL_CHARS); // Encode special chars
filter_var("Hello World!", FILTER_SANITIZE_ENCODED);          // URL encode
filter_var("3.14abc", FILTER_SANITIZE_NUMBER_FLOAT, FILTER_FLAG_ALLOW_FRACTION); // "3.14"
filter_var("test@example.com", FILTER_SANITIZE_EMAIL);  // Remove invalid chars

// filter_input — safely read from superglobals:
$id    = filter_input(INPUT_GET, "id", FILTER_VALIDATE_INT);
$email = filter_input(INPUT_POST, "email", FILTER_VALIDATE_EMAIL);
$page  = filter_input(INPUT_GET, "page", FILTER_VALIDATE_INT, [
    "options" => ["min_range" => 1, "max_range" => 1000],
    "flags"   => FILTER_NULL_ON_FAILURE,
]);

// filter_input_array — validate multiple inputs at once:
$rules = [
    "name"  => FILTER_SANITIZE_SPECIAL_CHARS,
    "email" => FILTER_VALIDATE_EMAIL,
    "age"   => ["filter" => FILTER_VALIDATE_INT, "options" => ["min_range" => 1]],
];
$data = filter_input_array(INPUT_POST, $rules);
```

---

### 💎 Tip 5: `Closure::bind` and `Closure::call` — Bind Closures to Objects

```php
<?php

class MyClass {
    private int $secret = 42;
    private string $name = "private";
}

// Access private properties from outside the class:
$getSecret = Closure::bind(function() {
    return $this->secret;
}, new MyClass(), MyClass::class);

echo $getSecret();  // 42

// Bind and call in one step:
$result = Closure::fromCallable(function() {
    return $this->name;
})->call(new MyClass());
echo $result;  // "private"

// Real use: testing private methods without reflection:
$closure = function(int $x) {
    return $this->secret + $x;  // Access private property!
};

$bound = Closure::bind($closure, new MyClass(), MyClass::class);
echo $bound(8);  // 50 (42 + 8)

// Middleware pattern with closures:
function pipe(callable ...$stages): callable {
    return function($payload) use ($stages) {
        return array_reduce(
            $stages,
            fn($carry, $stage) => $stage($carry),
            $payload
        );
    };
}

$process = pipe(
    fn($s) => trim($s),
    fn($s) => strtolower($s),
    fn($s) => str_replace(" ", "-", $s),
);

echo $process("  Hello World  ");  // "hello-world"
```

---

## 🚀 9. Advanced Concepts (Expert Level)

---

### Advanced Concept 1: PHP Fibers — Cooperative Multitasking

```php
<?php
// PHP 8.1+ Fibers — cooperative concurrency (like goroutines without channels)

$fiber1 = new \Fiber(function(): void {
    echo "Fiber 1: started\n";
    $value = \Fiber::suspend("from fiber 1");
    echo "Fiber 1: resumed with '$value'\n";
    \Fiber::suspend("fiber 1 done");
});

$fiber2 = new \Fiber(function(): void {
    echo "Fiber 2: started\n";
    \Fiber::suspend("from fiber 2");
    echo "Fiber 2: resumed\n";
});

// Manual cooperative scheduling:
$v1 = $fiber1->start();       // "Fiber 1: started", $v1 = "from fiber 1"
$v2 = $fiber2->start();       // "Fiber 2: started", $v2 = "from fiber 2"
$v3 = $fiber1->resume("hello"); // "Fiber 1: resumed with 'hello'", $v3 = "fiber 1 done"
$fiber2->resume();             // "Fiber 2: resumed"

// Fibers enable async libraries like ReactPHP, Swoole, and amphp:
// These libraries use an event loop that switches between Fibers on I/O operations

// Simple async-like HTTP fetching with Fibers:
function fetchAsync(string $url): \Fiber {
    return new \Fiber(function() use ($url): string {
        $context = stream_context_create(["http" => ["timeout" => 5]]);
        // In real usage, this would use non-blocking I/O:
        return file_get_contents($url, false, $context);
    });
}

$fibers = [
    fetchAsync("https://api.example.com/users"),
    fetchAsync("https://api.example.com/posts"),
    fetchAsync("https://api.example.com/comments"),
];

// Start all fibers:
foreach ($fibers as $fiber) {
    $fiber->start();
}
```

---

### Advanced Concept 2: Reflection — Metaprogramming

```php
<?php

class UserService {
    #[Inject]
    private UserRepository $repository;

    /**
     * @param int $id User ID
     * @return array User data
     */
    public function getUser(int $id): array {
        return ["id" => $id];
    }

    #[Deprecated("Use getUser() instead")]
    public function fetchUser(int $id): array {
        return $this->getUser($id);
    }
}

// Inspect class via reflection:
$ref = new \ReflectionClass(UserService::class);
echo $ref->getName();        // "UserService"
echo $ref->getFileName();    // Full file path

// Inspect methods:
foreach ($ref->getMethods(\ReflectionMethod::IS_PUBLIC) as $method) {
    echo $method->getName() . "\n";

    // Get attributes:
    foreach ($method->getAttributes() as $attr) {
        echo "  Attribute: " . $attr->getName() . "\n";
    }

    // Get parameters:
    foreach ($method->getParameters() as $param) {
        $type = $param->getType()?->getName() ?? "mixed";
        $name = $param->getName();
        echo "  Param: \$$name: $type";
        if ($param->isOptional()) echo " (optional)";
        echo "\n";
    }
}

// Inspect properties:
foreach ($ref->getProperties() as $prop) {
    $prop->setAccessible(true);  // Access private/protected
    $attrs = $prop->getAttributes();
    foreach ($attrs as $attr) {
        if ($attr->getName() === "Inject") {
            echo "Inject: " . $prop->getName() . "\n";
        }
    }
}

// Build a simple DI container:
class Container {
    private array $bindings = [];
    private array $instances = [];

    public function bind(string $abstract, callable $factory): void {
        $this->bindings[$abstract] = $factory;
    }

    public function make(string $class): object {
        if (isset($this->instances[$class])) {
            return $this->instances[$class];
        }

        $ref = new \ReflectionClass($class);
        $constructor = $ref->getConstructor();

        if (!$constructor) {
            return $ref->newInstance();
        }

        $params = array_map(function(\ReflectionParameter $param) {
            $type = $param->getType();
            if (!$type || $type->isBuiltin()) {
                return $param->getDefaultValue();
            }
            return $this->make($type->getName());
        }, $constructor->getParameters());

        return $ref->newInstanceArgs($params);
    }
}
```

---

### Advanced Concept 3: Custom Stream Wrappers

```php
<?php

// Create a custom stream wrapper — lets you use file functions on custom protocols!
class EncryptedStreamWrapper {
    private $handle;
    private string $key = "my-secret-key-32chars-padded!!!!";
    public $context;

    public static function register(): bool {
        return stream_wrapper_register("encrypted", self::class);
    }

    public function stream_open(string $path, string $mode, int $options, ?string &$opened_path): bool {
        $file = substr($path, strlen("encrypted://"));
        $this->handle = fopen($file, $mode);
        return $this->handle !== false;
    }

    public function stream_read(int $count): string|false {
        $data = fread($this->handle, $count);
        if ($data === false) return false;
        return $this->decrypt($data);
    }

    public function stream_write(string $data): int {
        return fwrite($this->handle, $this->encrypt($data));
    }

    public function stream_eof(): bool {
        return feof($this->handle);
    }

    public function stream_close(): void {
        fclose($this->handle);
    }

    private function encrypt(string $data): string {
        $iv = random_bytes(16);
        return $iv . openssl_encrypt($data, "AES-256-CBC", $this->key, OPENSSL_RAW_DATA, $iv);
    }

    private function decrypt(string $data): string {
        if (strlen($data) < 16) return "";
        $iv = substr($data, 0, 16);
        $cipher = substr($data, 16);
        return openssl_decrypt($cipher, "AES-256-CBC", $this->key, OPENSSL_RAW_DATA, $iv) ?: "";
    }

    public function stream_stat(): array {
        return fstat($this->handle);
    }

    public function url_stat(string $path, int $flags): array {
        return stat(substr($path, strlen("encrypted://")));
    }
}

// Register and use:
EncryptedStreamWrapper::register();

// Now you can use file functions with the "encrypted://" protocol!
file_put_contents("encrypted:///path/to/file.dat", "Secret data");
$content = file_get_contents("encrypted:///path/to/file.dat");
```

---

### ⚡ Performance & Optimization Table

| Technique                            | Impact   | How To                                              |
|--------------------------------------|----------|-----------------------------------------------------|
| OPcache (bytecode cache)             | Very High| `opcache.enable=1` in php.ini — ALWAYS enable      |
| JIT Compilation (PHP 8.0+)           | High     | `opcache.jit=tracing` in php.ini                    |
| Use generators for large data        | Very High| Replace `array_map` with `yield` for big datasets   |
| `SplFixedArray` for numeric arrays   | Medium   | 40% less memory than regular PHP arrays             |
| Connection pooling (PgBouncer/ProxySQL)| High   | Reuse database connections across requests          |
| Redis/Memcached for sessions + cache | Very High| `session.save_handler=redis` in php.ini             |
| PHP-FPM tuning                       | High     | `pm.max_children`, `pm.start_servers` tuning        |
| `str_contains` over `strpos`         | Low      | More readable, slight performance gain              |
| Preloading (PHP 7.4+)               | High     | `opcache.preload=preload.php` for framework classes |
| Avoid `array_*` in tight loops      | Medium   | Cache results outside loops; avoid repeated calls   |

---

## 💀 10. 0.01% Hidden Secrets — Ultra Elite

---

### 🔮 Secret 1: Named Arguments Can Reorder Built-in Functions

```php
<?php

// Named arguments work with ALL PHP functions — including built-ins!
// This is revolutionary for readability:

// Old way — you have to memorize argument order:
$result = array_slice([1,2,3,4,5], 1, 3, true);

// New way — self-documenting:
$result = array_slice(
    array: [1,2,3,4,5],
    offset: 1,
    length: 3,
    preserve_keys: true
);

// str_pad — who remembers which argument is which?
$padded = str_pad(
    string: "42",
    length: 10,
    pad_string: "0",
    pad_type: STR_PAD_LEFT
);
// "0000000042"

// array_multisort with named args:
$data = [3, 1, 4, 1, 5, 9];
array_multisort(array: $data, rest: SORT_ASC);

// Named args + spread for dynamic calling:
function myFunc(int $a, int $b, int $c): int { return $a + $b + $c; }
$args = ["c" => 3, "a" => 1, "b" => 2];
myFunc(...$args); // 6 — order doesn't matter!
```

---

### 🔮 Secret 2: `list()` / `[]` Destructuring — Power Features

```php
<?php

// Basic destructuring:
[$first, $second, $third] = [1, 2, 3];

// Skip elements:
[, , $third] = [1, 2, 3];  // Only $third = 3

// Associative destructuring:
["name" => $name, "age" => $age] = ["name" => "Aryan", "age" => 17];

// Nested destructuring:
[[$a, $b], [$c, $d]] = [[1, 2], [3, 4]];

// Swap variables:
[$a, $b] = [$b, $a];

// In foreach:
$points = [[1, 2], [3, 4], [5, 6]];
foreach ($points as [$x, $y]) {
    echo "($x, $y) ";
}

// Associative in foreach:
$students = [
    ["name" => "Aryan", "gpa" => 9.8],
    ["name" => "Priya", "gpa" => 9.2],
];
foreach ($students as ["name" => $name, "gpa" => $gpa]) {
    echo "$name: $gpa\n";
}

// With reference:
$data = [1, 2, 3];
[&$first] = $data;  // $first is reference to $data[0]
$first = 99;
var_dump($data[0]);  // int(99)

// list() in older syntax (before []):
list($a, $b) = [1, 2];
```

---

### 🔮 Secret 3: `match` Is an Expression, Not a Statement

```php
<?php

// match can be used ANYWHERE an expression is expected:

// In echo:
echo match($status) { "active" => "✅", "inactive" => "❌", default => "?" };

// In return:
function getLabel(string $status): string {
    return match($status) {
        "active"   => "Active",
        "pending"  => "Pending",
        "inactive" => "Inactive",
    };
}

// In array values:
$config = [
    "driver"  => match(PHP_OS_FAMILY) { "Windows" => "sqlsrv", default => "pgsql" },
    "timeout" => match(true) { PHP_SAPI === "cli" => 0, default => 30 },
];

// Chained match:
$message = match(true) {
    $score >= 90 => match(true) {
        $score === 100 => "Perfect!",
        default        => "Excellent!",
    },
    $score >= 70 => "Good",
    default      => "Keep trying",
};

// match throws UnhandledMatchError if no arm matches (unlike switch which falls through):
try {
    $result = match("unknown") {
        "a" => 1,
        "b" => 2,
    };
} catch (\UnhandledMatchError $e) {
    echo "No matching arm!";
}
```

---

### 🔮 Secret 4: `compact()` and `extract()` — Dynamic Variables

```php
<?php

// compact() — create array from variable names:
function buildUserDTO(string $name, int $age, string $email, string $role): array {
    $createdAt = date("Y-m-d H:i:s");
    $isActive  = true;
    return compact("name", "age", "email", "role", "createdAt", "isActive");
    // Returns ["name"=>$name, "age"=>$age, "email"=>$email, ...]
}

// extract() — create variables from array keys:
$config = ["host" => "localhost", "port" => 3306, "name" => "mydb"];
extract($config, EXTR_PREFIX_ALL, "db");
// Creates: $db_host, $db_port, $db_name (prefixed to avoid variable collisions)

// EXTR_SKIP — don't overwrite existing variables:
$host = "production-server";
extract(["host" => "localhost"], EXTR_SKIP);
echo $host;  // "production-server" — protected!

// EXTR_IF_EXISTS — only extract keys that match existing variables:
$allowed = ["name" => "", "age" => 0];  // Template of allowed vars
extract($_POST, EXTR_IF_EXISTS);
// Only $name and $age can be extracted — others ignored!
```

---

### 🔮 Secret 5: Output Buffering — Full Control of Output

```php
<?php

// Start output buffering — capture everything sent to browser:
ob_start();

echo "This goes into the buffer, not the browser";
include "template.php";

$content = ob_get_clean();  // Get buffer contents AND stop buffering

// Now $content has all the output as a string!
echo "Processed: " . strtoupper($content);

// Nested buffers:
ob_start();                  // Level 1
ob_start();                  // Level 2
echo "inner";
$inner = ob_get_clean();     // "inner", back to level 1
echo "outer " . $inner;
$full = ob_get_clean();      // "outer inner", back to no buffer

// ob_start with callback — transform ALL output:
ob_start(function(string $buffer): string {
    return str_replace("PLACEHOLDER", date("Y"), $buffer);
});
echo "Copyright PLACEHOLDER. All rights reserved.";
ob_end_flush();  // "Copyright 2025. All rights reserved."

// Minify HTML output:
ob_start(function(string $html): string {
    $html = preg_replace("/>\s+</", "><", $html);  // Remove whitespace between tags
    $html = preg_replace("/\s{2,}/", " ", $html);  // Collapse multiple spaces
    return trim($html);
});

// PHP output buffering is how template engines, response middleware,
// and content compression work internally!
```

---

### 🔮 Secret 6: `register_shutdown_function` — Code That Always Runs

```php
<?php

// Runs ALWAYS when script ends — even on fatal errors, die(), exit():
register_shutdown_function(function(): void {
    $error = error_get_last();
    if ($error !== null && in_array($error["type"], [E_ERROR, E_PARSE, E_CORE_ERROR])) {
        // Fatal error occurred!
        http_response_code(500);
        echo json_encode(["error" => "Fatal error: " . $error["message"]]);
        error_log("FATAL: " . $error["message"] . " in " . $error["file"] . ":" . $error["line"]);
    }
});

// Multiple shutdown functions can be registered (run in FIFO order):
register_shutdown_function(function(): void {
    // Close database connections:
    // $pdo = null;
    echo "DB connections closed\n";
});

register_shutdown_function(function(): void {
    // Send telemetry:
    echo "Metrics sent\n";
});

// This enables you to:
// 1. Log fatal errors (try/catch can't catch fatal errors!)
// 2. Send performance metrics
// 3. Flush caches
// 4. Send monitoring alerts

// ── tick functions — called every N ticks ────────────────────────────────
declare(ticks=1);

$tickCount = 0;
register_tick_function(function() use (&$tickCount): void {
    $tickCount++;
    // Called every statement — use for profiling or resource monitoring
    if (memory_get_usage() > 50 * 1024 * 1024) {  // 50MB limit
        die("Memory limit reached!");
    }
});
```

---

### 🔮 Secret 7: PHP's Type Juggling Table — The Full Truth

```php
<?php

// The loose comparison table (== operator) — know this to avoid ALL type bugs:
// PHP 8 fixed many of these — but strict_types still doesn't affect ==!

// Comparisons that CHANGED from PHP 7 to PHP 8:
var_dump(0 == "foo");     // PHP 7: true | PHP 8: FALSE (fixed!)
var_dump(0 == "");        // PHP 7: true | PHP 8: FALSE (fixed!)
var_dump(0 == "0");       // PHP 7: true | PHP 8: TRUE (still true!)
var_dump(0 == null);      // PHP 7: true | PHP 8: TRUE (still true!)

// Still dangerous in PHP 8:
var_dump("1" == "01");    // TRUE — numeric strings compared as numbers
var_dump("10" == "1e1");  // TRUE — "1e1" = 10 in scientific notation
var_dump(100 == "1e2");   // TRUE
var_dump("" == null);     // TRUE
var_dump("" == false);    // TRUE
var_dump("0" == false);   // TRUE
var_dump("0" == null);    // FALSE! ← Inconsistency!
var_dump(null == false);  // TRUE

// PHP type comparison for switch:
$x = "0";
switch ($x) {
    case false:  echo "matches false\n";  break;  // MATCHES! "0" == false
    case null:   echo "matches null\n";   break;
    case 0:      echo "matches 0\n";      break;
    default:     echo "no match\n";
}
// USE match() instead — strict comparison!
```

---

### 🔮 Secret 8: `array_map` with `null` — The Zip Trick

```php
<?php

// array_map with null as callback = zip multiple arrays into one!
$names  = ["Alice", "Bob", "Carol"];
$scores = [95, 87, 92];
$grades = ["A", "B", "A"];

$combined = array_map(null, $names, $scores, $grades);
// [["Alice",95,"A"], ["Bob",87,"B"], ["Carol",92,"A"]]

// Use with spread for arbitrary number of arrays:
$arrays = [[1,2,3], [4,5,6], [7,8,9]];
$zipped = array_map(null, ...$arrays);
// [[1,4,7], [2,5,8], [3,6,9]] — matrix transpose!

// The "gotcha": different length arrays get null-padded:
array_map(null, [1,2,3], [4,5]);
// [[1,4], [2,5], [3,null]] — shorter array padded with null

// Practical: combine form field names with values:
$fields = ["name", "email", "age"];
$values = ["Aryan", "a@b.com", "17"];
$form = array_combine($fields, $values);
// ["name"=>"Aryan", "email"=>"a@b.com", "age"=>"17"]
```

---

### 🔮 Secret 9: `WeakReference` and `WeakMap` — Prevent Memory Leaks

```php
<?php

// WeakReference — reference an object without preventing garbage collection:
class HeavyObject {
    public array $data;
    public function __construct() {
        $this->data = array_fill(0, 1000, str_repeat("x", 1000)); // ~1MB
    }
}

$obj = new HeavyObject();
$weak = \WeakReference::create($obj);

$alive = $weak->get();  // Returns the object while it exists
var_dump($alive !== null);  // true

unset($obj);  // Garbage collected!
$dead = $weak->get();
var_dump($dead !== null);  // false — object is gone, WeakReference returns null

// WeakMap (PHP 8.0+) — map keyed by objects that are GC'd automatically:
$map = new \WeakMap();

$key1 = new \stdClass();
$key2 = new \stdClass();

$map[$key1] = "data for key1";
$map[$key2] = "data for key2";

echo count($map);  // 2

unset($key1);  // key1 is garbage collected

echo count($map);  // 1 — entry removed automatically!
echo isset($map[$key2]);  // true

// Use case: caching computed properties without preventing GC:
class PropertyCache {
    private \WeakMap $cache;

    public function __construct() {
        $this->cache = new \WeakMap();
    }

    public function get(object $obj, string $prop, callable $compute): mixed {
        $this->cache[$obj] ??= [];
        return $this->cache[$obj][$prop] ??= $compute();
    }
}
```

---

### 🔮 Secret 10: The `__invoke` Magic Method — Callable Objects

```php
<?php

// __invoke makes an object callable like a function:
class Memoize {
    private array $cache = [];

    public function __construct(private callable $fn) {}

    public function __invoke(mixed ...$args): mixed {
        $key = serialize($args);
        return $this->cache[$key] ??= ($this->fn)(...$args);
    }
}

// Use it like a function:
$expensiveFib = new Memoize(function(int $n): int {
    if ($n <= 1) return $n;
    return $n;  // Simplified
});

echo $expensiveFib(5);   // Cached after first call
echo $expensiveFib(5);   // Returns cached result instantly
echo is_callable($expensiveFib) ? "callable" : "not";  // "callable"

// Middleware stack with invokable classes:
class AuthMiddleware {
    public function __invoke(array $request, callable $next): array {
        if (empty($request["token"])) {
            return ["status" => 401, "body" => "Unauthorized"];
        }
        return $next($request);
    }
}

class LogMiddleware {
    public function __invoke(array $request, callable $next): array {
        error_log("Request: " . json_encode($request));
        $response = $next($request);
        error_log("Response status: " . $response["status"]);
        return $response;
    }
}

// Stack middlewares:
function buildMiddlewareStack(array $middlewares, callable $handler): callable {
    return array_reduce(
        array_reverse($middlewares),
        fn($carry, $middleware) => fn($req) => $middleware($req, $carry),
        $handler
    );
}

$stack = buildMiddlewareStack(
    [new LogMiddleware(), new AuthMiddleware()],
    fn($req) => ["status" => 200, "body" => "Hello!"]
);

$response = $stack(["token" => "valid-token"]);
```

---

### 🔮 Secret 11: `intl` Extension — Internationalization Superpowers

```php
<?php

// NumberFormatter — locale-aware number formatting:
$fmt = new \NumberFormatter("en_IN", \NumberFormatter::CURRENCY);
echo $fmt->formatCurrency(1234567.89, "INR");  // "₹12,34,567.89"

$fmt2 = new \NumberFormatter("de_DE", \NumberFormatter::DECIMAL);
echo $fmt2->format(1234567.89);  // "1.234.567,89"

// Relative time:
$fmt3 = new \IntlRelativeDateTimeFormatter();

// MessageFormatter — pluralization:
$fmt4 = \MessageFormatter::create("en_US",
    "{count, plural, =0{No items} =1{One item} other{# items}}"
);
echo $fmt4->format(["count" => 0]); // "No items"
echo $fmt4->format(["count" => 1]); // "One item"
echo $fmt4->format(["count" => 5]); // "5 items"

// Collator — locale-aware string comparison and sorting:
$collator = new \Collator("hi_IN");  // Hindi locale
$strings = ["आम", "केला", "सेब"];
$collator->sort($strings);

// Transliterator — convert scripts:
$t = \Transliterator::create("Any-Latin; Latin-ASCII");
echo $t->transliterate("Привет");  // "Privet"
echo $t->transliterate("مرحبا");    // "mrhba"

// Locale-aware case conversion:
$s = new \Transliterator("Any-Upper");
echo $s->transliterate("café");  // "CAFÉ"
```

---

## 🗺️ 11. Complete Roadmap

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — FOUNDATION (Week 1-2)
├── Day 1-2:  Syntax, variables, types, operators, type juggling
├── Day 3-4:  Strings (all functions), arrays (all functions), control flow
├── Day 5-6:  Functions, closures, arrow functions, named arguments
└── Day 7:    Project: CLI CRUD app, contact form, word counter

PHASE 2 — OOP & MODERN PHP (Week 3-5)
├── Week 3:  Classes, objects, constructor promotion, readonly, inheritance
├── Week 4:  Interfaces, abstract classes, traits, enums (PHP 8.1)
└── Week 5:  Error handling, type declarations, match, nullsafe operator
    └── Project: OOP bank account system, shape hierarchy

PHASE 3 — WEB DEVELOPMENT (Week 6-8)
├── Week 6:  PDO, prepared statements, SQL, CRUD with MySQL/PostgreSQL
├── Week 7:  Sessions, cookies, authentication, CSRF protection, XSS prevention
└── Week 8:  REST API design, JSON, HTTP, file uploads, email sending
    └── Project: Complete blog with auth, CRUD, REST API

PHASE 4 — ADVANCED PHP (Week 9-12)
├── Week 9:   Composer, PSR standards, autoloading, namespaces
├── Week 10:  Generators, SPL, reflection, attributes
├── Week 11:  Testing (PHPUnit), CI/CD, code quality tools
└── Week 12:  Performance: OPcache, JIT, profiling, caching
    └── Project: Full MVC framework from scratch

PHASE 5 — EXPERT / 0.01% (Month 4-6)
├── Month 4:  Laravel (Eloquent, Blade, Artisan, Queues, Events)
├── Month 5:  Symfony components, DI containers, event dispatchers
└── Month 6:  Fibers, async PHP, RoadRunner, Swoole, FrankenPHP
    └── Project: Production SaaS app or open-source library
```

---

### 🏁 Milestone Checklist

- [ ] I understand PHP's type juggling and always use `===`
- [ ] I use `declare(strict_types=1)` in all production files
- [ ] I can explain the difference between `include`, `require`, `include_once`, `require_once`
- [ ] I NEVER write SQL strings directly — always prepared statements
- [ ] I NEVER store passwords as MD5/SHA1 — always `password_hash()`
- [ ] I understand OOP: classes, traits, interfaces, enums
- [ ] I can write generators for memory-efficient data processing
- [ ] I understand Composer PSR-4 autoloading
- [ ] I use `DateTimeImmutable` instead of `DateTime`
- [ ] I've built a complete REST API with authentication
- [ ] I understand output buffering and can use it for template engines
- [ ] I've profiled PHP code with Xdebug and found a bottleneck
- [ ] I know how to enable and configure OPcache and JIT
- [ ] I've used PHP 8.1+ features: enums, readonly, fibers, intersection types

---

## 🧩 12. Bonus Deep Insights

---

### 🔮 Mental Model: "PHP is a Shared-Nothing Architecture"

Every PHP request starts fresh. No shared memory between requests (by default). All variables, objects, and connections are created and destroyed with each request.

This is fundamentally different from Node.js or Java apps where the server process lives between requests. The shared-nothing model:

**Advantages:**
- Trivially scalable — just add more servers/processes
- A crashed request doesn't affect others
- No inter-request state bugs

**Disadvantages:**
- Database connections re-established each request (use connection pooling!)
- Can't cache data in RAM between requests (use Redis!)
- JIT optimization loses context between requests

Understanding this explains WHY PHP needs Redis, OPcache, and PHP-FPM tuning.

---

### 🤫 Deep Insight 1: PHP's Error Model Is a Historical Accident

PHP has TWO parallel error systems:

1. **PHP Errors** (old system): `E_ERROR`, `E_WARNING`, `E_NOTICE`, `E_DEPRECATED` — triggered by the engine
2. **Exceptions** (OOP system): `throw new Exception()` — thrown by application code

These coexist awkwardly. Fatal errors (`E_ERROR`) CANNOT be caught by try/catch! You need `register_shutdown_function` + `error_get_last()` to catch them.

The modern PHP solution: `set_error_handler()` to convert PHP errors into `ErrorException` objects that CAN be caught. This bridges the two systems.

PHP 8.0 improved this significantly — many things that were E_WARNING now throw proper `TypeError` and `ValueError` exceptions.

---

### 🤫 Deep Insight 2: OPcache Is the Single Most Impactful PHP Performance Optimization

Without OPcache, PHP parses and compiles every `.php` file on every request. With OPcache:

1. File is parsed + compiled to bytecode ONCE
2. Bytecode stored in shared memory
3. All subsequent requests use the cached bytecode
4. 2-10× performance improvement — for free

With PHP 8.0+ JIT on top of OPcache:
- Frequently executed bytecode compiled to native machine code
- Additional 10-30% improvement for CPU-bound code
- Less benefit for I/O-bound code (most web apps)

**Every production PHP deployment must have OPcache enabled.**

---

### 🧠 The Big Picture — PHP in the Modern Ecosystem

```
PHP's evolution:
  PHP 3 (1997):   Simple templating
  PHP 4 (2000):   Object support, huge adoption
  PHP 5 (2004):   Proper OOP, PDO, SPL
  PHP 7 (2015):   2× faster, scalar type hints, return types
  PHP 8.0 (2020): JIT, match, nullsafe, named args, attributes
  PHP 8.1 (2021): Fibers, enums, readonly, intersection types
  PHP 8.2 (2022): Readonly classes, DNF types, true/false types
  PHP 8.3 (2023): Typed class constants, json_validate, array_find
  PHP 8.4 (2024): Property hooks, asymmetric visibility, pipe operator

Modern PHP ecosystem:
  Frameworks:   Laravel, Symfony, Slim, Lumen
  ORM:          Eloquent (Laravel), Doctrine (Symfony)
  Testing:      PHPUnit, Pest, Mockery, Behat
  Quality:      PHPStan, Psalm (static analysis), PHP-CS-Fixer
  Async:        Swoole, ReactPHP, Amp, RoadRunner, FrankenPHP
  Package mgr:  Composer (the gold standard of package management)
  Templating:   Blade, Twig, Plates
  API:          API Platform, Laravel API Resources

Where PHP is going:
  → Async-first with Fibers and event loops
  → FrankenPHP: PHP as a server (no PHP-FPM needed)
  → Property hooks (PHP 8.4): computed properties natively
  → Generics: proposed for future PHP versions
  → Better static analysis with PHPStan level 10
```

---

## 📌 13. Summary (Quick Revision & Cheat Sheet)

---

### Core Concepts (1-line each)

| Concept                  | What It Means                                                              |
|--------------------------|----------------------------------------------------------------------------|
| `declare(strict_types=1)`| Enforce exact types at function boundaries — use in ALL production files  |
| Type juggling            | PHP silently converts types with `==` — always use `===` to avoid bugs    |
| Prepared statements      | The ONLY safe way to use user input in SQL queries                         |
| `password_hash()`        | The ONLY safe way to store passwords — never MD5, SHA1, or plain text     |
| `htmlspecialchars()`     | The ONLY safe way to output user data in HTML — prevents XSS              |
| Shared-nothing           | Every request starts fresh — no shared memory between requests             |
| OPcache                  | Bytecode cache — 2-10× performance boost — always enable in production    |
| PSR standards            | Coding style, autoloading, interfaces standards — follow for pro PHP      |
| Composer                 | PHP's package manager — `composer require vendor/package`                 |
| Generators               | `yield` — lazy iteration — processes millions of rows with kilobytes RAM  |

---

### The 10 Things to Remember

1. ✅ **`declare(strict_types=1)`** — first line of every PHP file in production
2. ✅ **`===` not `==`** — loose comparison is a bug factory
3. ✅ **Prepared statements always** — SQL injection is the #1 PHP vulnerability
4. ✅ **`password_hash()` + `password_verify()`** — for ALL passwords, no exceptions
5. ✅ **`htmlspecialchars()` every output** — or use a template engine that does it automatically
6. ✅ **`unset($ref)` after `foreach (&$ref)`** — the most common PHP foreach bug
7. ✅ **Use `DateTimeImmutable` not `DateTime`** — immutable is always safer
8. ✅ **`require_once` for class files** — never duplicate class definitions
9. ✅ **Enable OPcache in production** — most impactful performance optimization
10. ✅ **Validate input with `filter_var`** — never trust `$_GET`, `$_POST`, `$_COOKIE`

---

### Quick Reference Cheat Sheet

```php
<?php
declare(strict_types=1);

// ── SUPERGLOBALS ────────────────────────────────────────────────────────────
$_GET        // URL query string params
$_POST       // POST body params
$_REQUEST    // GET + POST + COOKIE (avoid — use specific superglobals)
$_SESSION    // Session data (session_start() first!)
$_COOKIE     // HTTP cookies
$_FILES      // Uploaded file data
$_SERVER     // Server info: HTTP_HOST, REQUEST_METHOD, REMOTE_ADDR, etc.
$_ENV        // Environment variables
$_GLOBALS    // All global variables

// ── SAFE INPUT READING ──────────────────────────────────────────────────────
$id    = filter_input(INPUT_GET, "id", FILTER_VALIDATE_INT);
$email = filter_input(INPUT_POST, "email", FILTER_VALIDATE_EMAIL);
$data  = json_decode(file_get_contents("php://input"), true); // Raw JSON body

// ── STRING ESSENTIALS ───────────────────────────────────────────────────────
mb_strlen($s)              // Character count (Unicode-safe)
mb_substr($s, $start, $n) // Substring (Unicode-safe)
mb_strtolower/upper($s)   // Case change (Unicode-safe)
str_contains($s, $needle) // PHP 8.0+
str_starts_with($s, $pre) // PHP 8.0+
str_ends_with($s, $suf)   // PHP 8.0+
sprintf("%s: %d", $s, $n) // Formatted string
preg_match("/pattern/", $subject, $matches) // Regex match
preg_replace("/pattern/", $replacement, $subject) // Regex replace

// ── ARRAY ESSENTIALS ───────────────────────────────────────────────────────
array_map(fn($x) => $x*2, $arr)     // Transform
array_filter($arr, fn($x) => $x>0)  // Filter
array_reduce($arr, fn($c,$x) => $c+$x, 0) // Fold
array_column($arr, "key")           // Extract column
usort($arr, fn($a,$b) => $a <=> $b) // Custom sort (<=> is spaceship!)
in_array($val, $arr, true)          // Membership (strict!)
array_key_exists("key", $arr)       // Key exists
array_unique($arr)                  // Remove duplicates
array_merge($a, $b)                 // Merge
array_slice($arr, 0, 10)            // Take first 10
array_chunk($arr, 100)              // Split into chunks of 100

// ── DATABASE (PDO) ──────────────────────────────────────────────────────────
$pdo = new PDO("mysql:host=localhost;dbname=db;charset=utf8mb4", "user", "pass", [
    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
    PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
    PDO::ATTR_EMULATE_PREPARES => false,
]);
$stmt = $pdo->prepare("SELECT * FROM users WHERE id = :id");
$stmt->execute([":id" => $id]);
$user = $stmt->fetch();              // One row
$users = $stmt->fetchAll();         // All rows
$id = $pdo->lastInsertId();         // Last insert ID
$pdo->beginTransaction();           // Transaction
$pdo->commit();                     // Commit
$pdo->rollBack();                   // Rollback

// ── OOP QUICK REF ──────────────────────────────────────────────────────────
class Foo extends Bar implements Baz {
    public static int $count = 0;       // Static property
    public function __construct(
        private readonly string $name,  // Promoted + readonly
        public int $age = 18            // Promoted with default
    ) {}
    public static function create(): static { return new static(); }
    public function __toString(): string { return $this->name; }
    public function __clone() { }
    public function __debugInfo(): array { return ["name" => $this->name]; }
}

// ── MODERN PHP PATTERNS ────────────────────────────────────────────────────
// Null coalescing:
$val = $arr["key"] ?? "default";
$arr["key"] ??= "default";

// Nullsafe chaining:
$city = $user?->getAddress()?->getCity();

// Match expression:
$label = match($status) { "a" => "Active", default => "Unknown" };

// Named args:
str_pad(string: "5", length: 3, pad_string: "0", pad_type: STR_PAD_LEFT);

// Spread:
$merged = [...$defaults, ...$overrides];
func(...$args);

// Destructuring:
[$a, $b] = [1, 2];
["name" => $name] = $data;

// Arrow function:
$fn = fn($x) => $x * 2;
$doubled = array_map(fn($x) => $x * 2, $arr);

// ── SECURITY ESSENTIALS ────────────────────────────────────────────────────
htmlspecialchars($s, ENT_QUOTES | ENT_SUBSTITUTE, "UTF-8")  // XSS prevention
password_hash($pwd, PASSWORD_ARGON2ID)                       // Store passwords
password_verify($input, $hash)                              // Check passwords
random_bytes(32)                                            // Cryptographic random
bin2hex(random_bytes(32))                                   // Random hex token
hash_equals($known, $user)                                  // Timing-safe compare
csrf: bin2hex(random_bytes(32)) → session → check with hash_equals

// ── PHP CLI TOOLS ──────────────────────────────────────────────────────────
php -S localhost:8000 -t public/    // Built-in dev server
php -l script.php                   // Syntax check
php -r "echo phpinfo();"            // Run inline code
php artisan ...                     // Laravel CLI
composer require vendor/package     // Install package
composer dump-autoload              // Rebuild autoloader
php vendor/bin/phpunit              // Run tests
php vendor/bin/phpstan analyse src/ // Static analysis
php vendor/bin/php-cs-fixer fix     // Fix code style
```

---

### What's Next?

After mastering PHP deeply, your natural path forward:

- 📘 **Laravel** — The most elegant PHP framework — Eloquent ORM, Blade templates, Artisan CLI, Queues, Events
- 📘 **Symfony** — Enterprise-grade components — DI Container, Event Dispatcher, Console
- 📘 **PHPStan/Psalm** — Static analysis at level 10 — catch all type errors before runtime
- 📘 **PHPUnit + Pest** — Testing, mocking, TDD in PHP
- 📘 **API Platform** — Build production REST/GraphQL APIs in minutes
- 📘 **Async PHP** — Swoole, ReactPHP, FrankenPHP — break out of shared-nothing
- 📘 **RoadRunner** — Go-powered PHP application server — persistent processes, workers

---

> 💬 *"PHP is a minor evil perpetrated and created by incompetent amateurs, whereas Perl is a great and insidious evil, perpetrated by skilled but perverted professionals."*
> — Jon Ribbens (1997 — before modern PHP existed)

> 💬 *"PHP: It's like a giant pile of magic tricks, where someone put all of Houdini's notebooks through a shredder, mixed in some Java, a splash of Perl, and called it done. And somehow it runs half the internet."*

> 💬 *"Don't underestimate PHP. It's not what it was 15 years ago. Modern PHP 8.x with strict types, enums, readonly properties, and Fibers is genuinely beautiful."*
> — Every developer who learned PHP after 7.4

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: PHP — Complete Language Mastery | Version: 1.0*
*Sections: 13 | Level: Beginner → 0.01% Elite*
