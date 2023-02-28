# 寫程式

## 建立對照表

DNA 鏈對由核鹼基對組成。 鹼基對由字符 AT 和 CG 表示，它們構成了 DNA 雙螺旋結構的組成部分。 DNA 鏈缺少配對元素。
編寫一個函式來為所提供的 DNA 鏈匹配缺失的鹼基對。 對於提供的字符串中的每個字符，找到鹼基對字符。 將結果作為二維數組返回。

例如，對於輸入的 GCG，返回[["G", "C"], ["C","G"], ["G", "C"]]

來源：https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-dna-pairing/16009

```javascript
function pairElement(str) {
  const pairs = {
    A: 'T',
    T: 'A',
    C: 'G',
    G: 'C',
  };
  return str.split('').map((x) => [x, pairs[x]]);
}

pairElement('GCG');
// [ [ 'G', 'C' ], [ 'C', 'G' ], [ 'G', 'C' ] ]
pairElement('ATCGA');
// [ [ 'A', 'T' ], [ 'T', 'A' ], [ 'C', 'G' ], [ 'G', 'C' ], [ 'A', 'T' ] ]
pairElement('TTGAG');
// [ [ 'T', 'A' ], [ 'T', 'A' ], [ 'G', 'C' ], [ 'A', 'T' ], [ 'G', 'C' ] ]
pairElement('CTCTA');
// [ [ 'C', 'G' ], [ 'T', 'A' ], [ 'C', 'G' ], [ 'T', 'A' ], [ 'A', 'T' ] ]
```

## handle+事件名稱

事件的函式命名為'handle+事件名稱'。例如 handleClick()、handleSubmit()等等。

但是，每個按鈕都嘛是 click，這時可以特別註明。如：handleDrawerOpen()、handleDrawerClose()

```html
<button onclick="handleClick()">...</button>
```

```javascript
function handleClick(){
  generate();
}
function generate(){
  ...
}
```
