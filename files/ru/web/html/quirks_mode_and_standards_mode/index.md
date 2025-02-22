---
title: Режим совместимости (Quirks Mode) и стандартный режим (Standards Mode)
slug: Web/HTML/Quirks_Mode_and_Standards_Mode
translation_of: Web/HTML/Quirks_Mode_and_Standards_Mode
---
В самом начале веба страницы обычно писались в двух версиях: одна для браузера Netscape Navigator, другая для браузера Microsoft Internet Explorer. Когда W3C были созданы новые веб стандарты, браузеры не могли их сразу использовать, так как это могло привести к некорректному отображению большинства существующих сайтов. Для правильного отображения устаревших сайтов и сайтов, поддерживающих новые стандарты, браузерами были разработаны два режима отображения.

На сегодняшний день существует три режима отображения, которые используются движками разметки (layout engines) браузеров: режим совместимости (quirks mode), частично стандартный режим (almost standards mode) и стандартный режим (full standards mode). В режиме совместимости (**quirks mode)**, разметка эмулирует нестандартное поведение браузеров Navigator 4 и Internet Explorer 5. Этот режим необходим для поддержки сайтов, созданных до начала широкого применения веб стандартов. В стандартном режиме (**full standards mode)** поведение браузера соответствует (будем надеяться) описанному в спецификациях HTML и CSS. В частично стандартном режиме (**almost standards mode)** реализовано лишь незначительное количество так называемых "странностей" (quirks).

## Как браузеры понимают, какой режим использовать?

Браузеры используют тег DOCTYPE, чтобы определить в каком режиме обрабатывать документ. Для отображения страницы в стандартном режиме необходимо добавить тег DOCTYPE в HTML-код страницы как показано в примере ниже:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset=UTF-8>
    <title>Hello World!</title>
  </head>
  <body>
  </body>
</html>
```

Тег DOCTYPE, указанный в примере, - `<!DOCTYPE html>` - самый простой способ обеспечить стандартный режим отображения; использование этого тега рекомендовано стандартом HTML5. Для предыдущих версий HTML рекомендованы другие варианты, но все существующие на текущий момент браузеры используют такой тег DOCTYPE для отображения страницы в стандартном режиме, даже Internet Explorer 6. На сегодняшний день не существует веских причин для использования более сложного тега DOCTYPE. Использование какого-либо другого тега DOCTYPE может привести к переключению браузера в частично стандартный режим отображения или в режим совместимости.

Необходимо удостовериться, что тег DOCTYPE находится в самом начале HTML документа. Если на странице будет что-либо до тега DOCTYPE, например, комментарий или декларирование XML, то браузеры Internet Explorer 9 и выше будут переведены в режим совместимости.

В стандарте HTML5 тег DOCTYPE используется исключительно для активации стандартного режима отображения. Предыдущие версии HTML придавали дополнительное значение использованию тега DOCTYPE, но браузеры использовали тег DOCTYPE исключительно для переключения между режимом совместимости и стандартным режимом.

Смотрите также детальное описание того, [как разные браузеры выбирают режимы](http://hsivonen.iki.fi/doctype/).

### XHTML

Если страница написана в [XHTML](/ru/docs/XHTML "XHTML") формате с указанием типа MIME `application/xhtml+xml` в заголовке `Content-Type`, то не нужно указывать DOCTYPE для активации стандартного режима, так как подобные документы всегда отображаются в стандартном режиме. Важно иметь в виду, что Internet Explorer 8 вместо контента такой страницы отображает [диалоговое окно загрузки](/ru/docs/XHTML#Support "XHTML") как для неизвестного формата, поскольку поддержка XHTML реализована в Internet Explorer, начиная с 9 версии.

Если страница написана в XHTML формате с использованием типа MIME `text/html`, браузер будет интерпретировать его как HTML, поэтому для использования браузером стандартного режима отображения необходимо указать тег DOCTYPE.

## Как узнать, какой режим используется?

В Firefox необходимо в контекстном меню "Информация о странице" (_View Page Info)_ проверить\_ _"Тип визуализации" (\_Render Mode)_.

В Internet Explorer через _F12_ проверить Тип документа (_Document Mode)_.

## В чем разница между режимами?

См. [список странностей (list of quirks)](/ru/docs/Mozilla_Quirks_Mode_Behavior "Mozilla_Quirks_Mode_Behavior") и [частично стандартный режим](/ru/docs/Gecko's_"Almost_Standards"_Mode "Gecko%27s_%22Almost_Standards%22_Mode") для того, чтобы увидеть разницу между режимами.
