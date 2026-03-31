# 🔷 C# — The Ultimate Master Guide
### From Zero to 0.01% Expert — Every Concept, Pattern, Secret & Hidden Power

> 📘 **The most complete C# guide ever written — beginner to elite.**
>
> 🎯 *Who is this for?* Anyone who wants to go from writing C# to **mastering** C#.
> ⏱️ *Time to complete:* Self-paced — days to months
> 🛠️ *What you'll gain:* Every syntax rule, OOP pattern, async technique, runtime secret, and 0.01% hidden trick that separates a 0.01% C# developer from the rest.

---

## Table of Contents

1. [🧠 What is C#?](#1-what-is-c-super-simple)
2. [🌍 Why C# Exists & Dominates](#2-why-c-exists--dominates)
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

## 🧠 1. What is C#? (Super Simple)

### The 12-Year-Old Explanation

Imagine you want to build something incredible — a video game, a website, a mobile app, a desktop tool, or even an AI system. You need one language that's powerful enough to do all of these, easy enough to read, and fast enough to run millions of operations per second. That language is **C#**.

C# (pronounced "C sharp") was created by **Anders Hejlsberg** at Microsoft and first appeared in 2000. Hejlsberg had previously designed Turbo Pascal and Delphi — two legendary languages — so C# was built with decades of language design wisdom baked in. It runs on the **.NET platform**, which is Microsoft's framework for building all kinds of applications.

The name comes from music — just like the musical sharp symbol (♯) raises a note by a semitone, C# was designed to be a step above C and C++. Today it powers Xbox games, ASP.NET web applications serving billions of requests, Unity 3D games (including Pokémon GO), enterprise software at Fortune 500 companies, and Azure cloud services at Microsoft itself.

### Real-Life Analogy

💡 **Think of it like this:**
Languages are construction tools. C is a hand-forged chisel — incredibly precise but requires decades of skill. C++ is a Swiss Army knife with 50 blades — powerful but complex. Java is a pre-fab modular kit — consistent and portable. **C# is a fully-equipped modern workshop with power tools, a safety harness, and a floor plan** — professional-grade power with built-in safety, excellent tooling (Visual Studio / Rider), and thoughtful design that evolves every year.

### One-Line Definition

> **C#** is a strongly-typed, object-oriented, multi-paradigm programming language built on .NET that combines the performance of compiled languages with developer productivity features like LINQ, async/await, pattern matching, and a rich standard library.

---

## 🌍 2. Why C# Exists & Dominates

### The Problem It Solved

In 2000, Microsoft needed a language that was:
- More productive than C++ for Windows/enterprise development
- More performant than interpreted languages like Java (at the time)
- Designed from the ground up for the internet era
- Safe by default — preventing common bugs that plagued C/C++ codebases
- Deeply integrated with the Windows platform and later .NET ecosystem

C# delivered all of this, and with .NET Core (2016) and .NET 5+ (2020+), it became fully cross-platform — running on Linux, macOS, Windows, Android, iOS, WebAssembly, and embedded systems.

### Where C# Dominates in 2025

| Domain                        | How C# Is Used                                                          |
|-------------------------------|-------------------------------------------------------------------------|
| Game Development              | Unity Engine — the #1 game engine by market share, scripted in C#       |
| Web Backends (ASP.NET Core)   | High-performance REST APIs, gRPC, SignalR WebSockets                   |
| Desktop Applications (WPF/WinUI)| Windows desktop apps — enterprise LOB, tools, creative software       |
| Mobile (MAUI / Xamarin)       | Cross-platform mobile apps for iOS and Android                         |
| Cloud / Azure                 | Azure Functions, Azure Service Bus, the Microsoft cloud stack           |
| Enterprise Software           | SAP integrations, ERP systems, healthcare platforms                    |
| Machine Learning (.NET ML)    | ML.NET — production ML models in C#                                    |
| Game Backends                 | PlayFab, Playfab backend SDK, custom game server logic                 |
| Blazor (WebAssembly)          | Full-stack C# in the browser — no JavaScript required                   |
| Embedded / IoT                | .NET IoT, Raspberry Pi, industrial control systems                     |

### Why YOU Should Learn It Deeply

1. **Unity is the world's most popular game engine** — mastering C# unlocks game development for mobile, PC, VR, AR.
2. **ASP.NET Core is among the fastest web frameworks** — consistently topping TechEmpower benchmarks.
3. **The language evolves rapidly** — C# 12/13 have records, pattern matching, primary constructors, collection expressions — among the best syntax of any language.
4. **Incredible tooling** — Visual Studio / Rider provide the best IDE experience of any language.
5. **Full-stack with one language** — Blazor lets you write the browser UI, the server logic, and the database layer all in C#.

---

## 🧱 3. Core Fundamentals (Beginner Level)

> 🎯 *Goal: Build an unshakeable foundation. Every concept here is critical.*

---

### Concept 1: Your First C# Program & Project Setup

```csharp
// Program.cs — Top-level statements (C# 9+, no class/Main needed)
using System;
using System.Collections.Generic;

// This IS the entry point — no public class Program, no static void Main
Console.WriteLine("Hello, World!");
Console.Write("No newline here");
Console.WriteLine($"Pi is approximately {Math.PI:F4}");

// Console input:
Console.Write("Enter your name: ");
string? name = Console.ReadLine();       // Returns null if stdin is closed
Console.WriteLine($"Hello, {name}!");

// String interpolation (ALWAYS prefer over string.Format):
int age = 17;
string city = "Kolkata";
Console.WriteLine($"Name: {name}, Age: {age}, City: {city}");
Console.WriteLine($"Score: {98.756:F2}");       // 98.76 — format specifier
Console.WriteLine($"{"Center":^20}");           // Pad — C# 10+
Console.WriteLine($"{1_000_000:N0}");           // 1,000,000

// Full boilerplate (older style — still common):
// namespace MyApp;
// class Program {
//     static void Main(string[] args) {
//         Console.WriteLine("Hello!");
//     }
// }
```

```bash
# Install .NET SDK: https://dotnet.microsoft.com/download
dotnet --version                    # Verify installation

# Create new project:
dotnet new console -n MyApp         # Console app
dotnet new webapi  -n MyApi         # ASP.NET Core Web API
dotnet new classlib -n MyLib        # Class library
dotnet new blazorwasm -n MyBlazor   # Blazor WebAssembly

# Run:
cd MyApp
dotnet run                          # Build + run
dotnet build                        # Build only
dotnet publish -c Release           # Publish for production

# Package management:
dotnet add package Newtonsoft.Json  # Add NuGet package
dotnet restore                      # Restore packages
dotnet list package                 # List installed packages

# Testing:
dotnet new xunit -n MyTests
dotnet test
```

---

### Concept 2: Variables, Types & the Type System

```csharp
// ── VALUE TYPES — stored on stack, copied on assignment ──────────────────
// Integers:
sbyte  sb  = -128;              // 8-bit  signed: -128 to 127
byte   b   = 255;               // 8-bit  unsigned: 0 to 255
short  s   = -32_768;           // 16-bit signed
ushort us  = 65_535;            // 16-bit unsigned
int    i   = 2_147_483_647;     // 32-bit signed (most common)
uint   ui  = 4_294_967_295U;    // 32-bit unsigned
long   l   = 9_223_372_036_854_775_807L; // 64-bit signed
ulong  ul  = 18_446_744_073_709_551_615UL;
nint   ni  = 42;                // Native int (pointer-sized: 32 or 64 bit)
nuint  nui = 42;                // Native uint

// Floating point:
float   f   = 3.14f;            // 32-bit IEEE 754 (~7 digits)
double  d   = 3.14159265358979; // 64-bit IEEE 754 (~15 digits) — DEFAULT
decimal dec = 3.14159265358979323846m; // 128-bit EXACT decimal — USE FOR MONEY!

// Other value types:
char   c    = 'A';              // 16-bit Unicode UTF-16 code unit
bool   flag = true;

// Struct (value type):
DateTime now   = DateTime.Now;
TimeSpan span  = TimeSpan.FromHours(2.5);
Guid   guid    = Guid.NewGuid();
DateOnly date  = DateOnly.FromDateTime(now);   // C# 10+
TimeOnly time  = TimeOnly.FromDateTime(now);   // C# 10+

// ── REFERENCE TYPES — stored on heap, reference copied on assignment ──────
string  str  = "Hello";          // Immutable sequence of chars
object  obj  = 42;               // Base type of ALL types
dynamic dyn  = "can be anything"; // Late-bound — use sparingly

// Arrays (reference types):
int[]     arr1D = {1, 2, 3, 4, 5};
int[,]    arr2D = new int[3, 3];        // Multi-dimensional
int[][]   arr3D = new int[3][];         // Jagged (array of arrays)

// ── TYPE INFERENCE ────────────────────────────────────────────────────────
var x = 42;               // int — inferred by compiler
var y = 3.14;             // double
var z = "hello";          // string
var list = new List<int>(); // List<int>
// var is still STATICALLY typed — just inferred! Not dynamic!

// ── NULLABLE VALUE TYPES ──────────────────────────────────────────────────
int?  nullableInt  = null;       // Nullable<int>
bool? nullableBool = null;
nullableInt = 42;
int value = nullableInt ?? -1;   // Null-coalescing: use -1 if null
int guaranteed = nullableInt!.Value; // Null-forgiving (asserts not null)

// ── NULLABLE REFERENCE TYPES (C# 8+, enabled in csproj) ─────────────────
// <Nullable>enable</Nullable> in .csproj
string nonNullable = "hello";   // Cannot be null (compiler warning if assigned null)
string? nullable   = null;       // CAN be null
Console.WriteLine(nullable?.Length ?? 0); // Safe navigation + null coalescing

// ── CONSTANTS ─────────────────────────────────────────────────────────────
const int MaxSize    = 100;            // Compile-time constant
const double Pi      = 3.14159265358979;
const string AppName = "MyApp";

// Readonly (runtime constant — set in constructor):
static readonly DateTime StartTime = DateTime.UtcNow;

// ── TYPE CONVERSION ────────────────────────────────────────────────────────
// Implicit (safe, no data loss):
int n = 42;
long big = n;           // int → long: widening
double dbl = n;         // int → double: widening

// Explicit cast (may lose data):
double pi = 3.14159;
int truncated = (int)pi;     // 3 — truncates decimal
byte overflow  = (byte)300;  // 44 — wraps around!

// Safe conversion with TryParse:
if (int.TryParse("42", out int result)) {
    Console.WriteLine(result);  // 42
}
// Parse throws, TryParse returns false — ALWAYS prefer TryParse!

bool parsed = double.TryParse("3.14", out double dblResult);
bool success = Guid.TryParse("...", out Guid guidResult);

// Convert class:
int fromString = Convert.ToInt32("42");
string toString = Convert.ToString(42);
bool fromInt = Convert.ToBoolean(1);  // true

// as operator — returns null if cast fails (reference types):
object o = "hello";
string? s = o as string;   // "hello"
int?    n2 = o as int?;     // null — not an int

// is operator — type check:
if (o is string str2) {
    Console.WriteLine(str2.Length);  // Pattern matching!
}
```

---

### Concept 3: Strings — Mastery

```csharp
using System;
using System.Text;
using System.Text.RegularExpressions;

// ── STRING CREATION ────────────────────────────────────────────────────────
string s1 = "regular string";
string s2 = @"verbatim: no escape \n needed, ""quotes"" with double";
string s3 = """
    C# 11 raw string literals
    No escaping needed: \n "quotes" {braces}
    """;   // Triple-quoted raw strings

// String interpolation:
string name = "Aryan";
int age = 17;
string msg = $"Hello, {name}! You are {age} years old.";
string formatted = $"{Math.PI:F5}";           // "3.14159"
string padded = $"{name,10}";                 // Right-align in 10 chars
string leftPad = $"{name,-10}";              // Left-align in 10 chars

// Interpolated verbatim:
string path = $@"C:\Users\{name}\Documents";

// ── IMMUTABILITY — strings CANNOT be modified ─────────────────────────────
string original = "hello";
string upper = original.ToUpper();   // New string — original unchanged!
// original[0] = 'H';               // ❌ COMPILE ERROR — strings are immutable

// ── STRING METHODS — COMPLETE REFERENCE ──────────────────────────────────
string text = "  Hello, World!  ";

// Inspection:
text.Length;                              // 17
text.Contains("World");                   // true
text.Contains("world", StringComparison.OrdinalIgnoreCase); // true
text.StartsWith("  Hello");               // true
text.EndsWith("!  ");                     // true
text.IndexOf("World");                    // 9 — first occurrence
text.LastIndexOf("l");                    // 12
text.Equals("hello", StringComparison.OrdinalIgnoreCase); // true

// Transformation:
text.ToUpper();                           // "  HELLO, WORLD!  "
text.ToLower();                           // "  hello, world!  "
text.Trim();                              // "Hello, World!"
text.TrimStart();                         // "Hello, World!  "
text.TrimEnd();                           // "  Hello, World!"
text.Trim('!', ' ');                      // "Hello, World"
text.Replace("World", "C#");             // "  Hello, C#!  "
text.Replace("l", "L", StringComparison.Ordinal);
text.PadLeft(20);                         // Right-align in 20 chars
text.PadRight(20, '-');                   // "  Hello, World!  ---"

// Splitting and joining:
string csv = "a,b,c,d,e";
string[] parts = csv.Split(',');           // ["a","b","c","d","e"]
string[] limited = csv.Split(',', 3);      // ["a","b","c,d,e"]
string joined = string.Join(" | ", parts); // "a | b | c | d | e"
string joined2 = string.Join(", ", new[] {1, 2, 3}); // "1, 2, 3"

// Substring:
string sub = text.Substring(2, 5);        // "Hello"
ReadOnlySpan<char> span = text.AsSpan(2, 5); // Zero-allocation span!

// C# 8+ Range/Index:
string last3 = text[^3..];               // Last 3 chars
string first5 = text[..5];               // First 5 chars
string middle = text[2..^2];             // Without first/last 2
char last = text[^1];                    // Last character

// ── StringBuilder — for many concatenations (avoid + in loops!) ──────────
var sb = new StringBuilder();
sb.Append("Hello");
sb.Append(", ");
sb.AppendLine("World!");
sb.AppendFormat("Pi = {0:F2}", Math.PI);
sb.Insert(0, "[START] ");
sb.Replace("World", "C#");
string result = sb.ToString();
// Much faster than: result = result + piece (creates new string each time!)

// ── REGEX ─────────────────────────────────────────────────────────────────
var regex = new Regex(@"^\d{3}-\d{4}$");    // Compile regex once, reuse!
bool isMatch = regex.IsMatch("123-4567");   // true

// Named groups:
var emailRegex = new Regex(@"(?<user>[\w.]+)@(?<domain>[\w.]+)");
var match = emailRegex.Match("user@example.com");
if (match.Success) {
    Console.WriteLine(match.Groups["user"].Value);    // "user"
    Console.WriteLine(match.Groups["domain"].Value);  // "example.com"
}

// Replace with regex:
string cleaned = Regex.Replace("Hello   World", @"\s+", " ");

// ── STRING COMPARISON — IMPORTANT ─────────────────────────────────────────
// Always specify StringComparison:
bool eq = string.Equals("hello", "HELLO", StringComparison.OrdinalIgnoreCase);
int cmp = string.Compare("a", "B", StringComparison.Ordinal);
// Ordinal = byte comparison (fast, no culture)
// OrdinalIgnoreCase = byte comparison, case-insensitive
// CurrentCulture = locale-aware (for display to user)
// InvariantCulture = culture-invariant (for serialization/storage)
```

---

### Concept 4: Control Flow

```csharp
// ── IF / ELSE IF / ELSE ───────────────────────────────────────────────────
int score = 87;
if (score >= 90)      Console.WriteLine("A");
else if (score >= 80) Console.WriteLine("B");
else                  Console.WriteLine("F");

// Ternary:
string grade = score >= 50 ? "Pass" : "Fail";

// Null-coalescing:
string? username = null;
string display = username ?? "Guest";        // "Guest" if null
username ??= "DefaultUser";                  // Assign only if null

// ── SWITCH STATEMENT ──────────────────────────────────────────────────────
switch (score / 10) {
    case 10:
    case 9:  Console.WriteLine("A"); break;
    case 8:  Console.WriteLine("B"); break;
    default: Console.WriteLine("F"); break;
}

// ── SWITCH EXPRESSION (C# 8+) — expression, not statement ────────────────
string label = score switch {
    >= 90         => "Excellent",
    >= 80 and < 90=> "Good",        // Relational + logical patterns
    >= 70         => "Average",
    _             => "Below Average" // Default arm
};

// Switch with tuples:
(bool isWeekend, bool isHoliday) day = (true, false);
string mood = day switch {
    (true, true)   => "Double holiday!",
    (true, false)  => "Weekend",
    (false, true)  => "Holiday",
    (false, false) => "Weekday"
};

// ── LOOPS ─────────────────────────────────────────────────────────────────
for (int i = 0; i < 10; i++) Console.Write(i + " ");

// foreach — THE most used loop in C#:
var fruits = new[] {"apple", "banana", "cherry"};
foreach (string fruit in fruits) Console.WriteLine(fruit);

// With index (using LINQ):
foreach (var (fruit, i) in fruits.Select((v, i) => (v, i)))
    Console.WriteLine($"{i}: {fruit}");

// while / do-while:
int n = 1;
while (n < 100) n *= 2;
do { n--; } while (n > 50);

// ── PATTERN MATCHING — C# is the best at this ─────────────────────────────
object obj = 42;

// Type pattern:
if (obj is int num) Console.WriteLine($"Integer: {num}");

// Property pattern:
if (obj is string { Length: > 5 } longStr)
    Console.WriteLine($"Long string: {longStr}");

// Combined patterns:
object shape = new { Width = 10, Height = 5 };
string desc = shape switch {
    { } when shape is int i && i > 100 => "Large number",
    string s                            => $"String: {s}",
    null                                => "null",
    _                                   => "something else"
};

// Positional pattern with records:
record Point(int X, int Y);
var p = new Point(3, 4);
string quadrant = p switch {
    (> 0, > 0) => "First quadrant",
    (< 0, > 0) => "Second quadrant",
    (< 0, < 0) => "Third quadrant",
    (> 0, < 0) => "Fourth quadrant",
    _          => "On an axis"
};

// List pattern (C# 11+):
int[] numbers = {1, 2, 3};
bool isStartsWith1 = numbers is [1, ..];
bool isExact = numbers is [1, 2, 3];
bool has3Plus = numbers is [_, _, _, ..];
```

---

### Concept 5: Functions & Methods

```csharp
// ── BASIC METHODS ─────────────────────────────────────────────────────────
static int Add(int a, int b) => a + b;         // Expression-bodied
static void PrintHello() { Console.WriteLine("Hello!"); }

// ── PARAMETERS ────────────────────────────────────────────────────────────
// Default parameters:
static double Power(double base_, int exp = 2) => Math.Pow(base_, exp);
Power(3);       // 9.0 — uses default
Power(3, 3);    // 27.0

// Named arguments (call in any order!):
Power(exp: 3, base_: 2); // 8.0

// ref — modify the caller's variable:
static void Increment(ref int value) => value++;
int x = 5;
Increment(ref x);
Console.WriteLine(x); // 6

// out — return multiple values:
static bool TryParse(string s, out int result) {
    return int.TryParse(s, out result);
}
if (TryParse("42", out int val)) Console.WriteLine(val); // 42

// in — pass large struct by reference, read-only (C# 7.2+):
static double Length(in (double X, double Y) point) =>
    Math.Sqrt(point.X * point.X + point.Y * point.Y);

// params — variable argument list:
static int Sum(params int[] numbers) => numbers.Sum();
Sum(1, 2, 3);          // 6
Sum(1, 2, 3, 4, 5);    // 15
Sum(new[] {1,2,3});    // Also works with array

// ── LOCAL FUNCTIONS ───────────────────────────────────────────────────────
static int Fibonacci(int n) {
    if (n < 0) throw new ArgumentOutOfRangeException(nameof(n));

    // Local function — only visible inside Fibonacci:
    static int Fib(int n) => n < 2 ? n : Fib(n - 1) + Fib(n - 2);

    return Fib(n);
}

// Static local functions (C# 8+) — can't capture outer variables:
static int ProcessData(int[] data) {
    return data.Select(Transform).Sum();

    static int Transform(int x) => x * x + 1; // Static — no closure overhead
}

// ── EXTENSION METHODS — add methods to existing types ─────────────────────
public static class StringExtensions {
    public static bool IsNullOrWhiteSpace(this string? s)
        => string.IsNullOrWhiteSpace(s);

    public static string Truncate(this string s, int maxLength)
        => s.Length <= maxLength ? s : s[..maxLength] + "...";

    public static T? ParseAs<T>(this string s) where T : struct {
        var converter = System.ComponentModel.TypeDescriptor.GetConverter(typeof(T));
        return (T?)converter.ConvertFrom(s);
    }
}

// Usage — called ON the object as if it were a native method:
"Hello World".Truncate(5);    // "Hello..."
"42".ParseAs<int>();          // 42
```

---

🧪 **Mini Task 1:**
> Write a method `FizzBuzz(int n)` that returns a `List<string>` where each element is "Fizz" for multiples of 3, "Buzz" for multiples of 5, "FizzBuzz" for multiples of both, and the number as a string otherwise. Use a switch expression.
> ✅ *Expected: `FizzBuzz(15)[^1]` → `"FizzBuzz"`*

🧪 **Mini Task 2:**
> Write a generic extension method `Chunk<T>(this IEnumerable<T> source, int size)` that splits any sequence into chunks of a given size. Test it on a `List<int>` with 10 elements and chunk size 3.

---

## ⚙️ 4. Complete Language System Breakdown

> 🎯 *Goal: Understand ALL of C#'s machinery — nothing hidden.*

---

### Part 1: Object-Oriented Programming — The Complete System

```csharp
// ── CLASS FUNDAMENTALS ────────────────────────────────────────────────────
public class BankAccount {
    // ── Fields (prefer private + property) ──────────────────────────────
    private decimal _balance;
    private readonly string _accountNumber;   // readonly — set only in constructor
    private static int _totalAccounts = 0;    // Shared across all instances

    // ── Auto-Properties (C# shorthand for get/set) ────────────────────
    public string Owner { get; private set; } = "";    // Init in constructor
    public DateTime CreatedAt { get; } = DateTime.UtcNow; // Get-only auto-prop
    public bool IsActive { get; set; } = true;

    // ── Full Property with Validation ────────────────────────────────
    public decimal Balance {
        get => _balance;
        private set {
            if (value < -500m)
                throw new InvalidOperationException("Below overdraft limit");
            _balance = value;
        }
    }

    // ── Computed Property ────────────────────────────────────────────
    public string Status => Balance > 0 ? "In credit" : "Overdrawn";
    public int AccountId => _totalAccounts; // Expose static

    // ── Constants and static ─────────────────────────────────────────
    public const decimal OverdraftLimit = -500m;
    public static int TotalAccounts => _totalAccounts;

    // ── Constructor ──────────────────────────────────────────────────
    public BankAccount(string owner, decimal initialBalance = 0m) {
        if (string.IsNullOrWhiteSpace(owner))
            throw new ArgumentException("Owner name cannot be empty", nameof(owner));

        Owner = owner;
        _balance = initialBalance;
        _accountNumber = GenerateAccountNumber();
        Interlocked.Increment(ref _totalAccounts);
    }

    // ── Static Factory Method ────────────────────────────────────────
    public static BankAccount Create(string owner, decimal balance = 0m)
        => new BankAccount(owner, balance);

    // ── Methods with Fluent Interface ────────────────────────────────
    public BankAccount Deposit(decimal amount) {
        ArgumentOutOfRangeException.ThrowIfNegativeOrZero(amount);  // C# 8+
        Balance += amount;
        OnTransactionProcessed?.Invoke(this, new TransactionEventArgs("deposit", amount));
        return this;  // Fluent interface — enables chaining
    }

    public BankAccount Withdraw(decimal amount) {
        ArgumentOutOfRangeException.ThrowIfNegativeOrZero(amount);
        if (Balance - amount < OverdraftLimit)
            throw new InvalidOperationException("Insufficient funds");
        Balance -= amount;
        return this;
    }

    // ── Events ───────────────────────────────────────────────────────
    public event EventHandler<TransactionEventArgs>? OnTransactionProcessed;

    // ── Operator Overloading ─────────────────────────────────────────
    public static BankAccount operator +(BankAccount account, decimal amount)
        => account.Deposit(amount);

    // ── Object methods ────────────────────────────────────────────────
    public override string ToString()
        => $"Account({Owner}: {Balance:C})";

    public override bool Equals(object? obj)
        => obj is BankAccount other && _accountNumber == other._accountNumber;

    public override int GetHashCode()
        => _accountNumber.GetHashCode();

    private static string GenerateAccountNumber()
        => $"ACC{Random.Shared.Next(100000, 999999)}";
}

// ── INHERITANCE ───────────────────────────────────────────────────────────
public class SavingsAccount : BankAccount {
    public decimal InterestRate { get; }

    public SavingsAccount(string owner, decimal balance, decimal interestRate = 0.05m)
        : base(owner, balance) {       // Call base constructor!
        InterestRate = interestRate;
    }

    public void ApplyInterest() {
        Deposit(Balance * InterestRate);
    }

    // Override and extend:
    public override string ToString()
        => base.ToString() + $" [Savings, {InterestRate:P0} interest]";
}

// ── ABSTRACT CLASSES ──────────────────────────────────────────────────────
public abstract class Shape {
    public abstract double Area { get; }            // Must implement
    public abstract double Perimeter { get; }       // Must implement
    public virtual string Description               // CAN override
        => $"{GetType().Name}: Area={Area:F2}, Perimeter={Perimeter:F2}";
}

public class Circle(double radius) : Shape {
    public double Radius { get; } = radius;
    public override double Area      => Math.PI * Radius * Radius;
    public override double Perimeter => 2 * Math.PI * Radius;
}

// ── INTERFACES ────────────────────────────────────────────────────────────
public interface IRepository<T> where T : class {
    Task<T?> GetByIdAsync(int id);
    Task<IEnumerable<T>> GetAllAsync();
    Task<T> CreateAsync(T entity);
    Task UpdateAsync(T entity);
    Task DeleteAsync(int id);
}

// Default interface methods (C# 8+):
public interface ILogger {
    void Log(string message);
    void LogError(string message) => Log($"[ERROR] {message}");  // Default impl!
    void LogInfo(string message)  => Log($"[INFO] {message}");
}

// ── RECORDS — immutable data carriers (C# 9+) ────────────────────────────
// Positional record — most concise:
public record Person(string FirstName, string LastName, int Age) {
    // Derived property (not part of constructor):
    public string FullName => $"{FirstName} {LastName}";

    // Custom method:
    public Person WithBirthday() => this with { Age = Age + 1 }; // Nondestructive mutation!
}

// Records have: value equality, ToString, Deconstruct, with-expressions — for free!
var p1 = new Person("Aryan", "Dev", 17);
var p2 = new Person("Aryan", "Dev", 17);
Console.WriteLine(p1 == p2);             // true  — value equality by default!
Console.WriteLine(p1);                  // Person { FirstName = Aryan, LastName = Dev, Age = 17 }

var older = p1 with { Age = 18 };       // Creates a new record — original unchanged!

// Positional deconstruct:
var (firstName, lastName, age2) = p1;

// Record struct (C# 10+) — value type record:
public record struct Point(double X, double Y);

// Class record — mutable if desired:
public record class MutableRecord(string Name) {
    public int Count { get; set; } = 0; // Mutable property
}

// ── PRIMARY CONSTRUCTORS (C# 12+) ────────────────────────────────────────
// On regular classes (not just records):
public class Logger(string prefix, bool verbose = false) {
    // Parameters available in entire class body:
    public void Log(string message) {
        if (verbose) Console.WriteLine($"[{prefix}] {message}");
    }
}

// ── SEALED & STATIC CLASSES ──────────────────────────────────────────────
sealed class Singleton {                  // Cannot be inherited
    private static readonly Lazy<Singleton> _instance =
        new Lazy<Singleton>(() => new Singleton());
    public static Singleton Instance => _instance.Value;
    private Singleton() {}
}

static class MathUtils {                  // Cannot be instantiated, all members static
    public static int Square(int n) => n * n;
}
```

---

### Part 2: Collections & LINQ — The Power Duo

```csharp
using System.Collections.Generic;
using System.Linq;

// ── COLLECTIONS ───────────────────────────────────────────────────────────
// List<T> — most versatile dynamic list:
var list = new List<int> { 3, 1, 4, 1, 5, 9 };
list.Add(2);
list.AddRange(new[] { 6, 5, 3 });
list.Insert(0, 0);                   // Insert at index
list.Remove(9);                      // Remove first occurrence
list.RemoveAt(0);                    // Remove by index
list.RemoveAll(x => x % 2 == 0);    // Remove all matching predicate
list.Sort();
list.Reverse();
list.Contains(5);
list.FindIndex(x => x > 4);
list.Find(x => x > 4);
list.FindAll(x => x > 4);
list[^1];                            // Last element (C# 8 index)
list[1..4];                          // Slice — returns array

// Dictionary<TKey, TValue>:
var dict = new Dictionary<string, int> {
    ["Alice"] = 95,
    ["Bob"] = 87
};
dict["Carol"] = 92;                  // Add or update
dict.TryGetValue("Alice", out int score);     // Safe get
dict.ContainsKey("Dave");            // false
dict.Remove("Bob");
foreach (var (key, val) in dict)     // Tuple deconstruct in foreach!
    Console.WriteLine($"{key}: {val}");

// GetValueOrDefault:
int result = dict.GetValueOrDefault("Unknown", 0); // 0 — no exception!

// HashSet<T> — unique elements, O(1) operations:
var set = new HashSet<int> { 1, 2, 3, 4, 5 };
set.Add(6);                          // O(1)
set.Contains(3);                     // O(1) — much faster than List.Contains!
set.Remove(4);
var setB = new HashSet<int> { 3, 4, 5, 6, 7 };
set.IntersectWith(setB);             // Modifies set in-place: {3, 5, 6}
set.UnionWith(setB);                 // {3, 4, 5, 6, 7}
set.ExceptWith(setB);               // Elements in set but not setB

// SortedDictionary / SortedList — sorted key-value:
var sorted = new SortedDictionary<string, int>();

// Queue<T> — FIFO:
var queue = new Queue<int>();
queue.Enqueue(1); queue.Enqueue(2); queue.Enqueue(3);
int first = queue.Dequeue();         // 1 — removes and returns
int peek = queue.Peek();             // 2 — reads without removing

// Stack<T> — LIFO:
var stack = new Stack<int>();
stack.Push(1); stack.Push(2); stack.Push(3);
int top = stack.Pop();               // 3
int peek2 = stack.Peek();            // 2

// PriorityQueue<TElement, TPriority> (C# 10+):
var pq = new PriorityQueue<string, int>();
pq.Enqueue("low priority", 10);
pq.Enqueue("high priority", 1);     // Lower number = higher priority
string next = pq.Dequeue();         // "high priority"

// LinkedList<T> — O(1) insert/remove if you have the node:
var linked = new LinkedList<int>(new[] { 1, 2, 3 });
linked.AddFirst(0);
linked.AddLast(4);
linked.AddAfter(linked.Find(2)!, 99);

// ── LINQ — Language Integrated Query ─────────────────────────────────────
var students = new List<(string Name, int Age, double GPA, string Dept)> {
    ("Aryan",  17, 9.8, "CS"),
    ("Priya",  18, 9.2, "Math"),
    ("Rahul",  17, 8.9, "CS"),
    ("Kavya",  18, 9.5, "Physics"),
    ("Dev",    17, 7.5, "CS"),
};

// QUERY SYNTAX (SQL-like):
var topCS = from s in students
            where s.Dept == "CS" && s.GPA >= 9.0
            orderby s.GPA descending
            select new { s.Name, s.GPA };

// METHOD SYNTAX (more flexible — PREFER):
var topCS2 = students
    .Where(s => s.Dept == "CS" && s.GPA >= 9.0)
    .OrderByDescending(s => s.GPA)
    .Select(s => new { s.Name, s.GPA });

foreach (var s in topCS2) Console.WriteLine($"{s.Name}: {s.GPA}");

// ── ALL IMPORTANT LINQ METHODS ────────────────────────────────────────────

// FILTERING:
students.Where(s => s.Age >= 18);               // Filter by predicate
students.OfType<string>();                       // Filter by type
students.Distinct();                             // Unique elements
students.DistinctBy(s => s.Dept);               // Distinct by key (C# 6+/.NET 6+)

// PROJECTION:
students.Select(s => s.Name);                   // Transform
students.Select((s, i) => $"{i}: {s.Name}");   // With index
students.SelectMany(s => s.Name.Split(' '));    // Flatten

// ORDERING:
students.OrderBy(s => s.GPA);
students.OrderByDescending(s => s.GPA);
students.ThenBy(s => s.Name);                   // Secondary sort
students.Reverse();

// GROUPING:
var byDept = students.GroupBy(s => s.Dept);
foreach (var group in byDept) {
    Console.WriteLine($"{group.Key}: {group.Count()} students");
    foreach (var s in group) Console.WriteLine($"  {s.Name}");
}

var deptAverages = students
    .GroupBy(s => s.Dept)
    .Select(g => new { Dept = g.Key, AvgGPA = g.Average(s => s.GPA) })
    .OrderByDescending(d => d.AvgGPA);

// JOINING:
var courses = new[] { ("CS", "Algorithms"), ("Math", "Calculus"), ("Physics", "Mechanics") };
var joined = students.Join(
    courses,
    s => s.Dept,                    // Key from students
    c => c.Item1,                   // Key from courses
    (s, c) => $"{s.Name}: {c.Item2}" // Result selector
);

// AGGREGATION:
students.Count();                               // 5
students.Count(s => s.Age >= 18);              // How many >= 18
students.Sum(s => s.GPA);                      // Sum of GPAs
students.Average(s => s.GPA);                  // Average GPA
students.Min(s => s.GPA);                      // Minimum GPA
students.Max(s => s.GPA);                      // Maximum GPA
students.MinBy(s => s.GPA);                    // Student with min GPA
students.MaxBy(s => s.GPA);                    // Student with max GPA
students.Aggregate((acc, s) => acc.GPA > s.GPA ? acc : s); // Custom aggregate

// ELEMENT:
students.First();                              // First or InvalidOperationException
students.First(s => s.Dept == "CS");          // First CS student
students.FirstOrDefault();                     // First or default (null for class)
students.FirstOrDefault(s => s.Age > 100);    // null — no one over 100
students.Single(s => s.Name == "Aryan");      // Exactly one, else throw
students.SingleOrDefault(s => s.Name == "X"); // null
students.Last();
students.LastOrDefault();
students.ElementAt(2);                         // By index
students.ElementAtOrDefault(100);             // null

// CONVERSION:
students.ToList();
students.ToArray();
students.ToDictionary(s => s.Name, s => s.GPA);
students.ToHashSet();
students.ToLookup(s => s.Dept);               // Multi-value dictionary

// QUANTIFIERS:
students.Any();                               // true — any elements?
students.Any(s => s.GPA > 9.5);             // Any with GPA > 9.5?
students.All(s => s.Age >= 17);             // All aged 17+?
students.Contains(students[0]);              // Exact match

// SET OPERATIONS:
var group1 = students.Take(3).Select(s => s.Name);
var group2 = students.Skip(2).Select(s => s.Name);
group1.Union(group2);                         // Combined unique names
group1.Intersect(group2);                     // Common names
group1.Except(group2);                        // In group1, not group2

// PARTITIONING:
students.Take(3);                             // First 3
students.Skip(2);                             // Skip first 2
students.TakeLast(2);                         // Last 2
students.SkipLast(2);                         // Without last 2
students.TakeWhile(s => s.GPA >= 9.0);       // While condition is true
students.SkipWhile(s => s.GPA >= 9.0);       // Skip while condition is true

// PAGING:
int page = 1, pageSize = 3;
var paged = students.Skip((page - 1) * pageSize).Take(pageSize);

// Chunk (C# 6+):
students.Chunk(2);   // [[s1,s2], [s3,s4], [s5]]

// ZIP:
var names = students.Select(s => s.Name);
var gpas  = students.Select(s => s.GPA);
var zipped = names.Zip(gpas, (n, g) => $"{n}: {g}");
```

---

### Part 3: Async/Await — Asynchronous Programming

```csharp
using System.Net.Http;
using System.Threading;
using System.Threading.Tasks;

// ── TASK AND ASYNC/AWAIT ──────────────────────────────────────────────────
// async method returns Task (void), Task<T> (value), or ValueTask<T>:

// Basic async method:
public static async Task<string> FetchDataAsync(string url) {
    using var client = new HttpClient();
    string content = await client.GetStringAsync(url);  // Non-blocking wait!
    return content;
}

// ValueTask — for when the result is often available synchronously:
public static async ValueTask<int> GetCachedValueAsync(string key) {
    if (_cache.TryGetValue(key, out int val))
        return val;               // Synchronous path — no heap allocation!
    return await FetchFromDbAsync(key); // Asynchronous path
}

// ── PARALLEL ASYNC OPERATIONS ────────────────────────────────────────────
// Sequential (SLOW):
async Task SequentialBad() {
    var u = await FetchUserAsync(1);      // Wait for each one before starting next
    var p = await FetchPostsAsync(1);
    var c = await FetchCommentsAsync(1);
}

// Parallel (FAST) — start all, then await all:
async Task ParallelGood() {
    var userTask     = FetchUserAsync(1);     // Start immediately
    var postsTask    = FetchPostsAsync(1);    // Start immediately
    var commentsTask = FetchCommentsAsync(1); // Start immediately

    await Task.WhenAll(userTask, postsTask, commentsTask); // Wait for all

    var user     = await userTask;       // Already done — instant!
    var posts    = await postsTask;
    var comments = await commentsTask;
}

// Task.WhenAny — first to complete wins (timeout pattern):
async Task<string> WithTimeout(Task<string> operation, int timeoutMs) {
    var timeout = Task.Delay(timeoutMs);
    var completed = await Task.WhenAny(operation, timeout);
    if (completed == timeout) throw new TimeoutException("Operation timed out");
    return await operation;
}

// ── CANCELLATION TOKENS ───────────────────────────────────────────────────
// Always support cancellation in async methods:
public static async Task<IEnumerable<User>> SearchUsersAsync(
    string query,
    CancellationToken cancellationToken = default)
{
    using var client = new HttpClient();

    // Pass cancellationToken to every awaitable operation:
    var response = await client.GetAsync(
        $"/api/users?q={query}",
        cancellationToken         // If cancelled, OperationCanceledException thrown
    );

    cancellationToken.ThrowIfCancellationRequested(); // Manual check

    var json = await response.Content.ReadAsStringAsync(cancellationToken);
    return JsonSerializer.Deserialize<IEnumerable<User>>(json)!;
}

// Creating and using cancellation:
using var cts = new CancellationTokenSource();
cts.CancelAfter(TimeSpan.FromSeconds(5));   // Auto-cancel after 5 seconds

try {
    var results = await SearchUsersAsync("aryan", cts.Token);
} catch (OperationCanceledException) {
    Console.WriteLine("Search was cancelled");
}

// ── ASYNC STREAMS (C# 8+) ─────────────────────────────────────────────────
// IAsyncEnumerable — stream data without loading all into memory:
public static async IAsyncEnumerable<int> GenerateNumbersAsync(
    int count,
    [System.Runtime.CompilerServices.EnumeratorCancellation]
    CancellationToken ct = default)
{
    for (int i = 0; i < count; i++) {
        await Task.Delay(100, ct);          // Simulate async work
        yield return i;                     // Return one at a time
    }
}

// Consume async stream:
await foreach (int number in GenerateNumbersAsync(10))
    Console.WriteLine(number);

// With cancellation:
using var cts2 = new CancellationTokenSource();
await foreach (int n in GenerateNumbersAsync(100).WithCancellation(cts2.Token))
    if (n > 5) { cts2.Cancel(); break; }

// ── PARALLEL AND PLINQ ────────────────────────────────────────────────────
// Parallel.ForEach:
var numbers = Enumerable.Range(1, 1000).ToList();
Parallel.ForEach(numbers, n => {
    ProcessItem(n);                         // Runs on thread pool
});

// With options:
var options = new ParallelOptions {
    MaxDegreeOfParallelism = Environment.ProcessorCount,
    CancellationToken = CancellationToken.None
};
Parallel.ForEach(numbers, options, n => ProcessItem(n));

// PLINQ — parallel LINQ:
var result = numbers
    .AsParallel()                           // Parallelize!
    .WithDegreeOfParallelism(4)
    .Where(n => n % 2 == 0)
    .Select(n => n * n)
    .Sum();

// Parallel.ForEachAsync (C# .NET 6+):
await Parallel.ForEachAsync(numbers, async (n, ct) => {
    await ProcessItemAsync(n, ct);
});
```

---

### Part 4: Generics & Type System

```csharp
// ── GENERIC CLASSES ───────────────────────────────────────────────────────
public class Repository<T> where T : class, IEntity, new() {
    private readonly List<T> _store = new();

    public void Add(T item) => _store.Add(item);

    public T? GetById(int id) =>
        _store.FirstOrDefault(x => x.Id == id);

    public IEnumerable<T> GetAll() => _store.AsReadOnly();

    public T GetOrCreate(int id) {
        var existing = GetById(id);
        if (existing != null) return existing;

        var newItem = new T();    // Works because of new() constraint!
        newItem.Id = id;
        _store.Add(newItem);
        return newItem;
    }
}

// ── GENERIC CONSTRAINTS ───────────────────────────────────────────────────
// where T : struct           — T must be a value type
// where T : class            — T must be a reference type
// where T : new()            — T must have parameterless constructor
// where T : SomeClass        — T must inherit from SomeClass
// where T : ISomeInterface   — T must implement interface
// where T : unmanaged        — T must be unmanaged (no refs) — C# 7.3+
// where T : notnull          — T cannot be null — C# 8+
// where T : Enum             — T must be an enum — C# 7.3+
// where T : Delegate         — T must be a delegate — C# 7.3+

// Multiple constraints:
public class DataProcessor<TInput, TOutput>
    where TInput  : class, IConvertible
    where TOutput : struct, IComparable<TOutput> {

    public abstract TOutput Process(TInput input);
}

// ── COVARIANCE AND CONTRAVARIANCE ─────────────────────────────────────────
// Covariant (out T) — can only return T, not accept T:
public interface IProducer<out T> {
    T Produce();    // Can return T
    // void Consume(T item); // ❌ Cannot accept T in covariant interface
}

// Contravariant (in T) — can only accept T, not return T:
public interface IConsumer<in T> {
    void Consume(T item);  // Can accept T
    // T Produce();         // ❌ Cannot return T in contravariant interface
}

// Built-in examples:
IEnumerable<string> strings = new List<string>();
IEnumerable<object> objects = strings;  // Covariant — works!

Action<object> objAction = obj => Console.WriteLine(obj);
Action<string> strAction = objAction;   // Contravariant — works!

// ── GENERIC METHODS ───────────────────────────────────────────────────────
public static T Max<T>(T a, T b) where T : IComparable<T>
    => a.CompareTo(b) >= 0 ? a : b;

// Type inference lets you skip the type parameter:
Max(3, 5);           // Inferred as Max<int>
Max("hello", "world"); // Inferred as Max<string>

// ── DELEGATES, FUNC, ACTION, PREDICATE ───────────────────────────────────
// Built-in generic delegates:
Func<int, int, int> add = (a, b) => a + b;
Func<string, bool> isLong = s => s.Length > 5;
Func<int> getZero = () => 0;

Action<string> print = msg => Console.WriteLine(msg);
Action<string, int> printN = (msg, n) => Console.WriteLine($"{n}: {msg}");

Predicate<int> isEven = n => n % 2 == 0;   // Same as Func<int, bool>

// Higher-order functions:
public static IEnumerable<T> Filter<T>(IEnumerable<T> source, Func<T, bool> predicate)
    => source.Where(predicate);

public static IEnumerable<TResult> Map<T, TResult>(
    IEnumerable<T> source,
    Func<T, TResult> transform)
    => source.Select(transform);
```

---

### 📊 Full C# System Overview Table

| Feature                  | C# Mechanism                                | Key Insight                                           |
|--------------------------|---------------------------------------------|-------------------------------------------------------|
| Type system              | Strong, static, nominally typed             | Nullable reference types prevent null bugs at compile |
| Memory management        | GC with generations (gen0/1/2)              | Don't fight GC — help it with `IDisposable`/`using`   |
| Async model              | Task-based async (TAP) + async/await        | Non-blocking I/O — never block on async with `.Wait()`|
| OOP                      | Classes, interfaces, abstract, sealed       | Records for immutable data, classes for behavior      |
| Generics                 | CLR-level generics — true type safety       | Not type erasure like Java — full runtime type info   |
| LINQ                     | Deferred execution — lazy evaluation        | `.ToList()` materializes; without it, re-executes     |
| Pattern matching         | `is`, `switch` expressions, patterns       | C#'s most expressive feature — use everywhere         |
| Events                   | `event EventHandler<T>` + delegates        | Observer pattern built into the language              |
| Reflection               | `Type`, `MethodInfo`, `PropertyInfo`        | Full runtime introspection and dynamic invocation     |
| Source generators        | Compile-time code generation (Roslyn)       | Zero-runtime cost abstractions via codegen            |

---

## 🔄 5. Real-World Workflow

---

### 🟢 Beginner Workflow: REST API with ASP.NET Core

```csharp
// Program.cs — Minimal API (ASP.NET Core .NET 8+)
using Microsoft.AspNetCore.Mvc;
using System.ComponentModel.DataAnnotations;

var builder = WebApplication.CreateBuilder(args);

// Add services:
builder.Services.AddEndpointsApiExplorer();
builder.Services.AddSwaggerGen();
builder.Services.AddSingleton<IUserRepository, InMemoryUserRepository>();

var app = builder.Build();

// Configure middleware pipeline:
if (app.Environment.IsDevelopment()) {
    app.UseSwagger();
    app.UseSwaggerUI();
}

app.UseHttpsRedirection();

// ── MINIMAL API ENDPOINTS ─────────────────────────────────────────────────
var usersApi = app.MapGroup("/api/users").WithTags("Users");

usersApi.MapGet("/", async (IUserRepository repo) =>
    await repo.GetAllAsync());

usersApi.MapGet("/{id:int}", async (int id, IUserRepository repo) => {
    var user = await repo.GetByIdAsync(id);
    return user is null ? Results.NotFound($"User {id} not found") : Results.Ok(user);
}).WithName("GetUser");

usersApi.MapPost("/", async ([FromBody] CreateUserRequest request, IUserRepository repo) => {
    var user = await repo.CreateAsync(new User(0, request.Username, request.Email));
    return Results.CreatedAtRoute("GetUser", new { id = user.Id }, user);
});

usersApi.MapPut("/{id:int}", async (int id, UpdateUserRequest req, IUserRepository repo) => {
    var updated = await repo.UpdateAsync(id, req);
    return updated is null ? Results.NotFound() : Results.Ok(updated);
});

usersApi.MapDelete("/{id:int}", async (int id, IUserRepository repo) => {
    var deleted = await repo.DeleteAsync(id);
    return deleted ? Results.NoContent() : Results.NotFound();
});

app.Run();

// ── MODELS ────────────────────────────────────────────────────────────────
public record User(int Id, string Username, string Email);

public record CreateUserRequest(
    [Required][MinLength(3)] string Username,
    [Required][EmailAddress] string Email
);

public record UpdateUserRequest(string? Username, string? Email);

// ── REPOSITORY ────────────────────────────────────────────────────────────
public interface IUserRepository {
    Task<IEnumerable<User>> GetAllAsync();
    Task<User?> GetByIdAsync(int id);
    Task<User> CreateAsync(User user);
    Task<User?> UpdateAsync(int id, UpdateUserRequest req);
    Task<bool> DeleteAsync(int id);
}

public class InMemoryUserRepository : IUserRepository {
    private readonly List<User> _users = new();
    private int _nextId = 1;

    public Task<IEnumerable<User>> GetAllAsync()
        => Task.FromResult<IEnumerable<User>>(_users);

    public Task<User?> GetByIdAsync(int id)
        => Task.FromResult(_users.FirstOrDefault(u => u.Id == id));

    public Task<User> CreateAsync(User user) {
        var created = user with { Id = _nextId++ };
        _users.Add(created);
        return Task.FromResult(created);
    }

    public Task<User?> UpdateAsync(int id, UpdateUserRequest req) {
        var idx = _users.FindIndex(u => u.Id == id);
        if (idx < 0) return Task.FromResult<User?>(null);

        var existing = _users[idx];
        var updated = existing with {
            Username = req.Username ?? existing.Username,
            Email    = req.Email    ?? existing.Email
        };
        _users[idx] = updated;
        return Task.FromResult<User?>(updated);
    }

    public Task<bool> DeleteAsync(int id) {
        int removed = _users.RemoveAll(u => u.Id == id);
        return Task.FromResult(removed > 0);
    }
}
```

---

### 🔵 Professional Workflow: CQRS with MediatR Pattern

```csharp
// Full CQRS (Command Query Responsibility Segregation) pattern:

// ── DOMAIN ────────────────────────────────────────────────────────────────
public record CreateOrderCommand(
    int CustomerId,
    List<OrderItem> Items,
    string? DiscountCode = null
) : IRequest<Result<int>>;

public record GetOrderQuery(int OrderId) : IRequest<Result<OrderDto>>;

// ── COMMAND HANDLER ───────────────────────────────────────────────────────
public class CreateOrderCommandHandler(
    IOrderRepository orderRepository,
    ICustomerRepository customerRepository,
    IDiscountService discountService,
    ILogger<CreateOrderCommandHandler> logger
) : IRequestHandler<CreateOrderCommand, Result<int>>
{
    public async Task<Result<int>> Handle(
        CreateOrderCommand command,
        CancellationToken cancellationToken)
    {
        var customer = await customerRepository
            .GetByIdAsync(command.CustomerId, cancellationToken);

        if (customer is null)
            return Result.Failure<int>($"Customer {command.CustomerId} not found");

        decimal discount = 0;
        if (command.DiscountCode is not null) {
            var discountResult = await discountService
                .ValidateAsync(command.DiscountCode, cancellationToken);
            if (!discountResult.IsSuccess)
                return Result.Failure<int>("Invalid discount code");
            discount = discountResult.Value;
        }

        var order = Order.Create(customer.Id, command.Items, discount);
        await orderRepository.SaveAsync(order, cancellationToken);

        logger.LogInformation("Order {OrderId} created for customer {CustomerId}",
            order.Id, customer.Id);

        return Result.Success(order.Id);
    }
}

// ── RESULT TYPE — Railway-oriented programming ────────────────────────────
public class Result<T> {
    public bool IsSuccess { get; }
    public T? Value { get; }
    public string? Error { get; }

    private Result(bool isSuccess, T? value, string? error) {
        IsSuccess = isSuccess;
        Value = value;
        Error = error;
    }

    public static Result<T> Success(T value) => new(true, value, null);
    public static Result<T> Failure(string error) => new(false, default, error);

    public Result<TNew> Map<TNew>(Func<T, TNew> transform) =>
        IsSuccess ? Result<TNew>.Success(transform(Value!))
                  : Result<TNew>.Failure(Error!);

    public async Task<Result<TNew>> BindAsync<TNew>(Func<T, Task<Result<TNew>>> bind) =>
        IsSuccess ? await bind(Value!) : Result<TNew>.Failure(Error!);
}
```

---

## 🧪 6. Hands-on Practice Projects

---

### 🟢 Beginner Project: Generic Observable Collection

```csharp
// ObservableList<T> — a list that fires events when modified
using System.Collections;
using System.Collections.Generic;

public class ObservableList<T> : IList<T> {
    private readonly List<T> _inner = new();

    public event Action<T>? ItemAdded;
    public event Action<T>? ItemRemoved;
    public event Action?    CollectionCleared;
    public event Action<int, T, T>? ItemReplaced; // index, old, new

    public void Add(T item) {
        _inner.Add(item);
        ItemAdded?.Invoke(item);
    }

    public bool Remove(T item) {
        bool removed = _inner.Remove(item);
        if (removed) ItemRemoved?.Invoke(item);
        return removed;
    }

    public void Clear() {
        _inner.Clear();
        CollectionCleared?.Invoke();
    }

    public T this[int index] {
        get => _inner[index];
        set {
            T old = _inner[index];
            _inner[index] = value;
            ItemReplaced?.Invoke(index, old, value);
        }
    }

    // Delegate remaining to inner list:
    public int Count => _inner.Count;
    public bool IsReadOnly => false;
    public bool Contains(T item) => _inner.Contains(item);
    public void CopyTo(T[] array, int arrayIndex) => _inner.CopyTo(array, arrayIndex);
    public int IndexOf(T item) => _inner.IndexOf(item);
    public void Insert(int index, T item) { _inner.Insert(index, item); ItemAdded?.Invoke(item); }
    public void RemoveAt(int index) { ItemRemoved?.Invoke(_inner[index]); _inner.RemoveAt(index); }
    public IEnumerator<T> GetEnumerator() => _inner.GetEnumerator();
    IEnumerator IEnumerable.GetEnumerator() => _inner.GetEnumerator();
}

// Test:
var list = new ObservableList<string>();
list.ItemAdded    += item => Console.WriteLine($"Added: {item}");
list.ItemRemoved  += item => Console.WriteLine($"Removed: {item}");
list.CollectionCleared += () => Console.WriteLine("Cleared!");

list.Add("apple");   // "Added: apple"
list.Add("banana");  // "Added: banana"
list.Remove("apple");// "Removed: apple"
list.Clear();        // "Cleared!"
```

✅ **You've succeeded when:** All CRUD operations on the list fire the appropriate events, and the list still works correctly as an `IList<T>` in LINQ queries.

---

### 🔵 Intermediate Project: Fluent Validation Builder

```csharp
// Type-safe fluent validation library from scratch:
public class ValidationBuilder<T> {
    private readonly List<(string PropertyName, Func<T, bool> Predicate, string Message)> _rules = new();

    public ValidationBuilder<T> RuleFor<TProp>(
        System.Linq.Expressions.Expression<Func<T, TProp>> property,
        Func<TProp, bool> predicate,
        string message)
    {
        var propName = ((System.Linq.Expressions.MemberExpression)property.Body).Member.Name;
        _rules.Add((propName, obj => predicate(property.Compile()(obj)), message));
        return this;
    }

    public ValidationResult Validate(T obj) {
        var errors = _rules
            .Where(rule => !rule.Predicate(obj))
            .Select(rule => new ValidationError(rule.PropertyName, rule.Message))
            .ToList();

        return errors.Any()
            ? ValidationResult.Failure(errors)
            : ValidationResult.Success();
    }
}

public record ValidationError(string Property, string Message);

public class ValidationResult {
    public bool IsValid { get; }
    public IReadOnlyList<ValidationError> Errors { get; }

    private ValidationResult(bool isValid, IReadOnlyList<ValidationError> errors) {
        IsValid = isValid;
        Errors = errors;
    }

    public static ValidationResult Success() => new(true, Array.Empty<ValidationError>());
    public static ValidationResult Failure(IList<ValidationError> errors) => new(false, errors.AsReadOnly());

    public void ThrowIfInvalid() {
        if (!IsValid) throw new ValidationException(string.Join("; ", Errors.Select(e => $"{e.Property}: {e.Message}")));
    }
}

// Usage:
record UserInput(string Username, string Email, int Age);

var validator = new ValidationBuilder<UserInput>()
    .RuleFor(u => u.Username, name => name.Length >= 3,
        "Username must be at least 3 characters")
    .RuleFor(u => u.Username, name => !string.IsNullOrWhiteSpace(name),
        "Username is required")
    .RuleFor(u => u.Email, email => email.Contains('@'),
        "Invalid email format")
    .RuleFor(u => u.Age, age => age is >= 0 and <= 150,
        "Age must be between 0 and 150");

var result = validator.Validate(new UserInput("Ar", "notanemail", 200));
foreach (var error in result.Errors)
    Console.WriteLine($"{error.Property}: {error.Message}");
```

---

### 🔴 Advanced Project: Mini Dependency Injection Container

```csharp
// A fully functional DI container from scratch:
public sealed class Container : IDisposable {
    private readonly Dictionary<Type, ServiceDescriptor> _registrations = new();
    private readonly Dictionary<Type, object> _singletons = new();
    private readonly List<IDisposable> _disposables = new();
    private bool _disposed;

    // Registration API:
    public Container AddSingleton<TService, TImplementation>()
        where TImplementation : TService
        => Register(typeof(TService), typeof(TImplementation), ServiceLifetime.Singleton);

    public Container AddTransient<TService, TImplementation>()
        where TImplementation : TService
        => Register(typeof(TService), typeof(TImplementation), ServiceLifetime.Transient);

    public Container AddSingleton<TService>(Func<Container, TService> factory)
        where TService : notnull {
        _registrations[typeof(TService)] = new(typeof(TService), null, factory as Func<Container, object>, ServiceLifetime.Singleton);
        return this;
    }

    private Container Register(Type serviceType, Type implType, ServiceLifetime lifetime) {
        _registrations[serviceType] = new(serviceType, implType, null, lifetime);
        return this;
    }

    // Resolution:
    public T Resolve<T>() where T : notnull => (T)Resolve(typeof(T));

    private object Resolve(Type type) {
        if (!_registrations.TryGetValue(type, out var descriptor))
            throw new InvalidOperationException($"No registration for {type.Name}");

        if (descriptor.Lifetime == ServiceLifetime.Singleton) {
            if (!_singletons.TryGetValue(type, out var existing)) {
                existing = Create(descriptor);
                _singletons[type] = existing;
                if (existing is IDisposable d) _disposables.Add(d);
            }
            return existing;
        }

        return Create(descriptor);
    }

    private object Create(ServiceDescriptor descriptor) {
        if (descriptor.Factory is not null)
            return descriptor.Factory(this);

        var implType = descriptor.ImplementationType!;
        var constructor = implType.GetConstructors()
            .OrderByDescending(c => c.GetParameters().Length)
            .First();

        var args = constructor.GetParameters()
            .Select(p => Resolve(p.ParameterType))
            .ToArray();

        return constructor.Invoke(args);
    }

    public void Dispose() {
        if (_disposed) return;
        _disposed = true;
        foreach (var d in _disposables) d.Dispose();
        _disposables.Clear();
    }

    enum ServiceLifetime { Singleton, Transient }
    record ServiceDescriptor(Type ServiceType, Type? ImplementationType, Func<Container, object>? Factory, ServiceLifetime Lifetime);
}

// Usage:
var container = new Container();
container
    .AddSingleton<ILogger, ConsoleLogger>()
    .AddSingleton<IUserRepository, SqlUserRepository>()
    .AddTransient<IUserService, UserService>();

var service = container.Resolve<IUserService>();
```

🔥 **Challenge:** Add scoped lifetime (single instance per scope), property injection, and interception/decoration support.

---

## ⚠️ 7. Common Mistakes

---

### ❌ Mistake 1: Blocking on Async Code (Deadlock!)

```csharp
// ❌ WRONG — .Result and .Wait() can deadlock in UI/ASP.NET contexts:
public string GetData() {
    return FetchDataAsync().Result;   // Deadlocks in ASP.NET!
    // Thread holds SynchronizationContext,
    // but async continuation needs it to resume — DEADLOCK!
}

public void ProcessData() {
    DoWorkAsync().Wait();  // Same problem!
}

// ✅ RIGHT — go async all the way up:
public async Task<string> GetDataAsync() {
    return await FetchDataAsync();  // Non-blocking!
}

// ✅ RIGHT — if you MUST call sync (e.g., in constructor), use proper patterns:
// ConfigureAwait(false) releases SynchronizationContext:
var result = FetchDataAsync().ConfigureAwait(false).GetAwaiter().GetResult();
// But still prefer async all the way
```

---

### ❌ Mistake 2: Not Disposing IDisposable Resources

```csharp
// ❌ WRONG — connection never closed if exception thrown:
HttpClient client = new HttpClient();
var data = client.GetStringAsync(url).Result;
client.Dispose();  // Never called if exception occurs!

// ❌ ALSO WRONG — creating new HttpClient per request (socket exhaustion!):
for (int i = 0; i < 1000; i++) {
    using var c = new HttpClient();  // 1000 sockets opened and TIME_WAIT state!
    await c.GetStringAsync(url);
}

// ✅ RIGHT — use using statement (calls Dispose() even on exception):
using var stream = File.OpenRead("file.txt");
var content = await new StreamReader(stream).ReadToEndAsync();
// stream.Dispose() called automatically at end of using block!

// ✅ RIGHT — HttpClient should be reused (singleton or via IHttpClientFactory):
// Register in DI: builder.Services.AddHttpClient();
// Inject IHttpClientFactory and create named clients
```

---

### ❌ Mistake 3: LINQ Deferred Execution Gotcha

```csharp
// ❌ WRONG — modifying source while iterating a LINQ query:
var numbers = new List<int> { 1, 2, 3, 4, 5 };
var query = numbers.Where(n => n > 2);  // LAZY — not executed yet!

numbers.Add(6);    // Modifies source BEFORE query executes
numbers.Remove(3);

foreach (var n in query) // Query executes HERE — sees modified list!
    Console.Write(n + " "); // "4 5 6" — not "3 4 5" as you might expect!

// ✅ RIGHT — materialize the query immediately with ToList/ToArray:
var query2 = numbers.Where(n => n > 2).ToList();  // Executes NOW
numbers.Add(6);   // Doesn't affect query2

// ❌ WRONG — executing the same LINQ query multiple times (performance bug):
var expensiveQuery = GetDataFromDb().Where(x => x.Active).OrderBy(x => x.Name);
var count = expensiveQuery.Count();      // DB hit #1
var first = expensiveQuery.First();     // DB hit #2
var list  = expensiveQuery.ToList();    // DB hit #3

// ✅ RIGHT — materialize once:
var data = GetDataFromDb().Where(x => x.Active).OrderBy(x => x.Name).ToList();
var count2  = data.Count;    // Memory only
var first2  = data.First();  // Memory only
```

---

### ❌ Mistake 4: Mutable Shared State in Async Code

```csharp
// ❌ WRONG — race condition on shared state:
private int _counter = 0;

async Task IncrementManyTimesAsync() {
    var tasks = Enumerable.Range(0, 1000)
        .Select(_ => Task.Run(() => _counter++));  // NOT thread-safe!
    await Task.WhenAll(tasks);
    Console.WriteLine(_counter); // Probably NOT 1000!
}

// ✅ RIGHT — use Interlocked for atomic operations:
private int _counter2 = 0;
Interlocked.Increment(ref _counter2);  // Thread-safe increment

// ✅ RIGHT — use lock:
private readonly object _lock = new();
lock (_lock) { _counter++; }

// ✅ RIGHT — use Interlocked.Add / CompareExchange:
Interlocked.Add(ref _counter2, 5);

// ✅ BEST for complex scenarios — use Channel<T> or ConcurrentQueue<T>:
var channel = System.Threading.Channels.Channel.CreateUnbounded<int>();
```

---

### ❌ Mistake 5: Catching Exception (Too Broad)

```csharp
// ❌ WRONG — catches everything including OutOfMemoryException:
try {
    DoWork();
} catch (Exception) {  // TOO BROAD!
    // Swallows ALL exceptions — including ones you can't recover from
}

// ❌ ALSO WRONG — empty catch:
try { DoWork(); } catch { }  // Silent failure!

// ✅ RIGHT — catch specific exceptions:
try {
    await FetchDataAsync();
} catch (HttpRequestException ex) {
    _logger.LogError(ex, "Network error fetching data");
    // Handle gracefully
} catch (TaskCanceledException ex) when (ex.InnerException is TimeoutException) {
    _logger.LogWarning("Request timed out");
    // Handle timeout specifically
} catch (OperationCanceledException) {
    // User cancelled — don't log as error
    throw; // Re-throw cancellation!
}
// Don't catch what you can't handle
```

---

### ❌ Mistake 6: String Concatenation in Loops

```csharp
// ❌ WRONG — O(n²) complexity! Creates new string every iteration:
string result = "";
for (int i = 0; i < 100_000; i++) {
    result += i.ToString();  // Creates 100,000 temporary strings!
}

// ✅ RIGHT — StringBuilder: O(n) complexity:
var sb = new StringBuilder();
for (int i = 0; i < 100_000; i++) {
    sb.Append(i);
}
string result2 = sb.ToString();

// ✅ EVEN BETTER for known data — string.Join or string.Concat:
string result3 = string.Join("", Enumerable.Range(0, 100_000));
string result4 = string.Concat(Enumerable.Range(0, 100_000).Select(i => i.ToString()));

// ✅ For interpolation in loops — use $"" only outside loops:
// Inside tight loops, use sb.AppendFormat or sb.Append directly
```

---

### ❌ Mistake 7: Not Using ConfigureAwait(false) in Libraries

```csharp
// In LIBRARY code (not application code), always use ConfigureAwait(false):
// ❌ WRONG in a library:
public async Task<Data> GetDataAsync() {
    var response = await httpClient.GetAsync(url); // May cause deadlock in callers!
    return await response.Content.ReadFromJsonAsync<Data>();
}

// ✅ RIGHT in a library:
public async Task<Data> GetDataAsync() {
    var response = await httpClient.GetAsync(url).ConfigureAwait(false);
    return await response.Content.ReadFromJsonAsync<Data>().ConfigureAwait(false);
}
// ConfigureAwait(false) = "I don't need to resume on the original context"
// Prevents deadlocks AND improves performance
// In application code (controllers, UI event handlers): ConfigureAwait(true) is fine
```

---

## 🔥 8. Pro Tips & Hidden Tricks

---

### 💎 Tip 1: `Span<T>` and `Memory<T>` — Zero-Copy Performance

```csharp
using System;

// Span<T> — a view into contiguous memory with no allocation:
void ProcessSpan() {
    int[] array = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

    // Span is a "view" — no new array allocated:
    Span<int> span = array;
    Span<int> firstFive = span[..5];   // View first 5
    Span<int> lastFive  = span[5..];   // View last 5

    // Modify through span modifies original array:
    firstFive[0] = 99;
    Console.WriteLine(array[0]);  // 99!

    // Stack-allocated span:
    Span<int> stackSpan = stackalloc int[10];  // On stack — ZERO GC pressure!
    for (int i = 0; i < 10; i++) stackSpan[i] = i;

    // String slicing without allocation:
    ReadOnlySpan<char> text = "Hello, World!".AsSpan();
    ReadOnlySpan<char> word = text[7..12]; // "World" — no new string allocated!

    // Parsing numbers from span (no allocation):
    ReadOnlySpan<char> num = "12345".AsSpan();
    int parsed = int.Parse(num);

    // Memory<T> — like Span but can be stored as a field, used in async:
    Memory<byte> buffer = new byte[1024];
    await stream.ReadAsync(buffer, cancellationToken);
    ReadOnlyMemory<byte> slice = buffer.Slice(0, bytesRead);
}

// High-performance string processing with spans:
static int CountChar(ReadOnlySpan<char> text, char target) {
    int count = 0;
    foreach (char c in text) if (c == target) count++;
    return count;
}

// Called with zero allocation:
CountChar("hello world".AsSpan(), 'l'); // 3
```

---

### 💎 Tip 2: `IAsyncDisposable` and `await using`

```csharp
// For resources that need async cleanup (DB connections, file streams):
public class DatabaseConnection : IAsyncDisposable {
    private readonly SqlConnection _connection;

    public DatabaseConnection(string connectionString) {
        _connection = new SqlConnection(connectionString);
    }

    public async Task OpenAsync(CancellationToken ct = default)
        => await _connection.OpenAsync(ct);

    public async ValueTask DisposeAsync() {
        await _connection.CloseAsync();
        await _connection.DisposeAsync();
    }
}

// Usage:
await using var db = new DatabaseConnection(connectionString);
await db.OpenAsync();
// ... use db ...
// db.DisposeAsync() called automatically!

// Combined sync + async disposal:
public class MixedResource : IDisposable, IAsyncDisposable {
    private Stream? _stream;

    public void Dispose() {
        _stream?.Dispose();
    }

    public async ValueTask DisposeAsync() {
        if (_stream is not null) await _stream.DisposeAsync();
    }
}
```

---

### 💎 Tip 3: Source Generators — Zero-Overhead Code Generation

```csharp
// Source generators run at COMPILE TIME and generate code you'd otherwise write manually.
// The generated code has ZERO runtime overhead!

// Built-in source generators in .NET:

// 1. System.Text.Json — AOT-compatible serialization:
[JsonSerializable(typeof(User))]
[JsonSerializable(typeof(List<User>))]
public partial class AppJsonContext : JsonSerializerContext { }

// Generated serializer — 10x faster than reflection-based!
var json = JsonSerializer.Serialize(user, AppJsonContext.Default.User);
var user2 = JsonSerializer.Deserialize(json, AppJsonContext.Default.User);

// 2. LoggerMessage — high-performance structured logging:
public partial class UserService {
    private readonly ILogger<UserService> _logger;

    [LoggerMessage(Level = LogLevel.Information, Message = "User {UserId} created")]
    private partial void LogUserCreated(int userId);  // Generated at compile time!

    [LoggerMessage(Level = LogLevel.Error, Message = "Failed to find user {UserId}")]
    private partial void LogUserNotFound(int userId);
}

// 3. Regex source generator (C# 7+):
public partial class Parser {
    [GeneratedRegex(@"^\d{3}-\d{4}$", RegexOptions.Compiled)]
    private static partial Regex PhonePattern();  // Compile-time Regex!

    public bool IsValidPhone(string phone)
        => PhonePattern().IsMatch(phone);  // Much faster than new Regex(...)!
}

// 4. IIncrementalGenerator — write your own:
// Source generators read your code's syntax tree (Roslyn) and output C# code
// Use cases: ORM mappings, API clients, serializers, validators
```

---

### 💎 Tip 4: `Channel<T>` — The Go Channel for C#

```csharp
using System.Threading.Channels;

// Channel<T> is C#'s equivalent of Go channels — producer/consumer pipeline:
async Task ChannelPipeline() {
    // Bounded channel — blocks producer when full (backpressure!):
    var channel = Channel.CreateBounded<WorkItem>(new BoundedChannelOptions(100) {
        FullMode = BoundedChannelFullMode.Wait,           // Wait when full
        SingleReader = false,
        SingleWriter = false
    });

    // Unbounded (careful — can grow without limit):
    var unbounded = Channel.CreateUnbounded<WorkItem>(new UnboundedChannelOptions {
        SingleReader = true  // Optimization hint
    });

    // PRODUCER:
    async Task Produce(ChannelWriter<WorkItem> writer) {
        try {
            for (int i = 0; i < 1000; i++) {
                await writer.WriteAsync(new WorkItem(i));    // Blocks if full
                await Task.Delay(10);
            }
        } finally {
            writer.Complete();  // Signal: no more items!
        }
    }

    // CONSUMER:
    async Task Consume(ChannelReader<WorkItem> reader) {
        await foreach (var item in reader.ReadAllAsync()) {  // Iterates until Complete()!
            await ProcessItemAsync(item);
        }
    }

    // Multiple consumers (fan-out):
    var producers = new[] { Produce(channel.Writer), Produce(channel.Writer) };
    var consumers = Enumerable.Range(0, 4)
        .Select(_ => Consume(channel.Reader))
        .ToArray();

    await Task.WhenAll(producers);
    await Task.WhenAll(consumers);
}

// Pipeline pattern with multiple channels:
async Task Pipeline(IEnumerable<int> input) {
    var stage1 = Channel.CreateBounded<int>(50);
    var stage2 = Channel.CreateBounded<string>(50);

    async Task StageOneAsync() {
        await foreach (var n in stage1.Reader.ReadAllAsync())
            await stage2.Writer.WriteAsync(n.ToString());
        stage2.Writer.Complete();
    }

    // ... connect stages
}
```

---

### 💎 Tip 5: Interceptors and Attributes for AOP

```csharp
// Aspect-Oriented Programming via attributes + DispatchProxy:

// Define the cross-cutting concern (attribute):
[AttributeUsage(AttributeTargets.Method)]
public class LogAttribute : Attribute {
    public LogLevel Level { get; init; } = LogLevel.Information;
}

[AttributeUsage(AttributeTargets.Method)]
public class RetryAttribute(int maxAttempts = 3, int delayMs = 100) : Attribute {
    public int MaxAttempts { get; } = maxAttempts;
    public int DelayMs { get; } = delayMs;
}

// Intercepting proxy:
public class LoggingProxy<T> : DispatchProxy where T : class {
    private T? _target;
    private ILogger? _logger;

    protected override object? Invoke(System.Reflection.MethodInfo? method, object?[]? args) {
        var logAttr = method?.GetCustomAttribute<LogAttribute>();

        if (logAttr is not null)
            _logger?.Log(logAttr.Level, "Calling {Method}", method?.Name);

        try {
            var result = method?.Invoke(_target, args);
            if (logAttr is not null)
                _logger?.Log(logAttr.Level, "{Method} completed", method?.Name);
            return result;
        } catch (Exception ex) {
            _logger?.LogError(ex, "{Method} failed", method?.Name);
            throw;
        }
    }

    public static T Create(T target, ILogger logger) {
        var proxy = Create<T, LoggingProxy<T>>();
        ((LoggingProxy<T>)(object)proxy)._target = target;
        ((LoggingProxy<T>)(object)proxy)._logger = logger;
        return proxy;
    }
}

// Usage:
public interface IOrderService {
    [Log(Level = LogLevel.Information)]
    [Retry(maxAttempts: 3)]
    Task<Order> PlaceOrderAsync(OrderRequest request);
}

var service = LoggingProxy<IOrderService>.Create(new OrderService(), logger);
await service.PlaceOrderAsync(request);  // All calls logged automatically!
```

---

## 🚀 9. Advanced Concepts (Expert Level)

---

### Advanced Concept 1: Expression Trees — Code as Data

```csharp
using System.Linq.Expressions;

// Expression trees represent code as DATA — inspectable and transformable at runtime!
// Used by: Entity Framework (SQL generation), AutoMapper, FluentValidation, LINQ providers

// Create an expression tree:
Expression<Func<int, int, int>> addExpr = (x, y) => x + y;

// Inspect it:
var body = (BinaryExpression)addExpr.Body;
Console.WriteLine(body.NodeType);   // Add
Console.WriteLine(((ParameterExpression)body.Left).Name);  // "x"
Console.WriteLine(((ParameterExpression)body.Right).Name); // "y"

// Compile and execute:
Func<int, int, int> addFunc = addExpr.Compile();
Console.WriteLine(addFunc(3, 4));   // 7

// Build expression trees programmatically:
var x = Expression.Parameter(typeof(int), "x");
var y = Expression.Parameter(typeof(int), "y");
var add = Expression.Add(x, y);
var lambda = Expression.Lambda<Func<int, int, int>>(add, x, y);
var compiled = lambda.Compile();
Console.WriteLine(compiled(5, 3));  // 8

// Translate expression to SQL (how EF Core works):
public static string ToSqlWhere<T>(Expression<Func<T, bool>> predicate) {
    if (predicate.Body is BinaryExpression binary) {
        var left = ((MemberExpression)binary.Left).Member.Name;
        var op = binary.NodeType switch {
            ExpressionType.Equal              => "=",
            ExpressionType.NotEqual           => "!=",
            ExpressionType.GreaterThan        => ">",
            ExpressionType.LessThan           => "<",
            ExpressionType.GreaterThanOrEqual => ">=",
            ExpressionType.LessThanOrEqual    => "<=",
            _ => throw new NotSupportedException()
        };
        var right = Expression.Lambda(binary.Right).Compile().DynamicInvoke();
        return $"WHERE {left} {op} '{right}'";
    }
    throw new NotSupportedException();
}

Expression<Func<User, bool>> filter = u => u.Age > 18;
string sql = ToSqlWhere(filter);  // "WHERE Age > '18'"
```

---

### Advanced Concept 2: The CLR Memory Model & GC Internals

```csharp
// Understanding the CLR helps write faster, GC-friendlier code:

/*
   CLR GC Generations:
   Gen0 (< 256KB): Short-lived objects — collected very frequently (milliseconds)
   Gen1 (2MB):     Objects that survived Gen0 — medium-lived
   Gen2 (Unlimited): Long-lived objects, static data — collected rarely

   Large Object Heap (LOH):
   Objects >= 85,000 bytes go directly to Gen2 (NOT compacted by default!)
   → Avoid allocating large objects frequently — causes fragmentation

   Rules for GC-friendly code:
   1. Allocate and discard quickly (Gen0 is cheap)
   2. Avoid LOH allocations in hot paths — use ArrayPool<T>!
   3. Use struct for small, short-lived data (value type = no heap)
   4. Use object pooling for frequently created objects
*/

// ArrayPool — reuse arrays without allocating:
using System.Buffers;

async Task ProcessData(Stream stream) {
    byte[] buffer = ArrayPool<byte>.Shared.Rent(4096); // Borrow from pool
    try {
        int read = await stream.ReadAsync(buffer.AsMemory(0, 4096));
        ProcessBytes(buffer.AsSpan(0, read));
    } finally {
        ArrayPool<byte>.Shared.Return(buffer); // Return to pool — no GC!
    }
}

// MemoryPool<T> — for larger slices:
using var memoryOwner = MemoryPool<byte>.Shared.Rent(minimumLength: 1024);
Memory<byte> memory = memoryOwner.Memory;

// ObjectPool (Microsoft.Extensions.ObjectPool):
using Microsoft.Extensions.ObjectPool;
var policy = new DefaultPooledObjectPolicy<StringBuilder>();
var pool = new DefaultObjectPool<StringBuilder>(policy);

StringBuilder sb = pool.Get();
try {
    sb.Clear();
    sb.Append("Hello");
    string result = sb.ToString();
} finally {
    pool.Return(sb); // Return to pool
}

// GC.Collect — when to call (almost never!):
GC.Collect();                              // Force full GC — avoid!
GC.Collect(0, GCCollectionMode.Forced);   // Force Gen0 only
GC.SuppressFinalize(this);               // Tell GC not to call finalizer
GC.KeepAlive(obj);                        // Prevent GC during native interop
GC.GetTotalMemory(forceFullCollection: false); // Current memory usage
GC.GetGCMemoryInfo();                      // Detailed GC statistics
```

---

### Advanced Concept 3: Unsafe Code and Native Interop

```csharp
// Unsafe code — direct memory manipulation (use only when necessary!):

unsafe void UnsafeExample() {
    int x = 42;
    int* ptr = &x;          // Pointer to x
    Console.WriteLine(*ptr); // 42
    *ptr = 100;
    Console.WriteLine(x);   // 100

    // Fixed statement — pin managed object for native interop:
    byte[] array = new byte[100];
    fixed (byte* p = array) {
        // p is stable pointer to array[0]
        // Can pass to native code!
        FillNative(p, 100);
    }

    // Pointer arithmetic:
    int[] nums = {1, 2, 3, 4, 5};
    fixed (int* start = nums) {
        for (int i = 0; i < 5; i++)
            Console.Write(*(start + i) + " ");
    }
}

// Unmanaged type constraint:
unsafe static T ReadUnmanaged<T>(byte[] data, int offset) where T : unmanaged {
    fixed (byte* ptr = &data[offset]) {
        return *(T*)ptr;
    }
}

// P/Invoke — call native DLL functions:
using System.Runtime.InteropServices;

public static partial class NativeMethods {
    [LibraryImport("kernel32.dll", SetLastError = true)]  // C# 9 source-gen P/Invoke
    public static partial int GetCurrentProcessId();

    [LibraryImport("libc", StringMarshalling = StringMarshalling.Utf8)]
    public static partial int printf(string format, int value);

    [DllImport("user32.dll", CharSet = CharSet.Unicode)]  // Classic P/Invoke
    public static extern int MessageBox(IntPtr hWnd, string text, string caption, uint type);
}

// Interop with structs:
[StructLayout(LayoutKind.Sequential, Pack = 1)]  // Match C struct layout!
struct Point {
    public int X;
    public int Y;
}

// COM Interop (Windows-only):
// [ComImport][Guid("...")][InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
// public interface IComInterface { void Method(); }
```

---

### Advanced Concept 4: Roslyn Analyzers — Custom Compiler Checks

```csharp
// Write your own compiler warnings and errors!
// Add to a separate analyzer project (netstandard2.0):

using Microsoft.CodeAnalysis;
using Microsoft.CodeAnalysis.CSharp;
using Microsoft.CodeAnalysis.CSharp.Syntax;
using Microsoft.CodeAnalysis.Diagnostics;
using System.Collections.Immutable;

[DiagnosticAnalyzer(LanguageNames.CSharp)]
public class NullCheckAnalyzer : DiagnosticAnalyzer {
    private static readonly DiagnosticDescriptor Rule = new(
        id: "MY001",
        title: "Potential null dereference",
        messageFormat: "'{0}' might be null — consider null check",
        category: "Safety",
        defaultSeverity: DiagnosticSeverity.Warning,
        isEnabledByDefault: true,
        description: "Checks for potential null dereferences.");

    public override ImmutableArray<DiagnosticDescriptor> SupportedDiagnostics
        => ImmutableArray.Create(Rule);

    public override void Initialize(AnalysisContext context) {
        context.ConfigureGeneratedCodeAnalysis(GeneratedCodeAnalysisFlags.None);
        context.EnableConcurrentExecution();
        context.RegisterSyntaxNodeAction(AnalyzeMemberAccess, SyntaxKind.SimpleMemberAccessExpression);
    }

    private static void AnalyzeMemberAccess(SyntaxNodeAnalysisContext context) {
        var memberAccess = (MemberAccessExpressionSyntax)context.Node;
        var symbol = context.SemanticModel.GetTypeInfo(memberAccess.Expression);

        if (symbol.Nullability.FlowState == NullableFlowState.MaybeNull) {
            context.ReportDiagnostic(
                Diagnostic.Create(Rule, memberAccess.GetLocation(),
                    memberAccess.Expression));
        }
    }
}
// Package as NuGet analyzer → consumers get automatic warnings in their IDE!
```

---

### ⚡ Performance & Optimization Table

| Technique                               | Impact   | When to Use                                        |
|-----------------------------------------|----------|----------------------------------------------------|
| `Span<T>` / `Memory<T>` instead of array slices | Very High | Hot paths — zero allocation string/array work  |
| `ArrayPool<byte>.Shared.Rent()`         | Very High | Large temporary buffers in I/O-heavy code          |
| `struct` vs `class` for small value objects | High  | Objects with < 16 bytes and short lifetime         |
| `sealed` on classes                     | Medium   | Enables JIT devirtualization                       |
| `readonly struct`                       | Medium   | Prevents defensive copies in hot paths             |
| `ConfigureAwait(false)` in libraries    | Medium   | Releases SynchronizationContext — avoids deadlocks |
| `ValueTask<T>` over `Task<T>`          | High     | When operation is often synchronous                |
| Source-generated JSON serialization     | Very High | AOT and startup performance                        |
| `StringComparison.Ordinal`              | Medium   | 20-40% faster than culture-aware comparison        |
| `string.AsSpan()` for parsing          | High     | Zero-allocation substring operations               |
| PGO (Profile-Guided Optimization)       | High     | .NET 8+ ships with Dynamic PGO by default          |
| `[SkipLocalsInit]`                     | Low      | Skip zero-initialization of local variables        |

---

## 💀 10. 0.01% Hidden Secrets — Ultra Elite

---

### 🔮 Secret 1: `ref struct` and `ref return` — Stack-Only Types

```csharp
// ref struct — can only live on the stack, cannot be boxed, cannot be async field:
// This is how Span<T> is implemented!
ref struct MySpan {
    private readonly ref int _start;
    private readonly int _length;

    public MySpan(int[] array) {
        _start = ref array[0];
        _length = array.Length;
    }

    public ref int this[int index] {
        get {
            if ((uint)index >= (uint)_length)
                throw new IndexOutOfRangeException();
            return ref Unsafe.Add(ref _start, index);
        }
    }

    public int Length => _length;
}

// ref return — return a reference to a variable (can modify the original!):
static ref int FindFirst(int[] array, int value) {
    for (int i = 0; i < array.Length; i++)
        if (array[i] == value) return ref array[i]; // Return ref to array element!
    throw new InvalidOperationException("Not found");
}

int[] data = {1, 2, 3, 4, 5};
ref int found = ref FindFirst(data, 3);
found = 99;  // Modifies data[2]!
Console.WriteLine(data[2]);  // 99

// ref readonly return — return reference but prevent modification:
static ref readonly int GetMax(int[] a) {
    ref int max = ref a[0];
    foreach (ref int item in a.AsSpan())
        if (item > max) max = ref item;
    return ref max;
}
```

---

### 🔮 Secret 2: Caller Information Attributes

```csharp
using System.Runtime.CompilerServices;

// These attributes inject call-site info at compile time — ZERO runtime cost!
public static void Log(
    string message,
    [CallerMemberName] string memberName = "",
    [CallerFilePath]   string filePath = "",
    [CallerLineNumber] int lineNumber = 0,
    [CallerArgumentExpression(nameof(message))] string? expr = null)
{
    Console.WriteLine($"[{Path.GetFileName(filePath)}:{lineNumber}] {memberName}: {message}");
    Console.WriteLine($"  Expression: {expr}");
}

// Called as:
Log("Hello!");
// Outputs: "[Program.cs:42] Main: Hello!"
//          "  Expression: \"Hello!\""

// CallerArgumentExpression — C# 10+:
static void Assert(bool condition,
    [CallerArgumentExpression(nameof(condition))] string? expr = null)
{
    if (!condition)
        throw new AssertionException($"Assertion failed: {expr}");
}

int x = 5;
Assert(x > 10);  // Throws: "Assertion failed: x > 10"
// The expression text "x > 10" captured at compile time!

// INotifyPropertyChanged the right way:
public class ViewModel : INotifyPropertyChanged {
    public event PropertyChangedEventHandler? PropertyChanged;

    protected void SetProperty<T>(ref T field, T value,
        [CallerMemberName] string propertyName = "")
    {
        if (!EqualityComparer<T>.Default.Equals(field, value)) {
            field = value;
            PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
        }
    }

    private string _name = "";
    public string Name {
        get => _name;
        set => SetProperty(ref _name, value); // propertyName = "Name" auto-injected!
    }
}
```

---

### 🔮 Secret 3: `System.Runtime.CompilerServices.Unsafe` — Direct Memory

```csharp
using System.Runtime.CompilerServices;

// Unsafe class — zero-cost memory operations, no unsafe keyword needed!

// SizeOf<T>() — size at runtime:
int size = Unsafe.SizeOf<DateTime>();  // 8
int size2 = Unsafe.SizeOf<Guid>();     // 16

// As<T>() — reinterpret bytes (type-punning without unsafe):
float f = 3.14f;
int bits = Unsafe.As<float, int>(ref f);   // Same bits, different type interpretation
// This is safe because float and int are same size (4 bytes)

// Add<T>() — pointer arithmetic without unsafe:
ref int first = ref array[0];
ref int third = ref Unsafe.Add(ref first, 2);  // array[2]!
third = 99;

// SkipInit<T>() — skip default initialization:
Unsafe.SkipInit(out int uninitialized);  // Faster — but dangerous if you read before write!

// IsNullRef<T>() — check if reference is null:
if (Unsafe.IsNullRef(ref someRef)) { }

// NullRef<T>() — create a null reference (advanced use!):
ref int nullRef = ref Unsafe.NullRef<int>();

// Real use case — fast struct copy:
void FastCopy<T>(ref T source, ref T destination) where T : struct
    => Unsafe.CopyBlockUnaligned(
        ref Unsafe.As<T, byte>(ref destination),
        ref Unsafe.As<T, byte>(ref source),
        (uint)Unsafe.SizeOf<T>());
```

---

### 🔮 Secret 4: `InlineArray` — Stack-Allocated Fixed-Size Arrays (C# 12)

```csharp
using System.Runtime.CompilerServices;

// InlineArray — like a fixed-size array embedded directly in a struct!
// No heap allocation, SIMD-friendly, zero overhead

[InlineArray(4)]
struct Vector4 {
    private float _element;  // Just one field — InlineArray generates the rest!
}

// Usage:
var v = new Vector4();
v[0] = 1.0f;
v[1] = 2.0f;
v[2] = 3.0f;
v[3] = 4.0f;

// Works with foreach and span operations:
foreach (float f in v) Console.Write(f + " ");  // 1 2 3 4

Span<float> span = v;   // Get span without allocation!
float sum = 0;
foreach (float f in span) sum += f;

// InlineArray is how System.Runtime.Intrinsics.Vector128<T> is implemented!
// Perfect for: fixed-size buffers, SIMD vectors, ring buffers on stack

[InlineArray(256)]
struct FixedBuffer256 {
    private byte _element;
}
```

---

### 🔮 Secret 5: `IEnumerable<T>` vs `IQueryable<T>` — The Critical Difference

```csharp
// This distinction is THE most common performance mistake in .NET:

// IEnumerable<T> — executes IN MEMORY (C# / LINQ to Objects):
IEnumerable<User> localQuery = dbContext.Users
    .AsEnumerable()             // Loads ALL users into memory first!
    .Where(u => u.Age > 18);    // THEN filters in C#

// IQueryable<T> — executes AT THE SOURCE (EF Core / SQL):
IQueryable<User> dbQuery = dbContext.Users
    .Where(u => u.Age > 18);   // Translates to: SELECT * FROM Users WHERE Age > 18
                               // Only matching rows travel over the network!

// Rule: Keep queries as IQueryable as long as possible!
// Only call ToList()/First()/Count() when you need the data.

// The killer example:
// ❌ WRONG — loads 1M users, then filters in C#:
var adults1 = dbContext.Users.AsEnumerable().Where(u => u.Age > 18).ToList();

// ✅ RIGHT — SQL does the filtering, only adults come back:
var adults2 = dbContext.Users.Where(u => u.Age > 18).ToList();

// What can and can't be translated to SQL:
IQueryable<User> canTranslate = dbContext.Users
    .Where(u => u.Email.Contains("@gmail"))    // ✅ LIKE '%@gmail%'
    .Where(u => u.CreatedAt.Year == 2025)      // ✅ YEAR(CreatedAt) = 2025
    .OrderBy(u => u.LastName)                  // ✅ ORDER BY
    .Take(10);                                  // ✅ TOP 10

// If EF can't translate, it loads everything into memory (dangerous!):
IQueryable<User> cannotTranslate = dbContext.Users
    .Where(u => MyCustomMethod(u.Name));  // ❌ Loads ALL users, filters in memory!
```

---

### 🔮 Secret 6: `[StructLayout]` — Control Memory Layout

```csharp
using System.Runtime.InteropServices;

// Explicit layout — manual field offsets (for unions or C interop):
[StructLayout(LayoutKind.Explicit, Size = 4)]
struct FloatIntUnion {
    [FieldOffset(0)] public float FloatValue;
    [FieldOffset(0)] public int   IntBits;    // SAME bytes as FloatValue!
}

var u = new FloatIntUnion { FloatValue = 3.14f };
Console.WriteLine(u.IntBits.ToString("X8")); // 4048F5C3 — IEEE 754 bits!

// Sequential layout — ensure predictable field order (default for structs):
[StructLayout(LayoutKind.Sequential, Pack = 1)]  // No padding!
struct NetworkPacket {
    public byte   Type;       // Offset 0
    public ushort Length;     // Offset 1
    public uint   Checksum;   // Offset 3
    public byte   Flags;      // Offset 7
}
// Total: 8 bytes — matches wire format exactly!

// Checking struct layout:
Console.WriteLine(Marshal.OffsetOf<NetworkPacket>("Length"));   // 1
Console.WriteLine(Marshal.SizeOf<NetworkPacket>());             // 8

// Important for:
// 1. Network protocols — match wire format
// 2. File formats — binary I/O
// 3. Hardware registers — embedded/IoT
// 4. SIMD operations — alignment requirements
// 5. C library interop — match C struct layout
```

---

### 🔮 Secret 7: Compile-Time String Formatting with Interpolated String Handlers

```csharp
using System.Runtime.CompilerServices;

// C# 10+ allows creating custom interpolated string handlers —
// zero allocation string building at compile time!

// This is how Microsoft.Extensions.Logging avoids allocating log strings
// when the log level is disabled!

[InterpolatedStringHandler]
public ref struct ConditionalInterpolatedStringHandler {
    private readonly StringBuilder? _builder;

    public ConditionalInterpolatedStringHandler(
        int literalLength, int formattedCount, bool condition,
        out bool shouldAppend) {
        shouldAppend = condition;
        _builder = condition ? new StringBuilder(literalLength) : null;
    }

    public void AppendLiteral(string value) => _builder?.Append(value);

    public void AppendFormatted<T>(T value) => _builder?.Append(value);

    public override string ToString() => _builder?.ToString() ?? "";
}

// A method using it:
public static void LogIfEnabled(
    bool enabled,
    [InterpolatedStringHandlerArgument(nameof(enabled))]
    ConditionalInterpolatedStringHandler message)
{
    if (enabled) Console.WriteLine(message.ToString());
}

// MAGIC: if enabled is false, the string is NEVER formatted/allocated!
bool verbose = false;
LogIfEnabled(verbose, $"Expensive: {ExpensiveComputation()}");
// ↑ ExpensiveComputation() is NEVER CALLED if verbose is false!
// The compiler generates code that skips everything!
```

---

### 🔮 Secret 8: `Reflection.Emit` — Runtime Code Generation

```csharp
using System.Reflection;
using System.Reflection.Emit;

// Generate IL bytecode at runtime — create methods, types, assemblies dynamically!

// Create a dynamic method at runtime:
var method = new DynamicMethod("Add", typeof(int), new[] { typeof(int), typeof(int) });
var il = method.GetILGenerator();

il.Emit(OpCodes.Ldarg_0);     // Load arg0
il.Emit(OpCodes.Ldarg_1);     // Load arg1
il.Emit(OpCodes.Add);         // Add them
il.Emit(OpCodes.Ret);         // Return

var addDelegate = (Func<int, int, int>)method.CreateDelegate(typeof(Func<int, int, int>));
Console.WriteLine(addDelegate(3, 4));  // 7

// Create a dynamic type at runtime:
var assemblyBuilder = AssemblyBuilder.DefineDynamicAssembly(
    new AssemblyName("DynamicAssembly"),
    AssemblyBuilderAccess.Run);

var moduleBuilder = assemblyBuilder.DefineDynamicModule("DynamicModule");

var typeBuilder = moduleBuilder.DefineType("DynamicClass",
    TypeAttributes.Public | TypeAttributes.Class);

// Add a property:
var fieldBuilder = typeBuilder.DefineField("_value", typeof(int), FieldAttributes.Private);
var propBuilder = typeBuilder.DefineProperty("Value", PropertyAttributes.HasDefault, typeof(int), null);

var getterBuilder = typeBuilder.DefineMethod("get_Value",
    MethodAttributes.Public | MethodAttributes.SpecialName, typeof(int), Type.EmptyTypes);
var getterIL = getterBuilder.GetILGenerator();
getterIL.Emit(OpCodes.Ldarg_0);
getterIL.Emit(OpCodes.Ldfld, fieldBuilder);
getterIL.Emit(OpCodes.Ret);
propBuilder.SetGetMethod(getterBuilder);

var dynamicType = typeBuilder.CreateType()!;
var instance = Activator.CreateInstance(dynamicType)!;
// ... use instance

// Real use cases: ORMs, serializers, proxy generators (Castle DynamicProxy),
// compiled expression caches (EF Core change tracking)
```

---

### 🔮 Secret 9: `System.Threading.Channels` Advanced Patterns

```csharp
// The Pipes API — even lower level than channels, for raw I/O:
using System.IO.Pipelines;

async Task PipelineDemo(Stream stream) {
    var pipe = new Pipe();

    // Writer task — reads from stream and writes to pipe:
    async Task WritePipeAsync(PipeWriter writer) {
        while (true) {
            Memory<byte> buffer = writer.GetMemory(4096);  // Request buffer from pipe!
            int read = await stream.ReadAsync(buffer);
            if (read == 0) break;
            writer.Advance(read);                          // Tell pipe how much we wrote
            var result = await writer.FlushAsync();
            if (result.IsCompleted) break;
        }
        await writer.CompleteAsync();
    }

    // Reader task — reads from pipe and processes:
    async Task ReadPipeAsync(PipeReader reader) {
        while (true) {
            ReadResult result = await reader.ReadAsync();
            ReadOnlySequence<byte> buffer = result.Buffer;

            // Process buffer without copying:
            foreach (ReadOnlyMemory<byte> segment in buffer) {
                ProcessSegment(segment.Span);    // Zero copy!
            }

            reader.AdvanceTo(buffer.End);        // Mark consumed
            if (result.IsCompleted) break;
        }
    }

    await Task.WhenAll(
        WritePipeAsync(pipe.Writer),
        ReadPipeAsync(pipe.Reader)
    );
}

// This is how ASP.NET Core's Kestrel handles HTTP connections internally!
// Zero-copy I/O — buffers are reused across reads
```

---

### 🔮 Secret 10: `[ModuleInitializer]` — Code That Runs Before Main

```csharp
using System.Runtime.CompilerServices;

// ModuleInitializer — executes before any code in the assembly, including Main!
// Called exactly once when the module is first loaded.

public static class AppInitializer {
    [ModuleInitializer]
    internal static void Initialize() {
        // Register type converters, custom serializers, etc.
        TypeDescriptor.AddAttributes(typeof(MyType), new ConvertableAttribute());

        // Configure thread pool:
        ThreadPool.SetMinThreads(100, 100);

        // Register custom exception handlers:
        AppDomain.CurrentDomain.UnhandledException += (_, e) =>
            Console.Error.WriteLine($"Fatal: {e.ExceptionObject}");

        Console.WriteLine("Module initialized!"); // Before Main!
    }
}

// Multiple ModuleInitializers are allowed (execution order = undefined):
public class AnotherInitializer {
    [ModuleInitializer]
    internal static void Setup() {
        // This runs before Main too!
        // Used by: logging frameworks, DI bootstrappers, code generators
    }
}
```

---

## 🗺️ 11. Complete Roadmap

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — FOUNDATION (Week 1-3)
├── Week 1: Syntax, types, variables, string interpolation, control flow
├── Week 2: Functions, classes, OOP (inheritance, interfaces, abstract)
└── Week 3: Collections (List, Dictionary, HashSet), LINQ basics
    └── Project: Console to-do app, simple calculator, word frequency counter

PHASE 2 — MODERN C# (Week 4-7)
├── Week 4: Records, pattern matching, switch expressions, nullable types
├── Week 5: Async/await, Task, CancellationToken, async streams
├── Week 6: Generics, delegates, Func/Action, lambda expressions
└── Week 7: Extension methods, LINQ advanced, PLINQ
    └── Project: REST API with ASP.NET Core Minimal API

PHASE 3 — ADVANCED (Week 8-12)
├── Week 8:  ASP.NET Core — middleware, DI, configuration, logging
├── Week 9:  Entity Framework Core — Code First, migrations, LINQ to SQL
├── Week 10: Testing — xUnit, Moq, FluentAssertions
├── Week 11: Channels, Span<T>, ArrayPool, performance profiling
└── Week 12: Source generators, attributes, reflection
    └── Project: Full-stack app with EF Core, Auth, Tests

PHASE 4 — EXPERT / 0.01% (Month 4-6)
├── Month 4: Expression trees, Roslyn analyzers, compilation model
├── Month 5: Unsafe code, P/Invoke, Reflection.Emit, CLR internals
└── Month 6: Contribute to .NET runtime / ASP.NET Core / Write a NuGet library
    └── Project: Open-source library or production SaaS product
```

---

### 🏁 Milestone Checklist

- [ ] I understand the difference between value types and reference types
- [ ] I can write async/await correctly without blocking or deadlocking
- [ ] I know LINQ inside out — deferred execution, IQueryable vs IEnumerable
- [ ] I use records for immutable data and understand `with` expressions
- [ ] I can write generic classes and methods with constraints
- [ ] I understand and use `IDisposable` / `using` correctly
- [ ] I've built a working ASP.NET Core REST API
- [ ] I've written unit tests with xUnit and Moq
- [ ] I can use `Span<T>` for zero-allocation hot paths
- [ ] I understand pattern matching and use it to eliminate null checks
- [ ] I've published a NuGet package or contributed to an open-source C# project
- [ ] I can profile .NET applications with dotnet-trace and BenchmarkDotNet

---

## 🧩 12. Bonus Deep Insights

---

### 🔮 Mental Model: "C# is Designed for the 'Pit of Success'"

Anders Hejlsberg and the C# team explicitly design for the **"pit of success"** — the language should make the right thing easy and the wrong thing hard. Examples:

- **Nullable reference types** — the null-safe option requires explicit `?`; the common case is non-null
- **`using` for IDisposable** — forgetting to clean up is harder than remembering
- **`async`/`await`** — async code reads like sync code, so developers naturally write non-blocking code
- **Records** — immutable by default prevents accidental mutation bugs
- **Pattern matching** — exhaustive switches with `_` catch-all prevent silent failures

Every language version asks: "How can we make common correct patterns easier?"

---

### 🤫 Deep Insight 1: The CLR Is Not Just a Runtime

The Common Language Runtime is an abstract machine specification. **Any language that compiles to IL runs on the CLR** — F#, VB.NET, IronPython, and even languages you create yourself. They all share:
- The same GC
- The same JIT
- The same type system
- The same assemblies (one DLL, many languages!)

This means C# code can call F# code which calls VB.NET code — seamlessly, with zero marshalling cost. It's the most successful polyglot runtime ever created.

---

### 🤫 Deep Insight 2: `async/await` Is Compiler Magic

When you write `await someTask`, the compiler transforms your method into a **state machine** — a class with a `MoveNext()` method that resumes from where it left off. There is no blocked thread. The continuation is scheduled on the thread pool when the task completes.

```csharp
// What YOU write:
async Task<int> GetValueAsync() {
    int x = await Task.Delay(100).ContinueWith(_ => 42);
    return x * 2;
}

// What the COMPILER generates (simplified):
class GetValueAsyncStateMachine : IAsyncStateMachine {
    public int state;
    public TaskCompletionSource<int> builder;
    private int x;

    public void MoveNext() {
        switch (state) {
            case 0:
                // Start Task.Delay(100)...
                state = 1;
                // Schedule continuation...
                return;
            case 1:
                x = 42;        // Resumed here after delay
                builder.SetResult(x * 2);
                return;
        }
    }
}
```

Understanding this explains: why `async void` is dangerous (no task to await exceptions on), why `ConfigureAwait(false)` helps, and why `ValueTask` is faster for synchronous paths.

---

### 🧠 The Big Picture — C# in the Modern Ecosystem

```
C# Evolution Timeline:
  C# 1.0 (2002): Classes, interfaces, delegates, events
  C# 2.0 (2005): Generics, iterators (yield), anonymous methods
  C# 3.0 (2007): LINQ, lambda, extension methods, anonymous types
  C# 4.0 (2010): dynamic, named/optional args, covariance
  C# 5.0 (2012): async/await — GAME CHANGER
  C# 6.0 (2015): String interpolation, null-conditional, expression bodies
  C# 7.x (2017): Tuples, pattern matching, ref returns, local functions
  C# 8.0 (2019): Nullable refs, async streams, switch expressions, ranges
  C# 9.0 (2020): Records, init-only, top-level programs, pattern matching++
  C# 10 (2021): Global usings, file-scoped namespaces, record structs
  C# 11 (2022): Raw strings, generic math, required members, list patterns
  C# 12 (2023): Primary constructors, collection expressions, inline arrays
  C# 13 (2024): params IEnumerable, field keyword, allows ref struct

C#'s unique position:
  → Best-in-class async/await (the original inspiration for Python/JS/Rust)
  → Fastest-evolving major language (major version every year)
  → Full spectrum: embedded IoT → cloud functions → AAA games
  → Blazor: C# IN THE BROWSER — no JavaScript needed
  → Unity: C# IS game development for indie and AAA studios

The .NET ecosystem in 2025:
  ASP.NET Core → Fastest web framework in TechEmpower benchmarks
  MAUI          → Cross-platform mobile/desktop (iOS, Android, Windows, Mac)
  Blazor        → WebAssembly + Server components
  ML.NET        → Production ML models in C#
  Orleans       → Virtual actors / distributed systems (used by Xbox Live)
  gRPC          → Protocol buffers + HTTP/2 services
  SignalR       → Real-time WebSocket connections
  Dapr          → Distributed application runtime for microservices
```

---

## 📌 13. Summary (Quick Revision & Cheat Sheet)

---

### Core Concepts (1-line each)

| Concept                 | What It Means                                                              |
|-------------------------|----------------------------------------------------------------------------|
| Value types             | Stored on stack, copied on assignment — `int`, `struct`, `enum`, `record struct` |
| Reference types         | Stored on heap, reference copied — `class`, `interface`, `record class`, arrays |
| `IDisposable`/`using`  | Resource management — `Dispose()` called automatically at scope exit       |
| `async`/`await`         | Non-blocking async via compiler-generated state machines                   |
| LINQ deferred execution | Queries execute at iteration time — `.ToList()` materializes them          |
| `IQueryable<T>`         | Query translated to data source (SQL) — keep as `IQueryable` as long as possible |
| `Span<T>`               | Stack-only view into memory — zero allocation slicing and parsing          |
| Records                 | Immutable data carriers with value equality, `ToString`, `with` expressions |
| Pattern matching        | Rich conditional logic on types, properties, values — eliminates null checks |
| Nullable reference types| Compiler enforces null safety — `string?` can be null, `string` cannot    |

---

### The 10 Things to Remember

1. ✅ **Never block on async** — `.Result` and `.Wait()` cause deadlocks in ASP.NET/UI
2. ✅ **Use `using` for IDisposable** — always, even if you think you don't need it
3. ✅ **`ToList()` materializes LINQ** — be aware of deferred execution timing
4. ✅ **Use `StringBuilder` for string building in loops** — not `+` or `+=`
5. ✅ **`string?` vs `string`** — enable Nullable in your `.csproj`, fix all the warnings
6. ✅ **Prefer records for immutable data** — free equality, `ToString`, `with`
7. ✅ **`ConfigureAwait(false)` in library code** — prevents deadlocks for callers
8. ✅ **`IQueryable` stays queryable** — call `.ToList()` only at the top level
9. ✅ **Use `CancellationToken` everywhere** — every async method should accept one
10. ✅ **`HttpClient` is a singleton** — use `IHttpClientFactory`, never `new HttpClient()` per request

---

### Quick Reference Cheat Sheet

```csharp
// ── PROJECT & TOOLING ──────────────────────────────────────────────────────
dotnet new console -n App    // New console app
dotnet run                   // Build + run
dotnet test                  // Run tests
dotnet add package X         // Add NuGet package
dotnet publish -c Release    // Publish

// ── NULL HANDLING ──────────────────────────────────────────────────────────
x ?? "default"               // Use "default" if x is null
x ??= "default"              // Assign "default" only if null
x?.Property                  // Access safely — null if x is null
x?.Method()?.Value           // Chain safely
x!.Property                  // Assert not null (null-forgiving)
x is not null                // Null check
x is null                    // Null check

// ── PATTERN MATCHING ───────────────────────────────────────────────────────
obj is string s              // Type pattern with binding
obj is int n and > 0         // Logical pattern
obj is { Name: "Aryan" }     // Property pattern
obj is [1, ..]               // List pattern (C# 11)
x switch { > 0 => "pos", < 0 => "neg", _ => "zero" }  // Switch expression

// ── COLLECTIONS ────────────────────────────────────────────────────────────
var list = new List<T>();
var dict = new Dictionary<K, V>();
var set  = new HashSet<T>();
var arr  = new T[] { };
var arr2 = new T[10];
[1, 2, 3]                    // Collection expression (C# 12)
dict.GetValueOrDefault(key, defaultValue)  // Safe dictionary get

// ── LINQ ESSENTIALS ────────────────────────────────────────────────────────
.Where(x => condition)       // Filter
.Select(x => transform)      // Project
.OrderBy(x => key)           // Sort ascending
.OrderByDescending(x => key) // Sort descending
.GroupBy(x => key)           // Group
.First() / .FirstOrDefault() // First element (or null/default)
.Single() / .SingleOrDefault()// Exactly one
.Any(x => condition)         // Any matching?
.All(x => condition)         // All matching?
.Count() / .Sum() / .Average()// Aggregates
.Distinct() / .DistinctBy()  // Unique
.Take(n) / .Skip(n)          // Paging
.ToList() / .ToArray()       // Materialize!
.ToDictionary(k => k.Key)    // To dict
.Join(other, k1, k2, result) // Inner join

// ── ASYNC ──────────────────────────────────────────────────────────────────
async Task<T> MethodAsync(CancellationToken ct = default)
await Task.WhenAll(t1, t2, t3)     // Parallel, wait for all
await Task.WhenAny(t1, t2, t3)     // First to complete
await Task.Delay(ms, ct)           // Non-blocking sleep
ct.ThrowIfCancellationRequested()  // Manual cancellation check
using var cts = new CancellationTokenSource();
cts.CancelAfter(TimeSpan.FromSeconds(5));

// ── EXCEPTIONS ─────────────────────────────────────────────────────────────
throw new ArgumentNullException(nameof(param));
throw new ArgumentOutOfRangeException(nameof(param), $"Must be > 0, was {param}");
ArgumentNullException.ThrowIfNull(param);         // C# 10+
ArgumentOutOfRangeException.ThrowIfNegative(n);  // C# 8+
try { } catch (SpecificException e) when (e.Code == 404) { } // Filter clause!
finally { }                                       // Always runs

// ── RECORDS & STRUCTS ──────────────────────────────────────────────────────
record Person(string Name, int Age);              // Immutable positional record
var p2 = p with { Age = 18 };                    // Non-destructive mutation
var (name, age) = p;                              // Deconstruct
readonly struct Point(int X, int Y);              // Immutable value type

// ── USEFUL .NET TYPES ──────────────────────────────────────────────────────
DateTime.UtcNow                // Always UTC!
DateTimeOffset.UtcNow          // With timezone offset
TimeSpan.FromSeconds(30)
Guid.NewGuid()
Environment.GetEnvironmentVariable("KEY")
Path.Combine("folder", "file.txt")
File.ReadAllTextAsync("file.txt")
JsonSerializer.Serialize(obj)
JsonSerializer.Deserialize<T>(json)
Regex.IsMatch(input, @"pattern")  // One-off check
var r = new Regex(@"pattern");    // Reuse compiled regex!
Random.Shared.Next(1, 100)        // Thread-safe random (C# 6)
```

---

### What's Next?

After mastering C#, explore these natural paths:

- 📘 **ASP.NET Core + EF Core** — Full-stack web development with the fastest .NET web framework
- 📘 **Unity Game Development** — Apply C# mastery to build 2D/3D games
- 📘 **Blazor** — Write full-stack web apps with C# instead of JavaScript
- 📘 **Azure + .NET** — Cloud-native development with Azure Functions, Service Bus, CosmosDB
- 📘 **F#** — Functional-first language on .NET — shares all C# libraries
- 📘 **SignalR / Orleans** — Real-time and distributed actor-model applications

---

> 💬 *"C# is the language that proves you can have both power and elegance. It's what Java would have been if it had been designed a decade later by someone with better taste."*

> 💬 *"The best way to predict the future is to write it in C# and ship it on NuGet."*

> 💬 *"A language that doesn't affect the way you think about programming is not worth knowing. C# has made me think differently about types, async, and what elegance in code can look like."*

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: C# — Complete Language Mastery | Version: 1.0*
*Sections: 13 | Level: Beginner → 0.01% Elite*
