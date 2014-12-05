# paste.js

`paste.js` это интерфейс для чтения информации (текст / изображение) из буфера обмена в различных браузерах. Он также содержит немного браузерных хаков.


## Совместимость

|                              | IE11 | Firefox 33 | Chrome 38 | Safari | Opera |
|------------------------------|------|------------|-----------|--------|-------|
| pasteText (non-inputable)    | ok   | ok         | ok        | ok     | ok    |
| pasteText (textarea)         | ok   | ok         | ok        | ok     | ok    |
| pasteText (contenteditable)  | ok   | ok         | ok        | ok     | ok    |
| pasteImage (non-inputable)   | ok   | ok         | ok        |        |       |
| pasteImage (textarea)        | ok   | ok         | ok        |        |       |
| pasteImage (contenteditable) | ok   | ok         | ok        |        |       |

## Использование

```js
// jQuery необходим

// для вставки в обычный элемент, текстовое поле или редактируемый элемент
$('.mydiv, textarea, div[contenteditable]').pastableElement();

// можно использовать один обработчик
$('*').on('pasteImage', function (ev, data){
  console.log("dataURL: " + data.dataURL);
  console.log("width: " + data.width);
  console.log("height: " + data.height);
  console.log(data.blob);
}).on('pasteText', function (ev, data){
  console.log("text: " + data.text);
});
```

## Допольнительно

Смотрите [этот пример](http://micy.in/paste.js/)
