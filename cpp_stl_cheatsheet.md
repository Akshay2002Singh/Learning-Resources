# C++ STL Cheatsheet 🚀

## 1. Vector (`std::vector`)
*Dynamic array.*

**Initialization:**
```cpp
vector<int> v;                   // Empty vector
vector<int> v = {1, 2, 3};       // With elements
vector<int> v(5, 10);            // 5 elements, all with value 10
vector<int> v2(v);               // Copy of another vector
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `push_back(v)` | Add element to end | O(1) | `v.push_back(10);` |
| `pop_back()` | Remove last element | O(1) | `v.pop_back();` |
| `insert(it, v)`| Insert at position | O(N) | `v.insert(v.begin() + 1, 5);` |
| `erase(it)` | Remove at position | O(N) | `v.erase(v.begin() + 1);` |
| `size()` | Number of elements | O(1) | `v.size();` |
| `at(i)` / `v[i]`| Access element | O(1) | `int x = v.at(0);` |
| `empty()` | Check if empty | O(1) | `v.empty();` |
| `clear()` | Remove all elements | O(N) | `v.clear();` |

---

## 2. Stack (`std::stack`)
*LIFO (Last-In First-Out) container.*

**Initialization:**
```cpp
stack<int> st;
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `push(v)` | Add to top | O(1) | `st.push(1);` |
| `pop()` | Remove top element | O(1) | `st.pop();` |
| `top()` | Access top element | O(1) | `st.top();` |
| `size()` | Number of elements | O(1) | `st.size();` |
| `empty()` | Check if empty | O(1) | `st.empty();` |

---

## 3. Queue (`std::queue`)
*FIFO (First-In First-Out) container.*

**Initialization:**
```cpp
queue<int> q;
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `push(v)` | Add to back | O(1) | `q.push(1);` |
| `pop()` | Remove from front | O(1) | `q.pop();` |
| `front()` | Access front element | O(1) | `q.front();` |
| `back()` | Access last element | O(1) | `q.back();` |
| `size()` | Number of elements | O(1) | `q.size();` |
| `empty()` | Check if empty | O(1) | `q.empty();` |

---

## 4. Priority Queue (`std::priority_queue`)
*Heap data structure.*

**Initialization:**
```cpp
priority_queue<int> pq;                                    // Max-heap (Default)
priority_queue<int, vector<int>, greater<int>> min_pq;     // Min-heap
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `push(v)` | Insert element | O(log N) | `pq.push(10);` |
| `pop()` | Remove top element | O(log N) | `pq.pop();` |
| `top()` | Access top element | O(1) | `pq.top();` |
| `size()` | Number of elements | O(1) | `pq.size();` |
| `empty()` | Check if empty | O(1) | `pq.empty();` |

---

## 5. Deque (`std::deque`)
*Double-ended queue.*

**Initialization:**
```cpp
deque<int> dq;
deque<int> dq = {1, 2, 3};
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `push_back(v)` | Add to back | O(1) | `dq.push_back(1);` |
| `push_front(v)`| Add to front | O(1) | `dq.push_front(2);` |
| `pop_back()` | Remove from back | O(1) | `dq.pop_back();` |
| `pop_front()` | Remove from front | O(1) | `dq.pop_front();` |
| `front()` | Access first element | O(1) | `dq.front();` |
| `back()` | Access last element | O(1) | `dq.back();` |
| `size()` | Number of elements | O(1) | `dq.size();` |
| `empty()` | Check if empty | O(1) | `dq.empty();` |

---

## 6. List (`std::list`)
*Doubly linked list.*

**Initialization:**
```cpp
list<int> li;
list<int> li = {1, 2, 3};
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `push_back(v)` | Add to back | O(1) | `li.push_back(1);` |
| `push_front(v)`| Add to front | O(1) | `li.push_front(2);` |
| `pop_back()` | Remove from back | O(1) | `li.pop_back();` |
| `pop_front()` | Remove from front | O(1) | `li.pop_front();` |
| `insert(it, v)`| Insert at position | O(1) | `li.insert(it, 5);` |
| `erase(it)` | Delete node | O(1) | `li.erase(it);` |
| `front()` | Access first element | O(1) | `li.front();` |
| `back()` | Access last element | O(1) | `li.back();` |
| `size()` | Number of elements | O(1) | `li.size();` |
| `empty()` | Check if empty | O(1) | `li.empty();` |
| `clear()` | Remove all elements | O(N) | `li.clear();` |

**How to Iterate:**
```cpp
for (auto it = li.begin(); it != li.end(); ++it) {
    cout << *it << " ";
}
```

---

## 7. Map (`std::map`)
*Key-Value pairs (Sorted by Key).*

