# JavaScript演算法與資料結構
## 中級演算法(Intermediate Algorithm Scripting)
### [Sorted Union](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/intermediate-algorithm-scripting/sorted-union)
會有數量不等的參數傳入，並按照原始提供的array的順序返回一個新的唯一值array。
```javascript
function uniteUnique() {
  const arr = [];
  for(let i=0; i<arguments.length; i++){
    arr.push(...arguments[i])
  }
  return [...new Set(arr)];
}

uniteUnique([1, 3, 2], [5, 2, 1, 4], [2, 1]) 
// [1, 3, 2, 5, 4].
uniteUnique([1, 2, 3], [5, 2, 1]) 
// [1, 2, 3, 5].
uniteUnique([1, 2, 3], [5, 2, 1, 4], [2, 1], [6, 7, 8]) 
// [1, 2, 3, 5, 4, 6, 7, 8].
uniteUnique([1, 3, 2], [5, 4], [5, 6]) 
// [1, 3, 2, 5, 4, 6].
uniteUnique([1, 3, 2, 3], [5, 2, 1, 4], [2, 1]) 
// [1, 3, 2, 5, 4].
```
- 因為傳入的參數數量不等，用arguments取值並用for迴圈存入陣列中
- 用new Set(arr)去掉重複的值
- 再將obj解構賦值，存到新陣列中並回傳
#### 更厲害的寫法
```javascript
function uniteUnique(...arr) {
  return [...new Set(arr.flat())];
}

const uniteUnique = (...arr) => [...new Set(arr.flat())];
```