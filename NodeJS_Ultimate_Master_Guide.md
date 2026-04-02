# 🟢 Node.js — The Ultimate Master Guide
### From Zero to 0.01% Expert — Every Concept, Event Loop Secret, System Trick & Hidden Power

> 📘 **The most complete Node.js guide ever written — beginner to elite.**
>
> 🎯 *Who is this for?* Anyone who wants to go from writing Node.js to **mastering** it — understanding every layer from V8 to libuv to production deployment.
> ⏱️ *Time to complete:* Self-paced — days to months
> 🛠️ *What you'll gain:* Every API, async pattern, stream technique, performance trick, security secret, and 0.01% hidden technique that separates an elite Node.js engineer from the rest.

---

## Table of Contents

1. [🧠 What is Node.js?](#1-what-is-nodejs-super-simple)
2. [🌍 Why Node.js Exists & Dominates](#2-why-nodejs-exists--dominates)
3. [🧱 Core Fundamentals](#3-core-fundamentals-beginner-level)
4. [⚙️ Complete System Breakdown](#4-complete-system-breakdown)
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

## 🧠 1. What is Node.js? (Super Simple)

### The 12-Year-Old Explanation

Imagine JavaScript — the language that makes websites interactive — was always trapped inside web browsers. It could only run inside Chrome or Firefox, talking to web pages. Then in 2009, **Ryan Dahl** had a revolutionary idea: "What if JavaScript could run OUTSIDE the browser? What if it could run on servers, read files, create network connections — just like Python or Java?"

He took V8, Google's incredibly fast JavaScript engine from Chrome, and wrapped it with a layer that could talk to the operating system. He called it **Node.js**. Suddenly, JavaScript could do everything — run web servers, access databases, process files, and handle thousands of network connections simultaneously.

The secret power of Node.js is its **event-driven, non-blocking I/O model**. Instead of waiting for one thing to finish before starting another (like a waiter who takes one order, goes to the kitchen, waits for the food, comes back, THEN takes the next table's order), Node.js is like a waiter who takes ALL orders first, gives them ALL to the kitchen, and handles each table as the food becomes ready. One waiter, serving many tables efficiently.

### Real-Life Analogy

💡 **Think of it like this:**
A traditional server is like a bank with tellers. Each customer gets ONE dedicated teller who stays with them until the transaction is complete. If you have 100 customers, you need 100 tellers — expensive, slow to scale.

**Node.js is like a bank with ONE incredibly fast teller and a numbered ticket system.** You take a ticket (your request), the teller starts your transaction, and if it needs time (database, file, network), the teller moves to the NEXT customer. When your result is ready, your ticket number is called and the teller finishes your transaction immediately. One person, efficiently serving thousands.

### One-Line Definition

> **Node.js** is a cross-platform, open-source JavaScript runtime environment that executes JavaScript code outside a web browser using Google's V8 engine, enabling server-side JavaScript with an event-driven, non-blocking I/O architecture designed for building scalable network applications.

---

## 🌍 2. Why Node.js Exists & Dominates

### The Problem It Solved

In 2009, building web servers with Apache/PHP or Java meant one thread per connection. A thread is expensive — 1MB+ of memory each. A server with 1GB RAM could handle maybe 1000 simultaneous connections. For a chat application or real-time service needing 100,000 simultaneous connections, you needed a massive, expensive infrastructure.

Ryan Dahl observed that most server time is spent **waiting** — waiting for database queries, file reads, network responses. Threads sat idle, wasting memory, while waiting for I/O. The insight: what if we never waited? What if we started the I/O operation and moved on, coming back when the result was ready?

Node.js's single-threaded event loop handles thousands of simultaneous connections with minimal memory because it NEVER blocks waiting for I/O. LinkedIn rebuilt its mobile backend with Node.js and went from 30 servers to 3.

### Where Node.js Dominates in 2025

| Domain                        | How Node.js Is Used                                                    |
|-------------------------------|------------------------------------------------------------------------|
| REST APIs & Microservices      | Express, Fastify, NestJS — the most popular API stack in the world    |
| Real-Time Applications        | Socket.IO, WebSockets — chat, gaming, collaborative tools             |
| Streaming Services            | Netflix, Twitch — Node handles their streaming media pipelines        |
| CLI Tools                     | npm, yarn, eslint, webpack, vite — all Node.js CLI tools             |
| Serverless Functions          | AWS Lambda, Vercel, Netlify — Node.js is the default runtime         |
| Full-Stack JavaScript         | Next.js, Remix, Nuxt — server rendering with Node.js                 |
| Build Tools & Dev Experience  | Vite, esbuild, Rollup — JavaScript tooling IS Node.js                |
| IoT & Edge Computing          | Cloudflare Workers, Deno — JavaScript at the edge                    |
| GraphQL Servers               | Apollo Server, Pothos — the most popular GraphQL runtime              |
| Automation & Scripting        | Puppeteer, Playwright — browser automation in JavaScript             |

### Why YOU Should Master It Deeply

1. **The most-deployed runtime on Earth** — npm has 2 million+ packages; more JavaScript runs in Node than any other server runtime.
2. **Full-stack in one language** — React frontend + Node.js backend + MongoDB — JavaScript end-to-end.
3. **AI/ML tooling** — LangChain.js, OpenAI SDK, Anthropic SDK — AI integrations are first-class in Node.js.
4. **Job market dominance** — Node.js developer is the most common backend job title globally.
5. **The hidden depths are vast** — streams, worker threads, cluster, libuv internals — mastering Node.js makes you a 10× engineer.

---

## 🧱 3. Core Fundamentals (Beginner Level)

> 🎯 *Goal: Build an unshakeable foundation. Every concept here is critical.*

---

### Concept 1: Node.js Setup, REPL & Module System

```javascript
// ── INSTALLATION ──────────────────────────────────────────────────────────
// Use nvm (Node Version Manager) — NEVER install Node directly!
// curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
// nvm install --lts          # Install latest LTS
// nvm use --lts              # Use LTS
// nvm install 20.11.0        # Install specific version
// nvm ls                     # List installed versions
// node --version             # Check current version
// npm --version

// ── THE REPL (Read-Eval-Print Loop) ──────────────────────────────────────
// Just type `node` in terminal:
// > 2 + 2               → 4
// > "hello".toUpperCase() → 'HELLO'
// > .help                → REPL commands
// > .exit                → Exit REPL
// > _                    → Last evaluated value

// ── RUNNING SCRIPTS ───────────────────────────────────────────────────────
// node script.js             # Run a file
// node --watch script.js     # Auto-restart on changes (Node 18+)
// node -e "console.log('hi')" # Execute string directly
// node --inspect script.js   # Enable debugger
// node --inspect-brk script.js # Debug with breakpoint at first line

// ── COMMONJS MODULES (Traditional Node.js) ───────────────────────────────
// math.js
const add = (a, b) => a + b;
const multiply = (a, b) => a * b;
const PI = 3.14159265358979;

module.exports = { add, multiply, PI };
// Or: module.exports.add = add;
// Or: exports.add = add; (shorthand for module.exports.add)

// main.js — importing CommonJS:
const { add, multiply, PI } = require('./math');
const math = require('./math');   // Import entire object
const path = require('path');     // Built-in module (no ./)
const fs = require('fs');         // Built-in module
const express = require('express'); // npm package

console.log(add(3, 4));          // 7
console.log(math.PI);            // 3.14159...
console.log(require.resolve('./math')); // Full path to module

// ── ES MODULES (Modern Node.js) ───────────────────────────────────────────
// Two ways to enable ESM:
// 1. Use .mjs extension
// 2. Add "type": "module" to package.json

// math.mjs (or math.js with "type":"module" in package.json):
export const add = (a, b) => a + b;
export const multiply = (a, b) => a * b;
export const PI = Math.PI;
export default { add, multiply, PI }; // Default export

// main.mjs — importing ESM:
import { add, multiply } from './math.mjs';
import math from './math.mjs';           // Default import
import * as allOfMath from './math.mjs'; // Namespace import
import { readFile } from 'fs/promises';  // Built-in ESM
import express from 'express';           // npm package ESM

// Dynamic import (works in both CJS and ESM):
const { add: dynamicAdd } = await import('./math.mjs');

// ── PACKAGE.JSON — The Heart of Every Node.js Project ────────────────────
/*
{
  "name": "my-project",
  "version": "1.0.0",
  "description": "My awesome project",
  "type": "module",              // Enable ESM (omit for CommonJS)
  "main": "dist/index.js",       // Entry point for CJS
  "module": "dist/index.mjs",    // Entry point for ESM bundlers
  "exports": {
    ".": {
      "import": "./dist/index.mjs",
      "require": "./dist/index.js"
    }
  },
  "scripts": {
    "start":   "node src/index.js",
    "dev":     "node --watch src/index.js",
    "build":   "tsc",
    "test":    "node --test",
    "lint":    "eslint .",
    "format":  "prettier --write ."
  },
  "dependencies": {
    "express": "^4.18.2"
  },
  "devDependencies": {
    "typescript": "^5.0.0",
    "@types/node": "^20.0.0"
  },
  "engines": {
    "node": ">=20.0.0"
  }
}
*/
```

```bash
# ── NPM COMMANDS — Essential Reference ───────────────────────────────────
npm init -y                    # Initialize package.json (yes to all)
npm install express            # Install + add to dependencies
npm install -D typescript      # Install + add to devDependencies
npm install -g nodemon         # Install globally
npm install                    # Install all deps from package.json
npm uninstall express          # Remove package
npm update                     # Update all packages
npm outdated                   # Show outdated packages
npm audit                      # Security vulnerability check
npm audit fix                  # Auto-fix vulnerabilities
npm run start                  # Run "start" script
npm test                       # Run "test" script
npm ls                         # List installed packages
npm ls --depth=0               # List top-level packages only
npm ci                         # Clean install (for CI/CD — uses lock file)
npm pack                       # Create .tgz package
npm publish                    # Publish to npm registry
npm link                       # Link package locally for development
npx create-react-app my-app    # Run without installing (npx)
npx ts-node script.ts          # Run TypeScript directly
```

---

### Concept 2: The Global Object & Core APIs

```javascript
// ── GLOBAL OBJECTS (available everywhere, no require needed) ──────────────
console.log(__filename);       // Full path of current file (CJS only)
console.log(__dirname);        // Directory of current file (CJS only)
console.log(process.cwd());    // Current working directory (both)

// process — the running Node.js process:
console.log(process.version);          // 'v20.11.0'
console.log(process.platform);         // 'linux', 'darwin', 'win32'
console.log(process.arch);             // 'x64', 'arm64'
console.log(process.pid);              // Process ID
console.log(process.memoryUsage());    // {rss, heapTotal, heapUsed, external}
console.log(process.uptime());         // Seconds since process started
console.log(process.env.NODE_ENV);     // Environment variables
console.log(process.argv);             // ['node', 'script.js', ...args]
console.log(process.env.HOME);         // /home/username

// Exit:
process.exit(0);              // Exit with success code
process.exit(1);              // Exit with error code
process.exitCode = 1;         // Set exit code without immediate exit

// stdin/stdout:
process.stdout.write('Hello without newline');
process.stderr.write('Error message\n');

// Environment variables best practice:
const port = parseInt(process.env.PORT ?? '3000', 10);
const isDev = process.env.NODE_ENV !== 'production';

// ── TIMERS ────────────────────────────────────────────────────────────────
// Macrotask (runs after I/O events):
const timer = setTimeout(() => console.log('After 1s'), 1000);
clearTimeout(timer);          // Cancel

const interval = setInterval(() => console.log('Every 500ms'), 500);
clearInterval(interval);      // Cancel

// Immediate (runs after current event loop iteration):
setImmediate(() => console.log('After I/O events'));

// Microtask (runs before next macrotask):
Promise.resolve().then(() => console.log('Promise microtask'));
queueMicrotask(() => console.log('Microtask queue'));
process.nextTick(() => console.log('Next tick — even before Promise!'));

// Execution order:
// 1. process.nextTick queue (all)
// 2. Promise microtask queue (all)
// 3. setImmediate / setTimeout / I/O callbacks
console.log('1 - synchronous');
process.nextTick(() => console.log('3 - nextTick'));
Promise.resolve().then(() => console.log('4 - promise'));
setImmediate(() => console.log('5 - setImmediate'));
setTimeout(() => console.log('6 - setTimeout'), 0);
console.log('2 - synchronous');
// Output: 1, 2, 3, 4, 5 or 6 (setTimeout vs setImmediate depends on timing)

// ── CONSOLE ADVANCED USAGE ────────────────────────────────────────────────
console.log('Simple log');
console.error('Error — goes to stderr');
console.warn('Warning');
console.info('Info — same as log');
console.debug('Debug info');
console.dir(object, { depth: null, colors: true }); // Deep inspect
console.table([{a:1,b:2}, {a:3,b:4}]);              // Table format
console.group('Group Label');
console.log('Nested');
console.groupEnd();
console.time('myTimer');
// ... some code ...
console.timeEnd('myTimer');   // myTimer: 1.234ms
console.count('hit');         // hit: 1
console.count('hit');         // hit: 2
console.countReset('hit');
console.trace('Stack trace here');
console.assert(1 === 2, 'This will print: 1 !== 2');
```

---

### Concept 3: File System Operations

```javascript
// ── fs MODULE — Three API Styles ──────────────────────────────────────────
import { readFile, writeFile, appendFile, mkdir, readdir,
         stat, rename, unlink, copyFile, watch } from 'fs/promises';
import { createReadStream, createWriteStream, existsSync } from 'fs';
import fs from 'fs';  // Sync API + callback API

// ── ASYNC/AWAIT (Prefer this!) ────────────────────────────────────────────
async function fileOperations() {
    // Read file:
    const content = await readFile('file.txt', 'utf8');
    const buffer  = await readFile('image.png');  // No encoding = Buffer

    // Write file (overwrites!):
    await writeFile('output.txt', 'Hello, World!\n', 'utf8');
    await writeFile('data.json', JSON.stringify({ key: 'value' }, null, 2));

    // Append:
    await appendFile('log.txt', `${new Date().toISOString()} - Event\n`);

    // Directory operations:
    await mkdir('new-dir', { recursive: true });   // { recursive } = don't error if exists
    const entries = await readdir('.');             // Array of names
    const detailed = await readdir('.', { withFileTypes: true }); // DirEntry objects

    // Filter directories:
    const dirs = detailed.filter(e => e.isDirectory()).map(e => e.name);
    const files = detailed.filter(e => e.isFile()).map(e => e.name);

    // File info:
    const info = await stat('file.txt');
    console.log(info.size);           // Bytes
    console.log(info.mtime);          // Modified date
    console.log(info.isDirectory());  // false
    console.log(info.isFile());       // true

    // Move/rename:
    await rename('old.txt', 'new.txt');

    // Delete:
    await unlink('file.txt');    // Delete file
    // await rm('dir', { recursive: true, force: true }); // Delete directory

    // Copy:
    await copyFile('source.txt', 'destination.txt');

    // Check existence (no fs.promises.exists):
    if (existsSync('file.txt')) {  // Sync only — prefer try/catch
        console.log('Exists!');
    }
    // Async alternative:
    try {
        await stat('file.txt');
        console.log('Exists!');
    } catch (err) {
        if (err.code === 'ENOENT') console.log('Does not exist');
        else throw err;
    }
}

// ── STREAMS — for large files (don't load into memory!) ──────────────────
import { pipeline } from 'stream/promises';
import { createGzip } from 'zlib';

// Read large file line by line:
import readline from 'readline';

async function processLargeFile(filePath) {
    const fileStream = createReadStream(filePath, { encoding: 'utf8' });
    const rl = readline.createInterface({ input: fileStream, crlfDelay: Infinity });

    let lineCount = 0;
    for await (const line of rl) {
        lineCount++;
        if (line.includes('ERROR')) {
            console.log(`Line ${lineCount}: ${line}`);
        }
    }
    console.log(`Processed ${lineCount} lines`);
}

// Compress a file efficiently:
async function compressFile(input, output) {
    await pipeline(
        createReadStream(input),
        createGzip(),
        createWriteStream(output)
    );
    console.log('Compressed successfully!');
}

// ── WATCH FILE CHANGES ────────────────────────────────────────────────────
const watcher = watch('.', { recursive: true });
for await (const { eventType, filename } of watcher) {
    console.log(`${eventType}: ${filename}`);
}

// ── PATH MODULE — Cross-platform path handling ────────────────────────────
import path from 'path';
import { fileURLToPath } from 'url';

// ESM __dirname equivalent:
const __filename2 = fileURLToPath(import.meta.url);
const __dirname2 = path.dirname(__filename2);

path.join('/foo', 'bar', 'baz.txt');   // '/foo/bar/baz.txt'
path.join(__dirname2, 'data', 'config.json');
path.resolve('foo', 'bar');            // Absolute path from cwd
path.dirname('/foo/bar/baz.txt');      // '/foo/bar'
path.basename('/foo/bar/baz.txt');     // 'baz.txt'
path.basename('/foo/bar/baz.txt', '.txt'); // 'baz'
path.extname('/foo/bar/baz.txt');      // '.txt'
path.parse('/foo/bar/baz.txt');        // {root,dir,base,ext,name}
path.format({dir:'/foo', name:'baz', ext:'.txt'}); // '/foo/baz.txt'
path.isAbsolute('/foo/bar');           // true
path.relative('/foo/bar', '/foo/baz'); // '../baz'
path.sep;                              // '/' on Linux, '\' on Windows
path.delimiter;                        // ':' on Linux, ';' on Windows
```

---

### Concept 4: HTTP & Building a Server from Scratch

```javascript
// ── NATIVE HTTP MODULE ────────────────────────────────────────────────────
import http from 'http';
import { URL } from 'url';

const server = http.createServer(async (req, res) => {
    // Parse URL:
    const url = new URL(req.url, `http://${req.headers.host}`);
    const pathname = url.pathname;
    const searchParams = url.searchParams;

    console.log(`${req.method} ${pathname}`);
    console.log('Headers:', req.headers);
    console.log('Query:', Object.fromEntries(searchParams));

    // Read request body:
    let body = '';
    for await (const chunk of req) {
        body += chunk;
        if (body.length > 1_000_000) {  // 1MB limit
            res.statusCode = 413;
            res.end('Request too large');
            return;
        }
    }

    // Route handling:
    if (req.method === 'GET' && pathname === '/') {
        res.writeHead(200, {
            'Content-Type': 'text/html; charset=utf-8',
            'Cache-Control': 'no-store',
        });
        res.end('<h1>Hello from Node.js!</h1>');

    } else if (req.method === 'GET' && pathname === '/health') {
        res.writeHead(200, { 'Content-Type': 'application/json' });
        res.end(JSON.stringify({ status: 'ok', uptime: process.uptime() }));

    } else if (req.method === 'POST' && pathname === '/api/users') {
        try {
            const data = JSON.parse(body);
            res.writeHead(201, { 'Content-Type': 'application/json' });
            res.end(JSON.stringify({ id: 1, ...data }));
        } catch {
            res.writeHead(400, { 'Content-Type': 'application/json' });
            res.end(JSON.stringify({ error: 'Invalid JSON' }));
        }

    } else {
        res.writeHead(404, { 'Content-Type': 'application/json' });
        res.end(JSON.stringify({ error: 'Not Found' }));
    }
});

server.listen(3000, () => {
    console.log('Server running on http://localhost:3000');
});

// ── HTTPS SERVER ──────────────────────────────────────────────────────────
import https from 'https';
import { readFileSync } from 'fs';

const httpsServer = https.createServer({
    key: readFileSync('server.key'),
    cert: readFileSync('server.cert'),
}, (req, res) => { /* same handler */ });

httpsServer.listen(443);

// ── HTTP CLIENT ───────────────────────────────────────────────────────────
// Native fetch (Node.js 18+):
const response = await fetch('https://api.example.com/users');
const data = await response.json();
console.log(data);

// With options:
const createResponse = await fetch('https://api.example.com/users', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json', 'Authorization': 'Bearer token' },
    body: JSON.stringify({ name: 'Aryan' }),
    signal: AbortSignal.timeout(5000),  // 5 second timeout
});

if (!createResponse.ok) {
    throw new Error(`HTTP ${createResponse.status}: ${createResponse.statusText}`);
}

const created = await createResponse.json();
```

---

### Concept 5: Events & The EventEmitter Pattern

```javascript
// ── EventEmitter — the foundation of Node.js ─────────────────────────────
import { EventEmitter } from 'events';

// Basic usage:
const emitter = new EventEmitter();

emitter.on('data', (payload) => {
    console.log('Received:', payload);
});

emitter.once('connect', () => {
    console.log('Connected! (only fires once)');
});

emitter.on('error', (err) => {
    console.error('Error:', err.message);
    // MUST handle 'error' events! Unhandled errors crash the process.
});

emitter.emit('data', { message: 'Hello', timestamp: Date.now() });
emitter.emit('connect');
emitter.emit('connect');  // Ignored — once already fired

// ── CUSTOM EventEmitter CLASS ─────────────────────────────────────────────
class DataPipeline extends EventEmitter {
    #queue = [];
    #processing = false;

    enqueue(item) {
        this.#queue.push(item);
        this.emit('queued', item);
        this.#process();
    }

    async #process() {
        if (this.#processing || this.#queue.length === 0) return;
        this.#processing = true;

        while (this.#queue.length > 0) {
            const item = this.#queue.shift();
            try {
                this.emit('processing', item);
                const result = await this.#transform(item);
                this.emit('processed', result);
            } catch (err) {
                this.emit('error', err);
            }
        }

        this.#processing = false;
        this.emit('drain');
    }

    async #transform(item) {
        await new Promise(r => setTimeout(r, 100)); // Simulate async work
        return { ...item, processed: true, at: new Date() };
    }
}

const pipeline = new DataPipeline();
pipeline.on('processed', (result) => console.log('Done:', result));
pipeline.on('error', (err) => console.error('Pipeline error:', err));
pipeline.on('drain', () => console.log('Queue empty'));

pipeline.enqueue({ id: 1, data: 'hello' });
pipeline.enqueue({ id: 2, data: 'world' });

// ── EventEmitter INTERNALS ────────────────────────────────────────────────
emitter.listeners('data');               // Array of listener functions
emitter.listenerCount('data');           // Number of listeners
emitter.rawListeners('data');            // Including once wrappers
emitter.removeListener('data', handler); // Remove specific listener
emitter.removeAllListeners('data');      // Remove all for event
emitter.removeAllListeners();            // Remove ALL listeners
emitter.setMaxListeners(20);            // Default is 10 (warns if exceeded)
EventEmitter.setMaxListeners(0);         // 0 = unlimited (global)

// emitter.off = emitter.removeListener (alias)
emitter.off('data', handler);

// prependListener — add to FRONT of listener array:
emitter.prependListener('data', firstHandler);
emitter.prependOnceListener('data', firstOnceHandler);

// ── EVENTS module utilities ────────────────────────────────────────────────
import { once, on } from 'events';

// Wait for a single event (async):
const [payload] = await once(emitter, 'data');
console.log('Got:', payload);

// AsyncIterator over events:
async function* streamEvents(emitter, event) {
    for await (const [data] of on(emitter, event)) {
        yield data;
    }
}

for await (const event of streamEvents(emitter, 'data')) {
    console.log(event);
}
```

---

🧪 **Mini Task 1:**
> Build a `Logger` class that extends `EventEmitter`. It should have `info(msg)`, `warn(msg)`, and `error(msg)` methods, each of which emits a typed log event with `{ level, message, timestamp }`. Add a `FileLogHandler` that listens to all events and appends to a log file.
> ✅ *Expected: `logger.error('DB failed')` → writes `[2025-03-29 ERROR] DB failed\n` to a file.*

🧪 **Mini Task 2:**
> Create an async function `downloadAll(urls: string[])` that fetches all URLs concurrently (using `Promise.all`), retries each up to 3 times on failure (with exponential backoff), and returns an array of `{ url, status, bytes }` objects.

---

## ⚙️ 4. Complete System Breakdown

> 🎯 *Goal: Understand ALL of Node.js's machinery — nothing hidden.*

---

### Part 1: The Event Loop — The Heart of Node.js

```javascript
// ── THE EVENT LOOP PHASES ─────────────────────────────────────────────────
/*
   The Node.js Event Loop executes in phases:

   ┌─────────────────────────────────────────────────────────┐
   │                      EVENT LOOP                          │
   │                                                          │
   │   ┌──────────┐  ┌──────────┐  ┌──────────┐            │
   │   │  timers   │→ │ pending  │→ │  idle,   │            │
   │   │setTimeout │  │callbacks │  │ prepare  │            │
   │   │setInterval│  │          │  │          │            │
   │   └──────────┘  └──────────┘  └──────────┘            │
   │         ↓                                               │
   │   ┌──────────┐  ┌──────────┐  ┌──────────┐            │
   │   │   poll   │→ │  check   │→ │  close   │            │
   │   │ (I/O    │  │setImmed- │  │callbacks │            │
   │   │ events) │  │iate      │  │          │            │
   │   └──────────┘  └──────────┘  └──────────┘            │
   │                                                          │
   │   Between each phase:                                    │
   │   1. All process.nextTick callbacks                      │
   │   2. All Promise microtasks                              │
   └─────────────────────────────────────────────────────────┘

   Phases in order:
   1. timers       — setTimeout and setInterval callbacks
   2. pending      — I/O callbacks deferred to next loop
   3. idle/prepare — Internal use only
   4. poll         — Retrieve new I/O events; execute callbacks
   5. check        — setImmediate callbacks
   6. close        — Close event callbacks (socket.on('close'))

   BETWEEN EVERY PHASE:
   - process.nextTick queue drains completely
   - Promise microtask queue drains completely
*/

// Demonstrating the order:
setImmediate(() => console.log('8 - setImmediate'));
setTimeout(() => console.log('7 - setTimeout 0'), 0);

Promise.resolve()
    .then(() => console.log('3 - promise 1'))
    .then(() => console.log('4 - promise 2 (chained)'));

process.nextTick(() => {
    console.log('2 - nextTick 1');
    process.nextTick(() => console.log('5 - nextTick inside nextTick!'));
});

process.nextTick(() => console.log('6 - nextTick 2'));

console.log('1 - synchronous start');

// Output:
// 1 - synchronous start
// 2 - nextTick 1
// 6 - nextTick 2
// 5 - nextTick inside nextTick!  (nextTick is processed completely before promises)
// 3 - promise 1
// 4 - promise 2
// 7 - setTimeout 0       (or 8 first — race condition between setTimeout 0 and setImmediate)
// 8 - setImmediate

// ── BLOCKING THE EVENT LOOP ───────────────────────────────────────────────
// THIS IS THE #1 MISTAKE! Never do CPU-heavy work synchronously:

// ❌ BLOCKS the event loop — all requests wait while this runs:
app.get('/bad', (req, res) => {
    const result = heavyComputation(); // Synchronous CPU work!
    res.json(result);
});

// ✅ Offload to worker thread:
import { Worker, isMainThread, parentPort, workerData } from 'worker_threads';

app.get('/good', async (req, res) => {
    const result = await runInWorker('./compute.js', { data: req.query });
    res.json(result);
});

function runInWorker(workerFile, data) {
    return new Promise((resolve, reject) => {
        const worker = new Worker(workerFile, { workerData: data });
        worker.once('message', resolve);
        worker.once('error', reject);
        worker.once('exit', code => {
            if (code !== 0) reject(new Error(`Worker exited with code ${code}`));
        });
    });
}

// ── LIBUV THREAD POOL ─────────────────────────────────────────────────────
// libuv provides 4 threads by default for:
// - File system operations (fs.*)
// - DNS lookups (dns.lookup)
// - Crypto operations (crypto.pbkdf2, scrypt, etc.)
// - Zlib operations

// Increase thread pool for CPU-bound work:
process.env.UV_THREADPOOL_SIZE = 16; // Max: 128 (set BEFORE any async work!)
// Or at startup: UV_THREADPOOL_SIZE=16 node server.js
```

---

### Part 2: Streams — The Node.js Superpower

```javascript
import { Readable, Writable, Transform, Duplex, pipeline } from 'stream';
import { pipeline as pipelineAsync } from 'stream/promises';

// ── THE FOUR STREAM TYPES ─────────────────────────────────────────────────
// Readable  — data flows OUT (reading)
// Writable  — data flows IN (writing)
// Duplex    — both Readable and Writable
// Transform — data flows through with transformation

// ── READABLE STREAMS ──────────────────────────────────────────────────────
// Reading in flowing mode (push):
const readable = createReadStream('large-file.txt', {
    highWaterMark: 64 * 1024,  // 64KB chunks (default 16KB)
    encoding: 'utf8',
});

readable.on('data', chunk => process.stdout.write(chunk));
readable.on('end', () => console.log('Done!'));
readable.on('error', err => console.error(err));

// Reading in paused mode (pull) — PREFERRED:
readable.pause();
readable.on('readable', () => {
    let chunk;
    while (null !== (chunk = readable.read())) {
        process.stdout.write(chunk);
    }
});

// Modern: async iteration (CLEANEST way):
async function readStream(filePath) {
    const stream = createReadStream(filePath, { encoding: 'utf8' });
    const chunks = [];
    for await (const chunk of stream) {
        chunks.push(chunk);
    }
    return chunks.join('');
}

// ── CUSTOM READABLE STREAM ────────────────────────────────────────────────
class NumberStream extends Readable {
    constructor(max) {
        super({ objectMode: true });  // objectMode: emit objects, not buffers
        this.current = 0;
        this.max = max;
    }

    _read() {
        if (this.current <= this.max) {
            this.push(this.current++);
        } else {
            this.push(null);  // null signals end of stream
        }
    }
}

// ── TRANSFORM STREAM ──────────────────────────────────────────────────────
class CSVParser extends Transform {
    constructor() {
        super({ readableObjectMode: true }); // Output objects
        this.headers = null;
        this.buffer = '';
    }

    _transform(chunk, encoding, callback) {
        this.buffer += chunk.toString();
        const lines = this.buffer.split('\n');
        this.buffer = lines.pop();  // Keep incomplete line for next chunk

        for (const line of lines) {
            if (!line.trim()) continue;
            const values = line.split(',').map(v => v.trim());

            if (!this.headers) {
                this.headers = values;
                continue;
            }

            const obj = Object.fromEntries(
                this.headers.map((h, i) => [h, values[i] ?? ''])
            );
            this.push(obj);  // Push object to readable side
        }
        callback();
    }

    _flush(callback) {
        if (this.buffer.trim()) {
            const values = this.buffer.split(',').map(v => v.trim());
            if (this.headers) {
                const obj = Object.fromEntries(
                    this.headers.map((h, i) => [h, values[i] ?? ''])
                );
                this.push(obj);
            }
        }
        callback();
    }
}

// ── PIPELINE — the right way to connect streams ───────────────────────────
// pipeline handles backpressure and cleanup automatically!

// ❌ WRONG — .pipe() doesn't handle errors properly:
readable.pipe(transform).pipe(writable);  // Memory leak if error!

// ✅ CORRECT — use pipeline:
await pipelineAsync(
    createReadStream('data.csv'),
    new CSVParser(),
    new Writable({
        objectMode: true,
        write(obj, encoding, callback) {
            console.log(obj);
            callback();
        }
    })
);

// Real pipeline: compress a file:
import { createGzip, createGunzip } from 'zlib';
import { createReadStream, createWriteStream } from 'fs';

// Compress:
await pipelineAsync(
    createReadStream('input.txt'),
    createGzip({ level: 9 }),         // Max compression
    createWriteStream('output.txt.gz')
);

// Decompress:
await pipelineAsync(
    createReadStream('output.txt.gz'),
    createGunzip(),
    createWriteStream('restored.txt')
);

// ── BACKPRESSURE — critical for memory management ─────────────────────────
// Backpressure occurs when you write faster than the consumer can consume.
// pipeline handles this automatically, but understand the mechanism:

const writable = new Writable({
    write(chunk, encoding, callback) {
        // Call callback when ready for next chunk:
        setTimeout(callback, 100);  // Slow consumer
    }
});

// The write() return value:
const canContinue = writable.write(chunk);
if (!canContinue) {
    // Buffer is full! Wait for drain before writing more:
    await new Promise(resolve => writable.once('drain', resolve));
}
```

---

### Part 3: Worker Threads & Child Processes

```javascript
// ── WORKER THREADS — true parallelism in Node.js ─────────────────────────
// Use when: CPU-intensive work that would block the event loop
// Examples: image processing, encryption, ML inference, data compression

import { Worker, isMainThread, parentPort, workerData,
         MessageChannel, receiveMessageOnPort } from 'worker_threads';

// worker.js
if (!isMainThread) {
    // This code runs in the worker thread:
    const { numbers, operation } = workerData;

    let result;
    switch (operation) {
        case 'sum': result = numbers.reduce((a, b) => a + b, 0); break;
        case 'sort': result = [...numbers].sort((a, b) => a - b); break;
        case 'primes': result = numbers.filter(isPrime); break;
    }

    parentPort.postMessage(result);
}

function isPrime(n) {
    if (n < 2) return false;
    for (let i = 2; i <= Math.sqrt(n); i++)
        if (n % i === 0) return false;
    return true;
}

// main.js — using workers:
class WorkerPool {
    #workers = [];
    #queue = [];
    #size;

    constructor(workerFile, size = navigator?.hardwareConcurrency ?? 4) {
        this.#size = size;
        for (let i = 0; i < size; i++) {
            this.#createWorker(workerFile);
        }
    }

    #createWorker(workerFile) {
        const worker = new Worker(workerFile);
        worker.on('message', (result) => {
            const { resolve } = worker.currentTask;
            worker.currentTask = null;
            resolve(result);
            this.#processQueue(worker);
        });
        worker.on('error', (err) => {
            const { reject } = worker.currentTask;
            worker.currentTask = null;
            reject(err);
        });
        worker.idle = true;
        this.#workers.push(worker);
    }

    #processQueue(worker) {
        if (this.#queue.length > 0) {
            const { data, resolve, reject } = this.#queue.shift();
            worker.currentTask = { resolve, reject };
            worker.idle = false;
            worker.postMessage(data);
        } else {
            worker.idle = true;
        }
    }

    run(data) {
        return new Promise((resolve, reject) => {
            const idleWorker = this.#workers.find(w => w.idle);
            if (idleWorker) {
                idleWorker.currentTask = { resolve, reject };
                idleWorker.idle = false;
                idleWorker.postMessage(data);
            } else {
                this.#queue.push({ data, resolve, reject });
            }
        });
    }

    async terminate() {
        await Promise.all(this.#workers.map(w => w.terminate()));
    }
}