**Initialization:**
```cpp
map<string, int> m;
map<string, int> m = {{"a", 1}, {"b", 2}};
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `m[key] = v` | Insert/Update | O(log N) | `m["id"] = 1;` |
| `find(key)` | Search by key | O(log N) | `auto it = m.find("id");` |
| `erase(key)` | Remove by key | O(log N) | `m.erase("id");` |
| `count(key)` | Check existence | O(log N) | `if(m.count("id"))` |
| `size()` | Number of pairs | O(1) | `m.size();` |
| `clear()` | Remove all | O(N) | `m.clear();` |

---

## 8. Unordered Map (`std::unordered_map`)
*Key-Value pairs (Hash Table).*

**Initialization:**
```cpp
unordered_map<string, int> um;
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `m[key] = v` | Insert/Update | O(1) avg | `um["id"] = 1;` |
| `find(key)` | Search by key | O(1) avg | `um.find("id");` |
| `erase(key)` | Remove by key | O(1) avg | `um.erase("id");` |
| `size()` | Number of pairs | O(1) | `um.size();` |

---

## 9. Set (`std::set`)
*Unique values (Sorted).*

**Initialization:**
```cpp
set<int> s;
set<int> s = {1, 2, 3};
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `insert(v)` | Add value | O(log N) | `s.insert(5);` |
| `find(v)` | Search value | O(log N) | `auto it = s.find(5);` |
| `erase(v)` | Remove value | O(log N) | `s.erase(5);` |
| `count(v)` | Check existence | O(log N) | `if(s.count(5))` |
| `size()` | Number of elements | O(1) | `s.size();` |

---

## 10. Unordered Set (`std::unordered_set`)
*Unique values (Hash Table).*

**Initialization:**
```cpp
unordered_set<int> us;
```

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `insert(v)` | Add value | O(1) avg | `us.insert(5);` |
| `find(v)` | Search value | O(1) avg | `us.find(5);` |
| `count(v)` | Check existence | O(1) avg | `if(us.count(5))` |
| `size()` | Number of elements | O(1) | `us.size();` |

---

## 11. DSA Algorithms (`#include <algorithm>`)

| Function | Description | Complexity | Example |
| :--- | :--- | :--- | :--- |
| `sort(a, b)` | Sort range | O(N log N) | `sort(v.begin(), v.end());` |
| `reverse(a, b)`| Reverse range | O(N) | `reverse(v.begin(), v.end());` |
| `max_element()`| Max value ptr | O(N) | `*max_element(v.begin(), v.end());` |
| `binary_search()`| Search (Sorted) | O(log N) | `binary_search(v.begin(), v.end(), 5);` |
| `lower_bound()`| Iterator to >= v| O(log N) | `lower_bound(v.begin(), v.end(), 5);` |
| `upper_bound()`| Iterator to > v | O(log N) | `upper_bound(v.begin(), v.end(), 5);` |

---

## 12. String and Type Conversions

| Function | Description | Example |
| :--- | :--- | :--- |
| `to_string(n)` | Number to String | `string s = to_string(10);` |
| `stoi(s)` | String to Int | `int n = stoi("123");` |
| `stoll(s)` | String to Long Long | `long long n = stoll("123");` |
| `s.substr(p, l)`| Substring | `s.substr(0, 5);` |
| `getline(cin, s)`| Read line | `getline(cin, s);` |
| `INT_MAX/MIN` | Limits | `#include <climits>` |

---

---

---

## 13. Advanced Patterns

### 1. Sorting Vector of Pairs
By default, `std::sort` on pairs sorts by the **first** value.
```cpp
vector<pair<int, int>> v = {{10, 5}, {2, 8}, {10, 2}};

// 1. Default Sort (Sorts by First, then Second)
sort(v.begin(), v.end()); 
// Result: {2,8}, {10,2}, {10,5}

// 2. Custom Sort (Sort by Second value only)
sort(v.begin(), v.end(), [](auto a, auto b) {
    return a.second < b.second; 
});
```

### 2. Priority Queue with Pairs
```cpp
// Max-Heap of Pairs (Top is largest .first)
priority_queue<pair<int, int>> pq;

// Min-Heap of Pairs (Top is smallest .first)
priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> min_pq;
```

### 3. Sorting Vector of Structs
```cpp
struct Student {
    int roll;
    int marks;
};

// Sort by marks in descending order (highest first)
sort(v.begin(), v.end(), [](Student a, Student b) {
    return a.marks > b.marks; 
});
```

### 4. Custom Priority Queue (Top marks first)
```cpp
struct CompareMarks {
    bool operator()(Student a, Student b) {
        return a.marks < b.marks; // '<' makes it a MAX-heap (Top is highest)
    }
};

priority_queue<Student, vector<Student>, CompareMarks> pq;
```

### 5. STL `list` with Custom Struct
```cpp
struct Item {
    int id;
    int weight;
};

list<Item> myItems;

// 1. Push (Add)
myItems.push_back({1, 50}); 
myItems.push_front({2, 30});

// 2. Pop (Remove)
myItems.pop_back();
myItems.pop_front();

// 3. Insert at position
auto it = myItems.begin();
myItems.insert(it, {3, 100}); 
```

---
