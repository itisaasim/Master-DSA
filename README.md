# Master DSA

## 🧠 Master DSA Relearning Roadmap

### 🔹 Part 1: Foundations

1. **Time and Space Complexity**
2. **Big-O, Big-Ω, Big-Θ Notations**
3. **Recursion & Recursion Trees**
4. **Memoization & Dynamic Programming Basics**

---

### 🔹 Part 2: Core Data Structures

1. **Arrays**
2. **Strings**
3. **Linked Lists**
    - Singly, Doubly, Circular
4. **Stacks and Queues**
    - Queue, Deque, Priority Queue
5. **Hash Tables / Hash Maps / Sets**
6. **Trees**
    - Binary Trees
    - Binary Search Trees
    - AVL / Red-Black Trees (optional)
7. **Heaps (Min/Max Heap)**
8. **Tries**
9. **Graphs**
    - Representation (Adjacency List/Matrix)
    - Directed/Undirected, Weighted/Unweighted
10. **Disjoint Sets (Union-Find)**

---

### 🔹 Part 3: Essential Algorithms

1. **Searching Algorithms**
    - Linear Search
    - Binary Search
2. **Sorting Algorithms**
    - Bubble, Selection, Insertion
    - Merge Sort
    - Quick Sort
    - Heap Sort
    - Counting / Radix Sort
3. **Backtracking**
    - N-Queens
    - Subsets / Permutations
4. **Greedy Algorithms**
    - Activity Selection
    - Huffman Coding
5. **Divide and Conquer**
    - Merge Sort, Quick Sort, etc.

---

### 🔹 Part 4: Graph Algorithms

1. **DFS & BFS**
2. **Topological Sort**
3. **Dijkstra’s Algorithm**
4. **Bellman-Ford Algorithm**
5. **Floyd-Warshall Algorithm**
6. **Minimum Spanning Trees (Prim’s, Kruskal’s)**
7. **Cycle Detection (Union-Find / DFS)**

---

### 🔹 Part 5: Dynamic Programming (DP)

1. **0/1 Knapsack**
2. **Unbounded Knapsack**
3. **Longest Common Subsequence (LCS)**
4. **Longest Increasing Subsequence (LIS)**
5. **Matrix Chain Multiplication**
6. **Coin Change**
7. **Fibonacci Variants**
8. **DP on Trees / Graphs**

---

### 🔹 Part 6: Problem-Solving Patterns

1. **Sliding Window**
2. **Two Pointers**
3. **Fast & Slow Pointers (Floyd’s Cycle)**
4. **Binary Search on Answer**
5. **Greedy + Sorting**
6. **Prefix Sum / Difference Arrays**
7. **Bit Manipulation Patterns**

---

### 🔹 Part 7: Advanced Concepts (Optional)

1. **Segment Trees / Fenwick Trees (BIT)**
2. **KMP / Rabin-Karp (Pattern Matching)**
3. **Suffix Arrays / Tries**
4. **Mo’s Algorithm**
5. **Heavy-Light Decomposition**

---

### 🔹 Part 8: Interview-Focused Topics

1. **System Design Foundations (for DSA cross-over)**
2. **Top 100 Leetcode Patterns**
3. **Mock Interviews & Problem Solving Practice**
4. **Real-world Use Cases of DSA in Engineering**

## 🧠 1. Time and Space Complexity

### 📖 Definition

**Time Complexity** refers to the computational complexity that describes the amount of time it takes to run an algorithm as a function of the input size.

**Space Complexity** refers to the amount of memory space required by an algorithm in its life cycle.

---

### 🔧 Syntax / Pseudocode

There’s no formal syntax, but we use **Big-O notation** to express growth:

| Notation | Name | Example Use Case |
| --- | --- | --- |
| O(1) | Constant Time | Accessing an array element |
| O(n) | Linear Time | Looping through an array |
| O(log n) | Logarithmic Time | Binary Search |
| O(n²) | Quadratic Time | Nested loops on array |
| O(2ⁿ) | Exponential Time | Solving the Tower of Hanoi |

---

### 💻 Example (JavaScript)

```
js
CopyEdit
// O(1): Constant time
function getFirstItem(arr) {
  return arr[0];
}

// O(n): Linear time
function printAllItems(arr) {
  for (let item of arr) {
    console.log(item);
  }
}

// O(n^2): Quadratic time
function printAllPairs(arr) {
  for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < arr.length; j++) {
      console.log(arr[i], arr[j]);
    }
  }
}

```

---

### ✅ What to Do With It

- Use **Big-O** to evaluate and compare the scalability of algorithms.
- Always **optimize for the worst-case** unless told otherwise.
- Aim for algorithms with **lower time and space complexity** where possible.
- When optimizing, consider **amortized time** (e.g., for array resizing).

---

### 🚫 What Not to Do With It

- Don’t assume an algorithm is efficient just because it looks fast for small inputs.
- Don’t ignore **space complexity**—especially with recursion or large data.
- Don’t confuse **Big-O** (worst case) with **Big-Ω** (best case).

---

### 📚 If You Want to Learn More

- **Grokking Algorithms** – Chapter 2: *Big O Notation*
- **Introduction to Algorithms (CLRS)** – Chapter 3: *Growth of Functions*
- **Algorithms by Robert Sedgewick** – Section 1.4: *Analysis of Algorithms*

## 📊 2. Big-O, Big-Ω, and Big-Θ Notations

### 📖 Definition

These notations are used to describe the **asymptotic behavior** of algorithms:

- **Big-O (O)**: Describes the **worst-case** time or space complexity.
- **Big-Ω (Ω)**: Describes the **best-case** time or space complexity.
- **Big-Θ (Θ)**: Describes the **average or tight bound**, i.e., both best and worst-case bounds.

---

### 🔧 Syntax / Conceptual Format

There’s no executable syntax—these are mathematical notations used to describe algorithm efficiency.

| Notation | Meaning | Example |
| --- | --- | --- |
| O(n) | At most n steps | Linear search in worst case |
| Ω(1) | At least constant steps | Best case: finding element at index 0 |
| Θ(n) | Exactly linear | Every case needs n steps |

---

### 💻 Example (JavaScript)

```
js
CopyEdit
function linearSearch(arr, target) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === target) return i;
  }
  return -1;
}

// Big-O: O(n) - Worst case (target not found)
// Big-Ω: Ω(1) - Best case (target is at the first index)
// Big-Θ: Θ(n) - On average, we look at half the array

```

```
js
CopyEdit
function binarySearch(arr, target) {
  let left = 0, right = arr.length - 1;
  while (left <= right) {
    let mid = Math.floor((left + right) / 2);
    if (arr[mid] === target) return mid;
    else if (arr[mid] < target) left = mid + 1;
    else right = mid - 1;
  }
  return -1;
}

// Big-O: O(log n) - Worst case
// Big-Ω: Ω(1) - Best case (mid is the target)
// Big-Θ: Θ(log n) - Average case for most distributions

```

---

### ✅ What to Do With It

- Use **Big-O** to describe scalability (especially for interviews).
- Understand **Big-Ω** when designing best-case optimizations.
- Use **Big-Θ** to estimate average-case behavior, if known.
- Always check whether your algorithm's time complexity changes with input patterns.

---

### 🚫 What Not to Do With It

- Don’t assume Big-O tells you everything — it's the **upper bound**, not average performance.
- Don’t quote best-case (Ω) complexity when worst-case (O) matters more (e.g., in interviews).
- Don’t confuse Θ with O — they have **different guarantees**.

---

### 📚 If You Want to Learn More

- **Introduction to Algorithms (CLRS)** – Chapter 3: *Growth of Functions*
- **Algorithms by Robert Sedgewick** – Section 1.4: *Analysis of Algorithms*
- **Grokking Algorithms** – Chapter 2: *Big O Notation*

## 🔁 Recursion & Recursion Trees

### 📖 Definition

**Recursion** is a technique where a function calls itself to solve a smaller instance of the same problem, usually with a **base case** to stop the calls.

A **Recursion Tree** is a visual representation of recursive calls, showing how the problem breaks down into subproblems and how time complexity accumulates at each level.

---

### 🔧 Syntax / Pseudocode

```
js
CopyEdit
function recurse(params) {
  if (base_case_condition) {
    return base_case_value;
  }

  // smaller problem
  return recurse(smaller_params);
}

```

🔁 Example – Factorial:

```
js
CopyEdit
function factorial(n) {
  if (n === 0) return 1; // base case
  return n * factorial(n - 1); // recursive case
}

```

🔁 Example – Fibonacci:

```
js
CopyEdit
function fib(n) {
  if (n <= 1) return n;
  return fib(n - 1) + fib(n - 2);
}

```

---

### 🌳 Recursion Tree Example: Fibonacci

Visualizing `fib(4)`:

```
markdown
CopyEdit
               fib(4)
              /      \
         fib(3)       fib(2)
        /     \       /     \
    fib(2)  fib(1)  fib(1)  fib(0)
   /     \
fib(1)  fib(0)

```

➡️ **Work per level:**

- Level 0: 1 call → `fib(4)`
- Level 1: 2 calls → `fib(3), fib(2)`
- Level 2: 4 calls → `fib(2), fib(1), fib(1), fib(0)`
- Level 3: 3 calls → `fib(1), fib(0), fib(0)`

Total calls ≈ `2^n` → **Time Complexity: O(2ⁿ)**

---

### ✅ What to Do With It

- Always define a **base case** clearly.
- Use recursion when:
    - The problem is naturally recursive (e.g., trees, divide-and-conquer).
    - You can divide the problem into smaller identical subproblems.
- Use **memoization** or **dynamic programming** to optimize overlapping subproblems (like in Fibonacci).

---

### 🚫 What Not to Do With It

- Don’t forget the base case — this causes infinite recursion and a **stack overflow**.
- Don’t use recursion when iteration is simpler and more efficient (e.g., linear search).
- Don’t overuse recursion in JavaScript — it has a limited call stack depth (~10,000 recursive calls in most environments).
- Avoid unoptimized recursive calls in performance-critical code.

---

### 📚 If You Want to Learn More

- **Grokking Algorithms** – Chapter 3: *Recursion*
- **Introduction to Algorithms (CLRS)** – Chapter 4.1–4.5: *Recurrences & Recursion Trees*
- **Algorithms by Robert Sedgewick** – Section 2.3: *Divide-and-Conquer Recursion*

## 🧠 Memoization & Dynamic Programming (DP)

### 📖 Definition

- **Memoization** is a **top-down** optimization technique that caches the results of expensive function calls and returns the cached result when the same inputs occur again.
- **Dynamic Programming (DP)** is a **bottom-up** approach where we solve complex problems by solving all subproblems and building up the solution iteratively.

Both techniques are used to optimize problems with **overlapping subproblems** and **optimal substructure** (i.e., a problem can be broken down into subproblems which can be reused).

---

### 🔧 Syntax / Pseudocode

📌 **Memoization (Top-Down):**

```
js
CopyEdit
function fib(n, memo = {}) {
  if (n in memo) return memo[n];
  if (n <= 1) return n;

  memo[n] = fib(n - 1, memo) + fib(n - 2, memo);
  return memo[n];
}

```

📌 **Dynamic Programming (Bottom-Up):**

```
js
CopyEdit
function fib(n) {
  if (n <= 1) return n;

  let dp = new Array(n + 1).fill(0);
  dp[1] = 1;

  for (let i = 2; i <= n; i++) {
    dp[i] = dp[i - 1] + dp[i - 2];
  }

  return dp[n];
}

```

---

### 💻 Example – Climbing Stairs

**Problem**: You can climb 1 or 2 steps. How many distinct ways to reach the `n`th step?

📌 Memoization:

```
js
CopyEdit
function climbStairs(n, memo = {}) {
  if (n in memo) return memo[n];
  if (n <= 2) return n;

  memo[n] = climbStairs(n - 1, memo) + climbStairs(n - 2, memo);
  return memo[n];
}

```

📌 Dynamic Programming:

```
js
CopyEdit
function climbStairs(n) {
  if (n <= 2) return n;
  let first = 1, second = 2;

  for (let i = 3; i <= n; i++) {
    let third = first + second;
    first = second;
    second = third;
  }

  return second;
}

```

---

### ✅ What to Do With It

- Use **memoization** when working with **recursive top-down** solutions with overlapping subproblems.
- Use **DP** for bottom-up efficiency and space optimization.
- Apply DP to problems like:
    - Fibonacci
    - Coin Change
    - Longest Common Subsequence
    - Knapsack

---

### 🚫 What Not to Do With It

- Don’t memoize functions with too many parameters without careful planning (it may cause memory bloat).
- Avoid recomputing results in recursion — always check if a subproblem has been solved.
- Don’t ignore base cases — it can break the memoization logic.
- Don’t confuse **greedy algorithms** with **DP** — they solve problems differently.

---

### 📚 If You Want to Learn More

- **Grokking Algorithms** – Chapter 9: *Dynamic Programming*
- **Introduction to Algorithms (CLRS)** – Chapter 15: *Dynamic Programming*
- **Algorithms by Robert Sedgewick** – Section 4.3: *Memoization and Dynamic Programming*

## 📦 Arrays

### 📖 Definition

An **Array** is a linear, indexed data structure that stores elements in contiguous memory locations. Each element can be accessed via its index.

JavaScript arrays are dynamic and can hold mixed data types, but under the hood, they’re optimized for numeric, ordered collections.

---

### 🔧 Syntax / Pseudocode

```
js
CopyEdit
// Declaration
let arr = [1, 2, 3, 4];

// Accessing elements
let first = arr[0]; // 1

// Modifying elements
arr[2] = 99;

// Adding elements
arr.push(5);       // [1, 2, 99, 4, 5]
arr.unshift(0);    // [0, 1, 2, 99, 4, 5]

// Removing elements
arr.pop();         // removes last element
arr.shift();       // removes first element

// Iteration
for (let i = 0; i < arr.length; i++) {
  console.log(arr[i]);
}

```

---

### 💻 Example (JavaScript)

```
js
CopyEdit
let fruits = ["apple", "banana", "mango"];

fruits.push("orange");         // ["apple", "banana", "mango", "orange"]
fruits.splice(1, 1);           // removes "banana" -> ["apple", "mango", "orange"]
console.log(fruits[0]);        // "apple"

for (let fruit of fruits) {
  console.log(fruit);          // prints all fruits
}

```

---

### ✅ What to Do With It

- Use arrays when:
    - You need **ordered** collections.
    - You want **indexed** access.
    - You plan to **iterate frequently**.
- Use `for...of`, `forEach`, or `map()` for clean iteration.
- Prefer `push()` over `unshift()` and `pop()` over `shift()` for better performance (as the latter are O(n)).

---

### 🚫 What Not to Do With It

- Avoid using `delete` on arrays — it leaves holes (`undefined`), use `splice()` instead.
- Avoid treating arrays like associative arrays or objects.
- Don’t rely on sparse arrays; they can break iteration and create confusing behavior.
- Don’t mutate arrays in-place inside loops unless necessary.

---

### 📚 If You Want to Learn More

- **Grokking Algorithms** – Chapter 4: *Quicksort (Arrays as base structure)*
- **Introduction to Algorithms (CLRS)** – Chapter 10.1: *Stacks and Queues (based on arrays)*
- **Algorithms by Robert Sedgewick** – Section 1.3: *Arrays and Iteration*

## 🔤 Strings

### 📖 Definition

A **string** is a sequence of characters, typically used to represent text. Strings are one of the most common and important data types in programming. In JavaScript, strings are immutable, meaning once they are created, their values cannot be changed.

---

### 🔧 Syntax / Pseudocode

```
js
CopyEdit
// Declaration
let str = "Hello, World!";

// Accessing characters
let firstChar = str[0]; // 'H'

// String methods
let length = str.length; // 13
let upperStr = str.toUpperCase(); // "HELLO, WORLD!"
let lowerStr = str.toLowerCase(); // "hello, world!"

// Concatenation
let greeting = "Hello";
let name = "Alice";
let message = greeting + ", " + name; // "Hello, Alice"

// Substring
let substring = str.slice(0, 5); // "Hello"

// Search
let index = str.indexOf("World"); // 7
let includes = str.includes("Hello"); // true

```

---

### 💻 Example – Reversing a String

```
js
CopyEdit
function reverseString(str) {
  let reversed = '';
  for (let i = str.length - 1; i >= 0; i--) {
    reversed += str[i];
  }
  return reversed;
}

reverseString("Hello"); // "olleH"

```

Alternatively, using built-in methods:

```
js
CopyEdit
function reverseString(str) {
  return str.split('').reverse().join('');
}

reverseString("Hello"); // "olleH"

```

---

### ✅ What to Do With It

- Use **string methods** like `slice()`, `substring()`, and `split()` for common string manipulations.
- Use **`indexOf()`** or **`includes()`** to check for the presence of substrings.
- When concatenating multiple strings, consider **template literals** (`${}`) for better readability and performance.
- Remember that strings are immutable. Always treat string manipulations as creating a new string.

```
js
CopyEdit
let result = `Hello, ${name}!`; // Template literal, best for concatenation

```

---

### 🚫 What Not to Do With It

- Don’t use the `+` operator excessively for concatenation in loops, as it can be inefficient. Instead, use **`Array.join()`** or **template literals**.
- Avoid modifying the string directly (strings are immutable). Always create a new string by performing operations and assignments.
- Don’t confuse **`slice()`** with **`substring()`** — while they’re similar, `substring()` doesn’t accept negative indices, whereas `slice()` does.

---

### 📚 If You Want to Learn More

- **Grokking Algorithms** – Chapter 10: *Greedy Algorithms (Strings in compression algorithms)*
- **Introduction to Algorithms (CLRS)** – Chapter 34: *String Matching*
- **Algorithms by Robert Sedgewick** – Section 5.3: *String Searching Algorithms*

## 🔗 Linked Lists – Singly, Doubly, and Circular

### 📖 Definition

A **Linked List** is a sequence of nodes, where each node contains:

1. **Data** – The value stored.
2. **Next** – A reference to the next node in the list.

There are three main types of linked lists:

1. **Singly Linked List (SLL)** – Each node points to the next node and traverses in one direction.
2. **Doubly Linked List (DLL)** – Each node has pointers to both the next and previous nodes, allowing traversal in both directions.
3. **Circular Linked List (CLL)** – Similar to singly or doubly linked lists, but the last node points back to the first node, forming a circle.

---

### 1️⃣ Singly Linked List (SLL)

- **Structure**: Each node has two parts: data and a pointer to the next node.

```
js
CopyEdit
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
  }
}

class SinglyLinkedList {
  constructor() {
    this.head = null;
  }

  // Append new node
  append(data) {
    let newNode = new Node(data);
    if (!this.head) {
      this.head = newNode;
      return;
    }
    let current = this.head;
    while (current.next) {
      current = current.next;
    }
    current.next = newNode;
  }

  // Print list
  print() {
    let current = this.head;
    let result = '';
    while (current) {
      result += current.data + ' -> ';
      current = current.next;
    }
    console.log(result.slice(0, -4)); // Remove last ' -> '
  }
}

```

---

### 2️⃣ Doubly Linked List (DLL)

- **Structure**: Each node contains a **data** part, a pointer to the **next** node, and a pointer to the **previous** node. This allows traversal in both directions.

```
js
CopyEdit
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
    this.prev = null;
  }
}

class DoublyLinkedList {
  constructor() {
    this.head = null;
    this.tail = null;
  }

  // Append new node at the end
  append(data) {
    let newNode = new Node(data);
    if (!this.head) {
      this.head = newNode;
      this.tail = newNode;
      return;
    }
    this.tail.next = newNode;
    newNode.prev = this.tail;
    this.tail = newNode;
  }

  // Print list from head to tail
  print() {
    let current = this.head;
    let result = '';
    while (current) {
      result += current.data + ' <-> ';
      current = current.next;
    }
    console.log(result.slice(0, -4)); // Remove last ' <-> '
  }

  // Print list from tail to head
  printReverse() {
    let current = this.tail;
    let result = '';
    while (current) {
      result += current.data + ' <-> ';
      current = current.prev;
    }
    console.log(result.slice(0, -4)); // Remove last ' <-> '
  }
}

```

---

### 3️⃣ Circular Linked List (CLL)

- **Structure**: The last node’s **next** pointer points to the **head** node, making the list circular.
- **Singly Circular Linked List**: Points only to the next node, with the last node’s **next** pointing to the head.
- **Doubly Circular Linked List**: Each node has pointers to both the next and previous nodes, and the last node’s **next** points to the head, while the head's **prev** points to the last node.

### Singly Circular Linked List Example:

```
js
CopyEdit
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
  }
}

class CircularLinkedList {
  constructor() {
    this.head = null;
  }

  // Append new node
  append(data) {
    let newNode = new Node(data);
    if (!this.head) {
      this.head = newNode;
      newNode.next = this.head;  // Point to itself, circular
      return;
    }
    let current = this.head;
    while (current.next !== this.head) {
      current = current.next;
    }
    current.next = newNode;
    newNode.next = this.head;  // Make the list circular
  }

  // Print list
  print() {
    if (!this.head) return;
    let current = this.head;
    let result = '';
    do {
      result += current.data + ' -> ';
      current = current.next;
    } while (current !== this.head);
    console.log(result.slice(0, -4)); // Remove last ' -> '
  }
}

```

### Doubly Circular Linked List Example:

```
js
CopyEdit
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
    this.prev = null;
  }
}

class DoublyCircularLinkedList {
  constructor() {
    this.head = null;
    this.tail = null;
  }

  // Append new node
  append(data) {
    let newNode = new Node(data);
    if (!this.head) {
      this.head = newNode;
      this.tail = newNode;
      newNode.next = this.head;
      newNode.prev = this.tail;
      return;
    }
    this.tail.next = newNode;
    newNode.prev = this.tail;
    newNode.next = this.head;
    this.head.prev = newNode;
    this.tail = newNode;
  }

  // Print list from head to tail
  print() {
    if (!this.head) return;
    let current = this.head;
    let result = '';
    do {
      result += current.data + ' <-> ';
      current = current.next;
    } while (current !== this.head);
    console.log(result.slice(0, -4)); // Remove last ' <-> '
  }
}

```

---

### ✅ What to Do With It

- **Singly Linked Lists** are good for simple operations like insertion at the head or tail, and when only one-way traversal is needed.
- **Doubly Linked Lists** are useful when you need bidirectional traversal (forward and backward) or when deletion from the middle is frequent.
- **Circular Linked Lists** are useful when you want a loop of nodes or when you need the list to be traversed in a continuous manner (such as in a round-robin scheduler).

---

### 🚫 What Not to Do With It

- Don’t use **Singly Linked Lists** when you need to traverse backwards or delete from the middle without extra effort.
- **Doubly Linked Lists** may consume extra memory due to the additional `prev` pointer. Avoid using them when memory is a concern or when you don’t need backward traversal.
- **Circular Linked Lists** can be tricky to handle due to the circular reference. Avoid it unless you need the circular behavior (e.g., cyclic data structures or continuous looping).

---

### 📚 If You Want to Learn More

- **Grokking Algorithms** – Chapter 5: *Linked Lists*
- **Introduction to Algorithms (CLRS)** – Chapter 10: *Linked Lists*
- **Algorithms by Robert Sedgewick** – Section 2.2: *Linked Lists and Recursion*

## 📚 Stacks & Queues – Queue, Deque, Priority Queue

### 📖 Definition

1. **Stack** – A **LIFO (Last In, First Out)** data structure where the last element added is the first to be removed. Think of it like a stack of plates.
2. **Queue** – A **FIFO (First In, First Out)** data structure where the first element added is the first to be removed, like people waiting in line.
3. **Deque (Double-ended Queue)** – A data structure that allows inserting and deleting elements from both ends, i.e., it supports both **FIFO** and **LIFO** operations.
4. **Priority Queue** – A queue where elements are removed based on priority rather than insertion order. The element with the highest priority is dequeued first.

---

### 1️⃣ Stack

- **Structure**: A stack can be implemented using an array or a linked list. Elements are added and removed from the same end (top).

```
js
CopyEdit
class Stack {
  constructor() {
    this.items = [];
  }

  // Push element onto the stack
  push(element) {
    this.items.push(element);
  }

  // Pop element from the stack
  pop() {
    if (this.isEmpty()) return 'Stack is empty';
    return this.items.pop();
  }

  // Peek at the top element
  peek() {
    if (this.isEmpty()) return 'Stack is empty';
    return this.items[this.items.length - 1];
  }

  // Check if the stack is empty
  isEmpty() {
    return this.items.length === 0;
  }

  // Get stack size
  size() {
    return this.items.length;
  }
}

```

**Example**:

```
js
CopyEdit
const stack = new Stack();
stack.push(10);
stack.push(20);
stack.push(30);

console.log(stack.pop()); // 30
console.log(stack.peek()); // 20

```

---

### 2️⃣ Queue

- **Structure**: A queue follows FIFO order. Elements are added at the **rear** and removed from the **front**. We can implement it with an array or linked list.

```
js
CopyEdit
class Queue {
  constructor() {
    this.items = [];
  }

  // Enqueue element to the queue
  enqueue(element) {
    this.items.push(element);
  }

  // Dequeue element from the queue
  dequeue() {
    if (this.isEmpty()) return 'Queue is empty';
    return this.items.shift();  // Remove from the front
  }

  // Peek at the front element
  front() {
    if (this.isEmpty()) return 'Queue is empty';
    return this.items[0];
  }

  // Check if the queue is empty
  isEmpty() {
    return this.items.length === 0;
  }

  // Get queue size
  size() {
    return this.items.length;
  }
}

```

**Example**:

```
js
CopyEdit
const queue = new Queue();
queue.enqueue(10);
queue.enqueue(20);
queue.enqueue(30);

console.log(queue.dequeue()); // 10
console.log(queue.front()); // 20

```

---

### 3️⃣ Deque (Double-ended Queue)

- **Structure**: A **Deque** allows insertion and deletion of elements from both ends (front and back).

```
js
CopyEdit
class Deque {
  constructor() {
    this.items = [];
  }

  // Add element to the front
  addFront(element) {
    this.items.unshift(element);  // Add to the front
  }

  // Add element to the back
  addBack(element) {
    this.items.push(element);  // Add to the back
  }

  // Remove element from the front
  removeFront() {
    if (this.isEmpty()) return 'Deque is empty';
    return this.items.shift();  // Remove from the front
  }

  // Remove element from the back
  removeBack() {
    if (this.isEmpty()) return 'Deque is empty';
    return this.items.pop();  // Remove from the back
  }

  // Peek at the front element
  peekFront() {
    if (this.isEmpty()) return 'Deque is empty';
    return this.items[0];
  }

  // Peek at the back element
  peekBack() {
    if (this.isEmpty()) return 'Deque is empty';
    return this.items[this.items.length - 1];
  }

  // Check if the deque is empty
  isEmpty() {
    return this.items.length === 0;
  }

  // Get deque size
  size() {
    return this.items.length;
  }
}

```

**Example**:

```
js
CopyEdit
const deque = new Deque();
deque.addFront(10);
deque.addBack(20);
deque.addFront(5);

console.log(deque.removeBack()); // 20
console.log(deque.peekFront()); // 5

```

---

### 4️⃣ Priority Queue

- **Structure**: A **Priority Queue** is a queue where each element is assigned a priority. The element with the highest priority is dequeued first. This is often implemented using a heap data structure.

```
js
CopyEdit
class PriorityQueue {
  constructor() {
    this.items = [];
  }

  // Enqueue with priority
  enqueue(element, priority) {
    let queueElement = { element, priority };
    let added = false;
    for (let i = 0; i < this.items.length; i++) {
      if (queueElement.priority < this.items[i].priority) {
        this.items.splice(i, 0, queueElement);
        added = true;
        break;
      }
    }
    if (!added) {
      this.items.push(queueElement);
    }
  }

  // Dequeue element with highest priority
  dequeue() {
    if (this.isEmpty()) return 'Queue is empty';
    return this.items.shift().element;
  }

  // Check if the queue is empty
  isEmpty() {
    return this.items.length === 0;
  }

  // Peek at the front element (highest priority)
  front() {
    if (this.isEmpty()) return 'Queue is empty';
    return this.items[0].element;
  }

  // Get queue size
  size() {
    return this.items.length;
  }
}

```

**Example**:

```
js
CopyEdit
const pq = new PriorityQueue();
pq.enqueue('task 1', 2);  // Lower number means higher priority
pq.enqueue('task 2', 1);
pq.enqueue('task 3', 3);

console.log(pq.dequeue()); // task 2 (highest priority)
console.log(pq.front());  // task 1

```

---

### ✅ What to Do With It