// SharedArrayBuffer — zero-copy data sharing between threads:
const sharedBuffer = new SharedArrayBuffer(4 * Int32Array.BYTES_PER_ELEMENT);
const sharedArray = new Int32Array(sharedBuffer);

// Worker 1 and Worker 2 can BOTH access this memory:
Atomics.store(sharedArray, 0, 42);
const value = Atomics.load(sharedArray, 0);
Atomics.add(sharedArray, 0, 1);     // Atomic increment — thread-safe!
Atomics.wait(sharedArray, 0, 42);   // Wait until index 0 ≠ 42
Atomics.notify(sharedArray, 0, 1);  // Wake one waiting thread

// ── CHILD PROCESSES ───────────────────────────────────────────────────────
import { spawn, exec, execFile, fork } from 'child_process';
import { promisify } from 'util';

const execAsync = promisify(exec);

// exec — run shell command, buffer output:
const { stdout, stderr } = await execAsync('git log --oneline -5');
console.log(stdout);

// spawn — for streaming output or long-running processes:
const child = spawn('find', ['.', '-name', '*.js', '-not', '-path', '*/node_modules/*']);

child.stdout.on('data', data => process.stdout.write(data));
child.stderr.on('data', data => process.stderr.write(data));
const exitCode = await new Promise(resolve => child.on('close', resolve));

