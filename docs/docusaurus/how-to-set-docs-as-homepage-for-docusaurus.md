# 如何設定首頁
### 官方
#### 1) 在 /docs/ 中建立一個想要作為主頁的md檔，並將 slug 設置為 /
```markdown
---
id: my-home-doc
slug: /
---

My home doc content....
```
#### 2) 在 docusaurus.config.js 添加 routeBasePath: '/'
```javascript
presets: [
  [
    '@docusaurus/preset-classic',
    {
      docs: {
        routeBasePath: '/',
```
#### 3) 刪除index.js
```javascript
./src/pages/index.js
```
### Hack
使用redirect
```javascript
import React from 'react';
import  { Redirect } from 'react-router-dom';

export default function Home() {
  return <Redirect to='/docs/intro' />;
}
```