- **Stacks** are best used when you need to keep track of function calls (recursion), backtracking, or undo operations.
- **Queues** are ideal when you need to handle tasks in the order they are received, such as in breadth-first search (BFS) or task scheduling.
- **Deque** is useful for problems where you need fast access and modification at both ends, such as sliding window problems or maintaining a set of candidates.
- **Priority Queue** is useful when dealing with scheduling tasks or event-driven systems where different tasks have different priorities.

---

### 🚫 What Not to Do With It

- **Stack**: Don’t use a stack for problems that require random access to elements or when you need to traverse elements in arbitrary order.
- **Queue**: Avoid using a queue for scenarios where random access or complex modification of elements is required.
- **Deque**: Don’t use a deque when you only need access at one end, as it consumes extra memory compared to a simple queue or stack.
- **Priority Queue**: Avoid using a priority queue when you don't need to prioritize elements, as it can be more complex to implement and maintain.

---

### 📚 If You Want to Learn More

- **Grokking Algorithms** – Chapter 6: *Stacks and Queues*
- **Introduction to Algorithms (CLRS)** – Chapter 10: *Stack and Queue Algorithms*
- **Algorithms by Robert Sedgewick** – Section 3.3: *Stacks and Queues*

## 📚 Hash Tables / Hash Maps / Sets

### 📖 Definition

1. **Hash Table** (or Hash Map) – A **data structure** that stores key-value pairs, where each key is mapped to a unique value. It uses a **hash function** to compute an index (hash) where the value should be stored. This allows for fast **O(1)** average-time complexity for lookups, insertions, and deletions.
2. **Hash Map** – Often used interchangeably with hash table. It's a specific implementation of the hash table where each key is mapped to a value. In JavaScript, the `Map` object is typically used.
3. **Set** – A collection of unique values. Unlike arrays, sets do not allow duplicate values. It uses hashing to ensure that each element is stored only once.

---

### 1️⃣ Hash Table (Hash Map)

- **Structure**: A hash table uses an array to store values, and the key is passed through a **hash function** to determine where the value is stored in the array. The hash function should distribute keys uniformly across the array to minimize collisions.

```
js
CopyEdit
class HashTable {
  constructor(size = 42) {
    this.table = new Array(size);
  }

  // Hash function
  hash(key) {
    let hash = 0;
    for (let i = 0; i < key.length; i++) {
      hash = (hash << 5) + hash + key.charCodeAt(i);
    }
    return hash % this.table.length;
  }

  // Set key-value pair
  set(key, value) {
    const index = this.hash(key);
    if (!this.table[index]) {
      this.table[index] = [];
    }
    this.table[index].push([key, value]);
  }

  // Get value by key
  get(key) {
    const index = this.hash(key);
    const bucket = this.table[index];
    if (bucket) {
      for (let [k, v] of bucket) {
        if (k === key) return v;
      }
    }
    return undefined;
  }

  // Remove key-value pair
  remove(key) {
    const index = this.hash(key);
    const bucket = this.table[index];
    if (bucket) {
      for (let i = 0; i < bucket.length; i++) {
        if (bucket[i][0] === key) {
          bucket.splice(i, 1);
          return;
        }
      }
    }
  }

  // Check if key exists
  has(key) {
    const index = this.hash(key);
    const bucket = this.table[index];
    if (bucket) {
      for (let [k] of bucket) {
        if (k === key) return true;
      }
    }
    return false;
  }
}

```

**Example**:

```
js
CopyEdit
const hashTable = new HashTable();
hashTable.set('name', 'Alice');
hashTable.set('age', 25);

console.log(hashTable.get('name')); // 'Alice'
console.log(hashTable.has('age'));  // true
hashTable.remove('age');
console.log(hashTable.get('age'));  // undefined

```

---

### 2️⃣ Hash Map (in JavaScript)

- **Structure**: In JavaScript, the `Map` object is a built-in data structure that works like a hash map. It stores key-value pairs, and the keys can be of any data type.

```
js
CopyEdit
let map = new Map();

// Set key-value pairs
map.set('name', 'Alice');
map.set('age', 25);

// Get value by key
console.log(map.get('name')); // 'Alice'

// Check if key exists
console.log(map.has('age'));  // true

// Remove key-value pair
map.delete('age');
console.log(map.has('age'));  // false

// Get the size of the map
console.log(map.size); // 1

```

---

### 3️⃣ Set

- **Structure**: A **Set** is a collection of unique values. Unlike an array, a set does not allow duplicate values. Internally, it uses hashing to store the unique values.

```
js
CopyEdit
let set = new Set();

// Add values to the set
set.add(10);
set.add(20);
set.add(30);
set.add(10);  // Duplicate will not be added

// Check if the set contains a value
console.log(set.has(20)); // true
console.log(set.has(50)); // false

// Remove a value from the set
set.delete(20);
console.log(set.has(20)); // false

// Get the size of the set
console.log(set.size); // 2

// Iterate through set
set.forEach(value => console.log(value));

```

**Example**:

```
js
CopyEdit
const uniqueNumbers = new Set([1, 2, 3, 3, 4, 5, 5]);

console.log(uniqueNumbers); // Set { 1, 2, 3, 4, 5 }
console.log(uniqueNumbers.size); // 5

```

---

### ✅ What to Do With It

- **Hash Tables / Hash Maps** are ideal when you need **fast lookups**, especially when the key space is large, and you want to avoid searching through all elements.
- **Set** is useful when you need to store a collection of **unique values** and need to quickly check for membership or perform set operations like intersection, union, and difference.

---

### 🚫 What Not to Do With It

- **Hash Table / Hash Map**:
    - Don’t use hash tables for storing a small amount of data where a simple list or array would suffice, as hash tables have more overhead.
    - Avoid using a hash table with a poor hash function, which could lead to excessive collisions.
- **Set**:
    - Don’t use a set if you need to store **ordered** data or need to access elements by an index. Arrays are better suited for these tasks.
    - Don’t use a set if you need to allow **duplicate** values.

---

### 📚 If You Want to Learn More

- **Grokking Algorithms** – Chapter 7: *Hash Tables*
- **Introduction to Algorithms (CLRS)** – Chapter 11: *Hash Tables*
- **Algorithms by Robert Sedgewick** – Section 3.5: *Hashing and Hash Tables*

## 🌳 Trees

### 📖 Definition

- **Tree**: A tree is a hierarchical data structure that consists of nodes connected by edges. Each tree has a **root node** and a set of child nodes, forming a parent-child relationship.
- **Binary Tree**: A tree where each node has at most two children, often referred to as the **left** and **right** child.
- **Binary Search Tree (BST)**: A binary tree where the nodes are arranged in a specific order: for each node, all elements in the left subtree are smaller, and all elements in the right subtree are greater.
- **AVL Tree**: A self-balancing binary search tree where the difference between the heights of the left and right subtrees of any node is at most 1.
- **Red-Black Tree**: A self-balancing binary search tree where each node has an extra bit for denoting color (either red or black) to maintain balance during insertions and deletions.

---

### 1️⃣ Binary Tree

- **Definition**: A **binary tree** is a type of tree where each node has at most two children, typically referred to as **left** and **right**.

```
js
CopyEdit
class BinaryTreeNode {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

class BinaryTree {
  constructor() {
    this.root = null;
  }

  // Insert a new value
  insert(value) {
    const newNode = new BinaryTreeNode(value);
    if (this.root === null) {
      this.root = newNode;
      return;
    }
    let current = this.root;
    while (current) {
      if (value < current.value) {
        if (!current.left) {
          current.left = newNode;
          break;
        } else {
          current = current.left;
        }
      } else {
        if (!current.right) {
          current.right = newNode;
          break;
        } else {
          current = current.right;
        }
      }
    }
  }

  // In-order traversal
  inOrderTraversal(node) {
    if (node === null) return;
    this.inOrderTraversal(node.left);
    console.log(node.value);
    this.inOrderTraversal(node.right);
  }
}

```

**Example**:

```
js
CopyEdit
const binaryTree = new BinaryTree();
binaryTree.insert(10);
binaryTree.insert(5);
binaryTree.insert(20);

binaryTree.inOrderTraversal(binaryTree.root); // Output: 5, 10, 20

```

---

### 2️⃣ Binary Search Tree (BST)

- **Definition**: A **binary search tree (BST)** is a binary tree where for each node, all the nodes in the left subtree are smaller than the node, and all the nodes in the right subtree are greater.

```
js
CopyEdit
class BSTNode {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

class BinarySearchTree {
  constructor() {
    this.root = null;
  }

  // Insert a new value
  insert(value) {
    const newNode = new BSTNode(value);
    if (this.root === null) {
      this.root = newNode;
      return;
    }
    let current = this.root;
    while (current) {
      if (value < current.value) {
        if (!current.left) {
          current.left = newNode;
          break;
        } else {
          current = current.left;
        }
      } else {
        if (!current.right) {
          current.right = newNode;
          break;
        } else {
          current = current.right;
        }
      }
    }
  }

  // Search for a value
  search(value) {
    let current = this.root;
    while (current) {
      if (value === current.value) return true;
      if (value < current.value) current = current.left;
      else current = current.right;
    }
    return false;
  }
}

```

**Example**:

```
js
CopyEdit
const bst = new BinarySearchTree();
bst.insert(10);
bst.insert(5);
bst.insert(20);

console.log(bst.search(5));  // true
console.log(bst.search(15)); // false

```

---

### 3️⃣ AVL / Red-Black Trees (Optional)

- **Definition**:
    - **AVL Tree**: A self-balancing binary search tree where the height of two child subtrees of any node differs by no more than one. It uses **rotations** to maintain balance after insertions and deletions.
    - **Red-Black Tree**: A balanced binary search tree where each node has a color (either red or black). It maintains balance using properties related to the color of nodes, ensuring that the tree remains balanced during insertions and deletions.

Both AVL and Red-Black Trees are **advanced topics**, and while their implementation is quite complex, here are the general ideas:

- **AVL Tree**: After every insertion or deletion, the tree is balanced by checking the balance factor of each node (the difference in height between the left and right subtrees).
- **Red-Black Tree**: Red-Black trees use color properties to ensure that the tree remains balanced. Some of the key properties of a Red-Black Tree include:
    - Every node is either red or black.
    - The root is always black.
    - Red nodes can't have red children (no two consecutive red nodes).
    - The number of black nodes from the root to any leaf is the same for all paths.

Both AVL and Red-Black Trees ensure **O(log n)** time complexity for operations like insertion, deletion, and search.

---

### ✅ What to Do With It

- **Binary Trees**: Useful for general hierarchical data storage, such as representing file systems, organizational charts, and more.
- **Binary Search Trees (BST)**: Best used when you need to maintain **ordered** data and perform fast search, insert, and delete operations.
- **AVL/Red-Black Trees**: Use them when you need a **self-balancing** binary search tree to ensure that the height remains balanced and the time complexity stays logarithmic, even in the worst case.

---

### 🚫 What Not to Do With It

- **Binary Trees**: Avoid using binary trees for **searching** if data is not sorted, as searching would take linear time in the worst case.
- **Binary Search Trees**:
    - Don’t use a plain binary search tree when you need guaranteed balance and efficient performance. **AVL** or **Red-Black Trees** are better options for self-balancing.
- **AVL/Red-Black Trees**:
    - Avoid using these if you don’t need the added complexity of balancing or if your data doesn’t require frequent insertions or deletions.

---

### 📚 If You Want to Learn More

- **Grokking Algorithms** – Chapter 8: *Binary Search Trees*
- **Introduction to Algorithms (CLRS)** – Chapter 12: *Binary Search Trees*, Chapter 13: *Red-Black Trees*
- **Algorithms by Robert Sedgewick** – Section 3.6: *Balanced Search Trees*

## 🏔️ Heaps

### 📖 Definition

A **heap** is a complete binary tree that satisfies the **heap property**:

- **Min Heap**: For every parent node, the value of the parent is **smaller** than or equal to the values of its children.
- **Max Heap**: For every parent node, the value of the parent is **greater** than or equal to the values of its children.

Heaps are commonly used in algorithms like **Heapsort** and in data structures like **priority queues**.

---

### 1️⃣ **Min Heap**

- **Definition**: A **Min Heap** is a complete binary tree where the value of each node is **smaller** than or equal to the values of its children. The smallest element is at the root.

### Operations

- **Insert**: Add a new element to the heap while maintaining the heap property.
- **Extract Min**: Remove the smallest element (root) and rearrange the heap to maintain the heap property.

```
js
CopyEdit
class MinHeap {
  constructor() {
    this.heap = [];
  }

  // Helper function to swap elements in the heap
  swap(i, j) {
    [this.heap[i], this.heap[j]] = [this.heap[j], this.heap[i]];
  }

  // Helper function to heapify the tree (min-heapify)
  heapify(index) {
    let smallest = index;
    const left = 2 * index + 1;
    const right = 2 * index + 2;

    if (left < this.heap.length && this.heap[left] < this.heap[smallest]) {
      smallest = left;
    }
    if (right < this.heap.length && this.heap[right] < this.heap[smallest]) {
      smallest = right;
    }

    if (smallest !== index) {
      this.swap(index, smallest);
      this.heapify(smallest);
    }
  }

  // Insert a new element into the heap
  insert(value) {
    this.heap.push(value);
    let index = this.heap.length - 1;

    while (index > 0 && this.heap[index] < this.heap[Math.floor((index - 1) / 2)]) {
      this.swap(index, Math.floor((index - 1) / 2));
      index = Math.floor((index - 1) / 2);
    }
  }

  // Extract the minimum element
  extractMin() {
    if (this.heap.length === 0) return null;
    if (this.heap.length === 1) return this.heap.pop();

    const root = this.heap[0];
    this.heap[0] = this.heap.pop();
    this.heapify(0);
    return root;
  }
}

```

**Example**:

```
js
CopyEdit
const minHeap = new MinHeap();
minHeap.insert(10);
minHeap.insert(20);
minHeap.insert(5);
minHeap.insert(30);

console.log(minHeap.extractMin()); // 5
console.log(minHeap.extractMin()); // 10

```

---

### 2️⃣ **Max Heap**

- **Definition**: A **Max Heap** is a complete binary tree where the value of each node is **greater** than or equal to the values of its children. The largest element is at the root.

### Operations

- **Insert**: Add a new element to the heap while maintaining the heap property.
- **Extract Max**: Remove the largest element (root) and rearrange the heap to maintain the heap property.

```
js
CopyEdit
class MaxHeap {
  constructor() {
    this.heap = [];
  }

  // Helper function to swap elements in the heap
  swap(i, j) {
    [this.heap[i], this.heap[j]] = [this.heap[j], this.heap[i]];
  }

  // Helper function to heapify the tree (max-heapify)
  heapify(index) {
    let largest = index;
    const left = 2 * index + 1;
    const right = 2 * index + 2;

    if (left < this.heap.length && this.heap[left] > this.heap[largest]) {
      largest = left;
    }
    if (right < this.heap.length && this.heap[right] > this.heap[largest]) {
      largest = right;
    }

    if (largest !== index) {
      this.swap(index, largest);
      this.heapify(largest);
    }
  }

  // Insert a new element into the heap
  insert(value) {
    this.heap.push(value);
    let index = this.heap.length - 1;

    while (index > 0 && this.heap[index] > this.heap[Math.floor((index - 1) / 2)]) {
      this.swap(index, Math.floor((index - 1) / 2));
      index = Math.floor((index - 1) / 2);
    }
  }

  // Extract the maximum element
  extractMax() {
    if (this.heap.length === 0) return null;
    if (this.heap.length === 1) return this.heap.pop();

    const root = this.heap[0];
    this.heap[0] = this.heap.pop();
    this.heapify(0);
    return root;
  }
}

```

**Example**:

```
js
CopyEdit
const maxHeap = new MaxHeap();
maxHeap.insert(10);
maxHeap.insert(20);
maxHeap.insert(5);
maxHeap.insert(30);

console.log(maxHeap.extractMax()); // 30
console.log(maxHeap.extractMax()); // 20

```

---

### ✅ **What to Do With It**

- **Min Heap**: Best used in algorithms like **Dijkstra's shortest path**, **Prim's algorithm**, or **Priority Queues** where you need to efficiently get the minimum element.
- **Max Heap**: Commonly used for **Priority Queues** where the maximum element is needed, or in algorithms like **Heapsort** for sorting data.
- **Heap Operations**: All operations (insertion, deletion) are **O(log n)** due to the tree structure and the need to maintain the heap property through heapify.

---

### 🚫 **What Not to Do With It**

- **Min Heap**: Avoid using a Min Heap when you need to extract the **maximum** element, as this would require reordering the entire heap.
- **Max Heap**: Avoid using a Max Heap when you need to frequently extract the **minimum** element, as the heap property would need to be violated.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 10: *Heaps and Priority Queues*
- **Introduction to Algorithms (CLRS)** – Chapter 6: *Heapsort*, Chapter 7: *Priority Queues*
- **Algorithms by Robert Sedgewick** – Section 2.4: *Heaps*

### 📖 Definition

A **Trie** (pronounced as "try") is a tree-like data structure used for storing a dynamic set of strings where the keys are usually strings. It is particularly efficient for **prefix searching** and is often used in scenarios like **autocomplete** and **spell-checking**.

- In a Trie, each node represents a **single character** of a string.
- The **root node** represents an empty string, and every path down the tree represents a possible string.
- The **edges** are labeled with characters, and a node is marked as a complete string if it is the last character of the word.

---

### Basic Operations

1. **Insert**: Insert a string into the Trie.
2. **Search**: Search for a string in the Trie.
3. **StartsWith**: Check if there is any string in the Trie that starts with a given prefix.

---

### 1️⃣ **Insert**

To insert a word into the Trie:

- Start from the root node and follow the path of characters for the word.
- If a character does not exist in the current node’s children, create a new node.
- Mark the last node of the word as a **complete word** node.

---

### 2️⃣ **Search**

To search for a word in the Trie:

- Traverse the Trie following the characters of the word.
- If a character is missing, the word does not exist in the Trie.
- If you reach the end of the word and the final node is marked as a **complete word**, the word exists in the Trie.

---

### 3️⃣ **StartsWith**

To check if there is any word in the Trie that starts with a given prefix:

- Traverse the Trie following the characters of the prefix.
- If you reach the end of the prefix and the traversal is successful, the prefix exists in the Trie.

---

### Example: **Trie Implementation in JavaScript**

```
js
CopyEdit
class TrieNode {
  constructor() {
    this.children = {};  // Stores child nodes (characters)
    this.isEndOfWord = false;  // Marks the end of a word
  }
}

class Trie {
  constructor() {
    this.root = new TrieNode();  // Root of the Trie
  }

  // Insert a word into the Trie
  insert(word) {
    let currentNode = this.root;
    for (let char of word) {
      if (!currentNode.children[char]) {
        currentNode.children[char] = new TrieNode();
      }
      currentNode = currentNode.children[char];
    }
    currentNode.isEndOfWord = true;
  }

  // Search for a word in the Trie
  search(word) {
    let currentNode = this.root;
    for (let char of word) {
      if (!currentNode.children[char]) {
        return false;  // Word not found
      }
      currentNode = currentNode.children[char];
    }
    return currentNode.isEndOfWord;  // True if it's a complete word
  }

  // Check if there is any word in the Trie that starts with a given prefix
  startsWith(prefix) {
    let currentNode = this.root;
    for (let char of prefix) {
      if (!currentNode.children[char]) {
        return false;  // No word starts with this prefix
      }
      currentNode = currentNode.children[char];
    }
    return true;  // Prefix exists
  }
}

```

---

### Example Usage

```
js
CopyEdit
const trie = new Trie();

trie.insert("apple");
trie.insert("app");
trie.insert("banana");

console.log(trie.search("apple"));  // true
console.log(trie.search("app"));    // true
console.log(trie.search("banana")); // true
console.log(trie.search("bat"));    // false

console.log(trie.startsWith("app"));  // true
console.log(trie.startsWith("ban"));  // true
console.log(trie.startsWith("bat"));  // false

```

---

### ✅ **What to Do With It**

- **Autocompletion**: Tries are ideal for implementing autocomplete systems where you need to quickly suggest completions for a given prefix.
- **Spell Checking**: Tries can be used to suggest corrections for misspelled words by searching for words that start with a given prefix.
- **Prefix Search**: Any application that needs to handle prefix-based queries (e.g., searching for usernames, hashtags, etc.).

---

### 🚫 **What Not to Do With It**

- **Space Complexity**: Tries can consume a lot of memory, especially for large sets of strings with overlapping prefixes. Avoid using Tries when memory efficiency is a critical concern for large datasets.
- **Deep Trie Structures**: Inserting very long strings into the Trie can cause deep nesting of nodes, which may result in performance issues for certain applications.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 6: *Tries and Prefix Trees*
- **Introduction to Algorithms (CLRS)** – Chapter 16: *Pattern Matching Algorithms (KMP, Trie)*
- **Algorithms by Robert Sedgewick** – Section 5.4: *Tries and Prefix Trees*

### 📖 Definition

A **Graph** is a collection of nodes (vertices) and edges that connect pairs of nodes. It is a fundamental data structure used to represent various real-world problems such as networks, social connections, transportation systems, etc.

- **Vertex (Node)**: A point in the graph, representing an entity.
- **Edge**: A connection between two vertices.

---

### Types of Graphs

1. **Directed Graph (Digraph)**: The edges have a direction, meaning they go from one vertex to another (e.g., Twitter followers).
2. **Undirected Graph**: The edges do not have a direction; the connection is mutual (e.g., Facebook friends).
3. **Weighted Graph**: Each edge has a weight, representing the cost or distance between two vertices (e.g., road maps, flight costs).
4. **Unweighted Graph**: The edges do not have weights (e.g., unweighted social network connections).

---

### Graph Representation

Graphs can be represented in various ways. Two common representations are:

### 1️⃣ **Adjacency List**

- An adjacency list represents a graph using a list where each node has a list of neighboring nodes.
- It is efficient in terms of space, especially for sparse graphs.

Example (Adjacency List Representation):

- Graph:
    - A -- B, C
    - B -- A, D
    - C -- A, D
    - D -- B, C

```
js
CopyEdit
const graphAdjList = {
  A: ['B', 'C'],
  B: ['A', 'D'],
  C: ['A', 'D'],
  D: ['B', 'C']
};

```

### 2️⃣ **Adjacency Matrix**

- An adjacency matrix represents a graph using a 2D matrix (2D array), where the value at the position `[i][j]` indicates whether there is an edge between vertex `i` and vertex `j`.
- It is space-inefficient for sparse graphs but allows constant-time access to check if an edge exists between two nodes.

Example (Adjacency Matrix Representation):

- Graph:
    - A -- B, C
    - B -- A, D
    - C -- A, D
    - D -- B, C

```
js
CopyEdit
const graphAdjMatrix = [
  [0, 1, 1, 0],  // A -> B, C
  [1, 0, 0, 1],  // B -> A, D
  [1, 0, 0, 1],  // C -> A, D
  [0, 1, 1, 0],  // D -> B, C
];

```

In the adjacency matrix:

- `0` indicates no edge, and `1` indicates an edge between vertices.

---

### Example: **Graph Representation in JavaScript**

```
js
CopyEdit
// Adjacency List
const graphAdjList = {
  A: ['B', 'C'],
  B: ['A', 'D'],
  C: ['A', 'D'],
  D: ['B', 'C']
};

// Adjacency Matrix
const graphAdjMatrix = [
  [0, 1, 1, 0],  // A -> B, C
  [1, 0, 0, 1],  // B -> A, D
  [1, 0, 0, 1],  // C -> A, D
  [0, 1, 1, 0],  // D -> B, C
];

console.log(graphAdjList);
console.log(graphAdjMatrix);

```

---

### ✅ **What to Do With It**

- **Graph Traversal**: Use BFS (Breadth-First Search) or DFS (Depth-First Search) algorithms to explore all nodes in the graph.
- **Shortest Path Algorithms**: Use Dijkstra's algorithm or Bellman-Ford to find the shortest path between nodes in weighted graphs.
- **Cycle Detection**: Detect cycles in directed or undirected graphs using DFS.
- **Social Networks**: Represent users as nodes and their relationships as edges in social networks.

---

### 🚫 **What Not to Do With It**

- **Memory Usage in Sparse Graphs**: Adjacency matrices can consume too much memory when the graph is sparse, as they require `O(V^2)` space, where `V` is the number of vertices.
- **Inefficient Access in Adjacency List**: If you need frequent edge lookups between arbitrary pairs of nodes, adjacency lists can be slower compared to adjacency matrices (since you have to traverse the list to find edges).

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 8: *Graph Algorithms*
- **Introduction to Algorithms (CLRS)** – Chapter 22: *Graph Algorithms*
- **Algorithms by Robert Sedgewick** – Section 4.3: *Graph Representations*

### 📖 Definition

The **Disjoint Set** or **Union-Find** data structure is used to manage a collection of disjoint (non-overlapping) sets. It supports two main operations:

1. **Union**: Combine two disjoint sets into one.
2. **Find**: Find the representative (or leader) of the set to which a particular element belongs.

Union-Find is particularly useful in algorithms involving connected components, like **Kruskal's algorithm** for minimum spanning trees and for **cycle detection** in undirected graphs.

---

### Core Operations

1. **Find**:
    - This operation returns the **representative** or **parent** of the set that a particular element belongs to.
    - If two elements are in the same set, they share the same representative.
2. **Union**:
    - This operation merges two sets. It attaches the smaller set under the root of the larger set to maintain balance and optimize future operations.
3. **Path Compression (Optimization)**:
    - During the **find** operation, we can flatten the structure by pointing all nodes directly to the root. This ensures that subsequent queries are faster.
4. **Union by Rank/Size (Optimization)**:
    - When performing the **union**, we always attach the smaller tree under the root of the larger tree. This helps maintain a balanced tree structure and optimizes time complexity.

---

### 📊 Time Complexity

- **Find** and **Union** operations can be **amortized** to **O(α(n))**, where α is the inverse Ackermann function, which grows very slowly, making it almost constant for practical purposes.

---

### Example: **Union-Find Data Structure in JavaScript**

```
js
CopyEdit
class UnionFind {
  constructor(size) {
    this.parent = Array(size).fill(null).map((_, index) => index);  // Each node is its own parent initially
    this.rank = Array(size).fill(1);  // Initialize rank for union by rank
  }

  // Find the representative (or parent) of the set containing x
  find(x) {
    if (this.parent[x] !== x) {
      this.parent[x] = this.find(this.parent[x]);  // Path compression
    }
    return this.parent[x];
  }

  // Union of two sets
  union(x, y) {
    const rootX = this.find(x);
    const rootY = this.find(y);

    if (rootX !== rootY) {
      // Union by rank
      if (this.rank[rootX] > this.rank[rootY]) {
        this.parent[rootY] = rootX;
      } else if (this.rank[rootX] < this.rank[rootY]) {
        this.parent[rootX] = rootY;
      } else {
        this.parent[rootY] = rootX;
        this.rank[rootX] += 1;
      }
    }
  }

  // Check if two elements belong to the same set
  connected(x, y) {
    return this.find(x) === this.find(y);
  }
}

```

---

### Example Usage

```
js
CopyEdit
const uf = new UnionFind(5);

uf.union(0, 1);
uf.union(1, 2);
uf.union(3, 4);

console.log(uf.find(0)); // 0 (representative of the set containing 0)
console.log(uf.find(1)); // 0 (representative of the set containing 1)
console.log(uf.connected(0, 2)); // true
console.log(uf.connected(0, 3)); // false

uf.union(2, 3);
console.log(uf.connected(0, 3)); // true (after union)

```

---

### ✅ **What to Do With It**

- **Kruskal's Algorithm**: Use Union-Find to detect cycles and form minimum spanning trees (MST) in a graph.
- **Connected Components**: Quickly determine if two nodes are connected in a graph.
- **Dynamic Connectivity**: Maintain and query the connectivity of dynamic graphs where edges are added or removed over time.
- **Find Cycles in Undirected Graphs**: Detect cycles in graphs using Union-Find.

---

### 🚫 **What Not to Do With It**

- **Inefficient for Non-Dynamic Graphs**: If the graph is not dynamic (no changes in edges), there are other algorithms that might be more efficient for problems like MST (e.g., Prim’s algorithm).
- **Too Complex for Small Graphs**: Union-Find might be overkill for small graphs or simple connectivity problems that can be solved with basic depth-first search (DFS).

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 8: *Disjoint Sets and Union-Find*
- **Introduction to Algorithms (CLRS)** – Chapter 21: *Union-Find Algorithms*
- **Algorithms by Robert Sedgewick** – Section 4.5: *Union-Find Data Structure*

### Searching Algorithms: Linear Search & Binary Search

---

### 1. **Linear Search**

---

### 📖 Definition

**Linear Search** is a simple search algorithm that checks each element of a list sequentially until the target element is found or the entire list is traversed.

