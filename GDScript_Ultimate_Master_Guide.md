# 🎮 GDScript — The Ultimate Master Guide
### From Zero to 0.01% Expert — Every Concept, Game System, Node Secret & Hidden Power

> 📘 **The most complete GDScript guide ever written — beginner to elite.**
>
> 🎯 *Who is this for?* Anyone who wants to go from knowing nothing about GDScript to **mastering** it — the language that powers Godot Engine, the world's fastest-growing open-source game engine.
> ⏱️ *Time to complete:* Self-paced — days to months
> 🛠️ *What you'll gain:* Every syntax rule, Node pattern, signal system, physics trick, shader link, and 0.01% hidden technique that separates an elite Godot developer from the rest.

---

## Table of Contents

1. [🧠 What is GDScript?](#1-what-is-gdscript-super-simple)
2. [🌍 Why GDScript Exists & Dominates](#2-why-gdscript-exists--dominates)
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

## 🧠 1. What is GDScript? (Super Simple)

### The 12-Year-Old Explanation

Imagine you want to make a video game. You need a way to tell the computer: "When the player presses the jump button, make the character fly up. When they land, play a thud sound. When an enemy touches them, reduce their health." All of that logic is written in a **scripting language**.

**GDScript** is the built-in scripting language of the **Godot Engine** — a completely free and open-source game engine. GDScript was designed specifically for game development. Every feature in the language exists because it makes building games easier. It looks a lot like Python, so it's very readable, but it runs much faster because Godot compiles it when your game starts.

Think of Godot as a LEGO factory, and GDScript is the instruction manual language. The factory gives you pre-built pieces (sprites, physics bodies, cameras, audio players, timers), and GDScript is how you tell those pieces what to do, when to do it, and how to interact with each other.

**Godot 4** (released in 2023) brought a completely rewritten GDScript with much more power — typed variables, lambda functions, first-class signals, and performance improvements. It's the version this guide covers.

### Real-Life Analogy

💡 **Think of it like this:**
A game engine is like a fully-equipped movie studio. The studio provides cameras, lighting rigs, green screens, sound stages, and props. **GDScript is the screenplay** — it tells every actor when to walk, what to say, when to react, and how the scene ends. The studio provides all the infrastructure; the screenplay provides all the intelligence.

Without GDScript, Godot is just a collection of silent, motionless scenes. With GDScript, those scenes come alive: characters move, enemies chase, health bars drain, doors creak open, explosions boom, and game worlds breathe with life.

### One-Line Definition

> **GDScript** is Godot Engine's dynamically typed (optionally statically typed), Python-inspired, built-in scripting language designed for game development — tightly integrated with Godot's node-based architecture, signals system, and scene tree, compiled to bytecode at runtime for high-performance game logic.

---

## 🌍 2. Why GDScript Exists & Dominates

### The Problem It Solved

When Godot was created, game engines used either C++ (powerful but brutally complex for designers and small teams) or JavaScript/Lua (flexible but not designed for game-specific patterns). The Godot team needed a language that:

1. Was simple enough for beginners and designers to learn quickly
2. Was deeply integrated with Godot's scene and node system
3. Had first-class support for game patterns (signals, physics, animation)
4. Compiled fast enough to support hot reloading during development

GDScript solved all four. Its Python-like syntax flattens the learning curve. Its integration with Godot's node system means you call `$Sprite2D.play("idle")` instead of `engine.get_node("Sprite2D").animation_player.play("idle")`. It's game-native by design.

### Where Godot & GDScript Shine in 2025

| Domain                        | What's Being Built                                                         |
|-------------------------------|----------------------------------------------------------------------------|
| 2D Games                      | Platformers, RPGs, bullet hells, puzzle games, metroidvanias              |
| 3D Games                      | First-person games, third-person adventures, racing games, strategy       |
| Mobile Games                  | Android and iOS — single codebase exports to both platforms               |
| Web Games                     | HTML5/WebAssembly exports — browser-playable instantly                   |
| Game Jams                     | #1 engine used in game jams globally — fast prototyping                   |
| Indie Games                   | Thousands of released indie titles — Ex-Astris, Cassette Beasts, etc.    |
| Educational Games             | Godot is #1 in game dev education globally                               |
| Rapid Prototyping             | From idea to playable demo in hours                                       |
| Open Source Games             | Entire source available — moddable community-driven development           |

### Why YOU Should Learn It Deeply

1. **Godot is the fastest-growing game engine in the world** — after Unity's licensing crisis in 2023, Godot's GitHub stars tripled overnight. It's now the developer community's favorite.
2. **GDScript is genuinely easy and deep** — you can write your first game in a day, but the ceiling is extremely high with shader integration, C# scripting, and GDExtension.
3. **Completely free, forever** — no royalties, no subscription, no per-seat licenses. The engine you ship with is free regardless of revenue.
4. **Perfect for AI/ML integration** — Godot + Python AI backends via HTTP or sockets — a growing area.
5. **The community is extraordinarily welcoming** — Godot has the most beginner-friendly game dev community in existence.

---

## 🧱 3. Core Fundamentals (Beginner Level)

> 🎯 *Goal: Build an unshakeable foundation. Every concept here is critical.*

---

### Concept 1: The Godot Editor, Scenes & Nodes — The Foundation

```
Before GDScript, understand Godot's architecture:

SCENE TREE (runtime):
  Root
  ├── Game          ← Scene root node
  │   ├── Player    ← CharacterBody2D
  │   │   ├── Sprite2D
  │   │   ├── CollisionShape2D
  │   │   └── AnimationPlayer
  │   ├── Enemies   ← Node2D (container)
  │   │   ├── Enemy1 (Enemy.tscn instanced)
  │   │   └── Enemy2 (Enemy.tscn instanced)
  │   ├── HUD       ← CanvasLayer
  │   │   ├── HealthBar
  │   │   └── ScoreLabel
  │   └── World     ← TileMapLayer
  └── ...

KEY CONCEPTS:
- Scene: A reusable tree of Nodes saved as a .tscn file
- Node: The basic building block — everything is a Node
- Script: A .gd file attached to a Node, giving it behavior
- Scene Tree: The running hierarchy of all Nodes in your game
```

```gdscript
# ── ATTACHING A SCRIPT TO A NODE ──────────────────────────────────────────────
# In Godot Editor: Select node → Script tab → New Script
# Or: right-click node → Attach Script

# Every script extends a Node type:
extends Node            # Base node — no special features
extends Node2D          # 2D positioned node — has position, rotation, scale
extends Node3D          # 3D positioned node
extends CharacterBody2D # 2D character with physics (most common for players)
extends CharacterBody3D # 3D character with physics
extends Area2D          # Detects overlaps/entries (triggers, hitboxes)
extends RigidBody2D     # Physics-simulated 2D body (bowling balls, ragdolls)
extends StaticBody2D    # Non-moving physics body (walls, platforms)
extends Sprite2D        # Displays a texture (extend to add logic to sprites)
extends Control         # Base for UI elements
extends Label           # Text display
extends Button          # Clickable button

# ── YOUR FIRST SCRIPT ─────────────────────────────────────────────────────────
extends Node2D   # This script is for a Node2D

# Called once when the node enters the scene tree:
func _ready() -> void:
	print("Hello from GDScript!")
	print("My position is: ", position)
	print("My name is: ", name)  # The node's name in the scene tree

# Called every frame (60fps by default):
func _process(delta: float) -> void:
	# delta = time since last frame (usually ~0.016 seconds at 60fps)
	# Use delta to make movement frame-rate independent!
	position.x += 100.0 * delta  # Move 100 pixels per second, not per frame

# Called every physics frame (default 60fps, but separate from _process):
func _physics_process(delta: float) -> void:
	# Use this for physics-related movement (with CharacterBody2D, RigidBody2D)
	pass

# Called when an input event occurs:
func _input(event: InputEvent) -> void:
	if event is InputEventKey:
		print("Key pressed: ", event.keycode)
	if event is InputEventMouseButton:
		print("Mouse clicked at: ", event.position)

# Called for unhandled input (after GUI elements have had a chance):
func _unhandled_input(event: InputEvent) -> void:
	if event.is_action_pressed("jump"):
		print("Jump!")
```

---

### Concept 2: Variables, Types & GDScript's Type System

```gdscript
extends Node

func _ready() -> void:
	# ── BASIC TYPES ──────────────────────────────────────────────────────────
	# GDScript is dynamically typed by default (like Python)
	# BUT you can (and should) add type hints for performance + safety

	# Without type hints (dynamic — flexible but slower):
	var health = 100
	var name_str = "Aryan"
	var is_alive = true
	var speed = 3.14

	# With type hints (static — faster + auto-complete + error detection):
	var hp: int = 100
	var player_name: String = "Aryan"
	var alive: bool = true
	var move_speed: float = 200.0

	# Inferred type (let Godot figure it out from the value):
	var score := 0          # Inferred as int
	var direction := Vector2.ZERO  # Inferred as Vector2

	# ── CONSTANTS ─────────────────────────────────────────────────────────────
	# Constants are set once and never change:
	const MAX_HEALTH: int = 100
	const GRAVITY: float = 980.0
	const PLAYER_NAME: String = "Hero"
	const JUMP_FORCE := -400.0  # Negative because Y is down in 2D

	# ── ALL BUILT-IN TYPES ─────────────────────────────────────────────────
	# Integer:
	var i: int = 42
	var big: int = 1_000_000   # Underscores for readability
	var hex: int = 0xFF        # Hexadecimal = 255
	var binary: int = 0b1010   # Binary = 10

	# Float:
	var f: float = 3.14
	var sci: float = 1.5e10    # Scientific notation

	# Boolean:
	var b: bool = true
	var also: bool = false
	# In GDScript, only null and false are falsy — 0 is truthy!

	# String:
	var s: String = "Hello, World!"
	var multiline: String = """
	This is a
	multiline string
	"""
	# String interpolation:
	var hp2: int = 87
	var msg: String = "Health: %d" % hp2          # Python-style formatting
	var msg2: String = "HP: " + str(hp2)           # Concatenation
	print("Name: %s, HP: %d" % ["Aryan", hp2])   # Multiple values

	# Null:
	var nothing = null  # Represents "no value"

	# ── GODOT'S SPECIAL TYPES (game-specific!) ────────────────────────────
	# Vector2 — 2D position, direction, velocity:
	var pos: Vector2 = Vector2(100.0, 200.0)
	var zero: Vector2 = Vector2.ZERO    # (0, 0)
	var up: Vector2 = Vector2.UP        # (0, -1) — up is negative Y in 2D!
	var right: Vector2 = Vector2.RIGHT  # (1, 0)
	print(pos.x, pos.y)                 # 100.0, 200.0
	print(pos.length())                 # Distance from origin
	print(pos.normalized())             # Direction only, length = 1

	# Vector3 — 3D position:
	var pos3: Vector3 = Vector3(1.0, 2.0, 3.0)
	var up3: Vector3 = Vector3.UP  # (0, 1, 0) — up is +Y in 3D!

	# Color:
	var red: Color = Color.RED
	var custom: Color = Color(1.0, 0.5, 0.0, 1.0)  # RGBA, 0-1 range
	var from_html: Color = Color.html("#FF8800")
	var from_hex: Color = Color.hex(0xFF8800FF)
	print(red.r, red.g, red.b, red.a)  # 1.0, 0.0, 0.0, 1.0

	# Rect2 — 2D rectangle:
	var rect: Rect2 = Rect2(Vector2(10, 10), Vector2(100, 50))
	print(rect.position)   # Vector2(10, 10) — top-left corner
	print(rect.size)       # Vector2(100, 50) — width, height
	print(rect.end)        # Vector2(110, 60) — bottom-right corner
	print(rect.has_point(Vector2(50, 30)))  # true

	# Transform2D — full 2D transformation (position + rotation + scale):
	var t: Transform2D = Transform2D.IDENTITY
	print(t.origin)  # Position: Vector2(0, 0)

	# NodePath — path to a node in the scene tree:
	var path: NodePath = NodePath("Player/Sprite2D")

	# ── TYPE CHECKING AND CONVERSION ─────────────────────────────────────
	var x = 42
	print(typeof(x))              # 2 (TYPE_INT constant)
	print(x is int)               # true
	print(x is float)             # false
	print(str(x))                 # "42" — convert to string
	print(int(3.7))               # 3 — convert to int (truncates)
	print(float(5))               # 5.0 — convert to float
	print(bool(0))                # false
	print(bool(42))               # true
	print(bool(""))               # false (empty string)
	print(bool("hello"))          # true
```

---

### Concept 3: Arrays, Dictionaries & Collections

```gdscript
extends Node

func _ready() -> void:
	# ── ARRAYS ────────────────────────────────────────────────────────────────
	# Ordered, resizable, any type (or typed with Array[Type]):

	var fruits: Array = ["apple", "banana", "cherry"]
	var typed_nums: Array[int] = [1, 2, 3, 4, 5]  # Typed array (Godot 4!)
	var empty: Array[String] = []

	# Access:
	print(fruits[0])        # "apple" — 0-indexed
	print(fruits[-1])       # "cherry" — negative = from end
	print(fruits.size())    # 3
	print(fruits.is_empty()) # false

	# Modification:
	fruits.append("date")              # Add to end
	fruits.push_back("elderberry")    # Same as append
	fruits.push_front("avocado")      # Add to front
	fruits.insert(1, "blueberry")     # Insert at index 1
	fruits.remove_at(0)               # Remove at index
	fruits.erase("banana")            # Remove by value (first occurrence)
	fruits.pop_back()                 # Remove + return last element
	fruits.pop_front()                # Remove + return first element
	fruits.clear()                    # Remove all elements

	# Useful operations:
	var nums := [3, 1, 4, 1, 5, 9, 2, 6]
	nums.sort()                        # [1, 1, 2, 3, 4, 5, 6, 9] in-place
	nums.sort_custom(func(a, b): return a > b)  # Sort descending
	nums.shuffle()                     # Random order
	nums.reverse()                     # Reverse in-place
	print(nums.has(5))                # true — contains?
	print(nums.find(4))               # Index of 4 (or -1)
	print(nums.count(1))              # How many 1s? (2)
	print(nums.slice(1, 4))          # [1, 2, 3] (from index 1 to 4 exclusive)
	print(nums.min())                 # Smallest value
	print(nums.max())                 # Largest value
	print(nums.reduce(func(a, b): return a + b, 0))  # Sum
	var doubled = nums.map(func(n): return n * 2)
	var evens = nums.filter(func(n): return n % 2 == 0)
	var sum_all = nums.reduce(func(acc, n): return acc + n, 0)

	# 2D arrays (array of arrays):
	var matrix: Array = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
	print(matrix[1][2])   # 6

	# Concatenation:
	var a := [1, 2, 3]
	var b := [4, 5, 6]
	var combined := a + b  # [1, 2, 3, 4, 5, 6]
	a.append_array(b)      # Append b to a in-place

	# ── DICTIONARIES ──────────────────────────────────────────────────────────
	# Key-value pairs — keys can be any hashable type:

	var player: Dictionary = {
		"name": "Aryan",
		"health": 100,
		"mana": 50,
		"position": Vector2(100, 200),
		"inventory": ["sword", "shield", "potion"]
	}

	# Access:
	print(player["name"])              # "Aryan"
	print(player.health)              # 100 — dot notation works too!
	print(player.get("gold", 0))      # 0 — default if key missing

	# Modification:
	player["gold"] = 500              # Add/update key
	player.name = "Hero"             # Dot notation update
	player.erase("mana")             # Remove key
	print(player.has("health"))      # true — key exists?
	print(player.has_all(["name", "health"]))  # true — all keys exist?
	print(player.keys())             # Array of all keys
	print(player.values())           # Array of all values
	print(player.size())             # Number of key-value pairs

	# Iterating:
	for key in player:
		print(key, ": ", player[key])

	for key in player.keys():
		print("%s → %s" % [key, player[key]])

	# Merging dictionaries:
	var defaults := {"speed": 200.0, "jump": 400.0, "health": 100}
	var overrides := {"health": 150, "special": true}
	defaults.merge(overrides, true)  # true = overwrite existing keys
	print(defaults)  # {"speed": 200, "jump": 400, "health": 150, "special": true}

	# ── TYPED DICTIONARY (Godot 4.4+) ────────────────────────────────────
	var inventory: Dictionary[String, int] = {
		"arrows": 20,
		"potions": 5,
		"gold": 150
	}

	# ── PACKED ARRAYS — highly optimized for specific types ───────────────
	# These are much faster than Array for bulk numeric data!
	var packed_ints: PackedInt32Array = PackedInt32Array([1, 2, 3, 4, 5])
	var packed_floats: PackedFloat32Array = PackedFloat32Array([1.0, 2.0, 3.0])
	var packed_vectors: PackedVector2Array = PackedVector2Array([
		Vector2(0, 0), Vector2(100, 0), Vector2(100, 100)
	])
	var packed_bytes: PackedByteArray = PackedByteArray([0x48, 0x65, 0x6C])
	# print(packed_bytes.get_string_from_utf8())  # "Hel"

	# Packed arrays are used for:
	# - Polygon vertices
	# - Navigation mesh data
	# - Audio sample data
	# - Tile map data
```

---

### Concept 4: Control Flow

```gdscript
extends Node

func _ready() -> void:
	var score := 750
	var health := 85
	var player_class := "Warrior"

	# ── IF / ELIF / ELSE ──────────────────────────────────────────────────────
	if score >= 1000:
		print("Gold rank!")
	elif score >= 500:
		print("Silver rank!")
	elif score >= 100:
		print("Bronze rank!")
	else:
		print("Unranked")

	# Inline if (ternary-like):
	var status := "alive" if health > 0 else "dead"

	# ── MATCH — GDScript's powerful switch ────────────────────────────────────
	# match is EXHAUSTIVE — if no case matches and no default, nothing happens
	match player_class:
		"Warrior":
			print("Attack: 10, Defense: 8")
		"Mage":
			print("Attack: 15, Defense: 3")
		"Rogue":
			print("Attack: 12, Defense: 5")
		_:  # _ = wildcard/default
			print("Unknown class")

	# match with multiple values:
	var day := "Saturday"
	match day:
		"Saturday", "Sunday":
			print("Weekend!")
		"Monday", "Tuesday", "Wednesday", "Thursday", "Friday":
			print("Weekday")
		_:
			print("Invalid day")

	# match with ranges (using when):
	match score:
		var s when s >= 1000:
			print("Excellent: %d" % s)
		var s when s >= 500:
			print("Good: %d" % s)
		_:
			print("Keep trying: %d" % score)

	# match with arrays (pattern matching!):
	var move := ["jump", "forward"]
	match move:
		["jump", var direction]:
			print("Jumping: ", direction)
		["attack", var target]:
			print("Attacking: ", target)
		[var action]:
			print("Single action: ", action)

	# match with dictionaries:
	var event := {"type": "collision", "damage": 25}
	match event:
		{"type": "collision", "damage": var dmg}:
			print("Hit for %d damage!" % dmg)
		{"type": "pickup", "item": var item}:
			print("Picked up: ", item)

	# ── FOR LOOPS ────────────────────────────────────────────────────────────
	# Range:
	for i in range(5):
		print(i)   # 0, 1, 2, 3, 4

	for i in range(1, 10, 2):  # start, stop, step
		print(i)   # 1, 3, 5, 7, 9

	for i in range(10, 0, -1):  # Countdown
		print(i)   # 10, 9, 8, ..., 1

	# Over array:
	var enemies := ["Goblin", "Orc", "Dragon"]
	for enemy in enemies:
		print("Spawning: ", enemy)

	# Over dictionary:
	var stats := {"str": 10, "dex": 8, "int": 12}
	for stat_name in stats:
		print("%s: %d" % [stat_name, stats[stat_name]])

	# Over string (character by character):
	for char in "Hello":
		print(char)  # H, e, l, l, o

	# ── WHILE LOOPS ──────────────────────────────────────────────────────────
	var ammo := 10
	while ammo > 0:
		print("Shooting! Ammo: ", ammo)
		ammo -= 1

	# ── BREAK AND CONTINUE ────────────────────────────────────────────────────
	for i in range(10):
		if i == 3:
			continue  # Skip iteration 3
		if i == 7:
			break     # Stop at 7
		print(i)      # Prints: 0, 1, 2, 4, 5, 6

	# ── PASS — empty placeholder ───────────────────────────────────────────
	func empty_function() -> void:
		pass  # Does nothing — keeps syntax valid
```

---

### Concept 5: Functions

```gdscript
extends Node

# ── BASIC FUNCTIONS ─────────────────────────────────────────────────────────
func add(a: int, b: int) -> int:
	return a + b

func greet(name: String) -> String:
	return "Hello, %s!" % name

func print_info(player_name: String, score: int = 0) -> void:  # Default params
	print("%s: %d points" % [player_name, score])

# Void return (no return type annotation needed but good practice):
func spawn_enemy(position: Vector2) -> void:
	print("Spawning enemy at: ", position)

# ── MULTIPLE RETURN VALUES (via Array or Dictionary) ──────────────────────
func get_player_stats() -> Dictionary:
	return {"health": 100, "mana": 50, "gold": 250}

func get_minmax(arr: Array[int]) -> Array[int]:
	return [arr.min(), arr.max()]

# ── VARIABLE ARGUMENTS ────────────────────────────────────────────────────
func sum_all(numbers: Array) -> float:
	var total := 0.0
	for n in numbers:
		total += n
	return total

print(sum_all([1, 2, 3, 4, 5]))  # 15.0

# ── FIRST-CLASS FUNCTIONS AND LAMBDAS ─────────────────────────────────────
# Store functions in variables:
var my_func: Callable = greet

# Lambda functions (Godot 4):
var double: Callable = func(n: int) -> int: return n * 2
var add_lambda := func(a: int, b: int) -> int: return a + b

print(double.call(5))       # 10
print(add_lambda.call(3, 4)) # 7

# Passing functions as arguments:
func apply_to_all(arr: Array, f: Callable) -> Array:
	var result := []
	for item in arr:
		result.append(f.call(item))
	return result

var nums := [1, 2, 3, 4, 5]
var doubled := apply_to_all(nums, func(n): return n * 2)
print(doubled)  # [2, 4, 6, 8, 10]

# Using built-in array functional methods:
var evens := nums.filter(func(n): return n % 2 == 0)
var squares := nums.map(func(n): return n * n)
var total := nums.reduce(func(acc, n): return acc + n, 0)

# ── STATIC FUNCTIONS ──────────────────────────────────────────────────────
# Static functions don't need an instance — called on the class itself:
static func lerp_angle(from: float, to: float, t: float) -> float:
	return from + (to - from) * t

# ── RECURSION ────────────────────────────────────────────────────────────
func factorial(n: int) -> int:
	if n <= 1:
		return 1
	return n * factorial(n - 1)

func fibonacci(n: int) -> int:
	if n <= 1:
		return n
	return fibonacci(n - 1) + fibonacci(n - 2)

func _ready() -> void:
	print(add(3, 4))          # 7
	print(greet("Aryan"))     # Hello, Aryan!
	print_info("Player")      # Player: 0 points
	print_info("Boss", 9999)  # Boss: 9999 points
	print(factorial(6))       # 720
```

---

🧪 **Mini Task 1:**
> Create a script that generates a dungeon floor plan as a 2D array. The floor should be 10×10. Walls (`1`) should surround the border, empty space (`0`) fills the interior. Print the map to the console using `#` for walls and `.` for empty space.
> ✅ *Use: nested for loops, 2D arrays, string concatenation*

🧪 **Mini Task 2:**
> Write a function `roll_dice(sides: int, count: int) -> Dictionary` that rolls `count` dice each with `sides` sides, returns a Dictionary with `total`, `average`, and `rolls` (the individual results).
> ✅ *Use: `randi_range()`, arrays, dictionary building*

---

## ⚙️ 4. Complete Language System Breakdown

---

### Part 1: The Node System — Godot's Core Architecture

```gdscript
# ── ACCESSING NODES ──────────────────────────────────────────────────────────
extends Node2D

# Method 1: $ shorthand (most common):
@onready var sprite := $Sprite2D
@onready var anim := $AnimationPlayer
@onready var hitbox := $CollisionShape2D
@onready var hud := $"../HUD"        # Goes up one level, then finds HUD
@onready var health_bar := $"../HUD/HealthBar"

# Method 2: get_node() — same as $:
@onready var sprite2 := get_node("Sprite2D")
@onready var parent_hud := get_node("../HUD/HealthBar")
@onready var absolute := get_node("/root/Game/HUD")  # Absolute path from root

# Method 3: get_node_or_null() — safe, returns null if not found:
@onready var optional_boss := get_node_or_null("Boss")
func _ready() -> void:
	if optional_boss != null:
		print("Boss found!")

# Method 4: find_child() — search entire subtree by name:
@onready var player := find_child("Player", true, false)  # recursive, no owned check

# ── @onready — initialize after scene is ready ────────────────────────────
# @onready means: "assign this when _ready() is called, not at class creation"
# Without @onready, nodes might not exist yet:

# ❌ This CRASHES — node doesn't exist at class creation:
# var sprite = $Sprite2D  # Error! Scene not ready yet

# ✅ This works:
@onready var sprite3 := $Sprite2D

# ── CREATING AND DESTROYING NODES DYNAMICALLY ────────────────────────────
func spawn_bullet(spawn_position: Vector2) -> void:
	# Load a scene file:
	var bullet_scene := preload("res://scenes/bullet.tscn") as PackedScene
	# or: var bullet_scene = load("res://scenes/bullet.tscn") -- loads at runtime

	# Instantiate (create an instance):
	var bullet := bullet_scene.instantiate() as CharacterBody2D

	# Set properties before adding to tree:
	bullet.global_position = spawn_position
	bullet.rotation = rotation  # Face same direction as parent

	# Add to scene tree:
	get_tree().root.add_child(bullet)  # Add to root
	# or: get_parent().add_child(bullet)  # Add as sibling
	# or: add_child(bullet)  # Add as child of this node

func destroy_self() -> void:
	queue_free()  # Safe deletion at end of frame — use this!
	# NEVER call free() during _process — can crash!

# ── NODE LIFECYCLE CALLBACKS ─────────────────────────────────────────────
func _init() -> void:
	# Called when node is created (before entering scene tree)
	# Don't access other nodes here — they're not ready!
	pass

func _ready() -> void:
	# Called when node AND all children have entered scene tree
	# Best place to set up, connect signals, get node references
	print("All nodes ready!")

func _enter_tree() -> void:
	# Called when node first enters the scene tree
	pass

func _exit_tree() -> void:
	# Called when node is removed from scene tree (before queue_free())
	# Good for cleanup: disconnecting signals, saving data
	pass

func _notification(what: int) -> void:
	# Called for various engine notifications
	match what:
		NOTIFICATION_READY:
			pass  # Same as _ready()
		NOTIFICATION_PROCESS:
			pass  # Same as _process() (if enabled)
		NOTIFICATION_VISIBILITY_CHANGED:
			print("Visibility changed to: ", visible)
		NOTIFICATION_PREDELETE:
			print("About to be deleted!")

# ── SCENE MANAGEMENT ──────────────────────────────────────────────────────
func change_to_game_scene() -> void:
	get_tree().change_scene_to_file("res://scenes/game.tscn")

func change_scene_packed() -> void:
	var new_scene := preload("res://scenes/game.tscn") as PackedScene
	get_tree().change_scene_to_packed(new_scene)

func reload_scene() -> void:
	get_tree().reload_current_scene()

func quit_game() -> void:
	get_tree().quit()

# Pause the game:
func pause_game() -> void:
	get_tree().paused = true

func resume_game() -> void:
	get_tree().paused = false

# Nodes can be set to process during pause:
# In Godot Editor: Node → Process Mode → Always / When Paused
# Or in code:
func _ready2() -> void:
	process_mode = Node.PROCESS_MODE_ALWAYS  # Always process, even when paused
```

---

### Part 2: Signals — GDScript's Event System

```gdscript
# Signals are GDScript's pub-sub event system
# They decouple nodes — senders don't need to know who's listening

# ── DEFINING SIGNALS ──────────────────────────────────────────────────────────
extends CharacterBody2D

# Simple signal (no data):
signal jumped

# Signals with data:
signal health_changed(new_health: int, old_health: int)
signal item_collected(item_name: String, position: Vector2)
signal enemy_died(enemy_type: String, loot: Array)
signal player_level_up(new_level: int, stats: Dictionary)

# ── EMITTING SIGNALS ──────────────────────────────────────────────────────────
var health: int = 100:
	set(value):
		var old_health := health
		health = clamp(value, 0, max_health)
		health_changed.emit(health, old_health)  # Emit with data
		if health <= 0:
			died.emit()

signal died
var max_health: int = 100

func jump() -> void:
	velocity.y = -400.0
	jumped.emit()  # Emit signal

func collect_item(item: Node) -> void:
	item_collected.emit(item.item_name, item.global_position)
	item.queue_free()

# ── CONNECTING SIGNALS IN CODE ────────────────────────────────────────────────
extends Node  # HUD or GameManager script

@onready var player := $Player
@onready var health_bar := $HealthBar
@onready var score_label := $ScoreLabel

func _ready() -> void:
	# Connect signal to a method:
	player.health_changed.connect(_on_player_health_changed)
	player.jumped.connect(_on_player_jumped)
	player.died.connect(_on_player_died)

	# Connect with lambda (inline handler):
	player.item_collected.connect(
		func(item_name: String, pos: Vector2) -> void:
			print("Collected %s at %s" % [item_name, pos])
			score_label.text = "Items: " + str(items_count)
	)

	# One-shot signal (auto-disconnects after first call):
	player.died.connect(_on_player_died_once, CONNECT_ONE_SHOT)

	# Deferred connection (handler called at end of frame, not immediately):
	player.health_changed.connect(_on_health_changed_deferred, CONNECT_DEFERRED)

var items_count := 0

func _on_player_health_changed(new_hp: int, old_hp: int) -> void:
	health_bar.value = new_hp
	if new_hp < old_hp:
		print("Player took %d damage!" % (old_hp - new_hp))

func _on_player_jumped() -> void:
	print("Player jumped!")

func _on_player_died() -> void:
	print("Game Over!")
	get_tree().change_scene_to_file("res://scenes/game_over.tscn")

func _on_player_died_once() -> void:
	print("Dies only once!")

func _on_health_changed_deferred(new_hp: int, old_hp: int) -> void:
	print("Deferred: health is now %d" % new_hp)

# ── DISCONNECTING SIGNALS ─────────────────────────────────────────────────────
func cleanup() -> void:
	if player.health_changed.is_connected(_on_player_health_changed):
		player.health_changed.disconnect(_on_player_health_changed)

# ── AWAITING SIGNALS — async programming! ────────────────────────────────────
func play_death_sequence() -> void:
	print("Playing death animation...")
	$AnimationPlayer.play("death")

	# Wait for animation to finish before continuing:
	await $AnimationPlayer.animation_finished

	print("Animation done! Showing game over screen.")
	$GameOverScreen.show()

	# Wait for a signal from HUD:
	await $GameOverScreen.retry_pressed

	print("Restarting game!")
	get_tree().reload_current_scene()

func countdown(seconds: int) -> void:
	for i in range(seconds, 0, -1):
		$TimerLabel.text = str(i)
		await get_tree().create_timer(1.0).timeout  # Wait 1 second
	$TimerLabel.text = "GO!"

# ── BUILT-IN GODOT SIGNALS ────────────────────────────────────────────────────
# Area2D / Area3D:
# body_entered(body: Node2D)   — physics body entered
# body_exited(body: Node2D)    — physics body left
# area_entered(area: Area2D)   — another area entered
# area_exited(area: Area2D)    — another area left

# AnimationPlayer:
# animation_finished(anim_name: String)
# animation_started(anim_name: String)

# Timer:
# timeout()  — timer ran out

# Button:
# pressed()
# toggled(button_pressed: bool)

# SceneTree:
# process_frame()         — emitted every frame
# physics_frame()         — emitted every physics frame
# scene_changed(new_scene) — when scene changes
```

---

### Part 3: Object-Oriented Programming in GDScript

```gdscript
# ── CLASS BASICS ──────────────────────────────────────────────────────────────
class_name Item  # Makes this class available globally by name!
extends Resource  # Or Node, or any Godot class

# @export makes variables editable in the Godot Inspector!
@export var item_name: String = "Unknown Item"
@export var description: String = ""
@export var value: int = 0
@export var icon: Texture2D
@export_enum("Weapon", "Armor", "Consumable", "Quest") var category: int = 0
@export_range(0, 100) var weight: float = 1.0

# Private by convention (no enforcement — use _ prefix):
var _internal_id: int = 0
static var _item_count: int = 0  # Shared across all instances

# Constant:
const MAX_STACK_SIZE: int = 99

func _init(p_name: String = "", p_value: int = 0) -> void:
	item_name = p_name
	value = p_value
	_item_count += 1
	_internal_id = _item_count

func use() -> void:
	print("Used: %s" % item_name)

func get_info() -> String:
	return "%s (worth %d gold)" % [item_name, value]

static func get_total_items() -> int:
	return _item_count

# ── INHERITANCE ───────────────────────────────────────────────────────────────
class_name Weapon
extends Item

@export var damage: int = 10
@export var attack_speed: float = 1.0
@export_enum("Slash", "Pierce", "Blunt") var damage_type: int = 0

func _init(p_name: String = "", p_value: int = 0, p_damage: int = 10) -> void:
	super._init(p_name, p_value)  # Call parent _init!
	damage = p_damage

func attack(target: Node) -> int:
	print("Attacking %s with %s for %d damage!" % [target.name, item_name, damage])
	return damage

# Override parent method:
override func use() -> void:
	print("Equipping weapon: %s" % item_name)
	# Call parent's use() too:
	# super.use()

# ── INNER CLASSES ─────────────────────────────────────────────────────────────
class Inventory:
	var items: Array[Item] = []
	var max_slots: int = 20

	func add_item(item: Item) -> bool:
		if items.size() >= max_slots:
			return false
		items.append(item)
		return true

	func remove_item(item_name: String) -> Item:
		for i in items.size():
			if items[i].item_name == item_name:
				var item := items[i]
				items.remove_at(i)
				return item
		return null

	func get_total_value() -> int:
		return items.reduce(func(acc, item): return acc + item.value, 0)

# ── PROPERTIES WITH GETTER/SETTER ────────────────────────────────────────────
extends Node

var _health: int = 100
var health: int:
	get:
		return _health
	set(value):
		var old := _health
		_health = clamp(value, 0, max_health)
		if _health != old:
			health_changed.emit(_health, old)
		if _health <= 0:
			_die()

signal health_changed(new_hp: int, old_hp: int)
var max_health: int = 100

# Computed property (getter only):
var is_dead: bool:
	get:
		return health <= 0

var health_percent: float:
	get:
		return float(health) / float(max_health)

func _die() -> void:
	print("Player died!")

# ── STATIC CLASSES ────────────────────────────────────────────────────────────
# A class with all static members — like a utility/helper class:
class_name MathHelper
extends RefCounted  # Lightweight — no Node overhead

static func clamp_angle(angle: float) -> float:
	return fmod(angle + PI, TAU) - PI

static func lerp_unclamped(a: float, b: float, t: float) -> float:
	return a + (b - a) * t

static func random_point_in_circle(radius: float) -> Vector2:
	var angle := randf() * TAU
	var dist := sqrt(randf()) * radius
	return Vector2(cos(angle), sin(angle)) * dist

static func screen_shake(camera: Camera2D, strength: float, duration: float) -> void:
	var tween := camera.create_tween()
	for i in int(duration * 60):
		var offset := MathHelper.random_point_in_circle(strength)
		tween.tween_property(camera, "offset", offset, 1.0 / 60.0)
	tween.tween_property(camera, "offset", Vector2.ZERO, 0.1)
```

---

### Part 4: Input Handling

```gdscript
extends CharacterBody2D

# ── INPUT MAP — define actions in Project → Input Map ─────────────────────────
# Action names: "move_left", "move_right", "jump", "attack", "pause"

func _process(delta: float) -> void:
	# ── DIGITAL INPUT (pressed/released) ────────────────────────────────────
	if Input.is_action_just_pressed("jump"):
		# True ONLY on the frame the button is first pressed
		print("Jump started!")

	if Input.is_action_pressed("attack"):
		# True every frame while button is held
		print("Attacking...")

	if Input.is_action_just_released("attack"):
		# True ONLY on the frame the button is released
		print("Attack ended!")

	# Check specific keys:
	if Input.is_key_pressed(KEY_SPACE):
		print("Space held!")

	# Check specific mouse buttons:
	if Input.is_mouse_button_pressed(MOUSE_BUTTON_LEFT):
		print("Left click held!")

	# ── ANALOG INPUT (returns -1 to 1 float) ─────────────────────────────
	var move_x := Input.get_axis("move_left", "move_right")  # -1 to 1
	var move_y := Input.get_axis("move_up", "move_down")
	var movement := Vector2(move_x, move_y)

	# Gamepad axis:
	var gamepad_dir := Input.get_vector("move_left", "move_right", "move_up", "move_down")
	# Returns a Vector2 — automatically normalized if both axes pushed!

	# ── MOVEMENT WITH INPUT ──────────────────────────────────────────────
	var direction := Input.get_vector("move_left", "move_right", "move_up", "move_down")
	velocity = direction * 200.0
	move_and_slide()

	# ── MOUSE POSITION ──────────────────────────────────────────────────
	var mouse_pos := get_global_mouse_position()  # World position
	var mouse_screen := get_viewport().get_mouse_position()  # Screen position
	var angle_to_mouse := global_position.angle_to_point(mouse_pos)
	rotation = angle_to_mouse  # Face the mouse!

func _input(event: InputEvent) -> void:
	# ── HANDLING INPUT EVENTS ─────────────────────────────────────────────
	if event is InputEventKey:
		var key_event := event as InputEventKey
		if key_event.pressed and key_event.keycode == KEY_ESCAPE:
			get_tree().quit()

	if event is InputEventMouseButton:
		var mb := event as InputEventMouseButton
		if mb.pressed and mb.button_index == MOUSE_BUTTON_LEFT:
			print("Clicked at: ", mb.position)

	if event is InputEventMouseMotion:
		var mm := event as InputEventMouseMotion
		print("Mouse moved by: ", mm.relative)

	if event is InputEventJoypadButton:
		var joy := event as InputEventJoypadButton
		if joy.pressed:
			print("Gamepad button: ", joy.button_index)

	if event is InputEventJoypadMotion:
		var axis := event as InputEventJoypadMotion
		print("Gamepad axis %d: %f" % [axis.axis, axis.axis_value])

	# Check action (works for keyboard, gamepad, mouse — uses Input Map):
	if event.is_action_pressed("pause"):
		get_tree().paused = !get_tree().paused
		get_viewport().set_input_as_handled()  # Prevent event from propagating further

# ── CURSOR CONTROL ────────────────────────────────────────────────────────────
func setup_cursor() -> void:
	Input.set_mouse_mode(Input.MOUSE_MODE_HIDDEN)     # Hide cursor
	Input.set_mouse_mode(Input.MOUSE_MODE_CAPTURED)   # FPS: capture + hide
	Input.set_mouse_mode(Input.MOUSE_MODE_CONFINED)   # Keep within window
	Input.set_mouse_mode(Input.MOUSE_MODE_VISIBLE)    # Show (default)
	Input.warp_mouse(Vector2(400, 300))               # Move cursor position

# ── VIBRATION (Gamepad) ────────────────────────────────────────────────────
func rumble(device_id: int = 0) -> void:
	Input.start_joy_vibration(device_id, 0.5, 0.5, 0.3)  # weak, strong, duration
```

---

### 📊 Full GDScript System Overview Table

| Feature              | GDScript Mechanism                           | Key Insight                                            |
|----------------------|----------------------------------------------|--------------------------------------------------------|
| Node system          | Tree of Node objects — scene hierarchy       | Everything is a Node — the core of Godot's architecture|
| Signals              | Built-in event system — emit/connect         | Decouple game systems — no tight coupling needed       |
| @export              | Inspector-editable properties                | Design-time configuration without code changes         |
| @onready             | Node references initialized at _ready()      | Safe node access — prevents null reference errors      |
| Type hints           | Optional static typing `: Type`              | Better performance + autocompletion + error detection  |
| Physics              | _physics_process + move_and_slide()          | Frame-rate independent physics movement               |
| Tweens               | create_tween() API                           | Smooth animations without AnimationPlayer             |
| await                | Async signal/timer waiting                   | Sequential async code without callbacks               |
| PackedScene          | preload/load + instantiate()                 | Dynamic object spawning — bullets, enemies, effects   |
| match                | Pattern matching switch                       | More powerful than if/elif — handles types, arrays    |

---

## 🔄 5. Real-World Workflow

---

### 🟢 Beginner Workflow: Complete Platformer Player

```gdscript
# player.gd — A complete 2D platformer character controller
class_name Player
extends CharacterBody2D

# ── EXPORTED PROPERTIES (editable in Inspector) ────────────────────────────
@export_group("Movement")
@export var move_speed: float = 200.0
@export var acceleration: float = 800.0
@export var friction: float = 600.0
@export var air_friction: float = 200.0

@export_group("Jump")
@export var jump_velocity: float = -450.0
@export var jump_hold_force: float = -200.0
@export var max_jump_hold_time: float = 0.2
@export var fall_gravity_multiplier: float = 2.5
@export var coyote_time: float = 0.12
@export var jump_buffer_time: float = 0.15

@export_group("Stats")
@export var max_health: int = 3
@export var invincibility_time: float = 1.5

# ── SIGNALS ───────────────────────────────────────────────────────────────────
signal health_changed(new_hp: int, max_hp: int)
signal died
signal jumped
signal landed

# ── NODE REFERENCES ──────────────────────────────────────────────────────────
@onready var sprite := $Sprite2D
@onready var anim := $AnimationPlayer
@onready var collision := $CollisionShape2D
@onready var coyote_timer := $CoyoteTimer
@onready var jump_buffer_timer := $JumpBufferTimer
@onready var invincibility_timer := $InvincibilityTimer
@onready var audio_jump := $AudioJump
@onready var audio_land := $AudioLand

# ── STATE VARIABLES ───────────────────────────────────────────────────────────
var health: int:
	get: return _health
	set(value):
		var old := _health
		_health = clamp(value, 0, max_health)
		if _health != old:
			health_changed.emit(_health, max_health)
		if _health <= 0 and old > 0:
			_die()

var _health: int = max_health
var _is_dead: bool = false
var _is_invincible: bool = false
var _was_on_floor: bool = false
var _jump_hold_timer: float = 0.0
var _is_holding_jump: bool = false

# ── GODOT BUILT-IN GRAVITY ────────────────────────────────────────────────────
var gravity: float = ProjectSettings.get_setting("physics/2d/default_gravity")

func _ready() -> void:
	_health = max_health
	invincibility_timer.wait_time = invincibility_time
	invincibility_timer.timeout.connect(_on_invincibility_ended)

func _physics_process(delta: float) -> void:
	if _is_dead:
		return

	_apply_gravity(delta)
	_handle_jump(delta)
	_handle_movement(delta)
	_check_landing()
	_update_animation()

	move_and_slide()
	_was_on_floor = is_on_floor()

func _apply_gravity(delta: float) -> void:
	if not is_on_floor():
		var grav := gravity
		# Faster fall when moving down or releasing jump:
		if velocity.y > 0 or not _is_holding_jump:
			grav *= fall_gravity_multiplier
		velocity.y += grav * delta
	else:
		velocity.y = 0.0
		_jump_hold_timer = 0.0

func _handle_jump(delta: float) -> void:
	# Start coyote time when leaving floor without jumping:
	if _was_on_floor and not is_on_floor() and velocity.y >= 0:
		coyote_timer.start(coyote_time)

	# Buffer jump if pressed slightly before landing:
	if Input.is_action_just_pressed("jump"):
		jump_buffer_timer.start(jump_buffer_time)

	# Actually jump:
	var can_jump := is_on_floor() or not coyote_timer.is_stopped()
	var wants_jump := not jump_buffer_timer.is_stopped()

	if can_jump and wants_jump:
		velocity.y = jump_velocity
		coyote_timer.stop()
		jump_buffer_timer.stop()
		_is_holding_jump = true
		_jump_hold_timer = 0.0
		audio_jump.play()
		jumped.emit()

	# Variable jump height — hold for higher jump:
	if Input.is_action_pressed("jump") and _is_holding_jump:
		_jump_hold_timer += delta
		if _jump_hold_timer < max_jump_hold_time and velocity.y < 0:
			velocity.y += jump_hold_force * delta
	else:
		_is_holding_jump = false

func _handle_movement(delta: float) -> void:
	var direction := Input.get_axis("move_left", "move_right")

	if direction != 0.0:
		# Accelerate in direction:
		velocity.x = move_toward(velocity.x, direction * move_speed, acceleration * delta)
		# Flip sprite:
		sprite.flip_h = direction < 0
	else:
		# Apply friction:
		var fric := friction if is_on_floor() else air_friction
		velocity.x = move_toward(velocity.x, 0.0, fric * delta)

func _check_landing() -> void:
	if is_on_floor() and not _was_on_floor:
		audio_land.play()
		landed.emit()

func _update_animation() -> void:
	if not is_on_floor():
		anim.play("jump" if velocity.y < 0 else "fall")
	elif abs(velocity.x) > 10:
		anim.play("run")
	else:
		anim.play("idle")

# ── DAMAGE SYSTEM ─────────────────────────────────────────────────────────────
func take_damage(amount: int = 1, knockback: Vector2 = Vector2.ZERO) -> void:
	if _is_invincible or _is_dead:
		return

	health -= amount
	velocity += knockback
	_start_invincibility()
	_flash_sprite()

func _start_invincibility() -> void:
	_is_invincible = true
	invincibility_timer.start()

func _on_invincibility_ended() -> void:
	_is_invincible = false
	sprite.modulate.a = 1.0

func _flash_sprite() -> void:
	var tween := create_tween().set_loops(int(invincibility_time * 5))
	tween.tween_property(sprite, "modulate:a", 0.0, 0.1)
	tween.tween_property(sprite, "modulate:a", 1.0, 0.1)

func _die() -> void:
	_is_dead = true
	collision.set_deferred("disabled", true)
	velocity = Vector2.ZERO
	anim.play("death")
	died.emit()
	await anim.animation_finished
	queue_free()

func heal(amount: int) -> void:
	health += amount
```

---

### 🔵 Professional Workflow: Game Manager with State Machine

```gdscript
# game_manager.gd — Global game state and progression manager
class_name GameManager
extends Node

# Autoload singleton — one instance for entire game!
# (Add to Project → Autoloads as "GameManager")

# ── GAME STATE MACHINE ────────────────────────────────────────────────────────
enum GameState {
	MAIN_MENU,
	CUTSCENE,
	PLAYING,
	PAUSED,
	GAME_OVER,
	VICTORY,
	LOADING,
}

var current_state: GameState = GameState.MAIN_MENU:
	set(value):
		var old := current_state
		current_state = value
		_on_state_changed(old, value)
		state_changed.emit(value)

signal state_changed(new_state: GameState)
signal score_changed(new_score: int)
signal level_changed(new_level: int)

# ── PERSISTENT GAME DATA ───────────────────────────────────────────────────────
var score: int = 0:
	set(value):
		score = max(0, value)
		score_changed.emit(score)
		if score > high_score:
			high_score = score

var high_score: int = 0
var current_level: int = 1
var lives: int = 3
var coins_collected: int = 0
var total_play_time: float = 0.0

# Player save data:
var save_data: Dictionary = {}

# ── INITIALIZATION ────────────────────────────────────────────────────────────
func _ready() -> void:
	load_game()
	get_tree().process_frame.connect(_on_process_frame)

func _on_process_frame() -> void:
	if current_state == GameState.PLAYING:
		total_play_time += get_process_delta_time()

# ── STATE TRANSITIONS ─────────────────────────────────────────────────────────
func _on_state_changed(old: GameState, new_state: GameState) -> void:
	print("[GameManager] State: %s → %s" % [
		GameState.keys()[old], GameState.keys()[new_state]
	])

	match new_state:
		GameState.PLAYING:
			get_tree().paused = false
			Input.set_mouse_mode(Input.MOUSE_MODE_HIDDEN)
		GameState.PAUSED:
			get_tree().paused = true
			Input.set_mouse_mode(Input.MOUSE_MODE_VISIBLE)
		GameState.GAME_OVER:
			get_tree().paused = true
			save_game()
		GameState.MAIN_MENU:
			get_tree().paused = false
			score = 0
			lives = 3
			current_level = 1

func start_game() -> void:
	score = 0
	lives = 3
	current_level = 1
	coins_collected = 0
	current_state = GameState.PLAYING
	get_tree().change_scene_to_file("res://scenes/levels/level_1.tscn")

func pause_game() -> void:
	if current_state == GameState.PLAYING:
		current_state = GameState.PAUSED

func resume_game() -> void:
	if current_state == GameState.PAUSED:
		current_state = GameState.PLAYING

func player_died() -> void:
	lives -= 1
	if lives <= 0:
		current_state = GameState.GAME_OVER
	else:
		get_tree().reload_current_scene()

func complete_level() -> void:
	score += 1000 * current_level  # Bonus for completing level
	current_level += 1
	save_game()
	if current_level > MAX_LEVELS:
		current_state = GameState.VICTORY
	else:
		current_state = GameState.LOADING
		_load_next_level()

const MAX_LEVELS: int = 10

func _load_next_level() -> void:
	var level_path := "res://scenes/levels/level_%d.tscn" % current_level
	get_tree().change_scene_to_file(level_path)

# ── SAVE / LOAD SYSTEM ────────────────────────────────────────────────────────
const SAVE_PATH := "user://save_data.json"

func save_game() -> void:
	save_data = {
		"high_score": high_score,
		"current_level": current_level,
		"total_play_time": total_play_time,
		"version": "1.0.0",
	}

	var file := FileAccess.open(SAVE_PATH, FileAccess.WRITE)
	if file:
		file.store_string(JSON.stringify(save_data, "\t"))
		file.close()
		print("[GameManager] Game saved!")
	else:
		printerr("[GameManager] Failed to save game!")

func load_game() -> void:
	if not FileAccess.file_exists(SAVE_PATH):
		print("[GameManager] No save file found, starting fresh.")
		return

	var file := FileAccess.open(SAVE_PATH, FileAccess.READ)
	if file:
		var json := JSON.new()
		var err := json.parse(file.get_as_text())
		file.close()
		if err == OK:
			save_data = json.data
			high_score = save_data.get("high_score", 0)
			total_play_time = save_data.get("total_play_time", 0.0)
			print("[GameManager] Game loaded! High score: %d" % high_score)
		else:
			printerr("[GameManager] Failed to parse save file!")
```

---

## 🧪 6. Hands-on Practice Projects

---

### 🟢 Beginner Project: Top-Down Shooter

```gdscript
# player_topdown.gd — Top-down shooter with shooting mechanic
extends CharacterBody2D

@export var move_speed: float = 250.0
@export var bullet_scene: PackedScene
@export var fire_rate: float = 0.15  # Seconds between shots

@onready var gun_pivot := $GunPivot
@onready var bullet_spawn := $GunPivot/BulletSpawn
@onready var fire_timer := $FireTimer

func _ready() -> void:
	fire_timer.wait_time = fire_rate

func _physics_process(delta: float) -> void:
	# Movement:
	var direction := Input.get_vector("move_left", "move_right", "move_up", "move_down")
	velocity = direction * move_speed
	move_and_slide()

	# Rotate gun toward mouse:
	var mouse_pos := get_global_mouse_position()
	gun_pivot.look_at(mouse_pos)

	# Shooting:
	if Input.is_action_pressed("shoot") and fire_timer.is_stopped():
		_shoot()
		fire_timer.start()

func _shoot() -> void:
	if not bullet_scene:
		push_error("bullet_scene not set!")
		return

	var bullet := bullet_scene.instantiate()
	bullet.global_position = bullet_spawn.global_position
	bullet.rotation = gun_pivot.global_rotation
	get_tree().root.add_child(bullet)
```

```gdscript
# bullet.gd — Bullet behavior
extends Area2D

@export var speed: float = 600.0
@export var damage: int = 1
@export var lifetime: float = 2.0

func _ready() -> void:
	# Auto-destroy after lifetime:
	var timer := get_tree().create_timer(lifetime)
	await timer.timeout
	queue_free()

func _physics_process(delta: float) -> void:
	position += Vector2.RIGHT.rotated(rotation) * speed * delta

func _on_body_entered(body: Node2D) -> void:
	if body.has_method("take_damage"):
		body.take_damage(damage)
	queue_free()
```

✅ **You've succeeded when:** The player moves with WASD, the gun rotates to face the mouse, clicking shoots bullets that travel in the correct direction and destroy on impact.

---

### 🔵 Intermediate Project: Inventory System

```gdscript
# inventory.gd — Complete inventory with UI
class_name Inventory
extends Resource

signal item_added(item: ItemData, slot: int)
signal item_removed(item: ItemData, slot: int)
signal item_moved(from_slot: int, to_slot: int)

@export var size: int = 20
var slots: Array  # Array of ItemData or null

func _init(inventory_size: int = 20) -> void:
	size = inventory_size
	slots = []
	slots.resize(size)
	slots.fill(null)

func add_item(item: ItemData) -> int:
	# First try to stack with existing items:
	if item.stackable:
		for i in size:
			if slots[i] != null and slots[i].id == item.id:
				if slots[i].stack_count < item.max_stack:
					slots[i].stack_count += 1
					item_added.emit(item, i)
					return i

	# Find empty slot:
	for i in size:
		if slots[i] == null:
			slots[i] = item.duplicate()
			slots[i].stack_count = 1
			item_added.emit(slots[i], i)
			return i

	return -1  # Inventory full

func remove_item(slot: int, count: int = 1) -> ItemData:
	if slot < 0 or slot >= size or slots[slot] == null:
		return null

	var item := slots[slot]
	if item.stackable and item.stack_count > count:
		item.stack_count -= count
		item_removed.emit(item, slot)
		return item.duplicate()
	else:
		slots[slot] = null
		item_removed.emit(item, slot)
		return item

func move_item(from_slot: int, to_slot: int) -> void:
	var temp := slots[from_slot]
	slots[from_slot] = slots[to_slot]
	slots[to_slot] = temp
	item_moved.emit(from_slot, to_slot)

func get_item(slot: int) -> ItemData:
	return slots[slot]

func has_item(item_id: String) -> bool:
	for slot in slots:
		if slot != null and slot.id == item_id:
			return true
	return false

func count_item(item_id: String) -> int:
	var count := 0
	for slot in slots:
		if slot != null and slot.id == item_id:
			count += slot.stack_count
	return count

func get_used_slots() -> int:
	var count := 0
	for slot in slots:
		if slot != null:
			count += 1
	return count

func is_full() -> bool:
	return get_used_slots() >= size
```

---

### 🔴 Advanced Project: Behavior Tree Enemy AI

```gdscript
# enemy_ai.gd — Finite state machine AI for an enemy
class_name EnemyAI
extends CharacterBody2D

enum State { IDLE, PATROL, CHASE, ATTACK, STUNNED, DEAD }

@export var move_speed: float = 120.0
@export var chase_speed: float = 200.0
@export var detection_range: float = 250.0
@export var attack_range: float = 50.0
@export var attack_damage: int = 1
@export var attack_cooldown: float = 1.5
@export var patrol_wait_time: float = 2.0
@export var patrol_points: Array[Vector2] = []

@onready var detection_area := $DetectionArea
@onready var attack_area := $AttackArea
@onready var anim := $AnimationPlayer
@onready var nav_agent := $NavigationAgent2D

var state: State = State.IDLE:
	set(value):
		_exit_state(state)
		state = value
		_enter_state(state)

var health: int = 5
var target: Node2D = null
var _patrol_index: int = 0
var _attack_timer: float = 0.0
var _patrol_wait_timer: float = 0.0
var _stun_timer: float = 0.0

func _ready() -> void:
	detection_area.body_entered.connect(_on_detection_area_body_entered)
	detection_area.body_exited.connect(_on_detection_area_body_exited)
	attack_area.body_entered.connect(_on_attack_area_body_entered)
	state = State.PATROL if patrol_points.size() > 0 else State.IDLE

func _physics_process(delta: float) -> void:
	match state:
		State.IDLE:     _state_idle(delta)
		State.PATROL:   _state_patrol(delta)
		State.CHASE:    _state_chase(delta)
		State.ATTACK:   _state_attack(delta)
		State.STUNNED:  _state_stunned(delta)

func _enter_state(new_state: State) -> void:
	match new_state:
		State.IDLE:
			anim.play("idle")
			velocity = Vector2.ZERO
		State.PATROL:
			anim.play("walk")
		State.CHASE:
			anim.play("run")
		State.ATTACK:
			anim.play("attack")
			_attack_timer = 0.0
		State.STUNNED:
			anim.play("stunned")
			velocity = Vector2.ZERO
		State.DEAD:
			anim.play("death")
			set_physics_process(false)

func _exit_state(_old_state: State) -> void:
	pass

func _state_idle(_delta: float) -> void:
	if target != null:
		state = State.CHASE

func _state_patrol(delta: float) -> void:
	if target != null:
		state = State.CHASE
		return

	if patrol_points.is_empty():
		state = State.IDLE
		return

	var target_pos := patrol_points[_patrol_index]
	nav_agent.target_position = target_pos

	if nav_agent.is_navigation_finished():
		_patrol_wait_timer += delta
		velocity = Vector2.ZERO
		anim.play("idle")
		if _patrol_wait_timer >= patrol_wait_time:
			_patrol_wait_timer = 0.0
			_patrol_index = (_patrol_index + 1) % patrol_points.size()
			anim.play("walk")
	else:
		var next_pos := nav_agent.get_next_path_position()
		velocity = (next_pos - global_position).normalized() * move_speed
		move_and_slide()

func _state_chase(_delta: float) -> void:
	if target == null:
		state = State.PATROL
		return

	if global_position.distance_to(target.global_position) <= attack_range:
		state = State.ATTACK
		return

	nav_agent.target_position = target.global_position
	var next_pos := nav_agent.get_next_path_position()
	velocity = (next_pos - global_position).normalized() * chase_speed

	if velocity.x != 0:
		$Sprite2D.flip_h = velocity.x < 0

	move_and_slide()

func _state_attack(delta: float) -> void:
	velocity = Vector2.ZERO
	_attack_timer += delta
	if _attack_timer >= attack_cooldown:
		_attack_timer = 0.0
		if target != null and target.has_method("take_damage"):
			target.take_damage(attack_damage)
		if target == null or global_position.distance_to(target.global_position) > attack_range:
			state = State.CHASE

func _state_stunned(delta: float) -> void:
	_stun_timer -= delta
	if _stun_timer <= 0:
		state = State.CHASE if target != null else State.PATROL

func take_damage(amount: int, knockback: Vector2 = Vector2.ZERO) -> void:
	health -= amount
	velocity += knockback
	if health <= 0:
		state = State.DEAD
	else:
		_stun_timer = 0.4
		state = State.STUNNED

func _on_detection_area_body_entered(body: Node2D) -> void:
	if body.is_in_group("player"):
		target = body
		if state == State.IDLE or state == State.PATROL:
			state = State.CHASE

func _on_detection_area_body_exited(body: Node2D) -> void:
	if body == target:
		target = null
		state = State.PATROL

func _on_attack_area_body_entered(body: Node2D) -> void:
	if body == target:
		state = State.ATTACK
```

🔥 **Challenge:** Add a behavior tree system where each behavior (patrol, chase, attack, flee) is a separate class that can be composed, and the AI switches based on priorities with smooth transitions.

---

## ⚠️ 7. Common Mistakes

---

### ❌ Mistake 1: Accessing Nodes Before `_ready()`

```gdscript
# ❌ WRONG — $Sprite2D doesn't exist at class creation time:
extends Node2D

var sprite = $Sprite2D  # ERROR! Scene not initialized yet!

func _ready() -> void:
	sprite.modulate = Color.RED  # Crash! sprite is null

# ✅ RIGHT — use @onready:
extends Node2D

@onready var sprite := $Sprite2D  # Assigned during _ready()

func _ready() -> void:
	sprite.modulate = Color.RED  # Works!

# ✅ Also RIGHT — access inside _ready():
extends Node2D

func _ready() -> void:
	var sprite := $Sprite2D  # Also fine — accessed after scene is ready
	sprite.modulate = Color.RED
```

---

### ❌ Mistake 2: Calling `queue_free()` During Physics Processing

```gdscript
# ❌ WRONG — deleting nodes during _physics_process can crash or corrupt:
func _physics_process(delta: float) -> void:
	if health <= 0:
		free()  # DANGER! Crashes if anything else references this node

# ✅ RIGHT — use queue_free() (deferred deletion at end of frame):
func _physics_process(delta: float) -> void:
	if health <= 0:
		queue_free()  # Safe! Deleted after physics step completes

# ✅ Also RIGHT — set a flag and delete in _process:
var _should_die := false

func _physics_process(delta: float) -> void:
	if health <= 0:
		_should_die = true

func _process(delta: float) -> void:
	if _should_die:
		queue_free()

# ✅ For CollisionShape2D — disable deferred:
func die() -> void:
	$CollisionShape2D.set_deferred("disabled", true)  # Must be deferred!
	queue_free()
```

---

### ❌ Mistake 3: Not Using `move_and_slide()` Correctly

```gdscript
# ❌ WRONG — manually moving position bypasses physics:
func _physics_process(delta: float) -> void:
	position.x += 200.0 * delta  # Ignores walls! Falls through floors!

# ❌ WRONG — applying gravity every frame regardless of floor:
func _physics_process(delta: float) -> void:
	velocity.y += gravity * delta   # Keeps adding even on floor!
	position += velocity * delta    # Not using move_and_slide!

# ✅ RIGHT — proper physics movement:
extends CharacterBody2D

var gravity := ProjectSettings.get_setting("physics/2d/default_gravity")

func _physics_process(delta: float) -> void:
	# Apply gravity only when not on floor:
	if not is_on_floor():
		velocity.y += gravity * delta

	# Apply horizontal movement:
	var direction := Input.get_axis("move_left", "move_right")
	velocity.x = direction * 200.0

	# Let Godot handle collisions:
	move_and_slide()  # Automatically uses velocity, updates is_on_floor()
```

---

### ❌ Mistake 4: Forgetting Delta Time in Movement

```gdscript
# ❌ WRONG — speed depends on frame rate:
func _process(delta: float) -> void:
	position.x += 5.0   # At 60fps: 300 px/s. At 30fps: 150 px/s. INCONSISTENT!

# ❌ WRONG — same issue with rotation:
func _process(delta: float) -> void:
	rotation += 0.1  # Different speed on different hardware!

# ✅ RIGHT — multiply by delta for frame-rate independence:
func _process(delta: float) -> void:
	position.x += 300.0 * delta   # Always 300 px/s regardless of FPS
	rotation += deg_to_rad(90.0) * delta  # Always 90°/second

# ✅ RIGHT — use Tween for smooth animation instead:
func start_rotating() -> void:
	var tween := create_tween().set_loops()
	tween.tween_property(self, "rotation", TAU, 4.0)  # Full rotation in 4 seconds
```

---

### ❌ Mistake 5: Signal Connection Leaks

```gdscript
# ❌ WRONG — connecting signals inside _process creates duplicate connections:
func _process(delta: float) -> void:
	if score > 100:
		player.jumped.connect(_on_jumped)  # Called 60+ times! Hundreds of connections!

# ❌ WRONG — not disconnecting when node leaves tree:
func _ready() -> void:
	get_tree().process_frame.connect(_expensive_check)
	# If this node is freed, get_tree() still calls _expensive_check on deleted object!

# ✅ RIGHT — connect once in _ready():
func _ready() -> void:
	player.jumped.connect(_on_jumped)  # Connected exactly once

# ✅ RIGHT — use signal reference to disconnect, or use Callable.bind:
func _ready() -> void:
	# Auto-disconnects when this node is freed (Godot 4 feature):
	player.jumped.connect(_on_jumped.bind(), CONNECT_ONE_SHOT)

	# Or connect to a named method — Godot tracks it:
	get_tree().process_frame.connect(_on_frame)

func _exit_tree() -> void:
	# Manual cleanup if needed:
	if get_tree().process_frame.is_connected(_on_frame):
		get_tree().process_frame.disconnect(_on_frame)

func _on_jumped() -> void: pass
func _on_frame() -> void: pass
var player: Node
var score: int = 0
```

---

### ❌ Mistake 6: Using `_process` for Physics-Dependent Logic

```gdscript
# ❌ WRONG — checking collisions in _process instead of _physics_process:
func _process(delta: float) -> void:
	velocity.y += gravity  # Gravity in wrong callback!
	move_and_slide()       # Physics in wrong callback!
	if is_on_floor():      # Unreliable outside physics step
		print("On floor!")

# ✅ RIGHT — physics in _physics_process:
func _physics_process(delta: float) -> void:
	if not is_on_floor():
		velocity.y += gravity * delta
	move_and_slide()
	if is_on_floor():
		print("On floor!")

# ✅ RIGHT — visuals in _process:
func _process(delta: float) -> void:
	$Camera2D.offset = Vector2(sin(Time.get_ticks_msec() * 0.001) * 5.0, 0)
	$ParticleSystem.emitting = is_moving

var gravity := 980.0
var is_moving := false
```

---

## 🔥 8. Pro Tips & Hidden Tricks

---

### 💎 Tip 1: The Tween API — Silky Smooth Animations

```gdscript
extends Node2D

func _ready() -> void:
	# ── BASIC TWEEN ──────────────────────────────────────────────────────────
	var tween := create_tween()

	# Move to position over 1 second:
	tween.tween_property(self, "position", Vector2(400, 300), 1.0)

	# Chain multiple tweens:
	var chained := create_tween()
	chained.tween_property($Sprite2D, "modulate:a", 0.0, 0.5)  # Fade out
	chained.tween_property($Sprite2D, "position", Vector2(200, 0), 0.3)  # Move
	chained.tween_property($Sprite2D, "modulate:a", 1.0, 0.5)  # Fade in

	# ── EASING ────────────────────────────────────────────────────────────────
	var bouncy := create_tween()
	bouncy.tween_property(self, "position:y", 300.0, 1.0)\
		.set_ease(Tween.EASE_OUT)\
		.set_trans(Tween.TRANS_BOUNCE)

	# Ease types: EASE_IN, EASE_OUT, EASE_IN_OUT, EASE_OUT_IN
	# Transition types: TRANS_LINEAR, TRANS_QUAD, TRANS_CUBIC, TRANS_QUART,
	#   TRANS_QUINT, TRANS_EXPO, TRANS_CIRC, TRANS_BOUNCE, TRANS_ELASTIC,
	#   TRANS_BACK, TRANS_SPRING

	# ── LOOPS AND DELAYS ──────────────────────────────────────────────────────
	var looped := create_tween().set_loops()  # Infinite loop
	looped.tween_property($Icon, "rotation", TAU, 2.0)  # Spin forever

	var delayed := create_tween()
	delayed.tween_interval(2.0)  # Wait 2 seconds
	delayed.tween_property(self, "visible", false, 0)  # Then hide

	# ── TWEEN CALLBACKS ───────────────────────────────────────────────────────
	var with_callback := create_tween()
	with_callback.tween_property(self, "scale", Vector2(2, 2), 0.3)
	with_callback.tween_callback(_on_scale_done)  # Call function when done
	with_callback.tween_property(self, "scale", Vector2.ONE, 0.3)

	# ── PARALLEL TWEENS ───────────────────────────────────────────────────────
	var parallel := create_tween().set_parallel(true)  # Run all at same time!
	parallel.tween_property(self, "position", Vector2(500, 0), 1.0)
	parallel.tween_property(self, "rotation", PI, 1.0)
	parallel.tween_property($Sprite2D, "modulate", Color.BLUE, 1.0)

	# ── CUSTOM VALUE TWEENING ─────────────────────────────────────────────────
	var custom := create_tween()
	custom.tween_method(_on_health_tween, 0.0, 100.0, 1.5)  # Smoothly count 0→100

	# ── AWAIT TWEEN COMPLETION ────────────────────────────────────────────────
	var awaited := create_tween()
	awaited.tween_property(self, "position:x", 600.0, 1.0)
	await awaited.finished
	print("Tween done! Now at: ", position)

func _on_scale_done() -> void:
	print("Scale animation completed!")

func _on_health_tween(value: float) -> void:
	$HealthLabel.text = "HP: %d" % int(value)
```

---

### 💎 Tip 2: Groups — Broadcast Messages to Multiple Nodes

```gdscript
# Groups allow you to tag nodes and operate on all of them at once

# ── ADDING/REMOVING FROM GROUPS ──────────────────────────────────────────────
# In Godot Editor: Node → Groups tab → Add
# Or in code:
func _ready() -> void:
	add_to_group("enemies")
	add_to_group("damageable")
	add_to_group("saveable")

func die() -> void:
	remove_from_group("enemies")

# ── CHECKING GROUP MEMBERSHIP ─────────────────────────────────────────────────
func can_damage(node: Node) -> bool:
	return node.is_in_group("damageable")

# ── GETTING ALL GROUP MEMBERS ─────────────────────────────────────────────────
func damage_all_enemies(amount: int) -> void:
	var enemies := get_tree().get_nodes_in_group("enemies")
	for enemy in enemies:
		if enemy.has_method("take_damage"):
			enemy.take_damage(amount)

# ── CALL GROUP — broadcast method call to ALL group members ──────────────────
# This is the cleanest way to send a message to many nodes!
func screen_shake_all() -> void:
	get_tree().call_group("cameras", "start_shake", 10.0, 0.5)
	# Calls start_shake(10.0, 0.5) on every node in "cameras" group

# call_group options:
func broadcast() -> void:
	# Default — calls immediately:
	get_tree().call_group("enemies", "alert_player_spotted")

	# Deferred — calls at end of frame:
	get_tree().call_group_flags(
		SceneTree.GROUP_CALL_DEFERRED, "enemies", "update_patrol"
	)

# ── NOTIFY GROUP ─────────────────────────────────────────────────────────────
func notify_all() -> void:
	get_tree().notify_group("saveable", Node.NOTIFICATION_READY)

# ── SET GROUP PROPERTY ────────────────────────────────────────────────────────
func pause_all_enemies() -> void:
	get_tree().set_group("enemies", "process_mode", Node.PROCESS_MODE_DISABLED)
```

---

### 💎 Tip 3: Resource System — Data-Driven Game Design

```gdscript
# Resources are Godot's data containers — save/load via .tres files!
# Great for: items, characters, abilities, maps, stats, configs

# ── DEFINING A RESOURCE CLASS ─────────────────────────────────────────────────
class_name CharacterStats
extends Resource

@export var character_name: String = "Unknown"
@export var max_health: int = 100
@export var attack: int = 10
@export var defense: int = 5
@export var move_speed: float = 200.0
@export var sprite: Texture2D

@export_group("Progression")
@export var level: int = 1
@export var experience: int = 0
@export var experience_to_next_level: int = 100

@export_group("Abilities")
@export var abilities: Array[AbilityData] = []

# Computed properties:
var total_attack: int:
	get: return attack + _bonus_attack

var _bonus_attack: int = 0

func level_up() -> void:
	if experience >= experience_to_next_level:
		level += 1
		experience -= experience_to_next_level
		experience_to_next_level = int(experience_to_next_level * 1.5)
		max_health += 10
		attack += 2
		defense += 1

# ── USING RESOURCES ────────────────────────────────────────────────────────────
extends CharacterBody2D

@export var stats: CharacterStats  # Drag .tres file in Inspector!

var current_health: int

func _ready() -> void:
	if stats:
		current_health = stats.max_health
		$Sprite2D.texture = stats.sprite

func take_damage(amount: int) -> void:
	var actual_damage := max(1, amount - stats.defense)
	current_health -= actual_damage

# ── CREATING RESOURCES AT RUNTIME ─────────────────────────────────────────────
func create_custom_character() -> CharacterStats:
	var new_stats := CharacterStats.new()
	new_stats.character_name = "Custom Hero"
	new_stats.max_health = 150
	new_stats.attack = 15
	return new_stats

# ── SAVING RESOURCES ──────────────────────────────────────────────────────────
func save_stats() -> void:
	ResourceSaver.save(stats, "user://player_stats.tres")

func load_stats() -> void:
	if ResourceLoader.exists("user://player_stats.tres"):
		stats = ResourceLoader.load("user://player_stats.tres") as CharacterStats

# ── PRELOADING RESOURCES ──────────────────────────────────────────────────────
# Preload: compile-time, always available:
const WARRIOR_STATS := preload("res://resources/warrior.tres")

# Load: runtime, more flexible:
func load_character(character_id: String) -> CharacterStats:
	var path := "res://resources/characters/%s.tres" % character_id
	return ResourceLoader.load(path) as CharacterStats
```

---

### 💎 Tip 4: Autoloads — Global Singletons

```gdscript
# Autoloads are global nodes accessible from ANYWHERE in your game
# Add in: Project → Project Settings → Autoloads
# They're added as children of Root before any scene loads

# ── events.gd — Global Event Bus ─────────────────────────────────────────────
extends Node

# Centralized signals for game-wide events:
signal player_health_changed(new_hp: int, max_hp: int)
signal score_updated(new_score: int)
signal game_over()
signal level_completed(level_index: int)
signal item_picked_up(item_name: String)
signal enemy_killed(enemy_type: String, position: Vector2)
signal achievement_unlocked(achievement_id: String)

# Any node can emit global events:
# Events.player_health_changed.emit(50, 100)

# Any node can listen:
# Events.score_updated.connect(_on_score_updated)

# ── audio_manager.gd — Global Audio ───────────────────────────────────────────
extends Node

@onready var music_player := $MusicPlayer
@onready var sfx_player := $SFXPlayer

var music_volume: float = 0.8:
	set(v):
		music_volume = clamp(v, 0.0, 1.0)
		music_player.volume_db = linear_to_db(music_volume)

func play_sfx(sound_name: String) -> void:
	var path := "res://audio/sfx/%s.wav" % sound_name
	if ResourceLoader.exists(path):
		var audio := ResourceLoader.load(path) as AudioStream
		sfx_player.stream = audio
		sfx_player.play()

func play_music(track_name: String, fade_time: float = 1.0) -> void:
	var path := "res://audio/music/%s.ogg" % track_name
	if not ResourceLoader.exists(path):
		return
	var track := ResourceLoader.load(path) as AudioStream
	if music_player.stream == track:
		return  # Already playing

	var tween := create_tween()
	tween.tween_property(music_player, "volume_db", -60.0, fade_time)
	await tween.finished
	music_player.stream = track
	music_player.play()
	tween = create_tween()
	tween.tween_property(music_player, "volume_db", linear_to_db(music_volume), fade_time)

# Usage anywhere:
# AudioManager.play_sfx("jump")
# AudioManager.play_music("level_1_theme")
```

---

### 💎 Tip 5: Shaders from GDScript

```gdscript
# ── APPLYING SHADERS TO SPRITES ───────────────────────────────────────────────
extends Sprite2D

# Load a shader:
var outline_shader := preload("res://shaders/outline.gdshader")

func add_outline(color: Color = Color.WHITE, width: float = 2.0) -> void:
	var material := ShaderMaterial.new()
	material.shader = outline_shader
	material.set_shader_parameter("outline_color", color)
	material.set_shader_parameter("outline_width", width)
	self.material = material

func remove_outline() -> void:
	material = null

# ── SHADER-LIKE EFFECTS WITH CanvasItemMaterial ───────────────────────────────
func set_blend_mode_additive() -> void:
	var mat := CanvasItemMaterial.new()
	mat.blend_mode = CanvasItemMaterial.BLEND_MODE_ADD
	material = mat

# ── MODULATE TRICKS ───────────────────────────────────────────────────────────
func flash_white() -> void:
	# Flash white then return to normal:
	var tween := create_tween()
	tween.tween_property(self, "modulate", Color.WHITE * 3.0, 0.05)
	tween.tween_property(self, "modulate", Color.WHITE, 0.1)

func silhouette(color: Color) -> void:
	modulate = color  # Flat color over sprite (use with shader for true silhouette)

# ── INLINE SHADER ─────────────────────────────────────────────────────────────
func apply_inline_shader() -> void:
	var shader_code := """
shader_type canvas_item;

uniform float wave_strength : hint_range(0.0, 10.0) = 3.0;
uniform float wave_speed : hint_range(0.0, 10.0) = 2.0;

void fragment() {
	vec2 uv = UV;
	uv.x += sin(uv.y * 20.0 + TIME * wave_speed) * wave_strength * 0.01;
	COLOR = texture(TEXTURE, uv);
}
"""
	var shader := Shader.new()
	shader.code = shader_code
	var mat := ShaderMaterial.new()
	mat.shader = shader
	material = mat

	# Animate shader parameters:
	var tween := create_tween().set_loops()
	tween.tween_method(
		func(v): material.set_shader_parameter("wave_strength", v),
		0.0, 5.0, 2.0
	)
```

---

## 🚀 9. Advanced Concepts (Expert Level)

---

### Advanced Concept 1: 2D & 3D Physics Deep Dive

```gdscript
# ── CHARACTERBODY2D — THE PLATFORMER/TOPDOWN BODY ────────────────────────────
extends CharacterBody2D

var gravity := ProjectSettings.get_setting("physics/2d/default_gravity") as float
var speed := 300.0
var jump_velocity := -600.0

func _physics_process(delta: float) -> void:
	# Apply gravity:
	if not is_on_floor():
		velocity.y += gravity * delta

	# is_on_floor() / is_on_wall() / is_on_ceiling() return booleans
	# get_floor_normal() returns normal vector of floor surface
	# get_wall_normal() returns normal vector of wall

	# Slope detection — check if on a slope:
	if is_on_floor():
		var floor_angle := get_floor_angle()  # Angle of floor in radians
		if floor_angle > deg_to_rad(45):
			print("Steep slope! Sliding...")

	move_and_slide()  # Returns the velocity after collisions

	# Check what we collided with:
	for i in get_slide_collision_count():
		var collision := get_slide_collision(i)
		print("Collided with: ", collision.get_collider().name)
		print("Normal: ", collision.get_normal())
		print("Position: ", collision.get_position())

# ── RIGIDBODY2D — FULLY SIMULATED PHYSICS ────────────────────────────────────
extends RigidBody2D

func _ready() -> void:
	# Set physics properties:
	mass = 2.0
	gravity_scale = 1.5          # More gravity than default
	linear_damp = 0.5            # Slow down over time
	angular_damp = 2.0           # Stop spinning over time
	lock_rotation = false        # Allow free rotation

func apply_forces() -> void:
	# Apply impulse (instant force):
	apply_impulse(Vector2(0, -500))         # Jump
	apply_impulse(Vector2(200, 0))          # Dash right
	apply_impulse(Vector2(100, 0), Vector2(0, -30))  # Impulse at offset point

	# Apply continuous force:
	apply_force(Vector2(0, -1000))          # Anti-gravity boost
	apply_central_force(Vector2(500, 0))   # Push right (no rotation)

	# Apply torque (rotational force):
	apply_torque(1000.0)                   # Spin

	# Direct velocity setting:
	linear_velocity = Vector2(300, 0)
	angular_velocity = PI  # Spinning

# ── AREA2D — TRIGGER ZONES ────────────────────────────────────────────────────
extends Area2D

@export var damage_per_second: float = 10.0
var _bodies_inside: Array[Node] = []

func _ready() -> void:
	body_entered.connect(_on_body_entered)
	body_exited.connect(_on_body_exited)
	area_entered.connect(_on_area_entered)

func _physics_process(delta: float) -> void:
	# Damage all bodies inside:
	for body in _bodies_inside:
		if body.has_method("take_damage"):
			body.take_damage(damage_per_second * delta)

func _on_body_entered(body: Node2D) -> void:
	_bodies_inside.append(body)

func _on_body_exited(body: Node2D) -> void:
	_bodies_inside.erase(body)

func _on_area_entered(area: Area2D) -> void:
	if area.is_in_group("pickup"):
		# Pickup logic
		area.queue_free()

# ── RAY CASTING ───────────────────────────────────────────────────────────────
extends Node2D

func shoot_ray(from: Vector2, direction: Vector2, distance: float) -> Dictionary:
	var space_state := get_world_2d().direct_space_state
	var query := PhysicsRayQueryParameters2D.create(
		from,
		from + direction * distance
	)
	# Exclude self from raycast:
	query.exclude = [self]
	# Only hit certain collision layers:
	query.collision_mask = 0b0001  # Layer 1 only
	# Hit areas too (not just physics bodies):
	query.collide_with_areas = true

	var result := space_state.intersect_ray(query)
	return result
	# Returns: {"position": Vector2, "normal": Vector2, "collider": Node, ...}
	# Returns empty dict {} if no hit

func _process(_delta: float) -> void:
	var result := shoot_ray(global_position,
		(get_global_mouse_position() - global_position).normalized(), 1000.0)

	if result:
		$HitMarker.global_position = result["position"]
		var hit_node := result["collider"] as Node
		if hit_node.has_method("aim_at"):
			hit_node.aim_at()

# ── SHAPE CASTING ─────────────────────────────────────────────────────────────
func sweep_area(from: Vector2, to: Vector2, radius: float) -> Array[Dictionary]:
	var space := get_world_2d().direct_space_state
	var shape := CircleShape2D.new()
	shape.radius = radius

	var params := PhysicsShapeQueryParameters2D.new()
	params.shape = shape
	params.transform = Transform2D(0, from)
	params.motion = to - from
	params.collision_mask = 0xFFFFFFFF

	return space.cast_motion(params)
```

---

### Advanced Concept 2: Performance Optimization

```gdscript
# ── OBJECT POOLING — avoid GC pressure from constant instantiation ────────────
class_name ObjectPool
extends Node

@export var pool_size: int = 50
var _pool: Array[Node] = []
var _scene: PackedScene

func initialize(scene: PackedScene, initial_size: int = pool_size) -> void:
	_scene = scene
	for i in initial_size:
		var obj := scene.instantiate()
		obj.set_meta("pooled", true)
		add_child(obj)
		obj.hide()
		_pool.append(obj)

func get_object() -> Node:
	for obj in _pool:
		if not obj.visible:
			obj.show()
			return obj

	# Pool exhausted — create a new one:
	var obj := _scene.instantiate()
	obj.set_meta("pooled", true)
	add_child(obj)
	_pool.append(obj)
	print("[Pool] Pool exhausted! Creating new object. Total: ", _pool.size())
	return obj

func return_object(obj: Node) -> void:
	if obj.get_meta("pooled", false):
		obj.hide()
		obj.global_position = Vector2(-9999, -9999)  # Off screen
		# Reset state if needed:
		if obj.has_method("reset"):
			obj.reset()

# Usage:
extends Node2D

@onready var bullet_pool: ObjectPool = $BulletPool

func _ready() -> void:
	bullet_pool.initialize(preload("res://scenes/bullet.tscn"), 30)

func shoot() -> void:
	var bullet := bullet_pool.get_object()
	bullet.global_position = $BulletSpawn.global_position
	bullet.rotation = rotation
	# When bullet is done:
	# bullet_pool.return_object(bullet)

# ── VISIBILITY NOTIFIER — only process when on screen ────────────────────────
extends CharacterBody2D

@onready var notifier := $VisibleOnScreenNotifier2D

func _ready() -> void:
	notifier.screen_entered.connect(func(): set_physics_process(true))
	notifier.screen_exited.connect(func(): set_physics_process(false))
	set_physics_process(false)  # Start disabled!

# ── MULTIMESH — render thousands of instances cheaply ────────────────────────
extends MultiMeshInstance2D

func create_particles(count: int) -> void:
	multimesh = MultiMesh.new()
	multimesh.mesh = QuadMesh.new()
	multimesh.instance_count = count
	multimesh.transform_format = MultiMesh.TRANSFORM_2D

	for i in count:
		var transform := Transform2D()
		transform.origin = Vector2(
			randf_range(-500, 500),
			randf_range(-300, 300)
		)
		multimesh.set_instance_transform_2d(i, transform)
		multimesh.set_instance_color(i, Color(randf(), randf(), randf(), 1.0))

# ── OCCLUSION CULLING / LOD ───────────────────────────────────────────────────
extends Node3D  # 3D example

@export var lod_distances: Array[float] = [20.0, 50.0, 100.0]
@onready var lod_meshes: Array[MeshInstance3D] = [
	$HighDetailMesh, $MedDetailMesh, $LowDetailMesh
]

func _process(_delta: float) -> void:
	var camera := get_viewport().get_camera_3d()
	if not camera:
		return
	var distance := global_position.distance_to(camera.global_position)

	for i in lod_meshes.size():
		lod_meshes[i].visible = false

	if distance < lod_distances[0]:
		lod_meshes[0].visible = true
	elif distance < lod_distances[1]:
		lod_meshes[1].visible = true
	elif distance < lod_distances[2]:
		lod_meshes[2].visible = true
	# Beyond last distance: invisible
```

---

### Advanced Concept 3: Networked Multiplayer

```gdscript
# ── ENet MULTIPLAYER (Godot's built-in networking) ────────────────────────────
extends Node

const PORT := 9999
const MAX_CLIENTS := 8

var peer: ENetMultiplayerPeer

# ── SERVER SIDE ───────────────────────────────────────────────────────────────
func create_server() -> void:
	peer = ENetMultiplayerPeer.new()
	var err := peer.create_server(PORT, MAX_CLIENTS)
	if err != OK:
		printerr("Failed to create server: ", err)
		return

	multiplayer.multiplayer_peer = peer
	multiplayer.peer_connected.connect(_on_client_connected)
	multiplayer.peer_disconnected.connect(_on_client_disconnected)
	print("Server started on port ", PORT)

func _on_client_connected(id: int) -> void:
	print("Client %d connected!" % id)
	# Send game state to new client:
	_sync_game_state.rpc_id(id)

func _on_client_disconnected(id: int) -> void:
	print("Client %d disconnected!" % id)

# ── CLIENT SIDE ───────────────────────────────────────────────────────────────
func join_server(ip: String) -> void:
	peer = ENetMultiplayerPeer.new()
	var err := peer.create_client(ip, PORT)
	if err != OK:
		printerr("Failed to connect: ", err)
		return

	multiplayer.multiplayer_peer = peer
	multiplayer.connected_to_server.connect(_on_connected)
	multiplayer.connection_failed.connect(_on_connection_failed)
	print("Connecting to ", ip, ":", PORT)

func _on_connected() -> void:
	print("Connected! My ID: ", multiplayer.get_unique_id())

func _on_connection_failed() -> void:
	printerr("Connection failed!")

# ── RPC — Remote Procedure Calls ─────────────────────────────────────────────
extends CharacterBody2D

# @rpc — call this function on other clients/server:
@rpc("any_peer", "call_local", "reliable")
func sync_position(pos: Vector2, vel: Vector2) -> void:
	global_position = pos
	velocity = vel

@rpc("authority", "call_remote", "unreliable_ordered")
func update_animation(anim_name: String) -> void:
	$AnimationPlayer.play(anim_name)

@rpc("any_peer", "call_local", "reliable")
func _sync_game_state() -> void:
	# Called on specific client to sync state
	pass

# RPC modes:
# "any_peer"  — any peer can call this
# "authority" — only the network authority (usually server)
# "call_local" — also runs on calling peer
# "call_remote" — only runs on remote peers (not caller)
# "reliable"  — guaranteed delivery (TCP-like)
# "unreliable" — fast, may be lost (UDP-like)
# "unreliable_ordered" — fast but in order

func _physics_process(delta: float) -> void:
	if not is_multiplayer_authority():
		return  # Only authority controls this character

	# Move, then sync to all others:
	super(delta)
	sync_position.rpc(global_position, velocity)  # Broadcast to all!
```

---

### ⚡ Performance & Optimization Table

| Technique                              | Impact   | When to Use                                          |
|----------------------------------------|----------|------------------------------------------------------|
| Object pooling for bullets/particles   | Very High | Any frequently spawned/destroyed objects             |
| `@onready` + typed references          | Medium   | Faster than repeated `get_node()` calls in hot loops |
| `PackedByteArray`/`PackedVector2Array` | High     | Bulk numeric data — drawing, audio, collision meshes |
| `process_mode = DISABLED` off-screen  | High     | Enemies, NPCs, effects not currently on screen       |
| `VisibleOnScreenNotifier2D`            | High     | Auto-toggle processing based on camera view          |
| Typed arrays `Array[Type]`             | Medium   | 20-30% faster iteration than untyped `Array`         |
| `call_deferred()` for safe operations  | Medium   | Modify scene tree safely during physics/signal calls |
| MultiMeshInstance for crowds           | Very High | Grass, coins, stars — thousands with one draw call   |
| SubViewport + caching                  | High     | Expensive scenes rendered once, reused as texture    |
| `preload()` vs `load()`               | Medium   | `preload()` at compile time for frequently used assets|

---

## 💀 10. 0.01% Hidden Secrets — Ultra Elite

---

### 🔮 Secret 1: `call_deferred()` and Thread Safety

```gdscript
# call_deferred() runs a function at the end of the current frame
# CRITICAL for modifying the scene tree from signals or physics callbacks!

extends Node

func dangerous_in_signal() -> void:
	# ❌ Modifying scene tree during physics/collision callback can crash:
	get_node("Enemy").queue_free()     # May crash!
	add_child(new_object)              # May crash!

func safe_deferred() -> void:
	# ✅ Deferred — runs after current physics step completes:
	get_node("Enemy").queue_free()                          # Actually safe for queue_free
	call_deferred("_do_safe_thing")                        # Call method deferred
	set_deferred("visible", false)                         # Set property deferred
	$CollisionShape2D.set_deferred("disabled", true)      # MUST be deferred for shapes!

func _do_safe_thing() -> void:
	# This runs at the end of the frame — safe to modify scene tree:
	add_child(preload("res://scenes/effect.tscn").instantiate())

# ── DEFERRING PROPERTY CHANGES ────────────────────────────────────────────────
func on_collision(body: Node) -> void:
	# NEVER disable collision shapes directly in collision callbacks:
	# $CollisionShape2D.disabled = true  # ❌ CRASH!

	# ALWAYS deferred:
	$CollisionShape2D.set_deferred("disabled", true)  # ✅ Safe!

# ── THREAD-SAFE OPERATIONS ────────────────────────────────────────────────────
var _thread: Thread

func start_background_work() -> void:
	_thread = Thread.new()
	_thread.start(_background_task.bind(some_data))

func _background_task(data: Variant) -> void:
	# Running on a separate thread — DO NOT touch scene tree here!
	var result := _heavy_computation(data)
	# Safely return result to main thread via call_deferred:
	call_deferred("_on_background_complete", result)

func _on_background_complete(result: Variant) -> void:
	# Now we're on the main thread — safe to update scene tree!
	$ResultLabel.text = str(result)
	_thread.wait_to_finish()

func _heavy_computation(data: Variant) -> Variant: return data
var some_data: Variant = null
```

---

### 🔮 Secret 2: GDScript Annotations — Metaprogramming

```gdscript
# GDScript annotations modify how Godot treats your class and properties

class_name MyComponent
extends Node

# ── @export VARIANTS ─────────────────────────────────────────────────────────
@export var health: int = 100
@export_range(0, 100, 5) var armor: int = 50         # Slider with step
@export_range(0.0, 1.0, 0.01, "or_greater") var speed_multiplier: float = 1.0
@export_enum("Fire", "Ice", "Lightning", "Poison") var element: int = 0
@export_flags("Flies", "Swims", "Burrows", "Climbs") var movement_flags: int = 0
@export_color_no_alpha var tint: Color = Color.WHITE  # No alpha slider
@export_file("*.json") var config_file: String = ""  # File picker (json only)
@export_dir var asset_directory: String = ""           # Directory picker
@export_multiline var description: String = ""         # Multiline text editor
@export_node_path("CharacterBody2D") var target_path: NodePath  # Only CBs!
@export_group("Combat Stats")                          # Group in Inspector
@export_subgroup("Offense")
@export var attack: int = 10
@export_category("Advanced Settings")                  # Bold category header

# ── @tool — runs in EDITOR too! ──────────────────────────────────────────────
# Add this at top of script to run in editor:
# @tool
# extends Node
# This makes _process, _ready, etc. run while editing!
# Powerful for: editor plugins, procedural geometry, path previews

# ── @static_unload — prevent memory leaks from static vars ───────────────────
@static_unload  # Static variables are cleared when scene changes
class_name StaticDataHolder
extends RefCounted
static var heavy_cache: Dictionary = {}

# ── @warning_ignore — suppress specific warnings ──────────────────────────────
@warning_ignore("return_value_discarded")
func _call_ignoring_result() -> void:
	get_node("Something").do_something()  # Return value intentionally ignored

# ── Checking annotations at runtime ──────────────────────────────────────────
func inspect_class() -> void:
	var script := get_script() as GDScript
	if script:
		# Get all exported properties:
		for prop in get_property_list():
			if prop["usage"] & PROPERTY_USAGE_EDITOR:
				print("Exported: %s (%s)" % [prop["name"], prop["type"]])
```

---

### 🔮 Secret 3: GDExtension — C++ Speed in Godot

```gdscript
# GDExtension lets you write C++ code that integrates with Godot/GDScript
# Use for: performance-critical algorithms, existing C++ libraries, native plugins

# From GDScript, GDExtension classes look exactly like built-in Godot classes:

# Assume we have a C++ GDExtension class called FastPathfinder:
var pathfinder: FastPathfinder = FastPathfinder.new()

func find_path() -> void:
	pathfinder.set_grid_size(Vector2i(100, 100))
	pathfinder.add_obstacle(Vector2i(5, 5))
	var path := pathfinder.find_path(
		Vector2i(0, 0), Vector2i(99, 99)
	)  # Returns PackedVector2Array

# GDExtension alternative — use C# for performance:
# Add "C# (.NET)" to Godot, then:
# using Godot;
# public partial class FastSorter : Node {
#     public int[] Sort(int[] data) => data.OrderBy(x => x).ToArray();
# }
# Called from GDScript: $FastSorter.Sort(my_array)

# ── PROFILING GDScript PERFORMANCE ────────────────────────────────────────────
func profile_function() -> void:
	var start := Time.get_ticks_usec()
	_expensive_operation()
	var end := Time.get_ticks_usec()
	print("Took: %d microseconds" % (end - start))

func _expensive_operation() -> void:
	var sum := 0
	for i in 1000000:
		sum += i
	print(sum)
```

---

### 🔮 Secret 4: The Scene Tree as a State Machine

```gdscript
# Advanced pattern: use the scene tree itself as a state machine
# Each state is a separate scene — loaded/unloaded as state changes

class_name GameStateMachine
extends Node

var _current_state: Node = null
var _states: Dictionary = {}

func _ready() -> void:
	# Pre-register state scenes:
	_states = {
		"playing":   preload("res://states/playing_state.tscn"),
		"paused":    preload("res://states/paused_state.tscn"),
		"game_over": preload("res://states/game_over_state.tscn"),
		"victory":   preload("res://states/victory_state.tscn"),
	}
	transition_to("playing")

func transition_to(state_name: String, data: Dictionary = {}) -> void:
	if not _states.has(state_name):
		push_error("Unknown state: %s" % state_name)
		return

	# Exit current state:
	if _current_state:
		if _current_state.has_method("exit"):
			await _current_state.exit()
		_current_state.queue_free()
		_current_state = null

	# Enter new state:
	var state_scene := _states[state_name] as PackedScene
	_current_state = state_scene.instantiate()
	add_child(_current_state)

	if _current_state.has_method("enter"):
		_current_state.enter(data)

# Each state script:
# playing_state.gd:
# extends Node
# signal transition_requested(state_name: String, data: Dictionary)
#
# func enter(data: Dictionary) -> void:
#   Input.set_mouse_mode(Input.MOUSE_MODE_HIDDEN)
#   $HUD.show()
#
# func exit() -> void:
#   $HUD.hide()
#   await get_tree().create_timer(0.3).timeout  # Transition delay
```

---

### 🔮 Secret 5: Custom Iterators and Coroutines via Signals

```gdscript
# ── CUSTOM SIGNAL-BASED COROUTINES ────────────────────────────────────────────
extends Node

# Sequence of timed events using await chains:
func play_boss_intro() -> void:
	$ScreenDimmer.modulate.a = 0.0
	$BossSprite.visible = false

	# Fade to black:
	var tween1 := create_tween()
	tween1.tween_property($ScreenDimmer, "modulate:a", 0.8, 1.0)
	await tween1.finished

	# Show boss:
	$BossSprite.visible = true
	$BossRevealSound.play()

	# Wait for sound to finish:
	await get_tree().create_timer(2.0).timeout

	# Show boss name:
	$BossNameLabel.show()
	await $BossNameAnimation.animation_finished  # Wait for label anim

	# Fade back in:
	var tween2 := create_tween()
	tween2.tween_property($ScreenDimmer, "modulate:a", 0.0, 0.5)
	await tween2.finished

	print("Boss intro complete! Starting fight...")
	$BossAI.start_combat()

# ── YIELD-LIKE PATTERN WITH SIGNALS ──────────────────────────────────────────
func dialogue_sequence() -> void:
	# Show dialogue, wait for player input, continue:
	show_dialogue("Welcome to the dungeon...")
	await $DialogueBox.advance_pressed

	show_dialogue("Many dangers await you.")
	await $DialogueBox.advance_pressed

	show_dialogue("Are you ready?")
	await $DialogueBox.advance_pressed

	$DialogueBox.hide()
	start_game()

func show_dialogue(text: String) -> void:
	$DialogueBox.show()
	$DialogueBox.text = ""
	# Type out each character:
	for char in text:
		$DialogueBox.text += char
		await get_tree().create_timer(0.05).timeout
```

---

### 🔮 Secret 6: Visual Shaders — Connecting to GDScript

```gdscript
# VisualShader can be controlled entirely from GDScript:

extends MeshInstance3D

func apply_dissolve_shader(material: ShaderMaterial) -> void:
	material.set_shader_parameter("dissolve_threshold", 0.0)

	# Animate dissolve from 0 to 1:
	var tween := create_tween()
	tween.tween_method(
		func(value: float) -> void:
			material.set_shader_parameter("dissolve_threshold", value),
		0.0, 1.0, 2.0
	)
	tween.set_trans(Tween.TRANS_CUBIC)
	await tween.finished
	queue_free()

# Pass real-time data to shaders:
func _process(delta: float) -> void:
	var mat := material_override as ShaderMaterial
	if mat:
		mat.set_shader_parameter("time", Time.get_ticks_msec() / 1000.0)
		mat.set_shader_parameter("player_position",
			get_tree().get_first_node_in_group("player").global_position
		)
		mat.set_shader_parameter("screen_size", get_viewport().get_visible_rect().size)
```

---

### 🔮 Secret 7: AStar Pathfinding from Scratch

```gdscript
# Godot has a built-in AStar class — but understanding it unlocks everything:

extends Node2D

var astar := AStar2D.new()
const CELL_SIZE := 64
const GRID_SIZE := Vector2i(20, 15)

func _ready() -> void:
	_build_graph()
	var path := _find_path(Vector2i(0, 0), Vector2i(19, 14))
	_draw_path(path)

func _build_graph() -> void:
	astar.clear()
	for x in GRID_SIZE.x:
		for y in GRID_SIZE.y:
			var id := _pos_to_id(Vector2i(x, y))
			var pos := Vector2(x, y) * CELL_SIZE
			astar.add_point(id, pos)

	# Connect adjacent cells:
	for x in GRID_SIZE.x:
		for y in GRID_SIZE.y:
			var id := _pos_to_id(Vector2i(x, y))
			for dir in [Vector2i.RIGHT, Vector2i.DOWN, Vector2i.LEFT, Vector2i.UP]:
				var neighbor := Vector2i(x, y) + dir
				if _is_valid(neighbor):
					var neighbor_id := _pos_to_id(neighbor)
					astar.connect_points(id, neighbor_id, false)  # false = unidirectional? No, bidirectional

# Mark a cell as impassable:
func block_cell(cell: Vector2i) -> void:
	astar.set_point_disabled(_pos_to_id(cell), true)

func unblock_cell(cell: Vector2i) -> void:
	astar.set_point_disabled(_pos_to_id(cell), false)

func _find_path(from: Vector2i, to: Vector2i) -> PackedVector2Array:
	var from_id := _pos_to_id(from)
	var to_id := _pos_to_id(to)
	return astar.get_point_path(from_id, to_id)

func _pos_to_id(cell: Vector2i) -> int:
	return cell.y * GRID_SIZE.x + cell.x

func _is_valid(cell: Vector2i) -> bool:
	return cell.x >= 0 and cell.x < GRID_SIZE.x and \
		   cell.y >= 0 and cell.y < GRID_SIZE.y

func _draw_path(path: PackedVector2Array) -> void:
	for point in path:
		var marker := ColorRect.new()
		marker.size = Vector2(CELL_SIZE - 4, CELL_SIZE - 4)
		marker.position = point + Vector2(2, 2)
		marker.color = Color.GREEN.lerp(Color.BLUE,
			float(path.find(point)) / float(path.size()))
		add_child(marker)
```

---

### 🔮 Secret 8: Noise and Procedural Generation

```gdscript
# Godot has built-in FastNoiseLite — procedural content without external libraries!

extends Node2D

var noise := FastNoiseLite.new()

func _ready() -> void:
	# Configure noise:
	noise.noise_type = FastNoiseLite.TYPE_PERLIN
	noise.seed = randi()               # Random seed for different worlds
	noise.frequency = 0.05            # How zoomed-in the noise is
	noise.fractal_type = FastNoiseLite.FRACTAL_FBM
	noise.fractal_octaves = 5         # Detail levels
	noise.fractal_lacunarity = 2.0    # How much each octave zooms in
	noise.fractal_gain = 0.5          # How much each octave contributes

	generate_terrain()

func generate_terrain() -> void:
	var tile_map := $TileMapLayer

	for x in 100:
		for y in 100:
			var value := noise.get_noise_2d(x, y)  # Returns -1.0 to 1.0

			var tile_id: int
			if value < -0.3:
				tile_id = 0  # Deep water
			elif value < -0.1:
				tile_id = 1  # Shallow water
			elif value < 0.1:
				tile_id = 2  # Sand/beach
			elif value < 0.5:
				tile_id = 3  # Grass
			elif value < 0.7:
				tile_id = 4  # Forest
			else:
				tile_id = 5  # Mountain

			tile_map.set_cell(Vector2i(x, y), 0, Vector2i(tile_id, 0))

# ── 3D TERRAIN ────────────────────────────────────────────────────────────────
func generate_3d_terrain() -> void:
	var mesh := PlaneMesh.new()
	mesh.subdivide_width = 100
	mesh.subdivide_depth = 100

	var surface_tool := SurfaceTool.new()
	surface_tool.begin(Mesh.PRIMITIVE_TRIANGLES)

	var grid_size := 100
	var cell_size := 1.0
	var height_scale := 10.0

	# Generate vertices:
	for z in grid_size + 1:
		for x in grid_size + 1:
			var height := noise.get_noise_2d(x * 0.1, z * 0.1) * height_scale
			var vertex := Vector3(x * cell_size, height, z * cell_size)
			var uv := Vector2(float(x) / grid_size, float(z) / grid_size)
			surface_tool.set_uv(uv)
			surface_tool.add_vertex(vertex)

	# Generate indices (triangles):
	for z in grid_size:
		for x in grid_size:
			var i := z * (grid_size + 1) + x
			# Triangle 1:
			surface_tool.add_index(i)
			surface_tool.add_index(i + grid_size + 1)
			surface_tool.add_index(i + 1)
			# Triangle 2:
			surface_tool.add_index(i + 1)
			surface_tool.add_index(i + grid_size + 1)
			surface_tool.add_index(i + grid_size + 2)

	surface_tool.generate_normals()
	var terrain_mesh := surface_tool.commit()
	$TerrainMesh.mesh = terrain_mesh

func generate_noise_texture(width: int, height: int) -> ImageTexture:
	var image := Image.create(width, height, false, Image.FORMAT_RGB8)
	for x in width:
		for y in height:
			var value := (noise.get_noise_2d(x, y) + 1.0) / 2.0  # 0 to 1
			var color := Color(value, value, value)
			image.set_pixel(x, y, color)
	return ImageTexture.create_from_image(image)
```

---

### 🔮 Secret 9: `@tool` Scripts — Editor Plugins

```gdscript
# @tool scripts run inside the Godot editor — powerful for procedural content,
# custom inspector tools, and editor plugins!

@tool
extends Path2D

@export var num_points: int = 10:
	set(value):
		num_points = value
		if Engine.is_editor_hint():
			_regenerate_circle()

@export var radius: float = 100.0:
	set(value):
		radius = value
		if Engine.is_editor_hint():
			_regenerate_circle()

func _ready() -> void:
	_regenerate_circle()

func _regenerate_circle() -> void:
	if not curve:
		curve = Curve2D.new()
	curve.clear_points()

	for i in num_points:
		var angle := TAU * i / num_points
		var point := Vector2(cos(angle), sin(angle)) * radius
		var tangent := Vector2(-sin(angle), cos(angle)) * radius * 0.5
		curve.add_point(point, -tangent, tangent)

	curve.add_point(curve.get_point_position(0))  # Close the curve

# ── EDITOR PLUGIN BASICS ──────────────────────────────────────────────────────
# plugin.gd (in res://addons/my_plugin/plugin.gd):
# @tool
# extends EditorPlugin
#
# func _enter_tree() -> void:
#     add_custom_type("MyCustomNode", "Node2D",
#         preload("my_node.gd"), preload("icon.svg"))
#
# func _exit_tree() -> void:
#     remove_custom_type("MyCustomNode")
```

---

### 🔮 Secret 10: GDScript Performance — The Real Numbers

```gdscript
# Understanding what's fast and what's slow in GDScript:

# ── SLOW: avoid in hot loops ───────────────────────────────────────────────────
func slow_operations() -> void:
	# get_node() is slow — avoid in _process!
	for i in 1000:
		var x := get_node("Player").position.x  # String lookup every iteration!

	# Untyped arrays are slower:
	var untyped: Array = [1, 2, 3]
	for v in untyped:
		var doubled = v * 2

	# String formatting in hot loop:
	for i in 1000:
		print("Value: %d" % i)  # String allocation every frame!

# ── FAST: optimized patterns ───────────────────────────────────────────────────
@onready var _player: CharacterBody2D = $Player  # Cache once!
var _typed: Array[int] = [1, 2, 3]               # Typed array

func fast_operations(delta: float) -> void:
	# Use cached reference:
	var x := _player.position.x  # Direct reference — fast!

	# Typed array iteration:
	for v: int in _typed:
		var doubled: int = v * 2  # Type hints help JIT!

	# Avoid print in production:
	# if OS.is_debug_build():  print("debug info")

	# Cache frequently used values:
	var pos := position  # Local variable — faster repeated access
	var vel := velocity
	pos.x += vel.x * delta
	pos.y += vel.y * delta
	position = pos

# ── GDSCRIPT PROFILING ────────────────────────────────────────────────────────
func profile() -> void:
	# Enable in Godot Editor: Debugger → Profiler
	# Shows: GDScript, Physics, Idle time per frame
	# Sort by self time to find hotspots

	# In code:
	var start := Time.get_ticks_usec()
	_heavy_work()
	print("Time: %dµs" % (Time.get_ticks_usec() - start))

func _heavy_work() -> void:
	pass  # Your expensive code here
```

---

## 🗺️ 11. Complete Roadmap

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — FOUNDATION (Week 1-3)
├── Week 1: Godot Editor tour, Nodes, Scenes, basic GDScript syntax
├── Week 2: Variables, control flow, functions, Input handling
└── Week 3: CharacterBody2D, physics, _physics_process, move_and_slide()
    └── Project: Simple platformer with jump, wall collision, gravity

PHASE 2 — GAME SYSTEMS (Week 4-7)
├── Week 4: Signals, collision detection (Area2D), groups
├── Week 5: AnimationPlayer, Tween API, sound (AudioStreamPlayer)
├── Week 6: TileMapLayer, Resources, save/load with FileAccess
└── Week 7: UI (Control nodes, Label, Button, ProgressBar, TextureRect)
    └── Project: 2D top-down RPG with enemies, health, HUD, save system

PHASE 3 — ADVANCED GODOT (Week 8-12)
├── Week 8:  Autoloads (singletons), Game State Machines, scene management
├── Week 9:  Procedural generation (Noise), AStar pathfinding, AI behaviors
├── Week 10: Object pooling, performance optimization, profiling
├── Week 11: Shaders (canvas_item, spatial), VisualShader basics
└── Week 12: Multiplayer basics (ENet), 3D scenes (MeshInstance3D, Camera3D)
    └── Project: Complete indie-quality 2D game or 3D prototype

PHASE 4 — POLISH AND PUBLISHING (Month 4-5)
├── Month 4: Particle systems, post-processing, screen effects, accessibility
├── Month 5: Platform export (Android, iOS, Web, Desktop), CI/CD with Godot
    └── Project: Published game on itch.io or Google Play

PHASE 5 — EXPERT / 0.01% (Month 6+)
├── GDExtension (C++/Rust native extensions)
├── @tool scripts and editor plugins
├── Advanced rendering (Compute shaders, RenderingServer)
├── Contribute to Godot Engine itself (GDScript spec, documentation)
└── Build and ship a commercial game
    └── Project: Commercial release on Steam / App Store / Google Play
```

---

### 🏁 Milestone Checklist

- [ ] I can build and run a scene with custom GDScript without errors
- [ ] I understand the difference between `_process` and `_physics_process`
- [ ] I always multiply movement by `delta` for frame-rate independence
- [ ] I use `@onready` for node references instead of accessing in `_init`
- [ ] I understand signals and can create, emit, and connect custom signals
- [ ] I've built a complete character controller with jump, gravity, and collision
- [ ] I can design a finite state machine for enemy AI
- [ ] I understand Autoloads and use them for game-wide managers
- [ ] I've saved and loaded game data with `FileAccess`
- [ ] I can use the Tween API for smooth animations without `AnimationPlayer`
- [ ] I understand object pooling and use it for frequently spawned objects
- [ ] I've used `await` with signals for async game sequences
- [ ] I've built and exported a game to at least one platform
- [ ] I've profiled my game with the Godot Debugger profiler

---

## 🧩 12. Bonus Deep Insights

---

### 🔮 Mental Model: "Everything Communicates Through Signals"

The hallmark of well-written Godot code is **zero tight coupling between nodes**. A node should never need to know about another specific node's implementation. Instead, nodes communicate through:

1. **Signals** (preferred) — "I did something, anyone interested can react"
2. **Groups** — "Hey, everyone tagged 'enemy', do this thing"
3. **Autoloads** — "Global state/services everyone can access"
4. **Resources** — "Shared data that multiple nodes read/write"

When your Player node calls `$HUD.update_health(health)` directly, you've created a dependency — moving the HUD breaks the Player script. When Player emits `health_changed.emit(health)` and the HUD connects to that signal, they're completely independent. You could remove the HUD entirely and the Player still works perfectly.

This architecture — nodes as islands, signals as communication channels — is what makes Godot projects scalable from game jams to commercial products.

---

### 🤫 Deep Insight 1: GDScript is Not Python

Despite the similar syntax, GDScript has crucial differences:

- **Indentation**: GDScript uses tabs; mixing tabs and spaces causes syntax errors
- **True integer division**: In Python 3, `5 / 2 = 2.5`. In GDScript, `5 / 2 = 2` (integer division!). Use `5.0 / 2` for float result.
- **No list comprehensions**: GDScript has `.map()`, `.filter()`, `.reduce()` instead
- **No `None` or `null`**: GDScript uses `null` (not `None`) — and it's a special object, not absence of object
- **No multiple assignment**: `a, b = b, a` doesn't work. Use a temp variable.
- **No `*args` or `**kwargs`**: Functions have fixed signatures; use Arrays/Dictionaries for variable args
- **`and`/`or`/`not`** work the same, but `!` also works for `not`
- **Snake_case everything**: Variables, functions, signals — all snake_case in GDScript

---

### 🤫 Deep Insight 2: The Hidden Cost of Dynamic Typing

GDScript allows untyped variables: `var x = 42`. Under the hood, Godot stores `x` as a `Variant` — a union type that can hold anything. Every operation on a `Variant` requires:
1. Checking what type is stored
2. Extracting the value
3. Performing the operation
4. Wrapping the result in another `Variant`

With type hints: `var x: int = 42`, Godot knows at compile time that `x` is always an `int`. Operations are direct — no type checking, no boxing. In tight loops, this can be **2-3× faster**.

The rule: **always use type hints in scripts that run every frame**. Anywhere else, type hints are optional but help with IDE support.

---

### 🧠 The Big Picture — Godot/GDScript in the Modern Ecosystem

```
GDScript's evolution:
  Godot 2.x: First stable GDScript — Python-like but primitive
  Godot 3.x: Typed GDScript, GDNative (C++ extension API)
  Godot 4.0: Complete rewrite — lambdas, await, reified types,
              GDExtension (replaces GDNative), improved profiler
  Godot 4.2+: Typed arrays, first-class Callables, better LSP
  Godot 4.4+: Typed dictionaries, runtime class creation
  Future: Godot 5 — GPU-driven rendering, better C# integration

The Godot game dev ecosystem in 2025:
  Engine:     Godot 4.x — Vulkan/OpenGL renderer, web-first
  Scripting:  GDScript (primary), C# (.NET), C++ (GDExtension)
  2D:         TileMapLayer, 2D physics, 2D lighting, 2D particles
  3D:         WorldEnvironment, GPUParticles3D, NavigationMesh3D
  Audio:      AudioStreamPlayer, AudioBus, AudioEffect processing
  Networking: ENet, WebSocket, WebRTC built-in
  Physics:    Godot Physics (default) + Jolt Physics (addon)
  VFX:        CPUParticles2D/3D, GPUParticles2D/3D, BeamEffect
  AI:         NavigationAgent2D/3D, AStar2D/3D, custom behavior trees
  Shader:     GLSL-like .gdshader, VisualShader node graph
  Plugins:    GitHub community — godotengine.org/asset-library

Why developers choose Godot:
  ✅ 100% free and open source — no royalties, forever
  ✅ Small download (50-200MB vs Unity's 5GB+ install)
  ✅ Fast startup — editor loads in seconds
  ✅ Git-friendly — .tscn files are text, diffable
  ✅ No telemetry, no accounts, no subscription
  ✅ Exports to: Windows, macOS, Linux, Android, iOS, Web, consoles*
  ✅ Extraordinary community support and documentation

Godot vs Unity vs Unreal:
  Godot:   Free forever, best 2D, great 3D, easy to learn
  Unity:   Industry standard for mobile, C# ecosystem, more jobs
  Unreal:  Best 3D graphics, AAA industry, C++ complexity
  For Indie/Jam/Education: Godot is the clear winner in 2025

Career with Godot/GDScript:
  → Indie game developer (most common)
  → Game jam developer (#1 jam engine worldwide)
  → Educational game developer
  → Godot contributor / plugin author
  → Mobile game developer (Android + iOS from one codebase)
  → Godot Engine developer (C++ contribution)
```

---

## 📌 13. Summary (Quick Revision & Cheat Sheet)

---

### Core Concepts (1-line each)

| Concept              | What It Means                                                              |
|----------------------|----------------------------------------------------------------------------|
| Node                 | Everything in Godot — the basic building block of all game objects         |
| Scene                | A reusable tree of Nodes saved as a `.tscn` file                          |
| `@onready`           | Initialize node references safely when `_ready()` is called               |
| `@export`            | Make a variable editable in the Godot Inspector                           |
| `_process(delta)`    | Called every visual frame — use for visuals, input checking                |
| `_physics_process`   | Called every physics frame — use for movement and collision                |
| `delta`              | Time since last frame — ALWAYS multiply movement by delta                  |
| Signal               | Event system — emit when something happens, connect to react              |
| `queue_free()`       | Safe way to delete nodes — deferred to end of frame                       |
| `move_and_slide()`   | CharacterBody physics — handles collisions and slopes automatically        |
| `await`              | Wait for a signal or timer without blocking the whole game                |
| Autoload             | Global singleton — accessible from any script in the project              |
| Resource             | Data container — save/load as `.tres`, share between nodes                |
| Tween                | `create_tween()` — smooth property animations in code                     |

---

### The 10 Things to Remember

1. ✅ **ALWAYS multiply movement by `delta`** — frame-rate independence is non-negotiable
2. ✅ **Use `@onready` for all node references** — never access `$Node` at class level
3. ✅ **`queue_free()` not `free()`** — safe deletion at end of frame
4. ✅ **`set_deferred("disabled", true)` for CollisionShape changes** — never direct in physics
5. ✅ **Physics code in `_physics_process`, visuals in `_process`** — never mix these
6. ✅ **Emit signals to decouple systems** — nodes should know as little about each other as possible
7. ✅ **Use type hints everywhere possible** — `var hp: int = 100` is 2-3× faster in loops
8. ✅ **`preload()` at top of scripts** — not inside `_process()` (loaded every frame!)
9. ✅ **Groups for broadcast operations** — don't store arrays of references manually
10. ✅ **Use `await signal`** for game sequences — cleaner than state machine callbacks

---

### Quick Reference Cheat Sheet

```gdscript
# ── SCRIPT TEMPLATE ────────────────────────────────────────────────────────────
extends CharacterBody2D
class_name Player

signal died
signal score_changed(new_score: int)

const SPEED: float = 200.0
const JUMP_VELOCITY: float = -400.0
var gravity := ProjectSettings.get_setting("physics/2d/default_gravity") as float

@export var health: int = 100
@export var move_speed: float = SPEED

@onready var sprite    := $Sprite2D
@onready var anim      := $AnimationPlayer
@onready var collision := $CollisionShape2D

func _ready() -> void:
    print("Ready! Health: ", health)

func _process(delta: float) -> void:
    # Visuals, non-physics input
    sprite.flip_h = velocity.x < 0

func _physics_process(delta: float) -> void:
    if not is_on_floor():
        velocity.y += gravity * delta
    var dir := Input.get_axis("move_left", "move_right")
    velocity.x = dir * move_speed
    move_and_slide()

func _input(event: InputEvent) -> void:
    if event.is_action_pressed("jump") and is_on_floor():
        velocity.y = JUMP_VELOCITY

# ── CORE MOVEMENT ─────────────────────────────────────────────────────────────
# move_and_slide()              — for CharacterBody — handles collisions
# is_on_floor() / is_on_wall() — state checks after move_and_slide
# get_floor_angle()             — angle of surface below
# apply_impulse(Vector2)        — for RigidBody2D

# ── NODE ACCESS ───────────────────────────────────────────────────────────────
# $NodeName                     — get direct child
# $"Path/To/Node"               — get nested node
# get_node("path")              — same as $
# get_node_or_null("path")      — returns null if not found
# find_child("name", true)      — search entire subtree
# get_parent()                  — parent node
# get_tree().get_root()         — scene root
# get_tree().get_nodes_in_group("group")  — all nodes in group

# ── SIGNALS ────────────────────────────────────────────────────────────────────
# signal my_signal                     — declare
# signal my_signal(value: int)         — declare with data
# my_signal.emit()                     — fire
# my_signal.emit(42)                   — fire with data
# other.my_signal.connect(_on_signal)  — listen
# other.my_signal.disconnect(_on_it)   — stop listening
# await other.my_signal                — wait async
# await get_tree().create_timer(1.0).timeout  — wait 1 second

# ── INPUT ────────────────────────────────────────────────────────────────────
# Input.is_action_just_pressed("action")   — true on first frame
# Input.is_action_pressed("action")        — true every frame held
# Input.is_action_just_released("action")  — true on release frame
# Input.get_axis("neg", "pos")             — -1.0 to 1.0 float
# Input.get_vector("l","r","u","d")        — Vector2 normalized
# Input.is_key_pressed(KEY_SPACE)          — specific key
# get_global_mouse_position()              — mouse in world coords

# ── SCENE MANAGEMENT ─────────────────────────────────────────────────────────
# get_tree().change_scene_to_file("res://scenes/game.tscn")
# get_tree().reload_current_scene()
# get_tree().paused = true/false
# var scene = preload("res://scene.tscn") as PackedScene
# var node  = scene.instantiate()
# add_child(node)
# node.queue_free()

# ── TWEEN ────────────────────────────────────────────────────────────────────
# var t := create_tween()
# t.tween_property(node, "position", Vector2(100,0), 1.0)
# t.tween_property(node, "position:x", 100.0, 1.0)     # Sub-property!
# t.tween_interval(0.5)                                  # Wait
# t.tween_callback(func(): print("done"))               # Callback
# t.set_loops() / .set_parallel(true)
# t.set_ease(Tween.EASE_OUT).set_trans(Tween.TRANS_BOUNCE)
# await t.finished

# ── MATH & USEFUL FUNCTIONS ──────────────────────────────────────────────────
# Vector2(x, y) / Vector3(x, y, z)
# vec.length() / vec.normalized() / vec.dot(other) / vec.cross(other)
# vec.distance_to(other) / vec.angle_to(other) / vec.lerp(to, t)
# lerp(a, b, t)         — linear interpolation
# lerp_angle(a, b, t)   — angle lerp (handles wrap-around)
# clamp(value, min, max)
# move_toward(from, to, delta)   — move by at most delta
# remap(value, in_min, in_max, out_min, out_max)
# smoothstep(from, to, t)
# sin(angle) / cos(angle) / atan2(y, x)
# deg_to_rad(degrees) / rad_to_deg(radians)
# PI / TAU / INF / NAN
# randf() / randf_range(0.0, 1.0) / randi() / randi_range(0, 100)
# snapped(value, step)           — round to nearest step
# abs(value) / sign(value) / pow(base, exp) / sqrt(value)
# round(value) / floor(value) / ceil(value)
# max(a, b) / min(a, b)

# ── STRINGS ──────────────────────────────────────────────────────────────────
# "Hello, %s! You have %d HP" % ["Aryan", 100]
# str(42) / int("42") / float("3.14")
# s.to_upper() / s.to_lower()
# s.begins_with("pre") / s.ends_with("suf")
# s.contains("sub") / s.find("sub")
# s.replace("old", "new") / s.strip_edges()
# s.split(",") / ",".join(["a","b","c"])
# s.substr(start, length) / s.length()
# s.format({"name": "Aryan"})   — "{name} rocks!"

# ── ARRAYS ───────────────────────────────────────────────────────────────────
# var arr: Array[int] = [1, 2, 3]
# arr.append(4) / arr.push_front(0) / arr.insert(i, v)
# arr.pop_back() / arr.pop_front() / arr.remove_at(i)
# arr.erase(value) / arr.clear()
# arr.size() / arr.is_empty() / arr.has(v)
# arr.sort() / arr.shuffle() / arr.reverse()
# arr.find(v) / arr.count(v) / arr.slice(from, to)
# arr.map(func(v): return v*2)
# arr.filter(func(v): return v > 0)
# arr.reduce(func(acc, v): return acc+v, 0)
# arr.any(func(v): return v > 5)
# arr.all(func(v): return v > 0)

# ── SAVE & LOAD ───────────────────────────────────────────────────────────────
# SAVE:
# var f := FileAccess.open("user://save.json", FileAccess.WRITE)
# f.store_string(JSON.stringify(data))
# f.close()
# LOAD:
# if FileAccess.file_exists("user://save.json"):
#   var f := FileAccess.open("user://save.json", FileAccess.READ)
#   var data = JSON.parse_string(f.get_as_text())
#   f.close()

# ── USEFUL NODE TYPES QUICK REFERENCE ────────────────────────────────────────
# CharacterBody2D     — player, NPC physics
# RigidBody2D         — fully simulated physics objects
# StaticBody2D        — immovable platforms, walls
# Area2D              — triggers, hitboxes, pickups
# Sprite2D            — displays a texture
# AnimatedSprite2D    — frame-by-frame animation
# AnimationPlayer     — timeline animations
# AudioStreamPlayer   — plays audio
# Timer               — countdown, repeated timer
# Camera2D            — 2D camera with smoothing
# Label               — text display
# Button              — clickable button
# TextureProgressBar  — health/progress bars
# Control             — base UI element
# CanvasLayer         — UI that stays fixed on screen
# TileMapLayer        — tile-based maps
# NavigationAgent2D   — pathfinding for characters
# CPUParticles2D      — particle effects (CPU-based)
# Line2D              — draws lines
# Polygon2D           — draws polygons
# CollisionShape2D    — defines hitbox shape
# RayCast2D           — detects objects in a line
```

---

### What's Next?

After mastering GDScript and Godot, your natural paths:

- 📘 **C# in Godot** — For larger teams, more tooling, Unity migrants — same Godot but with .NET ecosystem
- 📘 **GDExtension** — Write performance-critical C++ or Rust plugins that integrate seamlessly
- 📘 **Godot 3D** — Cameras, lighting, MeshInstance3D, NavigationMesh3D, XR/VR
- 📘 **GLSL Shaders** — `.gdshader` for custom visual effects, dissolve, outline, distortion
- 📘 **Flame Engine (Dart)** — If you want Flutter-based game dev in Dart
- 📘 **Godot Engine Contribution** — The engine is open source — contribute features, fixes, docs

---

> 💬 *"The goal of Godot is to let developers focus on making games, not fighting their tools."*
> — Juan Linietsky, Godot Co-creator

> 💬 *"GDScript was designed to be simple enough to learn in a weekend but powerful enough to ship commercial games."*
> — Godot Documentation

> 💬 *"Godot's node-signal architecture is the cleanest game programming model I've ever used. Once you understand it, everything else makes sense."*
> — The Godot Community

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: GDScript — Complete Language & Godot Mastery | Version: 1.0*
*Sections: 13 | Level: Beginner → 0.01% Elite*