// fork — spawn another Node.js process with IPC:
const childProcess = fork('./worker.js', { env: { ...process.env, ROLE: 'worker' } });
childProcess.send({ task: 'compute', data: [1, 2, 3] });
childProcess.on('message', result => console.log('Result:', result));
childProcess.on('exit', code => console.log(`Worker exited: ${code}`));
```

---

### Part 4: Networking & Advanced HTTP

```javascript
// ── TCP SERVER ────────────────────────────────────────────────────────────
import net from 'net';

const tcpServer = net.createServer((socket) => {
    console.log(`Client connected: ${socket.remoteAddress}:${socket.remotePort}`);

    socket.setEncoding('utf8');
    socket.setTimeout(30_000);  // 30 second idle timeout

    socket.on('data', (data) => {
        console.log('Received:', data);
        socket.write(`Echo: ${data}`);  // Echo back
    });

    socket.on('timeout', () => {
        socket.end('Connection timed out\n');
    });

    socket.on('error', (err) => {
        console.error('Socket error:', err.message);
    });

    socket.on('close', () => {
        console.log('Client disconnected');
    });
});

tcpServer.listen(8080, () => console.log('TCP server on port 8080'));

// ── UDP SOCKET ────────────────────────────────────────────────────────────
import dgram from 'dgram';

const udpServer = dgram.createSocket('udp4');
udpServer.on('message', (msg, rinfo) => {
    console.log(`UDP: ${msg} from ${rinfo.address}:${rinfo.port}`);
    udpServer.send(`Got: ${msg}`, rinfo.port, rinfo.address);
});
udpServer.bind(41234);

// ── HTTPS with Let's Encrypt (production setup) ───────────────────────────
// In production, use nginx/caddy as reverse proxy for TLS termination
// Or use `greenlock` / `acme-client` for programmatic cert management

// ── WebSocket SERVER (native) ─────────────────────────────────────────────
// For WebSockets, use the 'ws' package:
// npm install ws
import { WebSocketServer } from 'ws';

const wss = new WebSocketServer({ port: 8080 });
const clients = new Set();

wss.on('connection', (ws, req) => {
    clients.add(ws);
    ws.isAlive = true;

    ws.on('pong', () => { ws.isAlive = true; }); // Heartbeat response

    ws.on('message', (data, isBinary) => {
        const message = isBinary ? data : data.toString();
        console.log('Message:', message);

        // Broadcast to all clients:
        for (const client of clients) {
            if (client !== ws && client.readyState === 1) {  // 1 = OPEN
                client.send(message);
            }
        }
    });

    ws.on('close', () => clients.delete(ws));
    ws.on('error', (err) => { console.error(err); clients.delete(ws); });
});

// Heartbeat — detect dead connections:
const heartbeat = setInterval(() => {
    for (const ws of wss.clients) {
        if (!ws.isAlive) { ws.terminate(); continue; }
        ws.isAlive = false;
        ws.ping();
    }
}, 30_000);

wss.on('close', () => clearInterval(heartbeat));
```

---

### Part 5: Databases & Caching

```javascript
// ── SQLITE (native, no external service) ─────────────────────────────────
// npm install better-sqlite3
import Database from 'better-sqlite3';

const db = new Database('myapp.db', { verbose: console.log });

// Create tables:
db.exec(`
    CREATE TABLE IF NOT EXISTS users (
        id      INTEGER PRIMARY KEY AUTOINCREMENT,
        name    TEXT NOT NULL,
        email   TEXT UNIQUE NOT NULL,
        created DATETIME DEFAULT CURRENT_TIMESTAMP
    );
    CREATE INDEX IF NOT EXISTS idx_users_email ON users(email);
`);

// Prepared statements (ALWAYS use for user input — prevents SQL injection):
const insertUser = db.prepare('INSERT INTO users (name, email) VALUES (?, ?)');
const getUserById = db.prepare('SELECT * FROM users WHERE id = ?');
const getAllUsers = db.prepare('SELECT * FROM users ORDER BY created DESC');

// Transactions (atomic):
const createUserWithProfile = db.transaction((user, profile) => {
    const result = insertUser.run(user.name, user.email);
    const userId = result.lastInsertRowid;
    // ... insert profile with userId
    return userId;
});

const newUserId = createUserWithProfile(
    { name: 'Aryan', email: 'aryan@example.com' },
    { bio: 'Developer', location: 'Kolkata' }
);

const user = getUserById.get(newUserId);  // get() = first row
const users = getAllUsers.all();           // all() = all rows

// ── REDIS CLIENT ──────────────────────────────────────────────────────────
// npm install ioredis
import Redis from 'ioredis';

const redis = new Redis({
    host: process.env.REDIS_HOST ?? 'localhost',
    port: 6379,
    password: process.env.REDIS_PASSWORD,
    retryStrategy: (times) => Math.min(times * 50, 2000),  // Reconnect backoff
    maxRetriesPerRequest: 3,
    enableReadyCheck: true,
    lazyConnect: false,
});

redis.on('error', err => console.error('Redis error:', err));
redis.on('connect', () => console.log('Redis connected'));

// Basic operations:
await redis.set('key', 'value');
await redis.set('key', 'value', 'EX', 3600);    // Expire in 1 hour
const val = await redis.get('key');              // 'value' or null

// Hash (object storage):
await redis.hset('user:1', { name: 'Aryan', email: 'a@example.com', age: '17' });
const user2 = await redis.hgetall('user:1');     // { name, email, age }
await redis.hget('user:1', 'name');              // 'Aryan'
await redis.hdel('user:1', 'age');

// List:
await redis.lpush('queue', 'task1', 'task2');
await redis.rpush('queue', 'task3');
await redis.blpop('queue', 0);                  // Blocking pop (0 = wait forever)

// Set:
await redis.sadd('tags', 'rust', 'nodejs', 'python');
await redis.smembers('tags');                    // All members
await redis.sismember('tags', 'rust');           // true/false

// Sorted Set (for leaderboards, rate limiting):
await redis.zadd('leaderboard', 1000, 'alice');
await redis.zadd('leaderboard', 950, 'bob');
await redis.zrange('leaderboard', 0, -1, 'WITHSCORES'); // All with scores
await redis.zrank('leaderboard', 'bob');         // Rank (0-indexed)

// Pipeline (batch commands — one round trip!):
const pipeline = redis.pipeline();
pipeline.set('a', 1);
pipeline.set('b', 2);
pipeline.incr('a');
const results = await pipeline.exec();  // [[null, 'OK'], [null, 'OK'], [null, 2]]

// Lua scripts (atomic operations):
const increment = redis.defineCommand('increment', {
    numberOfKeys: 1,
    lua: `
        local current = redis.call('get', KEYS[1])
        if current == false then current = 0 end
        local new = tonumber(current) + tonumber(ARGV[1])
        redis.call('set', KEYS[1], new)
        return new
    `
});
const newValue = await increment('counter', 5);

// Rate limiting with Redis:
async function rateLimit(key, limit, windowSeconds) {
    const now = Date.now();
    const window = now - (windowSeconds * 1000);

    const pipeline = redis.pipeline();
    pipeline.zremrangebyscore(key, 0, window);     // Remove old entries
    pipeline.zadd(key, now, `${now}-${Math.random()}`); // Add current
    pipeline.zcard(key);                            // Count in window
    pipeline.expire(key, windowSeconds);            // Set expiry
    const results = await pipeline.exec();

    const count = results[2][1];
    return { allowed: count <= limit, count, limit };
}
```

---

### 📊 Full Node.js System Overview Table

| Component          | What It Does                               | Key Insight                                           |
|--------------------|---------------------------------------------|-------------------------------------------------------|
| V8 Engine          | Executes JavaScript                        | JIT compilation — JS approaches C++ speed            |
| libuv              | Event loop + thread pool + async I/O       | Handles ALL OS-level async operations                 |
| Event Loop         | Orchestrates all async callbacks           | Single-threaded but NOT slow — never blocks           |
| Thread Pool        | 4 threads for blocking operations          | `UV_THREADPOOL_SIZE` to increase                     |
| EventEmitter       | Pub/sub event system                       | Foundation of all streams, servers, process          |
| Streams            | Chunk-based data processing                | Process gigabytes with megabytes of RAM              |
| Worker Threads     | True parallelism for CPU-bound work        | Shared memory via SharedArrayBuffer                  |
| Child Processes    | Spawn separate OS processes                | Full isolation, IPC via messaging                    |
| Cluster Module     | Multi-process with shared port             | Load balance across CPU cores                        |
| Native Modules     | C/C++ code loaded as .node files           | FFI for performance-critical operations              |

---

## 🔄 5. Real-World Workflow

---

### 🟢 Beginner Workflow: Express REST API

```javascript
// src/app.js — Production Express application
import express from 'express';
import cors from 'cors';
import helmet from 'helmet';
import morgan from 'morgan';
import rateLimit from 'express-rate-limit';

