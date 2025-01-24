# JavaScript has two different types of values:

1. Primitive values
2. Reference values

- Primitive values are atomic pieces of data.
- Reference values are objects that might consist of multiple values.

# Stack and heap memory

When you declare variables, the JavaScript engine allocates the memory for them on two memory locations: stack and heap.

Static data is the data whose size is fixed at compile time. Static data includes:

Primitive values `(null, undefined, boolean, number, string, symbol, and BigInt)`

Reference values that refer to objects.

Since static data has a size that does not change, the JavaScript engine allocates a fixed amount of memory space to the static data and stores it on the stack.

Unlike the stack, JavaScript stores objects (and functions) on the heap. The JavaScript engine doesn’t allocate a fixed amount of memory for these objects. Instead, it’ll allocate more space as needed.

# JavaScript Engine and Memory Management:

- The JavaScript engine, like V8 (used in Chrome and Node.js), is a program that runs JavaScript code.

- When it runs, it uses your computer's RAM to allocate and manage memory for various types of data (e.g., variables, objects, and functions). It decides what goes into the stack (static memory) and what goes into the heap (dynamic memory).

- The stack is used for storing static, short-lived, and small data like function calls, primitive values, and references. It's fast and organized.

- The heap is for larger and dynamic data like objects and arrays, which may grow in size during runtime.
---

# Array Methods with Explanation:
---

#### 1. Adding/Removing Elements:
`push()`, `pop()`, `unshift()`, `shift()`

#### 2. Iterating Over Arrays:
`forEach()`, `map()`, `filter()`, `reduce()`

#### 3. Checking/Modifying Arrays:
`includes()`, `indexOf()`, `splice()`, `slice()`

---

1. **forEach()**

- **Purpose**: Executes a provided function for each element in the array.
- **Return Value**: undefined. It doesn’t create a new array but modifies the original array (if needed).
- **Use Case**: When you need to iterate over an array to perform a side effect (e.g., logging, updating, etc.).
```javascript
const numbers = [1, 2, 3];
numbers.forEach((num) => console.log(num * 2));
// Output: 2, 4, 6
```
2. **map()**
- **Purpose**: Creates a new array by applying a provided function to each element in the array.
- **Return Value**: A new array containing the transformed elements.
- **Use Case**: When you want to transform or manipulate data and return the modified version.
```javascript
const numbers = [1, 2, 3];
const doubled = numbers.map((num) => num * 2);
console.log(doubled); // [2, 4, 6]
```
3. **filter()**
- **Purpose**: Creates a new array with all elements that pass a provided test (i.e., a condition).
- **Return Value**: A new array containing the elements that satisfy the condition.
- **Use Case**: When you need to filter out specific elements from an array.
```javascript
const numbers = [1, 2, 3, 4];
const evens = numbers.filter((num) => num % 2 === 0);
console.log(evens); // [2, 4]
```
4. **reduce()**
- **Purpose**: Reduces the array to a single value by applying a provided function that accumulates results.
- **Return Value**: A single value (e.g., sum, product, object, etc.).
- **Use Case**: When you need to combine array elements into a single output.
```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((accumulator, num) => accumulator + num, 0);
console.log(sum); // 10
```
---

#### Key Differences:
| Method	| Modifies Original Array?|	Creates New Array? | Purpose | Return Value |
|-----------|-------------------------|--------------------|---------|----------------|
| forEach()	| No | No	| Perform side effects on each element|	undefined
| map()	| No |	Yes | Transform elements | New array with transformed elements
|filter()	|No	|Yes	|Select elements based on a condition	| New array with filtered elements
|reduce()	|No	|No	|Reduce array to a single value	| Single accumulated value

#### When to Use Which?
- **forEach():** When you need to perform an action on each element, like logging or modifying an external variable.
- **map():** When you need to transform all elements of an array into a new array.
- **filter():** When you want to extract a subset of elements based on a condition.
- **reduce():** When you want to aggregate array values into a single value, like calculating a sum, average, or building an object.

---
## Array Destructuring:
---
Extract values from an array into variables.

```javascript
const [first, second] = fruits;
console.log(first); // "Apple"
```

## Spreading and Merging Arrays:
---
Use the spread operator `(...)` to copy or merge arrays.

```javascript
const moreFruits = [...fruits, "Durian"];
```

## Immutability
---
React encourages immutable updates. Use methods like `map()`, `filter()`, or the spread operator to avoid mutating the original array.

```javascript
const updatedTasks = tasks.map((task) =>
  task.id === targetId ? { ...task, completed: true } : task
);
```
---