It works on **unsorted** data and is straightforward but inefficient for large datasets.

---

### 🔑 Syntax / Pseudocode

```
js
CopyEdit
function linearSearch(arr, target) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === target) {
      return i;  // Return index of target
    }
  }
  return -1;  // Return -1 if target is not found
}

```

---

### 🖥️ Example: Linear Search

```
js
CopyEdit
function linearSearch(arr, target) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === target) {
      return i;  // Return index of target
    }
  }
  return -1;  // Return -1 if target is not found
}

const arr = [10, 20, 30, 40, 50];
console.log(linearSearch(arr, 30));  // returns 2 (index of 30)
console.log(linearSearch(arr, 60));  // returns -1 (not found)

```

---

### ✅ **What to Do With It**

- **Small Datasets**: Linear search is effective when the dataset is small and the simplicity of the algorithm is a priority.
- **Unsorted Data**: Use it when the data is unsorted or when sorting the data is not feasible.

---

### 🚫 **What Not to Do With It**

- **Large Datasets**: Linear search is inefficient for large datasets with time complexity **O(n)**.
- **Sorted Data**: Don't use it on sorted data, as more efficient algorithms like **binary search** can be applied.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 1: *Linear Search*
- **Introduction to Algorithms (CLRS)** – Chapter 2: *Searching Algorithms*
- **Algorithms by Robert Sedgewick** – Section 1.3: *Searching and Sorting*

---

---

### 2. **Binary Search**

---

### 📖 Definition

**Binary Search** is a more efficient search algorithm that works on **sorted** data. It repeatedly divides the search interval in half. If the target value is smaller than the middle element, the search continues in the left half. If the target value is larger, it continues in the right half. This results in a **logarithmic** time complexity.

---

### 🔑 Syntax / Pseudocode

```
js
CopyEdit
function binarySearch(arr, target) {
  let low = 0;
  let high = arr.length - 1;
  while (low <= high) {
    const mid = Math.floor((low + high) / 2);
    if (arr[mid] === target) {
      return mid;  // Return index of target
    } else if (arr[mid] < target) {
      low = mid + 1;
    } else {
      high = mid - 1;
    }
  }
  return -1;  // Return -1 if target is not found
}

```

---

### 🖥️ Example: Binary Search

```
js
CopyEdit
function binarySearch(arr, target) {
  let left = 0;
  let right = arr.length - 1;
  while (left <= right) {
    const mid = Math.floor((left + right) / 2);
    if (arr[mid] === target) return mid;
    if (arr[mid] < target) left = mid + 1;
    else right = mid - 1;
  }
  return -1;
}

const arr = [10, 20, 30, 40, 50];
console.log(binarySearch(arr, 30));  // returns 2 (index of 30)
console.log(binarySearch(arr, 60));  // returns -1 (not found)

```

---

### ✅ **What to Do With It**

- **Sorted Data**: Use binary search only on sorted arrays to take advantage of its **O(log n)** time complexity.
- **Optimal for Large Datasets**: Binary search is much faster than linear search for large datasets because of its **logarithmic** time complexity.

---

### 🚫 **What Not to Do With It**

- **Unsorted Data**: Don't use binary search on unsorted data; it requires the array to be sorted beforehand.
- **Data Structures Without Direct Access**: Avoid binary search on data structures like linked lists, where random access is not possible in constant time.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 2: *Binary Search*
- **Introduction to Algorithms (CLRS)** – Chapter 2: *Binary Search*
- **Algorithms by Robert Sedgewick** – Section 1.4: *Binary Search and Sorting*

### Sorting Algorithms

---

### 1. **Bubble Sort**

---

### 📖 Definition

**Bubble Sort** is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. The pass through the list is repeated until the list is sorted. It gets its name because the largest unsorted element "bubbles" up to its correct position after each pass.

---

### 🔑 Syntax / Pseudocode

```
js
CopyEdit
function bubbleSort(arr) {
  let n = arr.length;
  for (let i = 0; i < n - 1; i++) {
    for (let j = 0; j < n - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]]; // Swap
      }
    }
  }
  return arr;
}

```

---

### 🖥️ Example: Bubble Sort

```
js
CopyEdit
function bubbleSort(arr) {
  let n = arr.length;
  for (let i = 0; i < n - 1; i++) {
    for (let j = 0; j < n - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]]; // Swap
      }
    }
  }
  return arr;
}

const arr = [64, 34, 25, 12, 22, 11, 90];
console.log(bubbleSort(arr)); // returns [11, 12, 22, 25, 34, 64, 90]

```

---

### ✅ **What to Do With It**

- **Small Datasets**: Bubble Sort can be useful for small datasets where simplicity is more important than efficiency.
- **Educational Purpose**: It’s a great algorithm for teaching the fundamentals of sorting.

---

### 🚫 **What Not to Do With It**

- **Large Datasets**: Avoid Bubble Sort for large datasets due to its **O(n²)** time complexity.
- **Real-World Applications**: It is inefficient for practical use on large collections.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 3: *Bubble Sort*
- **Introduction to Algorithms (CLRS)** – Chapter 2: *Bubble Sort*
- **Algorithms by Robert Sedgewick** – Section 2.1: *Bubble Sort*

---

### 2. **Selection Sort**

---

### 📖 Definition

**Selection Sort** works by repeatedly selecting the smallest (or largest) element from the unsorted portion of the list and swapping it with the first unsorted element. The algorithm divides the list into two parts: the sorted part and the unsorted part.

---

### 🔑 Syntax / Pseudocode

```
js
CopyEdit
function selectionSort(arr) {
  let n = arr.length;
  for (let i = 0; i < n - 1; i++) {
    let minIndex = i;
    for (let j = i + 1; j < n; j++) {
      if (arr[j] < arr[minIndex]) {
        minIndex = j; // Find the minimum element
      }
    }
    [arr[i], arr[minIndex]] = [arr[minIndex], arr[i]]; // Swap
  }
  return arr;
}

```

---

### 🖥️ Example: Selection Sort

```
js
CopyEdit
function selectionSort(arr) {
  let n = arr.length;
  for (let i = 0; i < n - 1; i++) {
    let minIndex = i;
    for (let j = i + 1; j < n; j++) {
      if (arr[j] < arr[minIndex]) {
        minIndex = j;
      }
    }
    [arr[i], arr[minIndex]] = [arr[minIndex], arr[i]]; // Swap
  }
  return arr;
}

const arr = [64, 25, 12, 22, 11];
console.log(selectionSort(arr)); // returns [11, 12, 22, 25, 64]

```

---

### ✅ **What to Do With It**

- **Small Datasets**: Selection Sort can be useful for small datasets or when the simplicity of the algorithm is a priority.
- **Memory-Constrained Environments**: Selection Sort uses **O(1)** extra space.

---

### 🚫 **What Not to Do With It**

- **Large Datasets**: Selection Sort is not efficient for large datasets due to its **O(n²)** time complexity.
- **Real-World Applications**: There are more efficient algorithms (e.g., Merge Sort, Quick Sort) for large datasets.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 3: *Selection Sort*
- **Introduction to Algorithms (CLRS)** – Chapter 2: *Selection Sort*
- **Algorithms by Robert Sedgewick** – Section 2.2: *Selection Sort*

---

### 3. **Insertion Sort**

---

### 📖 Definition

**Insertion Sort** builds the sorted array one element at a time by repeatedly picking the next element and inserting it into its correct position among the previously sorted elements. It’s efficient for small datasets or partially sorted data.

---

### 🔑 Syntax / Pseudocode

```
js
CopyEdit
function insertionSort(arr) {
  let n = arr.length;
  for (let i = 1; i < n; i++) {
    let key = arr[i];
    let j = i - 1;
    while (j >= 0 && arr[j] > key) {
      arr[j + 1] = arr[j]; // Shift element to the right
      j--;
    }
    arr[j + 1] = key; // Insert key in its correct position
  }
  return arr;
}

```

---

### 🖥️ Example: Insertion Sort

```
js
CopyEdit
function insertionSort(arr) {
  let n = arr.length;
  for (let i = 1; i < n; i++) {
    let key = arr[i];
    let j = i - 1;
    while (j >= 0 && arr[j] > key) {
      arr[j + 1] = arr[j]; // Shift element to the right
      j--;
    }
    arr[j + 1] = key;
  }
  return arr;
}

const arr = [64, 25, 12, 22, 11];
console.log(insertionSort(arr)); // returns [11, 12, 22, 25, 64]

```

---

### ✅ **What to Do With It**

- **Small Datasets**: Efficient for small datasets or nearly sorted data.
- **Partially Sorted Data**: Works well for datasets that are already nearly sorted.

---

### 🚫 **What Not to Do With It**

- **Large Datasets**: Not efficient for large datasets due to its **O(n²)** time complexity.
- **Completely Unsorted Data**: For fully unsorted data, algorithms like Merge Sort or Quick Sort are better.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 4: *Insertion Sort*
- **Introduction to Algorithms (CLRS)** – Chapter 2: *Insertion Sort*
- **Algorithms by Robert Sedgewick** – Section 2.3: *Insertion Sort*

---

### 4. **Merge Sort**

---

### 📖 Definition

**Merge Sort** is a **divide and conquer** algorithm that divides the input array into two halves, sorts each half recursively, and then merges the two sorted halves back together. It has a consistent time complexity of **O(n log n)**.

---

### 🔑 Syntax / Pseudocode

```
js
CopyEdit
function mergeSort(arr) {
  if (arr.length <= 1) return arr;

  const mid = Math.floor(arr.length / 2);
  const left = mergeSort(arr.slice(0, mid));
  const right = mergeSort(arr.slice(mid));

  return merge(left, right);
}

function merge(left, right) {
  let result = [], i = 0, j = 0;
  while (i < left.length && j < right.length) {
    if (left[i] < right[j]) {
      result.push(left[i]);
      i++;
    } else {
      result.push(right[j]);
      j++;
    }
  }

  return result.concat(left.slice(i), right.slice(j));  // Append remaining elements
}

```

---

### 🖥️ Example: Merge Sort

```
js
CopyEdit
function mergeSort(arr) {
  if (arr.length <= 1) return arr;

  const mid = Math.floor(arr.length / 2);
  const left = mergeSort(arr.slice(0, mid));
  const right = mergeSort(arr.slice(mid));

  return merge(left, right);
}

function merge(left, right) {
  let result = [], i = 0, j = 0;
  while (i < left.length && j < right.length) {
    if (left[i] < right[j]) {
      result.push(left[i]);
      i++;
    } else {
      result.push(right[j]);
      j++;
    }
  }
  return result.concat(left.slice(i), right.slice(j));
}

const arr = [38, 27, 43, 3, 9, 82, 10];
console.log(mergeSort(arr)); // returns [3, 9, 10, 27, 38, 43, 82]

```

---

### ✅ **What to Do With It**

- **Large Datasets**: Merge Sort is efficient for large datasets and has a guaranteed **O(n log n)** time complexity.
- **Stable Sort**: Merge Sort is stable, meaning equal elements retain their relative order.

---

### 🚫 **What Not to Do With It**

- **Memory Usage**: Merge Sort requires additional memory to store the left and right halves, so it’s not ideal for memory-constrained environments.
- **Small Datasets**: For small datasets, simpler algorithms like Insertion Sort may perform better.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 7: *Merge Sort*
- **Introduction to Algorithms (CLRS)** – Chapter 4: *Merge Sort*
- **Algorithms by Robert Sedgewick** – Section 2.4: *Merge Sort*

### **Backtracking**

Backtracking is an algorithmic technique used to solve problems by trying all possible options and discarding those that fail to meet the problem's conditions. It’s typically used for constraint satisfaction problems such as puzzles, game-solving, and combinatorics.

---

### 1. **N-Queens Problem**

---

### 📖 Definition

The **N-Queens** problem asks for the placement of **N** chess queens on an **N x N** chessboard such that no two queens threaten each other. A queen can attack another queen if they share the same row, column, or diagonal.

---

### 🔑 Approach

Backtracking is used to try placing queens row by row and checking whether the current placement is safe. If placing a queen leads to a conflict (i.e., it shares a row, column, or diagonal with another queen), the algorithm backtracks and tries a different position.

---

### 🔑 Syntax / Pseudocode

```
js
CopyEdit
function solveNQueens(n) {
    let solutions = [];
    let board = Array(n).fill().map(() => Array(n).fill('.')); // Initialize the board with empty cells

    function isSafe(row, col) {
        // Check column and diagonals for any queens
        for (let i = 0; i < row; i++) {
            if (board[i][col] === 'Q' ||
                (col - (row - i) >= 0 && board[i][col - (row - i)] === 'Q') ||
                (col + (row - i) < n && board[i][col + (row - i)] === 'Q')) {
                return false;
            }
        }
        return true;
    }

    function backtrack(row) {
        if (row === n) {
            // All queens are placed, add the current solution to the results
            solutions.push(board.map(row => row.join('')));
            return;
        }

        for (let col = 0; col < n; col++) {
            if (isSafe(row, col)) {
                board[row][col] = 'Q'; // Place the queen
                backtrack(row + 1);     // Recursively place queens in the next row
                board[row][col] = '.';  // Backtrack: remove the queen
            }
        }
    }

    backtrack(0); // Start the backtracking process from the first row
    return solutions;
}

```

---

### 🖥️ Example: N-Queens Problem

```
js
CopyEdit
function solveNQueens(n) {
    let solutions = [];
    let board = Array(n).fill().map(() => Array(n).fill('.'));

    function isSafe(row, col) {
        for (let i = 0; i < row; i++) {
            if (board[i][col] === 'Q' ||
                (col - (row - i) >= 0 && board[i][col - (row - i)] === 'Q') ||
                (col + (row - i) < n && board[i][col + (row - i)] === 'Q')) {
                return false;
            }
        }
        return true;
    }

    function backtrack(row) {
        if (row === n) {
            solutions.push(board.map(row => row.join('')));
            return;
        }

        for (let col = 0; col < n; col++) {
            if (isSafe(row, col)) {
                board[row][col] = 'Q';
                backtrack(row + 1);
                board[row][col] = '.';
            }
        }
    }

    backtrack(0);
    return solutions;
}

console.log(solveNQueens(4)); // Prints all solutions for a 4x4 board

```

---

### ✅ **What to Do With It**

- **Constraint Problems**: Backtracking is useful for solving problems where constraints need to be satisfied (e.g., N-Queens, Sudoku, etc.).
- **Efficient Search**: Use backtracking when you need to search through all possible solutions but can eliminate large sections of the search space by pruning invalid solutions early.

---

### 🚫 **What Not to Do With It**

- **Large Datasets**: Backtracking can be slow when the search space is too large, as it explores all possibilities.
- **When Optimality is a Priority**: Backtracking is not guaranteed to find the most optimal solution, especially in cases like **traveling salesman** or **knapsack problems**.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 6: *Backtracking (N-Queens)*
- **Introduction to Algorithms (CLRS)** – Chapter 5: *Backtracking*
- **Algorithms by Robert Sedgewick** – Section 4.5: *Backtracking*

### 2. **Subsets / Permutations**

---

### 📖 Definition

The **Subsets** problem involves finding all subsets of a given set, while the **Permutations** problem involves finding all possible permutations (arrangements) of a given set of elements. Both problems are commonly solved using backtracking.

---

### 🔑 Approach

Backtracking can be used to explore all possible subsets or permutations by making a decision at each step: either to include an element in the current subset or permutation, or not. If a solution is valid, it's added to the results; otherwise, the algorithm backtracks and tries another choice.

---

### 🔑 Syntax / Pseudocode for Subsets

```
js
CopyEdit
function subsets(nums) {
    let result = [];

    function backtrack(start, path) {
        result.push([...path]); // Add the current subset to the result
        for (let i = start; i < nums.length; i++) {
            path.push(nums[i]); // Include current element in the subset
            backtrack(i + 1, path); // Recur with next elements
            path.pop(); // Backtrack by removing the current element
        }
    }

    backtrack(0, []); // Start with an empty subset
    return result;
}

```

---

### 🖥️ Example: Subsets

```
js
CopyEdit
function subsets(nums) {
    let result = [];

    function backtrack(start, path) {
        result.push([...path]); // Add the current subset
        for (let i = start; i < nums.length; i++) {
            path.push(nums[i]); // Include the element
            backtrack(i + 1, path); // Recur with the next elements
            path.pop(); // Backtrack
        }
    }

    backtrack(0, []);
    return result;
}

console.log(subsets([1, 2, 3])); // Prints all subsets of [1, 2, 3]

```

---

### 🔑 Syntax / Pseudocode for Permutations

```
js
CopyEdit
function permute(nums) {
    let result = [];

    function backtrack(path) {
        if (path.length === nums.length) {
            result.push([...path]); // If the permutation is complete
            return;
        }

        for (let i = 0; i < nums.length; i++) {
            if (path.includes(nums[i])) continue; // Skip if the number is already in the permutation
            path.push(nums[i]);
            backtrack(path); // Recur
            path.pop(); // Backtrack
        }
    }

    backtrack([]);
    return result;
}

```

---

### 🖥️ Example: Permutations

```
js
CopyEdit
function permute(nums) {
    let result = [];

    function backtrack(path) {
        if (path.length === nums.length) {
            result.push([...path]); // If the permutation is complete
            return;
        }

        for (let i = 0; i < nums.length; i++) {
            if (path.includes(nums[i])) continue; // Skip if the number is already in the permutation
            path.push(nums[i]);
            backtrack(path); // Recur
            path.pop(); // Backtrack
        }
    }

    backtrack([]);
    return result;
}

console.log(permute([1, 2, 3])); // Prints all permutations of [1, 2, 3]

```

---

### ✅ **What to Do With It**

- **Combinatorial Problems**: Backtracking is ideal for solving problems involving combinations, permutations, or subsets (e.g., generating power sets, solving Sudoku, etc.).
- **Optimizing Search Space**: By pruning invalid paths early, backtracking can optimize solutions when the search space is large but can be reduced at each step.

---

### 🚫 **What Not to Do With It**

- **Large Input Size**: The time complexity of generating all subsets or permutations grows exponentially, so backtracking should be avoided for large input sizes.
- **Unconstrained Search Spaces**: If the search space is too large without any constraints, backtracking might not be efficient.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 6: *Backtracking (Subsets/Permutations)*
- **Introduction to Algorithms (CLRS)** – Chapter 5: *Backtracking and its applications*
- **Algorithms by Robert Sedgewick** – Section 4.6: *Backtracking*

### **Greedy Algorithms**

Greedy algorithms are a class of algorithms that make locally optimal choices at each stage with the hope of finding a global optimum. They are often used for optimization problems where a globally optimal solution can be arrived at by choosing the best option available at each step.

---

### 1. **Activity Selection Problem**

---

### 📖 Definition

The **Activity Selection Problem** is about selecting the maximum number of activities that don’t overlap. Each activity has a start and end time, and the objective is to select the maximum number of activities that can be scheduled without any two overlapping.

The greedy strategy is to always select the next activity that finishes the earliest and is compatible with the already selected activities.

---

### 🔑 Approach

The problem can be solved using a greedy approach by:

1. Sorting the activities by their finishing time.
2. Selecting the activity that finishes first and doesn’t conflict with previously selected activities.
3. Repeating the process until all possible activities are selected.

---

### 🔑 Syntax / Pseudocode

```
js
CopyEdit
function activitySelection(activities) {
    // Sort the activities based on finish time
    activities.sort((a, b) => a.finish - b.finish);

    let selectedActivities = [];
    let lastFinishTime = -1;

    for (let i = 0; i < activities.length; i++) {
        if (activities[i].start >= lastFinishTime) {
            selectedActivities.push(activities[i]);
            lastFinishTime = activities[i].finish;
        }
    }

    return selectedActivities;
}

```

---

### 🖥️ Example: Activity Selection

```
js
CopyEdit
function activitySelection(activities) {
    activities.sort((a, b) => a.finish - b.finish); // Sort activities by finish time

    let selectedActivities = [];
    let lastFinishTime = -1;

    for (let i = 0; i < activities.length; i++) {
        if (activities[i].start >= lastFinishTime) {
            selectedActivities.push(activities[i]);
            lastFinishTime = activities[i].finish;
        }
    }

    return selectedActivities;
}

const activities = [
    { start: 1, finish: 4 },
    { start: 3, finish: 5 },
    { start: 0, finish: 6 },
    { start: 5, finish: 7 },
    { start: 8, finish: 9 },
    { start: 5, finish: 9 }
];

console.log(activitySelection(activities));
// Output: [{ start: 1, finish: 4 }, { start: 5, finish: 7 }, { start: 8, finish: 9 }]

```

---

### ✅ **What to Do With It**

- **Interval Scheduling**: Use greedy algorithms to select non-overlapping intervals in problems like task scheduling, room booking, etc.
- **Sorting by Finish Time**: Always sort intervals or activities by their finish time before selecting the next activity.

---

### 🚫 **What Not to Do With It**

- **Overlapping Intervals**: Greedy algorithms don’t work well for problems where a globally optimal solution involves considering overlapping intervals or more complex constraints.
- **When Constraints Matter**: If the problem has additional constraints that must be considered globally (e.g., deadlines, resource constraints), a greedy approach might not work.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 9: *Greedy Algorithms (Activity Selection)*
- **Introduction to Algorithms (CLRS)** – Chapter 16: *Greedy Algorithms*
- **Algorithms by Robert Sedgewick** – Section 5.3: *Greedy Algorithms*

---

### 2. **Huffman Coding**

---

### 📖 Definition

**Huffman Coding** is a lossless data compression algorithm that assigns variable-length codes to input characters, with shorter codes assigned to more frequent characters. It uses a binary tree to represent the codewords and is optimal for minimizing the overall length of the encoded message.

Huffman coding is widely used in file compression formats like ZIP, JPEG, and PNG.

---

### 🔑 Approach

1. Count the frequency of each character.
2. Create a priority queue (min-heap) to store the characters based on their frequencies.
3. Repeatedly extract two nodes with the smallest frequencies and combine them into a new node with the sum of their frequencies.
4. Insert the new node back into the priority queue.
5. Repeat until there’s only one node left in the queue, which will represent the Huffman tree.

---

### 🔑 Syntax / Pseudocode

```
js
CopyEdit
function huffmanCoding(freqMap) {
    let priorityQueue = new MinHeap();

    // Step 1: Build the priority queue with individual characters and their frequencies
    for (let [char, freq] of Object.entries(freqMap)) {
        priorityQueue.insert({ char, freq });
    }

    // Step 2: Build the Huffman tree
    while (priorityQueue.size() > 1) {
        let left = priorityQueue.extractMin();
        let right = priorityQueue.extractMin();

        let newNode = {
            freq: left.freq + right.freq,
            left: left,
            right: right
        };

        priorityQueue.insert(newNode);
    }

    // Step 3: Generate the codes from the Huffman tree
    let root = priorityQueue.extractMin();
    let codes = {};
    function generateCodes(node, currentCode) {
        if (node.char) {
            codes[node.char] = currentCode; // Store the code for the character
            return;
        }

        generateCodes(node.left, currentCode + '0');
        generateCodes(node.right, currentCode + '1');
    }

    generateCodes(root, '');

    return codes;
}

```

---

### 🖥️ Example: Huffman Coding

```
js
CopyEdit
class MinHeap {
    constructor() {
        this.heap = [];
    }

    insert(node) {
        this.heap.push(node);
        this._heapifyUp();
    }

    extractMin() {
        if (this.size() === 0) return null;
        if (this.size() === 1) return this.heap.pop();

        const min = this.heap[0];
        this.heap[0] = this.heap.pop();
        this._heapifyDown();
        return min;
    }

    size() {
        return this.heap.length;
    }

    _heapifyUp() {
        let index = this.size() - 1;
        while (index > 0) {
            const parentIndex = Math.floor((index - 1) / 2);
            if (this.heap[index].freq >= this.heap[parentIndex].freq) break;
            [this.heap[index], this.heap[parentIndex]] = [this.heap[parentIndex], this.heap[index]];
            index = parentIndex;
        }
    }

    _heapifyDown() {
        let index = 0;
        while (index < this.size()) {
            const leftChildIndex = 2 * index + 1;
            const rightChildIndex = 2 * index + 2;
            let smallest = index;

            if (leftChildIndex < this.size() && this.heap[leftChildIndex].freq < this.heap[smallest].freq) {
                smallest = leftChildIndex;
            }
            if (rightChildIndex < this.size() && this.heap[rightChildIndex].freq < this.heap[smallest].freq) {
                smallest = rightChildIndex;
            }
            if (smallest === index) break;

            [this.heap[index], this.heap[smallest]] = [this.heap[smallest], this.heap[index]];
            index = smallest;
        }
    }
}

function huffmanCoding(freqMap) {
    let priorityQueue = new MinHeap();

    // Step 1: Build the priority queue with individual characters and their frequencies
    for (let [char, freq] of Object.entries(freqMap)) {
        priorityQueue.insert({ char, freq });
    }

    // Step 2: Build the Huffman tree
    while (priorityQueue.size() > 1) {
        let left = priorityQueue.extractMin();
        let right = priorityQueue.extractMin();

        let newNode = {
            freq: left.freq + right.freq,
            left: left,
            right: right
        };

        priorityQueue.insert(newNode);
    }

    // Step 3: Generate the codes from the Huffman tree
    let root = priorityQueue.extractMin();
    let codes = {};
    function generateCodes(node, currentCode) {
        if (node.char) {
            codes[node.char] = currentCode; // Store the code for the character
            return;
        }

        generateCodes(node.left, currentCode + '0');
        generateCodes(node.right, currentCode + '1');
    }

    generateCodes(root, '');

    return codes;
}

const freqMap = {
    'a': 5,
    'b': 9,
    'c': 12,
    'd': 13,
    'e': 16,
    'f': 45
};

console.log(huffmanCoding(freqMap));
// Example Output: { a: '1111', b: '1110', c: '110', d: '10', e: '0', f: '1' }

```

---

### ✅ **What to Do With It**

- **Data Compression**: Use Huffman coding for compressing data efficiently, such as in text files or other formats (e.g., image compression).
- **Optimal Prefix Codes**: Huffman coding generates optimal prefix-free codes, making it suitable for communication protocols, file systems, and more.

---

### 🚫 **What Not to Do With It**

- **Large Data**: Huffman coding is not always the most efficient for extremely large datasets or in situations where other compression techniques like LZ77 or Arithmetic Coding are more effective.
- **Non-Optimal Performance for Small Data**: For small datasets, Huffman coding might not provide significant compression benefits.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 11: *Huffman Coding*
- **Introduction to Algorithms (CLRS)** – Chapter 16: *Greedy Algorithms (Huffman Coding)*
- **Algorithms by Robert Sedgewick** – Section 6.5: *Huffman Coding*

### **Divide and Conquer**

Divide and conquer is an algorithm design paradigm that involves breaking down a problem into smaller subproblems, solving those subproblems independently, and combining their results to solve the original problem. It is commonly used to solve problems that exhibit optimal substructure, where the problem can be divided into smaller subproblems that are similar in nature to the original problem.

---

### 1. **Merge Sort**

---

### 📖 Definition

**Merge Sort** is a classic divide-and-conquer algorithm used for sorting. It works by recursively dividing the input array into two halves, sorting each half, and then merging the sorted halves to produce the final sorted array.

The key concept is that merging two sorted arrays is an easy task, which is why merge sort breaks the problem down into progressively smaller subproblems and combines them efficiently.

---

### 🔑 Approach

1. **Divide**: Split the input array into two halves.
2. **Conquer**: Recursively sort each half.
3. **Combine**: Merge the sorted halves to form a sorted array.

---

### 🔑 Syntax / Pseudocode

```
js
CopyEdit
function mergeSort(arr) {
    if (arr.length <= 1) {
        return arr; // Base case: arrays of size 1 or less are already sorted
    }

    const mid = Math.floor(arr.length / 2);
    const left = arr.slice(0, mid);
    const right = arr.slice(mid);

    return merge(mergeSort(left), mergeSort(right));
}

function merge(left, right) {
    let result = [];
    let leftIndex = 0;
    let rightIndex = 0;

    // Merge the two sorted arrays
    while (leftIndex < left.length && rightIndex < right.length) {
        if (left[leftIndex] < right[rightIndex]) {
            result.push(left[leftIndex]);
            leftIndex++;
        } else {
            result.push(right[rightIndex]);
            rightIndex++;
        }
    }

    // Concatenate any remaining elements
    return result.concat(left.slice(leftIndex), right.slice(rightIndex));
}

```

---

### 🖥️ Example: Merge Sort