// ── MIDDLEWARE FACTORY ────────────────────────────────────────────────────
function createApp() {
    const app = express();

    // Security headers:
    app.use(helmet());

    // CORS:
    app.use(cors({
        origin: process.env.ALLOWED_ORIGINS?.split(',') ?? ['http://localhost:3000'],
        credentials: true,
        methods: ['GET', 'POST', 'PUT', 'PATCH', 'DELETE'],
    }));

    // Request logging:
    app.use(morgan('combined'));

    // Body parsing:
    app.use(express.json({ limit: '10mb' }));
    app.use(express.urlencoded({ extended: true }));

    // Rate limiting:
    app.use('/api/', rateLimit({
        windowMs: 15 * 60 * 1000,  // 15 minutes
        max: 100,                    // 100 requests per window
        standardHeaders: true,
        legacyHeaders: false,
        message: { error: 'Too many requests, please try again later' },
    }));

    // Health check:
    app.get('/health', (req, res) => {
        res.json({
            status: 'ok',
            uptime: process.uptime(),
            memory: process.memoryUsage(),
            timestamp: new Date().toISOString(),
        });
    });

    // Routes:
    app.use('/api/users', userRouter);
    app.use('/api/posts', postRouter);

    // 404 handler:
    app.use((req, res) => {
        res.status(404).json({ error: `Route ${req.method} ${req.path} not found` });
    });

    // Error handler (must have 4 params!):
    app.use((err, req, res, next) => {
        console.error(err);

        if (err.name === 'ValidationError') {
            return res.status(400).json({ error: err.message, details: err.details });
        }
        if (err.code === 'P2025') {  // Prisma not found
            return res.status(404).json({ error: 'Resource not found' });
        }

        res.status(err.status ?? 500).json({
            error: process.env.NODE_ENV === 'production'
                ? 'Internal server error'
                : err.message,
        });
    });

    return app;
}

// src/routes/users.js:
import { Router } from 'express';
const router = Router();

// Middleware for this router:
router.use(authenticate);  // All user routes require auth

// Async wrapper to catch errors:
const asyncHandler = fn => (req, res, next) =>
    Promise.resolve(fn(req, res, next)).catch(next);

router.get('/', asyncHandler(async (req, res) => {
    const { page = 1, limit = 20, search } = req.query;
    const users = await userService.findAll({
        page: parseInt(page),
        limit: Math.min(parseInt(limit), 100),
        search,
    });
    res.json(users);
}));

router.get('/:id', asyncHandler(async (req, res) => {
    const user = await userService.findById(req.params.id);
    if (!user) return res.status(404).json({ error: 'User not found' });
    res.json(user);
}));

router.post('/', validate(createUserSchema), asyncHandler(async (req, res) => {
    const user = await userService.create(req.body);
    res.status(201).json(user);
}));

router.patch('/:id', asyncHandler(async (req, res) => {
    const user = await userService.update(req.params.id, req.body);
    res.json(user);
}));

router.delete('/:id', asyncHandler(async (req, res) => {
    await userService.delete(req.params.id);
    res.status(204).end();
}));

export default router;

// src/server.js — Graceful shutdown:
const app = createApp();
const server = app.listen(process.env.PORT ?? 3000, () => {
    console.log(`Server running on port ${server.address().port}`);
});

// Graceful shutdown:
const shutdown = async (signal) => {
    console.log(`\nReceived ${signal}. Starting graceful shutdown...`);
    server.close(async () => {
        await db.end();           // Close DB connections
        await redis.quit();       // Close Redis
        console.log('Server shutdown complete');
        process.exit(0);
    });

    // Force kill after 30 seconds:
    setTimeout(() => {
        console.error('Forced shutdown after timeout');
        process.exit(1);
    }, 30_000).unref();
};

process.on('SIGTERM', () => shutdown('SIGTERM'));
process.on('SIGINT',  () => shutdown('SIGINT'));
process.on('uncaughtException',  err => { console.error('Uncaught:', err); shutdown('uncaughtException'); });
process.on('unhandledRejection', (reason) => { console.error('Unhandled:', reason); shutdown('unhandledRejection'); });
```

---

### 🔵 Professional Workflow: Fastify with Plugins

```javascript
// Fastify is 2-3× faster than Express with better TypeScript support
// npm install fastify @fastify/cors @fastify/helmet @fastify/rate-limit

import Fastify from 'fastify';
import cors from '@fastify/cors';
import helmet from '@fastify/helmet';
import rateLimit from '@fastify/rate-limit';

const fastify = Fastify({
    logger: {
        level: process.env.LOG_LEVEL ?? 'info',
        transport: process.env.NODE_ENV !== 'production'
            ? { target: 'pino-pretty' }
            : undefined,
    },
    trustProxy: true,
    requestTimeout: 30_000,
});

// Register plugins:
await fastify.register(helmet);
await fastify.register(cors, { origin: process.env.ALLOWED_ORIGINS?.split(',') });
await fastify.register(rateLimit, { max: 100, timeWindow: '15 minutes' });

// Schema validation (faster than Joi, compiled to native code):
const createUserSchema = {
    body: {
        type: 'object',
        required: ['username', 'email'],
        properties: {
            username: { type: 'string', minLength: 3, maxLength: 50 },
            email: { type: 'string', format: 'email' },
            age: { type: 'integer', minimum: 0, maximum: 150 },
        },
        additionalProperties: false,
    },
    response: {
        201: {
            type: 'object',
            properties: {
                id: { type: 'integer' },
                username: { type: 'string' },
                email: { type: 'string' },
            },
        },
    },
};

fastify.post('/users', { schema: createUserSchema }, async (request, reply) => {
    const user = await userService.create(request.body);
    reply.code(201).send(user);
});

// Plugin system — encapsulated routes:
fastify.register(async (instance, opts) => {
    instance.addHook('preHandler', authenticate);
    instance.get('/protected', async (req, reply) => reply.send({ user: req.user }));
}, { prefix: '/api' });

await fastify.listen({ port: 3000, host: '0.0.0.0' });
```

---

## 🧪 6. Hands-on Practice Projects

---

### 🟢 Beginner Project: File Watcher & Auto-Processor

```javascript
// file-watcher.js — Watch a directory and process new files automatically
import { watch, readdir, readFile, writeFile, mkdir } from 'fs/promises';
import { join, extname, basename } from 'path';
import { EventEmitter } from 'events';

class FileProcessor extends EventEmitter {
    #watching = false;
    #processors = new Map();
    #processed = new Set();

    constructor(inputDir, outputDir) {
        super();
        this.inputDir = inputDir;
        this.outputDir = outputDir;
    }

    addProcessor(extension, processor) {
        this.#processors.set(extension.toLowerCase(), processor);
        return this;
    }

    async start() {
        await mkdir(this.outputDir, { recursive: true });
        this.#watching = true;

        // Process existing files:
        const existing = await readdir(this.inputDir);
        await Promise.all(existing.map(f => this.#processFile(f)));

        // Watch for new files:
        this.emit('watching', this.inputDir);
        const watcher = watch(this.inputDir);

        for await (const { eventType, filename } of watcher) {
            if (!this.#watching) break;
            if (eventType === 'rename' && filename) {
                await this.#processFile(filename);
            }
        }
    }

    async #processFile(filename) {
        if (this.#processed.has(filename)) return;
        const ext = extname(filename).toLowerCase();
        const processor = this.#processors.get(ext);
        if (!processor) return;

        const inputPath = join(this.inputDir, filename);
        const outputName = basename(filename, ext) + '.processed' + ext;
        const outputPath = join(this.outputDir, outputName);

        try {
            const content = await readFile(inputPath, 'utf8');
            const result = await processor(content, filename);
            await writeFile(outputPath, result, 'utf8');
            this.#processed.add(filename);
            this.emit('processed', { input: filename, output: outputName });
        } catch (err) {
            this.emit('error', { file: filename, error: err });
        }
    }

    stop() { this.#watching = false; }
}

// Usage:
const processor = new FileProcessor('./inbox', './processed');

processor
    .addProcessor('.txt', async (content) => content.toUpperCase())
    .addProcessor('.json', async (content) => {
        const data = JSON.parse(content);
        return JSON.stringify({ ...data, processedAt: new Date() }, null, 2);
    })
    .addProcessor('.csv', async (content) => {
        const lines = content.split('\n');
        const headers = lines[0];
        return [headers, ...lines.slice(1).sort()].join('\n');
    });

processor.on('processed', ({ input, output }) => console.log(`✅ ${input} → ${output}`));
processor.on('error', ({ file, error }) => console.error(`❌ ${file}: ${error.message}`));
processor.on('watching', dir => console.log(`👀 Watching: ${dir}`));

await processor.start();
```

---

### 🔵 Intermediate Project: Real-Time Collaborative Notepad (WebSocket)

```javascript
// server.js — Real-time collaborative editor backend
import { WebSocketServer } from 'ws';
import { createServer } from 'http';
import express from 'express';

const app = express();
const server = createServer(app);
const wss = new WebSocketServer({ server });

// In-memory document store (use Redis in production):
const documents = new Map();
const clientDocuments = new Map();  // client → documentId

class Document {
    constructor(id) {
        this.id = id;
        this.content = '';
        this.clients = new Set();
        this.version = 0;
        this.history = [];
    }

    applyOperation(op) {
        const prevContent = this.content;
        switch (op.type) {
            case 'insert':
                this.content = this.content.slice(0, op.position) +
                               op.text +
                               this.content.slice(op.position);
                break;
            case 'delete':
                this.content = this.content.slice(0, op.position) +
                               this.content.slice(op.position + op.length);
                break;
            case 'replace':
                this.content = op.text;
                break;
        }
        this.version++;
        this.history.push({ ...op, version: this.version, prevContent });
        return this.version;
    }

    broadcast(message, excludeClient = null) {
        const data = JSON.stringify(message);
        for (const client of this.clients) {
            if (client !== excludeClient && client.readyState === 1) {
                client.send(data);
            }
        }
    }
}

wss.on('connection', (ws, req) => {
    const clientId = Math.random().toString(36).slice(2);
    ws.clientId = clientId;

    const send = (type, payload) => ws.send(JSON.stringify({ type, payload }));

    ws.on('message', (raw) => {
        let message;
        try { message = JSON.parse(raw); }
        catch { return send('error', { message: 'Invalid JSON' }); }

        const { type, payload } = message;

        switch (type) {
            case 'join': {
                const docId = payload.documentId;
                if (!documents.has(docId)) {
                    documents.set(docId, new Document(docId));
                }
                const doc = documents.get(docId);
                doc.clients.add(ws);
                clientDocuments.set(ws, docId);

                send('joined', { documentId: docId, content: doc.content, version: doc.version });
                doc.broadcast({ type: 'user_joined', payload: { clientId } }, ws);
                break;
            }

            case 'operation': {
                const docId = clientDocuments.get(ws);
                if (!docId) return send('error', { message: 'Not in a document' });

                const doc = documents.get(docId);
                if (payload.baseVersion !== doc.version) {
                    return send('error', { message: 'Version conflict', serverVersion: doc.version });
                }

                const newVersion = doc.applyOperation(payload.operation);
                send('ack', { version: newVersion });
                doc.broadcast({
                    type: 'operation',
                    payload: { operation: payload.operation, version: newVersion, clientId }
                }, ws);
                break;
            }

            case 'cursor': {
                const docId = clientDocuments.get(ws);
                if (!docId) return;
                documents.get(docId)?.broadcast({
                    type: 'cursor',
                    payload: { clientId, position: payload.position }
                }, ws);
                break;
            }
        }
    });

    ws.on('close', () => {
        const docId = clientDocuments.get(ws);
        if (docId) {
            const doc = documents.get(docId);
            doc?.clients.delete(ws);
            doc?.broadcast({ type: 'user_left', payload: { clientId } });
            clientDocuments.delete(ws);

            if (doc?.clients.size === 0) {
                // Keep document in memory for reconnections; clean up after timeout
                setTimeout(() => {
                    if (doc.clients.size === 0) documents.delete(docId);
                }, 5 * 60 * 1000);
            }
        }
    });

    send('connected', { clientId });
});

server.listen(3000, () => console.log('Collaborative editor running on :3000'));
```

---

### 🔴 Advanced Project: High-Performance Job Queue System

```javascript
// queue.js — Production-grade job queue with Redis
import Redis from 'ioredis';
import { EventEmitter } from 'events';
import { randomUUID } from 'crypto';

class JobQueue extends EventEmitter {
    #redis;
    #subscriber;
    #queueName;
    #processors = new Map();
    #concurrency;
    #running = 0;
    #paused = false;

    constructor(queueName, { redis, concurrency = 5 } = {}) {
        super();
        this.#queueName = queueName;
        this.#concurrency = concurrency;
        this.#redis = new Redis(redis);
        this.#subscriber = new Redis(redis);
    }

    // Queue a job:
    async add(type, data, options = {}) {
        const job = {
            id: randomUUID(),
            type,
            data,
            priority: options.priority ?? 0,
            attempts: 0,
            maxAttempts: options.maxAttempts ?? 3,
            delay: options.delay ?? 0,
            createdAt: Date.now(),
        };

        const key = options.delay > 0 ? `${this.#queueName}:delayed` : `${this.#queueName}:waiting`;
        const score = options.delay > 0 ? Date.now() + options.delay : -job.priority;

        await this.#redis.zadd(key, score, JSON.stringify(job));
        this.emit('added', job);
        return job;
    }

    // Register a processor:
    process(type, handler) {
        this.#processors.set(type, handler);
        return this;
    }

    // Start processing:
    async start() {
        this.#paused = false;
        this.#processDelayedJobs();
        this.#pullAndProcess();
    }

    async #processDelayedJobs() {
        while (!this.#paused) {
            const now = Date.now();
            const jobs = await this.#redis.zrangebyscore(
                `${this.#queueName}:delayed`, 0, now, 'LIMIT', 0, 10
            );

            if (jobs.length > 0) {
                const pipeline = this.#redis.pipeline();
                for (const job of jobs) {
                    const parsed = JSON.parse(job);
                    pipeline.zadd(`${this.#queueName}:waiting`, -parsed.priority, job);
                    pipeline.zrem(`${this.#queueName}:delayed`, job);
                }
                await pipeline.exec();
            }

            await new Promise(r => setTimeout(r, 500));
        }
    }

    async #pullAndProcess() {
        while (!this.#paused) {
            if (this.#running >= this.#concurrency) {
                await new Promise(r => setTimeout(r, 50));
                continue;
            }

            const [, jobStr] = await this.#redis.bzpopmin(
                `${this.#queueName}:waiting`, 1
            ) ?? [];

            if (!jobStr) continue;

            const job = JSON.parse(jobStr);
            this.#running++;
            this.#executeJob(job).finally(() => {
                this.#running--;
            });
        }
    }

    async #executeJob(job) {
        const processor = this.#processors.get(job.type);
        if (!processor) {
            this.emit('error', new Error(`No processor for job type: ${job.type}`), job);
            return;
        }

        job.attempts++;
        job.startedAt = Date.now();

        try {
            await this.#redis.hset(`${this.#queueName}:active`, job.id, JSON.stringify(job));
            const result = await Promise.race([
                processor(job),
                new Promise((_, reject) =>
                    setTimeout(() => reject(new Error('Job timed out')), 30_000)
                ),
            ]);

            job.completedAt = Date.now();
            job.result = result;
            await this.#redis.hdel(`${this.#queueName}:active`, job.id);
            await this.#redis.zadd(`${this.#queueName}:completed`, job.completedAt, JSON.stringify(job));
            this.emit('completed', job);

        } catch (err) {
            await this.#redis.hdel(`${this.#queueName}:active`, job.id);

            if (job.attempts < job.maxAttempts) {
                const delay = Math.pow(2, job.attempts) * 1000;  // Exponential backoff
                await this.add(job.type, job.data, {
                    delay,
                    maxAttempts: job.maxAttempts - job.attempts,
                    priority: job.priority,
                });
                this.emit('retrying', job, err);
            } else {
                job.error = err.message;
                await this.#redis.zadd(`${this.#queueName}:failed`, Date.now(), JSON.stringify(job));
                this.emit('failed', job, err);
            }
        }
    }

    async getStats() {
        const [waiting, delayed, active, completed, failed] = await Promise.all([
            this.#redis.zcard(`${this.#queueName}:waiting`),
            this.#redis.zcard(`${this.#queueName}:delayed`),
            this.#redis.hlen(`${this.#queueName}:active`),
            this.#redis.zcard(`${this.#queueName}:completed`),
            this.#redis.zcard(`${this.#queueName}:failed`),
        ]);
        return { waiting, delayed, active, completed, failed };
    }
}

