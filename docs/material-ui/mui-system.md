# MUI System

v5.11.9

## 安裝

```bash
npm install @mui/styles --legacy-peer-deps
```

## JSS

JSS 是一個 CSS in JS 的函式庫，可以用 JavaScript 來定義 classNames 及 styles

- Website: https://mui.com/system/styles/basics/#getting-started
- 參考: https://ithelp.ithome.com.tw/articles/10219921

```javascript
import React from 'react';
import { makeStyles } from '@mui/styles';

const styles = makeStyles({
  root: {
    backgroundColor: 'purple',
    border: '3px solid teal',
  },
});

export default function MiniPalette() {
  const classes = styles();
  return (
    <div className={classes.root}>
      <h1>Mini Palette</h1>
    </div>
  );
}
```
