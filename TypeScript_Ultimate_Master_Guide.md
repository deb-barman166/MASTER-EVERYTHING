# 🔷 TypeScript — The Ultimate Master Guide
### From Zero to 0.01% Expert — Every Type, Pattern, Secret & Hidden Power

> 📘 **The most complete TypeScript guide ever written — beginner to elite.**
>
> 🎯 *Who is this for?* Anyone who wants to go from writing TypeScript to **thinking** in TypeScript.
> ⏱️ *Time to complete:* Self-paced — days to months
> 🛠️ *What you'll gain:* Every type, utility, pattern, compiler secret, and advanced technique that separates a 0.01% TypeScript developer from the rest.

---

## Table of Contents

1. [🧠 What is TypeScript?](#1-what-is-typescript-super-simple)
2. [🌍 Why TypeScript Exists & Dominates](#2-why-typescript-exists--dominates)
3. [🧱 Core Fundamentals](#3-core-fundamentals-beginner-level)
4. [⚙️ Complete Type System Breakdown](#4-complete-type-system-breakdown)
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

## 🧠 1. What is TypeScript? (Super Simple)

### The 12-Year-Old Explanation

Imagine you're building something with LEGO. JavaScript is like having a giant pile of bricks with no labels — any brick can go anywhere. Sometimes you accidentally put a round brick where a flat one should go. Your creation collapses, and you only find out when you try to use it.

**TypeScript puts labels on every brick.** It tells you: "This slot only accepts 2×4 flat red bricks." If you try to put a round green brick there, it warns you *before* you finish building — not after it collapses.

TypeScript is JavaScript with a **type system** added on top. You write TypeScript code, and it compiles down to regular JavaScript that browsers and Node.js understand. The type system runs only during development — it catches bugs before your code ever runs, making you faster and more confident.

It was created by **Anders Hejlsberg** (who also created C# and Turbo Pascal) at Microsoft, released in 2012, and has since become the dominant way to write large-scale JavaScript applications.

### Real-Life Analogy

💡 **Think of it like this:**
JavaScript is like verbal instructions. "Go to the store, buy milk, and come back." Sounds clear — but what store? What kind of milk? How much? What if there's no milk?

TypeScript is like a detailed written contract. "Go to FoodMart on 5th Street, buy exactly 1 liter of full-fat milk in a recyclable bottle, and return within 30 minutes. If milk is unavailable, call me immediately." Everything is explicit, verifiable, and unambiguous — before a single step is taken.

### One-Line Definition

> **TypeScript** is a statically-typed superset of JavaScript that compiles to plain JavaScript — adding a powerful type system that catches bugs at compile time, enables superior tooling, and makes large codebases maintainable.

---

## 🌍 2. Why TypeScript Exists & Dominates

### The Problem It Solved

JavaScript was designed in 1995 for small scripts on web pages. By 2010, teams were writing hundreds of thousands of lines of JavaScript. Three massive problems emerged:

1. **Runtime errors** — You call `user.name` but `user` is `undefined`. You find out only when users report a bug at 2 AM.
2. **No tooling** — Your editor can't autocomplete because it doesn't know what properties an object has.
3. **Refactoring nightmares** — Rename a function and you have no idea what broke without running every code path manually.

TypeScript solves all three: **types** catch errors at development time, enable **intelligent autocomplete**, and make **safe refactoring** possible.

### Where TypeScript Is Used Today

| Company / Domain              | How TypeScript Is Used                                          |
|-------------------------------|------------------------------------------------------------------|
| Microsoft                     | VS Code, Azure SDKs, Office 365 — all TypeScript               |
| Google                        | Angular is TypeScript-first; internal tooling                   |
| Airbnb                        | Migrated entire frontend — caught 38% of bugs pre-release       |
| Slack                         | Entire desktop and web app rewritten in TypeScript              |
| Stripe                        | Payment APIs, dashboard, entire Node.js backend                 |
| Discord                       | Migrated from JavaScript — significant performance wins too     |
| Meta / Shopify / Twitter      | Heavy TypeScript usage across web properties                    |
| Open Source (React, Vue, etc.)| React, Vue 3, Next.js, Vite, Prisma — all written in TypeScript |

### Why YOU Should Learn It Deeply

1. **Every serious job requires it** — 80%+ of frontend and Node.js job listings mention TypeScript explicitly.
2. **Catches bugs you wouldn't catch in testing** — TypeScript finds entire categories of errors that tests miss.
3. **AI tools generate TypeScript** — GitHub Copilot and Claude generate typed code; you must understand types to evaluate it.
4. **Refactoring confidence** — Rename a property across 50 files without fear. The compiler guides every change.
5. **Documentation that never goes stale** — Types ARE documentation. A well-typed function tells you everything.

---

## 🧱 3. Core Fundamentals (Beginner Level)

> 🎯 *Goal: Build an unshakeable foundation in TypeScript's type system.*

---

### Concept 1: Basic Types — The Building Blocks

```typescript
// ── PRIMITIVE TYPES ────────────────────────────────────────────────────

// Explicit type annotations (: Type after variable name):
let name: string = "Aryan";
let age: number = 17;
let isStudent: boolean = true;
let nothing: null = null;
let notDefined: undefined = undefined;

// TypeScript can INFER types — you don't always need to annotate!
let name2 = "Aryan";     // TypeScript infers: string
let age2 = 17;           // TypeScript infers: number
let active = true;       // TypeScript infers: boolean

// Inference is preferred when the type is obvious from the value:
const PI = 3.14159;      // Inferred as literal type 3.14159 — even more precise!

// ── SPECIAL TYPES ─────────────────────────────────────────────────────

// any — disables type checking (use sparingly — it's an escape hatch):
let value: any = "hello";
value = 42;              // OK — any accepts everything
value = true;            // OK
value.foo.bar.baz;       // No error! (Dangerous — you lose all safety)

// unknown — type-safe version of any:
let safe: unknown = "hello";
safe = 42;               // OK — can assign anything
// safe.toUpperCase();   // ❌ Error! Must narrow first
if (typeof safe === "string") {
  safe.toUpperCase();    // ✅ OK — now TypeScript knows it's a string
}

// never — a value that never occurs (function that always throws, infinite loops):
function fail(message: string): never {
  throw new Error(message);     // This function never returns normally
}

function infiniteLoop(): never {
  while (true) {}               // Never returns
}

// void — function that doesn't return a meaningful value:
function logMessage(msg: string): void {
  console.log(msg);
  // No return, or return; — no value
}

// ── OBJECT TYPES ───────────────────────────────────────────────────────

// Object type literal:
let user: { name: string; age: number; email: string } = {
  name: "Aryan",
  age: 17,
  email: "aryan@example.com",
};

// Optional properties (? makes them optional):
let config: { host: string; port?: number; debug?: boolean } = {
  host: "localhost",
  // port and debug are optional
};

// Readonly properties:
let point: { readonly x: number; readonly y: number } = { x: 10, y: 20 };
// point.x = 30; // ❌ Error — cannot assign to 'x' because it is a read-only property

// ── ARRAY TYPES ────────────────────────────────────────────────────────

let numbers: number[] = [1, 2, 3, 4, 5];
let names: string[] = ["Alice", "Bob", "Charlie"];
let mixed: (string | number)[] = ["Alice", 1, "Bob", 2];  // Union array

// Alternative generic syntax:
let nums: Array<number> = [1, 2, 3];
let strs: Array<string> = ["a", "b", "c"];

// Readonly array:
let frozen: readonly number[] = [1, 2, 3];
// frozen.push(4);  // ❌ Error!

// ── TUPLE TYPES — fixed-length, typed arrays ────────────────────────────

let pair: [string, number] = ["Alice", 30];
let [personName, personAge] = pair;  // Destructuring with types preserved

// Named tuple elements (TypeScript 4.0+):
let rgb: [red: number, green: number, blue: number] = [255, 128, 0];

// Optional tuple elements:
let optTuple: [string, number?] = ["Alice"];  // number is optional
let optTuple2: [string, number?] = ["Alice", 30];

// Rest elements in tuples:
let flexTuple: [string, ...number[]] = ["label", 1, 2, 3, 4];
```

---

### Concept 2: Interfaces vs Type Aliases

```typescript
// ── INTERFACE — describes object shapes ────────────────────────────────

interface User {
  id: number;
  name: string;
  email: string;
  age?: number;           // Optional
  readonly createdAt: Date; // Readonly
}

// Interfaces can be EXTENDED (inheritance):
interface AdminUser extends User {
  role: "admin";
  permissions: string[];
}

// Interfaces can be MERGED (declaration merging):
interface Window {
  myCustomProperty: string;  // Adds to the existing Window interface!
}

// ── TYPE ALIAS — names any type ────────────────────────────────────────

type UserID = number | string;  // Union type — can't do this with interface
type Point = { x: number; y: number };
type Callback = (error: Error | null, result: string) => void;
type StringOrNumber = string | number;

// Type aliases can be extended with intersection (&):
type AdminUser2 = User & {
  role: "admin";
  permissions: string[];
};

// ── WHEN TO USE WHICH ──────────────────────────────────────────────────
/*
  Use INTERFACE when:
  ✅ Describing object shapes (especially in public APIs)
  ✅ You need declaration merging (extending built-in types)
  ✅ You're defining a class contract
  ✅ You want better error messages (interfaces have names in errors)

  Use TYPE when:
  ✅ Unions: type ID = string | number
  ✅ Intersections: type AB = A & B
  ✅ Mapped types, conditional types, template literals
  ✅ Aliases for primitive or complex types
  ✅ You want a type that cannot be re-opened/merged

  In practice: either works for most object shapes.
  The TypeScript team recommends interfaces for object types.
*/

// ── INTERFACE EXAMPLES ─────────────────────────────────────────────────

// Function interface:
interface Formatter {
  (value: string, options?: { uppercase?: boolean }): string;
}

// Indexable interface (like a dictionary):
interface StringDictionary {
  [key: string]: string;     // Any string key → string value
}

interface NumberDictionary {
  [key: string]: number;
  length: number;            // OK — number satisfies number
  // name: string;           // ❌ Error — string not assignable to number
}

// Class implementing an interface:
interface Serializable {
  serialize(): string;
  deserialize(data: string): this;
}

class UserModel implements Serializable {
  constructor(public name: string, public age: number) {}

  serialize(): string {
    return JSON.stringify({ name: this.name, age: this.age });
  }

  deserialize(data: string): this {
    const parsed = JSON.parse(data);
    return Object.assign(Object.create(Object.getPrototypeOf(this)), parsed);
  }
}
```

---

### Concept 3: Union & Intersection Types

```typescript
// ── UNION TYPES (|) — "this OR that" ───────────────────────────────────

type StringOrNumber = string | number;
type Status = "active" | "inactive" | "pending" | "banned";  // Literal union
type Result<T> = { success: true; data: T } | { success: false; error: string };

function formatId(id: string | number): string {
  // Narrowing with typeof:
  if (typeof id === "string") {
    return id.toUpperCase();    // TypeScript knows: id is string here
  }
  return id.toString();         // TypeScript knows: id is number here
}

// Discriminated union — unions with a common "discriminant" property:
type Shape =
  | { kind: "circle";    radius: number }
  | { kind: "rectangle"; width: number; height: number }
  | { kind: "triangle";  base: number; height: number };

function area(shape: Shape): number {
  switch (shape.kind) {
    case "circle":
      return Math.PI * shape.radius ** 2;   // shape is { kind: "circle", radius: number }
    case "rectangle":
      return shape.width * shape.height;    // shape is { kind: "rectangle", ... }
    case "triangle":
      return 0.5 * shape.base * shape.height;
    default:
      // Exhaustiveness check — if you add a new shape without handling it:
      const _exhaustive: never = shape;     // ❌ Error if shape is not never
      return _exhaustive;
  }
}

// ── INTERSECTION TYPES (&) — "this AND that" ───────────────────────────

type Timestamped = { createdAt: Date; updatedAt: Date };
type Identified = { id: string };
type SoftDeletable = { deletedAt: Date | null };

// Combine all three:
type Entity = Identified & Timestamped & SoftDeletable;

type Admin = User & { role: "admin"; permissions: string[] };

// Mixin pattern:
function withTimestamps<T>(obj: T): T & Timestamped {
  return {
    ...obj,
    createdAt: new Date(),
    updatedAt: new Date(),
  };
}
```

---

### Concept 4: Type Narrowing — The Art of Refinement

```typescript
// Narrowing = making TypeScript understand a value is a specific type
// within a conditional block

// ── TYPE GUARDS ────────────────────────────────────────────────────────

// typeof narrowing:
function process(value: string | number | boolean) {
  if (typeof value === "string") {
    return value.toUpperCase();   // string methods available
  }
  if (typeof value === "number") {
    return value.toFixed(2);      // number methods available
  }
  return value ? "yes" : "no";   // boolean
}

// instanceof narrowing:
function formatDate(date: Date | string): string {
  if (date instanceof Date) {
    return date.toISOString();    // Date methods available
  }
  return new Date(date).toISOString();
}

// in narrowing — check if property exists:
type Cat = { meow(): void; purr(): void };
type Dog = { bark(): void; fetch(): void };

function interact(animal: Cat | Dog) {
  if ("meow" in animal) {
    animal.meow();    // Cat
  } else {
    animal.bark();    // Dog
  }
}

// Truthiness narrowing:
function printLength(str: string | null | undefined) {
  if (str) {                        // null and undefined are falsy
    console.log(str.length);        // str is string here
  }
}

// Equality narrowing:
function compare(x: string | number, y: string | boolean) {
  if (x === y) {
    // x and y must both be string (only type they share)
    console.log(x.toUpperCase());
  }
}

// ── USER-DEFINED TYPE GUARDS ────────────────────────────────────────────

// Type predicate: "value is Type" return type
function isString(value: unknown): value is string {
  return typeof value === "string";
}

function isUser(value: unknown): value is User {
  return (
    typeof value === "object" &&
    value !== null &&
    "id" in value &&
    "name" in value &&
    typeof (value as any).id === "number" &&
    typeof (value as any).name === "string"
  );
}

// Usage:
function processValue(value: unknown) {
  if (isString(value)) {
    console.log(value.toUpperCase());  // TypeScript knows: string!
  }
  if (isUser(value)) {
    console.log(value.name, value.id); // TypeScript knows: User!
  }
}

// ── ASSERTION FUNCTIONS ────────────────────────────────────────────────

// asserts value is Type — throws if condition is false:
function assertIsString(value: unknown): asserts value is string {
  if (typeof value !== "string") {
    throw new Error(`Expected string, got ${typeof value}`);
  }
}

function assertDefined<T>(value: T | null | undefined): asserts value is T {
  if (value == null) throw new Error("Value is null or undefined");
}

// After calling assertDefined, TypeScript narrows the type:
function processUser(user: User | null) {
  assertDefined(user);
  console.log(user.name);  // TypeScript knows: user is User!
}
```

---

### Concept 5: Functions — Complete Typing

```typescript
// ── FUNCTION SIGNATURES ────────────────────────────────────────────────

// Named function:
function add(a: number, b: number): number {
  return a + b;
}

// Arrow function:
const multiply = (a: number, b: number): number => a * b;

// Optional parameters (must come after required):
function greet(name: string, greeting?: string): string {
  return `${greeting ?? "Hello"}, ${name}!`;
}

// Default parameters:
function createUser(name: string, role: string = "user"): User {
  return { id: Date.now(), name, email: "", role };
}

// Rest parameters:
function sum(...numbers: number[]): number {
  return numbers.reduce((a, b) => a + b, 0);
}

// ── FUNCTION OVERLOADS ────────────────────────────────────────────────

// Multiple signatures for one function:
function format(value: string): string;
function format(value: number, decimals: number): string;
function format(value: Date, locale: string): string;
function format(value: string | number | Date, param?: number | string): string {
  // Implementation (not visible to callers):
  if (typeof value === "string") return value;
  if (typeof value === "number") return value.toFixed(param as number ?? 2);
  return value.toLocaleString(param as string ?? "en-US");
}

// Callers see clean overloads:
format("hello");          // ✅ uses overload 1
format(3.14159, 2);       // ✅ uses overload 2
format(new Date(), "hi"); // ✅ uses overload 3

// ── GENERIC FUNCTIONS ──────────────────────────────────────────────────

// The most powerful pattern in TypeScript:
function identity<T>(value: T): T {
  return value;
}
const num = identity(42);    // T inferred as 42 (literal)
const str = identity("hi");  // T inferred as string

// Generic with constraint:
function getProperty<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}

const user = { name: "Aryan", age: 17 };
const name = getProperty(user, "name");  // Type: string
const age = getProperty(user, "age");    // Type: number
// getProperty(user, "email");           // ❌ Error! "email" not a key of user

// Multiple generics:
function zip<A, B>(a: A[], b: B[]): [A, B][] {
  return a.map((item, i) => [item, b[i]]);
}
const zipped = zip([1, 2, 3], ["a", "b", "c"]);
// Type: [number, string][]

// ── FUNCTION TYPE SIGNATURES ───────────────────────────────────────────

// Type alias for a function:
type Predicate<T> = (value: T) => boolean;
type Transform<T, U> = (value: T) => U;
type AsyncTransform<T, U> = (value: T) => Promise<U>;

// Using them:
const isEven: Predicate<number> = (n) => n % 2 === 0;
const toString: Transform<number, string> = (n) => String(n);

// ── CALLABLE INTERFACE ─────────────────────────────────────────────────
interface Validator {
  (value: string): boolean;
  description: string;    // Also has properties!
}

const emailValidator: Validator = Object.assign(
  (value: string) => /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(value),
  { description: "Validates email format" }
);
```

---

🧪 **Mini Task 1:**
> Create a `Stack<T>` class that is fully generic. It should have `push(item: T): void`, `pop(): T | undefined`, `peek(): T | undefined`, `isEmpty(): boolean`, and `size: number`. Make it impossible to push the wrong type.
> ✅ *Expected: `new Stack<number>()` accepts only numbers, `new Stack<string>()` accepts only strings.*

🧪 **Mini Task 2:**
> Write a type-safe `EventEmitter<Events>` where `Events` is a record of event names to their payload types. `emit("login", { userId: string })` should only compile if "login" maps to `{ userId: string }`.

---

## ⚙️ 4. Complete Type System Breakdown

> 🎯 *Goal: Master every category of TypeScript's type system — nothing hidden.*

---

### Part 1: Generics — The Cornerstone of Reusable Types

```typescript
// ── GENERIC CONSTRAINTS ────────────────────────────────────────────────

// extends — constrain what T can be:
function longest<T extends { length: number }>(a: T, b: T): T {
  return a.length >= b.length ? a : b;
}
longest("hello", "hi");        // ✅ strings have length
longest([1, 2, 3], [1, 2]);    // ✅ arrays have length
// longest(1, 2);               // ❌ numbers don't have length

// keyof constraint:
function pluck<T, K extends keyof T>(array: T[], key: K): T[K][] {
  return array.map(item => item[key]);
}
const users = [{ name: "Alice", age: 25 }, { name: "Bob", age: 30 }];
const names = pluck(users, "name");    // string[]
const ages  = pluck(users, "age");     // number[]
// pluck(users, "email");              // ❌ Error

// ── DEFAULT TYPE PARAMETERS ────────────────────────────────────────────

interface Container<T = string> {    // Default: string
  value: T;
  transform<U = T>(fn: (v: T) => U): Container<U>;
}

// ── GENERIC CLASSES ────────────────────────────────────────────────────

class Repository<T extends { id: number }> {
  private items: Map<number, T> = new Map();

  add(item: T): void {
    this.items.set(item.id, item);
  }

  getById(id: number): T | undefined {
    return this.items.get(id);
  }

  getAll(): T[] {
    return Array.from(this.items.values());
  }

  update(id: number, partial: Partial<T>): T | undefined {
    const item = this.items.get(id);
    if (!item) return undefined;
    const updated = { ...item, ...partial };
    this.items.set(id, updated);
    return updated;
  }

  delete(id: number): boolean {
    return this.items.delete(id);
  }

  query(predicate: (item: T) => boolean): T[] {
    return this.getAll().filter(predicate);
  }
}

const userRepo = new Repository<User>();
userRepo.add({ id: 1, name: "Aryan", email: "a@example.com" });
const user = userRepo.getById(1);      // User | undefined
const activeUsers = userRepo.query(u => u.name.startsWith("A")); // User[]
```

---

### Part 2: Utility Types — TypeScript's Built-in Power Tools

```typescript
// Every built-in utility type — learn these cold!

// ── Partial<T> — makes all properties optional ──────────────────────────
interface User {
  id: number;
  name: string;
  email: string;
  age: number;
}

type UserUpdate = Partial<User>;
// { id?: number; name?: string; email?: string; age?: number }

function updateUser(id: number, data: Partial<User>): User {
  // Only update provided fields
  return { ...getUser(id), ...data };
}

// ── Required<T> — makes all properties required ──────────────────────────
type RequiredConfig = Required<{
  host?: string;
  port?: number;
  debug?: boolean;
}>;
// { host: string; port: number; debug: boolean }

// ── Readonly<T> — makes all properties readonly ──────────────────────────
const frozenUser: Readonly<User> = { id: 1, name: "Aryan", email: "a@ex.com", age: 17 };
// frozenUser.name = "Bob";  // ❌ Error!

// ── Record<K, V> — dictionary type ───────────────────────────────────────
type PageViews = Record<string, number>;
const views: PageViews = { "/home": 1000, "/about": 500 };

type StatusMessage = Record<"pending" | "active" | "error", string>;
const messages: StatusMessage = {
  pending: "Loading...",
  active:  "Ready",
  error:   "Something went wrong",
};

// ── Pick<T, K> — select subset of properties ─────────────────────────────
type UserPreview = Pick<User, "id" | "name">;
// { id: number; name: string }

type LoginData = Pick<User, "email">;
// { email: string }

// ── Omit<T, K> — exclude properties ──────────────────────────────────────
type UserWithoutId = Omit<User, "id">;
// { name: string; email: string; age: number }

type CreateUserDTO = Omit<User, "id">;  // Input for creation
type UpdateUserDTO = Partial<Omit<User, "id">>;  // Input for update

// ── Exclude<T, U> — remove from union ────────────────────────────────────
type NonString = Exclude<string | number | boolean, string>;
// number | boolean

type CleanStatus = Exclude<"active" | "inactive" | "pending" | null | undefined, null | undefined>;
// "active" | "inactive" | "pending"

// ── Extract<T, U> — keep from union ───────────────────────────────────────
type StringsOnly = Extract<string | number | boolean, string | number>;
// string | number

// ── NonNullable<T> — remove null and undefined ────────────────────────────
type DefinitelyString = NonNullable<string | null | undefined>;
// string

function processDefinite<T>(value: NonNullable<T>): void { /* ... */ }

// ── ReturnType<T> — extract function return type ──────────────────────────
function createSession() {
  return {
    id: crypto.randomUUID(),
    createdAt: new Date(),
    expiresAt: new Date(Date.now() + 3600000),
    userId: "",
  };
}

type Session = ReturnType<typeof createSession>;
// { id: string; createdAt: Date; expiresAt: Date; userId: string }

// ── Parameters<T> — extract function parameter types ─────────────────────
function sendEmail(to: string, subject: string, body: string): Promise<void> {
  return Promise.resolve();
}

type SendEmailParams = Parameters<typeof sendEmail>;
// [to: string, subject: string, body: string]

type FirstParam = Parameters<typeof sendEmail>[0];  // string

// ── ConstructorParameters<T> — extract class constructor params ───────────
class ApiClient {
  constructor(baseUrl: string, timeout: number, apiKey: string) {}
}

type ApiClientParams = ConstructorParameters<typeof ApiClient>;
// [baseUrl: string, timeout: number, apiKey: string]

// ── InstanceType<T> — get class instance type ────────────────────────────
type ApiClientInstance = InstanceType<typeof ApiClient>;

// ── Awaited<T> — unwrap Promise (TypeScript 4.5+) ────────────────────────
type Resolved = Awaited<Promise<string>>;           // string
type DeepResolved = Awaited<Promise<Promise<number>>>;  // number

// ── ThisType<T> — type 'this' in methods ─────────────────────────────────
interface HelperMethods<T> {
  find(predicate: (item: T) => boolean): T | undefined;
  filter(predicate: (item: T) => boolean): T[];
}

// COMPOSING UTILITIES ──────────────────────────────────────────────────

// Real-world composition:
type CreateDTO<T extends { id: unknown; createdAt: unknown; updatedAt: unknown }> =
  Omit<T, "id" | "createdAt" | "updatedAt">;

type UpdateDTO<T extends { id: unknown }> =
  Partial<Omit<T, "id">> & Pick<T, "id">;

// Deep partial (recursive):
type DeepPartial<T> = {
  [P in keyof T]?: T[P] extends object ? DeepPartial<T[P]> : T[P];
};
```

---

### Part 3: Mapped Types — Transform Types Systematically

```typescript
// ── MAPPED TYPE SYNTAX ─────────────────────────────────────────────────
// { [P in keyof T]: NewType }

// Make all properties optional (reimplementing Partial):
type MyPartial<T> = {
  [P in keyof T]?: T[P];
};

// Make all properties readonly:
type MyReadonly<T> = {
  readonly [P in keyof T]: T[P];
};

// Make all properties nullable:
type Nullable<T> = {
  [P in keyof T]: T[P] | null;
};

// ── MAPPING MODIFIERS ─────────────────────────────────────────────────
// + adds modifier (default), - removes modifier

// Remove readonly:
type Mutable<T> = {
  -readonly [P in keyof T]: T[P];
};

// Remove optional:
type Complete<T> = {
  [P in keyof T]-?: T[P];
};

// ── KEY REMAPPING (TypeScript 4.1+) ────────────────────────────────────

// Remap keys with 'as':
type Getters<T> = {
  [K in keyof T as `get${Capitalize<string & K>}`]: () => T[K];
};

interface Person {
  name: string;
  age: number;
  email: string;
}

type PersonGetters = Getters<Person>;
// { getName: () => string; getAge: () => number; getEmail: () => string }

// Filter properties by type:
type StringProps<T> = {
  [K in keyof T as T[K] extends string ? K : never]: T[K];
};

type PersonStringProps = StringProps<Person>;
// { name: string; email: string }  — age (number) is filtered out!

// ── ADVANCED MAPPED TYPES ──────────────────────────────────────────────

// Create event handler types from a model:
type EventHandlers<T> = {
  [K in keyof T as `on${Capitalize<string & K>}Change`]: (
    newValue: T[K],
    oldValue: T[K]
  ) => void;
};

type PersonHandlers = EventHandlers<Person>;
// {
//   onNameChange: (newValue: string, oldValue: string) => void;
//   onAgeChange:  (newValue: number, oldValue: number) => void;
//   onEmailChange: (newValue: string, oldValue: string) => void;
// }

// Flatten nested types:
type Flatten<T> = {
  [K in keyof T]: T[K] extends Array<infer U> ? U : T[K];
};
```

---

### Part 4: Conditional Types — Type-Level Logic

```typescript
// ── CONDITIONAL TYPE SYNTAX ────────────────────────────────────────────
// T extends U ? TrueType : FalseType

type IsString<T> = T extends string ? true : false;

type A = IsString<string>;   // true
type B = IsString<number>;   // false
type C = IsString<"hello">; // true  (literal type extends string)

// ── INFER — extract types from within other types ─────────────────────

// Extract the return type of a function:
type GetReturnType<T> = T extends (...args: any[]) => infer R ? R : never;

type R1 = GetReturnType<() => string>;          // string
type R2 = GetReturnType<(x: number) => boolean>; // boolean
type R3 = GetReturnType<string>;                 // never (not a function)

// Extract the element type of an array:
type ArrayElement<T> = T extends Array<infer E> ? E : never;

type E1 = ArrayElement<string[]>;    // string
type E2 = ArrayElement<number[][]>;  // number[]
type E3 = ArrayElement<string>;      // never

// Extract Promise value:
type Unwrap<T> = T extends Promise<infer U> ? Unwrap<U> : T;

type U1 = Unwrap<Promise<string>>;                 // string
type U2 = Unwrap<Promise<Promise<number>>>;         // number
type U3 = Unwrap<string>;                           // string

// Extract function parameter types:
type FirstArg<T extends (...args: any[]) => any> =
  T extends (first: infer F, ...rest: any[]) => any ? F : never;

type F1 = FirstArg<(x: string, y: number) => void>;  // string

// ── DISTRIBUTIVE CONDITIONAL TYPES ────────────────────────────────────
// When T is a naked type parameter in a union, conditional distributes:

type ToArray<T> = T extends any ? T[] : never;
// With union: ToArray<string | number> = string[] | number[]

type NonNullableOwn<T> = T extends null | undefined ? never : T;
// NonNullableOwn<string | null | undefined> = string

// Prevent distribution with [] wrapper:
type ToArrayNonDist<T> = [T] extends [any] ? T[] : never;
// ToArrayNonDist<string | number> = (string | number)[]

// ── COMPLEX CONDITIONAL TYPE EXAMPLES ────────────────────────────────

// Deeply flatten a nested type:
type DeepFlatten<T> = T extends Array<infer U> ? DeepFlatten<U> : T;
type DF = DeepFlatten<number[][][]>;  // number

// Check if type is never:
type IsNever<T> = [T] extends [never] ? true : false;

// Check if two types are equal:
type Equal<A, B> =
  (<T>() => T extends A ? 1 : 2) extends
  (<T>() => T extends B ? 1 : 2) ? true : false;
```

---

### Part 5: Template Literal Types — String Manipulation at Type Level

```typescript
// ── BASIC TEMPLATE LITERALS ────────────────────────────────────────────

type Greeting = `Hello, ${string}!`;
const g1: Greeting = "Hello, Aryan!";     // ✅
const g2: Greeting = "Hello, World!";    // ✅
// const g3: Greeting = "Goodbye!";       // ❌

type EventName = `on${string}`;
const e1: EventName = "onClick";         // ✅
const e2: EventName = "onChange";        // ✅
// const e3: EventName = "click";          // ❌

// ── COMBINING WITH UNIONS ──────────────────────────────────────────────

type Direction = "top" | "right" | "bottom" | "left";
type CSSProperty = "margin" | "padding" | "border";

type CSSDirectionalProperty = `${CSSProperty}-${Direction}`;
// "margin-top" | "margin-right" | "margin-bottom" | "margin-left" |
// "padding-top" | ... | "border-left"  (12 combinations!)

// Color scale:
type ColorName = "red" | "green" | "blue" | "purple";
type ColorWeight = 50 | 100 | 200 | 300 | 400 | 500 | 600 | 700 | 800 | 900;
type TailwindColor = `${ColorName}-${ColorWeight}`;
// "red-50" | "red-100" | ... | "purple-900"

// ── STRING MANIPULATION TYPES ──────────────────────────────────────────

type Upper = Uppercase<"hello">;        // "HELLO"
type Lower = Lowercase<"WORLD">;        // "world"
type Cap   = Capitalize<"hello">;       // "Hello"
type Uncap = Uncapitalize<"Hello">;     // "hello"

// Real use case — generate getters from object type:
type PropToGetter<T> = {
  [K in keyof T & string as `get${Capitalize<K>}`]: () => T[K];
};

interface Config {
  host: string;
  port: number;
  debug: boolean;
}

type ConfigGetters = PropToGetter<Config>;
// { getHost: () => string; getPort: () => number; getDebug: () => boolean }

// CSS-in-TS property names:
type CSSValue = `${number}px` | `${number}%` | `${number}rem` | `${number}em` | "auto" | "none";

// API endpoints:
type ApiVersion = "v1" | "v2" | "v3";
type Resource = "users" | "posts" | "comments";
type ApiEndpoint = `/api/${ApiVersion}/${Resource}`;
// "/api/v1/users" | "/api/v1/posts" | ... (9 combinations)
```

---

### Part 6: Classes — Advanced OOP in TypeScript

```typescript
// ── CLASS MODIFIERS ────────────────────────────────────────────────────

class BankAccount {
  // Access modifiers:
  public accountNumber: string;          // Accessible everywhere (default)
  private balance: number;               // Only within THIS class
  protected owner: string;               // This class + subclasses
  readonly bank: string = "GlobalBank";  // Read-only after construction

  // Private class field (ECMAScript standard — truly private):
  #pin: number;

  // Static properties:
  static totalAccounts: number = 0;
  private static readonly INTEREST_RATE = 0.05;

  // Parameter shorthand (declare + assign in one):
  constructor(
    public accountNumber: string,    // shorthand: public
    private balance: number,         // shorthand: private
    protected owner: string          // shorthand: protected
  ) {
    this.#pin = Math.floor(1000 + Math.random() * 9000);
    BankAccount.totalAccounts++;
  }

  // Getter / Setter:
  get currentBalance(): number {
    return this.balance;
  }

  set deposit(amount: number) {
    if (amount <= 0) throw new Error("Deposit must be positive");
    this.balance += amount;
  }

  // Abstract-like method to override:
  protected calculateFee(amount: number): number {
    return amount * 0.01;
  }

  withdraw(amount: number): void {
    const fee = this.calculateFee(amount);
    if (amount + fee > this.balance) throw new Error("Insufficient funds");
    this.balance -= amount + fee;
  }

  verifyPin(pin: number): boolean {
    return this.#pin === pin;
  }

  static getInterestRate(): number {
    return BankAccount.INTEREST_RATE;
  }
}

// ── ABSTRACT CLASSES ──────────────────────────────────────────────────

abstract class Animal {
  constructor(public name: string) {}

  abstract makeSound(): string;           // Must be implemented by subclass
  abstract get description(): string;

  // Concrete method shared by all:
  move(distance: number = 0): void {
    console.log(`${this.name} moved ${distance}m.`);
  }
}

class Dog extends Animal {
  makeSound(): string {
    return "Woof!";
  }

  get description(): string {
    return `${this.name} is a dog`;
  }
}

// new Animal("Cat");  // ❌ Cannot instantiate abstract class

// ── MIXINS — reusable behavior composition ────────────────────────────

// Define mixin functions:
type Constructor<T = {}> = new (...args: any[]) => T;

function Timestamped<TBase extends Constructor>(Base: TBase) {
  return class extends Base {
    createdAt = new Date();
    updatedAt = new Date();

    touch() { this.updatedAt = new Date(); }
  };
}

function Activatable<TBase extends Constructor>(Base: TBase) {
  return class extends Base {
    isActive = false;

    activate()   { this.isActive = true; }
    deactivate() { this.isActive = false; }
  };
}

// Apply mixins:
class UserBase {
  constructor(public name: string) {}
}

const TimestampedActivatableUser = Activatable(Timestamped(UserBase));

class User2 extends TimestampedActivatableUser {
  constructor(name: string, public email: string) {
    super(name);
  }
}

const user = new User2("Aryan", "aryan@example.com");
user.activate();
user.touch();
console.log(user.isActive, user.createdAt, user.updatedAt);
```

---

### 📊 Full Type System Reference

| Category              | Examples                                                                     |
|-----------------------|------------------------------------------------------------------------------|
| Primitives            | `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint`       |
| Special               | `any`, `unknown`, `never`, `void`                                            |
| Object types          | Interface, type alias literal, class instance                                |
| Array / Tuple         | `T[]`, `Array<T>`, `[A, B, C]`, `readonly T[]`                               |
| Union / Intersection  | `A \| B`, `A & B`, discriminated unions                                      |
| Generics              | `<T>`, `<T extends U>`, `<T = Default>`                                      |
| Utility types         | `Partial`, `Required`, `Readonly`, `Record`, `Pick`, `Omit`, `ReturnType`... |
| Mapped types          | `{ [P in keyof T]: ... }`, key remapping with `as`                           |
| Conditional types     | `T extends U ? X : Y`, `infer`                                               |
| Template literals     | `` `prefix_${string}` ``, `Uppercase<T>`, `Capitalize<T>`                   |
| Type guards           | `typeof`, `instanceof`, `in`, user-defined predicates                        |

---

## 🔄 5. Real-World Workflow

### 🟢 Beginner Workflow: Type-Safe API Client

```typescript
// api-client.ts — A fully typed HTTP client

// Define API shape:
interface ApiEndpoints {
  "/users":           { GET: User[];      POST: User };
  "/users/:id":       { GET: User;        PUT: User;  DELETE: void };
  "/users/:id/posts": { GET: Post[] };
  "/posts":           { GET: Post[];      POST: Post };
}

// HTTP method type:
type HttpMethod = "GET" | "POST" | "PUT" | "PATCH" | "DELETE";

// Base API response wrapper:
interface ApiResponse<T> {
  data: T;
  status: number;
  message: string;
  timestamp: string;
}

// Error response:
interface ApiError {
  error: string;
  code: string;
  details?: Record<string, string[]>;
}

// Result type (avoid throwing):
type Result<T, E = ApiError> =
  | { ok: true;  data: T }
  | { ok: false; error: E };

// Generic request options:
interface RequestOptions<TBody = unknown> {
  body?: TBody;
  headers?: Record<string, string>;
  signal?: AbortSignal;
  timeout?: number;
}

class ApiClient {
  private baseURL: string;
  private defaultHeaders: Record<string, string>;

  constructor(baseURL: string, apiKey: string) {
    this.baseURL = baseURL;
    this.defaultHeaders = {
      "Content-Type": "application/json",
      "Authorization": `Bearer ${apiKey}`,
    };
  }

  async request<TResponse, TBody = unknown>(
    method: HttpMethod,
    endpoint: string,
    options: RequestOptions<TBody> = {}
  ): Promise<Result<TResponse>> {
    const controller = new AbortController();
    const timeoutId = options.timeout
      ? setTimeout(() => controller.abort(), options.timeout)
      : null;

    try {
      const response = await fetch(`${this.baseURL}${endpoint}`, {
        method,
        headers: { ...this.defaultHeaders, ...options.headers },
        body: options.body ? JSON.stringify(options.body) : undefined,
        signal: options.signal ?? controller.signal,
      });

      if (timeoutId) clearTimeout(timeoutId);

      const json = await response.json();

      if (!response.ok) {
        return { ok: false, error: json as ApiError };
      }

      return { ok: true, data: (json as ApiResponse<TResponse>).data };
    } catch (error) {
      return {
        ok: false,
        error: {
          error: error instanceof Error ? error.message : "Unknown error",
          code: "NETWORK_ERROR",
        },
      };
    }
  }

  get<T>(endpoint: string, options?: RequestOptions): Promise<Result<T>> {
    return this.request<T>("GET", endpoint, options);
  }

  post<T, B>(endpoint: string, body: B, options?: RequestOptions<B>): Promise<Result<T>> {
    return this.request<T, B>("POST", endpoint, { ...options, body });
  }
}

// Usage:
const api = new ApiClient("https://api.example.com", process.env.API_KEY!);

async function loadUser(id: number) {
  const result = await api.get<User>(`/users/${id}`);

  if (!result.ok) {
    console.error("Failed:", result.error.error);
    return null;
  }

  return result.data;  // Type: User — fully typed!
}
```

---

### 🔵 Professional Workflow: Domain-Driven Design with TypeScript

```typescript
// domain/user/types.ts

// Branded types — primitives with identity:
type UserId = string & { readonly __brand: "UserId" };
type Email = string & { readonly __brand: "Email" };
type HashedPassword = string & { readonly __brand: "HashedPassword" };

// Constructors that validate:
function createUserId(value: string): UserId {
  if (!value || value.length < 1) throw new Error("Invalid user ID");
  return value as UserId;
}

function createEmail(value: string): Email {
  if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(value))
    throw new Error("Invalid email");
  return value.toLowerCase() as Email;
}

// Domain entities:
interface UserProfile {
  readonly id: UserId;
  readonly email: Email;
  name: string;
  bio: string | null;
  avatar: string | null;
  createdAt: Date;
  updatedAt: Date;
}

// Value objects (immutable):
interface Address {
  readonly street: string;
  readonly city: string;
  readonly country: string;
  readonly postalCode: string;
}

// Commands (what you can do):
interface CreateUserCommand {
  name: string;
  email: string;
  password: string;
}

interface UpdateUserCommand {
  id: UserId;
  name?: string;
  bio?: string;
  avatar?: string;
}

// Events (what happened):
type UserEvent =
  | { type: "UserCreated";  payload: UserProfile }
  | { type: "UserUpdated";  payload: { id: UserId; changes: Partial<UserProfile> } }
  | { type: "UserDeleted";  payload: { id: UserId; deletedAt: Date } }
  | { type: "UserLoggedIn"; payload: { id: UserId; at: Date; ip: string } };

// Repository interface:
interface UserRepository {
  findById(id: UserId): Promise<UserProfile | null>;
  findByEmail(email: Email): Promise<UserProfile | null>;
  save(user: UserProfile): Promise<UserProfile>;
  delete(id: UserId): Promise<void>;
  findAll(options?: {
    skip?: number;
    take?: number;
    where?: Partial<Pick<UserProfile, "name">>;
    orderBy?: keyof UserProfile;
  }): Promise<{ items: UserProfile[]; total: number }>;
}

// Service:
class UserService {
  constructor(
    private repo: UserRepository,
    private hasher: { hash(pw: string): Promise<HashedPassword> },
    private eventBus: { emit(event: UserEvent): void }
  ) {}

  async createUser(cmd: CreateUserCommand): Promise<UserProfile> {
    const email = createEmail(cmd.email);

    const existing = await this.repo.findByEmail(email);
    if (existing) throw new Error("Email already in use");

    const user: UserProfile = {
      id: createUserId(crypto.randomUUID()),
      email,
      name: cmd.name.trim(),
      bio: null,
      avatar: null,
      createdAt: new Date(),
      updatedAt: new Date(),
    };

    const saved = await this.repo.save(user);
    this.eventBus.emit({ type: "UserCreated", payload: saved });
    return saved;
  }
}
```

---

## 🧪 6. Hands-on Practice Projects

---

### 🟢 Beginner Project: Typed Configuration System

**Goal:** Build a fully type-safe configuration loader that validates structure.
**Estimated Time:** 1-2 hours

```typescript
// config.ts — Type-safe configuration with validation

type LogLevel = "debug" | "info" | "warn" | "error";
type Environment = "development" | "production" | "test";

interface DatabaseConfig {
  host: string;
  port: number;
  name: string;
  username: string;
  password: string;
  ssl: boolean;
  maxConnections: number;
}

interface ServerConfig {
  host: string;
  port: number;
  corsOrigins: string[];
  rateLimit: { windowMs: number; max: number };
}

interface AppConfig {
  env: Environment;
  logLevel: LogLevel;
  server: ServerConfig;
  database: DatabaseConfig;
  apiKeys: Record<string, string>;
  features: Record<string, boolean>;
}

// Validation result:
type ValidationResult<T> =
  | { valid: true;  value: T }
  | { valid: false; errors: string[] };

// Type-safe config builder:
class ConfigBuilder {
  private errors: string[] = [];

  private validatePort(value: unknown, field: string): number {
    const port = Number(value);
    if (isNaN(port) || port < 1 || port > 65535) {
      this.errors.push(`${field} must be a valid port (1-65535)`);
      return 0;
    }
    return port;
  }

  private requireString(value: unknown, field: string): string {
    if (typeof value !== "string" || value.trim().length === 0) {
      this.errors.push(`${field} is required and must be a non-empty string`);
      return "";
    }
    return value.trim();
  }

  private requireEnum<T extends string>(
    value: unknown,
    field: string,
    values: readonly T[]
  ): T {
    if (!values.includes(value as T)) {
      this.errors.push(`${field} must be one of: ${values.join(", ")}`);
      return values[0];
    }
    return value as T;
  }

  build(raw: Record<string, unknown>): ValidationResult<AppConfig> {
    const env = this.requireEnum(
      raw.NODE_ENV ?? "development",
      "NODE_ENV",
      ["development", "production", "test"] as const
    );

    const config: AppConfig = {
      env,
      logLevel: this.requireEnum(
        raw.LOG_LEVEL ?? "info",
        "LOG_LEVEL",
        ["debug", "info", "warn", "error"] as const
      ),
      server: {
        host:        this.requireString(raw.SERVER_HOST ?? "localhost", "SERVER_HOST"),
        port:        this.validatePort(raw.SERVER_PORT ?? 3000, "SERVER_PORT"),
        corsOrigins: String(raw.CORS_ORIGINS ?? "").split(",").filter(Boolean),
        rateLimit: {
          windowMs: Number(raw.RATE_LIMIT_WINDOW_MS ?? 60000),
          max:      Number(raw.RATE_LIMIT_MAX ?? 100),
        },
      },
      database: {
        host:           this.requireString(raw.DB_HOST ?? "localhost", "DB_HOST"),
        port:           this.validatePort(raw.DB_PORT ?? 5432, "DB_PORT"),
        name:           this.requireString(raw.DB_NAME, "DB_NAME"),
        username:       this.requireString(raw.DB_USER, "DB_USER"),
        password:       this.requireString(raw.DB_PASSWORD, "DB_PASSWORD"),
        ssl:            raw.DB_SSL === "true",
        maxConnections: Number(raw.DB_MAX_CONNECTIONS ?? 10),
      },
      apiKeys: {},
      features: {},
    };

    if (this.errors.length > 0) {
      return { valid: false, errors: this.errors };
    }
    return { valid: true, value: config };
  }
}

// Usage:
const result = new ConfigBuilder().build(process.env as Record<string, unknown>);

if (!result.valid) {
  console.error("Configuration errors:\n", result.errors.join("\n"));
  process.exit(1);
}

// config is fully typed!
const config: AppConfig = result.value;
console.log(`Server starting on ${config.server.host}:${config.server.port}`);
```

---

### 🔵 Intermediate Project: Type-Safe Event Emitter

```typescript
// event-emitter.ts — Fully typed event system

// Define your events and their payloads:
interface AppEvents {
  "user:created":   { user: User; timestamp: Date };
  "user:updated":   { userId: string; changes: Partial<User>; by: string };
  "user:deleted":   { userId: string; deletedAt: Date };
  "order:placed":   { orderId: string; userId: string; total: number; items: OrderItem[] };
  "payment:success":{ paymentId: string; amount: number; currency: string };
  "payment:failed": { paymentId: string; reason: string; retryable: boolean };
  "error":          { message: string; code: string; stack?: string };
}

// Type extraction helpers:
type EventName = keyof AppEvents;
type EventPayload<E extends EventName> = AppEvents[E];
type EventListener<E extends EventName> = (payload: EventPayload<E>) => void | Promise<void>;

class TypedEventEmitter<Events extends Record<string, unknown>> {
  private listeners = new Map<keyof Events, Set<Function>>();
  private onceListeners = new Map<keyof Events, Set<Function>>();

  on<E extends keyof Events>(
    event: E,
    listener: (payload: Events[E]) => void | Promise<void>
  ): () => void {  // Returns unsubscribe function
    if (!this.listeners.has(event)) {
      this.listeners.set(event, new Set());
    }
    this.listeners.get(event)!.add(listener);

    // Return unsubscribe:
    return () => this.off(event, listener);
  }

  once<E extends keyof Events>(
    event: E,
    listener: (payload: Events[E]) => void | Promise<void>
  ): void {
    if (!this.onceListeners.has(event)) {
      this.onceListeners.set(event, new Set());
    }
    this.onceListeners.get(event)!.add(listener);
  }

  off<E extends keyof Events>(
    event: E,
    listener: (payload: Events[E]) => void | Promise<void>
  ): void {
    this.listeners.get(event)?.delete(listener);
  }

  async emit<E extends keyof Events>(event: E, payload: Events[E]): Promise<void> {
    const regular = this.listeners.get(event);
    const once    = this.onceListeners.get(event);

    const promises: Promise<void>[] = [];

    regular?.forEach(listener => {
      const result = listener(payload);
      if (result instanceof Promise) promises.push(result);
    });

    once?.forEach(listener => {
      const result = listener(payload);
      if (result instanceof Promise) promises.push(result);
    });
    this.onceListeners.delete(event);  // Remove after firing

    await Promise.all(promises);
  }

  listenerCount<E extends keyof Events>(event: E): number {
    return (this.listeners.get(event)?.size ?? 0) +
           (this.onceListeners.get(event)?.size ?? 0);
  }

  removeAllListeners<E extends keyof Events>(event?: E): void {
    if (event) {
      this.listeners.delete(event);
      this.onceListeners.delete(event);
    } else {
      this.listeners.clear();
      this.onceListeners.clear();
    }
  }
}

// Usage — fully typed!
const emitter = new TypedEventEmitter<AppEvents>();

// ✅ TypeScript knows the payload shape:
const unsubscribe = emitter.on("user:created", ({ user, timestamp }) => {
  console.log(`User ${user.name} created at ${timestamp.toISOString()}`);
});

emitter.on("payment:failed", async ({ paymentId, reason, retryable }) => {
  if (retryable) {
    await retryPayment(paymentId);
  } else {
    await notifyFailure(paymentId, reason);
  }
});

// Emit with full type safety:
await emitter.emit("user:created", {
  user: { id: 1, name: "Aryan", email: "a@ex.com" },
  timestamp: new Date(),
});

// ❌ TypeScript catches wrong payload shape:
// await emitter.emit("user:created", { wrongField: true }); // Error!

// Cleanup:
unsubscribe();  // Remove the first listener
```

---

### 🔴 Advanced Project: Type-Safe ORM Query Builder

```typescript
// query-builder.ts — A simplified type-safe query builder

type WhereOperator = "eq" | "ne" | "gt" | "gte" | "lt" | "lte" | "like" | "in" | "notIn";

type WhereClause<T> = {
  [K in keyof T]?: T[K] extends string | number | boolean | Date
    ? T[K] | { op: WhereOperator; value: T[K] | T[K][] }
    : never;
};

type OrderByClause<T> = {
  [K in keyof T]?: "asc" | "desc";
};

type SelectClause<T, K extends keyof T = keyof T> = K[];

interface QueryOptions<T, K extends keyof T = keyof T> {
  select?: SelectClause<T, K>;
  where?: WhereClause<T>;
  orderBy?: OrderByClause<T>;
  skip?: number;
  take?: number;
  include?: Partial<Record<string, boolean>>;
}

class QueryBuilder<T extends Record<string, unknown>> {
  private query: QueryOptions<T> = {};
  private tableName: string;

  constructor(tableName: string) {
    this.tableName = tableName;
  }

  select<K extends keyof T>(...fields: K[]): QueryBuilder<Pick<T, K>> {
    this.query.select = fields as any;
    return this as unknown as QueryBuilder<Pick<T, K>>;
  }

  where(conditions: WhereClause<T>): this {
    this.query.where = { ...this.query.where, ...conditions };
    return this;
  }

  orderBy(clause: OrderByClause<T>): this {
    this.query.orderBy = clause;
    return this;
  }

  skip(n: number): this {
    this.query.skip = n;
    return this;
  }

  take(n: number): this {
    this.query.take = n;
    return this;
  }

  toSQL(): string {
    let sql = `SELECT `;
    sql += this.query.select?.length
      ? this.query.select.join(", ")
      : "*";
    sql += ` FROM ${this.tableName}`;

    if (this.query.where && Object.keys(this.query.where).length > 0) {
      const conditions = Object.entries(this.query.where).map(([key, val]) => {
        if (typeof val === "object" && val !== null && "op" in val) {
          const { op, value } = val as { op: WhereOperator; value: unknown };
          const opMap: Record<WhereOperator, string> = {
            eq: "=", ne: "!=", gt: ">", gte: ">=", lt: "<", lte: "<=",
            like: "LIKE", in: "IN", notIn: "NOT IN",
          };
          if (op === "in" || op === "notIn") {
            return `${key} ${opMap[op]} (${(value as unknown[]).map(v => `'${v}'`).join(", ")})`;
          }
          return `${key} ${opMap[op]} '${value}'`;
        }
        return `${key} = '${val}'`;
      });
      sql += ` WHERE ${conditions.join(" AND ")}`;
    }

    if (this.query.orderBy) {
      const orders = Object.entries(this.query.orderBy)
        .map(([k, v]) => `${k} ${v!.toUpperCase()}`);
      sql += ` ORDER BY ${orders.join(", ")}`;
    }

    if (this.query.take) sql += ` LIMIT ${this.query.take}`;
    if (this.query.skip) sql += ` OFFSET ${this.query.skip}`;

    return sql;
  }
}

// Usage — fully type-safe!
interface Post {
  id: number;
  title: string;
  content: string;
  authorId: number;
  published: boolean;
  createdAt: Date;
  views: number;
}

const query = new QueryBuilder<Post>("posts")
  .select("id", "title", "authorId", "published")  // Only valid Post keys!
  .where({
    published: true,
    views: { op: "gt", value: 100 },
    authorId: { op: "in", value: [1, 2, 3] },
  })
  .orderBy({ views: "desc", createdAt: "asc" })
  .skip(0)
  .take(10);

console.log(query.toSQL());
// SELECT id, title, authorId, published FROM posts
// WHERE published = 'true' AND views > '100' AND authorId IN ('1', '2', '3')
// ORDER BY views DESC, createdAt ASC LIMIT 10 OFFSET 0
```

🔥 **Challenge:** Add a `join<J>(table: string, on: string)` method and `include` that automatically merges types from the joined table into the result type.

---

## ⚠️ 7. Common Mistakes

---

### ❌ Mistake 1: Using `any` Instead of `unknown`

```typescript
// ❌ WRONG — any disables ALL type checking:
function parseData(input: any): any {
  return JSON.parse(input);
}
const result = parseData('{"name": "Aryan"}');
result.nonExistent.deeply.nested;  // No error! Silent runtime crash.

// ✅ RIGHT — unknown forces you to narrow before using:
function parseData2(input: unknown): unknown {
  if (typeof input !== "string") throw new Error("Expected string input");
  return JSON.parse(input);
}

// Or with a type guard:
function safeParse<T>(input: string, guard: (v: unknown) => v is T): T | null {
  try {
    const parsed = JSON.parse(input);
    return guard(parsed) ? parsed : null;
  } catch {
    return null;
  }
}
```

---

### ❌ Mistake 2: Non-Null Assertion Operator Abuse

```typescript
// ❌ WRONG — using ! to silence errors without actual safety:
function getUser(id: number): User | undefined {
  return users.find(u => u.id === id);
}

const user = getUser(999)!;   // Runtime crash if user is undefined!
console.log(user.name);       // 💥 TypeError: Cannot read property 'name' of undefined

// ✅ RIGHT — actually check for null/undefined:
const user2 = getUser(999);
if (!user2) {
  throw new Error(`User ${999} not found`);
}
console.log(user2.name);  // Safe!

// Or use optional chaining:
const name = getUser(999)?.name ?? "Unknown";
```

---

### ❌ Mistake 3: Weak Object Types

```typescript
// ❌ WRONG — {} accepts almost everything (any non-null value):
function process(value: {}): void {
  // value could be ANYTHING: string, number, object, array, Date...
}

// ❌ WRONG — object is only slightly better:
function process2(value: object): void {
  // Rejects primitives but accepts arrays, functions, dates...
}

// ✅ RIGHT — be specific about what you expect:
function processUser(value: User): void { /* ... */ }
function processAny(value: unknown): void {
  // Use type guards to narrow
}
function processRecord(value: Record<string, unknown>): void { /* ... */ }
```

---

### ❌ Mistake 4: Type Assertion Instead of Type Guard

```typescript
// ❌ WRONG — type assertion bypasses safety checks:
const data = JSON.parse(jsonString) as User;
// What if the JSON is malformed? Runtime crash later.
data.name.toUpperCase();  // 💥 If data.name is undefined

// ✅ RIGHT — validate before asserting:
function parseUser(json: string): User | null {
  try {
    const data: unknown = JSON.parse(json);
    if (!isUser(data)) return null;
    return data;  // TypeScript knows it's User here!
  } catch {
    return null;
  }
}

function isUser(value: unknown): value is User {
  return (
    typeof value === "object" &&
    value !== null &&
    "id" in value && typeof (value as any).id === "number" &&
    "name" in value && typeof (value as any).name === "string" &&
    "email" in value && typeof (value as any).email === "string"
  );
}
```

---

### ❌ Mistake 5: Ignoring Strictness Options

```typescript
// ❌ WRONG — without strict mode, you miss important errors:
// tsconfig.json: { "strict": false }

function greet(name) {           // name is implicitly any!
  return name.toUpperCase();     // No error if name is number at runtime!
}

let value: string | null = null;
value.toUpperCase();             // No error! But crashes at runtime.

// ✅ RIGHT — always enable strict mode:
// tsconfig.json: { "strict": true }
// This enables: strictNullChecks, noImplicitAny, strictFunctionTypes,
//               strictPropertyInitialization, and more.

function greet2(name: string): string {   // Must annotate
  return name.toUpperCase();
}

let value2: string | null = null;
// value2.toUpperCase();                  // ❌ Error! Possible null
if (value2 !== null) value2.toUpperCase(); // ✅
```

---

### ❌ Mistake 6: Incorrect Generic Constraint Usage

```typescript
// ❌ WRONG — T extends object loses specific type info:
function clone<T extends object>(value: T): object {
  return { ...value };   // Returns object, not T!
}
const user = { name: "Aryan", age: 17 };
const cloned = clone(user);
// cloned.name   // ❌ Error — TypeScript only knows it's "object"

// ✅ RIGHT — return T to preserve the specific type:
function clone2<T extends object>(value: T): T {
  return { ...value } as T;
}
const cloned2 = clone2(user);
cloned2.name;   // ✅ string
cloned2.age;    // ✅ number
```

---

### ❌ Mistake 7: Enum Pitfalls

```typescript
// ❌ WRONG — numeric enums have surprising behavior:
enum Direction {
  Up,     // 0
  Down,   // 1
  Left,   // 2
  Right,  // 3
}

function move(direction: Direction) {}
move(Direction.Up);  // ✅
move(0);             // ✅ (surprise! any number is accepted for numeric enums)
move(999);           // ✅ (TypeScript accepts this! Silent bug.)

// ✅ BETTER — const object + union type:
const Direction2 = {
  Up:    "UP",
  Down:  "DOWN",
  Left:  "LEFT",
  Right: "RIGHT",
} as const;

type Direction2 = typeof Direction2[keyof typeof Direction2];
// "UP" | "DOWN" | "LEFT" | "RIGHT"

function move2(direction: Direction2) {}
move2(Direction2.Up);  // ✅
move2("UP");           // ✅
// move2("DIAGONAL");  // ❌ Error — not in the union!
// move2(0);           // ❌ Error — not a string!

// ✅ OR — string enum (safe):
enum Status {
  Active   = "ACTIVE",
  Inactive = "INACTIVE",
  Pending  = "PENDING",
}
// Status members only assignable to Status, not arbitrary strings
```

---

## 🔥 8. Pro Tips & Hidden Tricks

---

### 💎 Tip 1: `satisfies` Operator — Best of Both Worlds

```typescript
// TypeScript 4.9+ satisfies operator
// Validates type without widening — keeps narrow inference!

// Problem with explicit annotation:
const palette: Record<string, string | number[]> = {
  red:   [255, 0, 0],
  green: "#00ff00",
  blue:  [0, 0, 255],
};
// palette.red is now string | number[] — lost the specific type!

// Problem with no annotation:
const palette2 = {
  red:   [255, 0, 0],
  green: "#00ff00",
  blue:  [0, 0, 255],
};
// Type is correct but palette2.notExist would be undefined — no error!

// ✅ satisfies — validates AND preserves narrow types:
const palette3 = {
  red:   [255, 0, 0],
  green: "#00ff00",
  blue:  [0, 0, 255],
} satisfies Record<string, string | number[]>;

palette3.red.at(0);      // ✅ TypeScript knows red is number[] (not string | number[])
palette3.green.toUpperCase(); // ✅ TypeScript knows green is string

// Another example:
const config = {
  host: "localhost",
  port: 3000,
  debug: true,
} satisfies Partial<AppConfig["server"]>;
// All keys validated against AppConfig["server"] but types stay narrow!
```

---

### 💎 Tip 2: `as const` — Literal Type Preservation

```typescript
// Without as const — widened types:
const config1 = {
  host: "localhost",  // type: string  (widened)
  port: 3000,         // type: number  (widened)
};

// With as const — literal types:
const config2 = {
  host: "localhost",  // type: "localhost"  (literal!)
  port: 3000,         // type: 3000         (literal!)
  roles: ["admin", "user"],  // type: readonly ["admin", "user"]
} as const;

// Very powerful for union extraction:
const HTTP_METHODS = ["GET", "POST", "PUT", "PATCH", "DELETE"] as const;
type HttpMethod = typeof HTTP_METHODS[number];
// "GET" | "POST" | "PUT" | "PATCH" | "DELETE"

const COLORS = {
  red:   "#FF0000",
  green: "#00FF00",
  blue:  "#0000FF",
} as const;
type Color = typeof COLORS[keyof typeof COLORS];
// "#FF0000" | "#00FF00" | "#0000FF"

// Function that accepts only valid route paths:
const ROUTES = {
  home:    "/",
  about:   "/about",
  blog:    "/blog",
  contact: "/contact",
} as const;

type Route = typeof ROUTES[keyof typeof ROUTES];
// "/" | "/about" | "/blog" | "/contact"

function navigate(path: Route): void {
  window.location.href = path;
}

navigate(ROUTES.home);    // ✅
navigate("/");            // ✅
// navigate("/unknown");  // ❌ Error!
```

---

### 💎 Tip 3: Discriminated Unions with Exhaustiveness Checking

```typescript
// Build bulletproof discriminated unions with compile-time exhaustiveness:

type ApiState<T> =
  | { status: "idle" }
  | { status: "loading" }
  | { status: "success"; data: T }
  | { status: "error"; error: Error; retryCount: number };

// Exhaustive switch — TypeScript will error if you add a new status and forget to handle it!
function renderState<T>(state: ApiState<T>): string {
  switch (state.status) {
    case "idle":    return "Not started";
    case "loading": return "Loading...";
    case "success": return `Data: ${JSON.stringify(state.data)}`;
    case "error":   return `Error: ${state.error.message} (retry: ${state.retryCount})`;
    default: {
      // This line catches missing cases AT COMPILE TIME:
      const exhaustive: never = state;  // ❌ Error if state isn't never
      return exhaustive;
    }
  }
}

// Now if you add: | { status: "cancelled" }
// The default branch will FAIL TO COMPILE — reminding you to handle it!

// Even better — throw at runtime too:
function assertNever(value: never, message?: string): never {
  throw new Error(message ?? `Unhandled case: ${JSON.stringify(value)}`);
}

function renderState2<T>(state: ApiState<T>): string {
  switch (state.status) {
    case "idle":    return "Not started";
    case "loading": return "Loading...";
    case "success": return `Data: ${JSON.stringify(state.data)}`;
    case "error":   return `Error: ${state.error.message}`;
    default:        return assertNever(state);  // Compile + runtime safety!
  }
}
```

---

### 💎 Tip 4: Recursive Types — Self-Referencing Structures

```typescript
// JSON-compatible type:
type Json =
  | string
  | number
  | boolean
  | null
  | Json[]
  | { [key: string]: Json };

// File system tree:
interface FileSystemNode {
  name: string;
  type: "file" | "directory";
  size?: number;            // Only for files
  children?: FileSystemNode[]; // Only for directories
}

// Recursive comment thread:
interface Comment {
  id: number;
  content: string;
  author: User;
  createdAt: Date;
  replies: Comment[];     // Self-reference!
  parent: Comment | null;
}

// Deeply nested config:
interface MenuItem {
  label: string;
  href?: string;
  icon?: string;
  children?: MenuItem[];  // Recursive menu
  disabled?: boolean;
}

// Deep readonly (recursive):
type DeepReadonly<T> = {
  readonly [P in keyof T]: T[P] extends object
    ? T[P] extends Function
      ? T[P]
      : DeepReadonly<T[P]>
    : T[P];
};

// Deep partial (recursive):
type DeepPartial<T> = {
  [P in keyof T]?: T[P] extends object
    ? T[P] extends Function
      ? T[P]
      : DeepPartial<T[P]>
    : T[P];
};
```

---

### 💎 Tip 5: Declaration Merging — Extending Built-in Types

```typescript
// Extend Express Request with custom properties:
// types/express.d.ts

declare global {
  namespace Express {
    interface Request {
      user?: User;
      session: {
        id: string;
        data: Record<string, unknown>;
      };
      requestId: string;
    }
  }
}

// Now in route handlers:
app.get("/profile", (req, res) => {
  const user = req.user;    // Fully typed!
  const id = req.requestId; // Fully typed!
});

// Extend Window:
interface Window {
  analytics: {
    track(event: string, properties?: Record<string, unknown>): void;
    identify(userId: string, traits?: Record<string, unknown>): void;
  };
  __REACT_QUERY_STATE__?: unknown;
}

// Extend NodeJS process.env:
declare namespace NodeJS {
  interface ProcessEnv {
    NODE_ENV: "development" | "production" | "test";
    DATABASE_URL: string;
    JWT_SECRET: string;
    PORT?: string;
    API_KEY?: string;
  }
}

// Now process.env.NODE_ENV is typed!
if (process.env.NODE_ENV === "production") {
  // TypeScript knows this is valid
}
```

---

### 💎 Tip 6: `infer` in Complex Type Extraction

```typescript
// Extract deeply nested types:

// Get the type of Promise resolution:
type PromiseValue<T> = T extends Promise<infer V> ? PromiseValue<V> : T;

// Get the type of array elements:
type Unpack<T> = T extends Array<infer U> ? U : T;

// Get argument types of ANY function:
type Args<F> = F extends (...args: infer A) => any ? A : never;

// Get the last element of a tuple:
type Last<T extends any[]> = T extends [...any[], infer L] ? L : never;
type L = Last<[string, number, boolean]>;  // boolean

// Get all but last element:
type Init<T extends any[]> = T extends [...infer I, any] ? I : never;
type I = Init<[string, number, boolean]>;  // [string, number]

// Extract generic parameter:
type ExtractGeneric<T> =
  T extends Array<infer U>   ? U :
  T extends Promise<infer U> ? U :
  T extends Set<infer U>     ? U :
  T extends Map<any, infer U>? U :
  never;

type G1 = ExtractGeneric<string[]>;           // string
type G2 = ExtractGeneric<Promise<User>>;      // User
type G3 = ExtractGeneric<Set<number>>;        // number
type G4 = ExtractGeneric<Map<string, Date>>; // Date
```

---

### 🛠️ Recommended Tools & Resources

| Tool / Resource             | What It's For                                                  | Notes                                           |
|-----------------------------|----------------------------------------------------------------|-------------------------------------------------|
| `tsc` — TypeScript compiler | Compile and type-check your code                               | `npm install typescript --save-dev`             |
| `ts-node`                   | Run TypeScript files directly without compiling                | `npm install ts-node -g`                        |
| `tsx`                       | Faster ts-node alternative using esbuild                       | Best for development                            |
| TypeScript ESLint           | Lint TypeScript code — catch patterns compiler misses          | `@typescript-eslint/eslint-plugin`              |
| Zod                         | Runtime type validation — validates external data              | The perfect companion for TypeScript            |
| `type-fest`                 | Collection of advanced utility types                           | GitHub: sindresorhus/type-fest                  |
| `ts-reset`                  | Makes TypeScript's built-in types stricter                     | GitHub: total-typescript/ts-reset               |
| TypeScript Playground       | Test types in browser instantly                                | typescriptlang.org/play                         |
| Matt Pocock's Total TS      | Best TypeScript learning resource for advanced patterns        | totaltypescript.com                             |
| TypeScript Deep Dive        | Free online book — comprehensive reference                     | basarat.gitbook.io/typescript                   |

---

## 🚀 9. Advanced Concepts (Expert Level)

---

### Advanced Concept 1: Higher-Kinded Types (Simulated)

```typescript
// TypeScript doesn't natively support Higher-Kinded Types (HKT)
// but we can simulate them with clever type encoding

// The HKT encoding using type-level dictionary:
interface HKT {
  readonly _A?: unknown;
  readonly type?: unknown;
}

// URI registry — extend this interface to register types:
interface URItoHKT<A> {
  Array:   Array<A>;
  Maybe:   Maybe<A>;
  Result:  Result2<A>;
  Promise: Promise<A>;
}

type URIS = keyof URItoHKT<unknown>;
type Kind<F extends URIS, A> = URItoHKT<A>[F];

// Functor typeclass:
interface Functor<F extends URIS> {
  map<A, B>(fa: Kind<F, A>, f: (a: A) => B): Kind<F, B>;
}

// Implement Functor for Array:
const ArrayFunctor: Functor<"Array"> = {
  map: (fa, f) => fa.map(f),
};

// Now write generic code that works for ANY Functor:
function doubleAll<F extends URIS>(
  functor: Functor<F>,
  container: Kind<F, number>
): Kind<F, number> {
  return functor.map(container, (n) => n * 2);
}

// Works for any functor!
doubleAll(ArrayFunctor, [1, 2, 3]);    // [2, 4, 6]
```

---

### Advanced Concept 2: The Builder Pattern with Method Chaining Types

```typescript
// Fluent builder where each method call updates the type!

type BuilderState = {
  url: string;
  method: string;
  headers: Record<string, string>;
  body?: unknown;
  timeout?: number;
};

type HasUrl = BuilderState & { url: string };
type HasMethod = HasUrl & { method: string };

class RequestBuilder<State extends Partial<BuilderState> = {}> {
  private state: State;

  private constructor(state: State) {
    this.state = state;
  }

  static create(): RequestBuilder<{}> {
    return new RequestBuilder({});
  }

  url<U extends string>(url: U): RequestBuilder<State & { url: U }> {
    return new RequestBuilder({ ...this.state, url } as any);
  }

  method<M extends "GET" | "POST" | "PUT" | "PATCH" | "DELETE">(
    method: M
  ): RequestBuilder<State & { method: M }> {
    return new RequestBuilder({ ...this.state, method } as any);
  }

  header(key: string, value: string): RequestBuilder<State & { headers: Record<string, string> }> {
    return new RequestBuilder({
      ...this.state,
      headers: { ...((this.state as any).headers ?? {}), [key]: value },
    } as any);
  }

  body<B>(body: B): RequestBuilder<State & { body: B }> {
    return new RequestBuilder({ ...this.state, body } as any);
  }

  timeout(ms: number): RequestBuilder<State & { timeout: number }> {
    return new RequestBuilder({ ...this.state, timeout: ms } as any);
  }

  // Only available when url AND method are set:
  build(this: RequestBuilder<State & { url: string; method: string }>): BuilderState {
    return this.state as unknown as BuilderState;
  }
}

// Usage:
const request = RequestBuilder.create()
  .url("https://api.example.com/users")
  .method("POST")
  .header("Content-Type", "application/json")
  .body({ name: "Aryan" })
  .timeout(5000)
  .build();  // ✅ Works — url and method are set

// RequestBuilder.create().build();  // ❌ TypeScript Error! url and method not set
// RequestBuilder.create().url("/api").build();  // ❌ Error! method not set
```

---

### Advanced Concept 3: `const` Type Parameters (TypeScript 5.0)

```typescript
// TypeScript 5.0: const type parameter — infers literal types automatically!

// Without const — widened inference:
function makeArray<T>(items: T[]): T[] {
  return items;
}
const arr1 = makeArray(["a", "b", "c"]);
// Type: string[]  — widened!

// With const — literal inference:
function makeArrayConst<const T>(items: T[]): T[] {
  return items;
}
const arr2 = makeArrayConst(["a", "b", "c"]);
// Type: readonly ["a", "b", "c"]  — literal!

// Very useful for type-safe route definitions:
function createRoutes<const T extends Record<string, string>>(routes: T): T {
  return routes;
}

const routes = createRoutes({
  home:    "/",
  about:   "/about",
  profile: "/users/:id",
});

type Route = typeof routes[keyof typeof routes];
// "/" | "/about" | "/users/:id"  — literal types preserved!
```

---

### Advanced Concept 4: Variance — Covariance vs Contravariance

```typescript
/*
  Variance describes how type compatibility flows when types are nested.

  COVARIANT (T → U means Container<T> → Container<U>):
  - "Can substitute more specific types"
  - Return types are covariant

  CONTRAVARIANT (T → U means Container<U> → Container<T> — reversed!):
  - "Must accept more general types"
  - Function parameter types are contravariant

  INVARIANT (neither direction):
  - Mutable containers
*/

// Covariance example:
interface Animal { name: string }
interface Dog extends Animal { bark(): void }

type Producer<T> = () => T;
const dogProducer: Producer<Dog> = () => ({ name: "Rex", bark() {} });
const animalProducer: Producer<Animal> = dogProducer;  // ✅ Covariant!
// Producer<Dog> is assignable to Producer<Animal>

// Contravariance example:
type Consumer<T> = (value: T) => void;
const animalConsumer: Consumer<Animal> = (a) => console.log(a.name);
const dogConsumer: Consumer<Dog> = animalConsumer;  // ✅ Contravariant!
// Consumer<Animal> is assignable to Consumer<Dog>
// (A handler for animals can handle any dog)

// Invariance — mutable containers:
// let dogs: Dog[] = [];
// let animals: Animal[] = dogs;   // ❌ TypeScript rejects (for good reason!)
// animals.push({ name: "Cat" });  // Would corrupt the dogs array!

// in/out variance annotations (TypeScript 4.7+):
interface Covariant<out T> {     // T only in output positions
  value(): T;
}

interface Contravariant<in T> {  // T only in input positions
  consume(value: T): void;
}

interface Invariant<in out T> {  // T in both
  get(): T;
  set(value: T): void;
}
```

---

### ⚡ TypeScript Performance & Configuration

```json
// tsconfig.json — Production-ready configuration:
{
  "compilerOptions": {
    // Strictness (enable ALL of these):
    "strict": true,                    // Enable all strict checks
    "noUncheckedIndexedAccess": true,  // arr[0] returns T | undefined
    "exactOptionalPropertyTypes": true,// { a?: string } ≠ { a: string | undefined }
    "noImplicitOverride": true,        // Must use 'override' keyword
    "noPropertyAccessFromIndexSignature": true,

    // Output:
    "target": "ES2022",               // JS version to emit
    "module": "NodeNext",             // Module system
    "moduleResolution": "NodeNext",
    "outDir": "./dist",
    "declaration": true,              // Emit .d.ts files
    "declarationMap": true,           // Source maps for .d.ts
    "sourceMap": true,

    // Performance:
    "incremental": true,              // Cache compilation state
    "tsBuildInfoFile": ".tsbuildinfo",
    "skipLibCheck": true,             // Skip checking .d.ts files in node_modules

    // Extras:
    "paths": {
      "@/*": ["./src/*"]             // Import aliases
    },
    "lib": ["ES2022", "DOM", "DOM.Iterable"],
    "jsx": "react-jsx"               // For React projects
  },
  "include": ["src/**/*"],
  "exclude": ["node_modules", "dist"]
}
```

| Optimization                  | Impact   | Configuration                                 |
|-------------------------------|----------|-----------------------------------------------|
| `incremental: true`           | High     | Cache between builds — 10x faster rebuilds    |
| `skipLibCheck: true`          | High     | Skip checking node_modules .d.ts files        |
| `isolatedModules: true`       | Medium   | Enable with transpilers (esbuild, SWC)        |
| Project references            | High     | Split monorepos into independently-built pkgs |
| `tsBuildInfoFile`             | Medium   | Explicit cache file location                  |
| Avoid deep type recursion     | High     | Recursive types > 100 levels cause slowdown   |
| Use `interface` over `type`   | Low      | Interfaces cache better than complex types    |

---

## 💀 10. 0.01% Hidden Secrets — Ultra Elite

---

### 🔮 Secret 1: The `infer` Trick for Spread Argument Types

```typescript
// Extract types from complex generic signatures using infer:

// Get the last parameter of any function:
type LastParam<T extends (...args: any[]) => any> =
  T extends (...args: [...infer _, infer L]) => any ? L : never;

function test(a: string, b: number, c: boolean): void {}
type LP = LastParam<typeof test>;  // boolean

// Infer the callback type from addEventListener:
type EventListenerType<T extends keyof HTMLElementEventMap> =
  Parameters<HTMLElement["addEventListener"]>[1] extends
    EventListenerOrEventListenerObject ?
      (event: HTMLElementEventMap[T]) => void :
      never;

// Infer the type the function returns AFTER awaiting:
type UnwrappedReturn<T extends (...args: any[]) => any> =
  ReturnType<T> extends Promise<infer U> ? U : ReturnType<T>;

async function fetchUser(): Promise<User> { /* ... */ return {} as User; }
type FetchedUser = UnwrappedReturn<typeof fetchUser>;  // User (not Promise<User>!)
```

---

### 🔮 Secret 2: Phantom Types — Types That Don't Exist at Runtime

```typescript
// Phantom types encode information at the type level with zero runtime cost
// The type parameter exists ONLY in the type system — not in the actual value!

// Example: Type-safe unit system
type Quantity<Unit extends string> = number & { readonly __unit: Unit };

type Meters    = Quantity<"meters">;
type Kilograms = Quantity<"kilograms">;
type Seconds   = Quantity<"seconds">;
type MetersPerSecond = Quantity<"m/s">;

function meters(n: number): Meters {
  return n as Meters;
}
function kilograms(n: number): Kilograms {
  return n as Kilograms;
}

// ✅ Functions that only accept specific units:
function calculateSpeed(distance: Meters, time: Seconds): MetersPerSecond {
  return (distance / time) as MetersPerSecond;
}

const d = meters(100);
const t = 10 as Seconds;
const speed = calculateSpeed(d, t);  // ✅

// ❌ These would cause compile errors:
// calculateSpeed(100 as Kilograms, t);   // Wrong unit!
// calculateSpeed(d, 100 as Meters);      // Wrong unit!

// Example: Database query result tags
type Validated<T>   = T & { readonly __validated: true };
type Sanitized<T>   = T & { readonly __sanitized: true };
type Encrypted<T>   = T & { readonly __encrypted: true };

function validateInput(input: string): Validated<string> {
  if (input.includes("<script>")) throw new Error("Invalid input");
  return input as Validated<string>;
}

function sanitizeInput(input: Validated<string>): Sanitized<Validated<string>> {
  return input.replace(/[<>&]/g, "") as Sanitized<Validated<string>>;
}

// This function requires both validated AND sanitized input:
function storeInDatabase(data: Sanitized<Validated<string>>): void {
  // Safe to store!
}

const raw = getUserInput();
// storeInDatabase(raw);                     // ❌ Not validated or sanitized!
const validated = validateInput(raw);
// storeInDatabase(validated);               // ❌ Not sanitized!
const sanitized = sanitizeInput(validated);
storeInDatabase(sanitized);                  // ✅ Both validated AND sanitized!
```

---

### 🔮 Secret 3: Type-Level String Parsing with Template Literals

```typescript
// Parse URL patterns into typed parameter objects!

// Parse ":param" segments:
type ExtractRouteParams<T extends string> =
  T extends `${infer _Start}:${infer Param}/${infer Rest}`
    ? { [K in Param | keyof ExtractRouteParams<`/${Rest}`>]: string }
    : T extends `${infer _Start}:${infer Param}`
    ? { [K in Param]: string }
    : {};

type P1 = ExtractRouteParams<"/users/:userId">;
// { userId: string }

type P2 = ExtractRouteParams<"/users/:userId/posts/:postId">;
// { userId: string; postId: string }

type P3 = ExtractRouteParams<"/users/:userId/posts/:postId/comments/:commentId">;
// { userId: string; postId: string; commentId: string }

// Type-safe route handler factory:
function createHandler<Route extends string>(
  pattern: Route,
  handler: (params: ExtractRouteParams<Route>) => Response
): { pattern: Route; handler: typeof handler } {
  return { pattern, handler };
}

const userRoute = createHandler(
  "/users/:userId/posts/:postId",
  ({ userId, postId }) => {       // Params are typed!
    return new Response(`User: ${userId}, Post: ${postId}`);
  }
);
```

---

### 🔮 Secret 4: `NoInfer<T>` — Preventing Unwanted Type Inference (TypeScript 5.4)

```typescript
// TypeScript 5.4 added NoInfer<T>
// Prevents a type parameter from being inferred from a specific argument

// Problem — T is inferred from BOTH args, causing unexpected widening:
function createState<T>(initial: T, onchange: (val: T) => void): T {
  return initial;
}

// TypeScript infers T as string | number (union of both args):
const state = createState("hello", (val) => {
  val.toUpperCase(); // ❌ val is string | number — not just string!
});

// With NoInfer — T is only inferred from initial, not onchange:
function createState2<T>(initial: T, onChange: (val: NoInfer<T>) => void): T {
  return initial;
}

const state2 = createState2("hello", (val) => {
  val.toUpperCase(); // ✅ val is string — correct!
});

// createState2(42, (val) => val.toFixed(2)); // ✅ val is number
```

---

### 🔮 Secret 5: Recursive Type Tricks — Mutual Recursion

```typescript
// Types can be mutually recursive:

type JSONValue = JSONPrimitive | JSONArray | JSONObject;
type JSONPrimitive = string | number | boolean | null;
type JSONArray = JSONValue[];
type JSONObject = { [key: string]: JSONValue };

// Mutual recursion for expression trees:
type Expr =
  | { kind: "lit";   value: number }
  | { kind: "var";   name: string }
  | { kind: "add";   left: Expr; right: Expr }
  | { kind: "mul";   left: Expr; right: Expr }
  | { kind: "if";    cond: BoolExpr; then: Expr; else: Expr };

type BoolExpr =
  | { kind: "lit";  value: boolean }
  | { kind: "and";  left: BoolExpr; right: BoolExpr }
  | { kind: "not";  expr: BoolExpr }
  | { kind: "gt";   left: Expr; right: Expr }
  | { kind: "eq";   left: Expr; right: Expr };

// Type-safe evaluator:
function evalExpr(expr: Expr, env: Record<string, number>): number {
  switch (expr.kind) {
    case "lit":  return expr.value;
    case "var":  return env[expr.name] ?? 0;
    case "add":  return evalExpr(expr.left, env) + evalExpr(expr.right, env);
    case "mul":  return evalExpr(expr.left, env) * evalExpr(expr.right, env);
    case "if":   return evalBool(expr.cond, env)
                          ? evalExpr(expr.then, env)
                          : evalExpr(expr.else, env);
  }
}

function evalBool(expr: BoolExpr, env: Record<string, number>): boolean {
  switch (expr.kind) {
    case "lit":  return expr.value;
    case "and":  return evalBool(expr.left, env) && evalBool(expr.right, env);
    case "not":  return !evalBool(expr.expr, env);
    case "gt":   return evalExpr(expr.left, env) > evalExpr(expr.right, env);
    case "eq":   return evalExpr(expr.left, env) === evalExpr(expr.right, env);
  }
}
```

---

### 🔮 Secret 6: Opaque Types with Module Boundaries

```typescript
// Opaque.ts — types that LOOK like primitives but carry type identity

// Method 1 — Branded types (the most common approach):
declare const __brand: unique symbol;
type Brand<T, TBrand> = T & { readonly [__brand]: TBrand };

type UserId    = Brand<string, "UserId">;
type SessionId = Brand<string, "SessionId">;
type Token     = Brand<string, "Token">;

// Only these functions can create branded values:
export function toUserId(id: string): UserId {
  // Validate if needed
  return id as UserId;
}

export function toSessionId(id: string): SessionId {
  return id as SessionId;
}

// Now you CANNOT accidentally mix up IDs:
function lookupUser(userId: UserId): User { /* ... */ return {} as User; }
function destroySession(sessionId: SessionId): void { /* ... */ }

const userId    = toUserId("usr_123");
const sessionId = toSessionId("ses_456");

lookupUser(userId);        // ✅
destroySession(sessionId); // ✅

// lookupUser(sessionId);     // ❌ TypeScript Error!
// destroySession(userId);    // ❌ TypeScript Error!
// lookupUser("usr_123");     // ❌ TypeScript Error! (raw string not branded)
```

---

### 🔮 Secret 7: Type-Level Arithmetic (Limited but Possible)

```typescript
// TypeScript can do basic arithmetic at the TYPE level using tuple lengths!

type BuildTuple<L extends number, T extends unknown[] = []> =
  T["length"] extends L ? T : BuildTuple<L, [...T, unknown]>;

type Add<A extends number, B extends number> =
  [...BuildTuple<A>, ...BuildTuple<B>]["length"];

type Subtract<A extends number, B extends number> =
  BuildTuple<A> extends [...BuildTuple<B>, ...infer R]
    ? R["length"]
    : never;

// Test:
type Sum = Add<3, 5>;         // 8
type Diff = Subtract<10, 3>;  // 7

// Practical use: enforce array length at type level:
type FixedArray<T, N extends number, Acc extends T[] = []> =
  Acc["length"] extends N ? Acc : FixedArray<T, N, [...Acc, T]>;

// An array that MUST have exactly 3 elements:
type Triple<T> = FixedArray<T, 3>;

const rgb: Triple<number> = [255, 128, 0];     // ✅
// const bad: Triple<number> = [255, 128];       // ❌ Too short
// const bad2: Triple<number> = [255, 128, 0, 1]; // ❌ Too long
```

---

### 🔮 Secret 8: The `type` Modifier on Imports — Isolated Modules

```typescript
// TypeScript 3.8+ type-only imports — ONLY erased at compile time
// Essential for tools like esbuild, SWC, Babel that transpile per-file

// ❌ Value import: esbuild can't know if it's a type or value!
import { User, getUserById } from './user';

// ✅ Type import: guaranteed to be erased — no runtime cost, no confusion:
import type { User } from './user';
import { getUserById } from './user';

// Mix in a single import:
import { getUserById, type User, type UserRole } from './user';

// Type-only export:
export type { User, UserRole };

// Why it matters:
// 1. esbuild, SWC, Babel transpile each file independently
//    — they can't check if an import is used as a value or type
//    — import type guarantees it's erasable
// 2. Prevents circular dependency issues
// 3. Communicates intent — this is ONLY used for types
// 4. Slightly faster compilation

// `verbatimModuleSyntax` tsconfig option:
// Requires you to use import type for all type-only imports
// Great for enforcing clean module boundaries
```

---

### 🔮 Secret 9: Distributive vs Non-Distributive Conditional Types

```typescript
// The most subtle behavior in TypeScript's type system:

// DISTRIBUTIVE — happens when T is a "naked" type parameter:
type IsArray<T> = T extends any[] ? "yes" : "no";

type Result1 = IsArray<string[]>;          // "yes"
type Result2 = IsArray<string>;            // "no"
type Result3 = IsArray<string[] | string>; // "yes" | "no"  ← DISTRIBUTES over union!
// string[] | string → (string[] extends any[] ? "yes" : "no") | (string extends any[] ? "yes" : "no")
// → "yes" | "no"

// NON-DISTRIBUTIVE — wrap T in a tuple to prevent distribution:
type IsArrayND<T> = [T] extends [any[]] ? "yes" : "no";

type Result4 = IsArrayND<string[] | string>;
// [string[] | string] extends [any[]] ? "yes" : "no"
// → "no"  (string is not an array, so the whole union fails)

// Practical application — ToArray should distribute:
type ToArray<T> = T extends any ? T[] : never;
type A = ToArray<string | number>;  // string[] | number[]  (distributed — usually what you want!)

// But sometimes you DON'T want distribution:
type Wrap<T> = [T] extends [any] ? T[] : never;
type B = Wrap<string | number>;  // (string | number)[]  (not distributed)

// Checking "is this exactly never":
type IsNever<T> = [T] extends [never] ? true : false;
// Without []:  T extends never ? true : false  — never DISTRIBUTES to never!
type C = IsNever<never>;   // true  ✅ with [] wrapper
```

---

### 🔮 Secret 10: Module Augmentation — Extending Third-Party Libraries

```typescript
// Extend libraries you don't own — type-safe monkey patching!

// Extend Array prototype with a typed method:
declare global {
  interface Array<T> {
    groupBy<K extends string | number | symbol>(
      keyFn: (item: T) => K
    ): Record<K, T[]>;

    unique(): T[];
    unique<K>(keyFn: (item: T) => K): T[];

    first(): T | undefined;
    last(): T | undefined;
  }
}

// Implementation:
Array.prototype.groupBy = function(keyFn) {
  return this.reduce((acc, item) => {
    const key = keyFn(item);
    if (!acc[key]) acc[key] = [];
    acc[key].push(item);
    return acc;
  }, {});
};

// Now you get full type safety on your custom methods!
const users: User[] = [...];
const byCity = users.groupBy(u => u.city);
// Type: Record<string, User[]>

// Extend a library's types:
// node_modules/@types/express/index.d.ts — we can't edit this
// But we can augment it:

declare module "express-serve-static-core" {
  interface Request {
    user?: User;
    correlationId: string;
    startTime: number;
  }
}

// Now req.user is typed everywhere in your Express app!

// Augment a specific module's exported type:
declare module "zod" {
  interface ZodString {
    phoneNumber(): ZodString;  // Add custom validation method
  }
}
```

---

## 🗺️ 11. Complete Roadmap

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — FOUNDATION (Week 1-2)
├── Week 1: Basic types, type inference, interfaces vs type aliases,
│           arrays, tuples, optional & readonly, null safety
└── Week 2: Union types, intersection types, type narrowing (typeof, instanceof, in),
│           user-defined type guards, assertion functions
    └── Project: Type-safe config loader, typed API client

PHASE 2 — CORE TYPE SYSTEM (Week 3-5)
├── Week 3: Generics — basic, constrained, multiple, default; generic functions + classes
├── Week 4: All utility types (Partial, Required, Readonly, Record, Pick, Omit,
│           ReturnType, Parameters, Awaited, etc.) + composition
└── Week 5: Mapped types, template literal types, conditional types with infer
    └── Project: Type-safe event emitter, typed query builder

PHASE 3 — ADVANCED PATTERNS (Week 6-9)
├── Week 6: Classes — access modifiers, abstract, mixins, decorators (experimental)
├── Week 7: Module system — declaration merging, module augmentation, ambient declarations
├── Week 8: Advanced patterns — discriminated unions, exhaustiveness, phantom types,
│           branded types, builder pattern
└── Week 9: tsconfig mastery, project references, declaration files (.d.ts),
│           publishing typed packages to npm
    └── Project: Fully-typed domain model, shared npm package with types

PHASE 4 — EXPERT / 0.01% (Month 3-6)
├── Month 3: TypeScript compiler API — build custom lint rules, codemods, transformers
├── Month 4: Deep conditional types, recursive types, type-level computation,
│           variance annotations (in/out), NoInfer, satisfies
└── Month 5: Contribute types to DefinitelyTyped (the @types/* packages on npm)
    └── Project: TypeScript language service plugin, custom transformer
```

---

### 🏁 Milestone Checklist

- [ ] I can write type-safe code without reaching for `any`
- [ ] I understand the difference between `unknown`, `any`, `never`, and `void`
- [ ] I can write and constrain generic functions confidently
- [ ] I know all built-in utility types and can combine them
- [ ] I can write mapped types and conditional types
- [ ] I understand discriminated unions and exhaustiveness checking
- [ ] I can extend third-party library types with module augmentation
- [ ] I've published a typed npm package with proper `.d.ts` files
- [ ] I understand variance (covariant, contravariant, invariant)
- [ ] I can use branded/phantom types for domain safety
- [ ] I've configured `tsconfig.json` from scratch for a production project
- [ ] I understand why hooks can't be called conditionally (relates to TS + runtime)
- [ ] I can write recursive types without hitting TypeScript's depth limit

---

## 🧩 12. Bonus Deep Insights

---

### 🔮 Mental Model: "TypeScript is a Proof System"

When TypeScript type-checks your code, it's verifying a **proof**. Each type annotation is a claim, and TypeScript checks whether your claims are consistent.

When you write:
```typescript
function add(a: number, b: number): number {
  return a + b;
}
```

You're making three claims:
1. `a` will always be a `number`
2. `b` will always be a `number`
3. The function will always return a `number`

TypeScript verifies claim 3 is consistent with 1 and 2, and verifies at every call site that claims 1 and 2 are satisfied.

`any` breaks the proof. `as T` makes an unverified claim. `!` asserts the proof without evidence.

**Expert TypeScript developers minimize unverified claims.**

---

### 🤫 Deep Insight 1: Structural vs Nominal Typing

```typescript
// TypeScript is STRUCTURALLY typed — types are compatible if they have the same shape

interface Point2D { x: number; y: number }
interface Vector2D { x: number; y: number }  // Completely separate declaration

const point: Point2D = { x: 1, y: 2 };
const vector: Vector2D = point;  // ✅ Works! Same structure = compatible

// This means: a class "implements" an interface implicitly if it has the right properties:
class Car {
  x = 10;
  y = 20;
}

const p: Point2D = new Car();  // ✅ Works! Car has x and y

// NOMINAL typing (what Java uses) would REJECT this — types must be explicitly related.
// TypeScript's structural typing is more flexible but requires branded types for safety
// when you need nominal behavior (e.g., UserId vs SessionId).
```

---

### 🤫 Deep Insight 2: The TypeScript Type System is Turing Complete

TypeScript's type system with generics and conditional types can compute ANY computable function. It's a Turing-complete programming language at the TYPE level.

People have implemented:
- SQL parsers at the type level
- Regular expression matching
- A chess engine that runs at compile time
- JSON parsers that validate structure and infer types

This is why TypeScript types can sometimes cause the compiler to hang on extremely complex recursive types — you've accidentally written an infinite loop at the type level!

---

### 🤫 Deep Insight 3: TypeScript Does NOT Protect Your Runtime

```typescript
// TypeScript types are COMPLETELY erased at runtime.
// NOTHING stops a value from being a different type at runtime!

function processUser(user: User): void {
  console.log(user.name.toUpperCase());
}

// At runtime, this WILL crash — TypeScript can't stop it:
const mystery: unknown = fetch("/api/user").then(r => r.json());
processUser(mystery as User);  // 💥 Runtime crash if API returns wrong shape

// TypeScript only validates COMPILE-TIME types.
// For RUNTIME validation, you need:
// - Zod (most popular): z.object({ name: z.string() }).parse(data)
// - io-ts
// - class-validator
// - Manual type guards

import { z } from "zod";
const UserSchema = z.object({
  id:    z.number(),
  name:  z.string(),
  email: z.string().email(),
});

const result = UserSchema.safeParse(await fetchUser());
if (!result.success) {
  console.error(result.error);
} else {
  const user = result.data;  // Type: { id: number; name: string; email: string }
  // NOW it's safe — validated at runtime AND typed at compile time!
}
```

---

### 🧠 The Big Picture — TypeScript in the Modern Ecosystem

```
TypeScript's Position (2025):

    JavaScript ─────────────────── TypeScript
         ↓                              ↓
    No type safety               Full type safety
    No tooling                   Best-in-class IDE support
    Hard to refactor             Safe refactoring
    Fine for small scripts       Essential for large codebases

Used by:
    Frontend:   React + TS (Next.js), Vue 3 + TS, Angular (TS by default)
    Backend:    Node.js + TS (Fastify, Nest.js), Deno (TS native), Bun
    Full-stack: Next.js, tRPC (type-safe API end to end!)
    Mobile:     React Native + TS, NativeScript
    Desktop:    Electron + TS
    CLI:        Oclif, Commander.js with types

The Future:
    - TypeScript types becoming native to JavaScript (Stage 1 TC39 proposal!)
      "Type Annotations" — run TS natively without compilation
    - React 19 + TypeScript 5.x — even tighter integration
    - tRPC — end-to-end type safety without a schema language
    - Zod → TypeScript type inference = no more manual type writing
    - AI code generation almost always produces TypeScript
```

---

## 📌 13. Summary (Quick Revision & Cheat Sheet)

---

### Core Concepts (1-line each)

| Concept              | What It Means                                                               |
|----------------------|-----------------------------------------------------------------------------|
| Type annotation      | `: Type` after a variable/parameter — tells TypeScript the expected type    |
| Type inference       | TypeScript deduces the type automatically from the value                    |
| `interface`          | Describes object shapes — can be extended and merged                        |
| `type` alias         | Names any type — unions, intersections, primitives, complex types           |
| Generic `<T>`        | Type placeholder — makes functions/classes work with multiple types         |
| Union `A \| B`       | Value can be A or B — must handle both cases                                |
| Intersection `A & B` | Value must be BOTH A and B — all properties of each                        |
| Narrowing            | Reducing a broad type to a specific one inside a conditional block          |
| `unknown`            | Type-safe `any` — must narrow before use                                    |
| `never`              | Represents an impossible/unreachable type — used for exhaustiveness checks  |
| Utility types        | Built-in generic type transformations: `Partial`, `Pick`, `Omit`, etc.     |
| `as const`           | Preserves literal types, creates readonly tuples and objects                |
| `satisfies`          | Validates a value matches a type while preserving narrow inference          |
| Branded types        | Primitives with phantom type identifiers for nominal-like typing            |

---

### The 10 Things to Remember

1. ✅ **Enable `"strict": true` in tsconfig** — all strict checks enabled, no excuses
2. ✅ **Prefer `unknown` over `any`** — forces you to validate before using
3. ✅ **Use `as const` for object/array constants** — preserves literal types for unions
4. ✅ **Exhaustiveness check with `never`** — catch unhandled discriminated union cases
5. ✅ **Use `type` for unions/intersections, `interface` for object shapes** — each has its place
6. ✅ **Use Zod (or similar) for runtime validation** — TypeScript types don't exist at runtime
7. ✅ **`import type`** — use for type-only imports; compatible with esbuild/SWC/Babel
8. ✅ **Generic constraints with `extends`** — `<T extends object>` is better than `<T>`
9. ✅ **`satisfies` over `as`** — validates without losing specificity
10. ✅ **Type your API boundaries** — inputs from external systems are always `unknown`

---

### Quick Reference Cheat Sheet

```typescript
// ── BASIC TYPES ─────────────────────────────────────────────────────────
string | number | boolean | null | undefined | symbol | bigint
any  // Escape hatch — avoid
unknown  // Safe escape — always narrow before use
never  // Unreachable / impossible
void  // Function with no meaningful return

// ── TYPE DECLARATIONS ───────────────────────────────────────────────────
const x: number = 5;
let y = "inferred";  // TypeScript infers string
const z = 42 as const;  // Literal type 42

// ── INTERFACE ───────────────────────────────────────────────────────────
interface User {
  id: number;
  name: string;
  email?: string;        // Optional
  readonly role: string; // Readonly
  [key: string]: unknown; // Index signature
}

// ── TYPE ALIAS ──────────────────────────────────────────────────────────
type ID = string | number;
type Status = "active" | "inactive" | "pending";  // Literal union
type Handler = (event: Event) => void;

// ── GENERICS ────────────────────────────────────────────────────────────
function identity<T>(val: T): T { return val; }
function first<T>(arr: T[]): T | undefined { return arr[0]; }
function pick<T, K extends keyof T>(obj: T, keys: K[]): Pick<T, K> {
  return keys.reduce((acc, k) => ({ ...acc, [k]: obj[k] }), {} as Pick<T, K>);
}

// ── UTILITY TYPES ───────────────────────────────────────────────────────
Partial<User>         // All optional
Required<User>        // All required
Readonly<User>        // All readonly
Record<string, User>  // Dictionary
Pick<User, "id" | "name">    // Only id and name
Omit<User, "email">          // All except email
Exclude<Status, "pending">   // Remove "pending" from union
Extract<Status, "active" | "inactive"> // Keep only these
NonNullable<string | null>   // Remove null/undefined
ReturnType<typeof fetchUser> // Return type of function
Parameters<typeof sendEmail> // Param types as tuple
Awaited<Promise<User>>       // Unwrap Promise: User

// ── NARROWING ───────────────────────────────────────────────────────────
if (typeof x === "string") { /* x: string */ }
if (x instanceof Date) { /* x: Date */ }
if ("name" in x) { /* x has name property */ }
if (x != null) { /* x: not null or undefined */ }
function isUser(x: unknown): x is User { /* ... */ }
function assertUser(x: unknown): asserts x is User { /* ... */ }

// ── CONDITIONAL TYPES ───────────────────────────────────────────────────
type IsString<T> = T extends string ? true : false;
type Flatten<T> = T extends Array<infer U> ? U : T;
type UnwrapPromise<T> = T extends Promise<infer V> ? UnwrapPromise<V> : T;

// ── MAPPED TYPES ────────────────────────────────────────────────────────
type Optional<T> = { [P in keyof T]?: T[P] };
type Nullable<T> = { [P in keyof T]: T[P] | null };
type Getters<T> = { [K in keyof T as `get${Capitalize<string & K>}`]: () => T[K] };

// ── TEMPLATE LITERALS ───────────────────────────────────────────────────
type CSSProp = `${string}-${string}`;
type EventKey = `on${Capitalize<string>}`;
type RestAPI<R extends string> = `/api/${R}`;

// ── ASSERTION & SATISFIES ───────────────────────────────────────────────
const x = value as string;           // Assert (trust me)
const y = value satisfies Partial<User>; // Validate + keep narrow type
const z = value!;                    // Non-null assertion (avoid)

// ── AS CONST ───────────────────────────────────────────────────────────
const DIRECTIONS = ["up", "down", "left", "right"] as const;
type Direction = typeof DIRECTIONS[number]; // "up" | "down" | "left" | "right"

// ── BRANDED TYPES ──────────────────────────────────────────────────────
type UserId = string & { readonly __brand: "UserId" };
const toUserId = (id: string): UserId => id as UserId;

// ── EXHAUSTIVENESS ──────────────────────────────────────────────────────
function assertNever(x: never): never {
  throw new Error("Unhandled case: " + JSON.stringify(x));
}

// ── TSCONFIG MUST-HAVES ─────────────────────────────────────────────────
// "strict": true
// "noUncheckedIndexedAccess": true
// "exactOptionalPropertyTypes": true
// "noImplicitOverride": true
// "skipLibCheck": true
// "incremental": true
```

---

### What's Next?

After mastering TypeScript, your natural path:

- 📘 **tRPC** — End-to-end type safety between client and server with zero schema duplication
- 📘 **Zod** — Runtime type validation that generates TypeScript types — the perfect TypeScript companion
- 📘 **TypeScript Compiler API** — Build custom lint rules, code transformers, language service plugins
- 📘 **Prisma** — Type-safe database ORM — generates TypeScript types from your database schema
- 📘 **DefinitelyTyped** — Contribute type definitions for JavaScript libraries on npm
- 📘 **Effect-TS** — Typed functional programming for TypeScript — error types, dependency injection via types
- 📘 **ts-morph** — TypeScript compiler API wrapper — build codemods and refactoring tools

---

> 💬 *"TypeScript is not a different language — it is JavaScript with confidence."*

> 💬 *"Every `any` is a promise to yourself that you'll come back and fix it. You won't."*

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: TypeScript — Complete Language Mastery | Version: 1.0*
*Sections: 13 | Level: Beginner → 0.01% Elite*