// Usage:
const queue = new JobQueue('email', { concurrency: 10 });

queue.process('send_email', async (job) => {
    const { to, subject, body } = job.data;
    await emailService.send({ to, subject, body });
    return { sent: true };
});

queue.process('generate_report', async (job) => {
    const report = await reportService.generate(job.data);
    return { reportUrl: report.url };
});

queue.on('completed', job => console.log(`✅ Job ${job.id} completed`));
queue.on('failed', (job, err) => console.error(`❌ Job ${job.id} failed:`, err.message));
queue.on('retrying', (job, err) => console.warn(`🔄 Retrying ${job.id} after: ${err.message}`));

await queue.start();

// Add jobs:
await queue.add('send_email', { to: 'user@example.com', subject: 'Welcome!', body: '...' });
await queue.add('generate_report', { userId: 123 }, { delay: 5000, priority: 10 });
```

---

## ⚠️ 7. Common Mistakes

---

### ❌ Mistake 1: Blocking the Event Loop with Synchronous Operations

```javascript
// ❌ WRONG — synchronous fs operations block ALL requests:
app.get('/file', (req, res) => {
    const content = fs.readFileSync('huge-file.txt', 'utf8'); // Blocks!
    res.send(content);
});

// ❌ WRONG — CPU-heavy synchronous work:
app.get('/hash', (req, res) => {
    const hash = heavyCryptoWork(req.query.data); // Blocks for 500ms!
    res.json({ hash });
});

// ✅ RIGHT — async I/O:
app.get('/file', async (req, res) => {
    const content = await readFile('huge-file.txt', 'utf8');
    res.send(content);
});

// ✅ RIGHT — CPU work in worker thread:
app.get('/hash', async (req, res) => {
    const hash = await runInWorker('./hash-worker.js', { data: req.query.data });
    res.json({ hash });
});
```

---

### ❌ Mistake 2: Not Handling Errors in Async Code

```javascript
// ❌ WRONG — unhandled promise rejection crashes Node.js:
app.get('/data', (req, res) => {
    fetchData().then(data => res.json(data));
    // If fetchData() rejects, the error is unhandled!
});

// ❌ WRONG — forgot await, error not caught:
app.get('/create', async (req, res) => {
    createRecord(req.body);  // No await! Error silently ignored
    res.status(201).json({ ok: true });
});

// ✅ RIGHT — wrap async handlers:
const asyncHandler = fn => (req, res, next) =>
    Promise.resolve(fn(req, res, next)).catch(next);

app.get('/data', asyncHandler(async (req, res) => {
    const data = await fetchData();
    res.json(data);
}));

// ✅ RIGHT — always await:
app.post('/create', asyncHandler(async (req, res) => {
    const record = await createRecord(req.body);
    res.status(201).json(record);
}));

// ✅ RIGHT — global unhandled rejection handler (last resort):
process.on('unhandledRejection', (reason, promise) => {
    console.error('Unhandled Rejection at:', promise, 'reason:', reason);
    process.exit(1);  // Don't continue in inconsistent state
});
```

---

### ❌ Mistake 3: Memory Leaks from Event Listeners

```javascript
// ❌ WRONG — adding listeners inside a loop or per-request:
app.get('/stream', (req, res) => {
    emitter.on('data', (data) => res.write(data)); // Listener NEVER removed!
    // After request ends, listener still active — memory leak!
});

// ❌ WRONG — forgetting to remove interval/timeout:
function startPolling(callback) {
    const interval = setInterval(callback, 1000);
    // interval is never cleared — even after caller is done!
}

// ✅ RIGHT — remove listeners when done:
app.get('/stream', (req, res) => {
    const handler = (data) => {
        if (!res.writableEnded) res.write(data);
    };
    emitter.on('data', handler);
    req.on('close', () => emitter.off('data', handler)); // Cleanup!
    req.on('error', () => emitter.off('data', handler));
});

// ✅ RIGHT — return cleanup function:
function startPolling(callback) {
    const interval = setInterval(callback, 1000);
    return () => clearInterval(interval);  // Return cleanup!
}

const stop = startPolling(() => console.log('tick'));
setTimeout(stop, 10_000);  // Stop after 10 seconds

// ✅ Check for listener leaks:
emitter.setMaxListeners(10);  // Warns if > 10 listeners on same event
// MaxListenersExceededWarning is always a sign of a memory leak!
```

---

### ❌ Mistake 4: SQL Injection and Security Vulnerabilities

```javascript
// ❌ NEVER build SQL with string concatenation:
const query = `SELECT * FROM users WHERE name = '${req.body.name}'`;
// Input: ' OR '1'='1 → SELECT * FROM users WHERE name = '' OR '1'='1'
// This dumps your entire users table!

// ❌ NEVER use user input in shell commands:
const { exec } = require('child_process');
exec(`cat /logs/${req.query.filename}`);
// Input: ../../../etc/passwd → reads system files!

// ✅ RIGHT — parameterized queries:
const user = await db.get('SELECT * FROM users WHERE name = ?', [req.body.name]);

// ✅ RIGHT — validate file paths:
const safeName = path.basename(req.query.filename);  // Strips directory traversal
const filePath = path.join('/logs', safeName);
if (!filePath.startsWith('/logs/')) throw new Error('Invalid path');
const content = await readFile(filePath, 'utf8');
```

---

### ❌ Mistake 5: Not Using Environment Variables for Configuration

```javascript
// ❌ WRONG — hardcoded secrets in code (gets committed to Git!):
const dbUrl = 'postgresql://admin:p@ssw0rd@prod-db.example.com/myapp';
const apiKey = 'sk-1234567890abcdef';

// ❌ WRONG — no validation of environment variables:
const port = process.env.PORT;  // Could be undefined!
server.listen(port);            // Listens on undefined port?!

// ✅ RIGHT — use dotenv for local development, validate at startup:
// npm install dotenv zod
import 'dotenv/config';
import { z } from 'zod';

const envSchema = z.object({
    NODE_ENV:     z.enum(['development', 'production', 'test']).default('development'),
    PORT:         z.string().transform(Number).pipe(z.number().int().min(1).max(65535)).default('3000'),
    DATABASE_URL: z.string().url(),
    REDIS_URL:    z.string().url().optional(),
    JWT_SECRET:   z.string().min(32),
    API_KEY:      z.string().min(16),
});

const env = envSchema.safeParse(process.env);
if (!env.success) {
    console.error('❌ Invalid environment variables:');
    console.error(env.error.format());
    process.exit(1);
}
export const config = env.data;
```

---

### ❌ Mistake 6: Incorrect `this` in Class Methods Used as Callbacks

```javascript
// ❌ WRONG — this is lost when method used as callback:
class UserService {
    constructor() {
        this.users = [];
    }

    addUser(user) {
        this.users.push(user);  // 'this' is undefined or wrong context!
    }
}

const service = new UserService();
someEmitter.on('newUser', service.addUser);  // ❌ this is lost!
setTimeout(service.addUser, 100);            // ❌ this is lost!

// ✅ RIGHT — bind in constructor:
class UserService2 {
    constructor() {
        this.users = [];
        this.addUser = this.addUser.bind(this);  // Bind once
    }
    addUser(user) { this.users.push(user); }
}

// ✅ RIGHT — arrow function class field:
class UserService3 {
    users = [];
    addUser = (user) => { this.users.push(user); }; // Arrow — lexical this
}

// ✅ RIGHT — inline arrow in callback:
someEmitter.on('newUser', (user) => service.addUser(user));
```

---

## 🔥 8. Pro Tips & Hidden Tricks

---

### 💎 Tip 1: `node:` Protocol — Explicit Built-in Imports

```javascript
// Starting Node.js 14.18+, prefix built-ins with 'node:' for clarity:
import { readFile } from 'node:fs/promises';   // ✅ Explicit — faster lookup!
import { EventEmitter } from 'node:events';
import { createServer } from 'node:http';
import { Worker } from 'node:worker_threads';
import { pipeline } from 'node:stream/promises';
import { randomUUID, createHash, pbkdf2 } from 'node:crypto';
import { promisify } from 'node:util';
import { performance, PerformanceObserver } from 'node:perf_hooks';
import { inspect } from 'node:util';

// Benefits of 'node:' prefix:
// 1. Unambiguous — cannot be shadowed by npm package with same name
// 2. Slightly faster module resolution (no npm lookup)
// 3. Future-proof — required for some Node.js core modules going forward
// 4. Better tooling/editor support — clearly signals it's built-in

// inspect — powerful object formatting:
const complex = { a: 1, b: { c: [1,2,3], d: new Map([['key','value']]) } };
console.log(inspect(complex, { depth: null, colors: true, compact: false }));

// promisify — convert callback APIs to promises:
import { promisify } from 'node:util';
import dns from 'node:dns';

const dnsLookup = promisify(dns.lookup);
const addresses = await dnsLookup('google.com');  // Returns promise!

// util.callbackify — reverse: promise → callback style:
const callbackStyle = util.callbackify(async () => 'result');
```

---

### 💎 Tip 2: `AsyncLocalStorage` — Context Without Prop Drilling

```javascript
// AsyncLocalStorage provides request-scoped context — no request object threading!
import { AsyncLocalStorage } from 'node:async_hooks';

// Create the storage:
const requestContext = new AsyncLocalStorage();

// Middleware to set context:
function contextMiddleware(req, res, next) {
    const context = {
        requestId: req.headers['x-request-id'] ?? randomUUID(),
        userId: req.user?.id,
        startTime: Date.now(),
        traceId: randomUUID(),
    };
    requestContext.run(context, next);  // All downstream code sees this context!
}

// Access context ANYWHERE in the call stack — no passing req around:
function getContext() {
    return requestContext.getStore();
}

function logger(level, message, data = {}) {
    const ctx = getContext();
    console.log(JSON.stringify({
        level,
        message,
        requestId: ctx?.requestId,    // Automatically included!
        traceId: ctx?.traceId,
        ...data,
    }));
}

// Use in any service, any depth:
class DatabaseService {
    async query(sql, params) {
        const ctx = getContext();
        const start = Date.now();

        try {
            const result = await db.query(sql, params);
            logger('info', 'Query executed', {
                sql,
                duration: Date.now() - start,
                requestId: ctx?.requestId,  // Works even 10 levels deep!
            });
            return result;
        } catch (err) {
            logger('error', 'Query failed', { sql, error: err.message });
            throw err;
        }
    }
}

// In your app:
app.use(contextMiddleware);
app.get('/users', async (req, res) => {
    // requestId automatically available everywhere!
    const users = await dbService.query('SELECT * FROM users');
    res.json(users);
});
```

---

### 💎 Tip 3: `AbortController` & `AbortSignal` — Cancellation Everywhere

```javascript
// AbortController/AbortSignal — the standard cancellation pattern in Node.js 16+

// Cancel fetch requests:
const controller = new AbortController();
const { signal } = controller;

// Auto-cancel after 5 seconds:
const timeout = AbortSignal.timeout(5000);

// Cancel on demand:
setTimeout(() => controller.abort(new Error('User cancelled')), 3000);

try {
    const response = await fetch('https://api.example.com/huge-data', {
        signal: AbortSignal.any([signal, timeout]),  // First to fire wins!
    });
    const data = await response.json();
} catch (err) {
    if (err.name === 'AbortError') {
        console.log('Request cancelled:', err.cause?.message);
    } else {
        throw err;
    }
}

// In your own async functions:
async function longOperation(signal) {
    for (let i = 0; i < 1000; i++) {
        signal.throwIfAborted();  // Check and throw if cancelled!

        await processChunk(i);

        // Or register listener:
        await new Promise((resolve, reject) => {
            const done = () => { signal.removeEventListener('abort', onAbort); resolve(); };
            const onAbort = () => reject(signal.reason);
            signal.addEventListener('abort', onAbort, { once: true });
            setTimeout(done, 100);
        });
    }
}

// Combining signals:
const combined = AbortSignal.any([
    AbortSignal.timeout(10_000),     // 10 second timeout
    controller.signal,               // Manual cancellation
]);

// In streams (Node.js 18+):
const readStream = createReadStream('file.txt', { signal: combined });
```

---

### 💎 Tip 4: Native Test Runner (Node.js 18+)

```javascript
// Node.js 18+ has a built-in test runner — no Jest required for simple projects!
// node --test tests/**/*.test.js

import { test, describe, before, after, beforeEach, afterEach, mock } from 'node:test';
import assert from 'node:assert/strict';