```
js
CopyEdit
function mergeSort(arr) {
    if (arr.length <= 1) return arr;

    const mid = Math.floor(arr.length / 2);
    const left = arr.slice(0, mid);
    const right = arr.slice(mid);

    return merge(mergeSort(left), mergeSort(right));
}

function merge(left, right) {
    let result = [];
    let leftIndex = 0;
    let rightIndex = 0;

    while (leftIndex < left.length && rightIndex < right.length) {
        if (left[leftIndex] < right[rightIndex]) {
            result.push(left[leftIndex]);
            leftIndex++;
        } else {
            result.push(right[rightIndex]);
            rightIndex++;
        }
    }

    return result.concat(left.slice(leftIndex), right.slice(rightIndex));
}

const arr = [38, 27, 43, 3, 9, 82, 10];
console.log(mergeSort(arr)); // Output: [3, 9, 10, 27, 38, 43, 82]

```

---

### ✅ **What to Do With It**

- **Large Datasets**: Merge sort is efficient for sorting large datasets, as its time complexity is O(nlog⁡n)O(n \log n)O(nlogn), which is faster than simpler algorithms like bubble sort or insertion sort.
- **External Sorting**: Merge sort is commonly used in external sorting, such as sorting files stored on disk, because it can be implemented with a minimum amount of memory.

---

### 🚫 **What Not to Do With It**

- **Memory Usage**: Merge sort requires extra space for the left and right subarrays, which makes it less memory-efficient than algorithms like Quick Sort in situations where memory is a concern.
- **Small Data**: For small datasets, simpler algorithms like insertion sort may be more efficient because they have a smaller constant factor in practice.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 4: *Merge Sort*
- **Introduction to Algorithms (CLRS)** – Chapter 2: *Merge Sort*
- **Algorithms by Robert Sedgewick** – Section 2.3: *Merge Sort*

---

### 2. **Quick Sort**

---

### 📖 Definition

**Quick Sort** is another divide-and-conquer sorting algorithm that works by selecting a "pivot" element from the array, partitioning the array into two subarrays (one with elements smaller than the pivot and the other with elements larger than the pivot), and then recursively sorting the subarrays. Quick sort is considered efficient and typically outperforms merge sort in practice due to its smaller memory footprint.

---

### 🔑 Approach

1. **Choose a pivot**: Pick an element from the array, commonly the first, last, or middle element.
2. **Partition**: Rearrange the array such that elements smaller than the pivot are on one side, and elements greater than the pivot are on the other.
3. **Recursively apply**: Apply the same process to the two subarrays formed by splitting around the pivot.

---

### 🔑 Syntax / Pseudocode

```
js
CopyEdit
function quickSort(arr) {
    if (arr.length <= 1) return arr;

    let pivot = arr[arr.length - 1];  // Choose last element as pivot
    let left = [];
    let right = [];

    for (let i = 0; i < arr.length - 1; i++) {
        if (arr[i] < pivot) {
            left.push(arr[i]);
        } else {
            right.push(arr[i]);
        }
    }

    return [...quickSort(left), pivot, ...quickSort(right)];
}

```

---

### 🖥️ Example: Quick Sort

```
js
CopyEdit
function quickSort(arr) {
    if (arr.length <= 1) return arr;

    let pivot = arr[arr.length - 1];
    let left = [];
    let right = [];

    for (let i = 0; i < arr.length - 1; i++) {
        if (arr[i] < pivot) left.push(arr[i]);
        else right.push(arr[i]);
    }

    return [...quickSort(left), pivot, ...quickSort(right)];
}

const arr = [38, 27, 43, 3, 9, 82, 10];
console.log(quickSort(arr)); // Output: [3, 9, 10, 27, 38, 43, 82]

```

---

### ✅ **What to Do With It**

- **In-place Sorting**: Quick sort sorts in-place, meaning it doesn’t require extra memory like merge sort.
- **Efficient for Large Arrays**: Quick sort is generally faster than merge sort for larger datasets due to its smaller memory footprint and cache-friendly nature.

---

### 🚫 **What Not to Do With It**

- **Worst-case Performance**: Quick sort has a worst-case time complexity of O(n2)O(n^2)O(n2), which can occur when the pivot is consistently the smallest or largest element. This can be mitigated by using random pivot selection or the median-of-three method.
- **Stack Overflow**: Recursive quicksort can cause a stack overflow for large arrays, although this can be mitigated with tail recursion or iterative implementations.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 6: *Quick Sort*
- **Introduction to Algorithms (CLRS)** – Chapter 7: *Quick Sort*
- **Algorithms by Robert Sedgewick** – Section 3.4: *Quick Sort*

---

### 3. **Other Divide and Conquer Algorithms**

While Merge Sort and Quick Sort are the most common and widely known divide and conquer algorithms, other problems can also be solved using this technique, such as:

- **Binary Search**: Divides the search space in half at each step to find an element in a sorted array.
- **Closest Pair of Points**: Divides the set of points into smaller subsets to efficiently find the closest pair in O(nlog⁡n)O(n \log n)O(nlogn) time.

### 4. **Graph Algorithms**

Graphs are fundamental data structures used to model networks and relationships between objects. Several algorithms are used to explore and manipulate graphs. The two most common graph traversal algorithms are **Depth First Search (DFS)** and **Breadth First Search (BFS)**. Both are used to explore all nodes and edges in a graph, but they do so in different ways.

---

### 1. **Depth First Search (DFS)**

---

### 📖 **Definition**

**Depth First Search (DFS)** is an algorithm used to traverse or search through a graph (either directed or undirected). It starts at a given node and explores as far as possible along each branch before backtracking. This means it goes deep into a graph before exploring other branches.

DFS is commonly used in problems involving pathfinding, connected components, and topological sorting.

---

### 🔑 **Approach**

1. **Start**: Begin at a node and mark it as visited.
2. **Explore**: Recursively explore all unvisited adjacent nodes.
3. **Backtrack**: If there are no unvisited adjacent nodes, backtrack to the previous node and continue the process.

DFS can be implemented using either **recursion** or an **explicit stack**.

---

### 🔑 **Syntax / Pseudocode**

```
js
CopyEdit
function dfs(graph, start, visited = new Set()) {
    if (visited.has(start)) return;

    // Mark the node as visited
    visited.add(start);
    console.log(start); // Process the node (for example, print it)

    // Explore all adjacent nodes
    for (let neighbor of graph[start]) {
        if (!visited.has(neighbor)) {
            dfs(graph, neighbor, visited);
        }
    }
}

```

---

### 🖥️ **Example: DFS**

```
js
CopyEdit
const graph = {
    A: ['B', 'C'],
    B: ['A', 'D', 'E'],
    C: ['A', 'F'],
    D: ['B'],
    E: ['B'],
    F: ['C']
};

function dfs(graph, start, visited = new Set()) {
    if (visited.has(start)) return;

    visited.add(start);
    console.log(start);

    for (let neighbor of graph[start]) {
        if (!visited.has(neighbor)) {
            dfs(graph, neighbor, visited);
        }
    }
}

dfs(graph, 'A');
// Output: A, B, D, E, C, F

```

---

### ✅ **What to Do With It**

- **Finding Connected Components**: Use DFS to find all connected nodes in an undirected graph.
- **Topological Sorting**: DFS is useful for topological sorting in directed acyclic graphs (DAGs), such as ordering tasks in a project.
- **Pathfinding**: DFS can be used to find paths between nodes, although it may not find the shortest path.

---

### 🚫 **What Not to Do With It**

- **Not Always Optimal for Shortest Path**: DFS does not guarantee the shortest path, unlike BFS. If you need the shortest path, prefer BFS.
- **Stack Overflow**: DFS can cause a stack overflow if the recursion goes too deep (e.g., for very large graphs).

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 7: *DFS*
- **Introduction to Algorithms (CLRS)** – Chapter 22: *Depth First Search*
- **Algorithms by Robert Sedgewick** – Section 4.2: *Depth First Search*

---

### 2. **Breadth First Search (BFS)**

---

### 📖 **Definition**

**Breadth First Search (BFS)** is another graph traversal algorithm that explores all nodes at the present depth level before moving on to nodes at the next depth level. BFS uses a queue to keep track of the nodes to be visited next, ensuring that the closest nodes are visited first.

BFS is commonly used for finding the shortest path in an unweighted graph and for exploring graphs layer by layer.

---

### 🔑 **Approach**

1. **Start**: Begin at a node and mark it as visited.
2. **Explore**: Explore all neighbors at the current depth level before moving to the next depth level.
3. **Queue**: Use a queue to keep track of nodes to visit next.

---

### 🔑 **Syntax / Pseudocode**

```
js
CopyEdit
function bfs(graph, start) {
    let visited = new Set();
    let queue = [start];

    while (queue.length > 0) {
        let node = queue.shift(); // Dequeue the front element
        if (visited.has(node)) continue;

        // Mark the node as visited
        visited.add(node);
        console.log(node); // Process the node (e.g., print it)

        // Enqueue all unvisited neighbors
        for (let neighbor of graph[node]) {
            if (!visited.has(neighbor)) {
                queue.push(neighbor);
            }
        }
    }
}

```

---

### 🖥️ **Example: BFS**

```
js
CopyEdit
const graph = {
    A: ['B', 'C'],
    B: ['A', 'D', 'E'],
    C: ['A', 'F'],
    D: ['B'],
    E: ['B'],
    F: ['C']
};

function bfs(graph, start) {
    let visited = new Set();
    let queue = [start];

    while (queue.length > 0) {
        let node = queue.shift();
        if (visited.has(node)) continue;

        visited.add(node);
        console.log(node);

        for (let neighbor of graph[node]) {
            if (!visited.has(neighbor)) {
                queue.push(neighbor);
            }
        }
    }
}

bfs(graph, 'A');
// Output: A, B, C, D, E, F

```

---

### ✅ **What to Do With It**

- **Shortest Path in Unweighted Graphs**: BFS is optimal for finding the shortest path between two nodes in an unweighted graph.
- **Level-by-Level Traversal**: Use BFS to process nodes level by level, which can be useful in scenarios like finding the nearest neighbor or implementing algorithms like the "Word Ladder Problem."
- **Connected Components**: BFS can help find all nodes reachable from a given starting node, helping to identify connected components in a graph.

---

### 🚫 **What Not to Do With It**

- **Space Complexity**: BFS requires storing all nodes at a given level in the queue, which may lead to high space complexity for large graphs.
- **Not Optimal for Weighted Graphs**: BFS does not work well for weighted graphs. For weighted shortest paths, use algorithms like Dijkstra's.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 8: *BFS*
- **Introduction to Algorithms (CLRS)** – Chapter 22: *Breadth First Search*
- **Algorithms by Robert Sedgewick** – Section 4.3: *Breadth First Search*

---

### Comparison of DFS vs BFS

| **Property** | **DFS** | **BFS** |
| --- | --- | --- |
| **Time Complexity** | O(V + E) (V = number of vertices, E = number of edges) | O(V + E) |
| **Space Complexity** | O(V) (for recursion stack) | O(V) (for queue) |
| **Shortest Path** | Not guaranteed | Guaranteed in unweighted graphs |
| **Traversal Type** | Deep into the graph | Level-by-level traversal |
| **Use Cases** | Pathfinding, Topological Sort | Shortest Path, Level Traversal |

### **Topological Sort**

---

### 📖 **Definition**

**Topological Sort** is an ordering of the vertices in a directed acyclic graph (DAG) such that for every directed edge u→vu \rightarrow vu→v, vertex uuu comes before vvv in the ordering. In other words, it is a way to arrange the nodes of a directed graph in a linear order that respects the dependencies between them.

Topological sorting is commonly used in tasks such as task scheduling, resolving dependencies in software packages, and organizing data processing tasks.

---

### 🔑 **Approach**

- **Preconditions**: The graph must be a **Directed Acyclic Graph (DAG)**. If the graph has a cycle, topological sorting is impossible.
- **Algorithm**: We can use two main approaches to perform topological sorting:
    - **Kahn’s Algorithm** (using in-degree)
    - **DFS-based Algorithm**

---

### 🔑 **Syntax / Pseudocode**

**Kahn’s Algorithm**:

1. Initialize the in-degree (number of incoming edges) of each node.
2. Use a queue to store nodes with zero in-degree (no dependencies).
3. While the queue is not empty:
    - Dequeue a node, add it to the topological order.
    - For each adjacent node of the dequeued node, decrease its in-degree. If its in-degree becomes zero, add it to the queue.

```
js
CopyEdit
function topologicalSort(graph) {
    let inDegree = {};
    let queue = [];
    let result = [];

    // Initialize in-degree for each node
    for (let node in graph) {
        inDegree[node] = 0;
    }

    // Calculate the in-degree of each node
    for (let node in graph) {
        for (let neighbor of graph[node]) {
            inDegree[neighbor]++;
        }
    }

    // Enqueue nodes with no incoming edges (in-degree 0)
    for (let node in graph) {
        if (inDegree[node] === 0) {
            queue.push(node);
        }
    }

    // Process the queue
    while (queue.length > 0) {
        let node = queue.shift();
        result.push(node);

        // Decrease the in-degree of neighbors
        for (let neighbor of graph[node]) {
            inDegree[neighbor]--;
            if (inDegree[neighbor] === 0) {
                queue.push(neighbor);
            }
        }
    }

    // If result length equals the number of nodes, return topological order
    if (result.length === Object.keys(graph).length) {
        return result;
    } else {
        throw new Error("Graph has a cycle, topological sort is not possible");
    }
}

```

---

### 🖥️ **Example: Topological Sort**

```
js
CopyEdit
const graph = {
    A: ['B', 'C'],
    B: ['D'],
    C: ['D'],
    D: []
};

function topologicalSort(graph) {
    let inDegree = {};
    let queue = [];
    let result = [];

    for (let node in graph) {
        inDegree[node] = 0;
    }

    for (let node in graph) {
        for (let neighbor of graph[node]) {
            inDegree[neighbor]++;
        }
    }

    for (let node in graph) {
        if (inDegree[node] === 0) {
            queue.push(node);
        }
    }

    while (queue.length > 0) {
        let node = queue.shift();
        result.push(node);

        for (let neighbor of graph[node]) {
            inDegree[neighbor]--;
            if (inDegree[neighbor] === 0) {
                queue.push(neighbor);
            }
        }
    }

    if (result.length === Object.keys(graph).length) {
        return result;
    } else {
        throw new Error("Graph has a cycle, topological sort is not possible");
    }
}

console.log(topologicalSort(graph));
// Output: [ 'A', 'B', 'C', 'D' ]

```

---

### ✅ **What to Do With It**

- **Task Scheduling**: Use topological sort for tasks where certain tasks depend on others. It ensures that each task is performed only after its dependencies are completed.
- **Compilation Order**: In compilers, topological sorting helps in determining the correct order of compilation, ensuring that libraries or modules are compiled in a sequence that respects dependencies.
- **Dependency Resolution**: Topological sorting can be used in scenarios like package managers (npm, pip), where package dependencies need to be installed in the correct order.

---

### 🚫 **What Not to Do With It**

- **Cyclic Graphs**: Do not apply topological sort to graphs that contain cycles (circular dependencies). If the graph has cycles, a topological sort is not possible.
- **Not for Undirected Graphs**: This algorithm is only applicable to **directed acyclic graphs (DAGs)**. It does not work with undirected graphs or graphs with cycles.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 12: *Topological Sort*
- **Introduction to Algorithms (CLRS)** – Chapter 22: *Topological Sorting*
- **Algorithms by Robert Sedgewick** – Section 4.5: *Topological Sort*

### **Dijkstra’s Algorithm**

---

### 📖 **Definition**

**Dijkstra’s Algorithm** is a famous algorithm used to find the shortest path between nodes in a graph, which may represent, for example, road networks. It works for graphs with non-negative edge weights and guarantees the shortest path from a source node to all other nodes in the graph.

The algorithm maintains a set of nodes whose shortest distance from the source is known and iteratively updates the shortest distance to all other nodes.

---

### 🔑 **Approach**

1. **Initialization**:
    - Set the distance to the source node as 0 and all other nodes as infinity.
    - Create a priority queue (min-heap) to store nodes based on their tentative distance values.
2. **Relaxation**:
    - Pick the node with the smallest tentative distance.
    - Update the distances of its neighboring nodes.
3. **Termination**:
    - The algorithm stops once all nodes have been processed or the smallest distance in the priority queue is infinity (indicating there is no more reachable node).

---

### 🔑 **Syntax / Pseudocode**

1. Initialize the distance to the source node as 0 and all other nodes as infinity.
2. Add the source node to a priority queue.
3. While the priority queue is not empty:
    - Extract the node with the smallest distance.
    - For each neighbor of the current node, calculate the new tentative distance. If it is smaller than the current stored distance, update it.
4. Repeat until the queue is empty or the shortest paths are found.

```
js
CopyEdit
function dijkstra(graph, source) {
    const distances = {};
    const priorityQueue = new PriorityQueue();

    // Initialize distances
    for (let node in graph) {
        distances[node] = Infinity;
    }
    distances[source] = 0;

    // Add source node to the queue
    priorityQueue.enqueue(source, 0);

    while (!priorityQueue.isEmpty()) {
        let currentNode = priorityQueue.dequeue();

        for (let neighbor in graph[currentNode]) {
            let distance = graph[currentNode][neighbor];
            let newDist = distances[currentNode] + distance;

            if (newDist < distances[neighbor]) {
                distances[neighbor] = newDist;
                priorityQueue.enqueue(neighbor, newDist);
            }
        }
    }

    return distances;
}

```

---

### 🖥️ **Example: Dijkstra’s Algorithm**

```
js
CopyEdit
class PriorityQueue {
    constructor() {
        this.queue = [];
    }

    enqueue(node, priority) {
        this.queue.push({ node, priority });
        this.queue.sort((a, b) => a.priority - b.priority);
    }

    dequeue() {
        return this.queue.shift().node;
    }

    isEmpty() {
        return this.queue.length === 0;
    }
}

const graph = {
    A: { B: 1, C: 4 },
    B: { A: 1, C: 2, D: 5 },
    C: { A: 4, B: 2, D: 1 },
    D: { B: 5, C: 1 }
};

function dijkstra(graph, source) {
    const distances = {};
    const priorityQueue = new PriorityQueue();

    for (let node in graph) {
        distances[node] = Infinity;
    }
    distances[source] = 0;

    priorityQueue.enqueue(source, 0);

    while (!priorityQueue.isEmpty()) {
        let currentNode = priorityQueue.dequeue();

        for (let neighbor in graph[currentNode]) {
            let distance = graph[currentNode][neighbor];
            let newDist = distances[currentNode] + distance;

            if (newDist < distances[neighbor]) {
                distances[neighbor] = newDist;
                priorityQueue.enqueue(neighbor, newDist);
            }
        }
    }

    return distances;
}

console.log(dijkstra(graph, 'A'));
// Output: { A: 0, B: 1, C: 3, D: 4 }

```

---

### ✅ **What to Do With It**

- **Shortest Path Problems**: Use Dijkstra’s algorithm for problems like shortest path finding in a graph where all edges have non-negative weights.
- **Routing Algorithms**: It is widely used in applications like GPS navigation systems for finding the shortest path between locations.
- **Network Routing**: Dijkstra’s algorithm is fundamental in network routing protocols (such as OSPF) for determining the best paths for data transmission.

---

### 🚫 **What Not to Do With It**

- **Negative Edge Weights**: Dijkstra’s algorithm doesn’t work correctly with graphs that contain negative weight edges. For graphs with negative weights, **Bellman-Ford Algorithm** is recommended.
- **Inefficient with Dense Graphs**: While Dijkstra’s algorithm is efficient with sparse graphs, it can become slow with very dense graphs due to the nature of the priority queue.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 10: *Dijkstra’s Algorithm*
- **Introduction to Algorithms (CLRS)** – Chapter 24: *Shortest Paths*
- **Algorithms by Robert Sedgewick** – Section 4.5: *Dijkstra’s Algorithm*

### **Bellman-Ford Algorithm**

---

### 📖 **Definition**

**Bellman-Ford Algorithm** is a single-source shortest path algorithm that is capable of handling graphs with negative edge weights, unlike Dijkstra’s algorithm. It can detect negative weight cycles in a graph, which is useful for applications where such cycles must be identified and avoided.

The algorithm works by relaxing all edges repeatedly, where "relaxing" means updating the shortest known path to each vertex.

---

### 🔑 **Approach**

1. **Initialization**:
    - Set the distance to the source node as 0 and all other nodes as infinity.
2. **Relaxation**:
    - For each edge, if the current shortest path to the destination node is greater than the sum of the shortest path to the source node and the edge weight, update the destination node’s shortest path.
3. **Negative Cycle Detection**:
    - After repeating the relaxation for `V-1` times (where `V` is the number of vertices), check all edges again. If any edge can still be relaxed, then a negative weight cycle exists in the graph.
4. **Termination**:
    - The algorithm stops once all edges are processed, and the shortest paths from the source node are finalized.

---

### 🔑 **Syntax / Pseudocode**

```
js
CopyEdit
function bellmanFord(graph, V, E, source) {
    let dist = new Array(V).fill(Infinity);
    dist[source] = 0;

    // Step 1: Relax all edges V-1 times
    for (let i = 1; i < V; i++) {
        for (let j = 0; j < E.length; j++) {
            let u = E[j][0];
            let v = E[j][1];
            let weight = E[j][2];

            if (dist[u] !== Infinity && dist[u] + weight < dist[v]) {
                dist[v] = dist[u] + weight;
            }
        }
    }

    // Step 2: Check for negative-weight cycles
    for (let j = 0; j < E.length; j++) {
        let u = E[j][0];
        let v = E[j][1];
        let weight = E[j][2];

        if (dist[u] !== Infinity && dist[u] + weight < dist[v]) {
            console.log("Graph contains negative weight cycle");
            return;
        }
    }

    return dist;
}

```

---

### 🖥️ **Example: Bellman-Ford Algorithm**

```
js
CopyEdit
function bellmanFord(graph, V, E, source) {
    let dist = new Array(V).fill(Infinity);
    dist[source] = 0;

    // Step 1: Relax all edges V-1 times
    for (let i = 1; i < V; i++) {
        for (let j = 0; j < E.length; j++) {
            let u = E[j][0];
            let v = E[j][1];
            let weight = E[j][2];

            if (dist[u] !== Infinity && dist[u] + weight < dist[v]) {
                dist[v] = dist[u] + weight;
            }
        }
    }

    // Step 2: Check for negative-weight cycles
    for (let j = 0; j < E.length; j++) {
        let u = E[j][0];
        let v = E[j][1];
        let weight = E[j][2];

        if (dist[u] !== Infinity && dist[u] + weight < dist[v]) {
            console.log("Graph contains negative weight cycle");
            return;
        }
    }

    return dist;
}

// Graph representation (edges: [u, v, weight])
const edges = [
    [0, 1, -1],
    [0, 2, 4],
    [1, 2, 3],
    [1, 3, 2],
    [1, 4, 2],
    [3, 2, 5],
    [3, 1, 1],
    [4, 3, -3]
];

const V = 5; // Number of vertices
const source = 0; // Source node

console.log(bellmanFord(null, V, edges, source));
// Output: [ 0, -1, 2, -2, 1 ]

```

---

### ✅ **What to Do With It**

- **Graphs with Negative Weights**: Use Bellman-Ford for shortest path problems where edge weights can be negative.
- **Cycle Detection**: The algorithm can be used to detect negative weight cycles, making it useful for various applications such as currency arbitrage and routing protocols.
- **Fallback for Dijkstra**: If the graph might contain negative weights, Bellman-Ford is a safer choice compared to Dijkstra's algorithm, which is inefficient in such cases.

---

### 🚫 **What Not to Do With It**

- **Graphs with Only Positive Weights**: For graphs with only non-negative weights, Dijkstra’s algorithm is generally more efficient than Bellman-Ford.
- **Large Graphs**: Bellman-Ford has a time complexity of O(V * E), making it slower than other algorithms like Dijkstra for large graphs with many edges.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 5: *Graph Algorithms*
- **Introduction to Algorithms (CLRS)** – Chapter 24: *Single-Source Shortest Paths (Bellman-Ford)*
- **Algorithms by Robert Sedgewick** – Section 4.3: *Single-Source Shortest Paths*

### **Floyd-Warshall Algorithm**

---

### 📖 **Definition**

**Floyd-Warshall Algorithm** is an all-pairs shortest path algorithm. It is used to find the shortest paths between every pair of vertices in a weighted graph, whether the graph is directed or undirected. It can also handle negative edge weights, but it does not work for graphs with negative weight cycles.

This algorithm is based on dynamic programming and computes the shortest paths between all pairs of vertices by progressively improving the solution with each step.

---

### 🔑 **Approach**

1. **Initialization**:
    - Start with a distance matrix where the value at position `(i, j)` is the weight of the edge between `i` and `j`, or infinity if no edge exists between them. The diagonal is initialized to 0, as the distance from any vertex to itself is 0.
2. **Relaxation Process**:
    - The algorithm iterates over all possible pairs of vertices `(i, j)` for each intermediate vertex `k`. For each pair, it checks if a path from `i` to `j` through `k` is shorter than the current shortest path. If it is, the matrix is updated.
3. **Termination**:
    - After iterating over all possible intermediate vertices, the final matrix contains the shortest distances between all pairs of vertices.

---

### 🔑 **Syntax / Pseudocode**

```
js
CopyEdit
function floydWarshall(graph, V) {
    let dist = Array.from(Array(V), () => Array(V).fill(Infinity));

    // Initialize the distance matrix
    for (let i = 0; i < V; i++) {
        dist[i][i] = 0;  // Distance to self is zero
    }

    // Initialize the graph distances
    for (let [u, v, weight] of graph) {
        dist[u][v] = weight;
    }

    // Floyd-Warshall algorithm
    for (let k = 0; k < V; k++) {
        for (let i = 0; i < V; i++) {
            for (let j = 0; j < V; j++) {
                if (dist[i][j] > dist[i][k] + dist[k][j]) {
                    dist[i][j] = dist[i][k] + dist[k][j];
                }
            }
        }
    }

    return dist;
}

```

---

### 🖥️ **Example: Floyd-Warshall Algorithm**

```
js
CopyEdit
function floydWarshall(graph, V) {
    let dist = Array.from(Array(V), () => Array(V).fill(Infinity));

    // Initialize the distance matrix
    for (let i = 0; i < V; i++) {
        dist[i][i] = 0;  // Distance to self is zero
    }

    // Initialize the graph distances
    for (let [u, v, weight] of graph) {
        dist[u][v] = weight;
    }

    // Floyd-Warshall algorithm
    for (let k = 0; k < V; k++) {
        for (let i = 0; i < V; i++) {
            for (let j = 0; j < V; j++) {
                if (dist[i][j] > dist[i][k] + dist[k][j]) {
                    dist[i][j] = dist[i][k] + dist[k][j];
                }
            }
        }
    }

    return dist;
}

// Graph representation as an array of edges [u, v, weight]
const graph = [
    [0, 1, 3],
    [0, 2, 8],
    [1, 2, -4],
    [2, 3, 1],
    [3, 0, 2],
    [3, 1, -5]
];

const V = 4; // Number of vertices

console.log(floydWarshall(graph, V));

```

---

### ✅ **What to Do With It**

- **All-Pairs Shortest Paths**: Use the Floyd-Warshall algorithm when you need the shortest paths between every pair of vertices, especially when negative weights are involved.
- **Graph with Negative Weights**: This algorithm is ideal for graphs with negative edge weights, but remember it doesn’t work for negative weight cycles.
- **Use for Dense Graphs**: It is generally more useful for dense graphs because its time complexity is O(V^3), which can become expensive for large sparse graphs with many vertices.

---

### 🚫 **What Not to Do With It**

- **Sparse Graphs**: For sparse graphs, algorithms like Dijkstra or Bellman-Ford may be more efficient, as Floyd-Warshall is slower for graphs with fewer edges.
- **Graphs with Negative Weight Cycles**: The Floyd-Warshall algorithm will not give correct results if there are negative weight cycles in the graph. You must detect cycles separately before applying this algorithm.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 6: *Graph Algorithms*
- **Introduction to Algorithms (CLRS)** – Chapter 25: *All-Pairs Shortest Paths (Floyd-Warshall)*
- **Algorithms by Robert Sedgewick** – Section 4.4: *All-Pairs Shortest Paths*

### **Minimum Spanning Trees (Prim’s & Kruskal’s)**

---

### 📖 **Definition**

A **Minimum Spanning Tree (MST)** is a tree that connects all the vertices in a graph with the minimum possible total edge weight. There are several algorithms for finding MSTs, with **Prim’s Algorithm** and **Kruskal’s Algorithm** being two of the most commonly used.

---

### **1. Prim’s Algorithm**

