# 🎯 Kotlin — The Ultimate Master Guide
### From Zero to 0.01% Expert — Every Concept, Coroutine Secret, DSL Trick & Hidden Power

> 📘 **The most complete Kotlin guide ever written — beginner to elite.**
>
> 🎯 *Who is this for?* Anyone who wants to go from writing Kotlin to **mastering** it — the language that makes JVM and Android development joyful.
> ⏱️ *Time to complete:* Self-paced — days to months
> 🛠️ *What you'll gain:* Every syntax rule, coroutine pattern, type system secret, DSL technique, and 0.01% hidden trick that separates an elite Kotlin developer from the rest.

---

## Table of Contents

1. [🧠 What is Kotlin?](#1-what-is-kotlin-super-simple)
2. [🌍 Why Kotlin Exists & Dominates](#2-why-kotlin-exists--dominates)
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

## 🧠 1. What is Kotlin? (Super Simple)

### The 12-Year-Old Explanation

Imagine you've been using a really old car — reliable, but uncomfortable, with manual windows and no GPS. Now imagine someone built a brand-new car that can run on the same roads as the old one, fits in the same garage, uses the same fuel — but has automatic everything, a built-in navigation system, and is much safer to drive. **That's Kotlin to Java.**

Kotlin was created by **JetBrains** (the company that makes IntelliJ IDEA, the most popular Java IDE) and officially released in 2016. It runs on the **Java Virtual Machine (JVM)** — meaning Kotlin code can call Java code and vice versa, perfectly and seamlessly. Every Java library ever written works in Kotlin. But Kotlin itself is much nicer to write.

In 2017, Google announced Kotlin as the **preferred language for Android development** — and in 2019, made it the **first-class language** for Android. Today, over 95% of professional Android apps use Kotlin. It's also used for server-side development (backend APIs with Ktor, Spring Boot), data science, and even compiles to JavaScript and native code.

### Real-Life Analogy

💡 **Think of it like this:**
Java is a massive, formal office building — extremely professional, incredibly capable, but you need a security badge, elevator access, three forms of ID, and written permission to open a window. **Kotlin is the same building after a renovation** — same structure, same foundation, every room still works — but now the doors open automatically, the lighting adjusts for you, and you can get anything done in half the time with a tenth of the paperwork.

### One-Line Definition

> **Kotlin** is a modern, statically typed, multiplatform programming language created by JetBrains that runs on the JVM (and compiles to JavaScript and native code), offering null safety, coroutines, expressive syntax, and full Java interoperability while eliminating most of Java's verbosity and pitfalls.

---

## 🌍 2. Why Kotlin Exists & Dominates

### The Problem It Solved

JetBrains used Java extensively for their IDE tools and experienced its frustrations daily: verbose boilerplate, `NullPointerException` crashes (the "billion dollar mistake"), no modern functional programming features, and slow iteration speed. They tried Scala but found it too complex and slow to compile. So they built their own language — one that would compile as fast as Java, be fully interoperable with it, but actually be pleasant to write.

The result fixed Java's biggest pain points in one shot: **null safety built into the type system** (no more NPEs), **concise syntax** (data classes replace 50 lines of Java boilerplate), **coroutines** (async programming without callback hell), and **extension functions** (add methods to any class without inheritance).

### Where Kotlin Dominates in 2025

| Domain                        | How Kotlin Is Used                                                       |
|-------------------------------|--------------------------------------------------------------------------|
| Android Development           | The primary language — 95%+ of new Android code is Kotlin               |
| Server-Side (Ktor)            | JetBrains' async web framework — Kotlin-native backend                  |
| Spring Boot                   | Spring fully supports Kotlin — many Spring teams prefer it over Java     |
| Kotlin Multiplatform (KMP)    | Share business logic between Android, iOS, Web, Desktop — single codebase|
| Compose Multiplatform         | Declarative UI for Android, Desktop, iOS, Web — all in Kotlin           |
| Data Science / ML             | Kotlin for Data Science initiative — Jupyter support, Kandy plotting    |
| Build Systems                 | Gradle Kotlin DSL — build scripts in Kotlin instead of Groovy           |
| CLI Tools                     | Kotlin/Native — compile to native binary, no JVM needed                  |
| Desktop Applications          | Compose Desktop — native desktop apps with Kotlin                       |
| Backend at Scale              | Netflix, Atlassian, Uber, Pinterest — all use Kotlin on the server      |

### Why YOU Should Learn It Deeply

1. **Android is Kotlin** — if you want Android development, Kotlin is non-negotiable.
2. **Kotlin Multiplatform is the future** — write once, deploy to every platform.
3. **Coroutines changed async programming** — understanding Kotlin coroutines makes you a better async programmer in any language.
4. **Null safety eliminates an entire class of bugs** — you'll never think about null the same way again.
5. **JVM ecosystem access** — every Java library (Spring, Hibernate, Kafka, Elasticsearch) works in Kotlin.

---

## 🧱 3. Core Fundamentals (Beginner Level)

> 🎯 *Goal: Build an unshakeable foundation. Every concept here is critical.*

---

### Concept 1: Setup, Hello World & Kotlin Basics

```kotlin
// ── SETUP ─────────────────────────────────────────────────────────────────
// Install Kotlin: https://kotlinlang.org/docs/getting-started.html
// Option 1: IntelliJ IDEA (recommended — best Kotlin support)
// Option 2: Android Studio (for Android development)
// Option 3: VS Code + Kotlin extension
// Option 4: Command line: brew install kotlin (macOS)

// ── RUNNING KOTLIN ────────────────────────────────────────────────────────
// kotlinc Main.kt -include-runtime -d main.jar  (compile to JAR)
// java -jar main.jar                             (run JAR)
// kotlin Main.kt                                 (interpret directly)
// kotlinc -script script.kts                    (run .kts script)

// ── YOUR FIRST KOTLIN PROGRAM ─────────────────────────────────────────────
// main.kt — top-level function, no class needed!
fun main() {
    println("Hello, World!")                    // print with newline
    print("No newline")                         // print without newline
    println("Pi = ${Math.PI:.4f}")             // String template

    // Variables:
    val name = "Aryan"     // val = immutable (like Java final) — PREFER THIS
    var age = 17           // var = mutable
    age = 18               // OK — var can be reassigned
    // name = "Other"      // ❌ COMPILE ERROR — val cannot be reassigned

    // Type inference — Kotlin infers types:
    val integer = 42              // Int
    val long    = 42L             // Long (L suffix)
    val float   = 3.14f           // Float (f suffix)
    val double  = 3.14            // Double (default for decimals)
    val char    = 'K'             // Char
    val boolean = true            // Boolean
    val string  = "Kotlin"        // String

    // Explicit type annotation:
    val x: Int = 42
    val y: Double = 3.14
    val z: String = "Hello"

    // String templates — much better than Java concatenation:
    println("$name is $age years old")          // Simple variable
    println("${name.uppercase()} is ${age * 2}") // Expression in braces
    println("Escaped: \$name")                   // Escaped dollar sign
    println("Newline:\nTab:\t")

    // Multi-line strings (raw strings):
    val multiLine = """
        Hello, $name!
        This is a raw string.
        No escape sequences needed: \n \t
    """.trimIndent()  // trimIndent removes common leading whitespace
    println(multiLine)

    // Kotlin compiles to JVM bytecode — same performance as Java!
}

// ── GRADLE BUILD SCRIPT (build.gradle.kts) ───────────────────────────────
/*
plugins {
    kotlin("jvm") version "1.9.22"
    application
}

repositories {
    mavenCentral()
}

dependencies {
    implementation("org.jetbrains.kotlinx:kotlinx-coroutines-core:1.7.3")
    testImplementation(kotlin("test"))
}

application {
    mainClass.set("MainKt")
}

tasks.test {
    useJUnitPlatform()
}
*/
```

---

### Concept 2: Variables, Types & Null Safety — Kotlin's Killer Feature

```kotlin
// ── NULL SAFETY — the most important Kotlin concept ───────────────────────
// In Java: every reference can be null → NullPointerException anywhere
// In Kotlin: types explicitly declare whether they can be null

// Non-nullable type — CANNOT be null:
var name: String = "Aryan"
// name = null  // ❌ COMPILE ERROR: Null can not be a value of a non-null type String

// Nullable type (add ? to the type):
var nullableName: String? = "Aryan"
nullableName = null  // ✅ OK — nullable type can hold null

// ── SAFE OPERATIONS ON NULLABLE TYPES ────────────────────────────────────
val maybeNull: String? = getNameFromNetwork()

// Safe call operator ?. — returns null instead of throwing NPE:
val length: Int? = maybeNull?.length    // null if maybeNull is null
val upper: String? = maybeNull?.uppercase()?.trim()  // Chains!

// Elvis operator ?: — provide default if null:
val len: Int = maybeNull?.length ?: 0   // 0 if null
val display = maybeNull ?: "Unknown"    // "Unknown" if null

// Not-null assertion !! — throw KotlinNullPointerException if null:
val definitelyNotNull: String = maybeNull!!  // DANGEROUS — use rarely!
// Only use !! when you're 100% certain the value is not null

// Smart cast — Kotlin infers non-null after null check:
if (maybeNull != null) {
    // Inside this block, maybeNull is automatically String (non-nullable)!
    println(maybeNull.length)  // No ?. needed — smart cast!
    println(maybeNull.uppercase())  // Smart cast applies to all String methods
}

// let — execute block only if not null:
maybeNull?.let { nonNullValue ->
    println("Value is: $nonNullValue")  // nonNullValue is String (non-null)
    nonNullValue.length  // Returned from let block
}

// also — like let but returns the original value:
val result = maybeNull?.also { println("Processing: $it") } ?: "default"

// ── TYPE SYSTEM ────────────────────────────────────────────────────────────
// Number types (no implicit conversion!):
val intVal: Int = 42          // 32-bit signed
val longVal: Long = 42L       // 64-bit signed
val shortVal: Short = 42      // 16-bit signed
val byteVal: Byte = 42        // 8-bit signed
val floatVal: Float = 3.14f   // 32-bit IEEE 754
val doubleVal: Double = 3.14  // 64-bit IEEE 754 (DEFAULT)

// Explicit conversion (no implicit!):
val i = 42
val l: Long = i.toLong()      // Must be explicit
val f: Float = i.toFloat()
val d: Double = i.toDouble()
val s: String = i.toString()
val fromString: Int = "42".toInt()
val safe: Int? = "abc".toIntOrNull()  // null instead of exception

// Number literals:
val million = 1_000_000        // Underscores for readability
val hex     = 0xFF             // Hexadecimal
val binary  = 0b11001011       // Binary
val longHex = 0xFFFFFFFFL      // Long hex

// Unsigned types (Kotlin 1.5+):
val uInt:  UInt  = 42u
val uLong: ULong = 42uL
val uByte: UByte = 42u

// Any, Nothing, Unit:
val anything: Any = 42         // Supertype of all non-null types
val nothing: Nothing? = null   // Subtype of all types (function that never returns)
fun alwaysThrows(): Nothing = throw RuntimeException("Always!")

// Unit — like void but it's a real type:
fun printSomething(): Unit { println("Hello") }  // Unit is optional to write
fun printSomething2() { println("Hello") }        // Same thing

// ── TYPE CHECKS AND CASTS ──────────────────────────────────────────────────
val obj: Any = "Hello, Kotlin!"

// is — type check:
if (obj is String) {
    println(obj.length)  // Smart cast — obj is String here!
}

// !is — not type check:
if (obj !is Int) {
    println("Not an integer")
}

// as — unsafe cast (throws ClassCastException if wrong type):
val str: String = obj as String

// as? — safe cast (returns null if wrong type):
val maybeStr: String? = obj as? String  // null if obj is not String
val maybeInt: Int?    = obj as? Int     // null — obj is String not Int

// when with type check:
fun describe(obj: Any): String = when (obj) {
    is Int    -> "Integer: $obj"
    is String -> "String of length ${obj.length}"
    is Double -> "Double: $obj"
    is List<*>-> "List of ${obj.size} items"
    is Array<*>->  "Array of ${obj.size} items"
    null      -> "null"
    else      -> "Unknown: ${obj::class.simpleName}"
}

fun getNameFromNetwork(): String? = null
```

---

### Concept 3: Control Flow — Expressions, Not Statements

```kotlin
// ── KEY INSIGHT: In Kotlin, control structures are EXPRESSIONS ────────────
// They return values! No need for ternary operator.

// if as expression:
val max = if (a > b) a else b   // Returns a value!
val grade = if (score >= 90) "A"
            else if (score >= 80) "B"
            else if (score >= 70) "C"
            else "F"

// ── WHEN — Kotlin's powerful switch ───────────────────────────────────────
val day = 3
val dayName = when (day) {
    1    -> "Monday"
    2    -> "Tuesday"
    3    -> "Wednesday"
    4, 5 -> "Thu/Fri"          // Multiple values
    in 6..7 -> "Weekend"       // Range check
    else -> "Unknown"
}

// when without argument — acts like if/else:
val score = 87
val letter = when {
    score >= 90 -> "A"
    score >= 80 -> "B"
    score >= 70 -> "C"
    else -> "F"
}

// when with complex types:
fun processInput(input: Any) = when (input) {
    is String  -> "String: ${input.uppercase()}"
    is Int     -> "Integer × 2 = ${input * 2}"
    in 1..10   -> "Small number: $input"
    is List<*> -> "List with ${input.size} items"
    null       -> "Got null!"
    else       -> "Unknown: $input"
}

// ── LOOPS ─────────────────────────────────────────────────────────────────
// for loop with ranges:
for (i in 1..10) print("$i ")     // 1 2 3 4 5 6 7 8 9 10
for (i in 1 until 10) print("$i ") // 1 2 3 4 5 6 7 8 9 (exclusive)
for (i in 10 downTo 1) print("$i ") // 10 9 8 7 6 5 4 3 2 1
for (i in 1..10 step 2) print("$i ") // 1 3 5 7 9

// for loop over collections:
val fruits = listOf("apple", "banana", "cherry")
for (fruit in fruits) println(fruit)
for ((index, fruit) in fruits.withIndex()) println("$index: $fruit")

// while and do-while:
var count = 0
while (count < 10) { count++ }
do { count++ } while (count < 20)

// break and continue with labels:
outer@ for (i in 1..5) {
    for (j in 1..5) {
        if (j == 3) continue@outer  // Continue outer loop
        if (i == 4) break@outer     // Break outer loop
        print("($i,$j) ")
    }
}

// repeat:
repeat(5) { index -> println("Iteration $index") }
repeat(3) { println("Hello!") }  // index optional

// ── FUNCTIONS AS EXPRESSIONS ───────────────────────────────────────────────
// Single-expression functions (= instead of {}):
fun double(x: Int) = x * 2
fun max(a: Int, b: Int) = if (a > b) a else b
fun describe(n: Int) = when {
    n > 0  -> "positive"
    n < 0  -> "negative"
    else   -> "zero"
}
```

---

### Concept 4: Functions — Every Feature

```kotlin
// ── FUNCTION DECLARATIONS ─────────────────────────────────────────────────
fun add(a: Int, b: Int): Int {
    return a + b
}

// Single expression (inferred return type):
fun add2(a: Int, b: Int) = a + b

// Default parameters (no overloading needed!):
fun greet(name: String, greeting: String = "Hello", punctuation: String = "!") =
    "$greeting, $name$punctuation"

greet("Aryan")                          // "Hello, Aryan!"
greet("Aryan", "Hi")                    // "Hi, Aryan!"
greet("Aryan", punctuation = ".")       // Named args can skip middle!

// Named arguments — call in any order:
greet(greeting = "Hey", name = "Aryan", punctuation = "?")

// ── VARARGS ───────────────────────────────────────────────────────────────
fun sum(vararg numbers: Int): Int = numbers.sum()
sum(1, 2, 3, 4, 5)       // 15
val nums = intArrayOf(1, 2, 3)
sum(*nums)                // Spread operator — unpack array into varargs

// ── HIGHER-ORDER FUNCTIONS ────────────────────────────────────────────────
// Functions that take or return functions:
fun operate(x: Int, y: Int, operation: (Int, Int) -> Int): Int {
    return operation(x, y)
}
operate(10, 5, ::add)               // Pass function reference
operate(10, 5) { a, b -> a * b }   // Pass lambda
operate(10, 5, { a, b -> a + b })  // Same (lambda in parens — less common)

// When lambda is last argument — trailing lambda syntax:
operate(10, 5) { a, b -> a - b }   // Lambda outside parentheses!

// ── LAMBDAS ───────────────────────────────────────────────────────────────
val double = { x: Int -> x * 2 }                     // Lambda with type
val add3: (Int, Int) -> Int = { a, b -> a + b }      // Explicit function type
val square: (Int) -> Int = { it * it }               // 'it' for single param

// Multi-line lambda:
val process: (String) -> String = {
    val trimmed = it.trim()
    val words = trimmed.split(" ")
    words.joinToString(", ") { word -> word.uppercase() }
}

// ── EXTENSION FUNCTIONS — add methods to existing types! ──────────────────
fun String.isPalindrome(): Boolean {
    val cleaned = lowercase().filter { it.isLetterOrDigit() }
    return cleaned == cleaned.reversed()
}

fun Int.factorial(): Long {
    if (this < 0) throw IllegalArgumentException("Negative factorial")
    return if (this == 0) 1L else this * (this - 1).factorial()
}

fun <T> List<T>.secondOrNull(): T? = if (size >= 2) this[1] else null

// Extension properties:
val String.wordCount: Int get() = split("\\s+".toRegex()).count { it.isNotEmpty() }
val Int.isEven: Boolean get() = this % 2 == 0

// Usage — looks like built-in methods!
"racecar".isPalindrome()    // true
5.factorial()               // 120L
listOf(1, 2, 3).secondOrNull() // 2
"Hello World".wordCount     // 2
42.isEven                   // true

// ── INLINE FUNCTIONS ──────────────────────────────────────────────────────
// inline eliminates lambda call overhead at the call site:
inline fun <T> measureTime(block: () -> T): Pair<T, Long> {
    val start = System.currentTimeMillis()
    val result = block()
    val end = System.currentTimeMillis()
    return result to (end - start)
}

val (result, time) = measureTime { complexComputation() }
println("Result: $result, Time: ${time}ms")

// noinline — opt specific parameters out of inlining:
inline fun example(inlined: () -> Unit, noinline notInlined: () -> Unit) {
    inlined()
    val stored = notInlined  // Can store because not inlined
    stored()
}

// crossinline — prevent non-local returns from inlined lambdas:
inline fun forEach(list: List<Int>, crossinline action: (Int) -> Unit) {
    list.forEach { action(it) }  // action can't use return to exit forEach's caller
}

fun complexComputation() = (1..1_000_000).sum()
```

---

### Concept 5: Collections — Immutable by Default

```kotlin
// ── KOTLIN'S TWO-TIER COLLECTION SYSTEM ───────────────────────────────────
// Read-only: List, Set, Map (cannot add/remove — but underlying data may be mutable)
// Mutable:   MutableList, MutableSet, MutableMap

// ── CREATING COLLECTIONS ──────────────────────────────────────────────────
// Read-only:
val list   = listOf(1, 2, 3, 4, 5)         // List<Int>
val set    = setOf("a", "b", "c")           // Set<String>
val map    = mapOf("key" to "value", "k2" to "v2") // Map<String, String>

// Mutable:
val mList  = mutableListOf(1, 2, 3)        // MutableList<Int>
val mSet   = mutableSetOf("a", "b")         // MutableSet<String>
val mMap   = mutableMapOf("key" to "value") // MutableMap<String, String>

// Specific types:
val arrayList = ArrayList<Int>()
val linkedList = ArrayDeque<String>()       // Kotlin's ArrayDeque (not Java's)
val hashMap = HashMap<String, Int>()
val treeMap = sortedMapOf("b" to 2, "a" to 1) // TreeMap — sorted

// Empty collections with type:
val empty: List<String> = emptyList()
val emptyMutable: MutableList<String> = mutableListOf()

// Build with buildList (scope function for construction):
val builtList = buildList {
    add(1)
    add(2)
    addAll(listOf(3, 4, 5))
    removeAt(0)
}  // [2, 3, 4, 5]

// ── LIST OPERATIONS ───────────────────────────────────────────────────────
val nums = listOf(3, 1, 4, 1, 5, 9, 2, 6, 5, 3)

// Access:
nums[0]                   // 3 — by index
nums.first()              // 3 — first element
nums.last()               // 3 — last element
nums.first { it > 5 }    // 9 — first matching predicate
nums.getOrNull(100)       // null — safe access
nums.getOrElse(100) { -1 } // -1 — with default

// Transformations:
nums.map { it * 2 }                  // [6,2,8,2,10,18,4,12,10,6]
nums.filter { it % 2 == 0 }         // [4,2,6]
nums.filterNot { it % 2 == 0 }      // [3,1,1,5,9,5,3]
nums.flatMap { listOf(it, it * 10) } // [3,30,1,10,4,40,...]
nums.mapNotNull { if (it > 5) it else null } // [9,6] — filter + map
nums.distinct()                      // [3,1,4,5,9,2,6]
nums.sortedDescending()             // [9,6,5,5,4,3,3,2,1,1]
nums.sortedBy { it.toString() }     // Sort by custom key
nums.reversed()                     // [3,5,6,2,9,5,1,4,1,3]
nums.shuffled()                     // Random order

// Aggregation:
nums.sum()                          // 39
nums.average()                      // 3.9
nums.min()                          // 1
nums.max()                          // 9
nums.count { it > 5 }              // 2
nums.sumOf { it.toLong() }         // 39L
nums.reduce { acc, n -> acc + n }  // 39
nums.fold(0) { acc, n -> acc + n } // 39 (with initial value)
nums.fold(1) { acc, n -> acc * n } // Product

// Grouping and partitioning:
nums.groupBy { it % 2 == 0 }       // {false=[3,1,1,5,9,5,3], true=[4,2,6]}
nums.groupingBy { it }.eachCount() // {3=2,1=2,4=1,5=2,9=1,2=1,6=1}
nums.partition { it > 5 }          // Pair([9,6],[3,1,4,1,5,2,5,3])
nums.chunked(3)                    // [[3,1,4],[1,5,9],[2,6,5],[3]]
nums.windowed(3)                   // Sliding windows of size 3
nums.zipWithNext()                 // [(3,1),(1,4),(4,1),...]

// Searching:
nums.any { it > 10 }              // false
nums.all { it > 0 }               // true
nums.none { it < 0 }              // true
nums.find { it > 5 }             // 9 — first match
nums.findLast { it > 5 }        // 6 — last match
nums.indexOf(5)                   // 4 — first index
nums.lastIndexOf(5)              // 8 — last index
nums.contains(7)                  // false
7 in nums                         // false (same as contains)
nums.binarySearch(5)             // index (list must be sorted!)

// Slicing:
nums.take(3)                     // [3,1,4]
nums.drop(3)                     // [1,5,9,2,6,5,3]
nums.takeLast(3)                 // [6,5,3]
nums.dropLast(3)                 // [3,1,4,1,5,9,2]
nums.takeWhile { it < 5 }       // [3,1,4,1]
nums.dropWhile { it < 5 }       // [5,9,2,6,5,3]
nums.slice(2..5)                 // [4,1,5,9]
nums.subList(2, 5)              // [4,1,5] (from index 2 to 5 exclusive)

// ── MAP OPERATIONS ────────────────────────────────────────────────────────
val scores = mapOf("Alice" to 95, "Bob" to 87, "Carol" to 92)

scores["Alice"]                  // 95
scores.getValue("Alice")         // 95 (throws if missing)
scores.getOrDefault("Dave", 0)  // 0
scores.getOrElse("Dave") { 0 }  // 0 from lambda

scores.keys                      // [Alice, Bob, Carol]
scores.values                    // [95, 87, 92]
scores.entries                   // [Alice=95, Bob=87, Carol=92]

scores.filter { (name, score) -> score > 90 }  // {Alice=95, Carol=92}
scores.mapValues { (_, score) -> score + 10 }  // Increase all scores
scores.mapKeys { (name, _) -> name.uppercase() }
scores.toSortedMap()            // Sorted by key
scores.toList()                 // List of pairs

// Mutable map operations:
val mScores = scores.toMutableMap()
mScores["Dave"] = 78
mScores.put("Eve", 88)
mScores.putIfAbsent("Alice", 0)   // Doesn't overwrite existing
mScores.remove("Bob")
mScores.getOrPut("Frank") { 75 }  // Get or add with default
```

---

🧪 **Mini Task 1:**
> Write an extension function `List<Int>.statistics()` that returns a data class `Statistics(min: Int, max: Int, average: Double, median: Double)`. Test with `listOf(3, 1, 4, 1, 5, 9, 2, 6)`.
> ✅ *Expected: `Statistics(min=1, max=9, average=3.875, median=3.5)`*

🧪 **Mini Task 2:**
> Write a function `wordFrequency(text: String): Map<String, Int>` that counts word occurrences case-insensitively, sorted by frequency descending. Use `groupingBy`, `eachCount`, and `toSortedMap`.

---

## ⚙️ 4. Complete Language System Breakdown

> 🎯 *Goal: Understand ALL of Kotlin's machinery — nothing hidden.*

---

### Part 1: OOP — Classes, Interfaces & Data Classes

```kotlin
// ── CLASSES ────────────────────────────────────────────────────────────────
// Primary constructor in the class header:
class Person(
    val name: String,         // val = read-only property
    var age: Int,             // var = read-write property
    private val email: String // private — not accessible outside class
) {
    // Secondary constructor must delegate to primary:
    constructor(name: String, age: Int) : this(name, age, "")

    // Init block — runs during construction:
    init {
        require(name.isNotBlank()) { "Name cannot be blank" }
        require(age >= 0) { "Age cannot be negative" }
        println("Created Person: $name")
    }

    // Computed property:
    val isAdult: Boolean get() = age >= 18

    // Backing field for custom getter/setter:
    var fullName: String = name
        get() = field.trim()             // field refers to backing field
        set(value) {
            field = value.trim()
            println("Name updated to: $field")
        }

    // Methods:
    fun greet() = "Hello, I'm $name!"
    fun birthday() { age++ }

    // Operator overloading:
    operator fun plus(other: Person) = Person("$name & ${other.name}", maxOf(age, other.age))

    // toString, equals, hashCode:
    override fun toString() = "Person(name=$name, age=$age)"
    override fun equals(other: Any?) = other is Person && name == other.name && age == other.age
    override fun hashCode() = 31 * name.hashCode() + age
}

// ── DATA CLASSES — Kotlin's killer feature vs Java ────────────────────────
// Automatically generates: toString, equals, hashCode, copy, componentN
data class User(
    val id: Int,
    val username: String,
    val email: String,
    val role: Role = Role.USER,  // Default value
    val active: Boolean = true
)

enum class Role { ADMIN, USER, MODERATOR }

// What you get for FREE with data class:
val user1 = User(1, "aryan", "a@b.com")
val user2 = User(1, "aryan", "a@b.com")
println(user1 == user2)        // true — structural equality!
println(user1)                 // User(id=1, username=aryan, email=a@b.com, role=USER, active=true)
println(user1.hashCode() == user2.hashCode()) // true

// copy — non-destructive modification:
val admin = user1.copy(role = Role.ADMIN)     // New object, only role changed
val updated = user1.copy(email = "new@b.com", active = false)

// Destructuring declarations:
val (id, username, email) = user1   // componentN() functions
val (_, name2) = user1              // Skip id with _
for ((userId, userName) in listOf(user1, admin)) {
    println("$userId: $userName")
}

// ── SEALED CLASSES — exhaustive hierarchies ────────────────────────────────
sealed class Result<out T> {
    data class Success<T>(val data: T) : Result<T>()
    data class Error(val message: String, val cause: Throwable? = null) : Result<Nothing>()
    data object Loading : Result<Nothing>()  // Singleton (Kotlin 1.9+)
}

fun handleResult(result: Result<User>) = when (result) {
    is Result.Success  -> println("Got user: ${result.data.username}")
    is Result.Error    -> println("Error: ${result.message}")
    is Result.Loading  -> println("Loading...")
    // No else needed — sealed class is exhaustive!
}

// Pattern matching on sealed classes:
val display = when (val r = fetchUser()) {
    is Result.Success -> r.data.username
    is Result.Error   -> "Error: ${r.message}"
    Result.Loading    -> "Loading..."
}

// ── INTERFACES ────────────────────────────────────────────────────────────
interface Drawable {
    fun draw(): String                  // Abstract method
    fun resize(factor: Double) { }     // Default implementation!
    val name: String                    // Abstract property
    val description: String             // Default property implementation:
        get() = "A drawable: $name"
}

interface Resizable {
    fun resize(factor: Double)
}

// Multiple interface implementation:
class Circle(val radius: Double) : Drawable, Resizable {
    override val name = "Circle"
    override fun draw() = "Drawing circle with radius $radius"
    override fun resize(factor: Double) { /* implementation */ }
}

// ── INHERITANCE ────────────────────────────────────────────────────────────
// Classes are final by default — must be 'open' to extend:
open class Animal(val name: String) {
    open fun sound() = "..."
    open fun describe() = "$name makes ${sound()}"
    fun breathe() = "Inhale... Exhale..."  // Cannot be overridden (not open)
}

class Dog(name: String) : Animal(name) {
    override fun sound() = "Woof"
    final override fun describe() = "Dog $name goes ${sound()}"  // final = no more overrides
}

class Cat(name: String, val indoor: Boolean = true) : Animal(name) {
    override fun sound() = "Meow"
}

// abstract class:
abstract class Shape {
    abstract val area: Double           // Must be implemented
    abstract val perimeter: Double      // Must be implemented
    fun describe() = "Area: $area, Perimeter: $perimeter"
}

// ── OBJECT DECLARATIONS — Singletons ──────────────────────────────────────
object Database {
    private val connections = mutableListOf<String>()
    val connectionCount get() = connections.size

    fun connect(url: String) {
        connections.add(url)
        println("Connected to $url")
    }

    fun disconnect() {
        connections.clear()
        println("All connections closed")
    }
}

Database.connect("postgresql://localhost/mydb")
println(Database.connectionCount)  // 1

// ── COMPANION OBJECTS — static members ────────────────────────────────────
class ApiClient private constructor(val baseUrl: String) {
    companion object {                    // Can have a name: companion object Factory
        const val DEFAULT_TIMEOUT = 30_000  // Compile-time constant

        fun create(baseUrl: String) = ApiClient(baseUrl)
        fun createDefault() = ApiClient("https://api.example.com")

        @JvmStatic  // Makes it callable as static from Java
        fun version() = "1.0.0"
    }

    fun get(path: String) = "$baseUrl/$path"
}

val client = ApiClient.create("https://api.example.com")
val defaultClient = ApiClient.createDefault()
println(ApiClient.DEFAULT_TIMEOUT)  // 30000

// ── VALUE CLASSES (inline classes) — Kotlin 1.5+ ─────────────────────────
@JvmInline
value class UserId(val value: Int)
@JvmInline
value class Email(val value: String) {
    init { require("@" in value) { "Invalid email" } }
}

// These are zero-cost wrappers at runtime!
// Type safety: can't accidentally pass Email where UserId is expected
fun findUser(id: UserId): User? = TODO()
val user = findUser(UserId(42))  // Can't accidentally pass raw Int

fun fetchUser(): Result<User> = Result.Success(User(1, "aryan", "a@b.com"))
```

---

### Part 2: Generics — The Type System Deep Dive

```kotlin
// ── GENERIC CLASSES AND FUNCTIONS ─────────────────────────────────────────
class Box<T>(var value: T) {
    fun get(): T = value
    fun set(newValue: T) { value = newValue }
    override fun toString() = "Box($value)"
}

fun <T> Box<T>.transform(block: (T) -> T): Box<T> {
    return Box(block(value))
}

val intBox = Box(42)
val strBox = Box("Hello")
intBox.transform { it * 2 }    // Box(84)

// Generic functions:
fun <T : Comparable<T>> max(a: T, b: T): T = if (a > b) a else b
fun <T, R> transform(list: List<T>, mapper: (T) -> R): List<R> = list.map(mapper)

// Multiple type bounds:
fun <T> T.toStringIfComparable(): String where T : Comparable<T>, T : Any {
    return this.toString()
}

// ── VARIANCE — in, out, * ──────────────────────────────────────────────────
// Covariance (out) — can be used as a producer of T:
// If Cat is a subtype of Animal, then Producer<Cat> is a subtype of Producer<Animal>
interface Producer<out T> {
    fun produce(): T         // Can only RETURN T (out position)
    // fun consume(t: T) {} // ❌ Would be compile error — T is out-only
}

// Contravariance (in) — can be used as a consumer of T:
// If Cat is subtype of Animal, Consumer<Animal> is subtype of Consumer<Cat>
interface Consumer<in T> {
    fun consume(t: T)        // Can only ACCEPT T (in position)
    // fun produce(): T {}  // ❌ Would be compile error — T is in-only
}

// Invariance (neither in nor out) — default for classes:
class MutableBox<T>(var value: T)  // T is invariant — read and write

// Star projection — when you don't know the type parameter:
fun printList(list: List<*>) {   // List of anything
    for (item in list) println(item)
}

// Use-site variance (type projection):
fun copyFrom(source: Array<out Any>, dest: Array<Any>) {
    // source is covariant here — can only read from it
}

// ── REIFIED TYPE PARAMETERS ────────────────────────────────────────────────
// Normally, type info is erased at runtime (type erasure).
// With reified, inline functions can access the actual type at runtime!

inline fun <reified T> Any.isInstanceOf(): Boolean = this is T
inline fun <reified T> List<*>.filterIsInstance(): List<T> = filterIsInstance<T>()
inline fun <reified T> parseJson(json: String): T = gson.fromJson(json, T::class.java)

// Usage:
val result = "hello".isInstanceOf<String>()  // true — works at runtime!
val strings = listOf(1, "a", 2, "b", 3).filterIsInstance<String>() // ["a","b"]
val user = parseJson<User>(jsonString)  // No Class<T> argument needed!

// Without reified, you'd need to pass Class<T> explicitly:
// fun <T> parseJson(json: String, type: Class<T>): T = gson.fromJson(json, type)
// parseJson(jsonString, User::class.java) — less ergonomic

val gson = com.google.gson.Gson()
```

---

### Part 3: Functional Programming — The Kotlin Standard Library

```kotlin
// ── SCOPE FUNCTIONS — let, run, with, apply, also ─────────────────────────
// These are crucial for Kotlin idioms:
//
// | Function | Object ref | Return value | Is extension? |
// |----------|------------|--------------|---------------|
// | let      | it         | lambda result| Yes           |
// | run      | this       | lambda result| Yes           |
// | with     | this       | lambda result| No (argument) |
// | apply    | this       | object itself| Yes           |
// | also     | it         | object itself| Yes           |

data class Config(var host: String = "", var port: Int = 0, var ssl: Boolean = false)

// apply — configure an object, return the object:
val config = Config().apply {
    host = "localhost"      // this.host inside apply
    port = 8080
    ssl = true
}  // config is the Config object

// also — do something extra, return the object:
val list = mutableListOf(1, 2, 3)
    .also { println("Original: $it") }
    .apply { add(4); add(5) }
    .also { println("Modified: $it") }

// let — transform nullable safely:
val name: String? = getUserName()
val nameLength = name?.let {
    println("Processing: $it")
    it.length
} ?: 0

// run — execute a block, return result:
val result = config.run {
    "Connecting to $host:$port (ssl=$ssl)"
}

// with — operate on object (no extension):
val greeting = with(config) {
    "Host: $host, Port: $port"  // this is config inside with
}

// takeIf / takeUnless — conditional selection:
val validated = name?.takeIf { it.length > 3 }     // null if too short
val notEmpty = name?.takeUnless { it.isEmpty() }    // null if empty

// ── FUNCTIONAL OPERATIONS ON COLLECTIONS ──────────────────────────────────
// All return types, no mutation of original:

data class Student(val name: String, val gpa: Double, val department: String)
val students = listOf(
    Student("Aryan",  9.8, "CS"),
    Student("Priya",  9.2, "Math"),
    Student("Rahul",  8.9, "CS"),
    Student("Kavya",  9.5, "Physics"),
    Student("Dev",    7.5, "CS"),
)

// Complex query — Kotlin's functional style shines here:
val topCsStudents = students
    .filter { it.department == "CS" }
    .sortedByDescending { it.gpa }
    .take(2)
    .map { "${it.name}: ${it.gpa}" }

println(topCsStudents)  // [Aryan: 9.8, Rahul: 8.9]

// groupBy returns Map<K, List<V>>:
val byDept: Map<String, List<Student>> = students.groupBy { it.department }
val deptAverages = byDept.mapValues { (_, students) -> students.map { it.gpa }.average() }

// associate — build a Map from a collection:
val nameToGpa = students.associate { it.name to it.gpa }
val nameToStudent = students.associateBy { it.name }
val nameToGpa2 = students.associateBy({ it.name }, { it.gpa })

// flatMap:
val allCourses = students.flatMap { student ->
    listOf("${student.department}101", "${student.department}201")
}

// zip — combine two lists:
val names = students.map { it.name }
val gpas = students.map { it.gpa }
val pairs = names.zip(gpas)           // List<Pair<String, Double>>
val merged = names.zip(gpas) { name, gpa -> "$name: $gpa" }  // With transform

// scan — running fold:
val runningSum = listOf(1, 2, 3, 4, 5).scan(0) { acc, n -> acc + n }
// [0, 1, 3, 6, 10, 15]

// ── SEQUENCES — lazy evaluation ────────────────────────────────────────────
// Lists evaluate eagerly (create intermediate collections)
// Sequences evaluate lazily (compute only what's needed)

// Without sequences (creates 3 intermediate lists!):
val result1 = (1..1_000_000)
    .map { it * 2 }          // Creates 1M element list
    .filter { it % 3 == 0 }  // Creates ~333K element list
    .take(5)                  // Finally takes 5 — wasted work!

// With sequences (lazy — stops after finding 5 elements):
val result2 = (1..1_000_000).asSequence()
    .map { it * 2 }          // No list created — lazy
    .filter { it % 3 == 0 }  // No list created — lazy
    .take(5)                  // Terminal operation — triggers evaluation
    .toList()                 // [6, 12, 18, 24, 30]

// Infinite sequences:
val fibonacci = generateSequence(Pair(0L, 1L)) { (a, b) -> b to a + b }
    .map { it.first }
val first20Fibs = fibonacci.take(20).toList()

// Custom sequence:
val primes = sequence {
    var candidate = 2
    val found = mutableListOf<Int>()
    while (true) {
        if (found.none { candidate % it == 0 }) {
            found.add(candidate)
            yield(candidate)          // yield — emit a value
        }
        candidate++
    }
}
primes.take(10).toList()  // [2, 3, 5, 7, 11, 13, 17, 19, 23, 29]

// yieldAll — emit multiple values:
val combined = sequence {
    yieldAll(listOf(1, 2, 3))
    yield(4)
    yieldAll(5..10)
}
```

---

### Part 4: Coroutines — Kotlin's Async Superpower

```kotlin
import kotlinx.coroutines.*
import kotlinx.coroutines.flow.*

// ── WHAT ARE COROUTINES? ──────────────────────────────────────────────────
// Coroutines are lightweight threads managed by Kotlin (not the OS)
// You can have millions of coroutines — not millions of threads!
// They're suspended (paused) rather than blocked — efficient!

// ── COROUTINE BUILDERS ────────────────────────────────────────────────────
fun main() = runBlocking {  // Creates event loop and runs coroutine
    // launch — fire and forget (returns Job):
    val job = launch {
        delay(1000L)             // Non-blocking delay (suspend function)
        println("Hello from coroutine!")
    }
    println("Hello from main!")
    job.join()                   // Wait for job to complete

    // async — returns a value (returns Deferred<T>):
    val deferred = async {
        computeAnswer()
    }
    println("Waiting for answer...")
    val answer = deferred.await()   // Suspend until result is ready
    println("Answer: $answer")

    // Parallel execution:
    val start = System.currentTimeMillis()
    val result1 = async { fetchFromDB() }    // Start immediately
    val result2 = async { fetchFromAPI() }   // Start immediately (parallel!)
    val combined = "${result1.await()} + ${result2.await()}"  // Wait for both
    println("Took: ${System.currentTimeMillis() - start}ms")  // ~max(db, api) time

    // coroutineScope — structured concurrency:
    coroutineScope {
        launch { delay(500); println("Child 1") }
        launch { delay(300); println("Child 2") }
    }  // Waits for ALL children before proceeding
    println("All children done")
}

// ── SUSPEND FUNCTIONS ──────────────────────────────────────────────────────
// suspend functions can be called from coroutines only:
suspend fun fetchUser(id: Int): User {
    delay(100)  // Simulates network call
    return User(id, "user$id", "user$id@example.com")
}

suspend fun fetchUsers(ids: List<Int>): List<User> = coroutineScope {
    ids.map { id -> async { fetchUser(id) } }.awaitAll()
}

// ── DISPATCHERS — WHERE does the coroutine run? ────────────────────────────
// Dispatchers.Default   — CPU-intensive work (thread pool = CPU count)
// Dispatchers.IO        — I/O operations (up to 64 threads)
// Dispatchers.Main      — Android UI thread
// Dispatchers.Unconfined— Runs in current thread (not recommended generally)

suspend fun processData() = withContext(Dispatchers.Default) {
    // Heavy computation — runs on Default thread pool
    (1..1_000_000).sum()
}

suspend fun readFile(path: String): String = withContext(Dispatchers.IO) {
    // File I/O — runs on IO thread pool
    java.io.File(path).readText()
}

// ── STRUCTURED CONCURRENCY ─────────────────────────────────────────────────
class UserRepository(private val scope: CoroutineScope) {
    suspend fun getUserWithPosts(userId: Int) = coroutineScope {
        val user  = async { fetchUser(userId) }
        val posts = async { fetchPosts(userId) }
        val comments = async { fetchComments(userId) }
        Triple(user.await(), posts.await(), comments.await())
    }

    fun startBackgroundSync() = scope.launch {
        while (true) {
            syncData()
            delay(60_000)  // Wait 1 minute between syncs
        }
    }
}

// ── CANCELLATION ──────────────────────────────────────────────────────────
val job = CoroutineScope(Dispatchers.Default).launch {
    repeat(1000) { i ->
        if (!isActive) return@launch  // Check cancellation
        println("Working $i...")
        delay(100)
    }
}

delay(500)
job.cancel()  // Cancel the coroutine
job.join()    // Wait for cancellation to complete
println("Cancelled!")

// timeout:
val result = withTimeoutOrNull(5000L) {
    fetchSlowData()  // Will return null if takes > 5 seconds
} ?: "Timeout default"

// ── FLOW — Kotlin's async streams ──────────────────────────────────────────
// Flow = cold asynchronous stream (like Sequence but async)

// Create a flow:
fun numberFlow(): Flow<Int> = flow {
    for (i in 1..10) {
        delay(100)
        emit(i)          // Emit values one at a time
    }
}

// Collect a flow:
runBlocking {
    numberFlow()
        .filter { it % 2 == 0 }
        .map { it * it }
        .collect { value -> println(value) }  // 4, 16, 36, 64, 100
}

// Flow operators:
val flow = flow {
    emit(1); delay(100)
    emit(2); delay(100)
    emit(3)
}

flow
    .map { it * 2 }
    .filter { it > 2 }
    .take(2)
    .onEach { println("Before: $it") }
    .collect { println("Received: $it") }

// StateFlow — observable state (hot flow):
class CounterViewModel : ViewModel() {
    private val _count = MutableStateFlow(0)
    val count: StateFlow<Int> = _count.asStateFlow()

    fun increment() { _count.value++ }
    fun decrement() { _count.update { it - 1 } }
}

// SharedFlow — broadcast to multiple collectors:
val sharedFlow = MutableSharedFlow<String>(replay = 1)
sharedFlow.emit("Hello")
sharedFlow.collect { println(it) }

// conflate — only keep latest value if collector is slow:
flow { while(true) { emit(System.currentTimeMillis()); delay(10) } }
    .conflate()
    .collect { delay(100); println(it) }  // Won't fall behind!

suspend fun computeAnswer() = 42
suspend fun fetchFromDB() = "DB data"
suspend fun fetchFromAPI() = "API data"
suspend fun fetchPosts(userId: Int) = listOf<String>()
suspend fun fetchComments(userId: Int) = listOf<String>()
suspend fun syncData() {}
suspend fun fetchSlowData() = "slow"
```

---

### 📊 Full Kotlin System Overview Table

| Feature              | Kotlin Mechanism                            | Key Insight                                           |
|----------------------|---------------------------------------------|-------------------------------------------------------|
| Null safety          | `T` vs `T?` — compile-time null checking   | Eliminates NPE — entire class of bugs gone            |
| Data classes         | `data class` — auto-generates boilerplate   | `toString`, `equals`, `hashCode`, `copy`, `component` |
| Sealed classes       | Exhaustive `when` — compiler ensures coverage | No missed cases — type-safe state machines          |
| Extension functions  | Add methods to any type — zero overhead     | Reads like built-in; compiles to static utility     |
| Coroutines           | Lightweight async — suspend/resume          | Millions of coroutines vs thousands of threads       |
| Scope functions      | `let`, `run`, `with`, `apply`, `also`       | Idiomatic null handling and object configuration     |
| Smart casts          | Automatic cast after type/null check        | No explicit casting after `is` or null check         |
| Companion objects    | Object inside class — static-like           | Factory methods, constants, `@JvmStatic`             |
| Inline functions     | Eliminates lambda call overhead             | Zero-cost higher-order functions                     |
| Reified generics     | Access type info at runtime in inline fns   | No `Class<T>` passing — `T::class.java` in inline   |

---

## 🔄 5. Real-World Workflow

---

### 🟢 Beginner Workflow: Android ViewModel with Kotlin

```kotlin
// ViewModel.kt — Android MVVM pattern with coroutines
import androidx.lifecycle.ViewModel
import androidx.lifecycle.viewModelScope
import kotlinx.coroutines.flow.*
import kotlinx.coroutines.launch

// Domain model:
data class Article(
    val id: Int,
    val title: String,
    val content: String,
    val author: String,
    val publishedAt: Long,
    val isFavorite: Boolean = false
)

// UI state:
sealed interface ArticleListUiState {
    data object Loading : ArticleListUiState
    data class Success(val articles: List<Article>) : ArticleListUiState
    data class Error(val message: String) : ArticleListUiState
}

// ViewModel:
class ArticleListViewModel(
    private val repository: ArticleRepository
) : ViewModel() {

    private val _uiState = MutableStateFlow<ArticleListUiState>(ArticleListUiState.Loading)
    val uiState: StateFlow<ArticleListUiState> = _uiState.asStateFlow()

    private val _searchQuery = MutableStateFlow("")
    val searchQuery: StateFlow<String> = _searchQuery.asStateFlow()

    // Derived state — combine multiple flows:
    val filteredArticles: StateFlow<List<Article>> = combine(
        repository.getArticles(),
        searchQuery
    ) { articles, query ->
        if (query.isEmpty()) articles
        else articles.filter {
            it.title.contains(query, ignoreCase = true) ||
            it.author.contains(query, ignoreCase = true)
        }
    }.stateIn(viewModelScope, SharingStarted.WhileSubscribed(5000), emptyList())

    init {
        loadArticles()
    }

    fun loadArticles() {
        viewModelScope.launch {
            _uiState.value = ArticleListUiState.Loading
            try {
                repository.refreshArticles()
                _uiState.value = ArticleListUiState.Success(repository.getArticlesOnce())
            } catch (e: Exception) {
                _uiState.value = ArticleListUiState.Error(e.message ?: "Unknown error")
            }
        }
    }

    fun updateSearchQuery(query: String) {
        _searchQuery.value = query
    }

    fun toggleFavorite(articleId: Int) {
        viewModelScope.launch {
            repository.toggleFavorite(articleId)
        }
    }
}

// Repository:
interface ArticleRepository {
    fun getArticles(): Flow<List<Article>>
    suspend fun getArticlesOnce(): List<Article>
    suspend fun refreshArticles()
    suspend fun toggleFavorite(id: Int)
}
```

---

### 🔵 Professional Workflow: Ktor Backend API

```kotlin
// Application.kt — Production Ktor server
import io.ktor.server.application.*
import io.ktor.server.engine.*
import io.ktor.server.netty.*
import io.ktor.server.routing.*
import io.ktor.server.plugins.contentnegotiation.*
import io.ktor.server.plugins.requestvalidation.*
import io.ktor.serialization.kotlinx.json.*
import kotlinx.serialization.Serializable
import kotlinx.serialization.json.Json

// ── DATA TRANSFER OBJECTS ────────────────────────────────────────────────
@Serializable
data class CreateUserRequest(
    val username: String,
    val email: String,
    val password: String
)

@Serializable
data class UserResponse(
    val id: Int,
    val username: String,
    val email: String,
    val createdAt: Long
)

@Serializable
data class ApiError(
    val code: String,
    val message: String
)

// ── ROUTING ──────────────────────────────────────────────────────────────
fun Application.configureRouting(userService: UserService) {
    routing {
        route("/api/v1") {
            usersRoute(userService)
        }
    }
}

fun Route.usersRoute(service: UserService) {
    route("/users") {
        get {
            val page = call.parameters["page"]?.toIntOrNull() ?: 1
            val limit = call.parameters["limit"]?.toIntOrNull()?.coerceIn(1, 100) ?: 20
            val users = service.getUsers(page, limit)
            call.respond(users)
        }

        get("/{id}") {
            val id = call.parameters["id"]?.toIntOrNull()
                ?: return@get call.respond(HttpStatusCode.BadRequest, ApiError("INVALID_ID", "ID must be integer"))
            val user = service.getUserById(id)
                ?: return@get call.respond(HttpStatusCode.NotFound, ApiError("NOT_FOUND", "User $id not found"))
            call.respond(user)
        }

        post {
            val request = call.receive<CreateUserRequest>()
            val user = service.createUser(request)
            call.respond(HttpStatusCode.Created, user)
        }

        delete("/{id}") {
            val id = call.parameters["id"]?.toIntOrNull()
                ?: return@delete call.respond(HttpStatusCode.BadRequest)
            service.deleteUser(id)
            call.respond(HttpStatusCode.NoContent)
        }
    }
}

// ── APPLICATION SETUP ─────────────────────────────────────────────────────
fun main() {
    embeddedServer(Netty, port = 8080) {
        install(ContentNegotiation) {
            json(Json {
                prettyPrint = true
                isLenient = true
                ignoreUnknownKeys = true
            })
        }
        install(RequestValidation) {
            validate<CreateUserRequest> { request ->
                when {
                    request.username.length < 3 -> ValidationResult.Invalid("Username too short")
                    "@" !in request.email -> ValidationResult.Invalid("Invalid email")
                    request.password.length < 8 -> ValidationResult.Invalid("Password too short")
                    else -> ValidationResult.Valid
                }
            }
        }
        val userService = UserService(UserRepository())
        configureRouting(userService)
    }.start(wait = true)
}

interface UserService {
    suspend fun getUsers(page: Int, limit: Int): List<UserResponse>
    suspend fun getUserById(id: Int): UserResponse?
    suspend fun createUser(request: CreateUserRequest): UserResponse
    suspend fun deleteUser(id: Int)
}
class UserRepository
class UserServiceImpl(private val repo: UserRepository) : UserService {
    override suspend fun getUsers(page: Int, limit: Int) = emptyList<UserResponse>()
    override suspend fun getUserById(id: Int): UserResponse? = null
    override suspend fun createUser(request: CreateUserRequest) = UserResponse(1, request.username, request.email, System.currentTimeMillis())
    override suspend fun deleteUser(id: Int) {}
}
fun UserService(repo: UserRepository): UserService = UserServiceImpl(repo)
```

---

## 🧪 6. Hands-on Practice Projects

---

### 🟢 Beginner Project: Type-Safe Builder DSL

```kotlin
// html_builder.kt — Build a simple HTML DSL
class HtmlElement(val tag: String) {
    private val attributes = mutableMapOf<String, String>()
    private val children = mutableListOf<Any>()

    fun attr(name: String, value: String) = apply { attributes[name] = value }
    operator fun String.unaryPlus() { children.add(this) }  // +text
    fun child(element: HtmlElement) { children.add(element) }

    fun build(indent: Int = 0): String {
        val spaces = "  ".repeat(indent)
        val attrStr = if (attributes.isEmpty()) ""
        else attributes.entries.joinToString(" ", prefix = " ") { (k,v) -> """$k="$v"""" }
        val childStr = children.joinToString("\n") { child ->
            when (child) {
                is HtmlElement -> child.build(indent + 1)
                else -> "$spaces  $child"
            }
        }
        return if (childStr.isEmpty()) "$spaces<$tag$attrStr/>"
        else "$spaces<$tag$attrStr>\n$childStr\n$spaces</$tag>"
    }
}

fun element(tag: String, block: HtmlElement.() -> Unit = {}): HtmlElement =
    HtmlElement(tag).apply(block)

// DSL builder functions:
fun html(block: HtmlElement.() -> Unit) = element("html", block)
fun HtmlElement.head(block: HtmlElement.() -> Unit) = child(element("head", block))
fun HtmlElement.body(block: HtmlElement.() -> Unit) = child(element("body", block))
fun HtmlElement.h1(text: String) = child(element("h1") { +"$text" })
fun HtmlElement.p(text: String, cls: String? = null) = child(element("p") {
    cls?.let { attr("class", it) }
    +"$text"
})
fun HtmlElement.div(cls: String? = null, block: HtmlElement.() -> Unit) = child(element("div") {
    cls?.let { attr("class", it) }
    block()
})
fun HtmlElement.a(href: String, text: String) = child(element("a") {
    attr("href", href)
    +"$text"
})
fun HtmlElement.ul(block: HtmlElement.() -> Unit) = child(element("ul", block))
fun HtmlElement.li(text: String) = child(element("li") { +"$text" })

// Usage — reads almost like HTML!
val page = html {
    head { child(element("title") { +"My Page" }) }
    body {
        div("container") {
            h1("Hello, Kotlin DSL!")
            p("This page was built with a Kotlin DSL.", cls = "intro")
            ul {
                li("Type-safe")
                li("Refactorable")
                li("IDE support")
            }
            a("https://kotlinlang.org", "Learn Kotlin")
        }
    }
}

println(page.build())
```

✅ **You've succeeded when:** The DSL is type-safe (can't put `li` outside `ul`), produces valid HTML, and gets full IDE autocomplete.

---

### 🔵 Intermediate Project: Generic Result Pipeline

```kotlin
// pipeline.kt — Functional Result type with transformation pipeline

sealed class Result<out T> {
    data class Ok<T>(val value: T) : Result<T>()
    data class Err(val error: AppError) : Result<Nothing>()

    fun isOk() = this is Ok
    fun isErr() = this is Err

    fun getOrNull(): T? = (this as? Ok)?.value
    fun errorOrNull(): AppError? = (this as? Err)?.error

    inline fun <R> map(transform: (T) -> R): Result<R> = when (this) {
        is Ok  -> runCatching { Ok(transform(value)) }.getOrElse { Err(AppError.from(it)) }
        is Err -> this
    }

    inline fun <R> flatMap(transform: (T) -> Result<R>): Result<R> = when (this) {
        is Ok  -> runCatching { transform(value) }.getOrElse { Err(AppError.from(it)) }
        is Err -> this
    }

    inline fun mapError(transform: (AppError) -> AppError): Result<T> = when (this) {
        is Ok  -> this
        is Err -> Err(transform(error))
    }

    inline fun recover(handler: (AppError) -> T): Result<T> = when (this) {
        is Ok  -> this
        is Err -> runCatching { Ok(handler(error)) }.getOrElse { Err(AppError.from(it)) }
    }

    inline fun onSuccess(action: (T) -> Unit): Result<T> = also { if (it is Ok) action(it.value) }
    inline fun onError(action: (AppError) -> Unit): Result<T> = also { if (it is Err) action(it.error) }

    fun getOrThrow(): T = when (this) {
        is Ok  -> value
        is Err -> throw error.toException()
    }

    fun getOrElse(default: T): T = (this as? Ok)?.value ?: default
    inline fun getOrElse(default: (AppError) -> T): T = when (this) {
        is Ok  -> value
        is Err -> default(error)
    }
}

sealed class AppError {
    data class NotFound(val resource: String, val id: Any) : AppError()
    data class Validation(val field: String, val message: String) : AppError()
    data class Database(val message: String, val cause: Throwable? = null) : AppError()
    data class Network(val statusCode: Int, val message: String) : AppError()
    data class Unknown(val message: String, val cause: Throwable? = null) : AppError()

    fun toException(): Exception = RuntimeException(toString())

    companion object {
        fun from(e: Throwable) = Unknown(e.message ?: "Unknown error", e)
    }
}

// Railway-oriented programming:
fun validateAge(age: Int): Result<Int> =
    if (age in 0..150) Result.Ok(age)
    else Result.Err(AppError.Validation("age", "Age must be 0-150, got $age"))

fun validateEmail(email: String): Result<String> =
    if ("@" in email && "." in email) Result.Ok(email)
    else Result.Err(AppError.Validation("email", "Invalid email: $email"))

fun createUser(name: String, email: String, age: Int): Result<User> =
    validateEmail(email)
        .flatMap { validEmail ->
            validateAge(age).map { validAge ->
                User(1, name, validEmail)
            }
        }
        .onSuccess { println("Created user: $it") }
        .onError { println("Failed: $it") }

// Usage:
createUser("Aryan", "aryan@example.com", 17)  // Ok
createUser("Aryan", "invalid", 17)             // Err(Validation)
createUser("Aryan", "a@b.com", -5)             // Err(Validation)
```

---

### 🔴 Advanced Project: Coroutine-Based Actor System

```kotlin
// actor.kt — Actor model using coroutines and channels
import kotlinx.coroutines.*
import kotlinx.coroutines.channels.*

// Messages:
sealed class BankMessage {
    data class Deposit(val amount: Double, val response: CompletableDeferred<Double>) : BankMessage()
    data class Withdraw(val amount: Double, val response: CompletableDeferred<Result<Double>>) : BankMessage()
    data class GetBalance(val response: CompletableDeferred<Double>) : BankMessage()
    object Close : BankMessage()
}

// Actor — processes messages sequentially (no race conditions!):
fun CoroutineScope.bankActor(initialBalance: Double = 0.0) = actor<BankMessage> {
    var balance = initialBalance

    for (msg in channel) {  // Process messages one at a time — thread-safe!
        when (msg) {
            is BankMessage.Deposit -> {
                balance += msg.amount
                msg.response.complete(balance)
            }
            is BankMessage.Withdraw -> {
                if (balance >= msg.amount) {
                    balance -= msg.amount
                    msg.response.complete(Result.success(balance))
                } else {
                    msg.response.complete(Result.failure(
                        InsufficientFundsException(msg.amount, balance)
                    ))
                }
            }
            is BankMessage.GetBalance -> {
                msg.response.complete(balance)
            }
            BankMessage.Close -> channel.close()
        }
    }
}

class BankAccount(scope: CoroutineScope, initialBalance: Double = 0.0) {
    private val actor = scope.bankActor(initialBalance)

    suspend fun deposit(amount: Double): Double {
        val response = CompletableDeferred<Double>()
        actor.send(BankMessage.Deposit(amount, response))
        return response.await()
    }

    suspend fun withdraw(amount: Double): kotlin.Result<Double> {
        val response = CompletableDeferred<kotlin.Result<Double>>()
        actor.send(BankMessage.Withdraw(amount, response))
        return response.await()
    }

    suspend fun getBalance(): Double {
        val response = CompletableDeferred<Double>()
        actor.send(BankMessage.GetBalance(response))
        return response.await()
    }

    fun close() { runBlocking { actor.send(BankMessage.Close) } }
}

class InsufficientFundsException(needed: Double, available: Double)
    : Exception("Need $needed but only have $available")

// Test — concurrent transactions with no race conditions!
fun main() = runBlocking {
    val account = BankAccount(this, 1000.0)

    // Concurrent deposits and withdrawals:
    val jobs = (1..100).map { i ->
        launch {
            if (i % 2 == 0) account.deposit(10.0)
            else account.withdraw(5.0)
        }
    }
    jobs.joinAll()

    println("Final balance: ${account.getBalance()}")
    account.close()
}
```

🔥 **Challenge:** Add transaction history, overdraft protection, and an interest calculation coroutine that runs periodically.

---

## ⚠️ 7. Common Mistakes

---

### ❌ Mistake 1: Using `!!` Instead of Safe Calls

```kotlin
// ❌ WRONG — crash waiting to happen:
fun getUserName(user: User?): String {
    return user!!.name  // KotlinNullPointerException if user is null!
}

// ❌ Also wrong — chaining !!:
val city = user!!.address!!.city!!  // Any null = crash!

// ✅ RIGHT — safe navigation:
fun getUserName(user: User?): String {
    return user?.name ?: "Unknown"  // Never crashes
}

// ✅ RIGHT — let for multiple operations:
user?.let { u ->
    val name = u.name
    val email = u.email
    processUser(name, email)
}

// ✅ RIGHT — early return:
fun processUser(user: User?) {
    user ?: return  // Early return if null
    // Here user is smart-cast to non-null User
    println(user.name)
}

// When IS !! acceptable?
// Only when you have 100% certainty it's not null AND the code is
// immediately obvious (like after you just constructed the object):
val parser = createParser()!!  // Only if createParser always returns non-null
// Even then, prefer: requireNotNull(createParser()) { "Parser must be created" }
```

---

### ❌ Mistake 2: Mutable Collections Exposed as Read-Only

```kotlin
// ❌ WRONG — the cast is easy to do from outside!
class UserManager {
    private val _users = mutableListOf<User>()
    val users: List<User> = _users  // "Read-only" view... but easily cast!
}

val manager = UserManager()
// From outside — someone can cast and mutate!
(manager.users as MutableList<User>).add(hackerUser)  // ❌ Works! Security hole!

// ✅ RIGHT — use toList() to create a true copy:
class UserManager2 {
    private val _users = mutableListOf<User>()
    val users: List<User> get() = _users.toList()  // Returns a copy each time
    // OR:
    val userSnapshot: List<User> get() = _users.toList()
}

// ✅ RIGHT — immutable backing field with defensive copy:
class Config {
    private val _settings = mutableMapOf<String, Any>()
    val settings: Map<String, Any> get() = _settings.toMap()  // Immutable copy
}
```

---

### ❌ Mistake 3: Coroutine Scope Misuse

```kotlin
// ❌ WRONG — GlobalScope leaks (lives until app dies):
GlobalScope.launch {
    while (true) {
        syncData()  // This NEVER stops, even after Activity is destroyed!
        delay(60_000)
    }
}

// ❌ WRONG — blocking the main thread with runBlocking in production:
class MyRepository {
    fun fetchData(): Data = runBlocking {  // ❌ Blocks the calling thread!
        api.fetchData()
    }
}

// ✅ RIGHT — use structured concurrency with proper scope:
class MyViewModel : ViewModel() {
    init {
        viewModelScope.launch {  // Cancelled when ViewModel is cleared
            while (true) {
                syncData()
                delay(60_000)
            }
        }
    }
}

// ✅ RIGHT — suspend functions instead of runBlocking:
class MyRepository {
    suspend fun fetchData(): Data = api.fetchData()  // Suspend, don't block!
}

// ❌ WRONG — creating new scope inside suspend function:
suspend fun badExample() {
    CoroutineScope(Dispatchers.IO).launch {  // This scope is unstructured!
        riskyOperation()
    }
}

// ✅ RIGHT — use coroutineScope for structured child coroutines:
suspend fun goodExample() {
    coroutineScope {
        launch { riskyOperation() }  // Cancellation propagates correctly
    }
}
```

---

### ❌ Mistake 4: Ignoring Data Class Mutability

```kotlin
// ❌ WRONG — var in data class enables bugs:
data class UserState(
    var name: String,        // var — mutable!
    var isLoggedIn: Boolean  // var — mutable!
)

val state = UserState("Aryan", false)
processState(state)  // processState might mutate state internally!
// After this call, state.name could be anything!

// ❌ WRONG — mutable collection in data class:
data class Cart(val items: MutableList<CartItem>)  // Internal list is mutable!
val cart = Cart(mutableListOf())
cart.items.add(CartItem("book"))  // "Immutable" cart... not really!

// ✅ RIGHT — val + immutable collections in data classes:
data class UserState2(
    val name: String,        // val — immutable
    val isLoggedIn: Boolean  // val — immutable
)

data class Cart2(val items: List<CartItem> = emptyList()) {  // Read-only list
    fun addItem(item: CartItem) = copy(items = items + item)  // Returns new Cart2
}

// ✅ Usage — pure functional update:
val cart = Cart2()
val withBook = cart.addItem(CartItem("book"))  // New cart, original unchanged!

data class CartItem(val name: String)
```

---

### ❌ Mistake 5: String Concatenation in Loops

```kotlin
// ❌ WRONG — creates O(n²) intermediate strings:
fun buildReport(items: List<String>): String {
    var result = ""
    for (item in items) {
        result += "$item\n"  // Creates new String object each time!
    }
    return result
}

// ✅ RIGHT — buildString or joinToString:
fun buildReport2(items: List<String>): String {
    return buildString {
        for (item in items) {
            appendLine(item)
        }
    }
}

// ✅ EVEN SIMPLER — joinToString:
fun buildReport3(items: List<String>) = items.joinToString("\n")

// ✅ MOST FLEXIBLE — StringBuilder:
fun buildReport4(items: List<String>): String {
    val sb = StringBuilder()
    for ((index, item) in items.withIndex()) {
        sb.append("${index + 1}. ")
        sb.appendLine(item)
    }
    return sb.toString()
}
```

---

### ❌ Mistake 6: `object` vs `companion object` Confusion

```kotlin
// ❌ WRONG — using object when companion object is needed:
class MyClass {
    object MyFactory {   // This is an inner singleton, not static!
        fun create() = MyClass()
    }
}
// Usage: MyClass.MyFactory.create()  — ugly!

// ✅ RIGHT — companion object for "static" members:
class MyClass {
    companion object {
        fun create() = MyClass()
        const val MAX_SIZE = 100
    }
}
// Usage: MyClass.create()  — clean, looks static!
// Usage: MyClass.MAX_SIZE  — same

// companion object can implement interfaces:
interface Factory<T> {
    fun create(): T
}

class MyWidget private constructor(val x: Int) {
    companion object : Factory<MyWidget> {
        override fun create() = MyWidget(0)
        fun create(x: Int) = MyWidget(x)
    }
}

val w1 = MyWidget.create()     // 0
val w2 = MyWidget.create(42)   // 42
```

---

## 🔥 8. Pro Tips & Hidden Tricks

---

### 💎 Tip 1: Delegated Properties — DRY Property Logic

```kotlin
import kotlin.properties.Delegates
import kotlin.reflect.KProperty

// ── BUILT-IN DELEGATES ────────────────────────────────────────────────────
// lazy — compute on first access, cache result:
class ExpensiveService {
    val heavyResource: HeavyResource by lazy {
        println("Initializing HeavyResource...")
        HeavyResource()  // Only called once, result cached
    }

    // Thread-safe lazy (default):
    val safeResource by lazy(LazyThreadSafetyMode.SYNCHRONIZED) { HeavyResource() }

    // Non-thread-safe lazy (faster in single-threaded):
    val fastResource by lazy(LazyThreadSafetyMode.NONE) { HeavyResource() }
}

// observable — watch for changes:
var score: Int by Delegates.observable(0) { property, oldValue, newValue ->
    println("${property.name}: $oldValue → $newValue")
    if (newValue > 100) println("🎉 High score!")
}
score = 50   // "score: 0 → 50"
score = 110  // "score: 50 → 110", "🎉 High score!"

// vetoable — can reject changes:
var age: Int by Delegates.vetoable(0) { _, _, newValue ->
    newValue in 0..150  // Return true to accept, false to reject
}
age = 25    // Accepted
age = -5    // Rejected — age stays 25
age = 200   // Rejected — age stays 25

// notNull — throw if accessed before set:
var name: String by Delegates.notNull()
// println(name)  // IllegalStateException if accessed before assignment
name = "Aryan"
println(name)   // "Aryan"

// ── CUSTOM DELEGATE ───────────────────────────────────────────────────────
// Delegate that validates and trims strings:
class TrimmedString(private val maxLength: Int = Int.MAX_VALUE) {
    private var value: String = ""

    operator fun getValue(thisRef: Any?, property: KProperty<*>): String = value

    operator fun setValue(thisRef: Any?, property: KProperty<*>, newValue: String) {
        value = newValue.trim().take(maxLength)
    }
}

class Profile {
    var displayName: String by TrimmedString(50)   // Max 50 chars, auto-trimmed
    var bio: String by TrimmedString(200)           // Max 200 chars, auto-trimmed
}

// Map delegate — store properties in a map:
class MappedUser(val map: Map<String, Any?>) {
    val name: String by map
    val age: Int by map
    val email: String by map
}

val user = MappedUser(mapOf("name" to "Aryan", "age" to 17, "email" to "a@b.com"))
println(user.name)   // "Aryan" — reads from map!
println(user.age)    // 17

class HeavyResource
```

---

### 💎 Tip 2: Context Receivers — Multiple Implicit This (Kotlin 1.6+)

```kotlin
// Context receivers allow functions to require multiple contexts:
// This is a preview feature — enable with -Xcontext-receivers

interface Logger {
    fun log(message: String)
}

interface Database {
    fun query(sql: String): List<Map<String, Any>>
}

interface Analytics {
    fun track(event: String, data: Map<String, Any> = emptyMap())
}

// Function that requires ALL three contexts:
context(Logger, Database, Analytics)
fun processUserAction(userId: Int, action: String) {
    log("Processing action '$action' for user $userId")  // Logger.log
    val userData = query("SELECT * FROM users WHERE id = $userId")  // Database.query
    track("user_action", mapOf("userId" to userId, "action" to action))  // Analytics.track
    log("Action completed for ${userData.firstOrNull()?.get("name")}")
}

// Usage — all three contexts must be in scope:
with(logger) {
    with(database) {
        with(analytics) {
            processUserAction(42, "purchase")
        }
    }
}
```

---

### 💎 Tip 3: `buildString`, `buildList`, `buildMap` — Functional Builders

```kotlin
// Build complex structures with declarative blocks:
val json = buildString {
    append("{")
    append("""  "name": "Aryan",""")
    appendLine()
    append("""  "age": 17""")
    append("}")
}

// buildList — create list with complex logic:
val numbers = buildList {
    add(1)
    addAll(2..10)
    removeIf { it % 3 == 0 }  // Remove multiples of 3
    sortDescending()
}
// [10, 8, 7, 5, 4, 2, 1]

// buildMap — create map with complex logic:
val config = buildMap {
    put("host", "localhost")
    put("port", 5432)
    val env = System.getenv("ENV") ?: "development"
    if (env == "production") {
        put("ssl", true)
        put("poolSize", 20)
    } else {
        put("ssl", false)
        put("poolSize", 5)
    }
}

// buildSet:
val uniqueWords = buildSet {
    addAll("hello world hello kotlin world".split(" "))
    remove("world")
}  // {hello, kotlin}
```

---

### 💎 Tip 4: `contract` — Kotlin Contracts for Smart Casts

```kotlin
import kotlin.contracts.*

// Contracts help the compiler understand what a function guarantees:

@OptIn(ExperimentalContracts::class)
fun String?.isNullOrBlankFixed(): Boolean {
    contract {
        returns(false) implies (this@isNullOrBlankFixed != null)
    }
    return this == null || this.isBlank()
}

// Now smart cast works:
val name: String? = getUserName()
if (!name.isNullOrBlankFixed()) {
    println(name.length)  // Smart cast! name is non-nullable String here
}

// callsInPlace — tell compiler how many times a lambda is called:
@OptIn(ExperimentalContracts::class)
inline fun <T> myRun(block: () -> T): T {
    contract {
        callsInPlace(block, InvocationKind.EXACTLY_ONCE)  // Called exactly once
    }
    return block()
}

// Now val initialization works through myRun:
val name2: String
myRun { name2 = "Aryan" }  // Compiler knows name2 is definitely initialized
println(name2)              // No "name2 might not be initialized" error!

fun getUserName(): String? = "Aryan"
```

---

### 💎 Tip 5: `crossinline`, `noinline` & Inline Class Tricks

```kotlin
// ── UNDERSTANDING INLINE ──────────────────────────────────────────────────
// Without inline: lambda creates an object allocation every call
// With inline: lambda code is copied to call site — zero overhead!

// timing function — inline eliminates all overhead:
inline fun <T> benchmark(label: String, block: () -> T): T {
    val start = System.nanoTime()
    val result = block()
    val end = System.nanoTime()
    println("$label: ${(end - start) / 1_000_000}ms")
    return result
}

// Can use return inside inlined lambda:
fun findFirstPositive(numbers: List<Int>): Int? {
    numbers.forEach { n ->         // forEach is inline!
        if (n > 0) return n        // This returns from findFirstPositive!
        // Without inline, this would be a local return only
    }
    return null
}

// Use crossinline when lambda might be called in different context:
inline fun doAsync(crossinline block: suspend () -> Unit) {
    CoroutineScope(Dispatchers.IO).launch {
        block()  // Called in different context — crossinline prevents non-local return
    }
}

// noinline for lambdas stored or passed elsewhere:
inline fun processAndStore(
    inlinedAction: () -> Unit,
    noinline storedAction: () -> Unit  // Will be stored — can't be inlined
) {
    inlinedAction()
    handlers.add(storedAction)  // Can store because not inlined
}

val handlers = mutableListOf<() -> Unit>()
```

---

## 🚀 9. Advanced Concepts (Expert Level)

---

### Advanced Concept 1: Type-Safe Builders & DSLs

```kotlin
// Kotlin DSLs use receiver lambdas — functions with a receiver type
// block: ReceiverType.() -> Unit  means: inside block, 'this' = ReceiverType

// ── GRADLE-STYLE DSL ──────────────────────────────────────────────────────
@DslMarker
annotation class QueryDsl  // Prevents outer receiver access inside nested scope

@QueryDsl
class SelectClause {
    private val columns = mutableListOf<String>()
    fun column(name: String) { columns.add(name) }
    operator fun String.unaryPlus() { columns.add(this) }
    fun build() = if (columns.isEmpty()) "*" else columns.joinToString(", ")
}

@QueryDsl
class WhereClause {
    private val conditions = mutableListOf<String>()
    fun condition(sql: String) { conditions.add(sql) }
    fun eq(column: String, value: Any) { conditions.add("$column = ${value.formatted()}") }
    fun gt(column: String, value: Number) { conditions.add("$column > $value") }
    fun like(column: String, pattern: String) { conditions.add("$column LIKE '$pattern'") }
    fun and(block: WhereClause.() -> Unit) { apply(block) }
    private fun Any.formatted() = if (this is String) "'$this'" else this.toString()
    fun build() = if (conditions.isEmpty()) "" else "WHERE ${conditions.joinToString(" AND ")}"
}

@QueryDsl
class OrderByClause {
    private val orders = mutableListOf<String>()
    fun asc(column: String) { orders.add("$column ASC") }
    fun desc(column: String) { orders.add("$column DESC") }
    fun build() = if (orders.isEmpty()) "" else "ORDER BY ${orders.joinToString(", ")}"
}

class QueryBuilder(private val table: String) {
    private var selectClause = SelectClause()
    private var whereClause = WhereClause()
    private var orderByClause = OrderByClause()
    private var limitClause: Int? = null

    fun select(block: SelectClause.() -> Unit) { selectClause.apply(block) }
    fun where(block: WhereClause.() -> Unit) { whereClause.apply(block) }
    fun orderBy(block: OrderByClause.() -> Unit) { orderByClause.apply(block) }
    fun limit(n: Int) { limitClause = n }

    fun build(): String {
        val parts = mutableListOf(
            "SELECT ${selectClause.build()}",
            "FROM $table",
            whereClause.build(),
            orderByClause.build(),
        )
        limitClause?.let { parts.add("LIMIT $it") }
        return parts.filter { it.isNotEmpty() }.joinToString(" ")
    }
}

fun query(table: String, block: QueryBuilder.() -> Unit): String =
    QueryBuilder(table).apply(block).build()

// Usage — reads like SQL but is completely type-safe!
val sql = query("users") {
    select {
        column("id")
        +"username"
        +"email"
    }
    where {
        eq("role", "admin")
        gt("age", 18)
        like("email", "%@example.com")
    }
    orderBy {
        desc("created_at")
        asc("username")
    }
    limit(20)
}
println(sql)
// SELECT id, username, email FROM users WHERE role = 'admin' AND age > 18 AND email LIKE '%@example.com' ORDER BY created_at DESC, username ASC LIMIT 20
```

---

### Advanced Concept 2: Kotlin Multiplatform (KMP)

```kotlin
// Kotlin Multiplatform — share code between Android, iOS, JVM, JS, Native!

// ── SHARED MODULE (commonMain) ─────────────────────────────────────────────
// This code runs on ALL platforms:

data class WeatherData(
    val temperature: Double,
    val humidity: Int,
    val description: String
)

// expect/actual — platform-specific implementations:
expect class Platform() {
    val platformName: String
}

// Platform-agnostic business logic:
class WeatherService(private val api: WeatherApi) {
    suspend fun getCurrentWeather(city: String): Result<WeatherData> {
        return try {
            Result.success(api.fetchWeather(city))
        } catch (e: Exception) {
            Result.failure(e)
        }
    }

    fun formatTemperature(celsius: Double, useFahrenheit: Boolean = false): String {
        return if (useFahrenheit) {
            "${"%.1f".format(celsius * 9 / 5 + 32)}°F"
        } else {
            "${"%.1f".format(celsius)}°C"
        }
    }
}

interface WeatherApi {
    suspend fun fetchWeather(city: String): WeatherData
}

// ── ANDROID (androidMain) ─────────────────────────────────────────────────
// actual class Platform() {
//     actual val platformName = "Android ${android.os.Build.VERSION.SDK_INT}"
// }

// ── iOS (iosMain) ─────────────────────────────────────────────────────────
// actual class Platform() {
//     actual val platformName = UIDevice.currentDevice.systemName()
// }

// ── KMP Project Structure ──────────────────────────────────────────────────
/*
shared/
  src/
    commonMain/kotlin/     <- Shared code (all platforms)
    commonTest/kotlin/     <- Shared tests
    androidMain/kotlin/    <- Android-specific implementations
    iosMain/kotlin/        <- iOS-specific implementations
    jvmMain/kotlin/        <- JVM-specific implementations
    jsMain/kotlin/         <- JavaScript-specific implementations

androidApp/                <- Android application
iosApp/                    <- iOS application (Xcode project)
*/
```

---

### Advanced Concept 3: Arrow — Functional Kotlin

```kotlin
// Arrow is the functional programming library for Kotlin
// Provides: Either, Option, Validated, IO, Optics, etc.
// https://arrow-kt.io

// ── EITHER — explicit error handling ──────────────────────────────────────
import arrow.core.*
import arrow.core.raise.*

// Either<Error, Value>:
fun divide(a: Int, b: Int): Either<String, Int> =
    if (b == 0) "Cannot divide by zero".left()
    else (a / b).right()

val result: Either<String, Int> = divide(10, 2)
result.fold(
    ifLeft = { error -> println("Error: $error") },
    ifRight = { value -> println("Result: $value") }
)

// Monadic chaining:
val chain = divide(10, 2)
    .flatMap { divide(it, 2) }
    .map { it * 10 }  // Result<String, 25>

// ── RAISE — the modern way in Arrow 2.x ───────────────────────────────────
data class ValidationError(val field: String, val message: String)

fun Raise<ValidationError>.validateName(name: String): String {
    ensure(name.isNotBlank()) { ValidationError("name", "Name cannot be blank") }
    ensure(name.length >= 2) { ValidationError("name", "Name too short") }
    return name.trim()
}

fun Raise<ValidationError>.validateAge(age: Int): Int {
    ensure(age >= 0) { ValidationError("age", "Age cannot be negative") }
    ensure(age <= 150) { ValidationError("age", "Age too large") }
    return age
}

val userResult: Either<ValidationError, User> = either {
    val name = validateName("Aryan")
    val age = validateAge(17)
    User(1, name, "aryan@example.com")  // Only reached if all validations pass!
}

// ── OPTION ────────────────────────────────────────────────────────────────
val some: Option<Int> = Some(42)
val none: Option<Int> = None

some.map { it * 2 }           // Some(84)
none.map { it * 2 }           // None
some.getOrElse { -1 }         // 42
none.getOrElse { -1 }         // -1
some.filter { it > 100 }      // None
```

---

### ⚡ Performance & Optimization Table

| Technique                          | Impact   | When to Use                                         |
|------------------------------------|----------|-----------------------------------------------------|
| `sequence {}` instead of list ops  | High     | Large/infinite data; avoid intermediate collections |
| `inline` functions with lambdas    | High     | Hot paths with higher-order functions               |
| `@JvmInline value class`           | High     | Wrapping primitives without boxing overhead         |
| `arrayOfNulls` vs `listOf`         | Medium   | Known-size collections with primitives              |
| `Dispatchers.Default` for CPU work | High     | Move heavy computation off main/IO thread           |
| `StateFlow` over `LiveData`        | Medium   | More idiomatic, coroutine-native observable state   |
| `buildList` / `buildMap`           | Medium   | Avoid creating intermediate mutable + converting    |
| Lazy properties with `by lazy`     | High     | Expensive initialization — defer until needed       |
| `crossinline` lambda storage       | Low      | When inlined lambda is stored in a collection       |
| `@Volatile` for shared state       | Medium   | Simple flags visible across threads (avoid Mutex)   |
| Coroutine `Channel` over callbacks | High     | Replace callback-based APIs with suspend functions  |

---

## 💀 10. 0.01% Hidden Secrets — Ultra Elite

---

### 🔮 Secret 1: `@JvmName`, `@JvmOverloads`, `@JvmField` — Java Interop

```kotlin
// ── @JvmName — rename Kotlin declaration for Java callers ─────────────────
// Kotlin creates utility classes named after the file with "Kt" suffix:
// utils.kt → UtilsKt class in Java

@file:JvmName("Utils")  // Java sees it as "Utils" not "UtilsKt"
package com.example

fun greet(name: String) = "Hello, $name!"

// In Java: Utils.greet("World")  instead of  UtilsKt.greet("World")

// ── @JvmOverloads — generate Java overloads for default params ────────────
// Kotlin with default parameters:
fun connect(host: String, port: Int = 5432, ssl: Boolean = false) { }
// Java can ONLY call connect(host, port, ssl) — no default support in Java!

// With @JvmOverloads — generates all overloads:
@JvmOverloads
fun connect2(host: String, port: Int = 5432, ssl: Boolean = false) { }
// Java can call: connect2("host") or connect2("host", 5432) or connect2("host", 5432, true)

// In classes (especially for Android Views):
class MyView @JvmOverloads constructor(
    context: Context,
    attrs: AttributeSet? = null,
    defStyleAttr: Int = 0
) : View(context, attrs, defStyleAttr)

// ── @JvmField — expose as Java field (no getter/setter) ────────────────────
class Config {
    @JvmField
    var maxConnections = 10  // Java: config.maxConnections directly
    // Without @JvmField: Java needs config.getMaxConnections() / setMaxConnections()
}

// ── @JvmStatic — true static method in companion object ────────────────────
class DatabaseFactory {
    companion object {
        @JvmStatic
        fun create(url: String): Database = TODO()
        // Java: DatabaseFactory.create(url) instead of DatabaseFactory.Companion.create(url)
    }
}

// ── @Throws — declare checked exceptions for Java ─────────────────────────
@Throws(IOException::class)  // Java callers know to handle this exception
fun readFile(path: String): String = File(path).readText()

class Context
class AttributeSet
class View(c: Context, a: AttributeSet?, d: Int)
class Database
interface IOException
class File(path: String) { fun readText() = "" }
```

---

### 🔮 Secret 2: Kotlin Symbol Processing (KSP) — Compile-Time Code Generation

```kotlin
// KSP is the modern annotation processor for Kotlin
// Faster than KAPT, understands Kotlin-specific constructs

// Custom annotation:
@Target(AnnotationTarget.CLASS)
@Retention(AnnotationRetention.SOURCE)  // Only needed at compile time
annotation class AutoFactory

// KSP processor would generate a factory for this class at compile time:
@AutoFactory
data class EmailMessage(
    val to: String,
    val subject: String,
    val body: String
)
// Generated: EmailMessageFactory { fun create(to, subject, body): EmailMessage }

// Real-world KSP examples:
// Room: @Entity, @Dao → generates SQL and Java code
// Moshi: @JsonClass → generates JSON adapters
// Dagger/Hilt: @Inject → generates dependency injection code
// Kotlin Serialization: @Serializable → generates serializers

// Understanding what KSP does vs what you write:
@kotlinx.serialization.Serializable  // This annotation triggers KSP processor
data class UserDto(val name: String, val age: Int)
// KSP generates: UserDtoSerializer : KSerializer<UserDto> — invisible to you!

val json = kotlinx.serialization.json.Json.encodeToString(UserDto("Aryan", 17))
// "{"name":"Aryan","age":17}" — zero reflection, pure compile-time generated code!
```

---

### 🔮 Secret 3: Destructuring and Component Functions

```kotlin
// Kotlin generates componentN() for data classes:
data class Point(val x: Double, val y: Double, val z: Double = 0.0)

val p = Point(1.0, 2.0, 3.0)
val (x, y, z) = p  // Calls p.component1(), p.component2(), p.component3()

// Use _ to skip components:
val (_, yOnly, _) = p  // Only care about y

// In loops:
val points = listOf(Point(1.0, 2.0), Point(3.0, 4.0))
for ((x, y) in points) {
    println("($x, $y)")
}

// Lambda destructuring:
points.forEach { (x, y) -> println("$x, $y") }
mapOf("a" to 1, "b" to 2).forEach { (key, value) -> println("$key=$value") }

// Add componentN to ANY class with operator functions:
class Matrix2x2(
    val a: Double, val b: Double,
    val c: Double, val d: Double
) {
    operator fun component1() = a
    operator fun component2() = b
    operator fun component3() = c
    operator fun component4() = d
    val determinant get() = a * d - b * c
}

val m = Matrix2x2(1.0, 2.0, 3.0, 4.0)
val (a, b, c, d) = m  // Works! Custom componentN functions

// Destructuring return values from functions:
fun minMax(list: List<Int>) = list.min() to list.max()  // Returns Pair
val (min, max) = minMax(listOf(3, 1, 4, 1, 5, 9))  // (1, 9)

// Multiple return values with data class:
data class DivisionResult(val quotient: Int, val remainder: Int)
fun divmod(a: Int, b: Int) = DivisionResult(a / b, a % b)
val (quotient, remainder) = divmod(17, 5)  // (3, 2)
```

---

### 🔮 Secret 4: `Sequence` Source Code — How Lazy Works

```kotlin
// Understanding Kotlin sequences helps write efficient pipelines

// Each sequence operation returns a new Sequence object (lazy evaluation):
// TransformingSequence, FilteringSequence, TakingSequence etc.
// Only when terminal operation (toList, sum, first, etc.) is called does
// evaluation happen — element by element through ALL transforms.

// Custom sequence with complex logic:
fun sieveOfEratosthenes(): Sequence<Int> = sequence {
    val marked = HashMap<Int, Int>()
    var candidate = 2

    while (true) {
        if (candidate !in marked) {
            yield(candidate)  // This is a prime!
            marked[candidate * candidate] = candidate
        } else {
            var composite = candidate
            while (composite in marked) {
                composite += marked.remove(composite)!!
                marked[composite] = marked.getOrDefault(composite, 0) + candidate
            }
        }
        candidate++
    }
}

// Memory efficient — never stores all primes!
val first100Primes = sieveOfEratosthenes().take(100).toList()
val primesUnder1000 = sieveOfEratosthenes().takeWhile { it < 1000 }.toList()
val sumOfFirst10Primes = sieveOfEratosthenes().take(10).sum()

// Sequence fusion — ALL operations run as one pass:
val result = (1..1_000_000).asSequence()
    .filter { it % 2 == 0 }     // Not a separate pass!
    .map { it * it }             // Not a separate pass!
    .takeWhile { it < 1000 }     // Not a separate pass!
    .sum()                       // ONE pass through data, stops early!
// This is 10,000× more efficient than list operations!
```

---

### 🔮 Secret 5: `Continuation` — The Foundation of Coroutines

```kotlin
// suspend functions compile to state machines!
// Every suspend function takes a hidden Continuation parameter.

// What you write:
suspend fun fetchAndProcess(): String {
    val data = fetchData()        // Suspend point 1
    val processed = process(data) // Suspend point 2
    return processed
}

// What the compiler generates (simplified):
// class FetchAndProcessContinuation : Continuation<String> {
//     var label = 0
//     var data: String? = null
//     
//     override fun resumeWith(result: Result<String>) {
//         when (label) {
//             0 -> {
//                 label = 1
//                 fetchData(this)  // Pass continuation as callback
//             }
//             1 -> {
//                 data = result.getOrThrow()
//                 label = 2
//                 process(data!!, this)
//             }
//             2 -> {
//                 continuation.resumeWith(result)  // Return to caller
//             }
//         }
//     }
// }

// This is why coroutines have zero overhead vs threads — they're just state machines!

// You can interact with continuations directly:
import kotlin.coroutines.*

suspend fun <T> suspendUntilReady(): T = suspendCoroutine { continuation ->
    // Store continuation, call continuation.resume(value) when ready
    onDataReady { value -> continuation.resume(value) }
    onError { error -> continuation.resumeWithException(error) }
}

// suspendCancellableCoroutine — for cancellation support:
suspend fun <T> awaitCallback(): T = suspendCancellableCoroutine { continuation ->
    val callback = object : Callback<T> {
        override fun onSuccess(value: T) = continuation.resume(value)
        override fun onError(e: Exception) = continuation.resumeWithException(e)
    }
    startAsync(callback)
    continuation.invokeOnCancellation { cancelAsync(callback) }
}

interface Callback<T> { fun onSuccess(value: T); fun onError(e: Exception) }
fun onDataReady(block: (String) -> Unit) {}
fun onError(block: (Throwable) -> Unit) {}
suspend fun fetchData() = "data"
suspend fun process(data: String) = data.uppercase()
fun <T> startAsync(callback: Callback<T>) {}
fun <T> cancelAsync(callback: Callback<T>) {}
```

---

### 🔮 Secret 6: Operator Overloading — Complete List

```kotlin
// Every Kotlin operator maps to a function — all overloadable!

data class Vector2D(val x: Double, val y: Double) {
    // Arithmetic:
    operator fun plus(other: Vector2D) = Vector2D(x + other.x, y + other.y)   // a + b
    operator fun minus(other: Vector2D) = Vector2D(x - other.x, y - other.y)  // a - b
    operator fun times(scalar: Double) = Vector2D(x * scalar, y * scalar)      // a * 2.0
    operator fun div(scalar: Double) = Vector2D(x / scalar, y / scalar)        // a / 2.0
    operator fun rem(other: Vector2D) = TODO()                                  // a % b
    operator fun unaryMinus() = Vector2D(-x, -y)                               // -a
    operator fun unaryPlus() = this                                            // +a

    // Augmented assignment (if not defined, falls back to op + assignment):
    // operator fun plusAssign(other: Vector2D) { /* mutable only */ }  // a += b

    // Comparison (must also implement Comparable<T>):
    operator fun compareTo(other: Vector2D) = length().compareTo(other.length()) // a < b

    // Index:
    operator fun get(index: Int) = when(index) { 0 -> x; 1 -> y; else -> throw IndexOutOfBoundsException() } // a[0]
    // operator fun set(index: Int, value: Double) { /* mutable */ }  // a[0] = 1.0

    // In/contains:
    operator fun contains(value: Double) = x == value || y == value  // value in v

    // Invoke:
    operator fun invoke(scalar: Double) = times(scalar)  // v(2.0) same as v * 2.0

    // Destructuring:
    operator fun component1() = x
    operator fun component2() = y

    // Range:
    operator fun rangeTo(other: Vector2D) = VectorRange(this, other)  // a..b

    fun length() = Math.sqrt(x * x + y * y)
    override fun toString() = "($x, $y)"
}

// Extension operator for 2.0 * vector (reversed):
operator fun Double.times(v: Vector2D) = v.times(this)

val v1 = Vector2D(1.0, 2.0)
val v2 = Vector2D(3.0, 4.0)

val sum = v1 + v2          // (4.0, 6.0)
val scaled = v1 * 3.0     // (3.0, 6.0)
val scaled2 = 3.0 * v1    // (3.0, 6.0) — extension
val neg = -v1              // (-1.0, -2.0)
val (x, y) = v1           // x=1.0, y=2.0
println(1.0 in v1)        // true
println(v1(2.0))          // (2.0, 4.0) — invoke operator

class VectorRange(val start: Vector2D, val end: Vector2D)
```

---

### 🔮 Secret 7: `@DslMarker` — Preventing DSL Scope Leaks

```kotlin
// Without @DslMarker, inner DSL blocks can accidentally access outer receivers:
// This creates confusing bugs and reduces DSL clarity

// ── WITHOUT @DslMarker (problematic) ──────────────────────────────────────
class HtmlBuilder {
    fun div(block: DivBuilder.() -> Unit) = DivBuilder().apply(block)
}

class DivBuilder {
    fun p(block: PBuilder.() -> Unit) = PBuilder().apply(block)
}

class PBuilder {
    fun text(s: String) {}
}

// Problem: inside p{}, you can accidentally call div() on the outer HtmlBuilder!
// html {
//     div {
//         p {
//             div { /* ❌ This calls HtmlBuilder.div — confusing! */ }
//         }
//     }
// }

// ── WITH @DslMarker (correct) ──────────────────────────────────────────────
@DslMarker
annotation class HtmlDsl

@HtmlDsl
class SafeHtmlBuilder {
    fun div(block: SafeDivBuilder.() -> Unit) = SafeDivBuilder().apply(block)
}

@HtmlDsl
class SafeDivBuilder {
    fun p(block: SafePBuilder.() -> Unit) = SafePBuilder().apply(block)
    fun text(s: String) {}
}

@HtmlDsl
class SafePBuilder {
    fun text(s: String) {}
    // div {} here would be a COMPILE ERROR — outer receiver is restricted!
}

// Now the DSL is safe:
// SafeHtmlBuilder().apply {
//     div {
//         p {
//             text("Hello")
//             // div {} ❌ Compile error — can't access outer div here!
//         }
//     }
// }
```

---

### 🔮 Secret 8: Flows — Under the Hood

```kotlin
// Flow is cold — no code runs until collect() is called
// Each collect() call runs the flow from scratch

val coldFlow = flow {
    println("Flow started!")  // Runs every time collect() is called
    emit(1)
    emit(2)
    emit(3)
}

// Hot flows — emit regardless of collectors:
// StateFlow — holds current value, replays to new collectors
// SharedFlow — configurable replay buffer

// ── FLOW CANCELLATION AND EXCEPTIONS ─────────────────────────────────────
val safeFlow = flow {
    emit(1)
    emit(2)
    throw RuntimeException("Error in flow!")
}.catch { e ->
    println("Caught: ${e.message}")
    emit(-1)  // Can emit recovery value
}.onCompletion { cause ->
    println("Flow completed. Cause: $cause")
}

// ── COMBINING FLOWS ────────────────────────────────────────────────────────
val flow1 = flowOf(1, 2, 3)
val flow2 = flowOf("a", "b", "c")

// zip — pair elements:
flow1.zip(flow2) { n, s -> "$n$s" }  // [1a, 2b, 3c]

// combine — use latest from both:
val ticker = flow { while(true) { emit(System.currentTimeMillis()); delay(100) } }
val data = flow { while(true) { emit(fetchLatestData()); delay(1000) } }
ticker.combine(data) { time, d -> "At $time: $d" }  // Emits whenever EITHER changes

// flatMapLatest — cancel previous when new value arrives:
val searchQuery = MutableStateFlow("")
searchQuery.flatMapLatest { query ->
    flow { emit(searchApi(query)) }  // Old search cancelled when query changes
}

// merge — interleave multiple flows:
merge(flow1, flow2)  // Emits from either flow as values arrive

// buffer — allow producer to run ahead of consumer:
flow { repeat(1000) { emit(it) } }
    .buffer(64)          // Producer can be 64 ahead of consumer
    .collect { process(it) }

suspend fun fetchLatestData() = "data"
suspend fun searchApi(query: String) = listOf<String>()
suspend fun process(item: Int) { delay(10) }
```

---

### 🔮 Secret 9: `inline class` Memory Layout

```kotlin
// @JvmInline value class — zero boxing overhead!

// Without value class:
data class Money(val amount: Long, val currency: String)
// In JVM: creates a separate heap object with header + two fields

// With value class (single property only):
@JvmInline
value class Cents(val value: Long) {
    val dollars get() = value / 100
    val formatted get() = "$${dollars}.${value % 100:02d}"

    operator fun plus(other: Cents) = Cents(value + other.value)
    operator fun minus(other: Cents) = Cents(value - other.value)
    operator fun times(factor: Int) = Cents(value * factor)
}

// At JVM bytecode level, Cents is just a Long — NO object allocation!
val price: Cents = Cents(1499)        // Just Long(1499) in JVM
val tax: Cents = Cents(120)
val total: Cents = price + tax        // Just Long arithmetic — no boxing!
println(total.formatted)              // "$16.19"

// Use cases for value classes:
@JvmInline value class UserId(val value: Int)
@JvmInline value class ProductId(val value: Int)
@JvmInline value class Quantity(val value: Int) {
    init { require(value > 0) { "Quantity must be positive" } }
}
@JvmInline value class Email(val value: String) {
    init { require("@" in value) { "Invalid email" } }
}

// Type safety with zero runtime cost:
fun processOrder(userId: UserId, productId: ProductId, qty: Quantity) {
    // Can't accidentally swap userId and productId — different types!
}
processOrder(UserId(42), ProductId(123), Quantity(5))
// processOrder(ProductId(123), UserId(42), Quantity(5))  // ❌ Compile error!
```

---

### 🔮 Secret 10: Kotlin Internal Compiler Plugins

```kotlin
// Kotlin has a plugin system that operates on the compiler level!
// Some important compiler plugins:

// 1. kotlinx.serialization — @Serializable
// Generates serializer classes at compile time (KSP or IR plugin)

// 2. Jetpack Compose compiler plugin
// Transforms @Composable functions into efficient state-machine code

// 3. Parcelize plugin (Android)
@android.os.Parcelize  // This is a COMPILER PLUGIN, not just an annotation!
data class MyParcelable(val id: Int, val name: String) : android.os.Parcelable
// Generates all Parcelable boilerplate at compile time — 0 runtime overhead!

// 4. All-open / No-arg (for Spring, Hibernate)
// Makes all classes open or adds no-arg constructors at compile time

// 5. Lombok alternative — @field:JvmField, @get:JvmName etc.
// Kotlin annotations that change bytecode generation

// 6. Coroutines compiler plugin
// Transforms suspend functions into state machines at compile time

// Understanding the IR (Intermediate Representation) pipeline:
// Kotlin Source → Frontend (parsing, type checking, resolve)
//              → IR (KotlinIR — platform-independent)
//              → Backend (JVM bytecode, JS, LLVM Native)
// Compiler plugins can hook in at ANY stage!

// Writing a simple compiler plugin is possible but advanced.
// Most developers interact with plugins through Gradle configuration:
// build.gradle.kts:
// plugins {
//     kotlin("plugin.serialization") version "1.9.22"
//     id("kotlin-parcelize")  // Android
//     id("com.google.devtools.ksp") version "1.9.22-1.0.17"
// }
```

---

## 🗺️ 11. Complete Roadmap

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — FOUNDATION (Week 1-3)
├── Week 1: Syntax, null safety, types, control flow, functions
├── Week 2: Classes, data classes, sealed classes, enums, objects
└── Week 3: Collections, sequences, higher-order functions, lambdas
    └── Project: CLI contact book, number guessing game, word analyzer

PHASE 2 — KOTLIN IDIOMS (Week 4-7)
├── Week 4: Extension functions, scope functions (let/run/with/apply/also)
├── Week 5: Generics (variance, reified), inline functions, type aliases
├── Week 6: Delegated properties, operator overloading, DSL building
└── Week 7: Interfaces, abstract classes, sealed hierarchies, patterns
    └── Project: Type-safe HTML builder, calculator with operations DSL

PHASE 3 — ADVANCED KOTLIN (Week 8-12)
├── Week 8:  Coroutines — launch/async, suspend functions, structured concurrency
├── Week 9:  Flow — cold/hot flows, StateFlow, SharedFlow, operators
├── Week 10: Multiplatform basics, expect/actual, shared code
├── Week 11: Testing — JUnit 5, MockK, coroutines testing, Turbine for flows
└── Week 12: Android (ViewModel, Room, Hilt) OR Ktor (backend APIs)
    └── Project: Full MVVM Android app OR REST API with Ktor

PHASE 4 — PRODUCTION KOTLIN (Month 4-5)
├── Month 4: Arrow, functional patterns, Either/Raise, optics
├── Month 5: KSP annotation processing, compiler plugins, advanced JVM
    └── Project: Library published to Maven Central with KSP processors

PHASE 5 — EXPERT / 0.01% (Month 6+)
├── Kotlin Multiplatform with Compose Multiplatform (iOS + Android + Desktop)
├── Coroutine internals — Continuation, CPS transformation, structured concurrency impl
├── KMP with Swift interop, Objective-C interop, JS interop
├── Kotlin compiler internals — IR, plugin API, KAPT vs KSP
└── Contribute to Kotlin standard library, Arrow, Ktor, or KMP libraries
    └── Project: KMP library for iOS + Android OR contribute to kotlinx.coroutines
```

---

### 🏁 Milestone Checklist

- [ ] I understand the difference between `val` and `var` deeply — and use `val` by default
- [ ] I never use `!!` — I handle nullable types with safe calls and Elvis
- [ ] I use `data class` for value objects and understand all generated functions
- [ ] I can write and use extension functions on any type
- [ ] I understand all five scope functions and when to use each
- [ ] I can write coroutines with `launch` and `async` and understand the difference
- [ ] I understand `Flow` vs `StateFlow` vs `SharedFlow` and when to use each
- [ ] I have used `sealed class` + `when` for exhaustive state handling
- [ ] I can write a simple DSL using receiver lambdas
- [ ] I understand generics variance (`in`, `out`) and reified type parameters
- [ ] I have built an Android app or Ktor backend in Kotlin
- [ ] I have written unit tests with MockK and coroutines test utilities
- [ ] I understand KMP `expect`/`actual` and can write shared code
- [ ] I can diagnose and fix common coroutine issues (leaks, cancellation, scope)

---

## 🧩 12. Bonus Deep Insights

---

### 🔮 Mental Model: "Kotlin Is Java Done Right"

The key to understanding Kotlin is understanding what pain points it was designed to eliminate:

**Java pain point → Kotlin solution:**
- `NullPointerException` → Nullable types in the type system (`String?` vs `String`)
- Verbose getter/setter/toString → `data class` generates everything
- Null checks everywhere → Smart casts after null check
- Thread boilerplate → Coroutines with structured concurrency
- Casting unsafely → Smart casts, `as?` safe cast
- No extension methods → Extension functions on any type
- Verbose lambdas → Trailing lambda syntax, `it`, `_` for unused params
- Static utility classes → Top-level functions and extension functions
- Ternary operator → `if` as expression
- Switch statement → `when` expression with patterns

Knowing this helps you read Kotlin idiomatically — when you see a `?.` instead of a null check, when you see `apply {}` instead of verbose initialization, when you see `when {}` instead of a switch — you're seeing intentional design choices.

---

### 🤫 Deep Insight 1: `copy()` in Data Classes Is Shallow

```kotlin
data class Department(val name: String, val employees: MutableList<String> = mutableListOf())
data class Company(val name: String, val departments: List<Department>)

val eng = Department("Engineering", mutableListOf("Alice", "Bob"))
val original = Company("TechCorp", listOf(eng))

val copy = original.copy()  // Shallow copy!

// The copy shares the SAME Department objects!
copy.departments[0].employees.add("Carol")

println(original.departments[0].employees)  // [Alice, Bob, Carol] — mutated!
println(copy.departments[0].employees)       // [Alice, Bob, Carol] — same list!

// For true deep copy — use a custom method or serialization:
fun Company.deepCopy() = Company(
    name = name,
    departments = departments.map { dept ->
        Department(dept.name, dept.employees.toMutableList())
    }
)

val deepCopied = original.deepCopy()
deepCopied.departments[0].employees.add("Dave")
println(original.departments[0].employees)  // Unchanged!
```

---

### 🤫 Deep Insight 2: Coroutine Context — The Invisible Parameter

```kotlin
// Every coroutine runs in a CoroutineContext — a map of elements:
// Job — controls the lifecycle and cancellation
// CoroutineDispatcher — where the coroutine runs (thread pool)
// CoroutineName — for debugging
// CoroutineExceptionHandler — handles uncaught exceptions

val context = Dispatchers.IO +
              Job() +
              CoroutineName("MyCoroutine") +
              CoroutineExceptionHandler { _, e -> println("Error: $e") }

val scope = CoroutineScope(context)
scope.launch {
    println(coroutineContext[CoroutineName])   // CoroutineName("MyCoroutine")
    println(coroutineContext[Job])             // The Job object
    // Children inherit the parent's context but with a CHILD Job!
    // This is how structured concurrency works — parent Job tracks all children
}

// Changing context within a coroutine:
launch(Dispatchers.Main) {
    val result = withContext(Dispatchers.IO) {  // Switch to IO thread
        fetchFromDatabase()
    }
    // Back on Main thread automatically!
    updateUi(result)
}

suspend fun fetchFromDatabase() = "data"
fun updateUi(data: String) {}
```

---

### 🧠 The Big Picture — Kotlin in the Modern Ecosystem

```
Kotlin's place in 2025:

  THE language for Android development — no serious alternative
  Growing fast for server-side (Ktor, Spring Boot with Kotlin)
  Kotlin Multiplatform — the first credible "write once" solution
  Compose Multiplatform — declarative UI for all platforms

  The Kotlin ecosystem:
  Android:  Jetpack Compose, Room, Hilt, Navigation, Lifecycle
  Server:   Ktor, Spring Boot (Kotlin), Micronaut, Quarkus
  KMP:      kotlinx.serialization, Ktor client, SQLDelight
  Build:    Gradle Kotlin DSL (replacing Groovy)
  Testing:  JUnit 5 + MockK + Turbine + Kotest
  FP:       Arrow (Either, Raise, Optics, Effect)
  Tools:    IntelliJ IDEA, Android Studio, Fleet

  Kotlin vs Java in 2025:
  ✅ Kotlin: Null safety, concise syntax, coroutines, DSLs
  ✅ Java: Huge codebase, mature ecosystem, record types (Java 16+)
  Most major companies use BOTH — Kotlin for new code, Java for old

  Kotlin vs Swift (mobile):
  Both: Native performance, null safety, type inference, pattern matching
  Kotlin: JVM ecosystem, multiplatform, DSLs, coroutines
  Swift: Apple ecosystem, performance, value semantics, async/await

  Career paths with Kotlin:
  → Android Developer → Senior Android → Principal/Staff
  → Backend Kotlin (Ktor/Spring) → Architect
  → KMP Developer → Platform Engineer
  → Kotlin tools/library author → Open source career

  Companies betting on Kotlin:
  JetBrains — creator, IntelliJ, all tools
  Google — Android, Jetpack, Firebase SDKs
  Netflix — streaming backend services
  Atlassian — Jira, Confluence platform
  Uber — mobile and server
  Shopify — mobile apps and tooling
  Square/Block — mobile and backend services
```

---

## 📌 13. Summary (Quick Revision & Cheat Sheet)

---

### Core Concepts (1-line each)

| Concept              | What It Means                                                              |
|----------------------|----------------------------------------------------------------------------|
| Null safety          | `String` = never null; `String?` = can be null — enforced at compile time |
| Smart casts          | Kotlin automatically casts after null/type check — no explicit cast needed|
| Data classes         | `data class` = free `toString`, `equals`, `hashCode`, `copy`, `componentN`|
| Sealed classes       | Closed hierarchy — `when` is exhaustive with no `else` needed             |
| Extension functions  | Add methods to any type — compiles to static utility calls                |
| Scope functions      | `let`/`run`/`with`/`apply`/`also` — idiomatic null handling & config      |
| Coroutines           | Lightweight threads — `suspend` functions pause without blocking           |
| Flow                 | Cold async stream; StateFlow = observable state; SharedFlow = broadcast    |
| Inline + reified     | Inline eliminates lambda overhead; reified accesses type at runtime       |
| Value classes        | `@JvmInline value class` — zero-cost wrapper around a single property     |

---

### The 10 Things to Remember

1. ✅ **Use `val` by default** — only `var` when you need to reassign
2. ✅ **Never use `!!`** — handle nulls with `?.`, `?:`, `let`, or early return
3. ✅ **`data class` for value objects** — stops you from forgetting `equals`/`hashCode`
4. ✅ **`sealed class` + `when`** — exhaustive pattern matching at compile time
5. ✅ **`coroutineScope` for structured concurrency** — never `GlobalScope` in production
6. ✅ **`StateFlow` for observable UI state** — not `MutableLiveData` in new code
7. ✅ **`sequence {}` for lazy evaluation** — avoid intermediate collections
8. ✅ **`by lazy` for expensive initialization** — compute once, cache forever
9. ✅ **Prefer `listOf()` / `mapOf()`** — immutable by default, explicit when mutable
10. ✅ **Extension functions over inheritance** — add methods without modifying class

---

### Quick Reference Cheat Sheet

```kotlin
// ── VARIABLES ─────────────────────────────────────────────────────────────
val immutable = "cannot reassign"
var mutable = "can reassign"
val inferred = 42           // Int
val typed: Long = 42L
const val COMPILE_TIME = "constant"  // Only in object/companion

// ── NULL SAFETY ───────────────────────────────────────────────────────────
val nullable: String? = null
nullable?.length            // Safe call → Int?
nullable ?: "default"       // Elvis → non-null
nullable!!.length           // Assert non-null (use rarely!)
nullable?.let { it.length } // Execute block if non-null
val nonNull = requireNotNull(nullable) { "Must not be null" }
val smartCast: String = if (nullable != null) nullable else "x"

// ── DATA / SEALED / ENUM ──────────────────────────────────────────────────
data class User(val id: Int, val name: String, val role: Role = Role.USER)
val copy = user.copy(name = "New Name")
val (id, name) = user  // Destructuring

sealed class State {
    data object Loading : State()
    data class Success<T>(val data: T) : State()
    data class Error(val msg: String) : State()
}

enum class Role(val displayName: String) {
    ADMIN("Administrator"), USER("User"), GUEST("Guest");
    fun isPrivileged() = this == ADMIN
}

// ── FUNCTIONS ─────────────────────────────────────────────────────────────
fun simple(x: Int): Int = x * 2                  // Single expression
fun withDefault(x: Int, y: Int = 10) = x + y    // Default param
fun vararg(vararg nums: Int) = nums.sum()        // Varargs
inline fun <reified T> typeOf(): String = T::class.simpleName!!  // Reified

// Extension:
fun String.isPalindrome() = this == this.reversed()
val String.wordCount: Int get() = split(" ").size

// Higher order:
fun operate(x: Int, block: (Int) -> Int) = block(x)
operate(5) { it * 2 }  // 10

// ── CLASSES ───────────────────────────────────────────────────────────────
class Person(val name: String, var age: Int) {
    companion object { fun create(name: String) = Person(name, 0) }
    val isAdult get() = age >= 18
    override fun toString() = "Person($name, $age)"
}

object Singleton { var count = 0 }
@JvmInline value class Id(val value: Int)

// ── COLLECTIONS ───────────────────────────────────────────────────────────
val list = listOf(1, 2, 3)       // Read-only
val mList = mutableListOf(1, 2)  // Mutable
val map = mapOf("a" to 1)
val mMap = mutableMapOf("a" to 1)
val set = setOf(1, 2, 3)

list.map { it * 2 }           // Transform
list.filter { it > 1 }        // Filter
list.flatMap { listOf(it, it) } // FlatMap
list.reduce { acc, n -> acc + n } // Fold
list.groupBy { it % 2 }       // Group
list.associate { it to it*2 } // Build map
list.partition { it > 1 }     // Split two lists
list.chunked(2)               // [[1,2],[3]]
list.windowed(2)              // [[1,2],[2,3]]
list.zipWithNext()            // [(1,2),(2,3)]
list.sortedBy { it.toString() }
list.sortedDescending()
list.any { it > 2 } / all { } / none { }
list.first { it > 1 } / firstOrNull { }
list.count { it > 1 }
list.sumOf { it.toLong() }
list.minByOrNull { } / maxByOrNull { }
(1..1_000_000).asSequence().map{}.filter{}.take(5).toList()  // Lazy!

// ── SCOPE FUNCTIONS ────────────────────────────────────────────────────────
obj.let { it.doSomething(); result }   // Transform, return result
obj.run { doSomething(); result }      // Transform (this), return result
with(obj) { doSomething(); result }   // Transform (not extension), return result
obj.apply { configure() }             // Configure, return obj
obj.also { log(it) }                 // Side effect, return obj
value.takeIf { it > 0 }             // Return value or null
value.takeUnless { it.isEmpty() }    // Return value or null

// ── COROUTINES ────────────────────────────────────────────────────────────
// Dependencies: kotlinx-coroutines-core, kotlinx-coroutines-android
runBlocking { }                // Create event loop (tests/main)
viewModelScope.launch { }     // Fire and forget
viewModelScope.async { result }.await() // Return value
withContext(Dispatchers.IO) { } // Switch thread
coroutineScope { launch{} launch{} } // Structured concurrency
delay(1000)                   // Non-blocking sleep
withTimeout(5000) { }         // Timeout
withTimeoutOrNull(5000) { }   // Timeout returning null

// Flow:
flow { emit(1); emit(2) }           // Create cold flow
flowOf(1, 2, 3)                     // From values
listOf(1,2,3).asFlow()              // From collection
MutableStateFlow(initialValue)      // Hot - state
MutableSharedFlow<T>()              // Hot - events
flow.map{}.filter{}.take(3).collect{}  // Pipeline
flow.catch { e -> emit(default) }   // Handle errors
flow.onEach { }.launchIn(scope)     // Side effects

// ── USEFUL STANDARD LIBRARY ────────────────────────────────────────────────
"hello".uppercase() / lowercase() / trim() / reversed()
"1,2,3".split(",")                  // [1, 2, 3]
listOf(1,2,3).joinToString(", ")    // "1, 2, 3"
buildString { append("a"); appendLine("b") }
repeat(3) { println(it) }          // 0, 1, 2
generateSequence(1) { it + 1 }    // Infinite sequence
measureTimeMillis { doWork() }     // Measure time
check(condition) { "Message" }     // Throw IllegalStateException
require(condition) { "Message" }   // Throw IllegalArgumentException
error("Message")                   // Throw IllegalStateException always
TODO("Not implemented")            // Throw NotImplementedError

// ── COMMON PATTERNS ────────────────────────────────────────────────────────
// Repository pattern return type:
sealed class Result<out T> {
    data class Success<T>(val data: T) : Result<T>()
    data class Error(val msg: String) : Result<Nothing>()
}

// Lazy property:
val expensiveValue by lazy { computeExpensiveValue() }

// Delegated property with validation:
var age by Delegates.vetoable(0) { _, _, new -> new in 0..150 }

// Observable property:
var name by Delegates.observable("") { _, old, new -> onNameChanged(old, new) }

// Singleton:
object AppConfig {
    const val API_URL = "https://api.example.com"
    val httpClient by lazy { createHttpClient() }
}

// Builder DSL:
fun html(block: HtmlBuilder.() -> Unit) = HtmlBuilder().apply(block).build()
```

---

### What's Next?

After mastering Kotlin deeply, your natural paths:

- 📘 **Jetpack Compose** — Declarative Android UI — the present and future of Android development
- 📘 **Ktor** — Kotlin-native async web framework — lightweight, coroutine-based backend
- 📘 **Kotlin Multiplatform + Compose Multiplatform** — Single codebase for Android, iOS, Desktop
- 📘 **Arrow** — Functional programming for Kotlin — Either, Raise, Optics, Effect
- 📘 **Spring Boot with Kotlin** — Enterprise-grade backend with the most popular Java framework
- 📘 **Android Architecture** — Clean Architecture, MVVM, MVI — patterns for scalable Android

---

> 💬 *"Kotlin makes me a better programmer. Not because it forces you to do the right thing, but because it makes doing the right thing the easy thing."*
> — Every Java developer who switched to Kotlin

> 💬 *"We built Kotlin because we needed it for our own productivity. And then everyone else needed it too."*
> — JetBrains, on Kotlin's creation

> 💬 *"Coroutines are the best abstraction for asynchronous programming I have ever seen in any language. Fight me."*
> — Roman Elizarov, Kotlin Coroutines lead

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: Kotlin — Complete Language Mastery | Version: 1.0*
*Sections: 13 | Level: Beginner → 0.01% Elite*