describe('UserService', () => {
    let service;

    before(async () => {
        // Setup shared resources
        await db.connect();
    });

    after(async () => {
        await db.disconnect();
    });

    beforeEach(() => {
        service = new UserService(db);
    });

    test('creates a user', async () => {
        const user = await service.create({ name: 'Aryan', email: 'a@b.com' });
        assert.equal(user.name, 'Aryan');
        assert.match(user.email, /@/);
        assert.ok(user.id > 0);
    });

    test('throws on duplicate email', async () => {
        await service.create({ name: 'Aryan', email: 'dup@b.com' });
        await assert.rejects(
            () => service.create({ name: 'Other', email: 'dup@b.com' }),
            { message: /duplicate/i }
        );
    });

    test('mocking with mock.fn', () => {
        const fn = mock.fn(() => 42);
        assert.equal(fn(1, 2), 42);
        assert.equal(fn.mock.calls.length, 1);
        assert.deepEqual(fn.mock.calls[0].arguments, [1, 2]);
    });

    test('timer mocking', async (t) => {
        t.mock.timers.enable(['setTimeout']);
        let called = false;
        setTimeout(() => { called = true; }, 5000);
        assert.equal(called, false);
        t.mock.timers.tick(5000);
        assert.equal(called, true);
    });
});

// Snapshot testing:
test('produces expected output', async (t) => {
    const result = processData({ input: 'test' });
    await t.test('matches snapshot', () => {
        assert.snapshot(result);  // Creates/compares snapshot file
    });
});
```

---

### 💎 Tip 5: Performance Measurement with `perf_hooks`

```javascript
// Node.js Performance API — precise timing, heap monitoring:
import { performance, PerformanceObserver } from 'node:perf_hooks';
import { monitorEventLoopDelay } from 'node:perf_hooks';

// Basic timing:
const start = performance.now();
await expensiveOperation();
const duration = performance.now() - start;
console.log(`Duration: ${duration.toFixed(3)}ms`);

// Named marks:
performance.mark('dbQueryStart');
await db.query('SELECT * FROM users');
performance.mark('dbQueryEnd');
performance.measure('dbQuery', 'dbQueryStart', 'dbQueryEnd');

// Observe measurements:
const observer = new PerformanceObserver((list) => {
    for (const entry of list.getEntries()) {
        console.log(`${entry.name}: ${entry.duration.toFixed(2)}ms`);
    }
});
observer.observe({ entryTypes: ['measure', 'http', 'http2', 'net', 'dns'] });

// Event loop delay monitoring (detect blocking!):
const histogram = monitorEventLoopDelay({ resolution: 20 });
histogram.enable();

setInterval(() => {
    const delay = histogram.mean / 1_000_000;  // Convert nanoseconds to ms
    if (delay > 10) {
        console.warn(`⚠️ Event loop delay: ${delay.toFixed(2)}ms — possible blocking!`);
    }
    histogram.reset();
}, 1000);

// Heap statistics:
import v8 from 'node:v8';
const heapStats = v8.getHeapStatistics();
console.log(`Heap used: ${(heapStats.used_heap_size / 1024 / 1024).toFixed(1)} MB`);
console.log(`Heap total: ${(heapStats.total_heap_size / 1024 / 1024).toFixed(1)} MB`);

// Garbage collection timing:
const gcObserver = new PerformanceObserver((list) => {
    for (const entry of list.getEntries()) {
        console.log(`GC: ${entry.detail.kind} in ${entry.duration.toFixed(2)}ms`);
    }
});
gcObserver.observe({ entryTypes: ['gc'] });
```

---

## 🚀 9. Advanced Concepts (Expert Level)

---

### Advanced Concept 1: The Cluster Module — Multi-Core Node.js

```javascript
// cluster.js — Utilize ALL CPU cores with the Cluster module
import cluster from 'node:cluster';
import os from 'node:os';
import { createServer } from 'node:http';

const NUM_WORKERS = os.availableParallelism();  // Number of CPU cores

if (cluster.isPrimary) {
    console.log(`Primary ${process.pid}: starting ${NUM_WORKERS} workers`);

    // Fork workers:
    for (let i = 0; i < NUM_WORKERS; i++) {
        const worker = cluster.fork();
        worker.on('message', (msg) => {
            console.log(`Worker ${worker.id} says:`, msg);
        });
    }

    // Restart dead workers:
    cluster.on('exit', (worker, code, signal) => {
        console.error(`Worker ${worker.process.pid} died (${signal ?? code}). Restarting...`);
        cluster.fork();  // Replace the dead worker
    });

    // Zero-downtime reload:
    process.on('SIGUSR2', () => {
        const workers = Object.values(cluster.workers);
        let i = 0;

        const reloadNext = () => {
            if (i >= workers.length) return console.log('Reload complete');
            const worker = workers[i++];
            worker.once('exit', reloadNext);  // Wait for exit before next
            worker.send('shutdown');
            setTimeout(() => worker.kill(), 10_000).unref();  // Force kill after 10s
        };

        reloadNext();
    });

    // Graceful shutdown of all workers:
    const shutdown = async (signal) => {
        console.log(`Shutting down cluster (${signal})`);
        for (const worker of Object.values(cluster.workers)) {
            worker.send('shutdown');
        }
        setTimeout(() => process.exit(0), 30_000);
    };

    process.on('SIGTERM', () => shutdown('SIGTERM'));
    process.on('SIGINT',  () => shutdown('SIGINT'));

} else {
    // Worker process — runs the actual server:
    const server = createServer((req, res) => {
        res.writeHead(200);
        res.end(`Hello from worker ${cluster.worker.id} (PID: ${process.pid})\n`);
    });

    server.listen(3000);

    // Listen for shutdown signal from primary:
    process.on('message', (msg) => {
        if (msg === 'shutdown') {
            server.close(() => {
                console.log(`Worker ${cluster.worker.id} shutdown complete`);
                process.exit(0);
            });
        }
    });

    console.log(`Worker ${cluster.worker.id} (PID ${process.pid}) started`);
}

// In production: use PM2 for cluster management:
// pm2 start app.js -i max          # Use all CPU cores
// pm2 reload app.js                 # Zero-downtime reload
// pm2 monit                         # Real-time monitoring
```

---

### Advanced Concept 2: Native Addons with N-API

```javascript
// When you need C/C++ performance in Node.js:
// Node-API (N-API) provides a stable ABI across Node versions

// addon.c:
/*
#include <node_api.h>
#include <math.h>

napi_value ComputePrime(napi_env env, napi_callback_info info) {
    size_t argc = 1;
    napi_value args[1];
    napi_get_cb_info(env, info, &argc, args, NULL, NULL);

    int64_t n;
    napi_get_value_int64(env, args[0], &n);

    // Heavy computation in C — doesn't block event loop if in thread:
    bool is_prime = n > 1;
    for (int64_t i = 2; i <= sqrt(n) && is_prime; i++)
        if (n % i == 0) is_prime = false;

    napi_value result;
    napi_get_boolean(env, is_prime, &result);
    return result;
}

napi_value Init(napi_env env, napi_value exports) {
    napi_value fn;
    napi_create_function(env, "isPrime", NAPI_AUTO_LENGTH, ComputePrime, NULL, &fn);
    napi_set_named_property(env, exports, "isPrime", fn);
    return exports;
}

NAPI_MODULE(NODE_GYP_MODULE_NAME, Init)
*/

// Better alternative: node-addon-api (C++ wrapper for N-API)
// Or use WebAssembly (WASM) for portable performance

// Using an existing native addon:
import addon from './build/Release/addon.node';  // Compiled .node file
console.log(addon.isPrime(104729));  // true — very fast C computation

// Sending work to native code via worker threads (non-blocking):
const { Worker } = await import('node:worker_threads');
const result = await new Promise((resolve, reject) => {
    const w = new Worker(`
        const { workerData, parentPort } = require('worker_threads');
        const addon = require('./build/Release/addon');
        parentPort.postMessage(addon.isPrime(workerData.n));
    `, { eval: true, workerData: { n: 104729 } });
    w.on('message', resolve);
    w.on('error', reject);
});
```

---

### Advanced Concept 3: Diagnostics & APM (Application Performance Monitoring)

```javascript
// Node.js has rich built-in diagnostics tools:

// ── DIAGNOSTIC REPORTS ────────────────────────────────────────────────────
// Generate a JSON report with heap dump, native stack traces, env info:
process.report.writeReport();              // Write to file
const report = process.report.getReport(); // Get as string
process.report.reportOnFatalError = true;  // Auto-report on crash
process.report.reportOnSignal = true;      // Report on SIGUSR2
process.report.reportOnUncaughtException = true;

// ── V8 PROFILING ──────────────────────────────────────────────────────────
import v8 from 'node:v8';

// Take heap snapshot:
const snapshotStream = v8.writeHeapSnapshot();
console.log('Heap snapshot written to:', snapshotStream);
// Load in Chrome DevTools → Memory tab

// Profiling via CLI:
// node --prof app.js             # Generate V8 profiling data
// node --prof-process isolate-*.log > profile.txt  # Process the log
// node --cpu-prof app.js         # Generate CPU profile (.cpuprofile)
// node --heap-prof app.js        # Generate heap profile (.heapprofile)

// ── OPENTELEMETRY — production observability ──────────────────────────────
// npm install @opentelemetry/sdk-node @opentelemetry/auto-instrumentations-node

// tracing.js (must be imported FIRST with --require):
import { NodeSDK } from '@opentelemetry/sdk-node';
import { getNodeAutoInstrumentations } from '@opentelemetry/auto-instrumentations-node';
import { OTLPTraceExporter } from '@opentelemetry/exporter-trace-otlp-http';

const sdk = new NodeSDK({
    traceExporter: new OTLPTraceExporter({
        url: process.env.OTEL_EXPORTER_OTLP_ENDPOINT,
    }),
    instrumentations: [
        getNodeAutoInstrumentations({
            '@opentelemetry/instrumentation-http': { enabled: true },
            '@opentelemetry/instrumentation-express': { enabled: true },
            '@opentelemetry/instrumentation-pg': { enabled: true },
        }),
    ],
});

sdk.start();

// ── PINO — high-performance structured logging ────────────────────────────
// npm install pino
import pino from 'pino';

const logger = pino({
    level: process.env.LOG_LEVEL ?? 'info',
    base: { pid: process.pid, host: os.hostname() },
    timestamp: pino.stdTimeFunctions.isoTime,
    transport: process.env.NODE_ENV !== 'production'
        ? { target: 'pino-pretty', options: { colorize: true } }
        : undefined,
});

// Child logger with additional context:
const requestLogger = logger.child({ requestId: '123', service: 'user-api' });
requestLogger.info({ userId: 42, action: 'login' }, 'User logged in');
// Outputs: {"level":30,"time":"...","requestId":"123","userId":42,"action":"login","msg":"User logged in"}

// Pino is 5-10× faster than Winston, 20× faster than Bunyan
```

---

### ⚡ Performance & Optimization Table

| Technique                          | Impact   | When to Use                                         |
|------------------------------------|----------|-----------------------------------------------------|
| `UV_THREADPOOL_SIZE=16`            | High     | Many concurrent file/crypto/DNS operations          |
| Cluster mode (PM2 or cluster)      | Very High | Utilize all CPU cores                              |
| `--max-old-space-size=4096`        | High     | Memory-intensive applications                      |
| Connection pooling (DB)            | Very High | Always — never create connection per request        |
| Redis caching                      | Very High | DB queries that repeat with same params             |
| Streaming for large files          | Very High | Never load large files into memory                 |
| `node --enable-source-maps`        | Dev only  | Accurate stack traces with TypeScript               |
| Use `Buffer.allocUnsafe` carefully | Medium   | Small perf gain for frequent small buffer creation  |
| `worker_threads` for CPU work      | Very High | Any sync work > 10ms                               |
| Avoid `JSON.parse` of large strings| High     | Stream-parse with `jsonstream` or similar           |
| Keep-alive HTTP connections        | High     | Reuse TCP connections for same-host requests        |
| `--jitless` flag                   | Low      | Security-hardened environments (QUIC/WebCrypto)     |

---

## 💀 10. 0.01% Hidden Secrets — Ultra Elite

---

### 🔮 Secret 1: `process.nextTick` vs `queueMicrotask` — The Real Difference

```javascript
// Both run before the next event loop iteration, but they're DIFFERENT queues!

// process.nextTick — Node.js specific, runs BEFORE Promises
// queueMicrotask — Web standard, runs AFTER process.nextTick

console.log('1: sync');

process.nextTick(() => console.log('3: nextTick 1'));
queueMicrotask(() => console.log('5: microtask 1'));

Promise.resolve().then(() => {
    console.log('6: promise 1');
    process.nextTick(() => console.log('7: nextTick inside promise'));
    queueMicrotask(() => console.log('8: microtask inside promise'));
});

process.nextTick(() => {
    console.log('4: nextTick 2');
    queueMicrotask(() => console.log('???: microtask inside nextTick'));
});

console.log('2: sync end');

// Order: 1, 2, 3, 4, ???, 5, 6, 7, 8
// KEY: nextTick queue drains COMPLETELY before microtask queue runs
// And microtasks added during nextTick run AFTER ALL nextTicks!

// PRACTICAL RULE:
// Use process.nextTick when you need to fire before I/O callbacks
// Use queueMicrotask for web-compatible code
// Use Promise.resolve().then() for the most predictable behavior

// Real use case for nextTick — emit events after constructor:
class Stream extends EventEmitter {
    constructor() {
        super();
        // Can't emit here — listeners haven't been added yet!
        process.nextTick(() => this.emit('ready'));
        // Now callers can: new Stream().on('ready', handler)
    }
}
```

---

### 🔮 Secret 2: `vm` Module — Run Code in Isolated Contexts

```javascript
// node:vm — run JavaScript in a separate V8 context (sandbox)
import vm from 'node:vm';

// Create an isolated context:
const context = vm.createContext({
    console,                          // Expose console
    Math,                             // Expose Math
    setTimeout,                       // Expose timers
    // Everything NOT here is unavailable to the sandboxed code!
    // No fs, no http, no process!
});

// Run code in the context:
const code = `
    const result = Math.sqrt(144);
    result;
`;
const value = vm.runInContext(code, context, { timeout: 1000 });
console.log(value); // 12

// Script — compile once, run many times:
const script = new vm.Script(`
    const arr = [1, 2, 3, 4, 5];
    arr.reduce((sum, n) => sum + n, 0);
`);

for (let i = 0; i < 1000; i++) {
    script.runInContext(context); // Reuses compiled code
}

// Module — run ES modules in sandbox:
const module = new vm.SyntheticModule(['default'], function() {
    this.setExport('default', 'Hello from module!');
});

// Real use cases:
// - REPL environments
// - Template engines (EJS internals use vm)
// - Plugin systems with sandboxing
// - Online code editors (CodeSandbox, RunKit)
// Note: vm is NOT a true security sandbox — use dedicated processes for untrusted code!
```

---

### 🔮 Secret 3: V8 Flags for Maximum Performance

```javascript
// node's --v8-options shows all flags. Key ones for production:

// node --turbo-instruction-scheduling app.js    # Better instruction reordering
// node --optimize-for-size app.js               # Reduce memory at cost of speed
// node --max-semi-space-size=128 app.js         # Larger young gen (more GC pause, less frequency)
// node --max-old-space-size=8192 app.js         # 8GB heap limit

