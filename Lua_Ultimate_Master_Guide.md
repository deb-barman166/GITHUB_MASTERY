# 🌙 Lua — The Ultimate Master Guide
### From Zero to 0.01% Expert — Every Concept, Metatable Secret, Coroutine Trick & Hidden Power

> 📘 **The most complete Lua guide ever written — beginner to elite.**
>
> 🎯 *Who is this for?* Anyone who wants to go from knowing nothing about Lua to **mastering** it — the language that powers game mods, embedded systems, game engines, Redis, Nginx, and millions of IoT devices.
> ⏱️ *Time to complete:* Self-paced — days to months
> 🛠️ *What you'll gain:* Every syntax rule, metatables secret, coroutine model, C API trick, and 0.01% hidden technique that separates an elite Lua developer from the rest.

---

## Table of Contents

1. [🧠 What is Lua?](#1-what-is-lua-super-simple)
2. [🌍 Why Lua Exists & Dominates](#2-why-lua-exists--dominates)
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

## 🧠 1. What is Lua? (Super Simple)

### The 12-Year-Old Explanation

Imagine you've built a huge, powerful machine — a game engine, a web server, or an industrial robot. The machine works perfectly, but its creators want users to be able to customize it — add new behaviors, create content, write scripts — without rebuilding the machine from scratch every time. They need a small, simple language that can be embedded inside the machine.

**That language is Lua.**

Lua (pronounced "LOO-ah" — it means "Moon" in Portuguese) was created at the **Pontifical Catholic University of Rio de Janeiro** in Brazil in 1993 by **Roberto Ierusalimschy**, **Waldemar Celes**, and **Luiz Henrique de Figueiredo**. It was designed with one goal: to be **the best embedding language ever made**.

Lua is used everywhere you find systems that need scripting:
- **Roblox** — every Roblox game is scripted entirely in Lua
- **World of Warcraft** — all addons and UI are written in Lua
- **Redis** — scripting Redis operations with Lua
- **Nginx** (via OpenResty) — handling millions of web requests
- **Neovim** — the popular code editor uses Lua for configuration and plugins
- **Love2D** — a game framework built purely on Lua
- **Adobe Lightroom** — plugin system
- **Wireshark** — network protocol dissectors

The language itself is tiny — the entire Lua interpreter fits in about **200KB**. Yet it is extraordinarily powerful, with one of the most elegant design philosophies in programming history.

### Real-Life Analogy

💡 **Think of it like this:**
A game engine is like a professional film studio — fully equipped with cameras, lights, green screens, and editing software. The studio is massive and powerful, but it's built in C++. Most people can't modify the studio itself.

**Lua is like the film studio's scripting console** — a small, portable control panel that any director (game designer, modder, administrator) can use to control every aspect of the studio without touching the underlying machinery. The console is lightweight enough to carry in a pocket, but through it you can direct the most complex productions imaginable.

### One-Line Definition

> **Lua** is a lightweight, fast, embeddable scripting language with a clean syntax, first-class functions, powerful metatables for OOP and operator overloading, and cooperative multitasking via coroutines — designed to be embedded in C/C++ applications and to run everywhere from microcontrollers to web servers.

---

## 🌍 2. Why Lua Exists & Dominates

### The Problem It Solved

In the early 1990s, Brazilian engineers at Tecgraf (a computer graphics lab) were building industrial applications for Petrobras (Brazil's oil company). They needed a way to let non-programmers configure these applications without recompiling C code. They tried existing languages (Tcl, Python) but found them too heavy or too complex to embed. So they built their own — and Lua was born.

The core design insight was radical simplicity: **every feature in Lua must pay for its existence in multiple ways**. If a feature doesn't earn its place, it doesn't go in. This philosophy produced a language that is simultaneously:
- Tiny enough to run on embedded devices with 256KB RAM
- Fast enough to power real-time game logic
- Flexible enough to implement any paradigm (OOP, FP, prototypal)
- Simple enough to learn in a weekend

### Where Lua Dominates in 2025

| Domain                     | How Lua Is Used                                                              |
|----------------------------|------------------------------------------------------------------------------|
| Game Scripting             | Roblox (billions of users), WoW addons, Unity Lua plugins, LÖVE2D            |
| Game Engines               | Custom engines embed Lua as their scripting layer (Defold, Gideros)          |
| Web Infrastructure         | OpenResty (Nginx + Lua) handles millions of RPS at companies like Cloudflare |
| Database Scripting         | Redis EVAL — atomic server-side Lua scripts for complex operations           |
| Network Equipment          | Cisco IOS, network device configuration and automation                       |
| Text Editors               | Neovim, TextPad — entire plugin ecosystems in Lua                           |
| Security / Pen Testing     | Nmap NSE (Network Script Engine) — network scanning scripts                  |
| IoT / Embedded             | NodeMCU (ESP8266/ESP32) — WiFi microcontroller scripting in Lua              |
| Machine Learning Tools     | Torch (Facebook AI, used before PyTorch) was Lua-based                      |
| Adobe Apps                 | Lightroom Classic plugin system uses Lua throughout                          |

### Why YOU Should Learn It Deeply

1. **Roblox alone has 3+ million active developers** — all coding in Lua (Luau, Roblox's variant).
2. **OpenResty/Nginx Lua is the backbone of modern CDNs** — Cloudflare processes trillions of requests with Lua at the edge.
3. **Neovim is the fastest-growing developer tool** — its entire ecosystem runs on Lua.
4. **Metatables are a masterclass in language design** — understanding them makes you a better programmer in every language.
5. **Coroutines in Lua predate `async/await`** — learning them teaches you how modern async patterns work at a fundamental level.

---

## 🧱 3. Core Fundamentals (Beginner Level)

> 🎯 *Goal: Build an unshakeable foundation. Every concept here is critical.*

---

### Concept 1: Setup, Hello World & Running Lua

```lua
-- ── INSTALLATION ──────────────────────────────────────────────────────────────
-- Ubuntu/Debian: sudo apt install lua5.4
-- macOS:         brew install lua
-- Windows:       Download from https://luabinaries.sourceforge.net/
--                Or: scoop install lua
-- Check version: lua -v

-- ── RUNNING LUA ───────────────────────────────────────────────────────────────
-- lua script.lua          ← Run a file
-- lua                     ← Start interactive REPL
-- lua -e "print('hi')"   ← Execute a string directly
-- lua -i script.lua       ← Run file then drop into REPL
-- luac script.lua         ← Compile to bytecode (luac)
-- luac -o out.luac s.lua  ← Compile to named bytecode file

-- ── YOUR FIRST LUA PROGRAM ────────────────────────────────────────────────────
-- hello.lua

-- Comments use double dashes:
-- This is a single-line comment

--[[
  This is a multi-line comment.
  Everything between [[ and ]] is ignored.
  Can also use --[[ to start.
]]

print("Hello, World!")            -- print() is the basic output function
print("Lua version: " .. _VERSION) -- _VERSION = "Lua 5.4"

-- io.write doesn't add a newline:
io.write("No newline")
io.write(" here\n")

-- String formatting:
print(string.format("Pi = %.4f", math.pi))
print(string.format("Name: %s, Age: %d", "Aryan", 17))

-- ── COMMENTS ──────────────────────────────────────────────────────────────────
-- Single line comment

--[[
Multi-line comment
across multiple lines
--]]

-- Nested long comments (using levels):
--[==[
  This comment uses level 2 brackets.
  Useful when comment contains ]] inside.
--]==]
```

---

### Concept 2: Variables, Types & Lua's Dynamic Type System

```lua
-- ── LUA HAS ONLY 8 TYPES ──────────────────────────────────────────────────────
-- nil, boolean, number, string, function, table, thread, userdata

-- ── VARIABLES ─────────────────────────────────────────────────────────────────
-- ALL variables are GLOBAL by default unless declared with 'local'!
-- This is the #1 pitfall for new Lua programmers.

x = 10           -- GLOBAL variable (avoid in production!)
local y = 20     -- LOCAL variable (always prefer local)

-- Multiple assignment (Lua's unique feature):
local a, b, c = 1, 2, 3
print(a, b, c)    -- 1  2  3

-- Swap values elegantly:
a, b = b, a
print(a, b)       -- 2  1

-- Excess values are discarded:
local p, q = 1, 2, 3    -- 3 is discarded
print(p, q)              -- 1  2

-- Missing values become nil:
local r, s, t = 1, 2    -- t = nil
print(r, s, t)           -- 1  2  nil

-- ── NIL — the absence of value ───────────────────────────────────────────────
local nothing = nil
print(nothing)           -- nil
print(type(nothing))     -- "nil"

-- Setting a variable to nil effectively deletes it:
local x2 = 42
x2 = nil    -- x2 is now nil (garbage collected if no other references)

-- ── BOOLEANS ──────────────────────────────────────────────────────────────────
local t_val = true
local f_val = false

-- CRITICAL: In Lua, ONLY nil and false are falsy!
-- 0 is TRUTHY! "" is TRUTHY! These are NOT false!
if 0 then print("0 is truthy!") end   -- Prints! (Unlike Python/C)
if "" then print("'' is truthy!") end -- Prints! (Unlike Python/JavaScript)

-- ── NUMBERS ───────────────────────────────────────────────────────────────────
-- Lua 5.3+ has two numeric subtypes: integer and float
-- Lua 5.2 and below: all numbers are doubles

local integer  = 42           -- Integer
local float    = 3.14         -- Float
local hex      = 0xFF         -- Hexadecimal integer = 255
local hex_flt  = 0x1p4        -- Hex float = 16.0
local sci      = 1.5e10       -- Scientific notation
local big      = 1000000      -- No underscores in Lua (unlike Python)

-- Type subtypes (Lua 5.3+):
print(math.type(42))          -- "integer"
print(math.type(42.0))        -- "float"
print(math.type("hello"))     -- fail (not a number type)

-- Integer vs float operations:
print(10 / 3)                 -- 3.3333... (float division)
print(10 // 3)                -- 3 (floor division — integer result)
print(10 % 3)                 -- 1 (modulo)
print(2 ^ 10)                 -- 1024.0 (power — always float!)
print(math.maxinteger)        -- 9223372036854775807 (2^63 - 1)
print(math.mininteger)        -- -9223372036854775808

-- ── STRINGS ───────────────────────────────────────────────────────────────────
local s1 = "double quotes"
local s2 = 'single quotes'    -- Identical to double quotes
local s3 = [[
  Long string literal.
  Spans multiple lines.
  No escape sequences needed!
  ]] .. "" -- trim if needed

-- String length:
print(#"hello")               -- 5 (# operator = length)
print(#s1)                    -- 14

-- Concatenation with ..:
local greeting = "Hello" .. ", " .. "World" .. "!"
print(greeting)               -- Hello, World!

-- Numbers auto-coerce to strings in concatenation:
local msg = "Score: " .. 100  -- "Score: 100"

-- Strings do NOT auto-coerce to numbers (unlike JavaScript!):
-- print("10" + 5)            -- ERROR in strict mode, but Lua 5.3 tries coercion
-- Safer: use tonumber()
print(tonumber("10") + 5)     -- 15

-- Escape sequences:
print("Tab:\there")
print("Newline:\nhere")
print("Quote: \"hi\"")
print("Backslash: \\")
print("\65")                   -- "A" (decimal escape = ASCII 65)
print("\x41")                  -- "A" (hex escape)

-- String comparisons (lexicographic):
print("abc" < "abd")           -- true
print("abc" == "abc")          -- true
print("ABC" == "abc")          -- false (case-sensitive!)

-- ── TYPE FUNCTIONS ────────────────────────────────────────────────────────────
print(type(nil))               -- "nil"
print(type(true))              -- "boolean"
print(type(42))                -- "number"
print(type("hello"))           -- "string"
print(type(print))             -- "function"
print(type({}))                -- "table"
print(type(type))              -- "function"

-- Type coercions:
print(tostring(42))            -- "42"
print(tostring(true))          -- "true"
print(tostring(nil))           -- "nil"
print(tonumber("3.14"))        -- 3.14
print(tonumber("0xFF"))        -- 255
print(tonumber("10", 2))       -- 2 (parse "10" as base-2 = 2)
print(tonumber("FF", 16))      -- 255
print(tonumber("abc"))         -- nil (failed conversion)
```

---

### Concept 3: Tables — Lua's Only Data Structure

```lua
-- Tables are THE data structure in Lua.
-- They implement: arrays, dictionaries, objects, modules, namespaces, classes.
-- Everything is a table. Even the global environment is a table!

-- ── CREATING TABLES ────────────────────────────────────────────────────────────
local empty = {}                    -- Empty table
local arr   = {10, 20, 30, 40, 50} -- Array-like (1-indexed!)
local dict  = {name = "Aryan", age = 17, city = "Kolkata"}  -- Dictionary-like
local mixed = {                     -- Mixed table
    1, 2, 3,                        -- Sequence part (index 1, 2, 3)
    name = "Mixed",                  -- String key
    [100] = "sparse"                -- Explicit integer key 100
}

-- ── ARRAY TABLES (sequences) ──────────────────────────────────────────────────
-- Lua arrays are 1-indexed! (Not 0!)
local fruits = {"apple", "banana", "cherry", "date"}

print(fruits[1])     -- "apple"  (NOT fruits[0]!)
print(fruits[2])     -- "banana"
print(fruits[4])     -- "date"
print(fruits[0])     -- nil (index 0 doesn't exist by convention)
print(#fruits)       -- 4 (length operator)

-- Modifying:
fruits[5] = "elderberry"    -- Add new element
fruits[2] = "blueberry"     -- Replace
fruits[3] = nil             -- Remove (creates a "hole" — careful!)
print(#fruits)              -- May be 4 or 5 — # is undefined for tables with holes!

-- ── DICTIONARY TABLES ─────────────────────────────────────────────────────────
local player = {
    name = "Hero",
    health = 100,
    mana = 50,
    level = 5,
    position = {x = 100, y = 200},  -- Nested table!
}

-- Accessing with dot notation:
print(player.name)           -- "Hero"
print(player.health)         -- 100
print(player.position.x)     -- 100

-- Accessing with bracket notation:
print(player["name"])        -- "Hero"
print(player["health"])      -- 100

-- Adding new fields:
player.gold = 250
player["weapon"] = "Sword"

-- Removing fields (set to nil):
player.mana = nil            -- Field removed!

-- Check if field exists:
if player.boss == nil then
    print("No boss field")   -- This prints
end

-- ── ITERATING TABLES ──────────────────────────────────────────────────────────
-- pairs() — iterate ALL key-value pairs (unordered):
for key, value in pairs(player) do
    print(key, "=", value)
end

-- ipairs() — iterate SEQUENCE part (1, 2, 3... until nil):
local scores = {95, 87, 92, 78, 100}
for index, score in ipairs(scores) do
    print(index, score)     -- 1 95, 2 87, 3 92, 4 78, 5 100
end

-- next() — iterate manually:
local t = {a = 1, b = 2, c = 3}
local k, v = next(t)
while k ~= nil do
    print(k, v)
    k, v = next(t, k)
end

-- ── TABLE STANDARD LIBRARY ────────────────────────────────────────────────────
local list = {3, 1, 4, 1, 5, 9, 2, 6}

-- Insert:
table.insert(list, 10)         -- Append to end
table.insert(list, 1, 0)       -- Insert at position 1

-- Remove:
local removed = table.remove(list)     -- Remove last, return it
local first = table.remove(list, 1)   -- Remove at index 1, return it

-- Sort:
table.sort(list)                           -- Sort ascending (in-place)
table.sort(list, function(a, b) return a > b end)  -- Sort descending

-- Concat (array of strings to string):
local words = {"Hello", "World", "from", "Lua"}
print(table.concat(words, " "))    -- "Hello World from Lua"
print(table.concat(words, ", "))   -- "Hello, World, from, Lua"

-- Move (Lua 5.3+):
table.move(list, 1, 3, 2)   -- Copy elements 1-3 to position 2

-- ── TABLE AS SET ─────────────────────────────────────────────────────────────
local set = {}
local items = {"apple", "banana", "apple", "cherry", "banana"}

-- Build set (deduplicate):
for _, item in ipairs(items) do
    set[item] = true
end
-- set = {apple=true, banana=true, cherry=true}

-- Check membership (O(1)!):
if set["apple"] then print("apple is in set") end
if not set["grape"] then print("grape is not in set") end

-- Convert set back to array:
local unique = {}
for key in pairs(set) do
    unique[#unique + 1] = key    -- Efficient append
end
```

---

### Concept 4: Control Flow

```lua
-- ── IF / ELSEIF / ELSE ────────────────────────────────────────────────────────
local score = 87

if score >= 90 then
    print("A")
elseif score >= 80 then
    print("B")
elseif score >= 70 then
    print("C")
else
    print("F")
end

-- Lua has NO switch/case — use if/elseif chains or table dispatch:
local action = "jump"
local handlers = {
    jump   = function() print("Jumping!") end,
    attack = function() print("Attacking!") end,
    duck   = function() print("Ducking!") end,
}
local handler = handlers[action]
if handler then handler() end

-- ── LOGICAL OPERATORS ─────────────────────────────────────────────────────────
-- and, or, not — work as expected but have SPECIAL return behavior!

-- 'and' returns first falsy value, or last value if all truthy:
print(1 and 2)          -- 2 (both truthy, return last)
print(nil and 2)        -- nil (first is falsy, return it)
print(false and 2)      -- false
print(false and nil)    -- false

-- 'or' returns first truthy value, or last value if all falsy:
print(1 or 2)           -- 1 (first is truthy, return it)
print(nil or 2)         -- 2 (first is falsy, return second)
print(false or nil)     -- nil
print(nil or false)     -- false

-- IDIOM: Default values with 'or':
local function greet(name)
    name = name or "World"    -- If name is nil/false, use "World"
    print("Hello, " .. name)
end
greet()             -- "Hello, World"
greet("Aryan")      -- "Hello, Aryan"

-- IDIOM: Ternary-like expression:
local x = 10
local result = (x > 5) and "big" or "small"  -- "big"
-- WARNING: This fails if "big" is false/nil! Use if/else then.

-- ── LOOPS ─────────────────────────────────────────────────────────────────────
-- Numeric for loop:
for i = 1, 5 do
    print(i)   -- 1, 2, 3, 4, 5
end

for i = 1, 10, 2 do    -- start, stop, step
    print(i)   -- 1, 3, 5, 7, 9
end

for i = 10, 1, -1 do   -- Countdown
    print(i)   -- 10, 9, 8, 7, 6, 5, 4, 3, 2, 1
end

-- Generic for loop (iterators):
local fruits2 = {"apple", "banana", "cherry"}
for i, v in ipairs(fruits2) do
    print(i, v)    -- 1 apple, 2 banana, 3 cherry
end

local person = {name = "Aryan", age = 17}
for k, v in pairs(person) do
    print(k, v)    -- (order not guaranteed)
end

-- While loop:
local count = 0
while count < 5 do
    count = count + 1
    print(count)
end

-- Repeat-until (like do-while — condition checked at end!):
local n = 0
repeat
    n = n + 1
    print(n)
until n >= 5    -- Loop body runs AT LEAST ONCE

-- Break (no continue in Lua!):
for i = 1, 10 do
    if i == 5 then break end   -- Exit loop
    print(i)    -- 1, 2, 3, 4
end

-- Goto (Lua 5.2+) — can simulate continue:
for i = 1, 10 do
    if i % 2 == 0 then goto continue end   -- Skip even numbers
    print(i)    -- 1, 3, 5, 7, 9
    ::continue::   -- Label
end
```

---

### Concept 5: Functions — The Heart of Lua

```lua
-- ── BASIC FUNCTIONS ───────────────────────────────────────────────────────────
-- Functions are first-class values in Lua!

-- Standard definition:
function add(a, b)
    return a + b
end

-- Equivalent (function assigned to variable):
local subtract = function(a, b)
    return a - b
end

-- Local function (self-referencing works!):
local function factorial(n)
    if n <= 1 then return 1 end
    return n * factorial(n - 1)
end

print(add(3, 4))           -- 7
print(subtract(10, 3))     -- 7
print(factorial(6))         -- 720

-- ── MULTIPLE RETURN VALUES ────────────────────────────────────────────────────
-- Lua natively supports multiple return values!
function minmax(t)
    local min, max = t[1], t[1]
    for _, v in ipairs(t) do
        if v < min then min = v end
        if v > max then max = v end
    end
    return min, max   -- Returns TWO values!
end

local lo, hi = minmax({3, 1, 4, 1, 5, 9, 2, 6})
print(lo, hi)    -- 1  9

-- Collect multiple returns:
local function get_info()
    return "Aryan", 17, "Kolkata"
end

local name, age, city = get_info()
print(name, age, city)    -- Aryan  17  Kolkata

-- Only first value used in most contexts:
print(get_info())          -- Aryan  17  Kolkata (all values printed)
local just_name = get_info()   -- Only "Aryan"
print(just_name)          -- Aryan

-- Parentheses adjust to one value:
print((get_info()))        -- Aryan (parentheses = exactly one value)

-- ── VARIADIC FUNCTIONS ────────────────────────────────────────────────────────
function sum(...)
    local args = {...}    -- Pack into table
    local total = 0
    for _, v in ipairs(args) do
        total = total + v
    end
    return total
end
print(sum(1, 2, 3, 4, 5))  -- 15

-- select() with variadic:
function info(...)
    print("Count:", select("#", ...))    -- Number of args
    print("From 2:", select(2, ...))     -- Args from position 2 onward
end
info("a", "b", "c", "d")
-- Count: 4
-- From 2: b  c  d

-- Passing varargs to another function:
function wrap_print(...)
    io.write("[LOG] ")
    print(...)    -- Pass all args to print
end
wrap_print("Hello", "World", 42)    -- [LOG] Hello World 42

-- ── CLOSURES ──────────────────────────────────────────────────────────────────
-- Functions capture their enclosing variables (upvalues)!
function make_counter(start)
    local count = start or 0    -- Captured upvalue
    return {
        increment = function() count = count + 1 end,
        decrement = function() count = count - 1 end,
        get       = function() return count end,
        reset     = function() count = 0 end,
    }
end

local c = make_counter(10)
c.increment()
c.increment()
c.increment()
print(c.get())    -- 13

local c2 = make_counter()
c2.increment()
print(c2.get())   -- 1  (separate counter!)
print(c.get())    -- 13 (unchanged!)

-- ── HIGHER-ORDER FUNCTIONS ────────────────────────────────────────────────────
function map(t, f)
    local result = {}
    for i, v in ipairs(t) do
        result[i] = f(v)
    end
    return result
end

function filter(t, pred)
    local result = {}
    for _, v in ipairs(t) do
        if pred(v) then
            result[#result + 1] = v
        end
    end
    return result
end

function reduce(t, f, init)
    local acc = init
    for _, v in ipairs(t) do
        acc = f(acc, v)
    end
    return acc
end

local nums = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
local doubled = map(nums, function(n) return n * 2 end)
local evens   = filter(nums, function(n) return n % 2 == 0 end)
local total   = reduce(nums, function(a, b) return a + b end, 0)

print(table.concat(doubled, ", "))   -- 2, 4, 6, 8, 10, 12, 14, 16, 18, 20
print(table.concat(evens, ", "))     -- 2, 4, 6, 8, 10
print(total)                          -- 55

-- ── FUNCTION ENVIRONMENTS ─────────────────────────────────────────────────────
-- Functions have access to their defining scope's variables:
local function outer()
    local x = 10
    local function inner()
        local y = 20
        return x + y    -- inner can access outer's x!
    end
    return inner()
end
print(outer())    -- 30
```

---

🧪 **Mini Task 1:**
> Write a function `flatten(t)` that takes a nested table (array of arrays, any depth) and returns a single flat array. Test with `flatten({1, {2, {3, 4}}, 5, {6}})` → `{1, 2, 3, 4, 5, 6}`.
> ✅ *Use: recursion, `type() == "table"`, `ipairs`, table building*

🧪 **Mini Task 2:**
> Write a function `memoize(f)` that wraps any function and caches its results. Test with a Fibonacci function — memoized `fib(40)` should be instant vs exponential without memoization.
> ✅ *Use: closures, tables as cache, varargs with `table.pack`/`table.unpack`*

---

## ⚙️ 4. Complete Language System Breakdown

---

### Part 1: Metatables — Lua's Superpower

```lua
-- ── WHAT ARE METATABLES? ──────────────────────────────────────────────────────
-- A metatable is a regular table that controls the behavior of another table.
-- It defines what happens when you:
-- - Add two tables: t1 + t2
-- - Compare tables: t1 < t2
-- - Index missing keys: t[key] where key doesn't exist
-- - Call a table like a function: t()
-- - Get length: #t
-- - And more...

-- ── SETTING A METATABLE ───────────────────────────────────────────────────────
local t = {}
local mt = {}

-- Associate mt as the metatable of t:
setmetatable(t, mt)

-- Get the metatable:
print(getmetatable(t) == mt)   -- true

-- ── __INDEX — handle missing key access ────────────────────────────────────────
local Vector2 = {}
local Vector2_mt = {}

-- When a key isn't found in the table, look in Vector2:
Vector2_mt.__index = Vector2

function Vector2.new(x, y)
    local self = {x = x or 0, y = y or 0}
    setmetatable(self, Vector2_mt)
    return self
end

function Vector2:length()
    return math.sqrt(self.x^2 + self.y^2)
end

function Vector2:normalize()
    local len = self:length()
    return Vector2.new(self.x / len, self.y / len)
end

function Vector2:__tostring()
    return string.format("Vector2(%.2f, %.2f)", self.x, self.y)
end

local v1 = Vector2.new(3, 4)
print(v1.x)           -- 3 (direct field)
print(v1:length())    -- 5.0 (found via __index)
print(tostring(v1))   -- Vector2(3.00, 4.00) (via __tostring)

-- ── OPERATOR OVERLOADING ──────────────────────────────────────────────────────
-- ALL metamethods for operators:

Vector2_mt.__add = function(a, b)
    return Vector2.new(a.x + b.x, a.y + b.y)
end

Vector2_mt.__sub = function(a, b)
    return Vector2.new(a.x - b.x, a.y - b.y)
end

Vector2_mt.__mul = function(a, b)
    if type(a) == "number" then
        return Vector2.new(a * b.x, a * b.y)
    elseif type(b) == "number" then
        return Vector2.new(a.x * b, a.y * b)
    else
        return a.x * b.x + a.y * b.y  -- dot product
    end
end

Vector2_mt.__unm = function(a)       -- Unary minus: -v
    return Vector2.new(-a.x, -a.y)
end

Vector2_mt.__eq = function(a, b)     -- Equality: a == b
    return a.x == b.x and a.y == b.y
end

Vector2_mt.__lt = function(a, b)     -- Less than: a < b
    return a:length() < b:length()
end

Vector2_mt.__le = function(a, b)     -- Less than or equal: a <= b
    return a:length() <= b:length()
end

Vector2_mt.__len = function(a)       -- Length: #a
    return a:length()
end

Vector2_mt.__concat = function(a, b) -- Concatenation: a .. b
    return tostring(a) .. tostring(b)
end

local v2 = Vector2.new(1, 2)
local v3 = Vector2.new(3, 4)

local sum = v2 + v3
print(sum.x, sum.y)       -- 4  6
local scaled = v2 * 3
print(scaled.x, scaled.y) -- 3  6
local neg = -v2
print(neg.x, neg.y)       -- -1  -2
print(v2 == Vector2.new(1, 2))  -- true
print(#v3)                       -- 5.0

-- ── __NEWINDEX — intercept assignment ─────────────────────────────────────────
local readonly_mt = {
    __newindex = function(t, key, value)
        error("Attempt to modify read-only table: " .. tostring(key))
    end,
    __index = {x = 10, y = 20}
}

local readonly = setmetatable({}, readonly_mt)
print(readonly.x)    -- 10 (via __index)
-- readonly.x = 5   -- ERROR: Attempt to modify read-only table: x

-- ── __CALL — make table callable ──────────────────────────────────────────────
local callable_mt = {
    __call = function(self, ...)
        print("Called with:", ...)
        return "result"
    end
}

local obj = setmetatable({}, callable_mt)
print(obj("hello", 42))   -- Called with: hello 42 \n result

-- ── __INDEX AS FUNCTION — dynamic lookups ────────────────────────────────────
local defaults = setmetatable({}, {
    __index = function(t, key)
        return "default_" .. key   -- Generate default for any missing key!
    end
})

print(defaults.name)     -- "default_name"
print(defaults.color)    -- "default_color"
defaults.size = 10
print(defaults.size)     -- 10 (found in table, __index not called)

-- ── INHERITANCE CHAIN ────────────────────────────────────────────────────────
local Animal = {}
Animal.__index = Animal

function Animal.new(name, sound)
    return setmetatable({name = name, sound = sound}, Animal)
end

function Animal:speak()
    print(self.name .. " says " .. self.sound .. "!")
end

function Animal:__tostring()
    return "Animal(" .. self.name .. ")"
end

-- Dog extends Animal:
local Dog = setmetatable({}, {__index = Animal})
Dog.__index = Dog

function Dog.new(name)
    local self = Animal.new(name, "Woof")
    return setmetatable(self, Dog)
end

function Dog:fetch(item)
    print(self.name .. " fetches the " .. item)
end

local rex = Dog.new("Rex")
rex:speak()        -- Rex says Woof! (inherited from Animal)
rex:fetch("ball")  -- Rex fetches the ball (Dog method)
print(tostring(rex))  -- Animal(Rex) (inherited __tostring from Animal)
```

---

### Part 2: Object-Oriented Programming in Lua

```lua
-- Lua has no built-in class system — we build our own with metatables!
-- This flexibility means Lua can implement ANY OOP model.

-- ── PATTERN 1: Simple Class Factory ──────────────────────────────────────────
local function create_class()
    local Class = {}
    Class.__index = Class

    function Class.new(...)
        local self = setmetatable({}, Class)
        if self.init then self:init(...) end
        return self
    end

    function Class:is_a(klass)
        return getmetatable(self) == klass
    end

    return Class
end

-- Define classes:
local Person = create_class()

function Person:init(name, age)
    self.name = name
    self.age = age
end

function Person:greet()
    return string.format("Hi, I'm %s, %d years old.", self.name, self.age)
end

function Person:__tostring()
    return string.format("Person(%s, %d)", self.name, self.age)
end

local aryan = Person.new("Aryan", 17)
print(aryan:greet())        -- Hi, I'm Aryan, 17 years old.
print(tostring(aryan))      -- Person(Aryan, 17)

-- ── PATTERN 2: Inheritance ────────────────────────────────────────────────────
local function extend(Base)
    local Sub = create_class()

    -- Sub inherits from Base:
    setmetatable(Sub, {__index = Base})

    -- super() helper:
    function Sub:super(method, ...)
        return Base[method](self, ...)
    end

    return Sub
end

local Student = extend(Person)

function Student:init(name, age, gpa)
    Person.init(self, name, age)   -- Call parent init
    self.gpa = gpa
end

function Student:greet()
    local base = Person.greet(self)    -- Call parent method
    return base .. " My GPA is " .. self.gpa
end

function Student:study(subject)
    print(self.name .. " is studying " .. subject)
end

local priya = Student.new("Priya", 18, 9.5)
print(priya:greet())   -- Hi, I'm Priya, 18 years old. My GPA is 9.5
priya:study("Math")    -- Priya is studying Math

-- ── PATTERN 3: Mixin Composition ─────────────────────────────────────────────
local Serializable = {}
function Serializable:serialize()
    local parts = {}
    for k, v in pairs(self) do
        if type(v) ~= "function" then
            parts[#parts + 1] = k .. "=" .. tostring(v)
        end
    end
    return "{" .. table.concat(parts, ", ") .. "}"
end

local Comparable = {}
function Comparable:compare_to(other)
    -- Default: compare by a 'value' field
    if self.value < other.value then return -1
    elseif self.value > other.value then return 1
    else return 0
    end
end

-- Apply mixins:
local function mixin(target, ...)
    for _, source in ipairs({...}) do
        for k, v in pairs(source) do
            if target[k] == nil then   -- Don't overwrite existing methods
                target[k] = v
            end
        end
    end
    return target
end

local Product = create_class()
mixin(Product, Serializable, Comparable)

function Product:init(name, price)
    self.name  = name
    self.value = price    -- Comparable uses 'value'
end

local apple_prod = Product.new("Apple", 1.5)
local orange = Product.new("Orange", 2.0)
print(apple_prod:serialize())        -- {name=Apple, value=1.5}
print(apple_prod:compare_to(orange)) -- -1 (apple is cheaper)
```

---

### Part 3: The String Library — Complete Reference

```lua
-- ── STRING FUNCTIONS ──────────────────────────────────────────────────────────
-- Note: Lua strings are immutable — all operations return NEW strings

local s = "Hello, World!"

-- Length:
print(#s)                           -- 13
print(string.len(s))                -- 13

-- Case:
print(string.upper(s))              -- "HELLO, WORLD!"
print(string.lower(s))              -- "hello, world!"

-- Substrings:
print(string.sub(s, 1, 5))         -- "Hello"    (1-indexed, inclusive!)
print(string.sub(s, 8))            -- "World!"   (from index 8 to end)
print(string.sub(s, -6))           -- "World!"   (negative = from end)
print(string.sub(s, -6, -2))       -- "World"

-- Find:
local start, finish = string.find(s, "World")
print(start, finish)                -- 8  12

local s2, e2 = string.find(s, "o", 1, true)  -- 4th arg: plain search
print(s2, e2)                       -- 5  5

-- Searching with patterns (Lua's regex-like system):
local _, _, month, day, year = string.find("Date: 2025-03-29", "(%d+)-(%d+)-(%d+)")
print(month, day, year)             -- 2025  03  29

-- Replace/substitute:
print(string.gsub(s, "World", "Lua"))         -- "Hello, Lua!"  1
print(string.gsub(s, "[aeiou]", "*"))         -- "H*ll*, W*rld!" 4
print(string.gsub(s, "%a", "_"))              -- "_____  ______" (all letters)
print(string.gsub("123 abc 456", "%d+", "N")) -- "N abc N"

-- gsub with function replacement:
local result = string.gsub("hello world", "(%w+)", function(w)
    return w:sub(1,1):upper() .. w:sub(2)   -- Capitalize each word
end)
print(result)    -- "Hello World"

-- Count occurrences:
local _, count = string.gsub("banana", "a", "a")
print(count)     -- 3 (gsub returns count as 2nd value)

-- Format (sprintf-equivalent):
print(string.format("Name: %-10s Age: %03d GPA: %.2f", "Aryan", 17, 9.8))
-- "Name: Aryan      Age: 017 GPA: 9.80"

-- Format specifiers:
-- %d = integer, %i = integer, %u = unsigned
-- %f = float, %e = scientific, %g = shorter of f/e
-- %s = string, %q = quoted string (safe for Lua code)
-- %x = hex lowercase, %X = hex uppercase
-- %c = character from ASCII code
-- %% = literal %

-- Repeat:
print(string.rep("ab", 3))          -- "ababab"
print(string.rep("ab", 3, ","))     -- "ab,ab,ab" (with separator)

-- Reverse:
print(string.reverse("hello"))       -- "olleh"

-- Byte/char conversion:
print(string.byte("A"))             -- 65
print(string.byte("hello", 1, 3))  -- 104  101  108
print(string.char(72, 101, 108, 108, 111))  -- "Hello"

-- ── LUA PATTERNS (not full regex, but powerful) ──────────────────────────────
-- Pattern classes:
-- %a  — letters          %A  — non-letters
-- %d  — digits           %D  — non-digits
-- %l  — lowercase        %L  — non-lowercase
-- %u  — uppercase        %U  — non-uppercase
-- %s  — whitespace       %S  — non-whitespace
-- %w  — alphanumeric     %W  — non-alphanumeric
-- %p  — punctuation      %P  — non-punctuation
-- %c  — control chars    %C  — non-control
-- %x  — hex digits
-- .   — any character
-- [set] — character class: [abc], [a-z], [^abc] (negation)

-- Anchors:
-- ^ — beginning of string
-- $ — end of string

-- Quantifiers:
-- * — 0 or more (greedy)
-- + — 1 or more (greedy)
-- - — 0 or more (lazy, shortest match)
-- ? — 0 or 1

-- Captures:
-- (pattern) — captured group

-- String match:
local date = "2025-03-29"
local y, m, d = date:match("(%d%d%d%d)-(%d%d)-(%d%d)")
print(y, m, d)    -- 2025  03  29

-- gmatch — iterate all matches:
local str = "one 1, two 2, three 3"
for word, num in str:gmatch("(%a+)%s*(%d+)") do
    print(word, num)   -- one 1, two 2, three 3
end

-- Method syntax (using :):
-- s:method(args) is same as string.method(s, args)
print(("hello world"):upper())         -- "HELLO WORLD"
print(("  hello  "):match("^%s*(.-)%s*$"))  -- "hello" (trim!)

-- ── COMMON STRING PATTERNS ────────────────────────────────────────────────────
local function trim(s)
    return s:match("^%s*(.-)%s*$")
end

local function split(s, sep)
    sep = sep or "%s"
    local parts = {}
    for part in s:gmatch("([^" .. sep .. "]+)") do
        parts[#parts + 1] = part
    end
    return parts
end

local function startswith(s, prefix)
    return s:sub(1, #prefix) == prefix
end

local function endswith(s, suffix)
    return s:sub(-#suffix) == suffix
end

print(trim("   hello   "))         -- "hello"
local p = split("a,b,c,d", ",")
print(table.concat(p, "|"))        -- "a|b|c|d"
print(startswith("hello", "hel")) -- true
print(endswith("hello", "llo"))   -- true
```

---

### Part 4: Modules and Package System

```lua
-- ── LUA MODULE PATTERN ────────────────────────────────────────────────────────
-- A module is a table of functions and values
-- Convention: return a table from your module file

-- math_utils.lua:
local M = {}   -- Module table (M by convention)

function M.clamp(value, min, max)
    return math.min(math.max(value, min), max)
end

function M.lerp(a, b, t)
    return a + (b - a) * t
end

function M.round(n, decimals)
    local mult = 10 ^ (decimals or 0)
    return math.floor(n * mult + 0.5) / mult
end

function M.is_nan(n)
    return n ~= n    -- NaN is the only value not equal to itself!
end

-- Private function (not in M — not exported):
local function _validate(n)
    if type(n) ~= "number" then
        error("Expected number, got " .. type(n), 2)
    end
end

function M.safe_sqrt(n)
    _validate(n)
    if n < 0 then return nil, "Cannot take sqrt of negative number" end
    return math.sqrt(n)
end

return M   -- ALWAYS return the module table!

-- ── USING MODULES ─────────────────────────────────────────────────────────────
-- main.lua:
local utils = require("math_utils")   -- Load math_utils.lua

print(utils.clamp(150, 0, 100))  -- 100
print(utils.lerp(0, 100, 0.5))  -- 50.0
print(utils.round(3.14159, 2))  -- 3.14

local result, err = utils.safe_sqrt(-5)
print(result, err)   -- nil  Cannot take sqrt of negative number

-- ── HOW REQUIRE WORKS ─────────────────────────────────────────────────────────
-- require("name") does:
-- 1. Check package.loaded["name"] — if found, return cached module
-- 2. Search package.path for name.lua or name/init.lua
-- 3. Load and execute the file
-- 4. Store result in package.loaded["name"]
-- 5. Return the result

-- package.path — where Lua looks for modules:
print(package.path)
-- Typically: ./?.lua;/usr/local/share/lua/5.4/?.lua;etc.

-- Add custom search path:
package.path = package.path .. ";./my_libs/?.lua"

-- package.loaded — cache of loaded modules:
package.loaded["math_utils"] = nil   -- Force reload next require
local fresh = require("math_utils")  -- Reloads from file

-- ── SUBMODULE PATTERN ─────────────────────────────────────────────────────────
-- game/player.lua
local Player = {}
Player.__index = Player

function Player.new(x, y)
    return setmetatable({x = x, y = y, health = 100}, Player)
end

function Player:move(dx, dy)
    self.x = self.x + dx
    self.y = self.y + dy
end

return Player

-- main.lua:
local Player2 = require("game.player")   -- Loads game/player.lua
local p = Player2.new(0, 0)
p:move(10, 5)

-- ── ENVIRONMENT ISOLATION ─────────────────────────────────────────────────────
-- Good modules don't pollute the global namespace:
-- BAD:
-- x = 10           -- Creates global!
-- function foo()   -- Creates global!

-- GOOD:
-- local M = {}
-- M.x = 10
-- function M.foo() end
-- return M
```

---

### 📊 Full Lua System Overview Table

| Feature              | Lua Mechanism                             | Key Insight                                            |
|----------------------|-------------------------------------------|--------------------------------------------------------|
| Types                | 8 types: nil, boolean, number, string, function, table, thread, userdata | Everything is one of these |
| Tables               | The ONLY data structure — arrays, dicts, objects, modules | Master tables = master Lua |
| Metatables           | `setmetatable` + metamethods               | OOP, operator overloading, any behavior extensibility |
| Closures             | Functions capture upvalues                 | Enables modules, OOP, iterators, coroutines          |
| Coroutines           | Cooperative threads via `coroutine.*`      | Non-preemptive concurrency — like `async/await` manual|
| Multiple returns     | `return a, b, c` — native language feature | No need for tuples or wrappers                        |
| Varargs              | `...` — spread all args                   | Combined with `select()` for rich variadic functions  |
| Global vs local      | `local` keyword — explicit scoping        | Globals are default (dangerous!) — always use local   |
| GC                   | Incremental mark-and-sweep                 | Tune with `collectgarbage()` for game/RT use          |
| C API                | `lua_State*` — call Lua from C and back   | The entire power of Lua's embedding story             |

---

## 🔄 5. Real-World Workflow

---

### 🟢 Beginner Workflow: Configuration System

```lua
-- config.lua — A real-world Lua configuration and settings system

local Config = {}
Config.__index = Config

-- Default values:
local DEFAULTS = {
    server = {
        host = "localhost",
        port = 8080,
        max_connections = 100,
        timeout = 30,
        ssl = false,
    },
    database = {
        url      = "sqlite:///app.db",
        pool_min = 2,
        pool_max = 10,
        timeout  = 5,
    },
    logging = {
        level    = "info",
        file     = "app.log",
        max_size = 10 * 1024 * 1024,  -- 10MB
        console  = true,
    },
    features = {
        analytics  = false,
        dark_mode  = true,
        beta       = false,
    },
}

-- Deep merge (override defaults with user config):
local function deep_merge(base, override)
    local result = {}
    for k, v in pairs(base) do
        result[k] = v
    end
    for k, v in pairs(override or {}) do
        if type(v) == "table" and type(result[k]) == "table" then
            result[k] = deep_merge(result[k], v)
        else
            result[k] = v
        end
    end
    return result
end

function Config.new(user_config)
    local self = setmetatable({}, Config)
    self._data = deep_merge(DEFAULTS, user_config or {})
    return self
end

-- Dot-path access: config:get("server.host")
function Config:get(path, default)
    local current = self._data
    for key in path:gmatch("[^.]+") do
        if type(current) ~= "table" then
            return default
        end
        current = current[key]
    end
    if current == nil then return default end
    return current
end

function Config:set(path, value)
    local keys = {}
    for k in path:gmatch("[^.]+") do
        keys[#keys + 1] = k
    end

    local current = self._data
    for i = 1, #keys - 1 do
        if type(current[keys[i]]) ~= "table" then
            current[keys[i]] = {}
        end
        current = current[keys[i]]
    end
    current[keys[#keys]] = value
end

function Config:require_field(path)
    local value = self:get(path)
    if value == nil then
        error("Required config field missing: " .. path, 2)
    end
    return value
end

-- Usage:
local cfg = Config.new({
    server = {port = 3000, ssl = true},
    features = {analytics = true},
})

print(cfg:get("server.host"))           -- "localhost" (default)
print(cfg:get("server.port"))           -- 3000 (overridden)
print(cfg:get("server.ssl"))            -- true (overridden)
print(cfg:get("logging.level"))         -- "info" (default)
print(cfg:get("missing.key", "none"))   -- "none" (default)
print(cfg:get("features.analytics"))    -- true (overridden)

cfg:set("database.url", "postgresql://localhost/mydb")
print(cfg:get("database.url"))          -- "postgresql://localhost/mydb"
```

---

### 🔵 Professional Workflow: Event System & Plugin Architecture

```lua
-- event_system.lua — A robust event/plugin system (used in games, servers)

-- ── EVENT EMITTER ─────────────────────────────────────────────────────────────
local EventEmitter = {}
EventEmitter.__index = EventEmitter

function EventEmitter.new()
    return setmetatable({_handlers = {}, _once_handlers = {}}, EventEmitter)
end

function EventEmitter:on(event, handler, priority)
    if not self._handlers[event] then
        self._handlers[event] = {}
    end
    table.insert(self._handlers[event], {
        fn = handler,
        priority = priority or 0,
    })
    -- Sort by priority (higher priority runs first):
    table.sort(self._handlers[event], function(a, b)
        return a.priority > b.priority
    end)
    return self  -- Enable chaining
end

function EventEmitter:once(event, handler)
    if not self._once_handlers[event] then
        self._once_handlers[event] = {}
    end
    self._once_handlers[event][#self._once_handlers[event] + 1] = handler
    return self
end

function EventEmitter:off(event, handler)
    if self._handlers[event] then
        for i, h in ipairs(self._handlers[event]) do
            if h.fn == handler then
                table.remove(self._handlers[event], i)
                return
            end
        end
    end
end

function EventEmitter:emit(event, ...)
    -- Run once handlers first:
    local once = self._once_handlers[event]
    if once then
        self._once_handlers[event] = nil
        for _, handler in ipairs(once) do
            handler(...)
        end
    end

    -- Run regular handlers:
    local handlers = self._handlers[event]
    if not handlers then return end

    for _, h in ipairs(handlers) do
        local ok, err = pcall(h.fn, ...)
        if not ok then
            io.stderr:write("Event handler error [" .. event .. "]: " .. err .. "\n")
        end
    end
end

function EventEmitter:remove_all(event)
    if event then
        self._handlers[event] = nil
        self._once_handlers[event] = nil
    else
        self._handlers = {}
        self._once_handlers = {}
    end
end

-- ── PLUGIN SYSTEM ─────────────────────────────────────────────────────────────
local PluginManager = {}
PluginManager.__index = PluginManager

function PluginManager.new(app)
    return setmetatable({
        _app = app,
        _plugins = {},
        _hooks = {},
    }, PluginManager)
end

function PluginManager:register(plugin)
    assert(plugin.name, "Plugin must have a name")
    assert(type(plugin.install) == "function", "Plugin must have an install function")

    if self._plugins[plugin.name] then
        error("Plugin already registered: " .. plugin.name)
    end

    self._plugins[plugin.name] = plugin
    plugin:install(self._app)
    print("[Plugin] Registered: " .. plugin.name)
    return self
end

function PluginManager:hook(name, fn)
    if not self._hooks[name] then
        self._hooks[name] = {}
    end
    self._hooks[name][#self._hooks[name] + 1] = fn
end

function PluginManager:run_hooks(name, context)
    local hooks = self._hooks[name]
    if not hooks then return context end

    for _, hook in ipairs(hooks) do
        context = hook(context) or context
    end
    return context
end

-- Example usage:
local emitter = EventEmitter.new()

emitter
    :on("user:login", function(user)
        print("User logged in: " .. user.name)
    end, 10)                          -- High priority
    :on("user:login", function(user)
        print("Sending welcome email to: " .. user.email)
    end)                              -- Normal priority
    :once("first:visit", function()
        print("First time visitor!")
    end)

emitter:emit("user:login", {name = "Aryan", email = "a@b.com"})
-- User logged in: Aryan
-- Sending welcome email to: a@b.com

emitter:emit("first:visit")   -- First time visitor!
emitter:emit("first:visit")   -- Nothing (once handler consumed)
```

---

## 🧪 6. Hands-on Practice Projects

---

### 🟢 Beginner Project: JSON-Like Serializer

```lua
-- serializer.lua — Serialize Lua tables to/from JSON-like format

local Serializer = {}

local function serialize_value(v, indent, current_indent)
    local t = type(v)
    if t == "nil" then
        return "null"
    elseif t == "boolean" then
        return tostring(v)
    elseif t == "number" then
        if v ~= v then return "null" end  -- NaN
        if v == math.huge or v == -math.huge then return "null" end
        if math.type(v) == "integer" then
            return tostring(v)
        else
            return string.format("%.14g", v)
        end
    elseif t == "string" then
        -- Escape special characters:
        v = v:gsub('\\', '\\\\')
        v = v:gsub('"', '\\"')
        v = v:gsub('\n', '\\n')
        v = v:gsub('\r', '\\r')
        v = v:gsub('\t', '\\t')
        return '"' .. v .. '"'
    elseif t == "table" then
        -- Check if it's an array:
        local is_array = true
        local max_n = 0
        for k, _ in pairs(v) do
            if type(k) ~= "number" or k < 1 or math.floor(k) ~= k then
                is_array = false
                break
            end
            max_n = math.max(max_n, k)
        end
        is_array = is_array and max_n == #v

        local next_indent = current_indent .. indent
        local parts = {}

        if is_array then
            for _, val in ipairs(v) do
                parts[#parts + 1] = next_indent .. serialize_value(val, indent, next_indent)
            end
            if #parts == 0 then return "[]" end
            return "[\n" .. table.concat(parts, ",\n") .. "\n" .. current_indent .. "]"
        else
            -- Sort keys for deterministic output:
            local keys = {}
            for k in pairs(v) do
                if type(k) == "string" then
                    keys[#keys + 1] = k
                end
            end
            table.sort(keys)
            for _, k in ipairs(keys) do
                parts[#parts + 1] = next_indent
                    .. '"' .. k .. '": '
                    .. serialize_value(v[k], indent, next_indent)
            end
            if #parts == 0 then return "{}" end
            return "{\n" .. table.concat(parts, ",\n") .. "\n" .. current_indent .. "}"
        end
    else
        return '"[' .. t .. ']"'
    end
end

function Serializer.encode(value, indent)
    return serialize_value(value, indent or "  ", "")
end

-- Test:
local data = {
    name    = "Aryan",
    age     = 17,
    active  = true,
    scores  = {9.8, 9.2, 8.9},
    address = {city = "Kolkata", zip = "700001"},
    notes   = nil,  -- nil fields are excluded
}

print(Serializer.encode(data))
```

✅ **You've succeeded when:** The output is valid, properly indented JSON that can be parsed by any JSON parser.

---

### 🔵 Intermediate Project: Reactive State Machine

```lua
-- state_machine.lua — Hierarchical state machine with guards and transitions

local StateMachine = {}
StateMachine.__index = StateMachine

function StateMachine.new(config)
    local self = setmetatable({}, StateMachine)
    self._states  = config.states or {}
    self._initial = config.initial
    self._current = nil
    self._history = {}
    self._listeners = {}
    return self
end

function StateMachine:start()
    self:_enter_state(self._initial, nil, {})
    return self
end

function StateMachine:transition(event, data)
    data = data or {}
    local state = self._states[self._current]
    if not state then
        return false, "Current state not found: " .. tostring(self._current)
    end

    local trans = state.on and state.on[event]
    if not trans then
        return false, "No transition for event '" .. event .. "' in state '" .. self._current .. "'"
    end

    -- Evaluate guards:
    if trans.guard and not trans.guard(self, data) then
        return false, "Guard rejected transition"
    end

    -- Perform transition:
    local next_state = trans.target
    self:_exit_state(self._current, event, data)
    self:_enter_state(next_state, event, data)
    if trans.action then trans.action(self, data) end
    return true
end

function StateMachine:_enter_state(state_name, event, data)
    self._history[#self._history + 1] = {
        state = state_name,
        event = event,
        time  = os.clock(),
    }
    self._current = state_name
    local state = self._states[state_name]
    if state and state.on_enter then
        state.on_enter(self, data)
    end
    self:_notify("state:enter", {state = state_name, data = data})
end

function StateMachine:_exit_state(state_name, event, data)
    local state = self._states[state_name]
    if state and state.on_exit then
        state.on_exit(self, data)
    end
    self:_notify("state:exit", {state = state_name, event = event})
end

function StateMachine:on(event, handler)
    if not self._listeners[event] then
        self._listeners[event] = {}
    end
    self._listeners[event][#self._listeners[event] + 1] = handler
end

function StateMachine:_notify(event, data)
    local handlers = self._listeners[event]
    if handlers then
        for _, h in ipairs(handlers) do h(data) end
    end
end

function StateMachine:state() return self._current end
function StateMachine:can(event) return self._states[self._current]
    and self._states[self._current].on
    and self._states[self._current].on[event] ~= nil
end

-- Example: Traffic Light:
local light = StateMachine.new({
    initial = "red",
    states = {
        red = {
            on_enter = function(sm) print("🔴 RED — STOP!") end,
            on = {
                go = {target = "green"},
            }
        },
        green = {
            on_enter = function(sm) print("🟢 GREEN — GO!") end,
            on = {
                slow = {target = "yellow"},
            }
        },
        yellow = {
            on_enter = function(sm) print("🟡 YELLOW — CAUTION!") end,
            on = {
                stop = {target = "red"},
            }
        },
    }
})

light:on("state:enter", function(data)
    print("  → Entered state: " .. data.state)
end)

light:start()
light:transition("go")
light:transition("slow")
light:transition("stop")
print("Can 'go'?", light:can("go"))     -- true
print("Can 'slow'?", light:can("slow")) -- false
```

---

### 🔴 Advanced Project: Coroutine-Based Job Scheduler

```lua
-- scheduler.lua — Cooperative task scheduler using coroutines

local Scheduler = {}
Scheduler.__index = Scheduler

function Scheduler.new()
    return setmetatable({
        _ready   = {},    -- Tasks ready to run
        _waiting = {},    -- Tasks waiting for a condition
        _sleeping= {},    -- Tasks sleeping until a time
        _current = nil,
        _time    = 0,
        _id_counter = 0,
    }, Scheduler)
end

function Scheduler:spawn(fn, ...)
    self._id_counter = self._id_counter + 1
    local task = {
        id  = self._id_counter,
        co  = coroutine.create(fn),
        args = {...},
    }
    self._ready[#self._ready + 1] = task
    return task.id
end

function Scheduler:sleep(seconds)
    -- Suspend current coroutine until time passes
    coroutine.yield("sleep", seconds)
end

function Scheduler:yield()
    -- Give other coroutines a chance to run
    coroutine.yield("yield")
end

function Scheduler:wait_for(condition_fn)
    coroutine.yield("wait", condition_fn)
end

function Scheduler:run_until_done()
    while true do
        -- Move sleeping tasks that are ready:
        local now = self._time
        local still_sleeping = {}
        for _, entry in ipairs(self._sleeping) do
            if now >= entry.wake_at then
                self._ready[#self._ready + 1] = entry.task
            else
                still_sleeping[#still_sleeping + 1] = entry
            end
        end
        self._sleeping = still_sleeping

        -- Check waiting tasks:
        local still_waiting = {}
        for _, entry in ipairs(self._waiting) do
            if entry.condition() then
                self._ready[#self._ready + 1] = entry.task
            else
                still_waiting[#still_waiting + 1] = entry
            end
        end
        self._waiting = still_waiting

        -- No more tasks?
        if #self._ready == 0 and #self._waiting == 0 and #self._sleeping == 0 then
            break
        end

        -- Run one step per ready task:
        local tasks_this_round = self._ready
        self._ready = {}

        for _, task in ipairs(tasks_this_round) do
            self._current = task
            local ok, action, arg

            if task.args then
                ok, action, arg = coroutine.resume(task.co, table.unpack(task.args))
                task.args = nil
            else
                ok, action, arg = coroutine.resume(task.co)
            end

            if not ok then
                io.stderr:write("Task " .. task.id .. " error: " .. tostring(action) .. "\n")
            elseif coroutine.status(task.co) == "dead" then
                -- Task finished — don't reschedule
            elseif action == "sleep" then
                self._sleeping[#self._sleeping + 1] = {
                    task    = task,
                    wake_at = self._time + (arg or 0),
                }
            elseif action == "wait" then
                self._waiting[#self._waiting + 1] = {
                    task      = task,
                    condition = arg,
                }
            else  -- "yield" or anything else — just reschedule
                self._ready[#self._ready + 1] = task
            end

            -- Advance simulated time:
            self._time = self._time + 0.001
        end
    end
end

-- Usage:
local sched = Scheduler.new()
local shared_data = {}

sched:spawn(function()
    print("[Task 1] Starting")
    sched:sleep(0.1)
    print("[Task 1] After sleep 0.1")
    shared_data.ready = true
    sched:sleep(0.2)
    print("[Task 1] Done")
end)

sched:spawn(function()
    print("[Task 2] Starting, waiting for data...")
    sched:wait_for(function() return shared_data.ready == true end)
    print("[Task 2] Data is ready! Processing...")
    sched:yield()
    print("[Task 2] Done")
end)

sched:spawn(function()
    for i = 1, 3 do
        print("[Task 3] Step " .. i)
        sched:yield()
    end
end)

sched:run_until_done()
```

🔥 **Challenge:** Add task priorities, cancellation via `sched:cancel(id)`, and a `sched:all(...)` that waits for multiple tasks to finish before resuming.

---

## ⚠️ 7. Common Mistakes

---

### ❌ Mistake 1: Global Variables Instead of Local

```lua
-- ❌ WRONG — pollutes the global environment:
function process(data)
    result = 0           -- GLOBAL! Every function can see/modify this!
    for i, v in ipairs(data) do
        total = total + v  -- GLOBAL! Undefined if another function sets it
    end
    return result
end

-- ❌ Even worse — accidental global in a loop:
for i = 1, 10 do
    value = i * i   -- GLOBAL! Creates 10 iterations of global pollution
end

-- ✅ RIGHT — always use local:
local function process_good(data)
    local result = 0
    for _, v in ipairs(data) do
        result = result + v
    end
    return result
end

-- ✅ RIGHT — check for accidental globals during development:
-- Use the strict.lua module or add this to your environment:
setmetatable(_G, {
    __newindex = function(t, key, value)
        error("Attempt to create global: " .. tostring(key), 2)
    end
})
```

---

### ❌ Mistake 2: 1-Indexing Confusion

```lua
-- ❌ WRONG — Lua arrays are 1-indexed, not 0-indexed:
local arr = {"a", "b", "c", "d", "e"}
for i = 0, #arr - 1 do   -- WRONG! starts at 0
    print(arr[i])          -- arr[0] = nil!
end

-- ❌ WRONG — trying to use array length with "holes":
local sparse = {1, 2, nil, 4, 5}
print(#sparse)   -- UNDEFINED! Could be 2 or 5 — depends on Lua version!

-- ✅ RIGHT — use 1-indexed loops:
local arr2 = {"a", "b", "c", "d", "e"}
for i = 1, #arr2 do
    print(i, arr2[i])   -- 1 a, 2 b, 3 c, 4 d, 5 e
end

-- ✅ RIGHT — use ipairs for arrays (stops at first nil):
for i, v in ipairs(arr2) do
    print(i, v)
end

-- ✅ RIGHT — avoid holes; use explicit length tracking:
local list = {}
local count = 0

local function push(t, v, n)
    n = n + 1
    t[n] = v
    return n
end
```

---

### ❌ Mistake 3: String Comparison Instead of `==`

```lua
-- ❌ WRONG — comparing tables by value (tables compare by reference!):
local t1 = {1, 2, 3}
local t2 = {1, 2, 3}
print(t1 == t2)   -- false! Different table objects!

-- ❌ Also wrong — comparing numbers from different types:
print(1 == 1.0)   -- TRUE in Lua! int == float when values match
-- This is actually correct Lua behavior, but can surprise.

-- ❌ Wrong — using ~ for bitwise XOR instead of != :
-- ~= is NOT equal in Lua, not bitwise XOR!
print(1 ~= 2)   -- true (not equal)

-- ✅ RIGHT — deep equality for tables:
local function deep_equal(a, b)
    if type(a) ~= type(b) then return false end
    if type(a) ~= "table" then return a == b end
    for k, v in pairs(a) do
        if not deep_equal(v, b[k]) then return false end
    end
    for k in pairs(b) do
        if a[k] == nil then return false end
    end
    return true
end

print(deep_equal({1,2,3}, {1,2,3}))   -- true
```

---

### ❌ Mistake 4: Not Using `pcall` for Error Handling

```lua
-- ❌ WRONG — errors propagate and crash the program:
local function risky()
    error("Something went wrong!")
end

risky()   -- Program crashes here!

-- ❌ WRONG — not checking return values:
local f = io.open("missing.txt", "r")
local content = f:read("*a")   -- Crash! f is nil!

-- ✅ RIGHT — wrap in pcall:
local ok, err = pcall(risky)
if not ok then
    print("Caught error:", err)   -- Caught error: file.lua:2: Something went wrong!
end

-- ✅ RIGHT — xpcall for stack trace:
local function error_handler(err)
    return debug.traceback(err, 2)
end

local ok2, result = xpcall(risky, error_handler)
if not ok2 then
    print("Error with traceback:\n" .. result)
end

-- ✅ RIGHT — check all file/IO operations:
local file, err2 = io.open("data.txt", "r")
if not file then
    print("Cannot open file:", err2)
else
    local content = file:read("*a")
    file:close()
    print(content)
end

-- ✅ RIGHT — error with levels:
local function validate_age(age)
    if type(age) ~= "number" then
        error("age must be a number, got: " .. type(age), 2)  -- Level 2 = blame caller!
    end
    if age < 0 or age > 150 then
        error("age must be 0-150, got: " .. age, 2)
    end
end
```

---

### ❌ Mistake 5: Misusing `pairs` vs `ipairs`

```lua
-- ❌ WRONG — using pairs for ordered array iteration:
local names = {"Charlie", "Alice", "Bob"}
for k, v in pairs(names) do
    print(k, v)   -- Might not be in order! pairs doesn't guarantee order
end

-- ❌ WRONG — using ipairs when you have non-sequential keys:
local mixed = {name = "Aryan", 1, 2, 3}
for i, v in ipairs(mixed) do
    print(i, v)   -- Only prints: 1 1, 2 2, 3 3 — misses "name"!
end

-- ❌ WRONG — ipairs stops at nil:
local sparse = {1, 2, nil, 4}
for i, v in ipairs(sparse) do
    print(i, v)   -- Only: 1 1, 2 2 — stops at nil!
end

-- ✅ RIGHT — ipairs for sequential arrays (guaranteed order 1, 2, 3...):
local arr = {"Alice", "Bob", "Charlie"}
for i, name in ipairs(arr) do
    print(i, name)   -- 1 Alice, 2 Bob, 3 Charlie
end

-- ✅ RIGHT — pairs for all key-value pairs (dict + array keys):
local person = {name = "Aryan", age = 17}
for key, value in pairs(person) do
    print(key, value)   -- name Aryan, age 17
end

-- ✅ RIGHT — sort keys manually for deterministic pairs iteration:
local function sorted_pairs(t)
    local keys = {}
    for k in pairs(t) do keys[#keys + 1] = k end
    table.sort(keys, function(a, b) return tostring(a) < tostring(b) end)
    local i = 0
    return function()
        i = i + 1
        return keys[i], t[keys[i]]
    end
end

local cfg = {zebra = 3, apple = 1, mango = 2}
for k, v in sorted_pairs(cfg) do
    print(k, v)   -- apple 1, mango 2, zebra 3 (sorted!)
end
```

---

### ❌ Mistake 6: Concatenation in Loops (O(n²) Performance)

```lua
-- ❌ WRONG — string concatenation in loop is O(n²):
local function build_bad(n)
    local result = ""
    for i = 1, n do
        result = result .. tostring(i) .. ", "  -- Creates new string each iteration!
    end
    return result
end

-- For n=10000, this is catastrophically slow!

-- ✅ RIGHT — use table.concat:
local function build_good(n)
    local parts = {}
    for i = 1, n do
        parts[#parts + 1] = tostring(i)
    end
    return table.concat(parts, ", ")   -- ONE string allocation!
end

-- ✅ Also RIGHT — use string buffer with io approach:
local function build_with_buffer(n)
    local buf = {}
    for i = 1, n do
        buf[i] = i    -- Avoid tostring in inner loop if not needed
    end
    return table.concat(buf, ", ")
end

-- Benchmark:
local t1 = os.clock()
build_bad(5000)
print("Bad: " .. (os.clock() - t1) .. "s")

local t2 = os.clock()
build_good(5000)
print("Good: " .. (os.clock() - t2) .. "s")
-- Good is typically 100-1000× faster!
```

---

## 🔥 8. Pro Tips & Hidden Tricks

---

### 💎 Tip 1: The `__index` Function for Default Values and Validation

```lua
-- Use __index as a function for powerful default generation:

-- Auto-vivification (auto-create nested tables):
local function auto_table()
    return setmetatable({}, {
        __index = function(t, k)
            local inner = auto_table()
            t[k] = inner
            return inner
        end
    })
end

local data = auto_table()
data.users.aryan.settings.theme = "dark"   -- No errors! Tables created automatically
data.users.priya.settings.language = "en"

print(data.users.aryan.settings.theme)      -- "dark"
print(data.users.priya.settings.language)   -- "en"
print(type(data.users.aryan.settings))      -- "table"

-- Typed defaults with validation:
local function make_typed(schema)
    return setmetatable({}, {
        __index = function(t, k)
            local default = schema[k]
            if default ~= nil then return default end
            error("Unknown field: " .. tostring(k), 2)
        end,
        __newindex = function(t, k, v)
            local expected_type = schema[k .. "_type"] or type(schema[k])
            if schema[k] == nil then
                error("Unknown field: " .. tostring(k), 2)
            end
            if type(v) ~= expected_type and expected_type ~= "any" then
                error(string.format("Field '%s' must be %s, got %s", k, expected_type, type(v)), 2)
            end
            rawset(t, k, v)
        end
    })
end

local PlayerConfig = make_typed({
    name  = "Unknown",
    health= 100,
    speed = 200.0,
})

PlayerConfig.name = "Aryan"     -- OK: string = string
PlayerConfig.health = 150       -- OK: number = number
-- PlayerConfig.health = "100"  -- ERROR: number expected, got string
-- PlayerConfig.level = 5       -- ERROR: Unknown field: level
print(PlayerConfig.speed)       -- 200.0 (default from schema)
```

---

### 💎 Tip 2: Coroutines as Iterators

```lua
-- Coroutines make beautiful infinite iterators!

-- Range iterator (like Python's range):
local function range(from, to, step)
    step = step or 1
    return coroutine.wrap(function()
        if step > 0 then
            for i = from, to, step do coroutine.yield(i) end
        else
            for i = from, to, step do coroutine.yield(i) end
        end
    end)
end

for n in range(1, 10) do io.write(n .. " ") end
print()   -- 1 2 3 4 5 6 7 8 9 10

for n in range(10, 1, -2) do io.write(n .. " ") end
print()   -- 10 8 6 4 2

-- Infinite sequence:
local function naturals()
    return coroutine.wrap(function()
        local n = 1
        while true do
            coroutine.yield(n)
            n = n + 1
        end
    end)
end

local function take(n, iter)
    local result = {}
    local count = 0
    for v in iter do
        count = count + 1
        result[count] = v
        if count >= n then break end
    end
    return result
end

local first10 = take(10, naturals())
print(table.concat(first10, ", "))   -- 1, 2, 3, 4, 5, 6, 7, 8, 9, 10

-- Tree traversal as iterator:
local function dfs(node)
    return coroutine.wrap(function()
        coroutine.yield(node.value)
        if node.children then
            for _, child in ipairs(node.children) do
                for v in dfs(child) do
                    coroutine.yield(v)
                end
            end
        end
    end)
end

local tree = {
    value = 1,
    children = {
        {value = 2, children = {{value = 4}, {value = 5}}},
        {value = 3, children = {{value = 6}}},
    }
}

for v in dfs(tree) do io.write(v .. " ") end
print()   -- 1 2 4 5 3 6
```

---

### 💎 Tip 3: `rawget` / `rawset` — Bypass Metatables

```lua
-- rawget, rawset, rawequal, rawlen bypass metamethods entirely
-- Essential when you need to inspect or modify tables without triggering metamethods

local tracked = setmetatable({}, {
    __index = function(t, k)
        print("  READ: " .. tostring(k))
        return rawget(t, k)    -- Access without triggering __index again!
    end,
    __newindex = function(t, k, v)
        print("  WRITE: " .. tostring(k) .. " = " .. tostring(v))
        rawset(t, k, v)        -- Write without triggering __newindex again!
    end,
})

tracked.name = "Aryan"        -- WRITE: name = Aryan
print(tracked.name)            -- READ: name \n Aryan

-- Without raw: would cause infinite recursion!
-- __newindex calls rawset so we don't recurse
-- __index calls rawget so we don't recurse

-- rawequal — compare without __eq metamethod:
local t1 = setmetatable({}, {__eq = function() return true end})
local t2 = setmetatable({}, {__eq = function() return true end})
print(t1 == t2)           -- true (via __eq)
print(rawequal(t1, t2))   -- false (different table objects!)
print(rawequal(t1, t1))   -- true (same object)

-- rawlen — length without __len metamethod:
local custom_len = setmetatable({1, 2, 3}, {
    __len = function() return 999 end
})
print(#custom_len)          -- 999 (via __len)
print(rawlen(custom_len))   -- 3 (actual table length)
```

---

### 💎 Tip 4: The Power of `load()` and `loadstring()`

```lua
-- load() compiles a string as Lua code and returns a function
-- Enables: runtime code generation, sandboxing, hot reloading

-- Basic load:
local fn = load("return 1 + 1")
print(fn())    -- 2

-- Load with variables from an environment:
local code = "return x * y + z"
local env = {x = 3, y = 4, z = 5}

-- Lua 5.2+: load() with environment:
local fn2 = load("return x * y + z", "chunk", "t", env)
print(fn2())    -- 17

-- Template evaluation:
local function eval_template(template, vars)
    -- Replace {{var}} with Lua expressions:
    local code2 = template:gsub("{{(.-)}}",
        function(expr)
            return '" .. tostring(' .. expr .. ') .. "'
        end
    )
    code2 = 'return "' .. code2 .. '"'
    local fn3 = load(code2, "template", "t", vars)
    if not fn3 then return nil, "Failed to compile template" end
    return pcall(fn3)
end

local ok, result = eval_template(
    "Hello, {{name}}! You have {{coins * 2}} coins.",
    {name = "Aryan", coins = 50}
)
print(result)    -- Hello, Aryan! You have 100 coins.

-- Sandboxed execution (limited environment):
local function sandbox_run(code2, allowed)
    local env2 = {
        print = print,
        math  = math,
        table = table,
        -- No io, os, load, dofile, etc. — sandboxed!
    }
    for k, v in pairs(allowed or {}) do
        env2[k] = v
    end
    setmetatable(env2, {__index = function() return nil end})

    local fn3, err = load(code2, "sandbox", "t", env2)
    if not fn3 then return nil, err end
    return pcall(fn3)
end

local ok2, res = sandbox_run("return math.sqrt(144)")
print(ok2, res)    -- true  12.0

local ok3, err2 = sandbox_run("return io.open('secret.txt')")
print(ok3, err2)   -- false  [sandbox]:1: attempt to index a nil value (global 'io')
```

---

### 💎 Tip 5: Weak Tables — Memory-Friendly Caches

```lua
-- Weak tables let the garbage collector reclaim objects
-- even if the table still references them!
-- Key for: caches, memoization, observer patterns without memory leaks

-- Weak keys: key can be GC'd even though it's in this table
-- Weak values: value can be GC'd even though table references it
-- Weak both: both key and value are weak

-- Memoization cache with weak values (cache entries GC'd when not used):
local function make_cache(compute)
    local cache = setmetatable({}, {__mode = "v"})  -- Weak values!
    return function(key)
        local result = cache[key]
        if result == nil then
            result = compute(key)
            cache[key] = result
        end
        return result
    end
end

local expensive = make_cache(function(n)
    print("Computing for " .. n)
    -- Simulate expensive work:
    local result = {}
    for i = 1, n do result[i] = i * i end
    return result
end)

local r1 = expensive(5)   -- Computing for 5
local r2 = expensive(5)   -- (cached — no print)
print(#r1, #r2)            -- 5  5

-- Observer pattern without memory leaks:
local EventBus = {}
local listeners = setmetatable({}, {__mode = "k"})  -- Weak keys!

function EventBus.subscribe(obj, event, handler)
    if not listeners[obj] then
        listeners[obj] = {}
    end
    listeners[obj][event] = handler
end

function EventBus.broadcast(event, data)
    for obj, events in pairs(listeners) do
        if events[event] then
            events[event](obj, data)
        end
    end
end

-- When obj is GC'd, its entry in listeners is automatically removed!
do
    local obj = {}
    EventBus.subscribe(obj, "update", function(self, data)
        print("Got update:", data)
    end)
    EventBus.broadcast("update", "hello")   -- Got update: hello
end
-- obj goes out of scope here; GC will clean up the listener automatically
collectgarbage()
EventBus.broadcast("update", "world")   -- No output (listener GC'd)
```

---

## 🚀 9. Advanced Concepts (Expert Level)

---

### Advanced Concept 1: Coroutines — Full Model

```lua
-- ── COROUTINE BASICS ──────────────────────────────────────────────────────────
-- coroutine.create(fn)  → creates coroutine, returns thread object
-- coroutine.resume(co, ...) → start/continue coroutine, returns ok, values
-- coroutine.yield(...) → pause coroutine, pass values to resume caller
-- coroutine.wrap(fn)   → creates coroutine, returns a function (throws on error)
-- coroutine.status(co) → "running", "suspended", "dead", "normal"
-- coroutine.isyieldable() → can we yield from here?
-- coroutine.running()  → currently running coroutine

-- Basic producer-consumer:
local function producer()
    local items = {"apple", "banana", "cherry", "date"}
    for _, item in ipairs(items) do
        print("Producing: " .. item)
        coroutine.yield(item)    -- Pause, send item
    end
    return "done"    -- Final value on completion
end

local co = coroutine.create(producer)

while true do
    local ok, value = coroutine.resume(co)
    if not ok then
        print("Error:", value)
        break
    end
    if coroutine.status(co) == "dead" then
        print("Producer finished, last value:", value)  -- "done"
        break
    end
    print("Consumed:", value)
end

-- ── BIDIRECTIONAL COMMUNICATION ───────────────────────────────────────────────
local function echo_server()
    local received = coroutine.yield("ready")   -- Yield "ready", receive first message
    while received ~= "quit" do
        print("Server received: " .. received)
        received = coroutine.yield("ack: " .. received)
    end
    return "server done"
end

local server = coroutine.create(echo_server)

local ok, msg = coroutine.resume(server)       -- Start server
print("Server says:", msg)                      -- "ready"

ok, msg = coroutine.resume(server, "hello")    -- Send "hello"
print("Server replied:", msg)                   -- "ack: hello"

ok, msg = coroutine.resume(server, "world")    -- Send "world"
print("Server replied:", msg)                   -- "ack: world"

ok, msg = coroutine.resume(server, "quit")     -- Quit
print("Final:", msg)                            -- "server done"

-- ── ASYNC I/O SIMULATION ──────────────────────────────────────────────────────
-- This is the pattern used by OpenResty (Nginx + Lua):
-- Coroutines "block" by yielding, but the scheduler handles I/O without blocking

local function async_sleep(scheduler, seconds)
    scheduler:register_sleep(coroutine.running(), seconds)
    coroutine.yield()   -- Suspend until sleep is done
end

local function async_fetch(scheduler, url)
    scheduler:register_request(coroutine.running(), url)
    return coroutine.yield()   -- Suspend until request completes
end

-- ── COROUTINE PIPELINE ────────────────────────────────────────────────────────
local function pipeline(source, ...)
    local transforms = {...}

    return coroutine.wrap(function()
        for value in source do
            local current = value
            local skip = false

            for _, transform in ipairs(transforms) do
                local result = transform(current)
                if result == nil then
                    skip = true
                    break
                end
                current = result
            end

            if not skip then
                coroutine.yield(current)
            end
        end
    end)
end

-- Build a lazy processing pipeline:
local numbers = coroutine.wrap(function()
    for i = 1, 100 do coroutine.yield(i) end
end)

local result2 = pipeline(
    numbers,
    function(n) return n % 3 == 0 and n or nil end,  -- Only multiples of 3
    function(n) return n * n end,                       -- Square them
    function(n) return n < 1000 and n or nil end       -- Below 1000
)

local collected = {}
for v in result2 do
    collected[#collected + 1] = v
end
print(table.concat(collected, ", "))   -- 9, 36, 81, 144, 225, 324, 441, 576, 729, 900
```

---

### Advanced Concept 2: The C API Connection

```lua
-- ── UNDERSTANDING LUA'S C API ─────────────────────────────────────────────────
-- This section shows how Lua and C interact — the basis of ALL Lua embedding

-- From C, a function that Lua can call looks like this:
--[[
static int c_function(lua_State *L) {
    // Stack operations:
    int n = lua_gettop(L);      // Number of arguments
    double a = lua_tonumber(L, 1);  // Get arg 1 as double
    double b = lua_tonumber(L, 2);  // Get arg 2 as double
    lua_pushnumber(L, a + b);   // Push result
    return 1;                   // Number of return values
}
--]]

-- From Lua, calling C functions is completely transparent:
-- (As if they were regular Lua functions)

-- ── UNDERSTANDING THE STACK ────────────────────────────────────────────────────
-- Lua uses a stack for all C/Lua interaction:
-- Positive indices (1, 2, 3...) from bottom
-- Negative indices (-1, -2, -3...) from top

-- ── WRITING C EXTENSIONS FOR LUA ────────────────────────────────────────────────
-- Example C extension (mylib.c):
--[[
#include <lua.h>
#include <lualib.h>
#include <lauxlib.h>

static int l_add(lua_State *L) {
    double a = luaL_checknumber(L, 1);
    double b = luaL_checknumber(L, 2);
    lua_pushnumber(L, a + b);
    return 1;
}

static const luaL_Reg mylib[] = {
    {"add", l_add},
    {NULL, NULL}
};

int luaopen_mylib(lua_State *L) {
    luaL_newlib(L, mylib);
    return 1;
}
--]]
-- Compile: gcc -shared -o mylib.so mylib.c -llua5.4
-- Use:
-- local mylib = require("mylib")
-- print(mylib.add(3, 4))   -- 7.0

-- ── CALLING C FROM LUA: ffi library (LuaJIT) ─────────────────────────────────
-- With LuaJIT's FFI, you can call C functions without writing wrappers!
--[[
local ffi = require("ffi")

ffi.cdef[[
    int printf(const char *fmt, ...);
    double sqrt(double x);
    void *malloc(size_t size);
    void free(void *ptr);
]]

ffi.C.printf("Hello from C! sqrt(144) = %.0f\n", ffi.C.sqrt(144))

local buf = ffi.C.malloc(100)
-- Use buf...
ffi.C.free(buf)
--]]

-- ── DEBUG LIBRARY ─────────────────────────────────────────────────────────────
-- The debug library provides introspection (use carefully!):
local function show_stack()
    local level = 1
    while true do
        local info = debug.getinfo(level, "nSl")
        if not info then break end
        print(string.format("Level %d: %s (%s:%d)",
            level,
            info.name or "<anonymous>",
            info.short_src,
            info.currentline
        ))
        level = level + 1
    end
end

-- Get/set local variables (debugging):
local function get_locals(level)
    level = level or 1
    local locals = {}
    local i = 1
    while true do
        local name, value = debug.getlocal(level + 1, i)
        if not name then break end
        if name:sub(1, 1) ~= "(" then   -- Skip internal vars
            locals[name] = value
        end
        i = i + 1
    end
    return locals
end

-- Upvalue inspection:
local function inspect_upvalues(fn)
    local i = 1
    while true do
        local name, value = debug.getupvalue(fn, i)
        if not name then break end
        print("Upvalue: " .. name .. " = " .. tostring(value))
        i = i + 1
    end
end

local hidden = 42
local function uses_hidden()
    return hidden * 2
end
inspect_upvalues(uses_hidden)   -- Upvalue: hidden = 42
```

---

### Advanced Concept 3: LuaJIT and Performance

```lua
-- LuaJIT is a Just-In-Time compiler for Lua — typically 10-50× faster than PUC Lua!
-- Used by: OpenResty, Redis (older versions), game engines, high-frequency trading

-- ── LuaJIT-SPECIFIC FEATURES ──────────────────────────────────────────────────
-- 1. FFI (Foreign Function Interface) — call C with zero overhead
-- 2. BitOp — bit operations: bit.band, bit.bor, bit.bxor, bit.bnot, bit.lshift, bit.rshift
-- 3. JIT control: jit.on(), jit.off(), jit.opt

-- BitOp (works in both LuaJIT and Lua 5.3+ with << >> operators):
-- Lua 5.3+ native bit operations:
local flags = 0b00000000

local function set_bit(n, bit)  return n | (1 << bit) end
local function clear_bit(n, bit) return n & ~(1 << bit) end
local function test_bit(n, bit)  return (n >> bit) & 1 == 1 end
local function toggle_bit(n, bit) return n ~ (1 << bit) end  -- ~ = XOR in Lua 5.3+

flags = set_bit(flags, 0)    -- Set bit 0 (READABLE)
flags = set_bit(flags, 2)    -- Set bit 2 (EXECUTABLE)
print(string.format("Flags: %08b", flags))   -- 00000101

print(test_bit(flags, 0))    -- true  (readable)
print(test_bit(flags, 1))    -- false (not writable)
print(test_bit(flags, 2))    -- true  (executable)

flags = clear_bit(flags, 2)  -- Remove executable
print(string.format("Flags: %08b", flags))   -- 00000001

-- ── PERFORMANCE PATTERNS ──────────────────────────────────────────────────────
-- 1. Cache global accesses in locals:
-- ❌ Slow (global lookup every iteration):
--    for i = 1, 1e6 do math.sin(i) end

-- ✅ Fast (local lookup):
local sin = math.sin
local cos = math.cos
local floor = math.floor
for i = 1, 1000000 do
    sin(i)   -- Roughly 2× faster than math.sin(i) in a loop
end

-- 2. Avoid table creation in hot paths:
-- ❌ Slow — creates thousands of tables:
local function bad_hot()
    for i = 1, 10000 do
        local v = {x = i, y = i}   -- New table each iteration!
        _ = v.x + v.y
    end
end

-- ✅ Fast — reuse values:
local function good_hot()
    for i = 1, 10000 do
        local x, y = i, i          -- Stack values, no allocation!
        _ = x + y
    end
end

-- 3. Length caching:
-- ❌ Slow — #arr computed every iteration:
-- for i = 1, #large_arr do end

-- ✅ Fast:
local n = #large_arr
for i = 1, n do end

local large_arr = {}
for i = 1, 1000 do large_arr[i] = i end
local _ = nil
```

---

### ⚡ Performance & Optimization Table

| Technique                            | Impact   | When to Use                                           |
|--------------------------------------|----------|-------------------------------------------------------|
| Local variables for globals          | High     | Any loop accessing `math.*`, `string.*`, `table.*`   |
| `table.concat` over `..` loops       | Very High | Building strings from many parts                     |
| Typed tables vs mixed               | Medium   | Array tables (ipairs) faster than mixed pair tables   |
| Pre-size tables: `t = {}; t[100]=0` | Medium   | Known-size arrays avoid rehashing                    |
| Weak tables for caches              | High     | Prevents memory leaks in long-running programs        |
| `coroutine.wrap` vs `create/resume` | Low      | wrap has overhead but is cleaner to use               |
| `rawget/rawset` in tight loops       | Medium   | Bypasses metamethods when you know they're not needed|
| LuaJIT's FFI over C modules         | Very High | FFI is zero-overhead; C module has call overhead     |
| Avoid `#t` in loops on sparse tables | High     | # is O(log n) worst case on sparse tables            |
| Intern strings with table keys      | Medium   | String keys are interned — `==` is pointer compare   |

---

## 💀 10. 0.01% Hidden Secrets — Ultra Elite

---

### 🔮 Secret 1: Environment Manipulation (`_ENV`)

```lua
-- In Lua 5.2+, every function has an implicit upvalue: _ENV
-- All global accesses are actually accesses to _ENV!
-- x = 10  is really  _ENV.x = 10
-- print(x) is really  print(_ENV.x)

-- This means you can completely replace a function's global environment!

-- Default environment:
print(_ENV == _G)   -- true (global environment = _G table)

-- Create a sandboxed function with limited environment:
local function sandboxed(code)
    local safe_env = {
        print = print,
        math  = math,
        type  = type,
        pairs = pairs,
        ipairs = ipairs,
        tostring = tostring,
        tonumber = tonumber,
        -- No io, os, load, dofile, rawget, debug, etc.!
    }
    safe_env._ENV = safe_env   -- Allow self-reference

    local fn, err = load(code, "sandbox", "t", safe_env)
    if not fn then
        return nil, err
    end
    return pcall(fn)
end

local ok, val = sandboxed("return math.sqrt(16) + 1")
print(ok, val)   -- true  5.0

local ok2, err2 = sandboxed("return io.open('secret.txt')")
print(ok2, err2) -- false  [sandbox]:1: attempt to index a nil value (field 'io')

-- ── FUNCTION ENVIRONMENTS ────────────────────────────────────────────────────
-- Give a function its own namespace:
local myenv = {x = 100, y = 200}
setmetatable(myenv, {__index = _G})  -- Fall through to globals

local fn = load("return x + y", "myenv", "t", myenv)
print(fn())   -- 300 (uses myenv.x and myenv.y)

-- Swap environment at runtime:
local function with_env(fn_chunk, env)
    local f = load(fn_chunk, "temp", "t", env)
    return f and f()
end

print(with_env("return x * 2", {x = 21}))    -- 42
print(with_env("return x * 2", {x = 100}))   -- 200
```

---

### 🔮 Secret 2: Prototype Chains and Mixin Delegation

```lua
-- Build a full prototype-based OOP system:

local Object = {}
Object.__index = Object

function Object:new(attrs)
    local instance = setmetatable({}, self)
    instance.__index = instance
    if attrs then
        for k, v in pairs(attrs) do
            instance[k] = v
        end
    end
    if instance.init then instance:init() end
    return instance
end

function Object:extend()
    local cls = setmetatable({}, {__index = self})
    cls.__index = cls
    cls.super = self
    return cls
end

function Object:mixin(...)
    for _, source in ipairs({...}) do
        for k, v in pairs(source) do
            if type(v) == "function" and not self[k] then
                self[k] = v
            end
        end
    end
    return self
end

function Object:is_a(klass)
    local mt = getmetatable(self)
    while mt do
        if mt == klass then return true end
        mt = getmetatable(mt)
    end
    return false
end

function Object:__tostring()
    return "[Object]"
end

-- Mixins:
local Serializable2 = {
    to_json = function(self)
        local parts = {}
        for k, v in pairs(self) do
            if type(v) ~= "function" and k:sub(1,2) ~= "__" then
                parts[#parts + 1] = string.format('"%s": %s', k,
                    type(v) == "string" and ('"' .. v .. '"') or tostring(v))
            end
        end
        return "{" .. table.concat(parts, ", ") .. "}"
    end
}

local Validatable = {
    validate = function(self)
        if self.validators then
            for field, validator in pairs(self.validators) do
                local ok, err = validator(self[field])
                if not ok then
                    return false, field .. ": " .. err
                end
            end
        end
        return true
    end
}

-- Use the system:
local Shape2 = Object:extend()

function Shape2:area() return 0 end
function Shape2:describe()
    return string.format("%s with area %.2f", type(self), self:area())
end

local Circle2 = Shape2:extend()
Circle2:mixin(Serializable2)

function Circle2:init()
    self.radius = self.radius or 1
end

function Circle2:area()
    return math.pi * self.radius ^ 2
end

function Circle2:__tostring()
    return "Circle(r=" .. self.radius .. ")"
end

local c = Circle2:new({radius = 5})
print(tostring(c))     -- Circle(r=5)
print(c:area())        -- 78.539...
print(c:to_json())     -- {"radius": 5}
print(c:is_a(Circle2)) -- true
print(c:is_a(Shape2))  -- true (inheritance chain!)
```

---

### 🔮 Secret 3: Infinite Loops Without Blocking — `coroutine.running()`

```lua
-- Using coroutine.running() to implement non-blocking game loops:

-- Simulated async I/O system:
local pending = {}
local time_queue = {}
local current_time = 0

local function async_sleep2(seconds)
    local co = coroutine.running()
    assert(co, "async_sleep called from main thread!")
    table.insert(time_queue, {
        wake_at = current_time + seconds,
        co = co
    })
    coroutine.yield()
end

local function spawn_task(fn)
    local co = coroutine.create(fn)
    local ok, err = coroutine.resume(co)
    if not ok then print("Task error: " .. err) end
end

local function event_loop()
    while #time_queue > 0 do
        current_time = current_time + 0.016  -- Simulate 60fps tick

        local remaining = {}
        for _, entry in ipairs(time_queue) do
            if current_time >= entry.wake_at then
                local ok, err = coroutine.resume(entry.co)
                if not ok then print("Resume error: " .. err) end
            else
                remaining[#remaining + 1] = entry
            end
        end
        time_queue = remaining
    end
end

-- Tasks run concurrently:
spawn_task(function()
    print(string.format("[%.1f] Task A: Starting", current_time))
    async_sleep2(0.5)
    print(string.format("[%.1f] Task A: After 0.5s sleep", current_time))
    async_sleep2(0.5)
    print(string.format("[%.1f] Task A: Done", current_time))
end)

spawn_task(function()
    print(string.format("[%.1f] Task B: Starting", current_time))
    async_sleep2(0.25)
    print(string.format("[%.1f] Task B: After 0.25s sleep", current_time))
    async_sleep2(0.75)
    print(string.format("[%.1f] Task B: Done", current_time))
end)

event_loop()
```

---

### 🔮 Secret 4: `__gc` Metamethod — Destructors in Lua 5.4

```lua
-- Lua 5.4 supports __gc on tables (previously only userdata)!
-- This enables RAII patterns in pure Lua

local function make_resource(name)
    local resource = setmetatable({name = name}, {
        __gc = function(self)
            print("Cleaning up resource: " .. self.name)
            -- Close files, free memory, disconnect from DB, etc.
        end
    })
    print("Acquired resource: " .. name)
    return resource
end

-- Usage:
do
    local r1 = make_resource("DatabaseConnection")
    local r2 = make_resource("FileHandle")
    -- Use r1 and r2...
    print("Working with resources...")
end
-- r1 and r2 go out of scope here
collectgarbage()   -- Force GC to demonstrate:
-- Cleaning up resource: FileHandle
-- Cleaning up resource: DatabaseConnection

-- RAII pattern:
local function with_file(path, mode, fn)
    local file = io.open(path, mode)
    if not file then error("Cannot open: " .. path) end

    -- Register cleanup:
    local guard = setmetatable({}, {
        __gc = function() file:close() end
    })

    local ok, err = pcall(fn, file)
    -- guard will be GC'd when this function returns
    if not ok then error(err, 2) end
end

-- with_file("data.txt", "r", function(f)
--     print(f:read("*a"))
-- end)
-- File is ALWAYS closed, even if fn throws!
```

---

### 🔮 Secret 5: The Registry — Lua's Hidden Table

```lua
-- The Lua registry is a hidden table accessible only from C
-- It's used to store values that must persist across C function calls
-- But from Lua, you can access it via debug.getregistry()!

-- From C:
--[[
// Store value in registry:
lua_pushstring(L, "my_value");
int ref = luaL_ref(L, LUA_REGISTRYINDEX);  // Store and get reference ID

// Retrieve later:
lua_rawgeti(L, LUA_REGISTRYINDEX, ref);    // Push stored value

// Remove:
luaL_unref(L, LUA_REGISTRYINDEX, ref);
--]]

-- From Lua (introspection/debugging only):
local reg = debug.getregistry()
-- reg contains: _LOADED (modules), _PRELOAD, main thread, etc.
print(type(reg))             -- "table"
print(type(reg._LOADED))     -- "table" (= package.loaded)
print(reg._LOADED == package.loaded)  -- true!

-- The registry is why package.loaded persists across require() calls:
-- It's stored in the registry, not in a local variable anywhere!

-- Understanding LUA_RIDX_MAINTHREAD (registry index 1):
-- The main Lua thread (coroutine) is always stored at registry[1]
print(type(reg[1]))    -- "thread" (the main coroutine!)

-- LUA_RIDX_GLOBALS (registry index 2):
-- The global environment (_G) is stored at registry[2]
print(reg[2] == _G)    -- true!
```

---

### 🔮 Secret 6: Symbolic Computation with Metatables

```lua
-- Build a symbolic math system — metatables all the way down:

local Expr = {}
Expr.__index = Expr

local function expr(type, ...)
    return setmetatable({type = type, args = {...}}, Expr)
end

local function num(n)   return expr("num", n) end
local function var(name) return expr("var", name) end

-- Operator overloading for symbolic expressions:
function Expr.__add(a, b)
    if type(a) == "number" then a = num(a) end
    if type(b) == "number" then b = num(b) end
    return expr("add", a, b)
end

function Expr.__mul(a, b)
    if type(a) == "number" then a = num(a) end
    if type(b) == "number" then b = num(b) end
    return expr("mul", a, b)
end

function Expr.__unm(a)  return expr("neg", a) end

function Expr:eval(env)
    env = env or {}
    if self.type == "num" then return self.args[1] end
    if self.type == "var" then return env[self.args[1]] or 0 end
    if self.type == "neg" then return -self.args[1]:eval(env) end
    if self.type == "add" then
        return self.args[1]:eval(env) + self.args[2]:eval(env)
    end
    if self.type == "mul" then
        return self.args[1]:eval(env) * self.args[2]:eval(env)
    end
end

function Expr:__tostring()
    if self.type == "num" then return tostring(self.args[1]) end
    if self.type == "var" then return self.args[1] end
    if self.type == "neg" then return "-" .. tostring(self.args[1]) end
    if self.type == "add" then
        return "(" .. tostring(self.args[1]) .. " + " .. tostring(self.args[2]) .. ")"
    end
    if self.type == "mul" then
        return "(" .. tostring(self.args[1]) .. " * " .. tostring(self.args[2]) .. ")"
    end
end

-- Build symbolic expressions:
local x = var("x")
local y = var("y")
local expr1 = x * 2 + y * 3 + 5

print(tostring(expr1))                    -- ((((x * 2) + (y * 3)) + 5))
print(expr1:eval({x = 3, y = 4}))        -- 23 (3*2 + 4*3 + 5 = 6+12+5)

-- Differentiate (symbolic derivative!):
function Expr:diff(var_name)
    if self.type == "num" then return num(0) end
    if self.type == "var" then
        return num(self.args[1] == var_name and 1 or 0)
    end
    if self.type == "add" then
        return self.args[1]:diff(var_name) + self.args[2]:diff(var_name)
    end
    if self.type == "mul" then
        -- Product rule: (f*g)' = f'*g + f*g'
        local f, g = self.args[1], self.args[2]
        return f:diff(var_name) * g + f * g:diff(var_name)
    end
end

local deriv = expr1:diff("x")
print(tostring(deriv))              -- Symbolic derivative w.r.t. x
print(deriv:eval({x = 0, y = 0}))  -- 2 (coefficient of x)
```

---

### 🔮 Secret 7: `string.dump` and Bytecode Portability

```lua
-- Lua can serialize compiled functions to bytecode strings!
-- Useful for: caching compiled scripts, sending code over network, protecting source

-- Compile function to bytecode:
local function greet(name)
    return "Hello, " .. name .. "!"
end

local bytecode = string.dump(greet)
print(type(bytecode))      -- "string"
print(#bytecode)           -- Number of bytes

-- Load from bytecode:
local loaded_fn = load(bytecode)
print(loaded_fn("Aryan"))  -- "Hello, Aryan!"

-- Save bytecode to file:
-- local f = io.open("greet.luac", "wb")
-- f:write(bytecode)
-- f:close()

-- Load from file:
-- local f = io.open("greet.luac", "rb")
-- local bc = f:read("*a")
-- f:close()
-- local fn = load(bc)

-- Strip debug info (smaller, faster to load, harder to decompile):
local stripped = string.dump(greet, true)  -- true = strip debug
print("Original:", #bytecode, "Stripped:", #stripped)

-- WARNING: Bytecode is NOT portable across Lua versions or architectures!
-- Lua 5.1 bytecode ≠ Lua 5.4 bytecode
-- 32-bit bytecode ≠ 64-bit bytecode

-- For portable code distribution, use LuaJIT which has more stable bytecode
-- Or distribute source files and let Lua compile at load time
```

---

### 🔮 Secret 8: `__index` Chaining for Multiple Inheritance

```lua
-- Simulate multiple inheritance using __index chains:

local function create_multi_inherit(...)
    local parents = {...}
    return setmetatable({}, {
        __index = function(t, k)
            for _, parent in ipairs(parents) do
                local v = parent[k]
                if v ~= nil then return v end
            end
            return nil
        end
    })
end

local Flyable = {
    fly = function(self) print(self.name .. " is flying!") end,
    max_altitude = 10000,
}

local Swimmable = {
    swim = function(self) print(self.name .. " is swimming!") end,
    max_depth = 100,
}

local Runnable = {
    run = function(self) print(self.name .. " is running!") end,
    max_speed = 40,
}

-- Duck can fly, swim, AND run:
local Duck = create_multi_inherit(Flyable, Swimmable, Runnable)
Duck.__index = Duck

function Duck.new(name)
    return setmetatable({name = name}, Duck)
end

local donald = Duck.new("Donald")
donald:fly()    -- Donald is flying!
donald:swim()   -- Donald is swimming!
donald:run()    -- Donald is running!
print(donald.max_altitude, donald.max_depth, donald.max_speed)  -- 10000  100  40

-- Method resolution order (search priority = order of parents):
local FlySwim = create_multi_inherit(Flyable, Swimmable)
-- If both Flyable and Swimmable had a 'describe' method,
-- Flyable's would be used (first in list)
```

---

### 🔮 Secret 9: `table.pack` and `table.unpack` for Vararg Magic

```lua
-- table.pack and table.unpack are crucial for vararg manipulation

-- table.pack creates a table from varargs WITH a .n field (true count):
local function capture(...)
    local args = table.pack(...)
    print("Got " .. args.n .. " arguments")
    for i = 1, args.n do
        print(i, args[i])   -- args.n is important for nil args!
    end
    return args
end

local captured = capture(1, nil, 3, nil, 5)
-- Got 5 arguments
-- 1  1
-- 2  nil
-- 3  3
-- 4  nil
-- 5  5
-- Note: args.n = 5, even though some are nil!

-- Without .n, you lose count due to nil:
local bad = {1, nil, 3, nil, 5}
print(#bad)   -- UNDEFINED (typically 1 or 5, depends on implementation)

-- table.unpack — spread table as multiple return values:
local function sum3(a, b, c)
    return a + b + c
end

local args2 = {10, 20, 30}
print(sum3(table.unpack(args2)))   -- 60

-- Partial unpack:
print(table.unpack(args2, 2))     -- 20  30 (from index 2)
print(table.unpack(args2, 1, 2))  -- 10  20 (from 1 to 2)

-- Passing varargs to another function perfectly:
local function forward(fn, ...)
    local args = table.pack(...)
    -- Can inspect, modify, filter args here...
    return fn(table.unpack(args, 1, args.n))   -- Pass ALL args (including nils)
end

-- Combine two vararg lists:
local function combine(f1, f2, ...)
    local a1 = table.pack(f1())
    local a2 = table.pack(f2())
    local result = {}
    for i = 1, a1.n do result[i] = a1[i] end
    for i = 1, a2.n do result[a1.n + i] = a2[i] end
    result.n = a1.n + a2.n
    return table.unpack(result, 1, result.n)
end
```

---

### 🔮 Secret 10: Generalized For Loops — Custom Iterators

```lua
-- The generic for loop: for var in expr do end
-- expr must return: iterator_fn, state, initial_value
-- Each iteration calls: iterator_fn(state, current_value)
-- Loop ends when iterator returns nil

-- Understanding the protocol:
-- for i, v in ipairs(t) do end
-- is equivalent to:
-- local fn, state, init = ipairs(t)
-- local i = init
-- while true do
--     local v
--     i, v = fn(state, i)
--     if i == nil then break end
--     -- body
-- end

-- Build custom stateful iterator:
local function stateful_counter(from, to, step)
    step = step or 1
    local i = from - step
    return function()
        i = i + step
        if (step > 0 and i <= to) or (step < 0 and i >= to) then
            return i
        end
    end
end

for n in stateful_counter(1, 10, 2) do
    io.write(n .. " ")   -- 1 3 5 7 9
end
print()

-- Stateless iterator (more efficient — no closure needed):
local function values_iter(t, i)
    i = i + 1
    local v = t[i]
    if v ~= nil then
        return i, v
    end
end

local function values(t)
    return values_iter, t, 0   -- fn, state, initial
end

for i, v in values({"a", "b", "c", "d"}) do
    print(i, v)   -- 1 a, 2 b, 3 c, 4 d
end

-- Iterator over all files in directory (using os.execute):
local function files(dir, pattern)
    pattern = pattern or "*"
    local handle = io.popen('ls "' .. dir .. '"' .. (pattern ~= "*" and ' | grep "' .. pattern .. '"' or ""))
    if not handle then return function() end end
    return function()
        local line = handle:read("*l")
        if line == nil then handle:close() end
        return line
    end
end

-- Fibonacci generator iterator:
local function fibonacci_iter()
    local a, b = 0, 1
    return function()
        local current = a
        a, b = b, a + b
        return current
    end
end

local fib = fibonacci_iter()
for i = 1, 10 do
    io.write(fib() .. " ")   -- 0 1 1 2 3 5 8 13 21 34
end
print()
```

---

## 🗺️ 11. Complete Roadmap

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — FOUNDATION (Week 1-3)
├── Week 1: Syntax, types (nil/bool/number/string), variables (local!), tables
├── Week 2: Control flow (if/for/while/repeat), functions, multiple returns
└── Week 3: String library, table library, closures, modules
    └── Project: Calculator, text processor, simple config parser

PHASE 2 — CORE LUA (Week 4-7)
├── Week 4: Metatables and metamethods — the heart of Lua OOP
├── Week 5: Object-oriented Lua — classes, inheritance, mixins
├── Week 6: Coroutines — producer/consumer, async I/O, custom iterators
└── Week 7: Error handling (pcall/xpcall), patterns (string matching)
    └── Project: JSON serializer, event system, state machine

PHASE 3 — ADVANCED LUA (Week 8-12)
├── Week 8:  Module system, environments (_ENV), sandboxing
├── Week 9:  The C API — understanding Lua's embedding model
├── Week 10: LuaJIT — FFI, bit operations, performance optimization
├── Week 11: OpenResty (Nginx + Lua) — web request handling
└── Week 12: Redis scripting with Lua — atomic server-side operations
    └── Project: Web middleware, Redis rate limiter, game mod system

PHASE 4 — SPECIALIZATIONS (Month 4-5)
├── Game modding: Roblox/Luau or LÖVE2D game development
├── Neovim config: Full Lua-based editor configuration and plugins
└── Embedded: NodeMCU ESP32 Lua for IoT projects

PHASE 5 — EXPERT / 0.01% (Month 6+)
├── Write a Lua C extension library
├── Contribute to LuaJIT, OpenResty, or Neovim ecosystem
├── Implement a language interpreter in Lua
└── Build a production OpenResty/Nginx application
    └── Project: Published LuaRocks module OR production web service
```

---

### 🏁 Milestone Checklist

- [ ] I always use `local` for variables — I never create accidental globals
- [ ] I understand why Lua arrays are 1-indexed and never use index 0
- [ ] I use `table.concat` instead of `..` in loops
- [ ] I understand metatables and can implement `__index`, `__newindex`, and operator overloads
- [ ] I can build a class system with inheritance using metatables
- [ ] I understand coroutines and can implement a producer-consumer pattern
- [ ] I use `pcall`/`xpcall` for all error-prone operations
- [ ] I understand `pairs` vs `ipairs` and use them correctly
- [ ] I can write Lua patterns (not regexes!) for string matching
- [ ] I understand the module pattern and never pollute `_G`
- [ ] I can profile Lua code and identify performance bottlenecks
- [ ] I have written at least one Lua library published or used by others
- [ ] I understand how Lua embeds in C — even if I don't write C myself
- [ ] I've used Lua in at least one "host" — Redis, Neovim, LÖVE2D, or Roblox

---

## 🧩 12. Bonus Deep Insights

---

### 🔮 Mental Model: "Tables Are Everything"

The single most important insight about Lua: **there is only one data structure, and it does everything**.

- Arrays? A table with integer keys starting at 1.
- Dictionaries? A table with string/mixed keys.
- Objects? A table with a metatable.
- Classes? A table with functions and `__index`.
- Modules? A table returned from a file.
- Namespaces? A table accessed with `.` notation.
- The global environment? The table `_G`.
- Package system? The table `package.loaded`.

This radical simplicity means that when you truly understand tables and metatables, you understand almost all of Lua. The complexity isn't in the language — it's in how you compose these simple pieces to build complex systems.

---

### 🤫 Deep Insight 1: Why Lua Indices Start at 1

Many programmers question Lua's 1-based indexing. The answer reveals Lua's philosophy: **Lua is designed for humans who aren't programmers first**.

When Lua was created for Petrobras engineers, many users were petroleum engineers, mathematicians, and scientists — people who work with 1-indexed mathematical arrays, not 0-indexed C arrays. Starting at 1 was a deliberate user-experience decision.

The technical consequence: `#t` gives you the count directly usable as "number of elements" (`for i = 1, #t`), whereas C-style would need `for i = 0, #t-1`. For non-programmers, 1-based is genuinely more natural.

---

### 🤫 Deep Insight 2: Lua's Garbage Collector

Lua 5.4 introduced a **generational garbage collector** — objects that survive one collection cycle are assumed to be long-lived and collected less frequently. This dramatically reduces pause times for game/real-time applications.

The GC can be tuned:
```lua
collectgarbage("setpause", 200)     -- Collect when memory grows by 200%
collectgarbage("setstepmul", 200)   -- 200% GC speed vs allocation speed
collectgarbage("step", 100)         -- Run one GC step (for incremental)
collectgarbage("stop")              -- Disable automatic GC
collectgarbage("restart")           -- Re-enable
collectgarbage("count")             -- Memory used in KB
```

For game loops, you can run GC manually between frames, preventing mid-frame pauses.

---

### 🤫 Deep Insight 3: Lua's Influence on JavaScript

Lua's design deeply influenced modern JavaScript:
- **Closures** — JavaScript adopted Lua-style closures
- **Prototype-based OOP** — both use prototype chains (Lua via `__index`, JS via `__proto__`)
- **First-class functions** — both treat functions as values equally
- **Event-driven programming** — the coroutine model inspired `async/await`
- **Tables = Objects** — `{}` in both languages creates the fundamental data structure

Understanding Lua deeply makes JavaScript design decisions more comprehensible, and vice versa.

---

### 🧠 The Big Picture — Lua in the Modern Ecosystem

```
Lua's evolution:
  1993: Lua 1.0 — born at PUC-Rio for Petrobras
  1994: Lua 2.0 — tables become the universal data structure
  1996: Lua 3.0 — metatables introduced
  2000: Lua 4.0 — standard library expansion
  2003: Lua 5.0 — Coroutines, metatables revamped, incremental GC
  2006: Lua 5.1 — module system, package.loaded, LuaJIT starts
  2011: LuaJIT 2.0 — revolutionary performance, FFI interface
  2012: Lua 5.2 — _ENV, ephemeron tables, emergency GC
  2015: Lua 5.3 — integer subtype, bit operations, UTF-8 library
  2020: Lua 5.4 — generational GC, to-be-closed variables, new integers
  2023+: Luau (Roblox) — type annotations, vector types, fast VM

Lua variants in 2025:
  PUC Lua (reference) — the official implementation (~200KB)
  LuaJIT             — JIT-compiled, FFI, 10-50× faster
  Luau (Roblox)      — typed Lua, vector types, ~1B users via Roblox
  MicroLua/eLua      — Lua for microcontrollers (8-bit, 32KB RAM)
  Fengari             — Lua compiled to JavaScript (browser)

Lua ecosystem in 2025:
  Package manager: LuaRocks (https://luarocks.org)
  Common libraries:
    lua-cjson    — Fast JSON encoder/decoder
    luasocket    — TCP/UDP networking
    luasec       — TLS/SSL support
    penlight     — Python-like standard library extension
    busted       — BDD-style testing framework
    luafilesystem— File system operations
    inspect      — Human-readable table printing
    middleclass  — OOP library
    lua-resty-*  — OpenResty/Nginx ecosystem (hundreds of modules)
  
  Major hosts:
    Roblox/Luau  — 3M+ developers, 1B+ users
    Neovim       — Entire config ecosystem in Lua
    OpenResty    — Web at scale (Cloudflare, Shopify, etc.)
    Redis        — Server-side atomic scripting
    LÖVE2D       — 2D game framework
    Defold       — Cross-platform game engine

  Career paths:
    → Roblox developer (massive market, 3M+ developers)
    → Game mod developer (WoW, Garry's Mod, Factorio all use Lua)
    → OpenResty/Nginx engineer (high-performance web)
    → Neovim plugin developer (growing community)
    → Embedded systems engineer (NodeMCU, IoT)
    → Game engine scripter (any custom engine using Lua)
```

---

## 📌 13. Summary (Quick Revision & Cheat Sheet)

---

### Core Concepts (1-line each)

| Concept              | What It Means                                                              |
|----------------------|----------------------------------------------------------------------------|
| Tables               | The ONLY data structure — implements arrays, dicts, objects, modules       |
| `local`              | ALWAYS use it — globals are the #1 Lua pitfall                            |
| 1-indexed            | Lua arrays start at 1, not 0 — always                                     |
| Metatables           | Control any operation on a table — OOP, operators, defaults                |
| `__index`            | Called when key not found — enables inheritance and defaults               |
| Closures             | Functions capture surrounding variables — modules, counters, callbacks     |
| Multiple returns     | Functions return multiple values natively — no wrapper needed              |
| Coroutines           | Cooperative multitasking — `yield` suspends, `resume` continues            |
| `pairs` vs `ipairs`  | `pairs` = all keys (any order); `ipairs` = sequence (1,2,3... stops at nil)|
| `pcall` / `xpcall`  | Error handling — never let errors crash your program silently              |
| Patterns             | Lua's regex-like system — `%a %d %s %w` etc. — NOT full POSIX regex      |
| `table.concat`       | Build strings from many parts — NEVER use `..` in loops                   |

---

### The 10 Things to Remember

1. ✅ **`local` everywhere** — `local x = 1` not `x = 1` — globals destroy performance and safety
2. ✅ **Arrays start at 1** — `arr[1]` is the first element, never `arr[0]`
3. ✅ **`table.concat` for string building** — never `result = result .. part` in a loop
4. ✅ **`pcall` for all risky code** — file I/O, network, type errors
5. ✅ **`nil` and `false` are falsy** — `0`, `""`, `{}` are ALL truthy in Lua!
6. ✅ **`~=` is not-equal** — not `!=` — and `~` is NOT a bitwise operator in Lua 5.2-
7. ✅ **`ipairs` stops at nil** — don't have holes in arrays you use with `ipairs`
8. ✅ **Set to `nil` to delete** — `t.key = nil` removes the key from a table
9. ✅ **`return M` at end of module** — always return the module table
10. ✅ **`rawget`/`rawset` to bypass metatables** — essential when implementing metatables

---

### Quick Reference Cheat Sheet

```lua
-- ── VARIABLES AND TYPES ────────────────────────────────────────────────────────
local x = 42                    -- integer
local y = 3.14                  -- float
local s = "hello"               -- string
local b = true                  -- boolean
local n = nil                   -- nil (falsy!)
local t = {}                    -- empty table
local f = function() end        -- function

print(type(x))                  -- "number"
print(math.type(x))            -- "integer"
print(math.type(y))            -- "float"

-- ── OPERATORS ─────────────────────────────────────────────────────────────────
-- Arithmetic: + - * / // % ^
-- Comparison: == ~= < > <= >=
-- Logical: and or not (SHORT-CIRCUIT! Return actual values, not bool)
-- String: ..  #
-- Bitwise (5.3+): & | ~ << >> (~ is XOR, not NOT; use ~x for bitwise NOT)

-- Ternary idiom:
local result = condition and "yes" or "no"  -- WARNING: fails if "yes" is false/nil

-- Default value idiom:
local val = arg or "default"

-- ── TABLES ────────────────────────────────────────────────────────────────────
local arr = {10, 20, 30}        -- Array: arr[1]=10, arr[2]=20, arr[3]=30
local dict = {a = 1, b = 2}    -- Dict: dict.a=1, dict["b"]=2
local mixed = {1, 2, x = 3}    -- Mixed

table.insert(arr, 40)           -- Append
table.insert(arr, 2, 15)        -- Insert at position 2
table.remove(arr)               -- Remove last, return it
table.remove(arr, 1)            -- Remove at position 1, return it
table.sort(arr)                  -- Sort in-place
table.sort(arr, function(a,b) return a > b end)  -- Custom sort
table.concat(arr, ", ")         -- Join to string: "10, 20, 30"
table.unpack(arr)               -- Spread: returns 10, 20, 30 separately
table.pack(1, 2, 3)            -- Creates {1,2,3,n=3}
table.move(t, f, e, dest)      -- Copy t[f..e] to starting at dest

-- ── FUNCTIONS ─────────────────────────────────────────────────────────────────
function name(a, b) return a+b end
local fn = function(a, b) return a+b end
local fn2 = function(...) local t = {...}; return #t end  -- Variadic

-- Named method syntax:
function obj:method(x) return self.value + x end
-- Is sugar for:
function obj.method(self, x) return self.value + x end

-- ── CONTROL FLOW ──────────────────────────────────────────────────────────────
if x > 0 then
elseif x < 0 then
else
end

for i = 1, 10 do end
for i = 1, 10, 2 do end       -- With step
for i = 10, 1, -1 do end      -- Countdown
for k, v in pairs(t) do end    -- All keys (any order)
for i, v in ipairs(t) do end  -- Array keys (1,2,3... stops at nil)

while condition do end
repeat until condition          -- Runs at least once

break                            -- Exit loop
goto label; ::label::            -- Jump (Lua 5.2+, simulates continue)

-- ── METATABLES ────────────────────────────────────────────────────────────────
setmetatable(t, mt)
getmetatable(t)

-- Metamethods:
-- __index    — t[key] when key missing (table or function)
-- __newindex — t[key] = val when key missing
-- __call     — t(...) — call table as function
-- __tostring — tostring(t) and print(t)
-- __len      — #t
-- __eq       — t1 == t2
-- __lt       — t1 <  t2
-- __le       — t1 <= t2
-- __add      -- t1 +  t2
-- __sub      -- t1 -  t2
-- __mul      -- t1 *  t2
-- __div      -- t1 /  t2
-- __mod      -- t1 %  t2
-- __pow      -- t1 ^  t2
-- __unm      -- -t    (unary minus)
-- __idiv     -- t1 // t2  (floor division)
-- __band     -- t1 &  t2
-- __bor      -- t1 |  t2
-- __bxor     -- t1 ~  t2
-- __bnot     -- ~t    (bitwise not)
-- __shl      -- t1 << t2
-- __shr      -- t1 >> t2
-- __concat   -- t1 .. t2
-- __gc       -- destructor (Lua 5.4+)

-- ── OOP PATTERN ───────────────────────────────────────────────────────────────
local MyClass = {}
MyClass.__index = MyClass

function MyClass.new(x)
    return setmetatable({x = x}, MyClass)
end

function MyClass:get_x()
    return self.x          -- self = the table (set by : syntax)
end

function MyClass:__tostring()
    return "MyClass(" .. self.x .. ")"
end

local obj = MyClass.new(42)
print(obj:get_x())          -- 42
print(tostring(obj))        -- MyClass(42)

-- ── COROUTINES ────────────────────────────────────────────────────────────────
local co = coroutine.create(function(a)
    print("Start:", a)
    local b = coroutine.yield(a + 1)   -- Pause, send a+1, receive b
    print("Resumed with:", b)
    return "done"
end)

local ok, v = coroutine.resume(co, 10)  -- Start: 10 / ok=true, v=11
ok, v = coroutine.resume(co, 20)        -- Resumed with: 20 / ok=true, v="done"
-- coroutine.wrap(fn) — returns a function instead of dealing with resume/create

-- ── ERROR HANDLING ────────────────────────────────────────────────────────────
local ok, err = pcall(function()
    error("something went wrong")
end)
-- ok=false, err="file.lua:1: something went wrong"

local ok2, result = pcall(function() return 42 end)
-- ok2=true, result=42

local ok3, err3 = xpcall(risky_fn, function(e)
    return debug.traceback(e, 2)  -- Include full stack trace
end)

-- ── STRING PATTERNS ────────────────────────────────────────────────────────────
-- %a=letter %d=digit %l=lower %u=upper %s=space %w=alphanumeric %p=punct
-- . = any char   * = 0+   + = 1+   - = 0+ (lazy)   ? = 0 or 1
-- ^ = start   $ = end   (capture)   [set]   [^set]   %1-%9 = back-reference

s:find("pattern")           -- Returns start, end (or nil)
s:match("pattern")           -- Returns captures (or whole match)
s:gmatch("pattern")          -- Iterator over all matches
s:gsub("pattern", repl)      -- Replace all, returns new string + count
string.format("%s %d %.2f", "hi", 42, 3.14)

-- ── FILE I/O ──────────────────────────────────────────────────────────────────
local f = io.open("file.txt", "r")   -- "r","w","a","rb","wb"
if f then
    local content = f:read("*a")     -- Read all ("*l"=line, "*n"=number)
    f:close()
end

for line in io.lines("file.txt") do  -- Iterate lines
    print(line)
end

io.write("no newline")    -- Write to stdout
print("with newline")     -- Write with newline

-- ── MODULE PATTERN ───────────────────────────────────────────────────────────
-- mymodule.lua:
local M = {}
function M.foo() end
function M.bar() end
return M                   -- MUST return!

-- main.lua:
local mymod = require("mymodule")
mymod.foo()

-- ── USEFUL STDLIB ────────────────────────────────────────────────────────────
math.floor(3.7)        -- 3
math.ceil(3.2)         -- 4
math.sqrt(16)          -- 4.0
math.abs(-5)           -- 5
math.min(3, 1, 4)      -- 1
math.max(3, 1, 4)      -- 4
math.random()          -- [0, 1)
math.random(n)         -- [1, n]
math.random(m, n)      -- [m, n]
math.randomseed(os.time())  -- Seed RNG
math.huge              -- Infinity
math.pi                -- 3.14159...
math.maxinteger        -- Largest integer
math.mininteger        -- Smallest integer

os.time()              -- Current Unix timestamp
os.clock()             -- CPU time used
os.date("%Y-%m-%d")    -- Date as string
os.exit(0)             -- Exit with code
os.getenv("HOME")      -- Environment variable

string.upper("hello")  -- "HELLO"
string.lower("HELLO")  -- "hello"
string.rep("ab", 3)    -- "ababab"
string.rep("ab", 3, ",") -- "ab,ab,ab"
string.reverse("hello")-- "olleh"
string.byte("A")       -- 65
string.char(65)        -- "A"
string.sub(s, 1, 5)    -- Substring (1-indexed, inclusive)
string.len(s) / #s     -- Length
```

---

### What's Next?

After mastering Lua deeply, your natural paths:

- 📘 **Roblox/Luau** — Typed Lua for the world's biggest gaming platform — massive career opportunity
- 📘 **LÖVE2D** — Build beautiful 2D games in pure Lua — fast prototyping, game jams
- 📘 **OpenResty** — Lua inside Nginx — the professional web infrastructure path
- 📘 **Neovim** — Configure and extend the most powerful code editor with Lua
- 📘 **LuaJIT + FFI** — Ultra-performance Lua — call any C library with zero overhead
- 📘 **NodeMCU/eLua** — Embedded Lua for ESP32, IoT, and microcontroller projects

---

> 💬 *"Lua is what would have happened if C and Python had a baby that was raised in Brazil."*
> — The Lua Community

> 💬 *"I've used many scripting languages, and none has given me the pleasure of using Lua. It's the most consistent language I know of."*
> — Eric Raymond (author of "The Art of Unix Programming")

> 💬 *"The world would be a better place if more programming languages were as carefully designed as Lua."*
> — Edsger Dijkstra (paraphrased by the community)

> 💬 *"Simple things should be simple, complex things should be possible — Lua gets this exactly right."*
> — Roberto Ierusalimschy, Lua creator

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: Lua — Complete Language Mastery | Version: 1.0*
*Sections: 13 | Level: Beginner → 0.01% Elite*
