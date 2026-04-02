# 💎 Ruby — The Ultimate Master Guide
### From Zero to 0.01% Expert — Every Concept, Metaprogramming Secret, Rail & Hidden Power

> 📘 **The most complete Ruby guide ever written — beginner to elite.**
>
> 🎯 *Who is this for?* Anyone who wants to go from writing Ruby to **mastering** it — the language that prizes programmer happiness above all else.
> ⏱️ *Time to complete:* Self-paced — days to months
> 🛠️ *What you'll gain:* Every syntax rule, OOP pattern, metaprogramming trick, concurrency model, and 0.01% hidden secret that separates an elite Rubyist from the rest.

---

## Table of Contents

1. [🧠 What is Ruby?](#1-what-is-ruby-super-simple)
2. [🌍 Why Ruby Exists & Endures](#2-why-ruby-exists--endures)
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

## 🧠 1. What is Ruby? (Super Simple)

### The 12-Year-Old Explanation

Imagine if programming languages were tools. Most tools are designed to be efficient — they do the job, but they don't care about whether the person using them enjoys the experience. **Ruby was designed differently.** Its creator, **Yukihiro "Matz" Matsumoto**, designed Ruby with one guiding principle: **make programmers happy.**

Ruby was created in Japan in 1995. Matz blended his favorite features from Perl, Smalltalk, Eiffel, Ada, and Lisp into one elegant language. The goal wasn't to make the fastest language, or the most technically sophisticated — it was to make a language that felt natural, expressive, and joyful to write. When you write Ruby, the code reads almost like English.

Ruby became world-famous when **David Heinemeier Hansson** (DHH) used it to build Basecamp and then extracted the framework as **Ruby on Rails** in 2004. Rails proved that a small team could build a full-featured web application in a fraction of the time it would take in Java or PHP. GitHub, Shopify, Airbnb, Twitter (originally), and thousands of startups were built on Ruby on Rails.

### Real-Life Analogy

💡 **Think of it like this:**
Programming languages are kitchens. C is a professional kitchen with knives, fire, and zero safety equipment — extremely powerful but dangerous. Java is an IKEA kitchen — every piece labeled, assembly instructions included, very structured. Python is a food truck — portable, simple, great for experiments.

**Ruby is a Japanese kitchen designed by a master chef.** Every knife is perfectly balanced. Every surface is at the right height. Every tool is where your hand naturally reaches. Cooking there feels effortless — not because it's simple, but because it was designed around the human experience. You spend less time fighting the kitchen and more time creating.

### One-Line Definition

> **Ruby** is a dynamic, interpreted, open-source, object-oriented programming language focused on simplicity and programmer productivity, where everything is an object, code reads like natural language, and metaprogramming makes the language infinitely malleable.

---

## 🌍 2. Why Ruby Exists & Endures

### The Problem It Solved

In the mid-1990s, Matz was dissatisfied with the available scripting languages. Perl was powerful but ugly. Python was clean but felt too restricted. Smalltalk was beautiful in concept but impractical. He wanted a language that combined the power of Perl with the elegance of Smalltalk — something that would feel natural to write, expressive to read, and powerful enough to build real systems.

Matz has famously said: **"Ruby is designed to make programmers happy."** He prioritized developer joy over machine efficiency — a radical idea that paid off enormously when Rails demonstrated what a happy language could produce.

### Where Ruby Endures in 2025

| Domain                        | How Ruby Is Used                                                          |
|-------------------------------|---------------------------------------------------------------------------|
| Web Applications (Rails)      | Shopify ($billions GMV), GitHub, Basecamp, Airbnb (originally) — Rails    |
| E-commerce                    | Shopify platform — the world's largest Ruby deployment                    |
| Developer Tools               | Homebrew (macOS package manager), Fastlane (mobile CI/CD) — all Ruby     |
| Scripting & Automation        | Chef, Puppet (infrastructure automation) — written in Ruby               |
| API Backends                  | Sinatra microservices, Grape API, Hanami — lightweight Ruby web           |
| Testing                       | RSpec, Cucumber — behavior-driven development (Ruby is THE testing lang) |
| DevOps                        | Vagrant, Capistrano (deployment), Ansible (uses Ruby YAML)               |
| CLI Tools                     | Thor, GLI — Ruby builds beautiful command-line interfaces                 |
| Data & Science (niche)        | Numo, Rubex — Ruby for scientific computing                               |
| Education                     | Why the Lucky Stiff's work, Codecademy — Ruby teaches programming joy    |

### Why YOU Should Learn It Deeply

1. **Rails is still dominant** — Shopify processes more e-commerce than anyone except Amazon, and it runs on Ruby on Rails.
2. **The most expressive language for its purpose** — reading Ruby code is like reading specifications, not implementation.
3. **Metaprogramming mastery** — understanding Ruby's metaprogramming teaches you how programming languages work at a fundamental level.
4. **RSpec changed testing** — Ruby's testing culture is the best in any language community; learning it makes you a better tester in every language.
5. **Gems ecosystem** — 170,000+ gems on RubyGems.org; the ecosystem for web tooling is mature and battle-tested.

---

## 🧱 3. Core Fundamentals (Beginner Level)

> 🎯 *Goal: Build an unshakeable foundation. Every concept here is critical.*

---

### Concept 1: Ruby Setup, IRB & Running Programs

```ruby
# ── INSTALLATION — always use a version manager! ───────────────────────────
# rbenv (recommended):
# brew install rbenv ruby-build       (macOS)
# rbenv install 3.3.0
# rbenv global 3.3.0
# ruby --version                      # Check version

# RVM (alternative):
# \curl -sSL https://get.rvm.io | bash
# rvm install 3.3.0
# rvm use 3.3.0 --default

# ── IRB — Interactive Ruby (the REPL) ─────────────────────────────────────
# Just type `irb` in terminal:
# irb(main):001> 2 + 2
# => 4
# irb(main):002> "hello".upcase
# => "HELLO"
# irb(main):003> exit

# ── RUNNING RUBY PROGRAMS ─────────────────────────────────────────────────
# ruby script.rb              # Run a file
# ruby -e "puts 'hi'"        # Execute string directly
# ruby -c script.rb           # Check syntax only (no execution)
# ruby -w script.rb           # Enable warnings
# ruby -I lib script.rb       # Add lib to load path

# ── YOUR FIRST RUBY PROGRAM ───────────────────────────────────────────────
# hello.rb

# Output:
puts "Hello, World!"            # puts adds newline
print "No newline here"         # print doesn't add newline
p "Shows quotes: for debug"     # p shows object representation
pp [1, {a: 2}, :symbol]         # pp pretty-prints complex structures

# String interpolation (use double quotes for interpolation):
name = "Aryan"
age  = 17
puts "Hello, #{name}! You are #{age} years old."
puts "2 + 2 = #{2 + 2}"       # Expressions work inside #{}!
puts "Today: #{Time.now}"

# Single quotes — NO interpolation, mostly literal:
puts 'Hello, #{name}'          # Prints literally: Hello, #{name}
puts 'Tab: \t Newline: \n'     # No escape sequences (except \\ and \')

# Heredoc — multi-line strings:
message = <<~HEREDOC
  Hello, #{name}!
  This is a multi-line string.
  The ~ removes leading whitespace.
HEREDOC
puts message

# Comments:
# Single line comment
=begin
Multi-line comment
(rarely used in practice)
=end

# ── GEM ECOSYSTEM ─────────────────────────────────────────────────────────
# Gems are Ruby libraries — installed via RubyGems:
# gem install rails             # Install a gem
# gem install bundler           # Bundler — dependency management
# gem list                      # List installed gems
# gem search rails              # Search gems

# Bundler — manages gem dependencies for projects:
# bundle init                   # Create Gemfile
# bundle install                # Install Gemfile dependencies
# bundle exec ruby script.rb    # Run in bundled environment
# bundle update rails           # Update specific gem

# Gemfile:
# source 'https://rubygems.org'
# ruby '3.3.0'
# gem 'rails', '~> 7.1'        # ~> means >= 7.1 AND < 8.0
# gem 'pg'
# gem 'puma'
# group :development, :test do
#   gem 'rspec-rails'
#   gem 'factory_bot_rails'
# end
```

---

### Concept 2: Variables, Data Types & Ruby's Type Philosophy

```ruby
# ── EVERYTHING IS AN OBJECT in Ruby ───────────────────────────────────────
# Unlike most languages, even primitives are full objects with methods!

1.class          # => Integer
1.0.class        # => Float
true.class       # => TrueClass
nil.class        # => NilClass
"hello".class    # => String
:symbol.class    # => Symbol
[].class         # => Array
{}.class         # => Hash
(1..5).class     # => Range

# Even methods and classes are objects!
1.methods        # => List of all methods on Integer
1.respond_to?(:+) # => true — does Integer respond to + ?
42.to_s          # => "42" — convert to string
"42".to_i        # => 42  — convert to integer
3.14.to_i        # => 3   — truncates
nil.to_s         # => ""  — nil converts to empty string
nil.to_a         # => []  — nil converts to empty array
nil.to_i         # => 0   — nil converts to 0

# ── VARIABLE TYPES ────────────────────────────────────────────────────────
# local_variable    — lowercase or underscore, scope: method/block
# @instance_var     — starts with @, scope: object instance
# @@class_var       — starts with @@, scope: class and subclasses
# $global_var       — starts with $, scope: everywhere (avoid!)
# CONSTANT          — UPPERCASE, defined once (warning if changed)
# ClassName         — CamelCase is also a constant

local = "I'm local"
@instance = "I'm instance"
@@class_shared = "I'm class-shared"
$global = "I'm global (avoid me!)"
MAX_SIZE = 1000
PI = 3.14159

# ── INTEGERS ──────────────────────────────────────────────────────────────
# Ruby has ARBITRARY PRECISION integers — no overflow!
big = 2 ** 100               # Works! No overflow
puts big                     # 1267650600228229401496703205376

# Integer methods:
42.even?                     # => true
41.odd?                      # => true
-5.abs                       # => 5
255.to_s(16)                 # => "ff" (base 16)
255.to_s(2)                  # => "11111111" (base 2)
10.gcd(6)                    # => 2 (greatest common divisor)
10.lcm(6)                    # => 30 (least common multiple)
42.digits                    # => [2, 4] (digits in reverse)
42.digits(16)                # => [10, 2] (digits in base 16)
1_000_000                    # Underscores for readability

# Integer iteration (unique to Ruby!):
5.times { |i| print "#{i} " }    # 0 1 2 3 4
1.upto(5) { |i| print "#{i} " }  # 1 2 3 4 5
5.downto(1) { |i| print "#{i} " }# 5 4 3 2 1
1.step(10, 2) { |i| print "#{i} " } # 1 3 5 7 9

# ── FLOATS ────────────────────────────────────────────────────────────────
3.14.round(2)    # => 3.14
3.14159.ceil     # => 4
3.14159.floor    # => 3
3.14.nan?        # => false
(0.0/0.0).nan?   # => true  (NaN)
(1.0/0.0).infinite? # => 1  (positive infinity)

# ── SYMBOLS ───────────────────────────────────────────────────────────────
# Symbols are immutable, unique identifiers — like a constant string
# They are the SAME OBJECT every time (unlike strings!)
:hello.object_id == :hello.object_id  # => true (same object!)
"hello".object_id == "hello".object_id # => false (different objects)

# Use symbols for:
# - Hash keys (most common: { name: "Aryan" } is same as { :name => "Aryan" })
# - Method references
# - Enum-like values (status: :active, :pending, :inactive)

:hello.to_s       # => "hello"
"hello".to_sym    # => :hello
:hello.upcase     # => :HELLO
:hello.length     # => 5

# ── NIL ───────────────────────────────────────────────────────────────────
# nil is Ruby's null — also a full object!
nil.nil?          # => true
nil.to_s          # => ""
nil.to_a          # => []
nil.to_i          # => 0
nil == nil        # => true
nil == false      # => false (nil is NOT false!)
# Only nil and false are falsy in Ruby. 0, "", [] are ALL truthy!

# Safe navigation operator (Ruby 2.3+):
user = nil
user&.name        # => nil (no NoMethodError!)
user&.name&.upcase # => nil (chained safe navigation)

# ── RANGES ────────────────────────────────────────────────────────────────
(1..5)            # Inclusive: 1, 2, 3, 4, 5
(1...5)           # Exclusive: 1, 2, 3, 4
('a'..'z')        # Character range
(1..Float::INFINITY) # Infinite range

(1..5).to_a       # => [1, 2, 3, 4, 5]
(1..10).include?(7) # => true
(1..10).sum       # => 55
(1..10).min       # => 1
(1..10).max       # => 10
(1..5).step(2).to_a # => [1, 3, 5]
(1..100).select(&:even?).first(5) # => [2, 4, 6, 8, 10]
```

---

### Concept 3: Strings — The Most Expressive in Any Language

```ruby
# ── STRING CREATION ────────────────────────────────────────────────────────
s1 = "double quotes — interpolation works #{1+1}"
s2 = 'single quotes — literal'
s3 = %q(like single quotes)     # Alternative single-quote syntax
s4 = %Q(like double quotes #{Time.now}) # Alternative double-quote
s5 = %(default is double-quote #{2+2})
s6 = <<~TEXT
  Heredoc — great for multi-line
  strings with #{name} interpolation
TEXT

# ── STRING METHODS — EXHAUSTIVE ────────────────────────────────────────────
s = "Hello, World!"

# Information:
s.length            # => 13
s.size              # => 13 (alias)
s.empty?            # => false
"".empty?           # => true
s.include?("World") # => true
s.start_with?("Hello") # => true
s.end_with?("!")    # => true
s.count("l")        # => 3 (count occurrences)
s.index("o")        # => 4 (first occurrence)
s.rindex("o")       # => 8 (last occurrence)

# Transformation (returns NEW string — strings are mutable but these create new ones):
s.upcase            # => "HELLO, WORLD!"
s.downcase          # => "hello, world!"
s.capitalize        # => "Hello, world!"
s.swapcase          # => "hELLO, wORLD!"
s.reverse           # => "!dlroW ,olleH"
s.strip             # => "Hello, World!" (removes leading/trailing whitespace)
s.lstrip            # => removes leading whitespace
s.rstrip            # => removes trailing whitespace
s.chomp             # => removes trailing \n (for input)
s.chop              # => removes last character
s.squeeze           # => squeeze consecutive duplicate chars
s.squeeze("l")      # => "Helo, World!" (squeeze only 'l's)

# Bang! methods — modify in place:
s2 = "hello"
s2.upcase!          # Modifies s2 directly! Returns nil if no change.
s2.gsub!(/[aeiou]/, "*")  # In-place substitution

# Searching and replacing:
s.sub("World", "Ruby")     # => "Hello, Ruby!" (first occurrence)
s.gsub("l", "L")           # => "HeLLo, WorLd!" (all occurrences)
s.gsub(/[aeiou]/i, "*")    # => "H*ll*, W*rld!" (regex replace)
s.gsub(/(\w+)/) { |m| m.upcase } # Block version for complex replacement

# Splitting and joining:
"a,b,c".split(",")          # => ["a", "b", "c"]
"hello".split("")           # => ["h", "e", "l", "l", "o"] (chars)
"hello world".split          # => ["hello", "world"] (splits on whitespace)
"hello world".split(" ", 2) # => ["hello", "world"] (max 2 parts)
["a", "b", "c"].join(", ")  # => "a, b, c"

# Slicing:
s[0]                # => "H" (character at index)
s[0, 5]             # => "Hello" (start, length)
s[7..]              # => "World!" (from index 7 to end)
s[7..11]            # => "World"
s[-6..-1]           # => "orld!" (negative indices from end)
s[/\w+/]            # => "Hello" (first regex match)

# Encoding:
"café".encoding     # => #<Encoding:UTF-8>
"hello".bytes       # => [104, 101, 108, 108, 111]
"hello".chars       # => ["h", "e", "l", "l", "o"]
"hello".each_char { |c| print c } # Iterate chars

# Formatting:
"%.2f" % 3.14159    # => "3.14" (sprintf-style)
"%s is %d" % ["Aryan", 17] # => "Aryan is 17"
"hello".center(11, "-")    # => "---hello---"
"hello".ljust(10, ".")     # => "hello....."
"hello".rjust(10, ".")     # => ".....hello"

# Type conversion:
"42".to_i           # => 42
"3.14".to_f         # => 3.14
"FF".to_i(16)       # => 255 (hex to int)
"42abc".to_i        # => 42 (stops at first non-digit)
Integer("42")       # => 42 (strict — raises on "42abc")
Float("3.14")       # => 3.14 (strict)

# Frozen strings (performance optimization):
str = "hello".freeze  # Immutable! Any modification raises FrozenError
# Or at file top: # frozen_string_literal: true
# Makes ALL string literals in the file frozen automatically
```

---

### Concept 4: Control Flow

```ruby
# ── IF / ELSIF / ELSE ─────────────────────────────────────────────────────
score = 87

if score >= 90
  puts "A"
elsif score >= 80
  puts "B"
elsif score >= 70
  puts "C"
else
  puts "F"
end

# One-liner if (modifier form — very Rubylike!):
puts "Adult!" if age >= 18
puts "Negative!" unless score >= 0  # unless = if not

# Inline ternary:
grade = score >= 50 ? "Pass" : "Fail"

# ── CASE / WHEN (Ruby's switch — but far more powerful!) ──────────────────
day = "Monday"
result = case day
         when "Saturday", "Sunday" then "Weekend"
         when "Monday".."Friday"   then "Weekday"  # Range matching!
         else "Unknown"
         end

# Case with types (uses ===):
def describe(obj)
  case obj
  when Integer   then "an integer: #{obj}"
  when Float     then "a float: #{obj}"
  when String    then "a string of length #{obj.length}"
  when Array     then "an array of #{obj.size} items"
  when NilClass  then "nothing (nil)"
  when /^\d+$/   then "a numeric string"  # Regex matching!
  when ->(x) { x > 100 } then "large number (lambda)"
  else "something else"
  end
end

describe(42)        # => "an integer: 42"
describe("hello")   # => "a string of length 5"
describe([1,2,3])   # => "an array of 3 items"
describe(nil)       # => "nothing (nil)"

# case without subject — acts like if/elsif:
case
when score >= 90 then puts "A"
when score >= 80 then puts "B"
else puts "F"
end

# ── LOOPS ─────────────────────────────────────────────────────────────────
# while:
i = 0
while i < 5
  print "#{i} "
  i += 1
end

# until (while not):
until i >= 5
  i += 1
end

# loop (infinite — use break to exit):
loop do
  input = gets.chomp
  break if input == "quit"
  puts input.upcase
end

# for..in (rare — prefer each):
for i in 1..5
  print "#{i} "
end

# ── ITERATORS — The Ruby Way ───────────────────────────────────────────────
# Ruby uses iterators, not traditional loops:
[1,2,3,4,5].each { |n| print "#{n} " }
[1,2,3,4,5].each_with_index { |n, i| puts "#{i}: #{n}" }
[1,2,3,4,5].each_with_object([]) { |n, acc| acc << n * 2 }
5.times { |i| print "#{i} " }
1.upto(5) { |i| print "#{i} " }

# next (like continue) and break:
(1..10).each do |i|
  next if i.even?   # Skip even numbers
  break if i > 7    # Stop at 7
  print "#{i} "     # Prints: 1 3 5 7
end

# ── EXCEPTIONS ────────────────────────────────────────────────────────────
begin
  result = 10 / 0
  File.read("missing.txt")
rescue ZeroDivisionError => e
  puts "Math error: #{e.message}"
rescue Errno::ENOENT => e
  puts "File not found: #{e.message}"
rescue StandardError => e    # Catch-all for standard errors
  puts "Something went wrong: #{e.message}"
  raise                      # Re-raise the same exception
ensure
  puts "This always runs (like finally)"
end

# retry — try the block again:
attempts = 0
begin
  attempts += 1
  result = unreliable_api_call()
rescue NetworkError
  retry if attempts < 3
  raise "Failed after 3 attempts"
end

# Custom exceptions:
class InsufficientFundsError < StandardError
  def initialize(amount, balance)
    @amount = amount
    @balance = balance
    super("Cannot withdraw #{amount}. Balance is #{balance}.")
  end

  attr_reader :amount, :balance
end

raise InsufficientFundsError.new(100, 50)

# Inline rescue (one-liner):
value = Integer("abc") rescue 0  # Returns 0 if exception raised
```

---

### Concept 5: Methods — Every Form and Feature

```ruby
# ── BASIC METHOD DEFINITION ────────────────────────────────────────────────
def greet(name)
  "Hello, #{name}!"  # Last expression is return value (implicit return)
end

puts greet("Aryan")  # "Hello, Aryan!"

# Parentheses are optional for method calls (when unambiguous):
puts greet "Aryan"  # Same! (though parentheses preferred for clarity)

# ── DEFAULT ARGUMENTS ─────────────────────────────────────────────────────
def power(base, exp = 2)
  base ** exp
end
power(3)      # => 9 (uses default exp=2)
power(3, 3)   # => 27

# ── KEYWORD ARGUMENTS (Ruby 2.0+) ─────────────────────────────────────────
def create_user(name:, email:, role: :user, active: true)
  { name: name, email: email, role: role, active: active }
end

create_user(name: "Aryan", email: "a@b.com")             # Uses defaults
create_user(email: "a@b.com", name: "Aryan", role: :admin) # Any order!

# Double splat for arbitrary keyword args:
def log(message, **options)
  puts "[#{options[:level] || 'INFO'}] #{message}"
  puts "  Context: #{options.except(:level)}" if options.size > 1
end
log("Starting", level: :warn, request_id: "abc123")

# ── SPLAT OPERATOR (*) ────────────────────────────────────────────────────
def sum(*numbers)           # Collects all args into array
  numbers.sum
end
sum(1, 2, 3, 4, 5)         # => 15

# Splat in method calls — expand array into args:
args = [1, 2, 3]
sum(*args)                  # Same as sum(1, 2, 3)

# Mix of positional, splat, keyword:
def complex(first, *middle, last, key:)
  [first, middle, last, key]
end
complex(1, 2, 3, 4, 5, key: "value")
# => [1, [2, 3, 4], 5, "value"]

# ── BLOCKS, PROCS, AND LAMBDAS ────────────────────────────────────────────
# Block — anonymous code attached to a method call:
[1,2,3].each { |n| puts n }       # Single-line block
[1,2,3].each do |n|               # Multi-line block
  puts n * 2
end

# yield — call the block from inside a method:
def with_logging(label)
  puts "Starting #{label}"
  result = yield                   # Calls the block!
  puts "Finished #{label}: #{result}"
  result
end

with_logging("computation") { 2 ** 10 }  # Prints messages, returns 1024

# block_given? — check if a block was provided:
def optional_block
  if block_given?
    yield 42
  else
    "No block given"
  end
end

# &block — capture block as explicit Proc argument:
def apply_twice(value, &block)
  block.call(block.call(value))
end
apply_twice(2) { |n| n * 3 }  # => 18

# Proc — a reusable block:
doubler = Proc.new { |n| n * 2 }
tripler = proc { |n| n * 3 }   # proc {} is shorthand
doubler.call(5)                 # => 10
doubler.(5)                     # => 10 (alternate call syntax)
doubler[5]                      # => 10 (alternate call syntax)

# Lambda — like Proc but stricter argument checking:
square = lambda { |n| n ** 2 }
square2 = ->(n) { n ** 2 }      # Stabby lambda (Ruby 1.9+)
square2.call(4)                  # => 16
square2.(4)                      # => 16

# Proc vs Lambda differences:
# 1. Lambda checks arg count — Proc doesn't
# 2. Lambda return returns from lambda — Proc return returns from enclosing method

# Symbol to proc — the most used Ruby shortcut:
[1, 2, 3].map { |n| n.to_s }    # Verbose
[1, 2, 3].map(&:to_s)           # Shorthand! Same result: ["1","2","3"]
["hello", "world"].map(&:upcase) # => ["HELLO", "WORLD"]
[1, nil, 2, nil, 3].select(&:nil?) # => [nil, nil]
```

---

🧪 **Mini Task 1:**
> Write a method `palindrome?(str)` that returns `true` if the string is a palindrome (ignoring case and non-alphanumeric characters). Test: `palindrome?("A man, a plan, a canal: Panama")` → `true`.
> ✅ *Use: `.gsub`, `.downcase`, `.reverse`, `==`*

🧪 **Mini Task 2:**
> Write a method `group_by_length(words)` that takes an array of strings and returns a Hash where keys are word lengths and values are arrays of words with that length. Test: `group_by_length(%w[cat dog elephant ant])` → `{3=>["cat","dog","ant"], 8=>["elephant"]}`.

---

## ⚙️ 4. Complete Language System Breakdown

> 🎯 *Goal: Understand ALL of Ruby's machinery — nothing hidden.*

---

### Part 1: Object-Oriented Programming — The Ruby Way

```ruby
# ── CLASS FUNDAMENTALS ────────────────────────────────────────────────────
class BankAccount
  # Class-level constant:
  OVERDRAFT_LIMIT = -500.0

  # Class variable (shared across all instances — use carefully!):
  @@total_accounts = 0

  # attr_accessor creates both getter AND setter methods
  # attr_reader creates getter only
  # attr_writer creates setter only
  attr_reader :owner, :created_at
  attr_accessor :active

  # Constructor:
  def initialize(owner, initial_balance = 0.0)
    raise ArgumentError, "Owner name cannot be blank" if owner.to_s.strip.empty?

    @owner   = owner
    @balance = initial_balance.to_f
    @active  = true
    @created_at = Time.now
    @transactions = []
    @@total_accounts += 1
  end

  # Instance method with validation:
  def deposit(amount)
    raise ArgumentError, "Amount must be positive" unless amount.positive?
    @balance += amount
    record_transaction(:deposit, amount)
    self  # Return self for method chaining!
  end

  def withdraw(amount)
    raise ArgumentError, "Amount must be positive" unless amount.positive?
    raise "Insufficient funds" if @balance - amount < OVERDRAFT_LIMIT
    @balance -= amount
    record_transaction(:withdrawal, amount)
    self
  end

  # Protected methods — callable from instances of same class:
  def >(other)
    balance > other.balance
  end

  # Getter (we can't use attr_reader because we want to format it):
  def balance
    @balance.round(2)
  end

  # Computed attribute:
  def overdrawn?
    @balance < 0
  end

  # Class method (belongs to the class, not instances):
  def self.total_accounts
    @@total_accounts
  end

  def self.create(owner, balance = 0)
    new(owner, balance)  # 'new' is a class method
  end

  # to_s — called by puts and string interpolation:
  def to_s
    "#{@owner}'s account: $#{balance}"
  end

  # inspect — called by p and irb:
  def inspect
    "#<BankAccount owner=#{@owner.inspect} balance=#{balance}>"
  end

  private  # Everything below is private (can't be called externally)

  def record_transaction(type, amount)
    @transactions << { type: type, amount: amount, at: Time.now, balance: @balance }
  end

  protected  # Everything below is protected (callable from same class hierarchy)

  def balance_raw  # Private to public — used in comparison
    @balance
  end
end

# Method chaining with self:
account = BankAccount.new("Aryan", 1000)
account.deposit(500).deposit(200).withdraw(100)
puts account  # "Aryan's account: $1600.0"

puts BankAccount.total_accounts  # Class method

# ── INHERITANCE ────────────────────────────────────────────────────────────
class SavingsAccount < BankAccount  # < means "inherits from"
  INTEREST_RATE = 0.05

  def initialize(owner, balance = 0, rate = INTEREST_RATE)
    super(owner, balance)  # Call parent's initialize
    @rate = rate
  end

  def apply_interest
    interest = @balance * @rate
    deposit(interest)
    self
  end

  # Override parent method:
  def withdraw(amount)
    raise "Savings minimum balance is $500" if @balance - amount < 500
    super  # Call parent's withdraw!
  end

  def to_s
    "#{super} [Savings, #{(@rate * 100).round(1)}% interest]"
  end
end

savings = SavingsAccount.new("Priya", 2000)
savings.apply_interest
puts savings

# ── MODULES — Mixins and Namespaces ───────────────────────────────────────
module Describable
  def describe
    "I am a #{self.class.name}: #{to_s}"
  end

  def type_info
    "#{self.class.name} (#{self.class.superclass.name})"
  end
end

module Persistable
  def save
    puts "Saving #{inspect} to database..."
    true
  end

  def reload
    puts "Reloading #{self.class.name} from database..."
    self
  end
end

module Auditable
  def self.included(base)  # Called when module is included!
    base.extend(ClassMethods)  # Add class-level methods
    puts "#{base} is now auditable!"
  end

  module ClassMethods
    def audit_log
      @audit_log ||= []
    end
  end

  def audit(action)
    self.class.audit_log << { action: action, at: Time.now, object: self }
  end
end

class User
  include Describable    # Adds instance methods
  include Persistable
  include Auditable
  extend Describable     # extend adds as CLASS methods (not instance)

  attr_accessor :name, :email

  def initialize(name, email)
    @name = name
    @email = email
  end

  def to_s
    "#{@name} <#{@email}>"
  end
end

user = User.new("Aryan", "aryan@example.com")
user.describe   # From Describable mixin
user.save       # From Persistable mixin
user.audit(:created) # From Auditable mixin

# Method Resolution Order (MRO) — crucial for mixins:
User.ancestors  # => [User, Auditable, Persistable, Describable, Object, Kernel, BasicObject]
# Ruby searches in this order when you call a method!
```

---

### Part 2: Arrays & Hashes — Ruby's Power Data Structures

```ruby
# ── ARRAYS ────────────────────────────────────────────────────────────────
# Creating:
arr = [1, 2, 3, 4, 5]
arr2 = Array.new(5, 0)          # => [0, 0, 0, 0, 0]
arr3 = Array.new(5) { |i| i**2 } # => [0, 1, 4, 9, 16]
words = %w[apple banana cherry]  # Word array — splits on whitespace
syms  = %i[name age email]       # Symbol array

# Access:
arr[0]          # => 1 (first)
arr[-1]         # => 5 (last)
arr.first       # => 1
arr.last        # => 5
arr.first(3)    # => [1, 2, 3]
arr.last(2)     # => [4, 5]
arr[1..3]       # => [2, 3, 4]
arr[1...3]      # => [2, 3] (exclusive end)
arr.sample      # => random element
arr.sample(2)   # => [random, random] (no repeats)

# Modification:
arr.push(6)           # Add to end: [1,2,3,4,5,6]
arr << 7              # Same! (preferred Ruby style)
arr.append(8, 9)      # Add multiple
arr.unshift(0)        # Add to beginning (slow for large arrays)
arr.pop               # Remove + return last element
arr.shift             # Remove + return first element
arr.insert(2, :new)   # Insert at index
arr.delete(3)         # Delete by value (first occurrence)
arr.delete_at(0)      # Delete by index
arr.reject! { |n| n.even? }  # Remove all evens in-place
arr.select! { |n| n.odd? }   # Keep only odds in-place
arr.map! { |n| n * 2 }       # Transform in-place

# Transformation (return NEW arrays):
arr.map { |n| n * 2 }        # Transform: [2,4,6,8,10]
arr.select { |n| n.even? }   # Filter: keep matching
arr.reject { |n| n.even? }   # Filter: remove matching
arr.filter_map { |n| n * 2 if n.odd? } # Map + filter in one!
arr.reduce(0) { |sum, n| sum + n }  # Fold: sum
arr.reduce(:+)               # Same! (symbol shorthand)
arr.inject(:*)               # Product (inject = reduce)
arr.each_with_object([]) { |n, acc| acc << n**2 if n.odd? }

arr.sort                     # => sorted copy
arr.sort_by { |n| -n }      # Sort descending
arr.sort { |a, b| b <=> a } # Same (spaceship operator)
arr.reverse                  # Reversed copy
arr.shuffle                  # Shuffled copy
arr.uniq                     # Remove duplicates
arr.flatten                  # Flatten nested arrays
arr.flatten(1)               # Flatten one level only
arr.compact                  # Remove nils
arr.zip([6,7,8])            # [[1,6],[2,7],[3,8]] — zip arrays
arr.each_slice(2).to_a      # [[1,2],[3,4],[5]] — slice into chunks
arr.each_cons(2).to_a       # [[1,2],[2,3],[3,4],[4,5]] — sliding window
arr.tally                    # {"a"=>2,"b"=>1} — count occurrences

# Set operations:
[1,2,3] | [2,3,4]           # => [1,2,3,4] (union)
[1,2,3] & [2,3,4]           # => [2,3] (intersection)
[1,2,3] - [2,3,4]           # => [1] (difference)
[1,2] + [3,4]               # => [1,2,3,4] (concatenation)
[1,2] * 3                   # => [1,2,1,2,1,2] (repetition)

# Querying:
arr.any? { |n| n > 4 }      # true if ANY match
arr.all? { |n| n > 0 }      # true if ALL match
arr.none? { |n| n > 10 }    # true if NONE match
arr.one? { |n| n == 3 }     # true if EXACTLY ONE matches
arr.count { |n| n.even? }   # Count matching
arr.sum { |n| n * 2 }       # Sum with transformation
arr.min_by { |n| n.to_s }   # Min by criterion
arr.max_by { |n| n.to_s }   # Max by criterion
arr.minmax                   # => [min, max]
arr.flat_map { |n| [n, n*2] } # Map then flatten
arr.group_by { |n| n % 3 }  # Group by criterion
arr.partition { |n| n.even? } # Split into [matching, not_matching]
arr.take(3)                  # First 3 elements
arr.drop(3)                  # All but first 3
arr.take_while { |n| n < 4 } # Take while condition
arr.drop_while { |n| n < 4 } # Drop while condition
arr.zip(arr.map { |n| n**2 }).to_h # => {1=>1, 2=>4, 3=>9, ...}

# ── HASHES ────────────────────────────────────────────────────────────────
# Creating:
h = { name: "Aryan", age: 17, city: "Kolkata" }  # Symbol keys (common)
h2 = { "name" => "Aryan", "age" => 17 }           # String keys (old style)
h3 = Hash.new(0)                                   # Default value of 0
h4 = Hash.new { |h, k| h[k] = [] }               # Default: empty array

# Access:
h[:name]              # => "Aryan"
h[:missing]           # => nil (no error!)
h.fetch(:name)        # => "Aryan"
h.fetch(:missing)     # => KeyError raised!
h.fetch(:missing, "default")  # => "default"
h.fetch(:missing) { |k| "Generated: #{k}" } # Block default
h.dig(:address, :city)  # Safe nested access: nil if any key missing

# Modification:
h[:email] = "a@b.com"           # Add/update
h.merge(role: :admin)            # Returns new hash (non-destructive)
h.merge!(role: :admin)           # Updates in place
h.merge(other) { |key, old, new| old + new } # Conflict resolver
h.delete(:city)                  # Remove key, return value
h.reject! { |k, v| k == :age }  # Remove matching pairs in-place
h.select! { |k, v| v.is_a?(String) } # Keep matching pairs in-place
h.transform_values { |v| v.to_s }    # Transform all values
h.transform_keys { |k| k.to_s }      # Transform all keys
h.transform_values!(&:upcase)         # In-place transform

# Querying:
h.key?(:name)         # true (has key?)
h.has_key?(:name)     # alias
h.include?(:name)     # alias
h.value?("Aryan")     # true (has value?)
h.any? { |k,v| v.is_a?(Integer) }
h.all? { |k,v| !v.nil? }
h.count { |k,v| v.is_a?(String) }

# Iteration:
h.each { |key, value| puts "#{key}: #{value}" }
h.each_pair { |k, v| }         # alias for each
h.keys                          # => [:name, :age, :city]
h.values                        # => ["Aryan", 17, "Kolkata"]
h.to_a                          # => [[:name,"Aryan"],[:age,17],...]
h.map { |k, v| [k, v.to_s] }.to_h  # Transform to new hash
h.flat_map { |k, v| [k, v] }   # Flatten to array
h.min_by { |k, v| v.to_s }     # Min pair by criterion
h.sort_by { |k, v| v.to_s }    # Sort pairs by value
h.group_by { |k, v| v.class }  # Group pairs by class
h.filter_map { |k, v| "#{k}=#{v}" if v.is_a?(String) }

# Merging strategy (great for configuration):
defaults = { timeout: 30, retries: 3, verbose: false }
overrides = { timeout: 60, debug: true }
config = defaults.merge(overrides)  # => {timeout:60, retries:3, verbose:false, debug:true}

# Word frequency with Hash.new(0):
text = "the cat sat on the mat the cat"
freq = Hash.new(0)
text.split.each { |word| freq[word] += 1 }
freq  # => {"the"=>3, "cat"=>2, "sat"=>1, "on"=>1, "mat"=>1}
# Equivalent using tally:
text.split.tally  # Same result!
```

---

### Part 3: Enumerable — Ruby's Most Powerful Module

```ruby
# Every collection includes Enumerable if it defines #each
# Enumerable gives you ~60 methods for free!

# The core: if your class implements #each, you get ALL of these:
class NumberSet
  include Enumerable

  def initialize(*numbers)
    @numbers = numbers
  end

  def each(&block)    # Only method you MUST implement!
    @numbers.each(&block)
  end
end

ns = NumberSet.new(3, 1, 4, 1, 5, 9, 2, 6)
ns.sort          # Works!
ns.max           # Works!
ns.select(&:odd?) # Works!
ns.map { |n| n**2 }.sum # Works!

# ── LAZY ENUMERATORS — process infinite sequences ─────────────────────────
# Without lazy — creates intermediate arrays (memory-intensive):
(1..Float::INFINITY).select(&:odd?).take(5)  # Would run forever!

# With lazy — processes on demand:
result = (1..Float::INFINITY).lazy.select(&:odd?).first(5)
# => [1, 3, 5, 7, 9]  — only computes what's needed!

# Lazy pipeline:
(1..Float::INFINITY)
  .lazy
  .select { |n| n % 3 == 0 }
  .map { |n| n ** 2 }
  .reject { |n| n.to_s.include?("0") }
  .first(5)
# => [9, 81, 225, 441, 729]

# Enumerator — create external iterators:
enum = [1, 2, 3].each    # Creates an Enumerator
enum.next                 # => 1
enum.next                 # => 2
enum.next                 # => 3
enum.next                 # => StopIteration raised

# Enumerator::Chain (Ruby 2.6+):
chain = [1, 2, 3].chain([4, 5, 6], [7, 8, 9])
chain.to_a  # => [1, 2, 3, 4, 5, 6, 7, 8, 9]

# Custom Enumerator with Enumerator::Yielder:
fib = Enumerator.new do |yielder|
  a, b = 0, 1
  loop do
    yielder.yield a       # 'yield' to the external caller
    a, b = b, a + b
  end
end

fib.take(10)    # => [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
fib.lazy.select(&:even?).first(5)  # => [0, 2, 8, 34, 144]
```

---

### Part 4: Blocks and Functional Programming Patterns

```ruby
# ── FUNCTIONAL PATTERNS IN RUBY ────────────────────────────────────────────

# Higher-order functions:
def transform(data, &transformer)
  data.map(&transformer)
end
transform([1,2,3]) { |n| n * 2 }   # => [2, 4, 6]
transform([1,2,3], &method(:puts)) # Prints each, returns [nil,nil,nil]

# Method objects:
m = "hello".method(:upcase)  # Get a method object
m.call                        # => "HELLO"
["hello","world"].map(&m)     # => ["HELLO","WORLD"]

# Currying — partial application:
multiply = ->(x, y) { x * y }
double = multiply.curry.(2)   # Partially apply: fixes x=2
triple = multiply.curry.(3)
[1,2,3,4,5].map(&double)     # => [2, 4, 6, 8, 10]
[1,2,3,4,5].map(&triple)     # => [3, 6, 9, 12, 15]

# Function composition (Ruby 2.6+):
double  = ->(x) { x * 2 }
add_one = ->(x) { x + 1 }

double_then_add = double >> add_one  # double first, then add_one
add_then_double = double << add_one  # add_one first, then double

double_then_add.(5)  # => 11 (5*2+1)
add_then_double.(5)  # => 12 (5+1)*2

# Memoization with hash:
def fibonacci
  cache = Hash.new { |h, k| h[k] = k < 2 ? k : h[k-1] + h[k-2] }
  cache
end

fib = fibonacci
fib[10]   # => 55
fib[100]  # => 354224848179261915075 (instant due to memoization!)

# Tap — for debugging pipelines:
[1, 2, 3, 4, 5]
  .tap { |a| puts "Before: #{a}" }
  .select(&:odd?)
  .tap { |a| puts "After select: #{a}" }
  .map { |n| n ** 2 }
  .tap { |a| puts "After map: #{a}" }
# then / itself (Ruby 2.6+) — pass object to block:
"hello"
  .then { |s| s.upcase }
  .then { |s| "#{s}!" }
# => "HELLO!"

# yield_self (alias for then):
42.yield_self { |n| n * 2 }.yield_self { |n| "Result: #{n}" }
# => "Result: 84"
```

---

### 📊 Full Ruby System Overview Table

| Feature             | Ruby Mechanism                              | Key Insight                                           |
|---------------------|---------------------------------------------|-------------------------------------------------------|
| Everything object   | Integers, nil, true, false — all objects    | `1.class` → Integer; `nil.nil?` → true               |
| Open classes        | Any class can be reopened and extended      | Even String, Array, Integer can get new methods      |
| Mixins              | `include` module adds instance methods      | Multiple inheritance safely via modules               |
| Blocks              | Anonymous code chunks attached to methods  | The foundation of Ruby's elegant iteration API        |
| Metaprogramming     | `method_missing`, `define_method`, `eval`   | Code that writes code — Rails DSLs built this way    |
| Duck typing         | Objects respond to messages, not types      | `respond_to?` not `is_a?` — behavior over type       |
| Symbols             | Immutable, interned identifiers             | Same symbol = same object; hash keys, method names   |
| Frozen strings      | `# frozen_string_literal: true`             | All string literals immutable — significant perf win  |
| Enumerable          | Include + define `each` → 60+ methods      | The most powerful mixin in the standard library       |
| Method objects      | `method(:name)` — methods as first-class   | Pass methods as blocks with `&method(:name)`         |

---

## 🔄 5. Real-World Workflow

---

### 🟢 Beginner Workflow: Ruby CLI Tool

```ruby
#!/usr/bin/env ruby
# frozen_string_literal: true

# todo.rb — Command-line todo application
require "json"
require "date"
require "optparse"

class TodoApp
  STORAGE_FILE = File.expand_path("~/.todos.json")

  def initialize
    @todos = load_todos
  end

  def run(args)
    command, *rest = args
    case command
    when "add", "a"    then add(*rest)
    when "list", "ls"  then list
    when "done", "d"   then complete(rest.first&.to_i)
    when "remove", "r" then remove(rest.first&.to_i)
    when "clear"       then clear
    when nil, "help"   then help
    else
      puts "Unknown command: #{command}"
      help
    end
  end

  private

  def add(*words)
    title = words.join(" ")
    if title.strip.empty?
      puts "Error: Please provide a todo title"
      return
    end
    todo = { id: next_id, title: title, done: false, created_at: Time.now.iso8601 }
    @todos << todo
    save_todos
    puts "✅ Added: #{title} (id: #{todo[:id]})"
  end

  def list
    if @todos.empty?
      puts "No todos yet! Add one with: todo add <title>"
      return
    end
    puts "\n📋 Your Todos:\n#{"-" * 40}"
    @todos.each do |todo|
      status = todo[:done] ? "✅" : "⬜"
      puts "  #{status} [#{todo[:id]}] #{todo[:title]}"
    end
    pending = @todos.count { |t| !t[:done] }
    puts "\n#{pending}/#{@todos.size} pending"
  end

  def complete(id)
    todo = find_by_id(id)
    return puts "Error: Todo ##{id} not found" unless todo
    todo[:done] = true
    todo[:completed_at] = Time.now.iso8601
    save_todos
    puts "✅ Completed: #{todo[:title]}"
  end

  def remove(id)
    before_count = @todos.size
    @todos.reject! { |t| t[:id] == id }
    if @todos.size < before_count
      save_todos
      puts "🗑️  Removed todo ##{id}"
    else
      puts "Error: Todo ##{id} not found"
    end
  end

  def clear
    @todos.select! { |t| !t[:done] }
    save_todos
    puts "🧹 Cleared all completed todos"
  end

  def help
    puts <<~HELP
      Usage: todo <command> [args]

      Commands:
        add <title>   Add a new todo
        list          List all todos
        done <id>     Mark todo as done
        remove <id>   Remove a todo
        clear         Remove completed todos
        help          Show this help
    HELP
  end

  def find_by_id(id)
    @todos.find { |t| t[:id] == id }
  end

  def next_id
    (@todos.map { |t| t[:id] }.max || 0) + 1
  end

  def load_todos
    return [] unless File.exist?(STORAGE_FILE)
    JSON.parse(File.read(STORAGE_FILE), symbolize_names: true)
  rescue JSON::ParserError
    []
  end

  def save_todos
    File.write(STORAGE_FILE, JSON.pretty_generate(@todos))
  end
end

TodoApp.new.run(ARGV)
```

---

### 🔵 Professional Workflow: Sinatra REST API

```ruby
# frozen_string_literal: true
# app.rb — Lightweight REST API with Sinatra

require "sinatra"
require "sinatra/json"
require "json"

# Inline-style Sinatra app (DSL style):
configure do
  set :port, ENV.fetch("PORT", 3000).to_i
  set :bind, "0.0.0.0"
  enable :logging
  disable :show_exceptions
end

# In-memory store (use a database in production!):
USERS = {}
NEXT_ID = [1]

helpers do
  def parse_body
    request.body.rewind
    JSON.parse(request.body.read, symbolize_names: true)
  rescue JSON::ParserError => e
    halt 400, json(error: "Invalid JSON: #{e.message}")
  end

  def user_or_404(id)
    USERS[id.to_i] || halt(404, json(error: "User #{id} not found"))
  end

  def validate_user_params(params)
    errors = []
    errors << "username is required" if params[:username].to_s.strip.empty?
    errors << "email is required" if params[:email].to_s.strip.empty?
    errors << "email format invalid" unless params[:email].to_s.match?(/\A[\w+\-.]+@[a-z\d\-.]+\.[a-z]+\z/i)
    halt 422, json(errors: errors) unless errors.empty?
  end
end

before do
  content_type :json
  response.headers["X-Request-ID"] = SecureRandom.uuid
end

error do
  json(error: env["sinatra.error"].message)
end

# ── ROUTES ────────────────────────────────────────────────────────────────
get "/health" do
  json(status: "ok", uptime: Process.clock_gettime(Process::CLOCK_MONOTONIC))
end

get "/api/users" do
  page  = [params[:page].to_i, 1].max
  limit = [[params[:limit].to_i, 1].max, 100].min
  users = USERS.values
  users = users.select { |u| u[:username].include?(params[:search]) } if params[:search]
  total = users.size
  paginated = users.slice((page - 1) * limit, limit) || []
  json(data: paginated, total: total, page: page, limit: limit)
end

get "/api/users/:id" do
  json user_or_404(params[:id])
end

post "/api/users" do
  data = parse_body
  validate_user_params(data)
  id = NEXT_ID[0].tap { NEXT_ID[0] += 1 }
  user = { id: id, username: data[:username], email: data[:email], created_at: Time.now.iso8601 }
  USERS[id] = user
  status 201
  json user
end

put "/api/users/:id" do
  user = user_or_404(params[:id])
  data = parse_body
  validate_user_params(data)
  USERS[user[:id]] = user.merge(
    username: data[:username],
    email: data[:email],
    updated_at: Time.now.iso8601
  )
  json USERS[user[:id]]
end

patch "/api/users/:id" do
  user = user_or_404(params[:id])
  data = parse_body
  USERS[user[:id]] = user.merge(data.slice(:username, :email)).merge(updated_at: Time.now.iso8601)
  json USERS[user[:id]]
end

delete "/api/users/:id" do
  user_or_404(params[:id])
  USERS.delete(params[:id].to_i)
  status 204
end
```

---

## 🧪 6. Hands-on Practice Projects

---

### 🟢 Beginner Project: Markdown Report Generator

```ruby
# frozen_string_literal: true
# report_generator.rb — Generate markdown reports from data

class MarkdownReport
  def initialize(title)
    @title = title
    @sections = []
  end

  def heading(text, level = 1)
    @sections << "#{"#" * level} #{text}\n"
    self
  end

  def paragraph(text)
    @sections << "#{text}\n"
    self
  end

  def table(headers, rows)
    separator = headers.map { |h| "-" * h.length }
    lines = [
      "| #{headers.join(" | ")} |",
      "| #{separator.join(" | ")} |",
      *rows.map { |row| "| #{row.join(" | ")} |" }
    ]
    @sections << lines.join("\n") + "\n"
    self
  end

  def bullet_list(*items)
    @sections << items.map { |item| "- #{item}" }.join("\n") + "\n"
    self
  end

  def code_block(code, language = "ruby")
    @sections << "```#{language}\n#{code}\n```\n"
    self
  end

  def horizontal_rule
    @sections << "---\n"
    self
  end

  def to_s
    ["# #{@title}", "", *@sections].join("\n")
  end

  def save(path)
    File.write(path, to_s)
    puts "Report saved to #{path}"
    self
  end
end

# Usage:
students = [
  { name: "Aryan", grade: "A", gpa: 9.8 },
  { name: "Priya", grade: "A", gpa: 9.2 },
  { name: "Rahul", grade: "B", gpa: 8.9 }
]

report = MarkdownReport.new("Student Report Q1 2025")
  .heading("Executive Summary", 2)
  .paragraph("Total students: #{students.size}")
  .horizontal_rule
  .heading("Student Performance", 2)
  .table(
    ["Name", "Grade", "GPA"],
    students.map { |s| [s[:name], s[:grade], s[:gpa].to_s] }
  )
  .heading("Top Performers", 2)
  .bullet_list(*students.select { |s| s[:gpa] >= 9.0 }.map { |s| "#{s[:name]}: GPA #{s[:gpa]}" })
  .code_block("students.sort_by { |s| -s[:gpa] }.first(3)")

report.save("report.md")
puts report
```

✅ **You've succeeded when:** You can chain all methods fluently and produce a perfectly formatted Markdown file with proper tables, lists, and code blocks.

---

### 🔵 Intermediate Project: Type-Safe Configuration DSL

```ruby
# frozen_string_literal: true
# config_dsl.rb — Build a beautiful configuration DSL

class Configuration
  class ValidationError < StandardError; end

  def self.define(&block)
    config = new
    config.instance_eval(&block)
    config.validate!
    config.freeze
  end

  def initialize
    @settings = {}
    @validators = {}
    @required = []
  end

  def set(key, value, validate: nil, required: false)
    @settings[key] = value
    @validators[key] = validate if validate
    @required << key if required
  end

  def section(name, &block)
    sub = self.class.new
    sub.instance_eval(&block)
    @settings[name] = sub.to_h
  end

  def validate!
    @required.each do |key|
      raise ValidationError, "Required setting #{key} is missing" unless @settings.key?(key)
    end
    @validators.each do |key, validator|
      value = @settings[key]
      next unless value
      unless validator.call(value)
        raise ValidationError, "Setting #{key}=#{value.inspect} is invalid"
      end
    end
    self
  end

  def method_missing(name, *args, **kwargs, &block)
    if name.to_s.end_with?("=")
      set(name.to_s.chomp("=").to_sym, args.first)
    elsif @settings.key?(name)
      @settings[name]
    else
      super
    end
  end

  def respond_to_missing?(name, include_private = false)
    name.to_s.end_with?("=") || @settings.key?(name) || super
  end

  def to_h
    @settings.transform_values { |v| v.is_a?(self.class) ? v.to_h : v }
  end

  def [](key)
    @settings[key]
  end
end

# Usage — beautiful, readable configuration:
AppConfig = Configuration.define do
  set :app_name, "MyAwesomeApp", required: true
  set :version, "1.0.0"
  set :debug, ENV["DEBUG"] == "true"
  set :port, ENV.fetch("PORT", "3000").to_i,
      validate: ->(v) { v.between?(1, 65535) }
  set :max_connections, 100,
      validate: ->(v) { v.positive? }

  section :database do
    set :url, ENV["DATABASE_URL"] || "sqlite3::memory:", required: true
    set :pool_size, 5
    set :timeout, 5000
  end

  section :mail do
    set :host, "smtp.gmail.com"
    set :port, 587
    set :tls, true
  end
end

puts AppConfig[:app_name]            # "MyAwesomeApp"
puts AppConfig[:database][:pool_size] # 5
puts AppConfig.to_h.inspect
```

---

### 🔴 Advanced Project: Lazy Event-Sourced Collection

```ruby
# frozen_string_literal: true
# event_sourced.rb — Event sourcing with Ruby's power features

module EventSourced
  def self.included(base)
    base.extend(ClassMethods)
    base.instance_variable_set(:@event_handlers, {})
  end

  module ClassMethods
    def on(event_type, &handler)
      @event_handlers[event_type] = handler
    end

    def event_handlers
      @event_handlers
    end

    def from_events(events)
      instance = allocate
      instance.instance_variable_set(:@events, [])
      instance.instance_variable_set(:@version, 0)
      events.each { |e| instance.apply(e) }
      instance
    end
  end

  def initialize
    @events = []
    @version = 0
  end

  def record(type, **data)
    event = { type: type, data: data, version: @version + 1, at: Time.now }
    apply(event)
    @events << event
    self
  end

  def apply(event)
    handler = self.class.event_handlers[event[:type]]
    instance_exec(event[:data], &handler) if handler
    @version = event[:version]
  end

  def uncommitted_events
    @events.dup
  end

  def event_count = @events.size
  def version = @version
end

class ShoppingCart
  include EventSourced
  include Enumerable

  attr_reader :id, :customer_id, :status

  on :cart_created do |data|
    @id = data[:id]
    @customer_id = data[:customer_id]
    @status = :open
    @items = {}
  end

  on :item_added do |data|
    @items[data[:sku]] ||= { sku: data[:sku], name: data[:name], price: data[:price], qty: 0 }
    @items[data[:sku]][:qty] += data[:qty]
  end

  on :item_removed do |data|
    return unless @items[data[:sku]]
    @items[data[:sku]][:qty] -= data[:qty]
    @items.delete(data[:sku]) if @items[data[:sku]][:qty] <= 0
  end

  on :cart_checked_out do |data|
    @status = :checked_out
    @checked_out_at = data[:at]
  end

  def self.create(id:, customer_id:)
    cart = new
    cart.record(:cart_created, id: id, customer_id: customer_id)
    cart
  end

  def add_item(sku:, name:, price:, qty: 1)
    raise "Cart is checked out" if status == :checked_out
    record(:item_added, sku: sku, name: name, price: price, qty: qty)
  end

  def remove_item(sku:, qty: 1)
    record(:item_removed, sku: sku, qty: qty)
  end

  def checkout!
    raise "Cart is empty" if @items.empty?
    raise "Already checked out" if status == :checked_out
    record(:cart_checked_out, at: Time.now.iso8601, total: total)
  end

  def each(&block)
    @items.values.each(&block)  # Enumerable works!
  end

  def total
    sum { |item| item[:price] * item[:qty] }
  end

  def item_count
    sum { |item| item[:qty] }
  end
end

cart = ShoppingCart.create(id: "cart-001", customer_id: "user-123")
cart.add_item(sku: "RUBY-BOOK", name: "Programming Ruby", price: 49.99, qty: 2)
cart.add_item(sku: "MUG", name: "Ruby Mug", price: 14.99)
cart.remove_item(sku: "MUG")
cart.checkout!

puts "Total: $#{cart.total}"
puts "Events: #{cart.event_count}"
puts "Version: #{cart.version}"
cart.each { |item| puts "  #{item[:name]}: #{item[:qty]} × $#{item[:price]}" }

# Rebuild from events:
events = cart.uncommitted_events
rebuilt = ShoppingCart.from_events(events)
puts "Rebuilt total: $#{rebuilt.total}"  # Same!
```

🔥 **Challenge:** Add persistence with JSON file storage and an event replay mechanism that can rebuild any cart state from a specific version.

---

## ⚠️ 7. Common Mistakes

---

### ❌ Mistake 1: Mutating Objects Unexpectedly

```ruby
# ❌ WRONG — modifying strings in-place changes all references!
name = "Aryan"
alias_name = name      # NOT a copy — same object!
alias_name.upcase!     # Modifies the original too!
puts name              # "ARYAN" — surprise!

# ✅ RIGHT — use dup or clone, or non-bang methods:
name = "Aryan"
upper_name = name.upcase  # Returns NEW string, name unchanged
alias_name = name.dup     # Explicit copy
alias_name.upcase!         # Only modifies alias_name

# ❌ Same problem with arrays:
original = [1, 2, 3]
other = original          # Same array!
other << 4                # Modifies original!
puts original.inspect     # [1, 2, 3, 4]

# ✅ RIGHT:
other = original.dup      # Shallow copy
other = original.map { |n| n } # New array with same elements
other = Marshal.load(Marshal.dump(original)) # Deep clone (complex objects)
```

---

### ❌ Mistake 2: Using `==` vs `equal?` vs `eql?`

```ruby
# Ruby has THREE equality methods:
# == (value equality)    — are values logically equal?
# eql? (hash equality)   — used for hash key comparison (type + value)
# equal? (identity)      — are they the exact same object? (object_id)

1 == 1.0          # => true  (Integer == Float, numerically equal)
1.eql?(1.0)       # => false (different types)
1.equal?(1)       # => true  (small integers are cached!)
"a".equal?("a")   # => false (different string objects)

:foo.equal?(:foo) # => true  (symbols are interned — always same object)

# ❌ WRONG — comparing for object identity when you want value:
if str1.equal?(str2)  # Compares object IDs — almost never what you want
  puts "Same!"
end

# ✅ RIGHT — use == for value comparison:
if str1 == str2   # Value comparison — what you usually mean
  puts "Equal!"
end

# ❌ WRONG — expecting === to behave like ==:
puts 1..10 === 5    # => true  (case equality — is 5 in range?)
puts String === "x" # => true  (case equality — is "x" a String?)
puts /ab/ === "abc" # => true  (case equality — does "abc" match /ab/?)
# === is what case/when uses internally!
```

---

### ❌ Mistake 3: Forgetting `freeze` on Constants

```ruby
# ❌ WRONG — Ruby constants aren't truly constant!
MAX_SIZE = 100
MAX_SIZE = 200        # Warning: already initialized constant (but still works!)

NAMES = ["Alice", "Bob"]
NAMES << "Carol"      # No error! The array is mutated! (even though NAMES is a constant)
NAMES.push("Dave")    # Same problem

# ✅ RIGHT — freeze to prevent mutation:
NAMES = ["Alice", "Bob"].freeze
# NAMES << "Carol"    # => FrozenError (cannot modify frozen Array)
# NAMES.push("Dave")  # => FrozenError

# But shallow freeze doesn't protect nested objects!
MATRIX = [[1, 2], [3, 4]].freeze
# MATRIX << [5, 6]   # FrozenError — can't add new row
MATRIX[0] << 99     # ✅ Works! Inner array not frozen!

# Deep freeze with a gem or manual recursion:
def deep_freeze(obj)
  case obj
  when Array then obj.each { |e| deep_freeze(e) }.freeze
  when Hash  then obj.each { |k,v| deep_freeze(k); deep_freeze(v) }.freeze
  else obj.freeze
  end
end
```

---

### ❌ Mistake 4: `rescue Exception` vs `rescue StandardError`

```ruby
# ❌ WRONG — catching Exception catches EVERYTHING including signals!
begin
  do_work()
rescue Exception => e   # Catches Interrupt, SignalException, NoMemoryError!
  puts "Caught: #{e}"   # Prevents Ctrl+C from working! Traps system signals!
end

# ✅ RIGHT — rescue StandardError (the default):
begin
  do_work()
rescue => e             # Same as: rescue StandardError => e
  puts "Caught: #{e}"   # Only catches application-level errors
end

# Only catch specific exceptions you can handle:
begin
  response = http_client.get(url)
rescue Net::TimeoutError
  retry_with_backoff
rescue Net::HTTPError => e
  log_error(e)
  raise  # Re-raise if you can't handle it
end

# Exception hierarchy to know:
# Exception
#   ├── ScriptError (SyntaxError, LoadError)
#   ├── SignalException (Interrupt)
#   └── StandardError ← rescue this by default
#       ├── RuntimeError ← raise "message" creates this
#       ├── ArgumentError
#       ├── TypeError
#       ├── NameError (NoMethodError)
#       ├── IOError (Errno::ENOENT)
#       └── ...
```

---

### ❌ Mistake 5: Incorrect Use of `send` and `method_missing`

```ruby
# ❌ WRONG — using send without sanitizing method name (security risk!):
class UserAPI
  def public_data = { name: "Aryan" }
  def private_data = { password: "secret" }
  private :private_data
end

api = UserAPI.new
field = params[:field]  # Could be user-controlled!
api.send(field)         # ❌ Can call private_data if field = "private_data"!

# ✅ RIGHT — use public_send (respects private/protected):
api.public_send(field)  # Raises NoMethodError for private methods

# ✅ RIGHT — whitelist allowed methods:
ALLOWED_FIELDS = %i[name email age].freeze
if ALLOWED_FIELDS.include?(field.to_sym)
  api.public_send(field.to_sym)
end

# ❌ WRONG — method_missing without respond_to_missing?:
class Proxy
  def method_missing(name, *args)  # Handles unknown methods
    "Proxy: #{name}(#{args})"
  end
  # Missing respond_to_missing? — proxy.respond_to?(:anything) returns false!
end

# ✅ RIGHT — always pair method_missing with respond_to_missing?:
class Proxy
  def method_missing(name, *args, &block)
    return super unless valid_method?(name)
    "Proxy: #{name}(#{args})"
  end

  def respond_to_missing?(name, include_private = false)
    valid_method?(name) || super
  end

  private

  def valid_method?(name)
    name.to_s.start_with?("find_by_")
  end
end
```

---

### ❌ Mistake 6: N+1 Queries in ActiveRecord

```ruby
# ❌ WRONG — N+1 query problem:
# 1 query for posts + N queries for each post's author:
posts = Post.all
posts.each do |post|
  puts "#{post.title} by #{post.author.name}"  # author loaded one at a time!
end
# => 1 + N queries (terrible for performance!)

# ✅ RIGHT — eager load with includes:
posts = Post.includes(:author).all
posts.each do |post|
  puts "#{post.title} by #{post.author.name}"  # No extra queries!
end
# => 2 queries total (posts + all authors at once)

# Multiple associations:
posts = Post.includes(:author, :tags, comments: :author).all

# preload vs eager_load vs includes:
Post.preload(:author)     # Two separate queries (like includes)
Post.eager_load(:author)  # Single JOIN query (needed for WHERE on association)
Post.joins(:author).where(authors: { role: :admin }).eager_load(:author)
```

---

## 🔥 8. Pro Tips & Hidden Tricks

---

### 💎 Tip 1: Comparable and Enumerable — Free Superpowers

```ruby
# Include Comparable and define <=> — get all comparison methods free!
class Temperature
  include Comparable  # Gives: <, >, <=, >=, ==, between?, clamp

  attr_reader :value, :unit

  def initialize(value, unit = :celsius)
    @value = value.to_f
    @unit = unit
  end

  def to_celsius
    case @unit
    when :celsius    then @value
    when :fahrenheit then (@value - 32) * 5.0 / 9.0
    when :kelvin     then @value - 273.15
    end
  end

  # Only method Comparable needs:
  def <=>(other)
    to_celsius <=> other.to_celsius
  end

  def to_s
    "#{@value}°#{@unit.to_s[0].upcase}"
  end
end

boiling = Temperature.new(100, :celsius)
freezing = Temperature.new(32, :fahrenheit)
body = Temperature.new(310.15, :kelvin)

puts boiling > freezing   # true
puts freezing == Temperature.new(0, :celsius)  # true

# Works with sort, min, max on arrays:
temps = [boiling, freezing, body]
puts temps.sort.map(&:to_s).inspect   # From coldest to warmest
puts temps.min  # freezing
puts temps.max  # boiling

# clamp (Ruby 2.4+):
Temperature.new(50).clamp(freezing, boiling) # Returns self (in range)
Temperature.new(-10).clamp(freezing, boiling) # Returns freezing
```

---

### 💎 Tip 2: Struct and Data — Lightweight Value Objects

```ruby
# Struct — create simple value objects quickly:
Point = Struct.new(:x, :y) do
  def distance_to(other)
    Math.sqrt((x - other.x)**2 + (y - other.y)**2)
  end

  def to_s
    "(#{x}, #{y})"
  end
end

p1 = Point.new(0, 0)
p2 = Point.new(3, 4)
p1.distance_to(p2)  # => 5.0
p1 == Point.new(0, 0)  # => true (value equality!)

# Struct also works as hash-like:
p1.to_h     # => {x: 0, y: 0}
p1.members  # => [:x, :y]

# Data (Ruby 3.2+) — immutable value object:
Measurement = Data.define(:value, :unit) do
  def to_si
    case unit
    when :kg  then Measurement.new(value: value, unit: :kg)
    when :lb  then Measurement.new(value: value * 0.453592, unit: :kg)
    when :oz  then Measurement.new(value: value * 0.0283495, unit: :kg)
    end
  end

  def to_s
    "#{value} #{unit}"
  end
end

weight = Measurement.new(value: 10, unit: :lb)
puts weight.to_si  # "4.53592 kg"
# weight.value = 20  # => NoMethodError: frozen (immutable!)
weight == Measurement.new(value: 10, unit: :lb)  # => true (value equality)
```

---

### 💎 Tip 3: Kernel Methods Hidden in Plain Sight

```ruby
# Ruby's Kernel module provides methods available everywhere:

# pp — pretty print (better than p for nested structures):
pp({ name: "Aryan", scores: [9.8, 9.2, 8.9], nested: { deep: true } })

# format / sprintf — string formatting:
format("%.2f GB", 3.14159)    # => "3.14 GB"
sprintf("%05d", 42)           # => "00042"
"%s costs $%.2f" % ["Book", 49.9]  # => "Book costs $49.90"

# `caller` — get the call stack:
def who_called_me?
  caller[0]  # => "script.rb:42:in `some_method'"
end

# `__method__` — name of current method:
def my_method
  puts __method__  # => :my_method
end

# `sleep` with float:
sleep 0.5   # Sleep 500ms

# `rand` — random numbers:
rand        # => 0.0 to 1.0 (float)
rand(10)    # => 0 to 9 (integer)
rand(5..10) # => 5, 6, 7, 8, 9, or 10

# `exit`, `abort`:
exit        # Exit with 0
exit(1)     # Exit with error code
abort "Fatal error!"  # Print to stderr and exit(1)

# `at_exit` — cleanup on exit:
at_exit { puts "Goodbye!" }
at_exit { cleanup_resources }  # Multiple at_exit stack (LIFO order)

# `system` / backtick — run shell commands:
result = `ls -la`           # Returns output as string
system("ls -la")            # Prints output, returns true/false
system("ls", "-la")         # Safer version (no shell expansion)
output = IO.popen("date").read  # Capture output of command

# `require_relative` vs `require`:
require "json"              # From load path (gems, stdlib)
require_relative "utils"   # Relative to current file

# `puts` vs `print` vs `p` vs `pp`:
puts nil     # Prints blank line
p nil        # Prints "nil"
print nil    # Prints nothing, no newline
puts [1,2,3] # Prints each on own line
p [1,2,3]    # Prints [1, 2, 3] on one line
```

---

### 💎 Tip 4: String Formatting & Heredoc Power

```ruby
# Heredoc variants:
message1 = <<~TEXT      # ~ strips leading whitespace (use this!)
  Hello #{name}!
  This is indented properly.
TEXT

message2 = <<~'TEXT'   # Single-quote heredoc = no interpolation
  Hello #{name}!        # Prints literally
TEXT

result = <<~RUBY.strip.gsub("X", "Y")  # Can chain methods on heredoc!
  def hello
    "X World"
  end
RUBY

# String with format:
"%-20s %5.2f" % ["Total:", 99.99]  # "Total:               99.99"

# Color output in terminal (ANSI codes):
def colorize(text, color_code)
  "\e[#{color_code}m#{text}\e[0m"
end

puts colorize("Red text",   31)
puts colorize("Green text", 32)
puts colorize("Bold text",  1)

# Or use the 'colorize' gem:
# puts "Hello".red.bold
# puts "World".on_blue.white

# Template strings with ERB (built-in):
require "erb"
template = ERB.new(<<~TEMPLATE, trim_mode: "-")
  Hello, <%= name %>!
  You have <%= messages.count %> messages:
  <% messages.each do |msg| -%>
    - <%= msg %>
  <% end -%>
TEMPLATE

name = "Aryan"
messages = ["Welcome!", "New feature available", "Your report is ready"]
puts template.result(binding)
```

---

### 💎 Tip 5: `freeze`, `dup`, `clone` — Object Immutability

```ruby
# freeze — make object immutable:
str = "hello".freeze
str.upcase   # => "HELLO" (returns new string — fine)
# str.upcase! # => FrozenError (would modify in-place)
# str << "!"  # => FrozenError

# frozen? — check if frozen:
"hello".frozen?         # => false
"hello".freeze.frozen?  # => true
:symbol.frozen?         # => true  (symbols always frozen)
1.frozen?               # => true  (integers always frozen)
true.frozen?            # => true  (booleans always frozen)
nil.frozen?             # => true  (nil always frozen)

# dup vs clone:
# dup  — creates unfrozen copy (loses frozen state and singleton methods)
# clone — creates exact copy (preserves frozen state and singleton methods)

frozen_str = "hello".freeze
dup_str   = frozen_str.dup    # => unfrozen copy
clone_str = frozen_str.clone  # => frozen copy!

dup_str.frozen?    # => false
clone_str.frozen?  # => true

# Deep dup with Marshal (for simple objects):
original = { a: [1, 2, 3], b: { c: "deep" } }
deep_copy = Marshal.load(Marshal.dump(original))
deep_copy[:a] << 4
original[:a]  # => [1, 2, 3] — unchanged!

# Frozen string literals (performance magic):
# frozen_string_literal: true
# (at top of file — makes ALL string literals frozen in that file)
# Result: Ruby reuses the same object for identical literals!
# Can reduce memory by 30-40% in string-heavy code!
```

---

## 🚀 9. Advanced Concepts (Expert Level)

---

### Advanced Concept 1: Metaprogramming — Code That Writes Code

```ruby
# ── OPEN CLASSES — Reopen any class and add methods! ─────────────────────
class Integer
  def factorial
    return 1 if self <= 1
    self * (self - 1).factorial
  end

  def prime?
    return false if self < 2
    (2..Math.sqrt(self)).none? { |i| self % i == 0 }
  end

  def seconds = self
  def minutes = self * 60
  def hours   = self * 3600
  def days    = self * 86_400
end

puts 5.factorial  # => 120
puts 7.prime?     # => true
Time.now + 2.hours  # 2 hours from now!

class String
  def word_count
    split.size
  end

  def titleize
    split.map(&:capitalize).join(" ")
  end

  def palindrome?
    cleaned = downcase.gsub(/[^a-z0-9]/, "")
    cleaned == cleaned.reverse
  end
end

"hello world".word_count  # => 2
"the quick brown fox".titleize  # => "The Quick Brown Fox"

class Array
  def second = self[1]
  def third  = self[2]

  def average
    return nil if empty?
    sum.to_f / size
  end

  def frequencies
    tally
  end
end

[5, 3, 8, 1, 9, 2].average  # => 4.666...
["a", "b", "a", "c", "b", "a"].frequencies  # => {"a"=>3,"b"=>2,"c"=>1}

# ── DEFINE_METHOD — create methods programmatically ───────────────────────
class Logger
  LEVELS = %i[debug info warn error fatal].freeze

  LEVELS.each do |level|
    define_method(level) do |message|
      output("[#{level.upcase}] #{message}")
    end

    define_method("#{level}?") do
      @level <= LEVELS.index(level)
    end
  end

  def initialize(level = :info)
    @level = LEVELS.index(level)
  end

  private

  def output(msg)
    puts "#{Time.now.strftime('%H:%M:%S')} #{msg}"
  end
end

log = Logger.new(:warn)
log.debug("This is hidden")  # Won't print (below warn level)
log.warn("This shows!")      # Prints
log.error("Uh oh!")          # Prints

# ── METHOD_MISSING — handle undefined method calls ────────────────────────
class FlexibleRecord
  def initialize(data = {})
    @data = data
  end

  def method_missing(name, *args)
    name_str = name.to_s
    if name_str.end_with?("=")
      @data[name_str.chomp("=").to_sym] = args.first
    elsif name_str.end_with?("?")
      !@data[name_str.chomp("?").to_sym].nil?
    elsif @data.key?(name)
      @data[name]
    else
      super
    end
  end

  def respond_to_missing?(name, include_private = false)
    name.to_s.end_with?("=", "?") || @data.key?(name) || super
  end

  def to_h = @data
end

record = FlexibleRecord.new
record.name = "Aryan"  # Calls method_missing with :name=
record.age  = 17
puts record.name       # "Aryan"
puts record.name?      # true
puts record.email?     # false

# ── CLASS_EVAL AND INSTANCE_EVAL ──────────────────────────────────────────
# class_eval — execute code in the context of a class:
String.class_eval do
  def shout
    "#{upcase}!!!"
  end
end
"hello".shout  # => "HELLO!!!"

# instance_eval — execute code in the context of an object:
obj = Object.new
obj.instance_eval do
  @secret = 42  # Sets instance variable on obj
  def secret
    @secret  # Defines method on obj (singleton method)
  end
end
obj.secret  # => 42

# ── DSL BUILDING — the reason Ruby is so popular for DSLs ────────────────
class RouteBuilder
  attr_reader :routes

  def initialize
    @routes = []
  end

  def get(path, **options, &handler)
    @routes << { method: :GET, path: path, options: options, handler: handler }
  end

  def post(path, **options, &handler)
    @routes << { method: :POST, path: path, options: options, handler: handler }
  end

  def middleware(name)
    @routes.each { |r| (r[:middleware] ||= []) << name }
  end
end

class Application
  def self.routes(&block)
    builder = RouteBuilder.new
    builder.instance_eval(&block)  # Execute block as if inside builder
    @routes = builder.routes
  end

  def self.start
    puts "Starting with #{@routes.size} routes:"
    @routes.each { |r| puts "  #{r[:method]} #{r[:path]}" }
  end
end

Application.routes do
  get "/", cache: true do
    "Welcome home!"
  end

  post "/users" do
    "Creating user..."
  end

  get "/users/:id", auth: :required do |id|
    "User #{id}"
  end
end

Application.start
```

---

### Advanced Concept 2: Fibers — Cooperative Concurrency

```ruby
# Fibers — cooperative threads (not preemptive like OS threads)
# Control exactly when a fiber pauses and resumes

# Basic Fiber:
fiber = Fiber.new do
  puts "Fiber started"
  Fiber.yield "first value"  # Pause here, return "first value"
  puts "Fiber resumed"
  Fiber.yield "second value"
  puts "Fiber finishing"
  "final value"              # Last value is return value of fiber.resume
end

puts fiber.resume     # "Fiber started", prints "first value"
puts fiber.resume     # "Fiber resumed", prints "second value"
puts fiber.resume     # "Fiber finishing", prints "final value"
# fiber.resume       # => FiberError: dead fiber called

# Generator pattern with Fibers:
def fibonacci_generator
  Fiber.new do
    a, b = 0, 1
    loop do
      Fiber.yield a
      a, b = b, a + b
    end
  end
end

fib = fibonacci_generator
10.times { print "#{fib.resume} " }  # 0 1 1 2 3 5 8 13 21 34

# Producer-consumer with Fibers:
producer = Fiber.new do
  5.times do |i|
    puts "Producing item #{i}"
    Fiber.yield i
  end
  nil  # Signal done
end

consumer = Fiber.new do |item|
  while item
    puts "Consuming item #{item}"
    item = Fiber.yield
  end
end

consumer.resume  # Start consumer, it waits for first item
loop do
  item = producer.resume
  break if item.nil?
  consumer.resume(item)
end

# Fiber.scheduler (Ruby 3.0+) — non-blocking I/O with fibers:
# Used by async gem for cooperative multitasking
require "async"  # gem install async

Async do
  task1 = Async { sleep(2); puts "Task 1 done" }
  task2 = Async { sleep(1); puts "Task 2 done" }
  # Both run concurrently! Total time: ~1 second, not 3
end
```

---

### Advanced Concept 3: Ruby's ObjectSpace & Reflection

```ruby
require "objspace"

# ObjectSpace — enumerate and inspect all live objects
ObjectSpace.each_object(String) { |s| puts s if s.frozen? && s.length > 20 }

# Count objects by type:
counts = Hash.new(0)
ObjectSpace.each_object { |obj| counts[obj.class] += 1 }
counts.sort_by { |_, v| -v }.first(10).each { |cls, n| puts "#{cls}: #{n}" }

# Memory size of object:
str = "hello world"
ObjectSpace.memsize_of(str)  # => size in bytes

# ── REFLECTION — inspect code at runtime ──────────────────────────────────
class MyClass
  MY_CONST = 42
  attr_accessor :name

  def public_method = "public"
  protected def protected_method = "protected"
  private def private_method = "private"
end

obj = MyClass.new

# Inspect methods:
MyClass.instance_methods(false)           # => [:name, :name=, :public_method]
MyClass.protected_instance_methods(false) # => [:protected_method]
MyClass.private_instance_methods(false)   # => [:private_method]
MyClass.public_instance_method(:public_method) # UnboundMethod

# Inspect class hierarchy:
MyClass.ancestors      # => [MyClass, Object, Kernel, BasicObject]
MyClass.superclass     # => Object
MyClass.included_modules # => [Kernel]

# Inspect constants:
MyClass.constants      # => [:MY_CONST]
MyClass.const_get(:MY_CONST) # => 42

# Inspect instance variables:
obj.name = "Aryan"
obj.instance_variables  # => [:@name]
obj.instance_variable_get(:@name)  # => "Aryan"
obj.instance_variable_set(:@name, "Priya")

# Inspect methods dynamically:
obj.methods            # All methods (including inherited)
obj.public_methods     # Only public methods
obj.respond_to?(:name) # => true
obj.respond_to?(:private_method) # => false (doesn't check private by default)
obj.respond_to?(:private_method, true) # => true (second arg = include_private)

# method() — get Method object:
m = obj.method(:name)
m.call                  # => "Priya"
m.arity                 # => 0 (no required args)
m.owner                 # => MyClass
m.source_location       # => ["script.rb", 5] — where method is defined!
m.unbind                # => UnboundMethod
```

---

### ⚡ Performance & Optimization Table

| Technique                              | Impact   | When to Use                                          |
|----------------------------------------|----------|------------------------------------------------------|
| `# frozen_string_literal: true`        | High     | Every file — reduces string allocations drastically  |
| `Symbol` keys in hashes (vs strings)   | Medium   | Hash lookups faster with symbols                     |
| Lazy enumerators                       | High     | Large/infinite sequences — avoid materializing       |
| `Array#flatten(1)` vs `flatten`        | Medium   | Stop at first level when deeper isn't needed         |
| Pre-allocate Array: `Array.new(n, default)` | High| Avoid repeated reallocation                         |
| `StringIO` instead of `+` concatenation | High    | Building large strings in a loop                    |
| `dup` instead of `clone` when possible | Low      | dup is slightly faster (skips singleton class copy) |
| Memoization: `@result ||= compute`     | Very High| Cache expensive computations on objects              |
| `hash.fetch` vs `hash[]`              | Low      | fetch with default avoids nil checks                 |
| YJIT (Ruby 3.1+): `RUBY_YJIT_ENABLE=1`| Very High| JIT compilation — up to 40% faster for Rails apps   |

---

## 💀 10. 0.01% Hidden Secrets — Ultra Elite

---

### 🔮 Secret 1: `BasicObject` — Minimal Object for DSLs

```ruby
# BasicObject is Ruby's root — even Object inherits from it!
# BasicObject has almost NO methods — perfect for clean DSLs and proxies.

BasicObject.instance_methods  # => [:==, :equal?, :!, :!=, :instance_eval, ...]
# Compare to Object.instance_methods.length  # => 60+

class CleanProxy < BasicObject
  def initialize(target)
    @target = target
  end

  def method_missing(name, *args, &block)
    ::Kernel.puts "Calling: #{name}(#{args})"  # Must use ::Kernel!
    @target.public_send(name, *args, &block)
  end

  def respond_to_missing?(name, include_private = false)
    @target.respond_to?(name, include_private)
  end
end

# Almost every method dispatches to target — nothing predefined to interfere:
proxy = CleanProxy.new("hello world")
proxy.upcase     # => "HELLO WORLD" (via method_missing)
proxy.split      # => ["hello", "world"]
proxy.length     # => 11

# Real use case: BlankSlate in older Ruby, Delegator::BasicDelegator, tracing proxies
```

---

### 🔮 Secret 2: `binding` — Capture the Execution Context

```ruby
# binding captures the current execution context:
# all local variables, self, and the block (if any)

def make_binding(x, y)
  local_var = x + y
  binding  # Returns a Binding object capturing this context!
end

b = make_binding(3, 4)
b.eval("local_var")       # => 7 — accesses local variable!
b.eval("x")               # => 3
b.eval("x + y")           # => 7

# b.local_variables        # => [:x, :y, :local_var]
# b.local_variable_get(:x) # => 3
# b.local_variable_set(:x, 99) # Change a local variable in the binding!

# ERB uses binding to access local variables:
require "erb"
name = "Aryan"
score = 98
template = ERB.new("Hello, <%= name %>! Score: <%= score %>")
template.result(binding)  # => "Hello, Aryan! Score: 98"

# Use in DSLs for clean evaluation:
class ConfigDSL
  def initialize(&block)
    instance_eval(&block)  # Block runs with self = this instance
  end

  def database(url)
    @db_url = url
  end

  def port(num)
    @port = num
  end
end

config = ConfigDSL.new do
  database "postgresql://localhost/myapp"
  port 5432
end
```

---

### 🔮 Secret 3: `Refinements` — Scoped Monkey Patching

```ruby
# Refinements let you extend classes but ONLY within a specific scope!
# Solves the global pollution problem of open classes.

module StringExtensions
  refine String do
    def word_count
      split.size
    end

    def palindrome?
      cleaned = downcase.gsub(/[^a-z0-9]/, "")
      cleaned == cleaned.reverse
    end
  end
end

module IntegerExtensions
  refine Integer do
    def factorial
      (1..self).reduce(1, :*)
    end
  end
end

# Without refinement — these methods don't exist:
# "hello world".word_count  # NoMethodError!

module MyFeature
  using StringExtensions   # Activate refinement in THIS scope only
  using IntegerExtensions

  def self.analyze(text)
    words = text.word_count  # Works here!
    "#{words} words, factorial: #{words.factorial}"
  end

  def self.is_palindrome?(text)
    text.palindrome?         # Works here!
  end
end

MyFeature.analyze("hello world ruby")  # => "3 words, factorial: 6"
MyFeature.is_palindrome?("racecar")    # => true

# Outside MyFeature — refinements NOT active:
# "hello world".word_count  # Still NoMethodError!

# This is how refinements protect the global namespace!
# Perfect for library authors who want to extend core classes without polluting.
```

---

### 🔮 Secret 4: Proc Curry and Function Composition Pipeline

```ruby
# Building a functional pipeline with curry and composition:

# Curried operations:
add      = ->(x, y) { x + y }
multiply = ->(x, y) { x * y }
subtract = ->(x, y) { x - y }

add5      = add.curry.(5)        # Partial application: adds 5
triple    = multiply.curry.(3)   # Partial application: multiplies by 3
subtract2 = subtract.curry.(2)   # subtract2.(x) = 2 - x (not x - 2!)

# Better: use the second arg via flip:
flip = ->(f) { ->(x, y) { f.(y, x) } }
subtract_from = flip.(subtract)
subtract2_from = subtract_from.curry.(2)  # x - 2

# Compose a pipeline:
double_then_add5 = method(:itself)
  .to_proc
  .then { multiply.curry.(2) }
  .then { |f| ->(x) { add5.(f.(x)) } }

# Or using >> and <<:
pipeline = triple >> add5 >> subtract2_from
pipeline.(4)  # => (4*3)+5-2 = 15

# Real pipeline with Ruby 2.6+ composition:
normalize = ->(s) { s.strip.downcase }
tokenize  = ->(s) { s.split(/\W+/).reject(&:empty?) }
remove_stopwords = ->(words) { words - %w[the a an is are was were] }
count_freq = ->(words) { words.tally.sort_by { |_,v| -v } }

analyze = normalize >> tokenize >> remove_stopwords >> count_freq
analyze.("The quick brown fox is a quick animal")
# => [["quick", 2], ["brown", 1], ["fox", 1], ["animal", 1]]
```

---

### 🔮 Secret 5: `TracePoint` — Runtime Code Tracing

```ruby
# TracePoint — hook into Ruby's VM execution events!
# Used for profilers, debuggers, test coverage tools

# Available events:
# :call          — method call
# :return        — method return
# :class         — class/module definition
# :end           — end of class/module
# :raise         — exception raised
# :b_call        — block call
# :b_return      — block return
# :c_call        — C-level function call
# :c_return      — C-level function return
# :thread_begin  — new thread starts
# :thread_end    — thread ends
# :line          — each new line executed
# :script_compiled — code is compiled

# Method call tracer:
tracer = TracePoint.new(:call, :return) do |tp|
  indent = tp.event == :call ? "→" : "←"
  puts "#{indent} #{tp.defined_class}##{tp.method_id} (#{tp.path}:#{tp.lineno})"
end

tracer.enable { "hello".upcase.reverse }
# → String#upcase (string.rb:N)
# ← String#upcase (string.rb:N)
# → String#reverse (string.rb:N)
# ← String#reverse (string.rb:N)

# Exception tracer — find where exceptions are RAISED (not rescued):
exception_tracer = TracePoint.new(:raise) do |tp|
  puts "RAISED: #{tp.raised_exception.class}: #{tp.raised_exception.message}"
  puts "  at #{tp.path}:#{tp.lineno}"
end

exception_tracer.enable

# Coverage tool:
executed_lines = Hash.new { |h, k| h[k] = [] }
line_tracer = TracePoint.new(:line) do |tp|
  executed_lines[tp.path] << tp.lineno
end

line_tracer.enable { run_tests }  # Enable only during tests
# Now executed_lines shows which lines were exercised!

# Object allocation tracer:
alloc_counts = Hash.new(0)
alloc_tracer = TracePoint.new(:c_return) do |tp|
  alloc_counts[tp.defined_class] += 1 if tp.method_id == :new
end
```

---

### 🔮 Secret 6: Ractor — Parallel Execution Without GIL

```ruby
# Ractor (Ruby 3.0+) — true parallelism in Ruby!
# Each Ractor has its own GVL (Global VM Lock) — true multi-core!

# The rule: Ractors cannot share mutable state (enforces thread safety)
# Communication: via message passing (like Erlang/Go channels)

# Simple parallel computation:
results = (1..8).map do |i|
  Ractor.new(i) do |n|
    # Compute in parallel:
    (1..n * 100_000).reduce(0) { |sum, x| sum + x }
  end
end.map(&:take)  # Collect results (blocks until each Ractor finishes)

puts results.sum

# Pipeline with Ractors:
pipeline_start = Ractor.new do
  (1..10).each do |n|
    Ractor.yield n  # Send to next stage
  end
end

doubler = Ractor.new(pipeline_start) do |upstream|
  loop do
    value = upstream.take
    Ractor.yield value * 2
  end
end

printer = Ractor.new(doubler) do |upstream|
  loop do
    value = upstream.take
    puts "Processed: #{value}"
  end
end

printer.take  # Wait for processing

# Ractor message passing:
r = Ractor.new do
  msg = Ractor.receive  # Block until message received
  "Got: #{msg}"
end

r.send("hello")   # Send message
r.take            # => "Got: hello"

# Ractors can share frozen/immutable objects:
SHARED_CONFIG = { timeout: 30, retries: 3 }.freeze  # frozen = shareable!
ractors = 4.times.map { Ractor.new(SHARED_CONFIG) { |cfg| cfg[:timeout] } }
ractors.map(&:take)  # => [30, 30, 30, 30]
```

---

### 🔮 Secret 7: Singleton Methods and Eigenclass

```ruby
# Every Ruby object has a hidden class called the "eigenclass" or "singleton class"
# This is where singleton methods (methods defined on a single object) live

obj = "hello"

# Define a method on just this one string object:
def obj.shout
  "#{upcase}!!!"
end

obj.shout          # => "HELLO!!!"
"world".shout      # => NoMethodError — only obj has this method!

# The eigenclass:
eigenclass = obj.singleton_class
eigenclass.instance_methods(false)  # => [:shout]

# Class methods ARE singleton methods on the Class object!
class Dog
  def self.species   # This is actually a singleton method on Dog
    "Canis lupus familiaris"
  end
end

Dog.singleton_class.instance_methods(false)  # => [:species]

# Equivalent ways to define class methods:
class Cat
  class << self      # Open eigenclass explicitly
    def species
      "Felis catus"
    end

    def describe
      "A domestic cat"
    end
  end
end

# Why this matters:
# When you call obj.method_name, Ruby looks in:
# 1. obj's eigenclass (singleton methods)
# 2. obj's class
# 3. Modules included in obj's class (in reverse inclusion order)
# 4. obj's superclass
# 5. ... up the chain to BasicObject

# extend adds a module's methods to the EIGENCLASS:
module Debuggable
  def debug_info
    "#{self.class}@#{object_id}: #{inspect}"
  end
end

user = User.new("Aryan", "a@b.com")
user.extend(Debuggable)           # Only for this one user object
user.debug_info                   # Works!
User.new("Bob", "b@b.com").debug_info # => NoMethodError (not extended)
```

---

### 🔮 Secret 8: `Comparable#clamp` and Custom Enumerators

```ruby
# clamp — keep value within range (Ruby 2.4+):
5.clamp(1, 10)       # => 5 (in range)
0.clamp(1, 10)       # => 1 (below minimum)
15.clamp(1, 10)      # => 10 (above maximum)
5.clamp(1..)         # => 5 (one-sided: minimum only)
5.clamp(..3)         # => 3 (one-sided: maximum only)

# Works on ANY Comparable (including your custom classes!):
Temperature.new(120).clamp(Temperature.new(0), Temperature.new(100))
# => Temperature(100°C) (too hot — clamped to max)

# Enumerator::ArithmeticSequence (Ruby 2.6+):
(1..100).step(3)               # Arithmetic sequence
(0.0..1.0).step(0.1).to_a     # Float ranges!
(1...Float::INFINITY).step(2) # Infinite odd numbers

# Enumerator::Lazy — chain lazy operations:
result = (1..Float::INFINITY)
  .lazy
  .flat_map { |n| [n, n**2] }
  .select { |n| n % 3 == 0 }
  .map { |n| "#{n}" }
  .first(5)
# => ["3", "9", "6", "36", "9"] — computed lazily!

# Custom enumerator with Enumerator.produce (Ruby 2.7+):
# Produces infinite sequence based on previous value:
random_walk = Enumerator.produce(0) { |prev| prev + rand(-1..1) }
random_walk.take(10)  # 10 steps of a random walk

# Tree traversal as lazy enumerator:
def bfs(root)
  Enumerator.new do |yielder|
    queue = [root]
    until queue.empty?
      node = queue.shift
      yielder.yield node
      queue.concat(node.children)
    end
  end
end

bfs(root_node).lazy.select { |node| node.value > 5 }.first(3)
```

---

### 🔮 Secret 9: `__send__` vs `send` — The Subtle Difference

```ruby
# send — calls a method by name, works on all methods including private:
"hello".send(:upcase)     # => "HELLO"
42.send(:+, 8)            # => 50

# __send__ — same but CANNOT be overridden by user code:
# If someone defines a 'send' method in their class, __send__ still works!

class WeirdClass
  def send(method_name)
    "I've hijacked send! You wanted: #{method_name}"
  end

  def do_it
    __send__(:real_method)  # Still works!
  end

  def real_method
    "This is the real method"
  end
end

wc = WeirdClass.new
wc.send(:real_method)    # => "I've hijacked send! You wanted: real_method"
wc.__send__(:real_method) # => "This is the real method"
wc.do_it                 # => "This is the real method"

# Rule: in library/framework code, use __send__ or public_send
# public_send — like send but raises for private methods:
"hello".public_send(:upcase)   # => "HELLO"
# String.new.public_send(:initialize) # => NoMethodError (private)

# tap — call a method on an object, return the object (not the method result):
user = User.new("Aryan", "a@b.com")
  .tap { |u| puts "Created: #{u}" }
  .tap { |u| save_to_db(u) }
  .tap { |u| send_welcome_email(u) }
# user is returned after all tap blocks

# then/yield_self — call a method and return the BLOCK's result:
"hello"
  .then { |s| s.upcase }     # => "HELLO"
  .then { |s| s + "!" }      # => "HELLO!"
  .then { |s| [s] }          # => ["HELLO!"]
```

---

### 🔮 Secret 10: `GC` Module — Control the Garbage Collector

```ruby
# Ruby's garbage collector internals:
GC.stat                   # Hash of GC statistics
GC.count                  # Number of GC runs
GC.start                  # Force a GC run
GC.compact                # Compact the heap (Ruby 2.7+) — reduce fragmentation
GC.disable                # Disable GC (temporarily)
GC.enable                 # Re-enable GC

# GC tuning via environment variables:
# RUBY_GC_HEAP_GROWTH_FACTOR=1.5       # Factor to grow heap by
# RUBY_GC_MALLOC_LIMIT=16777216        # Malloc limit before GC
# RUBY_GC_HEAP_INIT_SLOTS=10000       # Initial heap slots

# GC.stat gives deep insight:
stats = GC.stat
puts "Heap pages: #{stats[:heap_allocated_pages]}"
puts "Live objects: #{stats[:heap_live_slots]}"
puts "Old objects: #{stats[:old_objects]}"
puts "Total GC runs: #{stats[:count]}"
puts "Major GC: #{stats[:major_gc_count]}"
puts "Minor GC: #{stats[:minor_gc_count]}"

# ObjectSpace.garbage_collect — also triggers GC
ObjectSpace.garbage_collect

# Memory profiling with memory_profiler gem:
require "memory_profiler"

report = MemoryProfiler.report do
  100.times { "a" * 1000 }  # Allocate strings
end

report.pretty_print         # Show allocation stats

# Profile what's allocating the most memory:
report.allocated_memsize_by_class_and_location_data.first(5).each do |item|
  puts "#{item.klass}: #{item.memsize} bytes"
end
```

---

## 🗺️ 11. Complete Roadmap

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — FOUNDATION (Week 1-3)
├── Week 1: Setup, IRB, types (integer, string, symbol, nil), control flow
├── Week 2: Methods, blocks, procs, lambdas, arrays, hashes
└── Week 3: Classes, objects, modules, mixins, basic OOP
    └── Project: CLI Todo app, text processor, simple calculator

PHASE 2 — RUBY WAY (Week 4-7)
├── Week 4: Enumerable deeply — all 60+ methods, lazy enumerators
├── Week 5: Error handling, exceptions, custom errors, retry patterns
├── Week 6: File I/O, standard library (Date, Time, JSON, CSV, URI)
└── Week 7: Regular expressions, string processing, ERB templating
    └── Project: Markdown processor, config file parser, data transformer

PHASE 3 — ADVANCED RUBY (Week 8-12)
├── Week 8:  Metaprogramming — open classes, method_missing, define_method
├── Week 9:  Modules deeply — refinements, eigenclass, Comparable, Enumerable
├── Week 10: Concurrency — Fibers, Threads, Ractor (Ruby 3.0+)
├── Week 11: Testing — RSpec (describe, context, it, let, subject, matchers)
└── Week 12: Gems — building your own gem, Bundler, RubyGems publishing
    └── Project: Build and publish a Ruby gem

PHASE 4 — RAILS & ECOSYSTEM (Month 4-5)
├── Month 4: Ruby on Rails — MVC, ActiveRecord, migrations, validations, callbacks
├── Month 5: Rails API mode, Action Cable, Sidekiq background jobs, Hotwire
    └── Project: Full Rails app with auth, background jobs, real-time features

PHASE 5 — EXPERT / 0.01% (Month 6+)
├── TracePoint, ObjectSpace, GC tuning, memory profiling
├── Native extensions (C extensions), JRuby, TruffleRuby
├── YJIT deep dive — JIT compilation internals
├── Contribute to Ruby core, Rails, or major gems
└── Ruby internals — MRI (CRuby) source code reading
    └── Project: Production Rails app or system-level Ruby gem
```

---

### 🏁 Milestone Checklist

- [ ] I understand that everything in Ruby is an object (including nil, integers, booleans)
- [ ] I use blocks, procs, and lambdas naturally and know their differences
- [ ] I can write Enumerable-based code without explicit loops
- [ ] I understand Ruby's module system and method resolution order (ancestors)
- [ ] I can implement a simple DSL using metaprogramming
- [ ] I always pair `method_missing` with `respond_to_missing?`
- [ ] I use `# frozen_string_literal: true` in all my files
- [ ] I have written a full test suite with RSpec
- [ ] I understand the difference between `instance_eval` and `class_eval`
- [ ] I have built and published a RubyGem
- [ ] I can explain how Rails uses Ruby's metaprogramming features
- [ ] I understand Ruby's GC and can profile memory usage
- [ ] I have contributed to an open-source Ruby project
- [ ] I know the Ruby version manager ecosystem (rbenv, RVM)

---

## 🧩 12. Bonus Deep Insights

---

### 🔮 Mental Model: "Objects Send Messages"

Ruby is fundamentally Smalltalk-inspired: **you don't call methods, you send messages to objects.** When you write `"hello".upcase`, you're literally saying to the string object "hello": "I'm sending you the message `:upcase`."

The object decides what to do with that message. If it doesn't have a handler for that message, it passes it up its ancestor chain. If nothing handles it, `method_missing` gets it. If you override `method_missing`, you can handle ANY message — which is why Ruby DSLs can feel like they're written in a completely different language.

This mental model unlocks metaprogramming: you're not doing magic, you're just controlling how objects respond to messages.

---

### 🤫 Deep Insight 1: Ruby's `||=` Is More Complex Than You Think

```ruby
# ||= is the "memoization operator" — but it has subtleties:
x ||= y
# Is NOT the same as: x = x || y
# Is actually:        x || (x = y)
# The difference: x= is only called if x is falsy

# This matters for hash default values:
h = {}
h[:key] ||= "default"   # Sets if nil OR false
h[:key] ||= "other"     # Already "default", no change

# ❌ PROBLEM: ||= can't distinguish nil from "not set":
h[:missing] ||= "default"   # Works — key was nil (missing)
h[:explicit_nil] = nil
h[:explicit_nil] ||= "default"  # Also "works" — but overwrites intentional nil!

# ✅ For hash default use fetch or has_key?:
h.fetch(:key) { "default" }
h[:key] = "default" unless h.key?(:key)  # Preserves intentional nil

# &&= — assign only if current value is truthy:
user.name &&= user.name.upcase  # Only uppercase if name exists
# Same as: user.name = user.name.upcase if user.name

# Memoization in instance methods — the right way:
class ExpensiveComputer
  def result
    @result ||= compute_expensive_thing  # Safe if result is never nil/false
  end

  def result_with_nil_possible
    return @result if defined?(@result)  # nil-safe memoization!
    @result = compute_thing_that_might_return_nil
  end
end
```

---

### 🤫 Deep Insight 2: The Ruby Object Model in One Picture

```
Every Ruby object has:
  ┌────────────────────────────────────────┐
  │ klass pointer → points to its CLASS   │
  │ instance variables [@name, @age, ...]  │
  └────────────────────────────────────────┘

The lookup chain for method calls:
  obj.method_name
  ↓
  obj's singleton class (eigenclass)
  ↓
  obj's class
  ↓
  modules included in obj's class (reverse order)
  ↓
  obj's superclass
  ↓
  modules included in superclass
  ↓
  ... up to BasicObject
  ↓
  method_missing (if defined)
  ↓
  BasicObject#method_missing → NoMethodError

Classes are objects too (instances of Class)!
Class's class is → Class
Class's superclass is → Module
Module's superclass is → Object
Object's superclass is → BasicObject
BasicObject's superclass is → nil (top of hierarchy)

"Constants" (including class names) stored in:
  - Top-level Object if defined at top level
  - Module/Class object if defined inside one
  - Accessible via Module::CONST notation
```

---

### 🧠 The Big Picture — Ruby in the Modern Ecosystem

```
Ruby's evolution:
  Ruby 1.8 (2004):  The scripting language era
  Ruby 1.9 (2007):  Fibers, encoding, VM rewrite (YARV)
  Ruby 2.0 (2013):  Keyword arguments, Module#prepend
  Ruby 2.3 (2015):  Safe navigation &., frozen_string_literal
  Ruby 2.5 (2017):  Bundler integrated, rescue in blocks
  Ruby 2.7 (2019):  Pattern matching (experimental), numbered params
  Ruby 3.0 (2020):  Ractor, Fiber scheduler, 3× faster goal
  Ruby 3.1 (2021):  YJIT (JIT compiler), Fiber improvements
  Ruby 3.2 (2022):  YJIT mature, Data class, regexp improvements
  Ruby 3.3 (2023):  YJIT 20% faster, Prism parser, Thread pool
  Ruby 3.4 (2024):  Frozen string default step, improved backtrace

Ruby's sweet spots in 2025:
  ✅ Web apps (Shopify scale — Rails IS production-ready at massive scale)
  ✅ Rapid prototyping — nothing ships faster
  ✅ DSL creation — the premier language for internal DSLs
  ✅ Developer tooling — Homebrew, Fastlane, CocoaPods
  ✅ Testing — RSpec is the gold standard
  ✅ Business logic — readable, maintainable code
  ✅ Infrastructure automation — Chef, Puppet

The Rails ecosystem today:
  Rails 7.x: Hotwire (Turbo + Stimulus), solid_cache, importmaps
  Sidekiq: Background job processing (most-used Ruby tool)
  RSpec: The testing framework that influenced an entire industry
  Devise: Authentication
  Pundit/CanCanCan: Authorization
  Puma: Multi-threaded web server
  Kamal: Rails deployment (from Basecamp team)
  Sorbet/RBS: Optional type checking for Ruby

Ruby vs Python comparison:
  Both: Scripting, web development, automation
  Ruby wins: Web apps (Rails >> Django ergonomics), DSLs, readability
  Python wins: Data science, ML/AI, scientific computing, wider adoption
  Both excellent: Automation, scripting, API development

Learning Ruby teaches you:
  - True OOP (everything is an object)
  - Metaprogramming (code that writes code)
  - DSL design (how to build expressive APIs)
  - Testing culture (RSpec's impact is permanent)
  - Programmer happiness philosophy (influences how you evaluate tools)
```

---

## 📌 13. Summary (Quick Revision & Cheat Sheet)

---

### Core Concepts (1-line each)

| Concept              | What It Means                                                              |
|----------------------|----------------------------------------------------------------------------|
| Everything is object | `1.class` → Integer; `nil.nil?` → true; even classes are objects         |
| Duck typing          | Objects respond to messages; check `respond_to?` not `is_a?`             |
| Blocks               | Anonymous code chunks attached to method calls — foundation of iterators  |
| Mixins               | `include Module` adds instance methods; `extend` adds class methods       |
| Open classes         | Any class (including String, Integer) can be reopened and extended        |
| Metaprogramming      | `method_missing`, `define_method`, `class_eval` — code writes code        |
| Symbol vs String     | Symbols are immutable, interned (same object always); strings are mutable |
| `||=` memoization    | `@result ||= expensive()` — compute once, cache forever (careful with nil!)|
| Enumerable           | Include + define `each` → 60+ iteration methods for free                 |
| `frozen_string_literal` | Makes string literals immutable — significant memory/performance win   |

---

### The 10 Things to Remember

1. ✅ **Always add `# frozen_string_literal: true`** to every Ruby file
2. ✅ **Prefer `map`, `select`, `reject` over explicit loops** — Enumerable is the Ruby way
3. ✅ **Use symbols for hash keys** — `{name: "Aryan"}` not `{"name" => "Aryan"}`
4. ✅ **Pair `method_missing` with `respond_to_missing?`** — always, without exception
5. ✅ **Use `public_send` over `send`** in library code — respects visibility
6. ✅ **`rescue StandardError`** not `rescue Exception` — don't trap signals
7. ✅ **Use `fetch` on hashes** when key is required — raises on missing vs silent nil
8. ✅ **`freeze` your constants** — `ARRAY = [].freeze` prevents accidental mutation
9. ✅ **Use keyword arguments** for methods with 3+ parameters — self-documenting
10. ✅ **Write the test first** — Ruby's testing culture (RSpec) will make you a better programmer

---

### Quick Reference Cheat Sheet

```ruby
# ── SETUP & TOOLING ────────────────────────────────────────────────────────
# rbenv install 3.3.0 && rbenv global 3.3.0
# gem install bundler && bundle init
# bundle add gem_name
# bundle exec ruby script.rb

# ── STRINGS ───────────────────────────────────────────────────────────────
"hello #{world}"          # Interpolation
'no #{interpolation}'     # Literal
str.upcase / downcase / capitalize / swapcase / reverse / strip / chomp
str.split(",") / str.split
str.gsub(/regex/, replacement) / str.sub("first", "only_first")
str.include?("sub") / str.start_with?("pre") / str.end_with?("suf")
str[0..5] / str[-3..] / str[/regex/]
"%-20s %.2f" % [label, value]  # sprintf-style formatting

# ── ARRAYS ────────────────────────────────────────────────────────────────
arr.push(x) / arr << x    # Append
arr.pop / arr.shift        # Remove last / first
arr.unshift(x)             # Prepend
arr.map { |x| x*2 }        # Transform → new array
arr.select { |x| x>0 }    # Filter → new array
arr.reject { |x| x<0 }    # Inverse filter
arr.reduce(0, :+)          # Fold with symbol
arr.flat_map { |x| [x,x] }# Map + flatten
arr.each_with_object([]) { |x,acc| acc << x if x>0 }
arr.group_by { |x| x%3 }  # Group → hash
arr.sort_by { |x| -x }    # Sort by criterion
arr.min_by / arr.max_by    # Extremum by criterion
arr.zip(other)             # Combine → [[a1,b1],[a2,b2],...]
arr.tally                   # Count occurrences → {"a"=>3,...}
arr.filter_map { |x| x*2 if x>0 } # Map + filter in one
arr.partition { |x| x.even? } # → [evens, odds]
arr.each_slice(3).to_a     # Chunk into groups of 3
arr.each_cons(2).to_a      # Sliding window pairs
arr.flatten(1)             # Flatten one level
arr.compact                # Remove nils
arr.uniq                   # Remove duplicates
arr.first(3) / arr.last(3) # Take n from each end

# ── HASHES ────────────────────────────────────────────────────────────────
h = { name: "Aryan", age: 17 }     # Symbol keys (preferred)
h[:name] / h.fetch(:name)           # Access (nil vs raise)
h.fetch(:key, "default")            # With default
h.merge(other) { |k, o, n| o + n } # Merge with conflict resolver
h.transform_values { |v| v.to_s }  # Transform all values
h.transform_keys { |k| k.to_s }    # Transform all keys
h.select { |k,v| v > 0 }           # Filter pairs → hash
h.reject { |k,v| v.nil? }          # Inverse filter
h.any? { |k,v| v > 10 }            # Predicate
h.min_by { |k,v| v }               # Minimum pair
h.each_with_object({}) { |(k,v),acc| acc[v] = k } # Invert hash
h.group_by { |k,v| v.class }       # Group pairs

# ── CLASSES & MODULES ─────────────────────────────────────────────────────
class Name < Parent
  include ModuleA       # Adds instance methods
  extend ModuleB        # Adds class methods
  prepend ModuleC       # Adds before existing methods in MRO
  attr_reader :x        # Creates x getter
  attr_writer :y        # Creates y= setter
  attr_accessor :z      # Creates z getter and setter
  def initialize(x) @x = x end
  def method = expression  # Endless method (Ruby 3.0+)
  def self.class_method; end
  protected def protected_method; end
  private def private_method; end
end

# ── BLOCKS AND ITERATORS ──────────────────────────────────────────────────
def method_with_block
  yield if block_given?          # Call the block
  result = yield(arg)            # Call block with argument
end
proc = Proc.new { |x| x * 2 }  # Proc
lamb = ->(x) { x * 2 }          # Lambda (strict args)
[1,2,3].map(&:to_s)             # Symbol to proc shorthand
[1,2,3].map(&method(:puts))     # Method to proc

# ── PATTERN MATCHING (Ruby 3.0+) ──────────────────────────────────────────
case data
in { name: String => name, age: (18..) }
  puts "Adult: #{name}"
in [Integer => first, *rest]
  puts "Array starting with int: #{first}"
in { status: :ok, value: }      # Rightward assignment
  puts value
end

data => { name:, age: }         # Deconstruct (raises if no match)
data in { name: }               # Check without raising (=> true/false)

# ── USEFUL IDIOMS ─────────────────────────────────────────────────────────
x ||= default                   # Assign if nil/false
x &&= transform(x)              # Assign if truthy
obj&.method                     # Safe navigation (nil if obj is nil)
array.tap { |a| puts a.length } # Debug in chain
value.then { |v| transform(v) } # Chain transformations
hash.dig(:a, :b, :c)           # Safe nested access
arr.flatten.compact.uniq        # Common cleanup chain
puts "Negative!" unless score >= 0  # unless = if not

# ── COMMON STDLIB ─────────────────────────────────────────────────────────
require "json"
JSON.parse(string)              # String → Hash/Array
JSON.generate(obj)              # Hash/Array → String
JSON.pretty_generate(obj)       # Formatted JSON

require "csv"
CSV.read("file.csv", headers: true)  # Read with headers as keys
CSV.generate { |csv| csv << ["col1","col2"] }  # Generate CSV

require "date"
Date.today                      # Current date
Date.parse("2025-03-29")        # Parse string
date + 30                       # Add 30 days
date.strftime("%B %d, %Y")     # Format: "March 29, 2025"

require "time"
Time.now                        # Current time
Time.now.iso8601                # "2025-03-29T10:30:00+05:30"
Time.parse("2025-03-29 10:30") # Parse string

require "uri"
URI.parse("https://example.com/path?key=val")
uri.host / uri.path / uri.query

require "digest"
Digest::SHA256.hexdigest("data")  # SHA256 hash
Digest::MD5.hexdigest("data")     # MD5 (don't use for security!)

require "securerandom"
SecureRandom.uuid               # "550e8400-e29b-41d4-a716-..."
SecureRandom.hex(32)            # 64-char hex string
SecureRandom.base64(32)         # Base64 encoded bytes
```

---

### What's Next?

After mastering Ruby deeply, your natural paths:

- 📘 **Ruby on Rails** — The framework that made Ruby famous — MVC, ActiveRecord, ActionCable, Hotwire
- 📘 **RSpec** — The most expressive test framework in any language — BDD, matchers, shared contexts
- 📘 **Sinatra / Hanami** — Lightweight Ruby web frameworks for APIs and microservices
- 📘 **Sidekiq** — Background job processing — the standard for Ruby async work
- 📘 **Sorbet / RBS** — Optional type checking for Ruby — the path to safer large codebases
- 📘 **TruffleRuby** — JVM-based Ruby with true parallelism and significant performance improvements

---

> 💬 *"Ruby is designed to make programmers happy."*
> — Yukihiro "Matz" Matsumoto, creator of Ruby

> 💬 *"I hope to see Ruby help every programmer in the world to be productive, and to enjoy programming, and to be happy. That is the primary purpose of the Ruby language."*
> — Matz

> 💬 *"Ruby has a beautiful, expressive syntax that reads almost like poetry. Once you write Ruby, every other language feels like work."*
> — The Ruby Community

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: Ruby — Complete Language Mastery | Version: 1.0*
*Sections: 13 | Level: Beginner → 0.01% Elite*
