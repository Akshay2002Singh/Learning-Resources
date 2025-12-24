# Python Cheatsheet 🐍

## 1. Basic Syntax

### I/O & Variables
```python
name = input("Enter name: ")    # Read string
age = int(input("Enter age: ")) # Read & convert to int
print(f"Hello {name}")          # F-string formatting
```

### Conditionals
```python
if score >= 90:
    print("A")
elif score >= 80:
    print("B")
else:
    print("C")
```

### Loops
```python
# For loop (0 to 4)
for i in range(5):
    print(i)

# For loop with step (10 down to 2)
for i in range(10, 0, -2):
    print(i)

# While loop
while count > 0:
    count -= 1
```

### Functions
```python
def my_function(param1, param2=10):
    result = param1 + param2
    return result
```

---

## 2. String (`str`)
*Immutable sequence of characters.*

**Initialization:**
```python
s = "Hello World"
s = 'Single quotes work too'
```

| Function | Description | Example |
| :--- | :--- | :--- |
| `s[i]` | Character at index | `'abc'[0] # 'a'` |
| `s[start:end]` | Substring (Slicing) | `'hello'[0:2] # 'he'` |
| `s.split(d)` | String to List | `'a,b'.split(',') # ['a','b']` |
| `"".join(list)`| List to String | `"-".join(['a','b']) # 'a-b'` |
| `s.strip()` | Remove whitespace | `'  hi '.strip() # 'hi'` |
| `s.lower()` | Case conversion | `'A'.lower() # 'a'` |
| `len(s)` | Length of string | `len("abc") # 3` |

---

## 3. List (`list`)
*Dynamic array (Mutable).*

**Initialization:**
```python
arr = []                        # Empty list
arr = [1, 2, 3]                 # With elements
arr = [0] * 5                   # 5 elements, all 0
arr = [x for x in range(5)]     # List comprehension
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `append(v)` | Add to end | O(1) | `arr.append(10)` |
| `pop()` | Remove from end | O(1) | `arr.pop()` |
| `pop(i)` | Remove at index | O(N) | `arr.pop(0)` |
| `insert(i, v)` | Insert at index | O(N) | `arr.insert(1, 5)` |
| `len(arr)` | Number of elements | O(1) | `len(arr)` |
| `arr[i]` | Access at index | O(1) | `x = arr[0]` |
| `arr[s:e]` | Slicing (sub-list) | O(K) | `arr[1:4]` |
| `sort()` | In-place sort | O(N log N) | `arr.sort()` |

---

## 4. Tuple (`tuple`)
*Immutable sequence (cannot be changed after creation).*

**Initialization:**
```python
t = (1, 2, 3)
t = 1, 2, 3                     # Parentheses are optional
single_t = (5,)                 # Note the trailing comma for single element
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `t[i]` | Access at index | O(1) | `x = t[0]` |
| `len(t)` | Number of elements | O(1) | `len(t)` |
| `count(v)` | Count occurrences | O(N) | `t.count(1)` |
| `index(v)` | Find first index | O(N) | `t.index(2)` |

---

## 5. Dictionary (`dict`)
*Key-Value pairs (Hash Table).*

**Initialization:**
```python
d = {}
d = {"a": 1, "b": 2}
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `d[k] = v` | Insert or update | O(1) | `d["id"] = 1` |
| `d.get(k, def)`| Access with default | O(1) | `d.get("id", 0)` |
| `k in d` | Check existence | O(1) | `if "id" in d:` |
| `del d[k]` | Remove key | O(1) | `del d["id"]` |
| `len(d)` | Number of pairs | O(1) | `len(d)` |
| `d.keys()` | Get all keys | O(1) | `d.keys()` |
| `d.items()` | Get all [k, v] pairs | O(1) | `d.items()` |

---

## 6. Set (`set`)
*Unique values (Mutable).*

**Initialization:**
```python
s = set()                       # Empty set (must use set(), {} is a dict)
s = {1, 2, 3}
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `add(v)` | Add unique value | O(1) | `s.add(5)` |
| `remove(v)` | Remove value (Error if missing)| O(1) | `s.remove(5)` |
| `discard(v)` | Remove (No error if missing)| O(1) | `s.discard(5)` |
| `v in s` | Check existence | O(1) | `if 5 in s:` |
| `len(s)` | Number of elements | O(1) | `len(s)` |
| `s1 \| s2` | Union (OR) | O(N+M) | `s1 \| s2` |
| `s1 & s2` | Intersection (AND) | O(min(N, M))| `s1 & s2` |

---

## 7. Math & Type Conversions

| Function | Description | Example |
| :--- | :--- | :--- |
| `int(s)` | String/Float to Int | `int("123")` |
| `str(n)` | Number to String | `str(123)` |
| `list(s)` | String/Tuple to List | `list("abc") # ['a','b','c']` |
| `abs(x)` | Absolute value | `abs(-5)` |
| `max(a, b)` | Get maximum | `max(10, 20)` |
| `min(a, b)` | Get minimum | `min(10, 20)` |
| `sum(list)` | Sum of all elements | `sum([1,2,3]) # 6` |