Prim’s Algorithm is a greedy algorithm that constructs the MST by starting from any arbitrary vertex and repeatedly adding the shortest edge that connects a vertex in the tree to a vertex outside the tree. It ensures that the edges selected are always the shortest possible, making it greedy.

---

### 🔑 **Approach**

1. **Start with any vertex** in the graph and mark it as part of the MST.
2. **Find the minimum-weight edge** that connects a vertex in the MST to a vertex outside it.
3. **Add that edge** and the new vertex to the MST.
4. Repeat the process until all vertices are included in the MST.

---

### 🔑 **Syntax / Pseudocode**

```
js
CopyEdit
function prim(graph, V) {
    let minEdge = Array(V).fill(Infinity);  // Store minimum edge weights
    let mstSet = Array(V).fill(false);      // Track vertices already in MST
    let parent = Array(V).fill(-1);         // To store MST structure
    minEdge[0] = 0;                         // Start from the first vertex

    for (let count = 0; count < V - 1; count++) {
        // Find the minimum edge
        let u = minKey(minEdge, mstSet, V);
        mstSet[u] = true;

        for (let v = 0; v < V; v++) {
            // If v is not in MST and there is an edge from u to v
            if (graph[u][v] && !mstSet[v] && graph[u][v] < minEdge[v]) {
                minEdge[v] = graph[u][v];
                parent[v] = u;
            }
        }
    }

    // Return the MST edges
    let mst = [];
    for (let i = 1; i < V; i++) {
        mst.push([parent[i], i, graph[i][parent[i]]]);
    }

    return mst;
}

// Helper function to find the vertex with the minimum key value
function minKey(minEdge, mstSet, V) {
    let min = Infinity, minIndex = -1;
    for (let v = 0; v < V; v++) {
        if (!mstSet[v] && minEdge[v] < min) {
            min = minEdge[v];
            minIndex = v;
        }
    }
    return minIndex;
}

```

---

### 🖥️ **Example: Prim’s Algorithm**

```
js
CopyEdit
const graph = [
    [0, 2, 0, 6, 0],
    [2, 0, 3, 8, 5],
    [0, 3, 0, 0, 7],
    [6, 8, 0, 0, 9],
    [0, 5, 7, 9, 0]
];

const V = 5;
console.log(prim(graph, V));  // Output: MST edges with weights

```

---

### **2. Kruskal’s Algorithm**

Kruskal’s Algorithm is also a greedy algorithm but works differently from Prim’s. Instead of growing the MST from a single vertex, Kruskal’s algorithm starts by sorting all the edges in the graph by weight and then adds the smallest edges to the MST while ensuring no cycles are formed.

---

### 🔑 **Approach**

1. **Sort all edges** in the graph in increasing order of their weights.
2. **Initialize a disjoint-set** (union-find) data structure to manage the vertices in the MST.
3. **Iterate over the edges** and add the edge to the MST if it does not form a cycle (i.e., the two vertices of the edge are not already in the same set).
4. **Repeat** until you have added `V-1` edges (where `V` is the number of vertices).

---

### 🔑 **Syntax / Pseudocode**

```
js
CopyEdit
function kruskal(graph, V) {
    let edges = [];
    for (let u = 0; u < V; u++) {
        for (let v = u + 1; v < V; v++) {
            if (graph[u][v] !== 0) {
                edges.push([graph[u][v], u, v]);
            }
        }
    }

    edges.sort((a, b) => a[0] - b[0]);  // Sort edges by weight

    let parent = Array(V).fill(-1);
    let mst = [];

    function find(x) {
        if (parent[x] === -1) return x;
        return find(parent[x]);
    }

    function union(x, y) {
        let rootX = find(x);
        let rootY = find(y);
        if (rootX !== rootY) {
            parent[rootX] = rootY;
        }
    }

    for (let [weight, u, v] of edges) {
        if (find(u) !== find(v)) {
            mst.push([u, v, weight]);
            union(u, v);
        }
    }

    return mst;
}

```

---

### 🖥️ **Example: Kruskal’s Algorithm**

```
js
CopyEdit
const graph = [
    [0, 2, 0, 6, 0],
    [2, 0, 3, 8, 5],
    [0, 3, 0, 0, 7],
    [6, 8, 0, 0, 9],
    [0, 5, 7, 9, 0]
];

const V = 5;
console.log(kruskal(graph, V));  // Output: MST edges with weights

```

---

### ✅ **What to Do With It**

- **Prim’s Algorithm**: Best for dense graphs, where you want to build the MST starting from a single vertex.
- **Kruskal’s Algorithm**: Works best for sparse graphs, especially when you can easily sort the edges and perform union-find operations.
- **Disjoint-Set (Union-Find)**: Always use this data structure in Kruskal’s algorithm to efficiently detect cycles.

---

### 🚫 **What Not to Do With It**

- **Prim’s Algorithm**: Avoid it on sparse graphs where Kruskal’s algorithm might be more efficient due to fewer edges.
- **Kruskal’s Algorithm**: Avoid it on graphs where edge sorting is expensive or when performing union-find operations is inefficient.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 6: *Graph Algorithms* (covers Kruskal’s and Prim’s in detail)
- **Introduction to Algorithms (CLRS)** – Chapter 23: *Minimum Spanning Trees*
- **Algorithms by Robert Sedgewick** – Section 4.3: *Minimum Spanning Trees*

### **Cycle Detection (Union-Find / DFS)**

---

### 📖 **Definition**

**Cycle detection** refers to the process of determining whether a graph contains any cycles. A **cycle** is a path that starts and ends at the same vertex without repeating any edges or vertices. There are two main approaches for detecting cycles in a graph:

1. **Union-Find** (also known as Disjoint Set Union - DSU)
2. **Depth-First Search (DFS)**

---

### **1. Cycle Detection Using Union-Find**

The **Union-Find** data structure is a powerful technique to detect cycles in undirected graphs. It efficiently handles dynamic connectivity and is commonly used in algorithms like Kruskal’s for Minimum Spanning Tree. To detect cycles, the idea is to keep track of connected components using **union** and **find** operations:

- **Find**: Determines the root or representative of the set to which an element belongs.
- **Union**: Merges two sets if they are not already connected.

If, during the process of adding an edge, both vertices belong to the same set (i.e., they have the same root), then adding the edge would form a cycle.

---

### 🔑 **Approach (Union-Find)**

1. **Initialize** a disjoint-set data structure.
2. For each edge in the graph:
    - **Find** the roots of the two vertices.
    - If the roots are the same, a cycle is detected.
    - Otherwise, **union** the two sets.
3. **Repeat** until all edges are processed.

---

### 🔑 **Syntax / Pseudocode (Union-Find)**

```
js
CopyEdit
function find(parent, x) {
    if (parent[x] === -1) {
        return x;
    }
    return find(parent, parent[x]);
}

function union(parent, x, y) {
    let rootX = find(parent, x);
    let rootY = find(parent, y);

    if (rootX !== rootY) {
        parent[rootX] = rootY; // Union by setting rootX's parent to rootY
    }
}

function detectCycle(graph, V) {
    let parent = Array(V).fill(-1);  // Initialize parent array for Union-Find

    for (let [u, v] of graph) {
        let rootU = find(parent, u);
        let rootV = find(parent, v);

        if (rootU === rootV) {
            return true;  // Cycle detected
        }

        union(parent, u, v);  // Union the two vertices
    }

    return false;  // No cycle found
}

```

---

### 🖥️ **Example: Cycle Detection using Union-Find**

```
js
CopyEdit
const graph = [
    [0, 1],
    [1, 2],
    [2, 0]  // This edge forms a cycle
];

const V = 3;
console.log(detectCycle(graph, V));  // Output: true (cycle detected)

```

---

### **2. Cycle Detection Using DFS**

In the **DFS** approach, we use depth-first traversal of the graph. During traversal, if we encounter a vertex that has already been visited and is not the immediate parent of the current vertex, then a cycle exists. This is because a back edge to an ancestor is found, forming a cycle.

---

### 🔑 **Approach (DFS)**

1. **Start DFS** traversal from any unvisited vertex.
2. Mark the current vertex as visited.
3. For each adjacent vertex:
    - If the adjacent vertex is not visited, recursively perform DFS on it.
    - If the adjacent vertex is already visited and is not the parent of the current vertex, a cycle is detected.
4. **Repeat** until all vertices are visited.

---

### 🔑 **Syntax / Pseudocode (DFS)**

```
js
CopyEdit
function dfs(graph, v, visited, parent) {
    visited[v] = true;

    for (let neighbor of graph[v]) {
        if (!visited[neighbor]) {
            if (dfs(graph, neighbor, visited, v)) {
                return true;  // Cycle detected
            }
        } else if (neighbor !== parent) {
            return true;  // Back edge found, cycle detected
        }
    }

    return false;
}

function detectCycle(graph, V) {
    let visited = Array(V).fill(false);

    for (let i = 0; i < V; i++) {
        if (!visited[i]) {
            if (dfs(graph, i, visited, -1)) {
                return true;  // Cycle detected
            }
        }
    }

    return false;  // No cycle found
}

```

---

### 🖥️ **Example: Cycle Detection using DFS**

```
js
CopyEdit
const graph = [
    [1],         // Vertex 0 is connected to 1
    [0, 2],      // Vertex 1 is connected to 0 and 2
    [1, 0]       // Vertex 2 is connected to 1 and 0, forming a cycle
];

const V = 3;
console.log(detectCycle(graph, V));  // Output: true (cycle detected)

```

---

### ✅ **What to Do With It**

- **Union-Find**: Best for cycle detection in undirected graphs with a large number of edges. It's efficient due to its near constant time complexity for union and find operations when using path compression and union by rank.
- **DFS**: Great for cycle detection in both directed and undirected graphs. It's simpler and doesn't require additional space for the union-find structure but may be less efficient on large graphs.

---

### 🚫 **What Not to Do With It**

- **Union-Find**: Avoid using it for directed graphs where the edge direction matters for cycle detection.
- **DFS**: Avoid using DFS on graphs that have very deep recursion as it may lead to stack overflow errors.

---

### 📚 **If You Want to Learn More**

- **Grokking Algorithms** – Chapter 7: *Graph Algorithms* (Covers DFS and cycle detection in graphs)
- **Introduction to Algorithms (CLRS)** – Chapter 22: *Minimum Spanning Trees* (Union-Find structure)
- **Algorithms by Robert Sedgewick** – Section 4.2: *Union-Find and Graphs*

### **0/1 Knapsack Problem**

---

### 📖 **Definition**

The **0/1 Knapsack Problem** is a classic **Dynamic Programming (DP)** problem where you're given a set of items, each with a weight and a value. You must choose a subset of these items to put into a knapsack (bag) so that:

- The **total weight does not exceed** the knapsack's capacity.
- The **total value is maximized**.

You can either **include** or **exclude** each item (hence "0/1").

---

### 🧠 **Key Concepts**

- **Choice**: For each item, you decide to either take it or leave it.
- **Overlapping subproblems**: The same sub-knapsack problems are solved multiple times.
- **Optimal substructure**: The solution to a problem depends on the solutions to subproblems.

---

### ✅ **Recursive Relation**

For each item `i` and capacity `W`:

```
swift
CopyEdit
dp[i][W] = max(
    dp[i-1][W],                             // Not including current item
    value[i] + dp[i-1][W - weight[i]]       // Including current item
)

```

---

### 💡 **Approach 1: Recursive (with Memoization)**

```
js
CopyEdit
function knapsack(weights, values, n, W, memo = {}) {
    const key = `${n}-${W}`;
    if (key in memo) return memo[key];

    if (n === 0 || W === 0) return 0;

    if (weights[n - 1] > W) {
        memo[key] = knapsack(weights, values, n - 1, W, memo);
    } else {
        const include = values[n - 1] + knapsack(weights, values, n - 1, W - weights[n - 1], memo);
        const exclude = knapsack(weights, values, n - 1, W, memo);
        memo[key] = Math.max(include, exclude);
    }

    return memo[key];
}

```

---

### 💡 **Approach 2: Bottom-Up DP (Tabulation)**

```
js
CopyEdit
function knapsack(weights, values, W) {
    const n = weights.length;
    const dp = Array(n + 1).fill().map(() => Array(W + 1).fill(0));

    for (let i = 1; i <= n; i++) {
        for (let w = 0; w <= W; w++) {
            if (weights[i - 1] <= w) {
                dp[i][w] = Math.max(
                    values[i - 1] + dp[i - 1][w - weights[i - 1]],
                    dp[i - 1][w]
                );
            } else {
                dp[i][w] = dp[i - 1][w];
            }
        }
    }

    return dp[n][W];
}

```

---

### 🖥️ **Example**

```
js
CopyEdit
const weights = [1, 3, 4, 5];
const values = [1, 4, 5, 7];
const capacity = 7;

console.log(knapsack(weights, values, capacity)); // Output: 9

```

---

### ✅ **What to Do With It**

- Use it when you need to **optimize value** within a limited capacity.
- Think recursively, then optimize using memoization or tabulation.
- Pay attention to constraints (e.g., capacity and item count).

---

### 🚫 **What Not to Do With It**

- Don't use recursion without memoization for large inputs — it will lead to **TLE (Time Limit Exceeded)**.
- Don’t confuse 0/1 Knapsack with **Unbounded Knapsack** (where items can be reused).

---

### 📚 **Learn More**

- **Aditya Verma’s DP playlist** (YouTube) – very beginner-friendly explanation.
- **"Introduction to Algorithms" by Cormen (CLRS)** – Chapter 16.
- **Leetcode** problems: 416 (Partition Equal Subset Sum), 474 (Ones and Zeroes), 494 (Target Sum)

### **Unbounded Knapsack Problem**

---

### 📖 **Definition**

The **Unbounded Knapsack Problem** is a variation of the 0/1 Knapsack where **you can include the same item multiple times**. Each item has a **weight** and a **value**, and the goal is to maximize the total value within the given knapsack capacity.

---

### 🧠 **Key Concepts**

- **Unlimited supply**: You can choose an item as many times as it fits.
- **Only one parameter changes in subproblem**: Capacity decreases, but the item index stays the same when we include it again.
- **Optimal substructure** and **overlapping subproblems** apply here too.

---

### ✅ **Recursive Relation**

For each item `i` and capacity `W`:

```
swift
CopyEdit
dp[i][W] = max(
    dp[i - 1][W],                          // Don’t take the item
    value[i] + dp[i][W - weight[i]]       // Take the item (again)
)

```

---

### 💡 **Approach 1: Recursive (with Memoization)**

```
js
CopyEdit
function unboundedKnapsack(weights, values, n, W, memo = {}) {
    const key = `${n}-${W}`;
    if (key in memo) return memo[key];

    if (n === 0 || W === 0) return 0;

    if (weights[n - 1] <= W) {
        const take = values[n - 1] + unboundedKnapsack(weights, values, n, W - weights[n - 1], memo);
        const skip = unboundedKnapsack(weights, values, n - 1, W, memo);
        memo[key] = Math.max(take, skip);
    } else {
        memo[key] = unboundedKnapsack(weights, values, n - 1, W, memo);
    }

    return memo[key];
}

```

---

### 💡 **Approach 2: Bottom-Up DP (Tabulation)**

```
js
CopyEdit
function unboundedKnapsack(weights, values, W) {
    const n = weights.length;
    const dp = Array(W + 1).fill(0);

    for (let w = 0; w <= W; w++) {
        for (let i = 0; i < n; i++) {
            if (weights[i] <= w) {
                dp[w] = Math.max(dp[w], values[i] + dp[w - weights[i]]);
            }
        }
    }

    return dp[W];
}

```

---

### 🖥️ **Example**

```
js
CopyEdit
const weights = [2, 3, 4];
const values = [40, 50, 60];
const capacity = 8;

console.log(unboundedKnapsack(weights, values, capacity)); // Output: 160

```

Explanation: Take two items of weight 4 (value 60 each) = 120, or one 4 and two 2s, etc.

---

### ✅ **What to Do With It**

- Use when **repetition of items is allowed** (e.g., coins, rods, unlimited stock).
- Optimize for either value maximization or minimum cost.
- Convert 2D `dp[i][w]` to 1D `dp[w]` for space optimization.

---

### 🚫 **What Not to Do With It**

- Don’t treat it the same as 0/1 Knapsack — logic differs.
- Avoid recomputing solutions for same capacity repeatedly — memoize or tabulate!

---

### 📚 **Learn More**

- **"Introduction to Algorithms" (CLRS)** – Chapter 16 (as extension of 0/1 Knapsack).
- **"Grokking Algorithms"** – Not directly covered, but inferred from patterns in DP.
- **"Algorithms" by Robert Sedgewick** – Chapter on Dynamic Programming, Knapsack variations.

### **Longest Common Subsequence (LCS)**

---

### 📖 **Definition**

The **Longest Common Subsequence (LCS)** is the longest sequence that appears **in the same relative order** (not necessarily contiguous) in **both strings**.

Example:

For strings `"abcde"` and `"ace"`, the LCS is `"ace"`.

---

### 📐 **Recursive Relation**

If `s1[i] === s2[j]`

→ `1 + lcs(i-1, j-1)`

Else

→ `max(lcs(i-1, j), lcs(i, j-1))`

---

### 💡 **Approach 1: Recursive (with Memoization)**

```
js
CopyEdit
function lcs(s1, s2, i = s1.length, j = s2.length, memo = {}) {
    const key = `${i}-${j}`;
    if (key in memo) return memo[key];

    if (i === 0 || j === 0) return 0;

    if (s1[i - 1] === s2[j - 1]) {
        memo[key] = 1 + lcs(s1, s2, i - 1, j - 1, memo);
    } else {
        memo[key] = Math.max(
            lcs(s1, s2, i - 1, j, memo),
            lcs(s1, s2, i, j - 1, memo)
        );
    }

    return memo[key];
}

```

---

### 💡 **Approach 2: Bottom-Up DP (Tabulation)**

```
js
CopyEdit
function lcs(s1, s2) {
    const m = s1.length, n = s2.length;
    const dp = Array.from({ length: m + 1 }, () => Array(n + 1).fill(0));

    for (let i = 1; i <= m; i++) {
        for (let j = 1; j <= n; j++) {
            if (s1[i - 1] === s2[j - 1]) {
                dp[i][j] = 1 + dp[i - 1][j - 1];
            } else {
                dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
            }
        }
    }

    return dp[m][n];
}

```

---

### 🖥️ **Example**

```
js
CopyEdit
const s1 = "abcde";
const s2 = "ace";

console.log(lcs(s1, s2)); // Output: 3 ("ace")

```

---

### ✅ **What to Do With It**

- Use when comparing **sequences or strings** (DNA sequences, diff tools, etc.).
- Great for solving **Edit Distance**, **Minimum Insert/Delete**, and **LPS** (Longest Palindromic Subsequence) problems.
- Always use memoization or tabulation to prevent exponential recursion.

---

### 🚫 **What Not to Do With It**

- Don’t confuse LCS with **Longest Common Substring** (which is contiguous).
- Avoid brute force approach on long strings — complexity is O(m * n), so optimize.

---

### 📚 **Learn More**

- **"Introduction to Algorithms (CLRS)"** – Chapter 15: Dynamic Programming
- **"Grokking Algorithms"** – Not directly covered, but dynamic programming patterns apply
- **"Algorithms by Robert Sedgewick"** – Refer to chapters on string processing or dynamic programming

### **Longest Increasing Subsequence (LIS)**

---

### 📖 **Definition**

The **Longest Increasing Subsequence (LIS)** is the longest subsequence in a given array such that **all elements are in increasing order**, and **not necessarily contiguous**.

Example:

For `arr = [10, 9, 2, 5, 3, 7, 101, 18]`

The LIS is `[2, 3, 7, 101]` with length `4`.

---

### 🧠 **Approach 1: Dynamic Programming (O(n²))**

```
js
CopyEdit
function lengthOfLIS(nums) {
  const n = nums.length;
  const dp = Array(n).fill(1);

  for (let i = 1; i < n; i++) {
    for (let j = 0; j < i; j++) {
      if (nums[i] > nums[j]) {
        dp[i] = Math.max(dp[i], dp[j] + 1);
      }
    }
  }

  return Math.max(...dp);
}

```

---

### 🧠 **Approach 2: Binary Search + Greedy (O(n log n))**

```
js
CopyEdit
function lengthOfLIS(nums) {
  const sub = [];

  for (let num of nums) {
    let left = 0, right = sub.length;

    while (left < right) {
      let mid = Math.floor((left + right) / 2);
      if (sub[mid] < num) left = mid + 1;
      else right = mid;
    }

    sub[left] = num;
  }

  return sub.length;
}

```

---

### 🖥️ **Example**

```
js
CopyEdit
const arr = [10, 9, 2, 5, 3, 7, 101, 18];
console.log(lengthOfLIS(arr)); // Output: 4

```

---

### ✅ **What to Do With It**

- Use for problems involving **subsequence optimizations**.
- Apply binary search-based method when performance matters.
- Know it's foundational for problems like:
    - Russian Doll Envelopes
    - Maximum Height of Stackable Boxes

---

### 🚫 **What Not to Do With It**

- Don't confuse with **subarrays** — subsequence elements aren’t required to be adjacent.
- Avoid brute force (2ⁿ) – extremely slow for large inputs.

---

### 📚 **Learn More**

- **"Introduction to Algorithms (CLRS)"** – Chapter 15 (Dynamic Programming)
- **"Grokking Algorithms"** – Not explicitly mentioned, but builds intuition for it
- **"Algorithms by Robert Sedgewick"** – Section on Sorting and Searching (binary search concept reuse)

### **Matrix Chain Multiplication**

---

### 📖 **Definition**

Matrix Chain Multiplication is a classic **Dynamic Programming** problem where the goal is to **find the most efficient way to multiply a chain of matrices**.

It focuses on minimizing the total number of scalar multiplications.

Note: Matrix multiplication is associative:

A × (B × C) = (A × B) × C

…but the number of operations may vary!

---

### 📌 **Problem Statement**

Given an array `arr[]` of size `n` that represents the dimensions of matrices such that the `i-th` matrix has dimensions `(arr[i-1] x arr[i])`, find the minimum number of scalar multiplications needed to multiply the entire chain.

---

### 🧠 **Approach: Dynamic Programming (Bottom-Up)**

```
js
CopyEdit
function matrixChainOrder(arr) {
  const n = arr.length;
  const dp = Array.from({ length: n }, () => Array(n).fill(0));

  for (let len = 2; len < n; len++) {
    for (let i = 1; i < n - len + 1; i++) {
      let j = i + len - 1;
      dp[i][j] = Infinity;

      for (let k = i; k < j; k++) {
        const cost = dp[i][k] + dp[k + 1][j] + arr[i - 1] * arr[k] * arr[j];
        if (cost < dp[i][j]) {
          dp[i][j] = cost;
        }
      }
    }
  }

  return dp[1][n - 1];
}

```

---

### 🖥️ **Example**

```
js
CopyEdit
const arr = [40, 20, 30, 10, 30];
// Matrices: A1(40x20), A2(20x30), A3(30x10), A4(10x30)

console.log(matrixChainOrder(arr));
// Output: 26000

```

---

### ✅ **What to Do With It**

- Use when:
    - Order of operations affects performance.
    - Optimizing cost of matrix multiplication.
- Understand it as a foundational problem in:
    - DP optimization
    - Compiler optimization (parsing, instruction ordering)

---

### 🚫 **What Not to Do With It**

- Don't attempt all permutations (brute force is O(2ⁿ) and infeasible).
- Don't forget that matrix multiplication is **not commutative** (A × B ≠ B × A).

---

### 📚 **Learn More**

- **"Introduction to Algorithms (CLRS)"** – Chapter 15.2: Matrix-Chain Multiplication
- **"Algorithms by Robert Sedgewick"** – Not covered in depth
- **"Grokking Algorithms"** – Not included, but pairs well with DP topics

### **Coin Change Problem**

---

### 📖 **Definition**

The **Coin Change** problem asks:

> “Given a set of coin denominations and a target amount, what’s the minimum number of coins required to make up that amount?”
> 

It’s a classic **Dynamic Programming** problem that models the **optimal substructure** and **overlapping subproblems** properties.

There are two common variations:

1. **Minimum coins to make a value** *(this one is covered here)*
2. **Count of ways to make the value** (variation used in Unbounded Knapsack)

---

### 📌 **Problem Statement**

Given an array `coins[]` of distinct coin denominations and an integer `amount`, return the **fewest number of coins** needed to make up that amount.

If it's not possible, return `-1`.

---

### 🧠 **Approach: Dynamic Programming (Bottom-Up)**

```
js
CopyEdit
function coinChange(coins, amount) {
  const dp = new Array(amount + 1).fill(Infinity);
  dp[0] = 0;

  for (let coin of coins) {
    for (let i = coin; i <= amount; i++) {
      dp[i] = Math.min(dp[i], dp[i - coin] + 1);
    }
  }

  return dp[amount] === Infinity ? -1 : dp[amount];
}

```

---

### 🖥️ **Example**

```
js
CopyEdit
const coins = [1, 2, 5];
const amount = 11;

console.log(coinChange(coins, amount));
// Output: 3 (5 + 5 + 1)

```

---

### ✅ **What to Do With It**

- Use for **unbounded knapsack**type problems (repeating items).
- Efficiently solve monetary change, partitioning, or combination problems.
- Know the time complexity: `O(n * amount)` where `n` = number of coin types.

---

### 🚫 **What Not to Do With It**

- Don’t use a greedy approach unless coins are canonical (e.g., US coins).
    - e.g., `coins = [1, 3, 4]`, amount = 6 → greedy gives 1+1+4, but optimal is 3+3.
- Avoid recursive brute-force (exponential time) without memoization.

---

### 📚 **Learn More**

- **"Introduction to Algorithms (CLRS)"** – Chapter 15.3: Dynamic Programming examples
- **"Grokking Algorithms"** – Chapter 9: Dynamic Programming
- **"Algorithms by Robert Sedgewick"** – Not directly covered

### **Fibonacci Variants**

---

### 📖 **Definition**

The **Fibonacci sequence** is a classic problem where:

> F(n) = F(n-1) + F(n-2) with base cases F(0) = 0, F(1) = 1
> 

Fibonacci and its variants appear in many **Dynamic Programming** and **recurrence-based** problems, such as climbing stairs, tiling problems, or decoding messages.

---

### 📌 **Standard Fibonacci: Recursive + Memoized + Iterative**

### 1. **Recursive with Memoization (Top-Down DP)**

```
js
CopyEdit
function fib(n, memo = {}) {
  if (n <= 1) return n;
  if (memo[n]) return memo[n];
  memo[n] = fib(n - 1, memo) + fib(n - 2, memo);
  return memo[n];
}

```

### 2. **Iterative (Bottom-Up DP)**

```
js
CopyEdit
function fib(n) {
  if (n <= 1) return n;
  let a = 0, b = 1;
  for (let i = 2; i <= n; i++) {
    let temp = a + b;
    a = b;
    b = temp;
  }
  return b;
}

```

---

### 🔄 **Common Fibonacci Variants**

### 1. **Climbing Stairs**

> Each step you can either take 1 or 2 steps. How many ways to climb n steps?
> 

```
js
CopyEdit
function climbStairs(n) {
  if (n <= 2) return n;
  let a = 1, b = 2;
  for (let i = 3; i <= n; i++) {
    let temp = a + b;
    a = b;
    b = temp;
  }
  return b;
}

```

### 2. **Tiling Problem**

> Given a 2×n board and tiles of size 2×1, how many ways can you tile the board?
> 

Same recurrence as Fibonacci:

```
js
CopyEdit
function tilingWays(n) {
  if (n <= 2) return n;
  let a = 1, b = 2;
  for (let i = 3; i <= n; i++) {
    let temp = a + b;
    a = b;
    b = temp;
  }
  return b;
}

```

### 3. **Decode Ways (Leetcode #91)**

> Given a string of digits representing A-Z ('1' -> 'A', '26' -> 'Z'), how many ways can you decode?
> 

More complex but related to Fibonacci (when analyzing length-1 and length-2 chunks).

---

### ✅ **What to Do With It**

- Recognize and reduce problems to Fibonacci recurrence.
- Optimize recursive solutions with **memoization** or **bottom-up iteration**.
- Use `O(1)` space if only last two states are needed.

---

### 🚫 **What Not to Do With It**

- Don’t use plain recursion for large `n` — exponential time.
- Don’t forget base cases (especially `n = 0`, `n = 1`).
- Don’t recompute overlapping subproblems – always memoize or tabulate.

---

### 📚 **Learn More**

- **"Introduction to Algorithms (CLRS)"** – Chapter 15.1: Introduction to DP with Fibonacci
- **"Grokking Algorithms"** – Chapter 9: Dynamic Programming
- **"Algorithms by Robert Sedgewick"** – Not directly covered

### **DP on Trees / Graphs**

