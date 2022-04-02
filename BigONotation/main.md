# Big O Notation
## Definition
We say that an algorithm is O(f(n)) if the number of simple operations the computer has to do is eventutally less than a constant times f(n), as n increases.
- f(n) could be linear (F(n) = n)
- f(n) could be quadratic (f(n) = n^2)
- f(n) could be constant (f(n) = 1)
- f(n) could be something entirely different

## Need
- Assign labels to our code while comparison of different ways of writing code using different logics.
- Find out the trade-offs between different approaches
- Identify which parts of the code is inefficient

## What
- Write a fn that sums all numbers 1 to n

Solution 1:
```bash
function addUpTo(n){
  let total=0;
  for(let i=1; i<=n; i++){ total+=1; }
  return total;
}
```
Solution 2:
```bash
function addUpTo(n){
  return n*(n+1)/2;
}
```
What does better mean? Faster, memory, readability, brevity?
Efficient code that is fast uses less memory and doesn't affect readability.

# Time Complexity
performance.now(); <---- to check time

Problem with Time
  - Diff machines will record diff times
  - Same machines will record diff times
  - Fast algo, speed measurements may not be precise enough

## Counting operations
Solution 1 has 5n+2 operations - 2*n additions, 2*n assignments n comparisons and 2 assignments (the number of operations grow in proportion with n)
Solution 2 has 3 operations - 1 multiplication, 1 addition, 1 division

Solution 1 - O(n)
Solution 2 - O(1)
Two loops over n back to back - O(n)
Two loops over n nested - O(n^2)

Simplification:
O(2n) = O(n)
O(500) = O(1)
O(13n^2) = O(n^2)
O(n+10) = O(n)
O(1000n+50) = O(n)
O(n^2+5n+8) = O(n^2)

--Shorthands--
1. Arithmetic operations are constant
2. Variable assignment is constant
3. Accessing elements in an array or obj is constant
4. Complexity of loops depends on logic within the loop

# Space Complexity
- primitives - constant space
- String, Object, Array require O(n) space - n string length, number of keys, number of elements

```bash
function sum(arr) {
  let total=0;
  for(let i=0;i<arr.length;i++){
    total+=arr[i];
  }
}
```
Space used - 2 numbers ---- O(1)

```bash
function double(arr) {
  let newArr=[];
  for(let i=0;i<arr.length;i++){
    newArr.push(2*arr[i]);
  }
}
```
Space used - 1 Array of size n, 1 number ---- O(n)

