# Panini

## 自訂 helper

```javascript
// Example file src/helpers/bold.js
module.exports = function (options) {
  // options.fn(this) = Handelbars content between {{#bold}} HERE {{/bold}}
  var bolder = '<strong>' + options.fn(this) + '</strong>';
  return bolder;
};
```

```html
<div>{{#bold}}這文字會變粗{{/bold}}</div>
```

## 自訂的 helper 如何促進工作效率

- 格式化資料
  - 電話號碼: 04-12345678
  - 金額加上千分位
- 製作 template
  - Modal
  - button 樣態，如編輯、新增、刪除、outline 等等
  - 已制定好的 html 碼，例如表單輸入時 require 的紅色\*字號

### 電話號碼格式化

```javascript
const phoneNumber = '0412345678';
const formattedPhoneNumber = phoneNumber.replace(
  /^(\d{2})(\d{4})(\d{4})$/,
  '$1-$2$3'
);
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

### modal

將常用的 modal 設定做成 helper，如：置中對其、按背景不可關閉、scroll 等設定。

```javascript
// modal.js
module.exports = function () {};
```

```html
{{#modal '這是標題''example-modal'true}}...{{/modal}}
```

### btn

設定常用帶 icon 的按鈕，如：新增、移除、編輯、取消、submit 等。

```javascript
// btn.js
module.exports = function () {};
```

### require

要用 Handlebar 的 SafeString 方法，才能順利輸出 html tag。不然 html tag 會被當成字串呈現。

```javascript
// require.js
const Handlebars = require('handlebars');
module.exports = function () {
  return new Handlebars.SafeString(`<span class="text-danger">*</span`);
};
```

```html
<label for="name">姓名{{require}}</label>
```

不用 Handlebar，也可以用三層花括弧呈現格式化的 HTML 碼。

```javascript
// require.js
module.exports = function () {
  return `<span class="text-danger">*</span`;
};
```

```html
<label for="name">姓名{{{require}}}</label>
```