---

### 📖 **Definition**

**Dynamic Programming on Trees/Graphs** is the technique of solving problems over non-linear structures like **trees** or **DAGs** by combining results from child nodes or subgraphs. This involves **bottom-up traversal (post-order DFS)** and using **memoization** to avoid recomputation.

It’s used in problems where substructure of the graph (typically a tree or DAG) can be used to solve the whole.

---

### ⚙️ **General Syntax Pattern**

```
js
CopyEdit
function dfs(node, parent) {
  let result = 0;
  for (let neighbor of graph[node]) {
    if (neighbor === parent) continue;
    result += dfs(neighbor, node);
  }
  dp[node] = result;
  return dp[node];
}

```

---

### 🔍 **Examples**

### 1. **Diameter of a Tree**

> Longest path between any two nodes in a tree.
> 

```
js
CopyEdit
function treeDiameter(edges) {
  const n = edges.length + 1;
  const graph = Array.from({ length: n }, () => []);
  for (let [u, v] of edges) {
    graph[u].push(v);
    graph[v].push(u);
  }

  let diameter = 0;

  function dfs(node, parent) {
    let max1 = 0, max2 = 0;
    for (let child of graph[node]) {
      if (child === parent) continue;
      let depth = dfs(child, node);
      if (depth > max1) {
        max2 = max1;
        max1 = depth;
      } else if (depth > max2) {
        max2 = depth;
      }
    }
    diameter = Math.max(diameter, max1 + max2);
    return max1 + 1;
  }

  dfs(0, -1);
  return diameter;
}

```

---

### 2. **House Robber III (Leetcode #337)**

> Can't rob both parent and child – classic DP on binary tree.
> 

```
js
CopyEdit
function rob(root) {
  function dfs(node) {
    if (!node) return [0, 0]; // [robbed, notRobbed]

    let [leftRob, leftNoRob] = dfs(node.left);
    let [rightRob, rightNoRob] = dfs(node.right);

    let robNode = node.val + leftNoRob + rightNoRob;
    let notRobNode = Math.max(leftRob, leftNoRob) + Math.max(rightRob, rightNoRob);

    return [robNode, notRobNode];
  }

  return Math.max(...dfs(root));
}

```

---

### ✅ **What to Do With It**

- Always **traverse in post-order DFS** for bottom-up DP.
- Use recursion with memoization (`Map` or object if tree/graph is big).
- Identify **overlapping subproblems** and reuse results.
- Watch for **root vs non-root** decisions (e.g., subtree excluding root).

---

### 🚫 **What Not to Do With It**

- Don’t apply regular DP tabulation directly — not ideal for tree structures.
- Avoid revisiting nodes in general graph — use visited checks or memoization.
- Don’t forget **base cases** like `null` nodes or leaf nodes.

---

### 📚 **Learn More**

- **"Introduction to Algorithms (CLRS)"** – Not covered in depth as “DP on Trees” but recursion & DAGs in Chapters 15–24.
- **"Grokking Algorithms"** – Chapter 10: Graph algorithms (applies in parts)
- **"Algorithms by Robert Sedgewick"** – Graph algorithms + DFS usage

### **Sliding Window Pattern**

---

### 📖 **Definition**

The **Sliding Window** pattern is used to reduce nested loops into a single loop by creating a “window” which slides over the data to inspect a subset at a time. Ideal for solving problems involving **subarrays**, **strings**, or **continuous segments**.

Used when we need to:

- Find the **maximum/minimum**, **sum**, or **length** of a subarray with certain properties.
- Work with **contiguous blocks** of elements.

---

### ⚙️ **Syntax / Pseudocode (Fixed Size)**

```
js
CopyEdit
function maxSumSubarray(arr, k) {
  let maxSum = 0, windowSum = 0;

  for (let i = 0; i < k; i++) {
    windowSum += arr[i];
  }

  maxSum = windowSum;

  for (let i = k; i < arr.length; i++) {
    windowSum += arr[i] - arr[i - k];
    maxSum = Math.max(maxSum, windowSum);
  }

  return maxSum;
}

```

---

### 🔍 **Examples**

### 1. **Fixed-Size Sliding Window**

**Problem:** Find max sum of a subarray of size `k`.

```
js
CopyEdit
function maxSum(arr, k) {
  let maxSum = 0, windowSum = 0;

  for (let i = 0; i < k; i++) {
    windowSum += arr[i];
  }

  maxSum = windowSum;

  for (let i = k; i < arr.length; i++) {
    windowSum += arr[i] - arr[i - k];
    maxSum = Math.max(maxSum, windowSum);
  }

  return maxSum;
}

maxSum([2, 1, 5, 1, 3, 2], 3); // Output: 9

```

---

### 2. **Variable-Size Sliding Window**

**Problem:** Smallest subarray with sum ≥ target.

```
js
CopyEdit
function minSubArrayLen(target, nums) {
  let left = 0, sum = 0, minLen = Infinity;

  for (let right = 0; right < nums.length; right++) {
    sum += nums[right];

    while (sum >= target) {
      minLen = Math.min(minLen, right - left + 1);
      sum -= nums[left++];
    }
  }

  return minLen === Infinity ? 0 : minLen;
}

```

---

### ✅ **What to Do With It**

- Use for problems with **contiguous elements** and **running values** (sum, max, etc.).
- Decide between **fixed window size** and **dynamic/variable size** early.
- Keep track of window bounds (`left`, `right`).

---

### 🚫 **What Not to Do With It**

- Don’t use it when elements aren’t **consecutive** or **indexed**.
- Avoid recalculating entire windows — **reuse the previous result**.

---

### 📚 **Learn More**

- **"Grokking Algorithms"** – Indirectly covered through examples (use-case-based)
- **"Algorithms by Robert Sedgewick"** – Not a named concept but used in array/sorting/searching patterns
- **"CLRS"** – Not directly named as a pattern, but underlying logic appears in dynamic programming and optimization problems

### **Two Pointers Pattern**

---

### 📖 **Definition**

The **Two Pointers** technique involves using two indices (or pointers) to iterate through a structure (typically an array or string) in a **coordinated** way. It’s commonly used to:

- Traverse from both ends toward the center.
- Traverse from the start and move pointers based on some condition.
- Eliminate nested loops in sorted arrays.

---

### ⚙️ **Syntax / Pseudocode**

**Basic Form:**

```
js
CopyEdit
function twoSumSorted(arr, target) {
  let left = 0, right = arr.length - 1;

  while (left < right) {
    const sum = arr[left] + arr[right];

    if (sum === target) return [left, right];
    if (sum < target) left++;
    else right--;
  }

  return [];
}

```

---

### 🔍 **Examples**

### 1. **Two Sum in a Sorted Array**

```
js
CopyEdit
function twoSum(arr, target) {
  let left = 0, right = arr.length - 1;

  while (left < right) {
    const sum = arr[left] + arr[right];
    if (sum === target) return [left, right];
    if (sum < target) left++;
    else right--;
  }

  return [];
}

twoSum([1, 2, 3, 4, 6], 6); // Output: [1, 3]

```

---

### 2. **Remove Duplicates from Sorted Array**

```
js
CopyEdit
function removeDuplicates(nums) {
  if (nums.length === 0) return 0;

  let i = 0;

  for (let j = 1; j < nums.length; j++) {
    if (nums[j] !== nums[i]) {
      i++;
      nums[i] = nums[j];
    }
  }

  return i + 1;
}

```

---

### 3. **Palindrome Check**

```
js
CopyEdit
function isPalindrome(s) {
  let left = 0, right = s.length - 1;

  while (left < right) {
    if (s[left] !== s[right]) return false;
    left++;
    right--;
  }

  return true;
}

```

---

### ✅ **What to Do With It**

- Apply on **sorted arrays** or **strings**.
- Use when you're reducing the **search space** from both sides.
- Great for problems involving **pairs**, **triplets**, or **palindromes**.

---

### 🚫 **What Not to Do With It**

- Don’t use on **unsorted data** without preprocessing (e.g., sorting).
- Avoid overcomplicating it—know when a simple linear loop is enough.

---

### 📚 **Learn More**

- **"Grokking Algorithms"** – Covered indirectly in pair-based problems.
- **"Introduction to Algorithms (CLRS)"** – Used in sorting/searching problems.
- **"Algorithms by Robert Sedgewick"** – Chapter on "Sorting and Searching"

### **Fast & Slow Pointers (Floyd’s Cycle Detection)**

---

### 📖 **Definition**

The **Fast & Slow Pointers** technique, also known as **Floyd’s Cycle Detection Algorithm**, is used to detect **cycles** in linked lists or arrays, where two pointers move at different speeds. This technique is most famous for detecting cycles in **linked lists** but can also be applied to problems where two entities are moving through a collection.

- The **slow pointer** advances by one step at a time.
- The **fast pointer** advances by two steps at a time.

If there is a cycle, the fast pointer will eventually meet the slow pointer.

---

### ⚙️ **Syntax / Pseudocode**

```
js
CopyEdit
function hasCycle(head) {
  let slow = head, fast = head;

  while (fast !== null && fast.next !== null) {
    slow = slow.next;
    fast = fast.next.next;

    if (slow === fast) {
      return true;  // Cycle detected
    }
  }

  return false;  // No cycle
}

```

---

### 🔍 **Examples**

### 1. **Cycle Detection in Linked List (Floyd's Cycle Algorithm)**

**Problem:** Detect if a given linked list has a cycle.

```
js
CopyEdit
function hasCycle(head) {
  let slow = head, fast = head;

  while (fast !== null && fast.next !== null) {
    slow = slow.next;        // Slow moves one step
    fast = fast.next.next;   // Fast moves two steps

    if (slow === fast) {     // If they meet, there's a cycle
      return true;
    }
  }

  return false;  // If fast pointer reaches the end, no cycle
}

```

**Example:**

- Input: `1 -> 2 -> 3 -> 4 -> 5 -> 2` (Cycle at node 2)
- Output: `true` (Cycle detected)

---

### 2. **Find the Start of the Cycle (Floyd's Cycle Algorithm)**

**Problem:** Find the node where the cycle begins in a linked list.

```
js
CopyEdit
function detectCycle(head) {
  let slow = head, fast = head;

  // Step 1: Check if there is a cycle
  while (fast !== null && fast.next !== null) {
    slow = slow.next;
    fast = fast.next.next;

    if (slow === fast) {
      // Step 2: Find the entry point of the cycle
      let entry = head;
      while (entry !== slow) {
        entry = entry.next;
        slow = slow.next;
      }
      return entry;
    }
  }

  return null;  // No cycle
}

```

---

### 3. **Detect Palindrome in Linked List Using Fast and Slow Pointers**

**Problem:** Check if a given linked list is a palindrome.

```
js
CopyEdit
function isPalindrome(head) {
  let slow = head, fast = head;

  // Step 1: Find the middle of the linked list using fast and slow pointers
  while (fast !== null && fast.next !== null) {
    slow = slow.next;
    fast = fast.next.next;
  }

  // Step 2: Reverse the second half of the list
  let prev = null;
  while (slow !== null) {
    let nextNode = slow.next;
    slow.next = prev;
    prev = slow;
    slow = nextNode;
  }

  // Step 3: Compare the first half and reversed second half
  let left = head, right = prev;
  while (right !== null) {
    if (left.val !== right.val) return false;
    left = left.next;
    right = right.next;
  }

  return true;
}

```

---

### ✅ **What to Do With It**

- Use this pattern when you suspect a **cycle** in linked lists or cyclic data structures.
- Fast & Slow pointers are useful for problems involving **duplicates**, **repeated patterns**, or **palindromes**.
- If you find yourself needing to **detect patterns** or **cycle dependencies**, this pattern is very effective.

---

### 🚫 **What Not to Do With It**

- Don't use this pattern in **non-cyclical data structures**.
- Avoid using it in unsorted data where cycle detection doesn't apply.

---

### 📚 **Learn More**

- **"Grokking Algorithms"** – Covers cycle detection and linked list problems.
- **"Introduction to Algorithms (CLRS)"** – Chapter 10, offers detailed analysis of cycle detection using Floyd’s algorithm.
- **"Algorithms by Robert Sedgewick"** – Chapter 5: Linked Lists

### **Binary Search on Answer**

---

### 📖 **Definition**

**Binary Search on Answer** is a technique where we apply binary search not directly on the data, but on the **range of possible answers**. It's typically used when the problem can be framed as finding an optimal solution within a **continuous** range of values. The range is usually determined by the problem constraints, and we iteratively check the feasibility of the current middle point using a **greedy check** or **feasibility check**.

This approach is often used in optimization problems, such as:

- Finding the **minimum** or **maximum** possible answer that satisfies some condition.
- Problems involving **time**, **space**, or other parameters where the answer lies in a **bounded range**.

---

### ⚙️ **Syntax / Pseudocode**

```
js
CopyEdit
function binarySearchOnAnswer(low, high) {
  let left = low, right = high;

  while (left < right) {
    let mid = Math.floor((left + right) / 2);

    if (isFeasible(mid)) {   // Check if mid is a valid answer
      right = mid;           // If yes, try a smaller range
    } else {
      left = mid + 1;        // If no, try a larger range
    }
  }

  return left;  // or right, since both will be equal
}

```

---

### 🔍 **Examples**

### 1. **Minimum Time to Paint Walls**

**Problem:** You have `n` walls to paint, and each wall has a certain number of units of paint required. You need to determine the minimum time `T` such that you can paint all the walls in `T` units of time, assuming there are `k` workers and each worker can paint one unit of the wall per unit time.

We need to find the smallest `T` where all the walls can be painted within that time.

```
js
CopyEdit
function minTimeToPaint(walls, k) {
  let left = Math.max(...walls);  // The minimum time can't be less than the biggest wall
  let right = walls.reduce((a, b) => a + b, 0);  // The max time is the sum of all wall times

  function isFeasible(time) {
    let workers = 1, timeSpent = 0;

    for (let i = 0; i < walls.length; i++) {
      if (timeSpent + walls[i] > time) {
        workers++;
        timeSpent = walls[i];
      } else {
        timeSpent += walls[i];
      }
    }

    return workers <= k;  // If workers needed is less than or equal to k, the time is feasible
  }

  while (left < right) {
    let mid = Math.floor((left + right) / 2);

    if (isFeasible(mid)) {
      right = mid;  // Try to find a smaller time
    } else {
      left = mid + 1;  // Try larger times
    }
  }

  return left;  // The smallest feasible time
}

minTimeToPaint([1, 2, 3, 4, 5], 2);  // Output: 6

```

**Explanation:**

- We use binary search on the possible values of `T` (time) between the maximum wall size and the total sum of all walls.
- For each value of `mid`, we check if it's feasible to paint the walls within that time using `k` workers.

---

### 2. **Allocate Minimum Number of Pages to Students (Book Allocation Problem)**

**Problem:** Given `n` books and `m` students, allocate the books to students such that the maximum number of pages assigned to a student is minimized. You need to find the **minimum** maximum number of pages assigned to any student.

```
js
CopyEdit
function allocateBooks(books, students) {
  let left = Math.max(...books);  // Minimum pages a student must read is at least the largest book
  let right = books.reduce((a, b) => a + b, 0);  // Maximum is the total sum of pages

  function isFeasible(pages) {
    let studentCount = 1, currentSum = 0;

    for (let i = 0; i < books.length; i++) {
      if (currentSum + books[i] > pages) {
        studentCount++;
        currentSum = books[i];
      } else {
        currentSum += books[i];
      }
    }

    return studentCount <= students;  // If students required is within the limit, it's feasible
  }

  while (left < right) {
    let mid = Math.floor((left + right) / 2);

    if (isFeasible(mid)) {
      right = mid;  // Try smaller values to minimize the max pages
    } else {
      left = mid + 1;  // Try larger values
    }
  }

  return left;  // The minimum max pages
}

allocateBooks([12, 34, 67, 90], 2);  // Output: 113

```

**Explanation:**

- We use binary search to minimize the maximum number of pages a student has to read.
- For each mid value, we check if it's feasible to allocate the books within that range, where no student gets more than `mid` pages.

---

### ✅ **What to Do With It**

- Use this technique when you need to find an **optimal answer** (e.g., minimum or maximum) within a defined range.
- It is most effective when the problem can be reduced to a **feasibility check** for each potential answer.
- This pattern is useful in problems involving **time**, **space**, or other **continuous parameters** (e.g., minimizing/maximizing resources).

---

### 🚫 **What Not to Do With It**

- Don’t use this technique when the problem does not involve a **searchable range** or is not about optimizing some parameter.
- Avoid using binary search in problems that **require brute force** or do not have a feasible check at each middle point.

---

### 📚 **Learn More**

- **"Grokking Algorithms"** – Chapter on Binary Search and optimization problems.
- **"Introduction to Algorithms (CLRS)"** – Section on binary search applications.
- **"Algorithms by Robert Sedgewick"** – Techniques for optimization problems involving binary search.

### **Greedy Algorithms + Sorting**

---

### 📖 **Definition**

**Greedy algorithms** make the locally optimal choice at each stage with the hope of finding a global optimum. The core idea is to solve optimization problems by selecting the best choice available at each step. These algorithms work well when the problem has the **greedy-choice property** and **optimal substructure**.

Sorting often plays a crucial role in greedy algorithms. Many greedy algorithms involve sorting the input data first before making decisions. Sorting ensures that the greedy approach works by processing elements in the most effective order.

---

### ⚙️ **Syntax / Pseudocode**

```
js
CopyEdit
// Greedy algorithm with sorting
function greedyAlgorithm(arr) {
  // Sort the array in desired order (e.g., ascending or descending)
  arr.sort((a, b) => a - b);  // Example: Sorting in ascending order

  let result = [];

  for (let i = 0; i < arr.length; i++) {
    // Make a greedy choice and add to the result
    result.push(arr[i]);
  }

  return result;
}

```

---

### 🔍 **Examples**

### 1. **Activity Selection Problem**

**Problem:** Given `n` activities with start and finish times, select the maximum number of activities that don't overlap.

```
js
CopyEdit
function activitySelection(activities) {
  // Sort activities based on finish time
  activities.sort((a, b) => a[1] - b[1]);

  let selectedActivities = [];
  let lastFinishTime = -1;

  for (let i = 0; i < activities.length; i++) {
    // If activity's start time is after the last finish time, select it
    if (activities[i][0] > lastFinishTime) {
      selectedActivities.push(activities[i]);
      lastFinishTime = activities[i][1];
    }
  }

  return selectedActivities;
}

// Example usage
activitySelection([[1, 3], [2, 5], [4, 6], [7, 8], [5, 7]]);
// Output: [[1, 3], [4, 6], [7, 8]]

```

**Explanation:**

- The activities are sorted by their finish times.
- Then, we iteratively select the activities whose start time is later than the finish time of the previously selected activity.

---

### 2. **Fractional Knapsack Problem**

**Problem:** Given a set of items with their weights and values, and a knapsack with a maximum weight capacity, find the maximum value you can achieve by selecting items (can take fractions of items).

```
js
CopyEdit
function fractionalKnapsack(weights, values, capacity) {
  let n = weights.length;
  let items = [];

  // Create an array of items with value-to-weight ratio
  for (let i = 0; i < n; i++) {
    items.push({ weight: weights[i], value: values[i], ratio: values[i] / weights[i] });
  }

  // Sort items by value-to-weight ratio in descending order
  items.sort((a, b) => b.ratio - a.ratio);

  let totalValue = 0;
  let currentWeight = 0;

  for (let i = 0; i < n; i++) {
    if (currentWeight + items[i].weight <= capacity) {
      // Take the whole item
      currentWeight += items[i].weight;
      totalValue += items[i].value;
    } else {
      // Take the fraction of the item
      let remainingCapacity = capacity - currentWeight;
      totalValue += items[i].value * (remainingCapacity / items[i].weight);
      break;
    }
  }

  return totalValue;
}

// Example usage
fractionalKnapsack([10, 20, 30], [60, 100, 120], 50);
// Output: 240

```

**Explanation:**

- We calculate the value-to-weight ratio for each item.
- Then, we sort the items based on this ratio in descending order.
- We take as much of the highest ratio item as we can until the knapsack is full.

---

### ✅ **What to Do With It**

- **Use Greedy algorithms** when you can make decisions that don't depend on previous choices, and there's an easy way to check if an overall optimal solution can be reached by selecting local optima.
- **Sort** the data before making decisions in problems that involve scheduling, resource allocation, or selecting the best subset of data (e.g., Activity Selection, Fractional Knapsack).
- For optimization problems, first check if the problem can be solved using a greedy approach by **sorting** and making decisions based on the sorted data.

---

### 🚫 **What Not to Do With It**

- Don’t apply greedy algorithms to problems where future decisions depend on past decisions or require backtracking. Greedy algorithms are not guaranteed to work for such problems.
- Avoid using this approach if the problem requires considering **all possible combinations** (e.g., the **0/1 Knapsack Problem**) without considering all solutions.

---

### 📚 **Learn More**

- **"Grokking Algorithms"** – Chapter on Greedy Algorithms and examples like the Activity Selection problem.
- **"Introduction to Algorithms (CLRS)"** – Section on Greedy Algorithms with detailed explanations and proofs.
- **"Algorithms by Robert Sedgewick"** – In-depth coverage of greedy algorithms and sorting-based approaches.

### **Prefix Sum / Difference Arrays**

---

### 📖 **Definition**

- **Prefix Sum Array** is a data structure that helps answer range sum queries efficiently. It is an array where each element at index `i` stores the sum of the elements from the start of the array to index `i`. This allows quick computation of the sum of any subarray.
- **Difference Array** is used to perform range updates efficiently. Instead of updating every element in a range, we update only two positions (the start and the end of the range), and the final array is obtained by taking the prefix sum of the difference array.

---

### ⚙️ **Syntax / Pseudocode**

1. **Prefix Sum Array**

```
js
CopyEdit
function prefixSum(arr) {
  let n = arr.length;
  let prefixSumArr = new Array(n);
  prefixSumArr[0] = arr[0];

  for (let i = 1; i < n; i++) {
    prefixSumArr[i] = prefixSumArr[i - 1] + arr[i];
  }

  return prefixSumArr;
}

function rangeSum(prefixSumArr, left, right) {
  if (left > 0) {
    return prefixSumArr[right] - prefixSumArr[left - 1];
  }
  return prefixSumArr[right];
}

```

1. **Difference Array**

```
js
CopyEdit
function differenceArray(arr, n) {
  let diff = new Array(n + 1).fill(0);

  // Update the difference array for a range [l, r] with value v
  function update(l, r, v) {
    diff[l] += v;
    diff[r + 1] -= v;
  }

  // After all updates, compute the final array
  function getFinalArray() {
    let finalArr = new Array(n);
    finalArr[0] = diff[0];
    for (let i = 1; i < n; i++) {
      finalArr[i] = finalArr[i - 1] + diff[i];
    }
    return finalArr;
  }

  return { update, getFinalArray };
}

```

---

### 🔍 **Examples**

### 1. **Prefix Sum Example**

**Problem:** Given an array, compute the sum of elements between any two indices efficiently.

```
js
CopyEdit
let arr = [1, 2, 3, 4, 5];
let prefixSumArr = prefixSum(arr);

// Get sum of elements from index 1 to 3
console.log(rangeSum(prefixSumArr, 1, 3));  // Output: 9 (2 + 3 + 4)

```

**Explanation:**

- `prefixSumArr = [1, 3, 6, 10, 15]` stores cumulative sums.
- To get the sum of the subarray between index 1 and 3, simply calculate `prefixSumArr[3] - prefixSumArr[0]`.

### 2. **Difference Array Example**

**Problem:** Update the range `[l, r]` of an array by adding a value `v` to every element in the range.

```
js
CopyEdit
let arr = [0, 0, 0, 0, 0];
let { update, getFinalArray } = differenceArray(arr, arr.length);

// Update the range [1, 3] by adding 5
update(1, 3, 5);

// Update the range [2, 4] by adding 2
update(2, 4, 2);

// Get the final array after all updates
let finalArr = getFinalArray();
console.log(finalArr);  // Output: [0, 5, 7, 7, 2]

```

**Explanation:**

- Initially, the array is `[0, 0, 0, 0, 0]`.
- After performing range updates, the difference array helps calculate the final array efficiently: `[0, 5, 7, 7, 2]`.

---

### ✅ **What to Do With It**

- **Use Prefix Sum Array** when you need to answer multiple range sum queries efficiently on a static array.
    - Example: If you have a large array and need to perform many sum queries over ranges, compute the prefix sum array once and answer queries in constant time.
- **Use Difference Array** when you need to perform **range updates** efficiently, especially when updates are frequent and the array is large.
    - Example: When you need to increment elements in a range repeatedly, the difference array allows efficient range updates and final array construction.

---

### 🚫 **What Not to Do With It**

- **Avoid using Prefix Sum for dynamic arrays** where elements are frequently updated, as updating the prefix sum array after each change can be costly (i.e., O(n) per update). Prefix sum arrays are best suited for static or infrequently updated arrays.
- **Avoid using the Difference Array for complex range queries** (other than sum) if the problem involves operations beyond simple additions (e.g., min, max, etc.).

---

### 📚 **Learn More**

- **"Introduction to Algorithms (CLRS)"** – Chapter on Range Queries and Range Updates.
- **"Grokking Algorithms"** – Chapter covering efficient data structures, including prefix sum and difference arrays.
- **"Algorithms by Robert Sedgewick"** – Detailed examples of range updates and cumulative sum queries.

### **Bit Manipulation Patterns**

---

### 📖 **Definition**

Bit manipulation involves operations on the individual bits of a number. These operations are often used to solve problems more efficiently by leveraging the binary representation of numbers. Some common bit manipulation operations are AND, OR, XOR, NOT, left and right shifts.

There are several patterns and tricks in bit manipulation that can optimize solutions for problems involving numbers or arrays.

---

### ⚙️ **Common Bit Manipulation Operations**

1. **AND (`&`)**: Performs bitwise AND between two numbers.
    - Example: `a & b`
2. **OR (`|`)**: Performs bitwise OR between two numbers.
    - Example: `a | b`
3. **XOR (`^`)**: Performs bitwise XOR between two numbers. Returns 1 if bits are different, 0 if the same.
    - Example: `a ^ b`
4. **NOT (`~`)**: Flips all the bits in a number.
    - Example: `~a`
5. **Left Shift (`<<`)**: Shifts all bits of a number to the left by a specified number of positions. This is equivalent to multiplying the number by `2^n`.
    - Example: `a << n`
6. **Right Shift (`>>`)**: Shifts all bits of a number to the right by a specified number of positions. This is equivalent to dividing the number by `2^n`.
    - Example: `a >> n`

---

### ⚡ **Bit Manipulation Patterns**

### 1. **Check if a number is even or odd**

To check if a number is even or odd, you can use the **bitwise AND** operation with `1`.

- **If the least significant bit (LSB) is `1`, the number is odd.**
- **If the LSB is `0`, the number is even.**

```
js
CopyEdit
function isEven(num) {
  return (num & 1) === 0;
}

console.log(isEven(4));  // true (even)
console.log(isEven(5));  // false (odd)

```

### 2. **Counting set bits (Hamming Weight)**

You can count the number of set bits (`1`s) in the binary representation of a number using the **Brian Kernighan’s Algorithm**.

```
js
CopyEdit
function countSetBits(num) {
  let count = 0;
  while (num > 0) {
    num = num & (num - 1); // Remove the rightmost set bit
    count++;
  }
  return count;
}

console.log(countSetBits(5));  // 2 (binary: 101)

```

**Explanation**:

`num & (num - 1)` clears the rightmost set bit in the number. Repeating this process until the number becomes `0` gives the count of set bits.

### 3. **Toggle a specific bit**

To toggle (flip) a specific bit, you use the **XOR (`^`)** operation with a bitmask.

```
js
CopyEdit
function toggleBit(num, bitPosition) {
  return num ^ (1 << bitPosition);  // Toggle the bit at position `bitPosition`
}

console.log(toggleBit(5, 1));  // 7 (binary: 111)

```

**Explanation**:

- `1 << bitPosition` creates a bitmask where only the bit at the given position is set to `1`.
- XORing the number with this bitmask flips the bit at that position.

### 4. **Check if a number is a power of 2**

A number is a power of 2 if it has exactly one set bit. You can use the expression `num & (num - 1)` to check this efficiently.

- **If the result is `0`, the number is a power of 2.**

```
js
CopyEdit
function isPowerOfTwo(num) {
  return (num > 0) && (num & (num - 1)) === 0;
}

console.log(isPowerOfTwo(16));  // true
console.log(isPowerOfTwo(18));  // false

```

**Explanation**:

- The expression `num & (num - 1)` will be `0` if there is only one set bit in the number.

### 5. **Reverse the bits of a number**

