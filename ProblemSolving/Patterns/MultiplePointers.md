## Multiple Pointers
Creating pointers or values that correspond to an index or position and move towards the beginning, end or middle based on a certain condition.
Very efficient for solving problems with minimal space complexity as well.

[-4, -3, -2, -1, 0, 1, 2, 5]
"alksjdlksjdl"

## Examples
### Write a fn called sumZero which accepts a sorted array of integers. The fn should find the first pair where the sum is 0. Return an array that includes both values that sum or zero or undefined if a pair does not exist.

```javascript
sumZero([-3,-2,-1,0,1,2,3]); // [-3,3]
sumZero([-2,0,1,3]); // undefined
sumZero([1,2,3]); // undefined
```
Naive solution:
```javascript
function sumZero (arr) {
  for (let i=0;i<arr.length;i++){
    const currI=arr[i];
    for (let j=(i+1);j<arr.length;j++){
      const currJ=arr[j];
      if (currI+currJ === 0) return [currI ,currJ];
    }
  }
  return undefined;
}
```
Multiple pointer solution:
```javascript
function sumZero (arr) {
  let left=0;
  let right=arr.length-1;
  let sum;
  do {
    sum = arr[right] + arr[left];
    if (sum === 0){
      return [lEl,rEl];
    }else if (sum > 0){
      right-=1;
    } else {
      left +=1;
    }
  }
  while(sum!==0 && left<right);
}
```
### Implement a fn called countUniqueValues, which accepts a sorted array, and counts the unique values in the arry. there can be negative numbers in the array, but it will always be sorted.

```javascript
countUniqueValues([1,1,1,1,1,2]); // 2
countUniqueValues([]); // 0
```
Own solution 1:
```javascript
function countUniqueValues (arr) {
  const obj = {};
  arr.forEach(el => obj[el]=true)
  return Object.keys(obj).length;
}
```
Own solution 2:
```javascript
function countUniqueValues (arr) {
  const obj = {};
  arr.forEach(el => obj[el]=true)
  return Object.keys(obj).length;
}
```
Copy of tutor solution:
```javascript
function countUniqueValues (arr) {
  let i=0;
  let j=1;
  while (j < arr.length){
    if (arr[i] !== arr[j]){
      i++;
      arr[i]=arr[j];
    }
    j++;
  }
  return i?(i+1):i;
}
```
