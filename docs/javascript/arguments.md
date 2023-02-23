# arguments
arguments object 是一個存儲所有傳遞給函式的值的object。 arguments 對象採用 JSON 對象的結構。
```javascript
function viewArgs() {
    return arguments;
}
console.log(viewArgs([3, 5, 1, 2, 2], 2, 3, 5));    
console.log(viewArgs([2, 3, 2, 3, 2, 3]));   
console.log(viewArgs(3,2,1,"life the universe and all"));
console.log(viewArgs("Douglas","Adams"));
console.log(viewArgs(["hello", "World!", 'and', 'thanks', 'for','all','the', 'fish'], "dolphines", 42));
```
Output:
```javascript
{ '0': [ 3, 5, 1, 2, 2 ], '1': 2, '2': 3, '3': 5 }
{ '0': [ 2, 3, 2, 3, 2, 3 ] }
{ '0': 3, '1': 2, '2': 1, '3': 'life the universe and all' }
{ '0': 'Douglas', '1': 'Adams' }
{ '0': [ 'hello', 'World!', 'and', 'thanks', 'for', 'all', 'the', 'fish' ],   '1': 'dolphins',   '2': 42 }
```
## 轉成陣列
- arguments不是陣列，是objec
- 用Array.prototype.slice.call method (arguments)轉成陣列
```javascript
var args = Array.prototype.slice.call(arguments)
```
但是freeCodeCamp說不建議使用slice方法，他會阻止 JavaScript 引擎（例如 V8）的優化，嘗試通過for迴圈來構造一個新的array。
```javascript
var args = []; 
for (var i = 0; i < arguments.length; i++) {
    args.push(arguments[i])
} 
```
## 參考
- [類陣例（Array-like）物件](https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Reference/Global_Objects/Array/slice#%E9%A1%9E%E9%99%A3%E4%BE%8B%EF%BC%88array-like%EF%BC%89%E7%89%A9%E4%BB%B6)
- [How Arguments work in JavaScript - JavaScript Arguments Guide](https://forum.freecodecamp.org/t/how-arguments-work-in-javascript-javascript-arguments-guide/14283)