To reverse the bits of a number, you can iteratively shift the bits into the correct positions.

```
js
CopyEdit
function reverseBits(num) {
  let result = 0;
  while (num > 0) {
    result = (result << 1) | (num & 1); // Shift result and add the least significant bit of num
    num >>= 1;
  }
  return result;
}

console.log(reverseBits(5));  // 2684354560 (binary: 101 -> 10100000000000000000000000000000)

```

**Explanation**:

The least significant bit of `num` is extracted with `num & 1`, and then `result` is shifted to the left, with the extracted bit added as the new least significant bit.

---

### ✅ **What to Do With It**

- **Use bitwise operations** to solve problems that involve integers or binary representations.
    - Example: Use bit manipulation when you need to efficiently check properties like whether a number is even, odd, or a power of 2.
- **Use bit shifts** to optimize operations that involve powers of 2 or divide/multiply by powers of 2.
- **Leverage XOR** for problems involving toggling or finding duplicates in arrays or sets.
- **Use bit manipulation for optimizing space and time complexity**, especially in problems with constraints involving large numbers or arrays.

---

### 🚫 **What Not to Do With It**

- **Avoid excessive use of bitwise operations** when working with non-integer values, as they are specifically designed for integer manipulation.
- **Don’t overuse bit shifts** in situations where simple arithmetic is sufficient, as it can make code harder to understand.

---

### 📚 **Learn More**

- **"Introduction to Algorithms (CLRS)"** – Chapter on Bitwise Operations and Optimization.
- **"Grokking Algorithms"** – Chapter on basic algorithms and efficient operations.
- **"Algorithms by Robert Sedgewick"** – Insights on bit manipulation in algorithm optimization.

### **Advanced Concepts (Optional)**

---

### **1. Segment Trees / Fenwick Trees (BIT)**

---

### 📖 **Definition**

Segment Trees and Binary Indexed Trees (Fenwick Trees) are advanced data structures used for efficiently solving range query problems and point updates. Both are designed to operate on a sequence of elements and perform operations like range sum, range minimum/maximum, and other similar queries efficiently.

- **Segment Trees**: Typically used when we need to perform range queries and updates on an array, with a time complexity of `O(log n)` for both query and update operations.
- **Fenwick Trees (Binary Indexed Trees)**: A simpler and space-efficient alternative to segment trees, usually used for cumulative frequency or prefix sum queries, with a time complexity of `O(log n)` for both query and update operations.

---

### ⚙️ **Segment Tree**

### **Definition**

A **Segment Tree** is a binary tree used for storing intervals or segments. It allows querying the sum or minimum/maximum of a range in an array in `O(log n)` time.

- It stores information about a range of indices (segments) in a recursive tree structure, where each internal node represents the union of its children (e.g., sum or minimum).
- It requires `O(4n)` space for an array of `n` elements.

### **Use Case**

- Range queries (sum, min, max) on an array.
- Range updates (e.g., adding a value to every element in a range).

### **Syntax / Pseudocode**

```
js
CopyEdit
// Segment Tree construction
function buildSegmentTree(arr) {
  const n = arr.length;
  const tree = new Array(4 * n);

  function build(node, start, end) {
    if (start === end) {
      tree[node] = arr[start];
    } else {
      const mid = Math.floor((start + end) / 2);
      build(2 * node, start, mid);
      build(2 * node + 1, mid + 1, end);
      tree[node] = tree[2 * node] + tree[2 * node + 1]; // For sum queries
    }
  }

  build(1, 0, n - 1);
  return tree;
}

// Range Query (Sum)
function rangeQuery(tree, node, start, end, l, r) {
  if (r < start || l > end) {
    return 0; // No overlap
  }
  if (l <= start && end <= r) {
    return tree[node]; // Total overlap
  }
  const mid = Math.floor((start + end) / 2);
  const left = rangeQuery(tree, 2 * node, start, mid, l, r);
  const right = rangeQuery(tree, 2 * node + 1, mid + 1, end, l, r);
  return left + right;
}

```

### **Example with Code**

```
js
CopyEdit
// Example usage of Segment Tree for range sum
const arr = [1, 3, 5, 7, 9, 11];
const segmentTree = buildSegmentTree(arr);

console.log(rangeQuery(segmentTree, 1, 0, arr.length - 1, 1, 3)); // 15 (3 + 5 + 7)

```

---

### ⚙️ **Fenwick Tree (Binary Indexed Tree)**

### **Definition**

A **Fenwick Tree (BIT)** is an advanced data structure that supports efficient prefix sum queries and point updates. It is a simpler, space-efficient alternative to a segment tree.

- It uses an array to store cumulative frequency information.
- Unlike segment trees, Fenwick trees have a space complexity of `O(n)` and a time complexity of `O(log n)` for both updates and queries.

### **Use Case**

- Efficiently calculate prefix sums.
- Range sum queries by leveraging two prefix sum queries.

### **Syntax / Pseudocode**

```
js
CopyEdit
// Fenwick Tree construction
function buildFenwickTree(arr) {
  const n = arr.length;
  const BIT = new Array(n + 1).fill(0);

  function update(index, value) {
    while (index <= n) {
      BIT[index] += value;
      index += index & -index; // Move to the next index
    }
  }

  // Building the Fenwick Tree
  for (let i = 0; i < n; i++) {
    update(i + 1, arr[i]);
  }

  return BIT;
}

// Range Query (Sum)
function prefixSum(BIT, index) {
  let sum = 0;
  while (index > 0) {
    sum += BIT[index];
    index -= index & -index; // Move to the parent index
  }
  return sum;
}

```

### **Example with Code**

```
js
CopyEdit
// Example usage of Fenwick Tree for range sum
const arr = [1, 3, 5, 7, 9, 11];
const BIT = buildFenwickTree(arr);

// To get the sum of range [1, 3]
const sum = prefixSum(BIT, 3) - prefixSum(BIT, 0); // sum(1, 3) = 3 + 5 + 7 = 15
console.log(sum); // 15

```

---

### ✅ **What to Do With It**

- **Use Segment Trees** when you need to perform range queries and updates on large data efficiently.
    - Common problems: Range sum, range minimum/maximum, range updates.
- **Use Fenwick Trees** when you need to efficiently compute prefix sums and perform point updates.
    - They are often used in problems involving cumulative frequencies or prefix sums.
- Both Segment Trees and Fenwick Trees reduce the complexity of range queries and updates from `O(n)` to `O(log n)`.

---

### 🚫 **What Not to Do With It**

- **Avoid using Segment Trees for small datasets** when simpler data structures (like simple arrays) can solve the problem with lower overhead.
- **Don’t use Fenwick Trees** when you need to perform complex range updates (like range additions), as they do not handle this as efficiently as Segment Trees.

---

### 📚 **Learn More**

- **"Introduction to Algorithms (CLRS)"** – Chapter on Segment Trees.
- **"Grokking Algorithms"** – Chapter on advanced data structures, including Fenwick Trees.
- **"Algorithms by Robert Sedgewick"** – Insights on advanced tree and frequency structures.

### **Pattern Matching Algorithms**

---

### **KMP (Knuth-Morris-Pratt) Algorithm**

---

### 📖 **Definition**

The **KMP algorithm** is a linear time algorithm for pattern matching, i.e., finding a substring (pattern) within a string (text). Unlike the naive approach, which checks each position in the text to see if the pattern matches, KMP uses previously gathered information about the pattern to skip unnecessary comparisons, improving performance.

- **Time Complexity**: `O(n + m)` where `n` is the length of the text and `m` is the length of the pattern.
- **Space Complexity**: `O(m)` for the auxiliary array (LPS array).

---

### ⚙️ **KMP Algorithm**

### **Steps of KMP**

1. **Preprocess the pattern**:
    - Create a "Longest Prefix Suffix" (LPS) array, which stores the length of the longest proper prefix of the pattern which is also a suffix.
2. **Search the text**:
    - Use the LPS array to avoid unnecessary comparisons. If a mismatch happens after some matches, the LPS array tells you the next position in the pattern to check.

### **LPS Array Explanation**

The LPS array helps in skipping parts of the pattern that have already been matched, thus reducing unnecessary checks.

---

### **Syntax / Pseudocode**

```
js
CopyEdit
// KMP Preprocessing (LPS Array)
function computeLPSArray(pattern) {
  const lps = new Array(pattern.length).fill(0);
  let length = 0; // length of the previous longest prefix suffix
  let i = 1;

  while (i < pattern.length) {
    if (pattern[i] === pattern[length]) {
      length++;
      lps[i] = length;
      i++;
    } else {
      if (length !== 0) {
        length = lps[length - 1];
      } else {
        lps[i] = 0;
        i++;
      }
    }
  }
  return lps;
}

// KMP Search Algorithm
function KMPSearch(text, pattern) {
  const lps = computeLPSArray(pattern);
  let i = 0; // index for text
  let j = 0; // index for pattern
  const n = text.length;
  const m = pattern.length;

  while (i < n) {
    if (pattern[j] === text[i]) {
      i++;
      j++;
    }

    if (j === m) {
      console.log(`Pattern found at index ${i - j}`);
      j = lps[j - 1];
    } else if (i < n && pattern[j] !== text[i]) {
      if (j !== 0) {
        j = lps[j - 1];
      } else {
        i++;
      }
    }
  }
}

```

### **Example with Code**

```
js
CopyEdit
// Example usage of KMP Algorithm
const text = "ABABDABACDABABCABAB";
const pattern = "ABABCABAB";
KMPSearch(text, pattern);
// Output: Pattern found at index 10

```

---

### **What to Do With It**

- **Use KMP for efficient pattern matching** in text. It is ideal when you need to search for a pattern multiple times within a string (e.g., string matching problems).
- **Preprocess the pattern once** to get the LPS array, which improves the matching step to linear time `O(n + m)`.

---

### **What Not to Do With It**

- **Avoid using KMP when the pattern is very short or static**, as the preprocessing time (building the LPS array) may not justify the benefits for small patterns.
- **Don’t use KMP when you only need to match a single pattern in a single search**. The brute force method may be simpler and faster in such cases.

---

### 📚 **Learn More**

- **"Introduction to Algorithms (CLRS)"** – Chapter on String Matching.
- **"Grokking Algorithms"** – Chapter on KMP and its applications.

---

---

### **Rabin-Karp Algorithm**

---

### 📖 **Definition**

The **Rabin-Karp algorithm** is a string matching algorithm that uses hashing to find any of a set of pattern strings in a text. It computes a hash value for the pattern and the substrings of the text, and compares them. When the hash values match, a detailed comparison is made.

- **Time Complexity**: `O(n + m)` on average, but can degrade to `O(n * m)` in the worst case (if hash collisions are frequent).
- **Space Complexity**: `O(1)` if the hash is computed in constant time.

---

### ⚙️ **Rabin-Karp Algorithm**

### **Steps of Rabin-Karp**

1. **Hash the pattern**: Compute the hash value of the pattern and each substring of the text.
2. **Compare hashes**: If the hash values match, do a detailed character-by-character comparison of the pattern and the substring.
3. **Sliding window**: Move the window over the text and compute hashes for subsequent substrings.

### **Rolling Hash Function**

A **rolling hash** helps in efficiently updating the hash value of the current window when the window slides.

---

### **Syntax / Pseudocode**

```
js
CopyEdit
// Rabin-Karp Search Algorithm
function rabinKarpSearch(text, pattern) {
  const d = 256; // Number of characters in the input alphabet
  const q = 101; // A prime number
  const m = pattern.length;
  const n = text.length;
  let i = 0;
  let j = 0;
  let p = 0; // Hash value for pattern
  let t = 0; // Hash value for text
  let h = 1; // The value of d^(m-1)

  // Calculate d^(m-1) % q
  for (i = 0; i < m - 1; i++) {
    h = (h * d) % q;
  }

  // Calculate initial hash values for pattern and text
  for (i = 0; i < m; i++) {
    p = (d * p + pattern.charCodeAt(i)) % q;
    t = (d * t + text.charCodeAt(i)) % q;
  }

  // Slide the pattern over the text
  for (i = 0; i <= n - m; i++) {
    if (p === t) {
      // If hash values match, check characters one by one
      for (j = 0; j < m; j++) {
        if (text[i + j] !== pattern[j]) {
          break;
        }
      }
      if (j === m) {
        console.log(`Pattern found at index ${i}`);
      }
    }

    // Calculate hash value for the next window of text
    if (i < n - m) {
      t = (d * (t - text.charCodeAt(i) * h) + text.charCodeAt(i + m)) % q;
      if (t < 0) {
        t += q; // To avoid negative values
      }
    }
  }
}

```

### **Example with Code**

```
js
CopyEdit
// Example usage of Rabin-Karp Algorithm
const text = "ABABDABACDABABCABAB";
const pattern = "ABABCABAB";
rabinKarpSearch(text, pattern);
// Output: Pattern found at index 10

```

---

### **What to Do With It**

- **Use Rabin-Karp when pattern matching needs to be fast on average** and when hash collisions are rare.
- **Use Rabin-Karp when you are searching for multiple patterns** within a text.

---

### **What Not to Do With It**

- **Avoid Rabin-Karp if the probability of hash collisions is high**, as this will degrade performance to a brute-force approach.
- **Don’t use it for large datasets or patterns** unless you can guarantee minimal collisions, or it could perform poorly.

---

### 📚 **Learn More**

- **"Introduction to Algorithms (CLRS)"** – Chapter on String Matching.
- **"Grokking Algorithms"** – Chapter on Rabin-Karp and its use in multiple pattern matching.
- **"Algorithms by Robert Sedgewick"** – Insights on hashing and pattern matching algorithms.

### **Suffix Arrays / Tries**

---

### **Suffix Arrays**

---

### 📖 **Definition**

A **Suffix Array** is a sorted array of all suffixes of a given string. It's used primarily for efficient string matching, searching, and pattern recognition in text. A **suffix** of a string is a substring that starts from any position in the string and goes to the end.

- **Time Complexity**:
    - **Naive Approach**: `O(n^2 log n)` for sorting suffixes.
    - **Efficient Construction**: `O(n log n)` using algorithms like DC3 or Manber & Myers.
- **Space Complexity**: `O(n)` for storing suffix array.

---

### ⚙️ **Suffix Array Construction**

1. **Sort all suffixes of the string**: A suffix is simply a substring that starts from any index of the original string and extends to the end.
2. **Efficient Construction**: The naive approach would involve generating all suffixes and sorting them, but more efficient algorithms like **Manber & Myers** or **DC3** can reduce the time complexity.

---

### **Example: Suffix Array**

Consider the string `"banana"`. The suffixes are:

```
css
CopyEdit
banana
anana
nana
ana
na
a

```

The suffix array is the sorted list of these suffixes:

```
csharp
CopyEdit
[5, 3, 1, 0, 4, 2]

```

The indices in the array correspond to the starting position of the sorted suffixes.

### **Code Example**

```
js
CopyEdit
function suffixArray(str) {
  const suffixes = [];
  const n = str.length;

  // Generate all suffixes of the string
  for (let i = 0; i < n; i++) {
    suffixes.push(str.slice(i));
  }

  // Sort the suffixes lexicographically
  suffixes.sort();

  // Get the starting index of each sorted suffix
  const suffixArray = suffixes.map(suffix => n - suffix.length);
  return suffixArray;
}

// Example usage
const str = "banana";
const suffixArr = suffixArray(str);
console.log(suffixArr); // [5, 3, 1, 0, 4, 2]

```

---

### **Applications of Suffix Arrays**

1. **Efficient String Matching**: Once the suffix array is constructed, searching for a pattern can be done efficiently in logarithmic time (`O(log n)`).
2. **Longest Common Prefix (LCP)**: Suffix arrays can be used in conjunction with **LCP arrays** to efficiently compute the longest common prefix between two suffixes.
3. **Text Compression**: Suffix arrays are useful in various text compression algorithms, including **Burrows-Wheeler Transform**.

---

### **What to Do With It**

- **Use Suffix Arrays** for fast substring searches in large texts.
- **Combine Suffix Arrays** with **LCP arrays** for solving problems related to string matching and pattern recognition.

---

### **What Not to Do With It**

- **Don’t use Suffix Arrays for small strings**. They are more useful in large-scale text search applications.
- **Avoid using Naive Methods** for constructing suffix arrays on very large texts due to the high time complexity.

---

### 📚 **Learn More**

- **"Introduction to Algorithms (CLRS)"** – Chapter on Suffix Arrays.
- **"Advanced Algorithms" by Jeff Erickson** – Insights into suffix arrays and applications.

---

---

### **Tries**

---

### 📖 **Definition**

A **Trie (Prefix Tree)** is a special tree-like data structure used to store a set of strings or prefixes. It allows efficient retrieval of words in a dictionary-like structure. Tries are used for fast searching, insertion, and deletion of strings.

- **Time Complexity**: `O(k)` where `k` is the length of the word being inserted or searched (because each word is processed one character at a time).
- **Space Complexity**: `O(n * k)` where `n` is the number of words, and `k` is the average length of the words.

---

### ⚙️ **Trie Structure**

- Each node in the trie represents a **character** in a string.
- The root node represents an empty string, and each path from the root to a leaf represents a word in the trie.
- **Children of a node** represent characters that can follow the node’s character to form a valid string.

---

### **Trie Operations**

1. **Insert**: Add a word into the trie by inserting characters one by one, creating new nodes as needed.
2. **Search**: Traverse through the trie according to the characters in the word, checking if a path exists for the word.
3. **Delete**: Remove a word by removing nodes that represent characters in the word (if no other words share those characters).

---

### **Code Example**

```
js
CopyEdit
class TrieNode {
  constructor() {
    this.children = {};  // key: character, value: TrieNode
    this.isEndOfWord = false;  // Indicates if the node represents the end of a word
  }
}

class Trie {
  constructor() {
    this.root = new TrieNode();
  }

  // Insert a word into the trie
  insert(word) {
    let node = this.root;
    for (let char of word) {
      if (!node.children[char]) {
        node.children[char] = new TrieNode();
      }
      node = node.children[char];
    }
    node.isEndOfWord = true;
  }

  // Search for a word in the trie
  search(word) {
    let node = this.root;
    for (let char of word) {
      if (!node.children[char]) {
        return false;
      }
      node = node.children[char];
    }
    return node.isEndOfWord;
  }

  // Delete a word from the trie
  delete(word) {
    function deleteHelper(node, word, index) {
      if (index === word.length) {
        if (node.isEndOfWord) {
          node.isEndOfWord = false; // Mark the end of the word as false
          return Object.keys(node.children).length === 0; // If the node has no children, delete it
        }
        return false;
      }
      const char = word[index];
      if (!node.children[char]) {
        return false;
      }
      const shouldDeleteCurrentNode = deleteHelper(node.children[char], word, index + 1);
      if (shouldDeleteCurrentNode) {
        delete node.children[char];
        return Object.keys(node.children).length === 0 && !node.isEndOfWord;
      }
      return false;
    }
    deleteHelper(this.root, word, 0);
  }
}

// Example usage
const trie = new Trie();
trie.insert("apple");
console.log(trie.search("apple"));  // true
console.log(trie.search("app"));    // false
trie.delete("apple");
console.log(trie.search("apple"));  // false

```

---

### **Applications of Tries**

1. **Auto-completion**: Tries are used in auto-completion systems, where you want to suggest possible completions for a partially typed word.
2. **Dictionary Implementation**: Tries are useful for efficiently checking whether a word exists in a dictionary.
3. **Pattern Matching**: Tries can be used for efficient pattern matching and string searching.

---

### **What to Do With It**

- **Use Tries** for fast dictionary lookups, prefix searches, and autocomplete functionalities.
- **Combine Tries with Suffix Arrays** for efficient substring matching, as they both offer fast querying capabilities.

---

### **What Not to Do With It**

- **Avoid using Tries for very small datasets** where other data structures (like HashMaps) could perform better.
- **Don’t use Tries in memory-constrained environments** due to their high space complexity.

---

### 📚 **Learn More**

- **"Introduction to Algorithms (CLRS)"** – Chapter on Tries.
- **"Competitive Programming" by Halim & Halim** – Insights into pattern matching using Tries.

### **Mo's Algorithm**

---

### 📖 **Definition**

**Mo's Algorithm** (also known as **Mo's sqrt decomposition**) is a query algorithm designed to efficiently answer **range queries** on static arrays. It is particularly useful when we need to answer multiple **range queries** on an array, and these queries require data aggregation over ranges, such as **sum**, **min/max**, or **count**.

The key idea behind Mo's algorithm is to **reorder the queries** in a way that minimizes the movement of the left and right pointers when answering each query. This makes it **much faster** than answering each query naively.

- **Time Complexity**:
    - **Preprocessing Time**: `O(n * sqrt(n))`
    - **Query Time**: `O((n + q) * sqrt(n))`, where `n` is the size of the array and `q` is the number of queries.
- **Space Complexity**: `O(n)`, primarily for storing the array and the results of queries.

---

### ⚙️ **Working of Mo's Algorithm**

1. **Divide the array into blocks** of size approximately `sqrt(n)` (where `n` is the size of the array). This ensures that moving the pointers over the blocks will be efficient.
2. **Reorder the queries** such that queries that overlap are answered in a way that minimizes the movement of the pointers.
3. **Process the queries** in the reordered order using two pointers, `left` and `right`, to manage the range.

---

### 🧑‍💻 **Algorithm Steps**

1. **Sort the queries**:
    - Sort queries based on the block of the left index (`left // sqrt(n)`) and by the right index (`right`).
    - The sorting step ensures that the queries are processed in an optimal order.
2. **Answer the queries**:
    - Use two pointers `left` and `right` to maintain the current range.
    - For each query, **expand or shrink** the range by adjusting the `left` and `right` pointers.
    - **Add or remove** elements from the range to update the result (depending on the query).

---

### 🧮 **Code Example**

Let's consider answering **range sum queries** using Mo's Algorithm.

```
js
CopyEdit
class MoAlgorithm {
  constructor(arr) {
    this.arr = arr;   // Original array
    this.n = arr.length;  // Size of the array
    this.blockSize = Math.sqrt(this.n);  // Block size for sqrt decomposition
  }

  // Utility function to calculate the sum of a given range
  rangeSum(left, right) {
    let sum = 0;
    for (let i = left; i <= right; i++) {
      sum += this.arr[i];
    }
    return sum;
  }

  // Main function to process queries using Mo's algorithm
  processQueries(queries) {
    // Step 1: Sort queries by block number and then by right index
    queries.sort((a, b) => {
      let blockA = Math.floor(a[0] / this.blockSize);
      let blockB = Math.floor(b[0] / this.blockSize);
      if (blockA !== blockB) {
        return blockA - blockB;
      }
      return a[1] - b[1];
    });

    // Step 2: Process each query
    let left = 0, right = -1; // Initialize the range [left, right]
    let results = [];

    for (let [l, r] of queries) {
      // Expand the range to the right
      while (right < r) {
        right++;
      }

      // Shrink the range from the right
      while (right > r) {
        right--;
      }

      // Expand the range to the left
      while (left < l) {
        left++;
      }

      // Shrink the range from the left
      while (left > l) {
        left--;
      }

      // Add the result for this query
      results.push(this.rangeSum(left, right));
    }

    return results;
  }
}

// Example usage
const arr = [1, 3, 2, 4, 5, 7, 6];
const queries = [
  [0, 2],  // Query: sum of elements from index 0 to 2
  [1, 4],  // Query: sum of elements from index 1 to 4
  [2, 5],  // Query: sum of elements from index 2 to 5
  [0, 6],  // Query: sum of elements from index 0 to 6
];

const mo = new MoAlgorithm(arr);
const results = mo.processQueries(queries);
console.log(results);  // Output: [6, 14, 18, 28]

```

---

### **Explanation**:

1. **Sorting Queries**: The queries are sorted based on the left index divided by the block size (`left // sqrt(n)`), and then by the right index for queries that belong to the same block.
2. **Processing Queries**: For each query, we adjust the `left` and `right` pointers to match the range defined by the query. We then calculate the result (range sum in this case) and add it to the results array.
3. **Optimized Query Handling**: By sorting the queries, we minimize the number of operations needed to adjust the pointers, making Mo’s Algorithm efficient for a large number of range queries.

---

### **Applications of Mo's Algorithm**

1. **Range Query Problems**: Mo's algorithm can handle range queries such as sum, minimum, maximum, and frequency counts efficiently.
2. **Offline Queries**: Mo's algorithm works on offline queries (i.e., queries can be given all at once), and it is not suited for online or dynamic queries where the array changes over time.

---

### **What to Do With It**

- **Use Mo’s Algorithm** when you need to answer multiple range queries efficiently on a static array.
- **Combine with other algorithms**: Mo’s algorithm can be combined with techniques like **Frequency Count** and **Two Pointers** for solving more complex range queries.

---

### **What Not to Do With It**

- **Avoid Mo’s Algorithm on Dynamic Arrays**: The array must remain static for Mo’s algorithm to work efficiently. If the array changes frequently (insertions/deletions), then Mo’s algorithm is not suitable.
- **Don’t Use Mo’s Algorithm for Small Arrays**: The preprocessing and sorting steps can add unnecessary overhead for small arrays or queries.

---

### 📚 **Learn More**

- **"Competitive Programming" by Halim & Halim** – Insights into Mo's algorithm and applications.
- **"Introduction to Algorithms (CLRS)"** – For understanding range queries and more advanced data structures for range queries.

### **Heavy-Light Decomposition (HLD)**

---

### 📖 **Definition**

**Heavy-Light Decomposition** (HLD) is a technique used in graph theory to decompose a tree into **heavy** and **light** edges for efficient path queries and updates. It is primarily used to solve **path queries** and **path updates** in trees (like **sum**, **min/max**, and **range queries**) efficiently in `O(log n)` time.

The decomposition works by dividing the tree into **heavy** and **light** edges such that:

- **Heavy Edge**: An edge connecting a node to its child with the **largest subtree**.
- **Light Edge**: Any edge that doesn't satisfy the heavy edge condition (i.e., it connects to a child with a smaller subtree).

This decomposition allows us to reduce the problem of path queries into **logarithmic** time complexity.

- **Time Complexity**:
    - **Preprocessing**: `O(n)` for decomposing the tree.
    - **Query/Update**: `O(log n)` for each query or update.
- **Space Complexity**: `O(n)` for storing the tree and additional arrays.

---

### ⚙️ **Working of Heavy-Light Decomposition**

1. **Identify Heavy and Light Edges**:
    - For each node, pick the child with the largest subtree and mark the edge between them as heavy. The rest are light edges.
2. **Decompose the Tree**:
    - Each node will either be the **root** of a heavy chain or part of an existing chain.
    - The tree will be divided into several **chains**, with each chain containing one heavy path.
3. **Efficient Path Queries**:
    - Using **segment trees** or **binary indexed trees (BIT)**, you can answer path queries (e.g., sum or minimum queries) by breaking the path into **logarithmic** segments that belong to different chains.
4. **Path Compression**:
    - Instead of traversing each node individually, a query or update on a path is reduced to a sequence of **log(n)** operations over heavy-light chains.

---

### 🧑‍💻 **Algorithm Steps**

1. **DFS Traversal**:
    - Perform a DFS to calculate the subtree sizes and identify the heavy edge for each node.
2. **Chain Building**:
    - For each node, start a new chain if its parent does not have a heavy edge pointing to it. Otherwise, add it to the existing chain.
3. **Segment Tree or BIT**:
    - For each chain, construct a segment tree or BIT to allow efficient range queries and point updates.
4. **Query Path**:
    - To query a path from node `u` to node `v`, decompose the path into multiple segments of heavy-light chains and answer each segment in logarithmic time.

---

### 🧮 **Code Example**

Let's consider solving a **range sum query** on a tree using Heavy-Light Decomposition with a **Segment Tree**.

