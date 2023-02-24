# Panini
## 自訂helper
```javascript
// Example file src/helpers/bold.js
module.exports = function(options) {
  // options.fn(this) = Handelbars content between {{#bold}} HERE {{/bold}}
  var bolder = '<strong>' + options.fn(this) + '</strong>';
  return bolder;
}
```
```html
<div>{{#bold}}這文字會變粗{{/bold}}</div>
```
## 自訂的helper如何促進工作效率
- 格式化資料
    - 電話號碼: 04-12345678
    - 金額加上千分位
    - 
### 電話號碼格式化
```javascript
const phoneNumber = '0412345678';
const formattedPhoneNumber = phoneNumber.replace(/^(\d{2})(\d{4})(\d{4})$/, '$1-$2$3');
console.log(formattedPhoneNumber); // 輸出 "04-12345678"
```
### 數字加千分位
```javascript
(12345.678).toLocaleString('en-US'); // "12,345.678"
// "NTD 12,345.68"
(12345.678).toLocaleString('zh-Hant', {
  style: 'currency',
  currency: 'NTD',
});

// "$12,345.68"
(12345.678).toLocaleString('en-US', {
  style: 'currency',
  currency: 'USD',
});
```