// Profile-guided optimization (AFTER collecting profile):
// node --prof app.js
// node --prof-process isolate-0x*.log > profile.txt
// Analysis reveals hot functions the JIT is struggling with

// Trigger V8 optimization hints in code:
function hotFunction(x, y) {
    // Keep types consistent across calls — V8 optimizes based on "shapes"
    return x + y;  // If always called with (int, int), V8 makes it very fast
}

// Type consistency is key — V8 creates "Hidden Classes" for objects:
// ✅ CONSISTENT SHAPE — V8 optimizes this well:
function makePoint(x, y) {
    return { x, y };  // Always same properties in same order
}

// ❌ INCONSISTENT — different shapes, V8 can't optimize:
function makePointBad(x, y, hasZ = false) {
    if (hasZ) return { x, y, z: 0 };  // Different shape!
    return { x, y };
}

// Monomorphic vs Polymorphic function calls:
class Shape { area() {} }
class Circle extends Shape { area() { return Math.PI * this.r ** 2; } }
class Square extends Shape { area() { return this.s ** 2; } }

// ❌ Polymorphic — V8 can't predict which area() to call:
function totalArea(shapes) {
    return shapes.reduce((sum, s) => sum + s.area(), 0);
}
totalArea([new Circle(), new Square(), new Circle()]); // Megamorphic!

// ✅ Monomorphic — V8 can inline the call:
function circleArea(circles) {
    return circles.reduce((sum, c) => sum + c.area(), 0);
}
```

---

### 🔮 Secret 4: Diagnostic Channels (`node:diagnostics_channel`)

```javascript
// diagnostics_channel — publish/subscribe to runtime events in libraries
// Available since Node.js 15 — used by OpenTelemetry, APM tools, loggers

import diagnostics_channel from 'node:diagnostics_channel';

// PUBLISHING (library author):
const channel = diagnostics_channel.channel('my-library:request');

async function makeRequest(url) {
    if (channel.hasSubscribers) {  // Only publish if someone listens (performance!)
        channel.publish({ type: 'start', url, timestamp: Date.now() });
    }
    try {
        const result = await fetch(url);
        if (channel.hasSubscribers) {
            channel.publish({ type: 'end', url, status: result.status });
        }
        return result;
    } catch (err) {
        if (channel.hasSubscribers) {
            channel.publish({ type: 'error', url, error: err });
        }
        throw err;
    }
}

// SUBSCRIBING (monitoring tool):
diagnostics_channel.subscribe('my-library:request', (message) => {
    console.log(`[TRACE] ${message.type}: ${message.url}`);
});

// Built-in channels (Node.js core publishes to these!):
diagnostics_channel.subscribe('http.client.request.start', ({ request }) => {
    console.log(`Outgoing HTTP: ${request.method} ${request.path}`);
});

diagnostics_channel.subscribe('net.server.connection', ({ server, socket }) => {
    console.log(`New connection from ${socket.remoteAddress}`);
});

// This is how APM tools (DataDog, New Relic) instrument Node.js without modifying your code!
```

---

### 🔮 Secret 5: `node:sea` — Single Executable Applications (Node.js 20+)

```javascript
// Single Executable Applications — package your app as a self-contained binary!
// No Node.js installation required on target machine!

// Steps:
// 1. Create sea-config.json:
/*
{
    "main": "dist/bundle.js",
    "output": "sea-prep.blob",
    "disableExperimentalSEAWarning": true,
    "useSnapshot": false,
    "useCodeCache": true
}
*/

// 2. Bundle your app:
// esbuild src/index.js --bundle --platform=node --outfile=dist/bundle.js

// 3. Generate the blob:
// node --experimental-sea-config sea-config.json

// 4. Copy Node.js binary:
// cp $(which node) myapp

// 5. Inject the blob:
// npx postject myapp NODE_SEA_BLOB sea-prep.blob \
//     --sentinel-fuse NODE_SEA_FUSE_fce680ab2cc467b6e072b8b5df1996b2

// 6. Run anywhere:
// ./myapp  (no Node.js needed!)

// At runtime, detect if running as SEA:
import { isSea, getAsset, getAssetAsBlob } from 'node:sea';

if (isSea()) {
    console.log('Running as Single Executable Application');
    // Read bundled asset files:
    const configJson = getAsset('config.json', 'utf8');
    const icon = getAssetAsBlob('icon.png');
}
```

---

### 🔮 Secret 6: `node:readline/promises` — Interactive CLI

```javascript
// Build beautiful interactive CLI tools with readline:
import { createInterface } from 'node:readline/promises';
import { stdin, stdout } from 'node:process';

const rl = createInterface({ input: stdin, output: stdout });

// Ask a question and await the answer:
const name = await rl.question('What is your name? ');
console.log(`Hello, ${name}!`);

const ageStr = await rl.question('How old are you? ');
const age = parseInt(ageStr);

// Multi-choice:
console.log('Choose your language:');
console.log('  1. Python');
console.log('  2. JavaScript');
console.log('  3. Rust');
const choice = await rl.question('Enter number (1-3): ');

// Password input (no echo):
process.stdout.write('Enter password: ');
stdin.setRawMode(true);
let password = '';
for await (const char of stdin) {
    if (char.toString() === '\r' || char.toString() === '\n') break;
    if (char.toString() === '\x7f') { password = password.slice(0, -1); }
    else { password += char.toString(); }
}
stdin.setRawMode(false);
console.log('');  // Newline after password

rl.close();

// Build an interactive REPL:
const customRepl = createInterface({
    input: stdin,
    output: stdout,
    prompt: '🟢 > ',
    completer: (line) => {
        const completions = ['help', 'exit', 'list', 'add', 'remove'];
        const hits = completions.filter(c => c.startsWith(line));
        return [hits.length ? hits : completions, line];
    },
});

customRepl.prompt();

customRepl.on('line', (input) => {
    const cmd = input.trim();
    if (cmd === 'exit') process.exit(0);
    else if (cmd === 'help') console.log('Commands: help, exit, list, add, remove');
    else console.log(`Unknown: ${cmd}`);
    customRepl.prompt();
});
```

---

### 🔮 Secret 7: `node:tls` — Custom TLS/mTLS

```javascript
// Mutual TLS (mTLS) — both client AND server authenticate with certificates
import tls from 'node:tls';
import { readFileSync } from 'node:fs';

// mTLS server — requires client certificate:
const server = tls.createServer({
    key: readFileSync('server.key'),
    cert: readFileSync('server.cert'),
    ca: readFileSync('ca.cert'),       // CA that signed client certs
    requestCert: true,                  // Require client certificate
    rejectUnauthorized: true,           // Reject if cert not from our CA
}, (socket) => {
    const cert = socket.getPeerCertificate();
    if (!socket.authorized) {
        socket.destroy(new Error('Unauthorized'));
        return;
    }
    console.log(`Authenticated client: ${cert.subject.CN}`);
    socket.write('Connected to secure server\n');
    socket.end();
});

server.listen(4443);

// mTLS client:
const client = tls.connect({
    host: 'localhost',
    port: 4443,
    key:  readFileSync('client.key'),   // Client's private key
    cert: readFileSync('client.cert'),  // Client's certificate
    ca:   readFileSync('ca.cert'),      // CA to verify server cert
    checkServerIdentity: (host, cert) => {
        // Custom hostname verification
        if (cert.subject.CN !== 'my-service') {
            return new Error('Server identity mismatch');
        }
    },
}, () => {
    console.log('Connected with mTLS!');
    client.write('Hello secure world');
});

// ALPN — Application-Layer Protocol Negotiation:
const h2Server = tls.createServer({
    key: readFileSync('server.key'),
    cert: readFileSync('server.cert'),
    ALPNProtocols: ['h2', 'http/1.1'],  // Negotiate HTTP/2 or HTTP/1.1
}, (socket) => {
    console.log('Negotiated protocol:', socket.alpnProtocol);
});
```

---

### 🔮 Secret 8: Undici — Node.js's Internal HTTP Client

```javascript
// Undici is Node.js's new high-performance HTTP client
// (used internally by node's fetch implementation since Node 18)
// npm install undici

import { request, stream, pipeline, connect, setGlobalDispatcher, Agent } from 'undici';

// Highly optimized pool (vs creating new connections):
const agent = new Agent({
    connections: 10,                  // Pool size
    pipelining: 10,                   // HTTP pipelining
    keepAliveTimeout: 30_000,         // Keep connections alive 30s
    keepAliveMaxTimeout: 60_000,
    headersTimeout: 5_000,
    bodyTimeout: 30_000,
});

setGlobalDispatcher(agent);  // Use for all fetch() calls globally!

// Undici request — faster than fetch for server-to-server:
const { statusCode, headers, body } = await request('https://api.example.com/data', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ key: 'value' }),
    signal: AbortSignal.timeout(5000),
    bodyTimeout: 10_000,
    headersTimeout: 5_000,
});

const data = await body.json();  // or body.text(), body.arrayBuffer()

// Streaming with undici (zero-copy for large files):
await stream('https://example.com/large-file', { opaque: createWriteStream('output.bin') },
    ({ statusCode, headers, opaque: file }) => file
);

// Benchmarks: Undici is 2-3× faster than axios, 30% faster than node-fetch
// for high-throughput server-to-server calls
```

---

### 🔮 Secret 9: Compile-Time TypeScript Checks with `satisfies`

```javascript
// Node.js + TypeScript = the modern professional stack
// Key patterns for Node.js TypeScript mastery:

// ── TYPED ENVIRONMENT CONFIG ──────────────────────────────────────────────
interface Env {
    readonly NODE_ENV: 'development' | 'production' | 'test';
    readonly PORT: string;
    readonly DATABASE_URL: string;
}

const env = process.env as unknown as Env;  // Type assertion for env

// ── TYPED EVENT EMITTER ───────────────────────────────────────────────────
import { EventEmitter } from 'node:events';

interface DataEvents {
    'data': [payload: { id: number; value: string }];
    'error': [error: Error];
    'end': [];
}

class TypedEmitter extends EventEmitter {
    override on<K extends keyof DataEvents>(
        event: K,
        listener: (...args: DataEvents[K]) => void
    ): this { return super.on(event, listener as any); }

    override emit<K extends keyof DataEvents>(
        event: K,
        ...args: DataEvents[K]
    ): boolean { return super.emit(event, ...args); }
}

const emitter = new TypedEmitter();
emitter.on('data', ({ id, value }) => console.log(id, value)); // ✅ Typed!
// emitter.on('data', ({ invalid }) => {}); // ❌ TypeScript error!

// ── ZODSCHEMA VALIDATION WITH INFERENCE ──────────────────────────────────
import { z } from 'zod';

const UserSchema = z.object({
    id: z.number().int().positive(),
    name: z.string().min(1).max(100),
    email: z.string().email(),
    role: z.enum(['admin', 'user', 'moderator']).default('user'),
    createdAt: z.date().default(new Date),
});

type User = z.infer<typeof UserSchema>;  // Derive TypeScript type from schema!

function createUser(input: unknown): User {
    return UserSchema.parse(input);  // Runtime validation + type safety
}
```

---

### 🔮 Secret 10: The `node:http2` Module — Native HTTP/2

```javascript
// HTTP/2 — multiplexing, server push, header compression
import http2 from 'node:http2';
import { readFileSync } from 'node:fs';

// HTTP/2 server:
const server = http2.createSecureServer({
    key: readFileSync('server.key'),
    cert: readFileSync('server.cert'),
    allowHTTP1: true,                 // Fallback to HTTP/1.1
});

server.on('stream', (stream, headers) => {
    const path = headers[':path'];
    const method = headers[':method'];

    console.log(`${method} ${path}`);

    if (path === '/') {
        // Server Push — send files before client requests them!
        stream.pushStream({ ':path': '/styles.css' }, (err, pushStream) => {
            if (!err) {
                pushStream.respond({ ':status': 200, 'content-type': 'text/css' });
                pushStream.end('body { color: red; }');
            }
        });

        stream.respond({
            ':status': 200,
            'content-type': 'text/html',
        });
        stream.end('<link rel="stylesheet" href="/styles.css"><h1>HTTP/2 with Push!</h1>');
    }
});

server.listen(8443);

// HTTP/2 client:
const client = http2.connect('https://localhost:8443', {
    ca: readFileSync('ca.cert'),
});

const req = client.request({ ':path': '/' });
req.on('push', (headers, flags) => {
    console.log('Server pushed:', headers[':path']);  // '/styles.css'
});
req.on('data', chunk => process.stdout.write(chunk));
req.end();

// HTTP/2 vs HTTP/1.1:
// ✅ Multiplexing: multiple requests over ONE connection
// ✅ Header compression: HPACK reduces overhead by 85%+
// ✅ Server push: send resources before asked
// ✅ Stream prioritization: control which responses to prioritize
```

---

## 🗺️ 11. Complete Roadmap

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — FOUNDATION (Week 1-3)
├── Week 1: Node.js setup, npm, CommonJS vs ESM, core modules (fs, path, os)
├── Week 2: HTTP server, EventEmitter, callbacks → promises → async/await
└── Week 3: Streams, Buffer, error handling patterns, process/signals
    └── Project: File processor CLI, static file server, CSV processor

PHASE 2 — WEB DEVELOPMENT (Week 4-7)
├── Week 4: Express.js — middleware, routing, error handling, authentication
├── Week 5: REST API design, validation (Zod/Joi), pagination, filtering
├── Week 6: Databases — SQLite/PostgreSQL with connection pooling, Redis caching
└── Week 7: Authentication — JWT, sessions, OAuth2, bcrypt, rate limiting
    └── Project: Full REST API with auth, CRUD, caching, rate limiting

PHASE 3 — ADVANCED NODE.JS (Week 8-12)
├── Week 8:  Event loop deep dive, blocking analysis, profiling with perf_hooks
├── Week 9:  Worker threads, cluster module, libuv thread pool tuning
├── Week 10: WebSockets, Server-Sent Events, real-time applications
├── Week 11: Streams advanced — backpressure, Transform streams, pipeline
└── Week 12: Testing (node:test/Jest/Vitest), CI/CD, Docker containerization
    └── Project: Real-time chat app, job queue system, streaming data processor

PHASE 4 — PRODUCTION NODE.JS (Month 4-5)
├── Month 4: PM2/Kubernetes deployment, health checks, graceful shutdown
├── Month 5: OpenTelemetry, Pino logging, Prometheus metrics, distributed tracing
    └── Project: Microservice with full observability stack

PHASE 5 — EXPERT / 0.01% (Month 6+)
├── V8 internals — hidden classes, JIT optimization, GC tuning
├── N-API native addons, WebAssembly integration
├── Diagnostics — heap dumps, CPU profiles, diagnostic reports
├── Custom protocols — TCP/UDP servers, binary protocols
└── Contribute to Node.js core, major npm packages (Express, Fastify, etc.)
```

---

### 🏁 Milestone Checklist