```
js
CopyEdit
class HLD {
  constructor(n, adj) {
    this.n = n;  // Number of nodes
    this.adj = adj;  // Adjacency list of the tree
    this.size = Array(n).fill(1);  // Subtree size for each node
    this.parent = Array(n).fill(-1);  // Parent of each node
    this.depth = Array(n).fill(0);  // Depth of each node
    this.chainHead = Array(n).fill(-1);  // Head of the chain for each node
    this.chainIndex = Array(n).fill(-1);  // Index of the node in its chain
    this.segTree = new SegmentTree(n);  // Segment Tree for range queries
  }

  // DFS to calculate size of subtrees
  dfsSize(node) {
    this.size[node] = 1;
    for (const child of this.adj[node]) {
      if (child === this.parent[node]) continue;
      this.parent[child] = node;
      this.depth[child] = this.depth[node] + 1;
      this.dfsSize(child);
      this.size[node] += this.size[child];
    }
  }

  // Decompose the tree into heavy-light chains
  hld(node, chainHead) {
    this.chainHead[node] = chainHead;
    this.chainIndex[node] = this.segTree.build(node);  // Segment Tree setup

    let heavyChild = -1;
    let maxSubtreeSize = -1;

    // Find the heavy child
    for (const child of this.adj[node]) {
      if (child === this.parent[node]) continue;
      if (this.size[child] > maxSubtreeSize) {
        maxSubtreeSize = this.size[child];
        heavyChild = child;
      }
    }

    if (heavyChild !== -1) {
      // If a heavy child exists, continue the current chain
      this.hld(heavyChild, chainHead);
    }

    // For all light children, start a new chain
    for (const child of this.adj[node]) {
      if (child === this.parent[node] || child === heavyChild) continue;
      this.hld(child, child);  // Start a new chain from this light child
    }
  }

  // Query the range [u, v]
  query(u, v) {
    let result = 0;
    while (this.chainHead[u] !== this.chainHead[v]) {
      if (this.depth[this.chainHead[u]] > this.depth[this.chainHead[v]]) {
        result += this.segTree.query(this.chainIndex[this.chainHead[u]], this.chainIndex[u]);
        u = this.parent[this.chainHead[u]];
      } else {
        result += this.segTree.query(this.chainIndex[this.chainHead[v]], this.chainIndex[v]);
        v = this.parent[this.chainHead[v]];
      }
    }
    result += this.segTree.query(this.chainIndex[u], this.chainIndex[v]);
    return result;
  }

  // Update the value at node 'u'
  update(u, value) {
    this.segTree.update(this.chainIndex[u], value);
  }
}

// Segment Tree implementation for range sum queries
class SegmentTree {
  constructor(n) {
    this.n = n;
    this.tree = Array(4 * n).fill(0);
  }

  build(index) {
    // Initialize segment tree at the given index
    return index; // Just an example for building
  }

  query(l, r) {
    // Query the range [l, r]
    return Math.random();  // Example to return a random value for illustration
  }

  update(index, value) {
    // Update the value at index
    this.tree[index] = value;
  }
}

// Example usage
const adj = [
  [1, 2],  // Node 0
  [0, 3, 4],  // Node 1
  [0],  // Node 2
  [1],  // Node 3
  [1]   // Node 4
];
const hld = new HLD(5, adj);
hld.dfsSize(0);  // Calculate subtree sizes starting from node 0
hld.hld(0, 0);   // Decompose the tree starting from root node 0

console.log(hld.query(3, 4));  // Query the range sum from node 3 to node 4
hld.update(3, 10);  // Update the value at node 3

```

---

### **Explanation**:

1. **DFS to Calculate Subtree Sizes**: We start by calculating the size of each subtree rooted at each node. This helps us in identifying the heavy edges during the HLD process.
2. **Heavy-Light Decomposition**: Using the subtree sizes, we recursively decompose the tree into chains, where each chain has one heavy path and the other edges are light.
3. **Segment Tree for Range Queries**: For each chain, we construct a segment tree that allows us to answer range queries efficiently on the path.
4. **Querying Path**: When querying the path between two nodes, we break the path into segments that belong to different chains and use the segment tree to query each segment.

---

### **What to Do With It**

- **Use HLD for Tree Path Queries**: HLD is very useful for answering path queries on trees like range sum, min, max, or more complex problems like Lowest Common Ancestor (LCA) queries.
- **Combine with Segment Tree/BIT**: To handle path queries and updates efficiently.

---

### **What Not to Do With It**

- **Avoid for Dynamic Graphs**: HLD is designed for **static** trees. If the tree changes frequently (like adding or removing edges), HLD may not be efficient.
- **Don’t Use for Small Trees**: For small trees, a simpler approach like DFS or BFS might be more efficient than HLD.

---

### 📚 **Learn More**

- **"Competitive Programming" by Halim & Halim** – Detailed examples and problems using HLD.
- **"Introduction to Algorithms (CLRS)"** – Chapter on **data structures for path queries** and **advanced tree algorithms**.

### **System Design Foundations (for DSA Cross-over)**

---

### 📖 **Definition**

**System Design** is the process of defining the architecture, components, modules, interfaces, and data for a system to satisfy specified requirements. It bridges the gap between **software engineering** and **problem-solving techniques** like **Data Structures and Algorithms (DSA)**. For interview purposes, system design often involves building scalable and efficient systems, focusing on aspects like load balancing, fault tolerance, and scalability.

System design problems in interviews assess your ability to:

- Break down a problem into smaller parts.
- Design systems that can scale and perform under stress.
- Make trade-offs and understand the implications of design decisions.

---

### ⚙️ **Key Concepts of System Design**

1. **Scalability**: Ensuring the system can handle growth, including:
    - **Vertical Scaling**: Adding resources (CPU, memory) to a single machine.
    - **Horizontal Scaling**: Adding more machines to distribute the load.
2. **Load Balancing**: Distributing requests across multiple servers to ensure no single server is overwhelmed.
3. **High Availability**: Designing a system that ensures continuous operation and minimizes downtime.
4. **Fault Tolerance**: Ensuring that the system continues to function even if part of it fails.
5. **Caching**: Using memory-based storage (like Redis) to speed up frequent queries and reduce load on databases.
6. **Database Sharding**: Splitting a database into smaller, more manageable pieces to improve performance and scalability.
7. **Consistent Hashing**: A technique for distributing data across multiple machines to ensure that when new machines are added or removed, the least amount of data is moved.
8. **Rate Limiting**: Limiting the number of requests a client can make to the system within a specified time period.
9. **CAP Theorem**: In distributed systems, the system can guarantee at most two of the following three properties:
    - **Consistency**: All nodes see the same data at the same time.
    - **Availability**: Every request receives a response, even if some nodes are down.
    - **Partition Tolerance**: The system continues to function even if network partitions occur.

---

### 🧑‍💻 **Interview Process for System Design**

1. **Problem Understanding**:
    - Clarify the requirements: Ask for functional and non-functional requirements. What are the goals (e.g., scalability, fault tolerance)?
    - Gather more details: Understand user behavior, expected load, and performance requirements.
2. **High-Level Architecture**:
    - Start with a high-level design: Show how the system components interact with each other (e.g., frontend, backend, databases).
    - Consider common patterns: Microservices, client-server models, REST APIs, etc.
3. **Breaking Down Components**:
    - Identify key components (e.g., web servers, databases, caching layers, messaging queues).
    - Consider data flow: How data is ingested, processed, and output.
4. **Scaling the System**:
    - Discuss how the system will handle an increase in users, traffic, or data.
    - Consider horizontal and vertical scaling strategies for key components (servers, databases).
5. **Database Design**:
    - Decide on the database type (SQL vs. NoSQL).
    - Design the schema or decide on data modeling.
    - Think about consistency, availability, and partition tolerance (CAP theorem).
6. **Handling Bottlenecks**:
    - Identify potential bottlenecks in performance (e.g., database queries, CPU, network).
    - Propose solutions like load balancing, caching, sharding, and CDNs.
7. **Fault Tolerance and Recovery**:
    - How will the system recover from failures? Consider strategies like replication, failover, and backup systems.
8. **Security Considerations**:
    - Data encryption, authentication, and authorization.
    - Rate limiting, protection from DDoS attacks.
9. **Monitoring and Logging**:
    - Discuss monitoring tools (e.g., Prometheus, Grafana) for system health.
    - Centralized logging for debugging and issue detection.

---

### ⚡ **Example: Design a URL Shortener**

Let’s take the **URL Shortener** problem, commonly asked in system design interviews.

### **Step 1: Understand Requirements**

- Functional: Given a long URL, generate a short URL that redirects to the original URL. The system should support large-scale traffic.
- Non-functional: System must be highly available, fast, and scalable.

### **Step 2: High-Level Design**

- **Frontend**: A web interface where users can input long URLs.
- **Backend**:
    - **API layer**: To handle URL shortening requests.
    - **Database**: Store long URL and corresponding short URL.
    - **Redirect Service**: Resolves short URLs to long URLs.
- **Key Components**:
    - **Database**: A NoSQL database (like Redis or MongoDB) to store mappings of short and long URLs.
    - **Cache**: Caching the most popular URLs in memory to reduce database load.
    - **Load Balancer**: Distribute incoming traffic across multiple API servers.

### **Step 3: Database Design**

- **Table schema**:
    - Short URL: Unique identifier (e.g., "abc123").
    - Long URL: Original long URL.
    - Timestamp: When the short URL was created.
- **Unique Key**: Use base62 encoding (letters, digits) for the short URL to keep it compact.

### **Step 4: Scalability**

- **Hashing**: Use consistent hashing for distributing URLs across multiple servers.
- **Database Sharding**: Divide data into multiple shards to handle growing data.

### **Step 5: Handling Bottlenecks**

- **Database Bottleneck**: Use a **cache** to store popular URLs.
- **Scaling**: Use horizontal scaling to add more web and API servers as traffic grows.

### **Step 6: Fault Tolerance**

- **Replication**: Replicate database to avoid a single point of failure.
- **Backup**: Regular backups to recover data in case of failures.

### **Step 7: Security and Rate Limiting**

- **Rate Limiting**: Use rate limiting to prevent abuse (e.g., excessive requests to shorten URLs).
- **Data Encryption**: Ensure that URLs are encrypted if necessary for sensitive information.

---

### 🧑‍💻 **Common System Design Interview Questions**

1. **Design a URL Shortener**
2. **Design a File Storage System (like Google Drive)**
3. **Design a Social Media Platform (like Twitter)**
4. **Design a Ride-Hailing System (like Uber)**
5. **Design a Messaging System (like WhatsApp)**
6. **Design a Cache System (like Redis)**
7. **Design a Notification System**
8. **Design a News Feed System**

---

### 📚 **Books and Resources for System Design**

- **"Designing Data-Intensive Applications" by Martin Kleppmann**: Comprehensive guide to designing scalable, reliable systems.
- **"System Design Interview" by Alex Xu**: A great resource for preparing for system design interviews.
- **Grokking the System Design Interview**: An online course focused on preparing for system design interviews.

---

### **Conclusion**

System Design is an essential part of software engineering, and it's crucial to practice designing scalable, efficient, and robust systems. By understanding key concepts and applying DSA knowledge, you can approach system design problems effectively and succeed in interviews.

### **Top 100 LeetCode Patterns**

Here’s a curated list of **Top 100 LeetCode Patterns** for systematic learning and interview preparation. These patterns will help you identify common techniques used to solve various types of problems.

---

### **1. Sliding Window**

1. Maximum Sum Subarray of Size K
2. Longest Substring Without Repeating Characters
3. Minimum Window Substring
4. Subarrays with K Different Integers
5. Permutation in String

### **2. Two Pointers**

1. Valid Palindrome
2. Remove Duplicates from Sorted Array
3. Container With Most Water
4. 3Sum
5. Trapping Rain Water

### **3. Fast & Slow Pointers (Floyd’s Cycle)**

1. Linked List Cycle
2. Linked List Cycle II
3. Happy Number
4. Middle of the Linked List
5. Detect a Cycle in a Linked List

### **4. Binary Search**

1. Binary Search
2. Search Insert Position
3. Find Minimum in Rotated Sorted Array
4. Kth Smallest Element in a Sorted Matrix
5. Search in Rotated Sorted Array II

### **5. Greedy Algorithms**

1. Jump Game
2. Gas Station
3. Candy
4. Partition Equal Subset Sum
5. Best Time to Buy and Sell Stock II

### **6. Sorting**

1. Merge Intervals
2. Sort Colors
3. Kth Largest Element in an Array
4. Counting Sort
5. Insertion Sort

### **7. Backtracking**

1. Permutations
2. Subsets
3. Combinations
4. N-Queens
5. Word Search

### **8. Dynamic Programming**

1. Fibonacci Number
2. Climbing Stairs
3. Coin Change
4. Longest Common Subsequence
5. Longest Increasing Subsequence

### **9. Prefix Sum / Difference Array**

1. Subarray Sum Equals K
2. Range Sum Query
3. Count of Subarrays
4. Prefix Sum
5. Maximum Sum Subarray of Size K

### **10. Trie**

1. Implement Trie (Prefix Tree)
2. Word Search II
3. Add and Search Word
4. Design Add and Search Data Structure
5. Replace Words

### **11. Union-Find (Disjoint Set)**

1. Number of Islands
2. Friend Circles
3. Redundant Connection
4. Accounts Merge
5. Surrounded Regions

### **12. Hashing**

1. Two Sum
2. Group Anagrams
3. Subarray Sum Equals K
4. Longest Consecutive Sequence
5. Valid Anagram

### **13. Topological Sort**

1. Course Schedule
2. Course Schedule II
3. Alien Dictionary
4. Find Order of Characters
5. Task Scheduler

### **14. Binary Search Tree (BST)**

1. Validate Binary Search Tree
2. Binary Search Tree Iterator
3. Lowest Common Ancestor of a Binary Search Tree
4. Kth Smallest Element in a BST
5. Recover Binary Search Tree

### **15. Linked List**

1. Merge Two Sorted Lists
2. Reorder List
3. Reverse Linked List
4. Remove Nth Node from End of List
5. Intersection of Two Linked Lists

### **16. Matrix**

1. Set Matrix Zeroes
2. Spiral Matrix
3. Word Search II
4. Rotate Image
5. Search a 2D Matrix II

### **17. Recursion**

1. Permutations
2. Combinations
3. Subsets II
4. Binary Tree Maximum Path Sum
5. Climbing Stairs

### **18. Divide and Conquer**

1. Merge Sort
2. Quick Sort
3. Kth Largest Element in an Array
4. Search in a Sorted Array
5. Maximum Subarray

### **19. Depth-First Search (DFS)**

1. Number of Islands
2. Same Tree
3. Path Sum
4. Sum of Left Leaves
5. Subtree of Another Tree

### **20. Breadth-First Search (BFS)**

1. Binary Tree Level Order Traversal
2. Word Ladder
3. Clone Graph
4. Populating Next Right Pointers in Each Node
5. Word Ladder II

---

This list covers various **LeetCode problem patterns** that will help you to identify key concepts and approaches needed for tackling different types of algorithmic challenges. Focus on mastering each pattern and its associated problems, as this will make solving other problems easier!

## Mock interviews and problem-solving practice

Mock interviews and problem-solving practice are essential components of preparing for coding interviews. They allow you to simulate real interview conditions, improve your problem-solving skills, and develop confidence in handling tough interview questions. Here’s a structured approach to mock interviews and problem-solving practice:

---

### **1. Mock Interviews**

### **Purpose**

- **Simulate real interview experience:** Mock interviews replicate the interview environment, helping you get used to the pressure and stress of real interviews.
- **Identify strengths and weaknesses:** They help you understand where you excel and where you need improvement.
- **Feedback and improvement:** Post-interview feedback from mock interviewers helps in identifying mistakes and working on them.

### **How to Conduct Mock Interviews**

1. **Schedule Mock Interviews**:
    - You can schedule mock interviews on platforms like:
        - **Pramp**
        - **Interviewing.io**
        - **Exercism**
        - **LeetCode Premium (Mock Interviews)**
        - **Coderbyte**
        - **Hackerrank (for mock contests)**
2. **Involve Real Interviewers**:
    - Ideally, practice with someone experienced in technical interviews (mentor, friend, or through paid services).
3. **Choose the Right Topics**:
    - Focus on algorithms, data structures, system design, or any specialized area like machine learning or frontend development depending on the role you're applying for.
4. **Time Yourself**:
    - Set a timer to mimic the time constraints typically found in coding interviews.
5. **Talk Through Your Thought Process**:
    - Communicate your thoughts clearly as you solve problems. This shows interviewers your problem-solving approach.
6. **Ask for Feedback**:
    - After the mock interview, request feedback on your performance. Pay attention to how you explain the solution and your problem-solving approach.

---

### **2. Problem Solving Practice**

### **Purpose**

- **Strengthen problem-solving skills**: Solving problems regularly helps improve logical thinking, algorithm design, and coding speed.
- **Prepare for different topics**: Exposure to diverse problems from various domains like arrays, trees, graphs, dynamic programming, etc.

### **How to Approach Problem Solving Practice**

1. **Use Platforms**:
    - **LeetCode**: One of the most popular platforms for practicing algorithm and data structure problems.
    - **HackerRank**: Good for practicing algorithms, data structures, and domain-specific skills.
    - **Codeforces**: Offers competitive programming contests that simulate real-time interview conditions.
    - **Codewars**: Provides a wide range of problems with varying difficulty levels.
    - **InterviewBit**: Offers problems specifically designed for interview preparation.
    - **TopCoder**: For advanced problem-solving and competitive programming.
2. **Start with Easy Problems**:
    - Focus on **easy** problems first to build a solid foundation. Understand the problem-solving techniques behind each solution.
3. **Move to Medium and Hard Problems**:
    - After mastering easy problems, increase the difficulty to **medium** and **hard** problems. These will test your skills and help you learn new algorithms and techniques.
4. **Practice Specific Patterns**:
    - Focus on practicing one pattern at a time. For example:
        - Sliding Window
        - Two Pointers
        - Greedy Algorithms
        - Dynamic Programming
        - Depth-First Search (DFS)
        - Breadth-First Search (BFS)
        - Backtracking
        - Binary Search
5. **Time Your Solutions**:
    - Set a timer while solving problems to simulate interview conditions where time is crucial.
6. **Review and Analyze Solutions**:
    - After solving a problem, review your solution. Can it be optimized? How would you explain it in an interview? Look at other solutions (if available) and compare them with yours for optimization and elegance.

---

### **3. Interviewing Strategies**

### **Prepare for Behavioral Questions**

- **STAR Method** (Situation, Task, Action, Result) to frame answers.
- **Why this company?**
- **Why this role?**
- **Describe a challenging situation and how you overcame it.**

### **Common Problem-Solving Tips**

- **Understand the Problem**: Before jumping into coding, make sure you completely understand the problem and ask clarifying questions if necessary.
- **Break Down the Problem**: Decompose large problems into smaller, manageable parts. This makes it easier to develop a solution.
- **Choose the Right Data Structures**: Picking the right data structure is key to solving most problems efficiently.
- **Write Clean and Efficient Code**: Focus on writing clean, readable, and efficient code. Optimize for time and space complexity.
- **Test Your Solution**: After writing the code, test it with sample inputs, edge cases, and boundary conditions.

---

### **4. Practice Problem Sets**

Here are curated sets of problems to practice from different categories:

### **Arrays and Strings**

1. **Two Sum**
2. **Maximum Subarray Sum (Kadane's Algorithm)**
3. **Longest Substring Without Repeating Characters**
4. **Group Anagrams**
5. **Move Zeroes**
6. **Palindrome Check**

### **Linked Lists**

1. **Reverse Linked List**
2. **Merge Two Sorted Lists**
3. **Detect Cycle in a Linked List**
4. **Remove Nth Node from End of List**
5. **Intersection of Two Linked Lists**

### **Trees and Graphs**

1. **Binary Tree Inorder Traversal**
2. **Level Order Traversal**
3. **DFS and BFS**
4. **Number of Islands**
5. **Clone Graph**

### **Dynamic Programming**

1. **Climbing Stairs**
2. **Coin Change**
3. **Longest Common Subsequence**
4. **0/1 Knapsack**
5. **Word Break**

### **Backtracking**

1. **N-Queens**
2. **Subsets**
3. **Combination Sum**
4. **Word Search**
5. **Permutations**

### **Greedy Algorithms**

1. **Activity Selection Problem**
2. **Gas Station**
3. **Huffman Encoding**
4. **Interval Scheduling Maximization**

### **Sorting & Searching**

1. **Binary Search**
2. **Merge Sort**
3. **Quick Sort**
4. **Find Kth Largest Element**
5. **Count Inversions**

---

### **5. Weekly/Monthly Mock Interview Schedule**

### **Week 1**: Data Structures and Algorithm Fundamentals

- Day 1-2: **Arrays & Strings**
- Day 3-4: **Linked Lists & Stacks/Queues**
- Day 5: **Trees & Graphs**
- Day 6: **Dynamic Programming**
- Day 7: **Backtracking & Greedy Algorithms**

### **Week 2**: Advanced Problem-Solving

- Day 1-2: **Advanced DP**
- Day 3: **Graph Algorithms (BFS, DFS)**
- Day 4: **Advanced Trees (AVL, Segment Trees)**
- Day 5-6: **Sorting & Searching**
- Day 7: **Mock Interview (Algorithms + Problem Solving)**

### **Week 3-4**: System Design and Real Interview Preparation

- Week 3: **System Design Basics**
- Week 4: **Mock Interviews + Full Stack Problems**

---

### **6. Additional Tips for Success**

- **Practice Consistently**: Make problem-solving a habit. Daily practice for at least 1-2 hours will significantly improve your coding skills.
- **Record Your Progress**: Keep track of problems you've solved, your time, and any optimizations you've made.
- **Mock Interviews**: Schedule mock interviews with peers or mentors regularly.
- **Stay Calm in Interviews**: Stay confident, and if you get stuck, communicate your thought process with the interviewer.

---

Following this structured approach will help you develop a strong problem-solving mindset and ensure you're well-prepared for technical interviews!

## Real-world Use Cases of DSA in Engineering

Data Structures and Algorithms (DSA) are foundational concepts in computer science, and their real-world applications span across various domains in engineering, software development, and system design. Below are some real-world use cases where DSA plays a critical role:

---

### **1. Web Development**

### **Use Case: Content Delivery Networks (CDNs)**

- **Data Structure(s) Used:** Hash Tables, Priority Queues, Trees (AVL, Red-Black Trees)
- **How DSA Helps:** CDNs optimize the delivery of web content by caching data at various edge servers. Hash tables are used to store and retrieve cached content efficiently, while priority queues help in selecting the best content to deliver based on demand.

### **Use Case: Routing and URL Shortening**

- **Data Structure(s) Used:** Graphs, Tries, Hash Maps
- **How DSA Helps:** In URL shortening services like Bitly, graphs are used to represent URL redirection chains, while tries and hash maps are used to efficiently store and search for shortened URLs.

---

### **2. Operating Systems**

### **Use Case: Process Scheduling**

- **Data Structure(s) Used:** Queues, Priority Queues, Heaps
- **How DSA Helps:** Operating systems use scheduling algorithms to manage multiple processes. A priority queue or heap helps manage which processes are executed first based on priority, ensuring optimal performance and fairness.

### **Use Case: File Systems**

- **Data Structure(s) Used:** B-trees, Hash Tables, Linked Lists
- **How DSA Helps:** File systems like NTFS and EXT4 use B-trees for indexing files, making it possible to search files efficiently. Hash tables are used to store metadata (e.g., file paths), and linked lists manage file allocations.

---

### **3. Networking**

### **Use Case: Routing Protocols**

- **Data Structure(s) Used:** Graphs, Dijkstra’s Algorithm, Bellman-Ford Algorithm
- **How DSA Helps:** In routing protocols like OSPF (Open Shortest Path First) and RIP (Routing Information Protocol), Dijkstra’s algorithm and other shortest path algorithms help routers find the best path for data transmission.

### **Use Case: Load Balancing**

- **Data Structure(s) Used:** Hash Tables, Queues
- **How DSA Helps:** Load balancers distribute network traffic efficiently across multiple servers. Hash tables store server information, while queues ensure requests are handled in the order they arrive, optimizing server utilization.

---

### **4. Databases**

### **Use Case: Indexing**

- **Data Structure(s) Used:** B-trees, Hash Maps
- **How DSA Helps:** Databases use indexing algorithms like B-trees to optimize search, insertion, and deletion operations. Hash maps are used to store and retrieve key-value pairs in NoSQL databases (e.g., Redis, MongoDB).

### **Use Case: Query Optimization**

- **Data Structure(s) Used:** Heaps, Priority Queues
- **How DSA Helps:** Query optimizers in databases use heaps and priority queues to efficiently sort and rank data for fast retrieval, ensuring that queries are executed in the most efficient way possible.

---

### **5. Machine Learning & AI**

### **Use Case: Graph-Based Algorithms (e.g., Social Network Analysis)**

- **Data Structure(s) Used:** Graphs, DFS, BFS, Dijkstra’s Algorithm
- **How DSA Helps:** Social networks like Facebook and LinkedIn model users and their interactions as graphs. Algorithms like BFS/DFS help identify connections between users, while Dijkstra’s algorithm can be used for recommendations and shortest paths between individuals.

### **Use Case: Data Clustering (K-means)**

- **Data Structure(s) Used:** Arrays, Heaps, Graphs
- **How DSA Helps:** In machine learning clustering algorithms like K-means, arrays and heaps are used to efficiently store and update cluster centers, while graph algorithms may be used for advanced clustering techniques.

---

### **6. Financial Engineering**

### **Use Case: Trading Algorithms**

- **Data Structure(s) Used:** Heaps, Hash Maps, Arrays
- **How DSA Helps:** In high-frequency trading (HFT), heaps and priority queues are used to maintain order books efficiently, allowing fast access to the best prices for buying or selling. Hash maps are used to quickly access historical trade data.

### **Use Case: Portfolio Management**

- **Data Structure(s) Used:** Arrays, Trees (Segment Trees)
- **How DSA Helps:** Portfolio managers use arrays to store individual asset performance and segment trees for efficient range queries and updates to portfolio performance in real-time.

---

### **7. Gaming and Simulations**

### **Use Case: Pathfinding (e.g., AI for Video Games)**

- **Data Structure(s) Used:** Graphs, Heaps, A* Algorithm
- **How DSA Helps:** In video games, AI characters use pathfinding algorithms like A* to navigate environments. Graphs represent game maps, and heaps are used to efficiently compute the shortest path from one point to another.

### **Use Case: Collision Detection**

- **Data Structure(s) Used:** Trees (Quadtrees, Octrees), Hash Maps
- **How DSA Helps:** In 3D simulations and games, spatial data structures like octrees and quadtrees are used to quickly detect potential collisions by organizing objects in the game world into hierarchical structures.

---

### **8. Web Search and Search Engines**

### **Use Case: Indexing and Searching**

- **Data Structure(s) Used:** Tries, Hash Maps, B-trees
- **How DSA Helps:** Search engines like Google use advanced data structures like tries for prefix-based searching and hash maps to store document frequencies. B-trees are used for indexing large amounts of data for quick retrieval.

### **Use Case: Relevance Ranking (PageRank)**

- **Data Structure(s) Used:** Graphs, Matrices
- **How DSA Helps:** PageRank, used by Google Search, is based on graph algorithms that rank web pages based on the structure of links between them. Matrices and eigenvectors are used to represent and calculate the importance of pages.

---

### **9. Cryptography and Security**

### **Use Case: Secure Hash Functions**

- **Data Structure(s) Used:** Hash Maps, Linked Lists
- **How DSA Helps:** Cryptographic hash functions like SHA-256 rely on data structures like hash maps to store and hash large amounts of data efficiently, ensuring data integrity and secure storage.

### **Use Case: Public Key Infrastructure (PKI)**

- **Data Structure(s) Used:** Trees (Binary Search Trees), Hash Maps
- **How DSA Helps:** PKI systems use trees and hash maps to store keys, certificates, and other cryptographic data. Binary search trees are used to quickly search and validate keys.

---

### **10. Internet of Things (IoT)**

### **Use Case: Real-Time Data Processing**

- **Data Structure(s) Used:** Queues, Priority Queues, Hash Maps
- **How DSA Helps:** In IoT systems that involve real-time data processing (e.g., sensor networks), queues and priority queues manage data streams efficiently. Hash maps are used to store sensor data in real-time for easy access.

### **Use Case: IoT Device Management**

- **Data Structure(s) Used:** Graphs, Trees
- **How DSA Helps:** In large-scale IoT systems, graphs model the relationships between devices, while trees are used to organize devices hierarchically for management and control purposes.

---

### **11. Robotics**

### **Use Case: Motion Planning**

- **Data Structure(s) Used:** Graphs, Heaps, Search Algorithms (A*, Dijkstra’s)
- **How DSA Helps:** In robotics, motion planning algorithms help robots navigate through an environment by finding the shortest path. These algorithms often use graphs, with A* or Dijkstra's algorithm providing the most efficient paths.

### **Use Case: Object Detection and Localization**

- **Data Structure(s) Used:** Trees (KD-trees), Hash Maps
- **How DSA Helps:** Robots use KD-trees to efficiently search for and localize objects in multi-dimensional spaces. Hash maps are used to quickly access object data for decision-making processes.

---

### **Conclusion**

DSA is not just theoretical but a practical set of tools that underpin the functionality of systems we use every day. From the optimization of search algorithms and routing protocols to the design of efficient databases and AI systems, DSA enables engineers to build scalable, performant, and reliable systems. Mastery of DSA is key to solving complex engineering challenges in both software and hardware systems.
