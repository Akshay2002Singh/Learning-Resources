# JavaScript Data Structures Cheatsheet ⚡

## 1. Array (`Array`)
*Dynamic list (serves as Vector, Stack, Queue, and Deque).*

**Initialization:**
```javascript
const arr = [];                    // Empty array
const arr = [1, 2, 3];             // With elements
const arr = new Array(5).fill(0);  // 5 elements, all 0
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `push(v)` | Add to end (Stack push) | O(1) | `arr.push(10);` |
| `pop()` | Remove from end (Stack pop) | O(1) | `arr.pop();` |
| `shift()` | Remove from front (Queue/Deque) | O(N) | `arr.shift();` |
| `unshift(v)` | Add to front (Deque) | O(N) | `arr.unshift(5);` |
| `slice(s, e)` | Get sub-array (shallow copy) | O(K) | `arr.slice(1, 4);` |
| `splice(i, c, ...v)`| Delete/Insert at index | O(N) | `arr.splice(1, 2, 'a');` |
| `length` | Property (count) | O(1) | `arr.length;` |
| `indexOf(v)` | Find index of value | O(N) | `arr.indexOf(10);` |

---

## 2. Map (`Map`)
*Key-Value pairs (Heads remains in insertion order).*

**Initialization:**
```javascript
const map = new Map();
const map = new Map([['a', 1], ['b', 2]]);
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `set(k, v)` | Insert or update | O(1) | `map.set('id', 1);` |
| `get(k)` | Access by key | O(1) | `map.get('id');` |
| `has(k)` | Check existence | O(1) | `if (map.has('id'))` |
| `delete(k)` | Remove key-value pair | O(1) | `map.delete('id');` |
| `size` | Property (count) | O(1) | `map.size;` |
| `clear()` | Remove all | O(N) | `map.clear();` |

---

## 3. Set (`Set`)
*Unique values.*

**Initialization:**
```javascript
const set = new Set();
const set = new Set([1, 2, 3]);
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `add(v)` | Add unique value | O(1) | `set.add(5);` |
| `has(v)` | Check existence | O(1) | `if (set.has(5))` |
| `delete(v)` | Remove value | O(1) | `set.delete(5);` |
| `size` | Property (count) | O(1) | `set.size;` |

---

## 4. Object (`Object`)
*Standard keyed collection (Hash Table).*

**Initialization:**
```javascript
const obj = {};
const obj = { a: 1, b: 2 };
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `obj[k] = v` | Insert or update | O(1) | `obj['key'] = 100;` |
| `Object.keys(o)`| Array of keys | O(N) | `Object.keys(obj);` |
| `Object.values(o)`| Array of values | O(N) | `Object.values(obj);` |
| `Object.entries(o)`| Array of [k, v] | O(N) | `Object.entries(obj);` |

---

## 5. Functional Array Methods (High Order)

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `forEach(cb)` | Iterate through elements | O(N) | `arr.forEach(x => ...)` |
| `map(cb)` | Transform elements (new arr) | O(N) | `arr.map(x => x * 2);` |
| `filter(cb)` | Filter elements (new arr) | O(N) | `arr.filter(x => x > 0);` |
| `reduce(cb, init)`| Accumulate/Total | O(N) | `arr.reduce((s, x) => s + x, 0);` |
| `sort(cb)` | In-place sort | O(N log N) | `arr.sort((a, b) => a - b);` |
| `reverse()` | In-place reverse | O(N) | `arr.reverse();`|

---

## 6. String Methods

| Function | Description | Example |
| :--- | :--- | :--- |
| `charAt(i)` | Character at index | `'abc'.charAt(0) // 'a'` |
| `substring(s, e)`| Slice string | `'hello'.substring(0, 2)` |
| `split(delim)` | String to Array | `'a,b'.split(',')` |
| `trim()` | Remove whitespace | `'  hi '.trim()` |
| `toLowerCase()` | Case conversion | `'A'.toLowerCase()` |
| `includes(v)` | Check if contains | `str.includes('abc')` |

---

## 7. Math & Type Conversions

| Function | Description | Example |
| :--- | :--- | :--- |
| `Number(s)` | String to Number | `Number("123")` |
| `parseInt(s, 10)`| String to Int | `parseInt("12.5") // 12` |
| `String(n)` | Number to String | `String(123)` |
| `Math.abs(x)` | Absolute value | `Math.abs(-5) // 5` |
| `Math.floor(x)` | Round down | `Math.floor(5.9) // 5` |
| `Math.ceil(x)` | Round up | `Math.ceil(5.1) // 6` |
| `Math.max(...v)` | Get max | `Math.max(1, 5, 2) // 5` |
| `BigInt(v)` | Handle large integers | `BigInt(Number.MAX_SAFE_INTEGER) + 1n` |

---

## 8. Detailed Explanations

### 1. `slice()` vs `splice()` (Most Confusing)
- **`slice(start, end)`**:
    - **Purpose**: "Slices" out a piece of the array.
    - **Behavior**: Does **NOT** change the original array.
    - **Returns**: A new array.
    - **Range**: From `start` (inclusive) up to `end` (**exclusive**).
- **`splice(start, deleteCount, item1, item2...)`**:
    - **Purpose**: "Splices" (cuts/wires) the array.
    - **Behavior**: **Does change** the original array.
    - **Returns**: An array of the elements that were removed.
    - **Parameters**:
        - `start`: The index where you want to start changing the array.
        - `deleteCount`: How many elements to remove (use `0` if you only want to insert).
        - `item1, item2...`: New elements you want to add into the array at that `start` position.
    - **Use Cases**:
        - **Delete**: `arr.splice(2, 1);` (Delete 1 element at index 2)
        - **Insert**: `arr.splice(2, 0, 'new');` (Insert 'new' at index 2 without deleting)
        - **Replace**: `arr.splice(2, 1, 'new');` (Replace element at index 2 with 'new')

### 2. `substring(start, end)` 
- Similar to `slice()` but specifically for **Strings**.
- It returns a part of the string between `start` and `end` (not including `end`).
- **Difference from slice**: If `start` is greater than `end`, `substring` will swap them, while `slice` will return an empty string.

### 3. Understanding `BigInt` and `1n`
- **Why?**: Standard JavaScript numbers lose precision after $2^{53}-1$ (`Number.MAX_SAFE_INTEGER`). For DSA problems involving very large numbers (like factorials), you must use `BigInt`.
- **The `n` suffix**: Adding `n` to the end of a number (like `10n` or `1n`) explicitly tells JavaScript "This is a BigInt type, not a regular Number".
- **Rule**: You **cannot mix** `BigInt` and regular numbers. 
    - ❌ `10n + 1` (Error)
    - ✅ `10n + 1n` (Works)
    - ✅ `10n + BigInt(1)` (Works)