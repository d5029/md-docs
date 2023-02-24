# Handlebars
## 自訂helper
```javascript
Handlebars.registerHelper("formatName", function(property1, property2){
    return new Handlebars.SafeString(`Hello my name is <strong>${property1}</strong> and I live at <strong>${property2}</strong>`)
})
```
```html
<div>{{formatName XXX}}</div>
```