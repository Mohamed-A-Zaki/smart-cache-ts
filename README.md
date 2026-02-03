# Smart Cache

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![npm version](https://img.shields.io/badge/npm-v1.0.0-blue)](https://www.npmjs.com/package/smart-cache)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)

A lightweight, zero-dependency TypeScript utility for caching data with TTL (Time To Live) support. This package provides
a simple and type-safe API for storing and retrieving data in localStorage with automatic expiration handling.

## Features

- 💾 Store any type of data with localStorage
- ⏰ Built-in TTL (Time To Live) support
- 🔄 Automatic expiration handling
- 🛠️ Built-in TypeScript support
- 🚫 Zero dependencies
- 📦 Small bundle size
- 🔍 Type-safe API

## Installation

### Using npm

```bash
npm install smart-cache
```

### Using Yarn

```bash
yarn add smart-cache
```

### Using pnpm

```bash
pnpm add smart-cache
```

> **Framework Agnostic**
> This package is designed to work seamlessly with any JavaScript framework including React, Vue, Angular, Svelte, and
> more. It has no framework dependencies and can be used in any JavaScript or TypeScript project.

## Usage

### Basic Cache Operations

```typescript
import { cache } from "smart-cache";

// Store data in cache
cache.set("user", { name: "John", age: 30 });

// Retrieve data from cache
const user = cache.get("user");
// Returns: { name: 'John', age: 30 }

// Check if key exists
const hasUser = cache.has("user");
// Returns: true
```

### Cache with TTL (Time To Live)

```typescript
import { cache } from "smart-cache";

// Store data with expiration (5 seconds)
cache.set("session", { token: "abc123" }, { ttl: 5000 });

// Retrieve before expiration
const session = cache.get("session");
// Returns: { token: 'abc123' }

// Wait 5+ seconds, then retrieve
const expiredSession = cache.get("session");
// Returns: null (automatically removed)
```

### Cache Management

```typescript
import { cache } from "smart-cache";

// Remove specific item
cache.remove("user");

// Clear all cache
cache.clear();

// Store different data types
cache.set("number", 42);
cache.set("string", "hello world");
cache.set("array", [1, 2, 3]);
cache.set("boolean", true);
```

## TypeScript Support

This package is written in TypeScript and includes type definitions out of the box.

## License

MIT © [Mohamed Zaki](https://github.com/Mohamed-A-Zaki)
