# chroma.js

chroma.js 是一個小型零依賴 JavaScript 庫 (13.5kB)，用於各種顏色轉換和色階。

```besh
npm install chroma-js.
```

## 亮度 luminance()

用來判斷顏色的亮度，最亮返回 1，最暗返回 0。

[更多設定](https://gka.github.io/chroma.js/#color-luminance)

```javascript
import chroma from 'chroma-js';

const isDark = chroma('white').luminance() <= 0.08;
```
