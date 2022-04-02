## Frequency Counters

This pattern uses objects or sets to collect values/frequencies of values.
This can often avoid the need for nested loops or O(n^2) operations with arrays/strings.

## Example:
### Write a fn called same, which accepts two arrays. The fn should return true if every value in the array has it's corresponding value squared in the second array. The frequency of values must be the same.

```javascript
function same (arr1, arr2){
  if (arr1.length !== arr2.length){
    return false;
  }
  for (let i=0;i<arr1.length;i++){
    let correctIndex - arr2.indexOf(arr1[i]**2);
    if (correctIndex === -1){
      return false;
    }
    arr2.splice(correctIndex, 1)l
  }
}
```
Complexity - O(n^2) - for loop + indexOf

```javascript
function same (arr1, arr2){
  if (arr1.length !== arr2.length){
    return false;
  }
  const obj1={}, obj2={};
  arr1.forEach((val) => {
    obj1[val] = ++obj1[val] || 1;
  });
  arr2.forEach((val) => {
    obj2[val] = ++obj2[val] || 1;
  });
  for (let key in obj1){
    if (!(key***2 in obj2)){
      return false;
    }
    if (obj1[key] !== obj2[key**2]){
      return false;
    }
  }
  return true;
}
```
Complexity - O(3n) ~ O(n)

### Anagrams
Given 2 strings, write a fn to determine if the second string is an anagram of the first.
'' ~ ''
'aaz' !~ 'zza'

```javascript
function anagramCheck (str1, str2){
  if (str1.length !== str2.length){
    return false;
  }
  const obj1={}, obj2={};
  for (let char of str1) {
    obj1[char] = ++obj1[char] || 1;
  };
  for (let char of str2) {
    obj2[char] = ++obj2[char] || 1;
  };
  for (let key in obj1){
    if (!(key in obj2)){
      return false;
    }
    if (obj1[key] !== obj2[key]){
      return false;
    }
  }
  return true;
}
```
Complexity - O(3n) ~ O(n)

#### Tutor's solution
```javascript
function anagramCheck (str1, str2){
  if (str1.length !== str2.length){
    return false;
  }
  const obj1={};
  for (let char of str1) {
    obj1[char] = ++obj1[char] || 1;
  };
  for (let char of str2) {
    if (!obj1[char]) return false;
    else obj1[char]-=1;
  };
  return true;
}
```
Complexity - O(2n) ~ O(n)