- [ ] I understand the event loop phases and execution order
- [ ] I can explain why blocking the event loop is catastrophic
- [ ] I use streams for all large file/data operations
- [ ] I implement proper graceful shutdown in all my servers
- [ ] I validate all environment variables at startup
- [ ] I use worker threads for any CPU-bound operation > 10ms
- [ ] I have connection pooling for all database clients
- [ ] I implement rate limiting and security headers on all APIs
- [ ] I understand `process.nextTick` vs `Promise.resolve().then()`
- [ ] I can debug a memory leak using heap snapshots
- [ ] I have zero `console.log` in production — only structured logging
- [ ] I use `AsyncLocalStorage` for request context propagation
- [ ] I have published an npm package
- [ ] I can profile event loop delay and identify blocking code

---

## 🧩 12. Bonus Deep Insights

---

### 🔮 Mental Model: "Node.js Is a Single Chef With a Very Organized Kitchen"

The hardest concept for developers coming from multi-threaded languages is: how can ONE thread handle thousands of requests?

The key insight: **most time in a web server is WAITING, not computing.** When your server receives a request that needs a database query, the CPU does almost nothing for 10-50ms while waiting for the database. With threads, that thread sleeps and wastes memory. Node.js doesn't sleep — it registers a callback and immediately handles the NEXT request.

This works because:
1. JavaScript runs in a single thread (V8)
2. I/O operations are handled by libuv (which uses the OS's async I/O facilities)
3. When I/O completes, the callback is queued in the event loop
4. The event loop continuously processes callbacks when the JS thread is free

**The result:** Node.js can handle 50,000+ simultaneous connections with a fraction of the memory that would require 50,000 threads.

---

### 🤫 Deep Insight 1: `require` Is Cached

```javascript
// CommonJS modules are cached after first load!
const a = require('./module');
const b = require('./module');
console.log(a === b); // TRUE — same object reference!

// This means:
// 1. Module initialization runs ONCE (singleton-like behavior)
// 2. State shared across requires — intentional!
// 3. Circular requires work but can return partial objects

// Circular dependency:
// a.js:
const b = require('./b');
module.exports = { a: 1, fromB: b.b };

// b.js:
const a = require('./a');  // Gets PARTIALLY initialized 'a'!
module.exports = { b: 2, fromA: a.a };  // a.a is 1, a.fromB is undefined

// Clear the cache to force reload:
delete require.cache[require.resolve('./module')];
const fresh = require('./module');  // Runs initialization again!

// ESM modules: also cached, but by URL (including query strings!)
```

---

### 🤫 Deep Insight 2: Node.js Is NOT Single-Threaded

This is the biggest misconception: **Node.js is NOT single-threaded.**

What IS single-threaded:
- JavaScript execution (V8)
- The event loop callbacks

What runs on MULTIPLE threads (libuv thread pool):
- `fs.*` file operations
- `dns.lookup` DNS resolution
- `crypto` operations (bcrypt, scrypt, pbkdf2)
- `zlib` compression
- Custom worker threads

What the OS handles asynchronously (no threads needed):
- Network I/O (TCP, UDP)
- Pipes
- Timers

The "single-threaded" label refers to JavaScript execution. The underlying C++ engine (libuv) uses multiple threads transparently. Understanding this reveals why `UV_THREADPOOL_SIZE` matters for file-heavy applications.

---

### 🤫 Deep Insight 3: The Cost of `async/await`

```javascript
// Every async function creates a hidden state machine.
// Every await point is a suspension point.
// This has real overhead — microseconds per call.

// For VERY hot paths (millions of calls/second):
// Sync is faster than async for in-memory operations!

// But the RULE is:
// Use async for ANYTHING that touches I/O
// Use sync for pure CPU computation that completes in < 1ms

// Async overhead measurement:
const N = 1_000_000;

async function asyncAdd(a, b) { return a + b; }
function syncAdd(a, b) { return a + b; }

console.time('async');
for (let i = 0; i < N; i++) await asyncAdd(1, 2);
console.timeEnd('async');  // ~500ms on typical hardware

console.time('sync');
for (let i = 0; i < N; i++) syncAdd(1, 2);
console.timeEnd('sync');   // ~5ms — 100× faster!

// Key takeaway: use async ONLY for I/O, not for pure computation
```

---

### 🧠 The Big Picture — Node.js in the Modern Ecosystem

```
Node.js Evolution:
  2009: Ryan Dahl creates Node.js — server-side JavaScript
  2010: npm launches — the package ecosystem explodes
  2012: Node.js v0.8 — cluster module for multi-core
  2015: io.js fork and reunion — corporate governance settled
  2015: npm surpasses all other registries in package count
  2016: Node.js LTS cycle established — enterprise adoption
  2017: Node.js v8 — async_hooks, N-API stable
  2020: Native ESM support — modern JavaScript in Node.js
  2022: Native fetch API — built-in HTTP client
  2022: Native test runner — no Jest required
  2023: Node.js v20 — permission model, SEA, stable test runner
  2024: Node.js v22 — WebSocket built-in, more Corepack features

The modern Node.js ecosystem:
  Runtimes: Node.js, Deno, Bun (all V8 or SpiderMonkey based)
  Frameworks: Fastify, Express, NestJS, Hono, Elysia
  ORMs: Drizzle, Prisma, Sequelize, TypeORM
  Testing: Vitest, Jest, node:test (built-in)
  Bundlers: esbuild, Rollup, Webpack (for Node, mostly esbuild/tsup)
  Deployment: Docker, PM2, Railway, Render, Fly.io, AWS Lambda
  Edge: Cloudflare Workers, Vercel Edge, Deno Deploy

Where Node.js is unbeatable:
  ✅ Real-time applications (chat, games, collaborative tools)
  ✅ API gateways and BFF (Backend for Frontend)
  ✅ Serverless functions (warm start, ecosystem)
  ✅ CLI tooling (package.json scripts, build tools)
  ✅ Streaming data processing
  ✅ Full-stack JavaScript (Next.js, Remix, SvelteKit)

Where alternatives are better:
  ❌ CPU-intensive computation → Rust, Go, C++
  ❌ ML training → Python (PyTorch, TensorFlow)
  ❌ Highest concurrency → Go (goroutines)
  ❌ Memory-constrained embedded → C, Rust

Learning after Node.js:
  → Bun (faster Node.js compatible runtime, built-in SQLite)
  → Deno (secure by default, TypeScript built-in, WinterCG)
  → TypeScript (statically typed JavaScript — industry standard)
  → Next.js / Remix (full-stack React with Node.js backend)
```

---

## 📌 13. Summary (Quick Revision & Cheat Sheet)

---

### Core Concepts (1-line each)

| Concept                 | What It Means                                                              |
|-------------------------|----------------------------------------------------------------------------|
| Event loop              | Single-threaded async orchestrator — processes callbacks in phases         |
| Non-blocking I/O        | Start I/O, register callback, move on — come back when result is ready    |
| libuv                   | C library that handles async I/O, thread pool, and the event loop         |
| EventEmitter            | Pub/sub pattern — foundation of streams, servers, process                 |
| Streams                 | Process data in chunks — handle gigabytes with kilobytes of RAM           |
| Worker threads          | True parallelism for CPU-bound work — separate V8 instances               |
| Cluster module          | Spawn N worker processes sharing a port — use all CPU cores               |
| `process.nextTick`      | Queue callback before I/O events — runs before Promise microtasks         |
| CommonJS vs ESM         | `require/module.exports` (CJS) vs `import/export` (ESM)                  |
| `AsyncLocalStorage`     | Request-scoped context without passing it through every function           |

---

### The 10 Things to Remember

1. ✅ **NEVER block the event loop** — any sync CPU work > 10ms kills performance
2. ✅ **Use streams for large files** — never `readFileSync` or `readFile` on large data
3. ✅ **Always handle `error` events** on EventEmitters — unhandled errors crash Node.js
4. ✅ **Use `pipeline` not `.pipe()`** — pipeline handles errors and cleanup correctly
5. ✅ **Validate environment variables at startup** — use Zod, fail fast on missing config
6. ✅ **Use connection pooling** for databases — never open/close per request
7. ✅ **Implement graceful shutdown** — close server, finish in-flight requests, then exit
8. ✅ **Use `node:` prefix** for built-in imports — `node:fs`, `node:http`, `node:events`
9. ✅ **Worker threads for CPU work** — image processing, crypto, ML inference
10. ✅ **Structured logging with Pino** — never `console.log` in production

---

### Quick Reference Cheat Sheet

```javascript
// ── SETUP ─────────────────────────────────────────────────────────────────
// nvm install --lts && nvm use --lts
// npm init -y
// node --watch src/index.js     (dev mode, Node 18+)
// UV_THREADPOOL_SIZE=16 node app.js

// ── ASYNC PATTERNS ────────────────────────────────────────────────────────
// Promise.all([p1, p2, p3])           // Concurrent, fail-fast
// Promise.allSettled([p1, p2, p3])    // Concurrent, get all results
// Promise.race([p1, timeout])         // First to settle wins
// Promise.any([p1, p2, p3])           // First to SUCCEED wins

// Retry with exponential backoff:
async function retry(fn, maxAttempts = 3, baseDelayMs = 1000) {
    for (let attempt = 1; attempt <= maxAttempts; attempt++) {
        try { return await fn(); }
        catch (err) {
            if (attempt === maxAttempts) throw err;
            await new Promise(r => setTimeout(r, baseDelayMs * 2 ** (attempt - 1)));
        }
    }
}

// Timeout:
const result = await Promise.race([
    operation(),
    new Promise((_, reject) => setTimeout(() => reject(new Error('Timeout')), 5000)),
]);
// Better:
const result2 = await operation();  // In fetch:  { signal: AbortSignal.timeout(5000) }

// ── FILE SYSTEM ───────────────────────────────────────────────────────────
import { readFile, writeFile, appendFile, mkdir, readdir, stat, unlink, rename } from 'node:fs/promises';
import { createReadStream, createWriteStream } from 'node:fs';
import { pipeline } from 'node:stream/promises';

// Read entire file:   await readFile(path, 'utf8')
// Write file:         await writeFile(path, content)
// Append:             await appendFile(path, content)
// Create dir:         await mkdir(path, { recursive: true })
// List dir:           await readdir(path)
// File info:          await stat(path)
// Delete file:        await unlink(path)
// Rename/move:        await rename(oldPath, newPath)
// Stream pipeline:    await pipeline(readable, transform, writable)
// Line-by-line:       for await (const line of rl) { }

// ── HTTP ──────────────────────────────────────────────────────────────────
// Native fetch (Node 18+):
const r = await fetch(url, { method, headers, body, signal });
await r.json() / r.text() / r.arrayBuffer()

// Express essentials:
// app.use(middleware)           // All routes
// app.get/post/put/patch/delete(path, handler)
// router.use(middleware)        // Router-scoped middleware
// req.params.id                 // URL parameters /:id
// req.query.page                // Query string ?page=1
// req.body.name                 // Request body (parsed)
// res.status(201).json(data)    // JSON response
// res.redirect('/new-path')     // Redirect
// next(err)                     // Pass to error handler
// next()                        // Pass to next middleware

// ── EVENTS ────────────────────────────────────────────────────────────────
// emitter.on(event, handler)     // Add listener
// emitter.once(event, handler)   // Listen once
// emitter.off(event, handler)    // Remove listener
// emitter.emit(event, ...args)   // Fire event
// emitter.listeners(event)       // Get all listeners
// await once(emitter, 'ready')   // Promise for single event
// for await (const [data] of on(emitter, 'data')) { }  // AsyncIterator

// ── STREAMS ───────────────────────────────────────────────────────────────
// createReadStream(path, { highWaterMark: 64*1024 })
// createWriteStream(path)
// new Transform({ transform(chunk, encoding, cb) { this.push(transformed); cb(); } })
// await pipeline(readable, ...transforms, writable)  // ALWAYS use pipeline!
// for await (const chunk of readable) { }            // Async iteration

// ── WORKER THREADS ────────────────────────────────────────────────────────
// if (!isMainThread) { parentPort.postMessage(result); }
// const w = new Worker('./worker.js', { workerData: { n: 42 } });
// w.on('message', handler); w.on('error', handler);

// ── CHILD PROCESS ─────────────────────────────────────────────────────────
// const { stdout } = await execAsync('git status')
// const child = spawn('node', ['--version']);
// child.stdout.pipe(process.stdout);

// ── CRYPTO ────────────────────────────────────────────────────────────────
import { randomUUID, randomBytes, createHash, createHmac, scrypt, timingSafeEqual } from 'node:crypto';
// randomUUID()                              // UUID v4
// randomBytes(32).toString('hex')           // 64-char hex token
// createHash('sha256').update(data).digest('hex')  // Hash
// createHmac('sha256', secret).update(data).digest('hex')  // HMAC
// await scrypt(password, salt, 64)          // Password hashing (KDF)
// timingSafeEqual(a, b)                     // Timing-safe comparison

// ── COMMON PATTERNS ───────────────────────────────────────────────────────
// Async wrapper for Express:
const wrap = fn => (req, res, next) => Promise.resolve(fn(req, res, next)).catch(next);

// Rate limit check with Redis:
const { allowed } = await rateLimit(`user:${userId}`, 100, 60);
if (!allowed) return res.status(429).json({ error: 'Rate limit exceeded' });

// Request context:
const requestId = req.headers['x-request-id'] ?? randomUUID();
res.setHeader('X-Request-ID', requestId);

// Graceful shutdown:
process.on('SIGTERM', async () => {
    server.close(async () => { await cleanup(); process.exit(0); });
    setTimeout(() => process.exit(1), 30_000).unref();
});
```

---

### What's Next?

After mastering Node.js deeply, your natural paths:

- 📘 **TypeScript** — Type-safe Node.js — the industry standard for serious projects
- 📘 **Fastify** — 2-3× faster than Express, schema-first, excellent plugin system
- 📘 **NestJS** — Angular-inspired enterprise Node.js framework with DI
- 📘 **Next.js / Remix** — Full-stack React with Node.js server rendering
- 📘 **Prisma / DrizzleORM** — Type-safe database access for Node.js
- 📘 **Bun** — Fast Node.js-compatible runtime with built-in SQLite and bundler
- 📘 **Deno** — Secure by default, TypeScript built-in, WinterCG compliant

---

> 💬 *"Node.js is a platform built on Chrome's JavaScript runtime for easily building fast and scalable network applications."*
> — Original Node.js description, Ryan Dahl (2009)

> 💬 *"You can never understand everything. But you should push yourself to understand the system."*
> — Ryan Dahl, on building Node.js

> 💬 *"JavaScript is the only language that I'm aware of that people feel they don't need to learn before they start using it."*
> — Douglas Crockford ... but once you truly learn it, Node.js is extraordinary.

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: Node.js — Complete Runtime Mastery | Version: 1.0*
*Sections: 13 | Level: Beginner → 0.01% Elite*
