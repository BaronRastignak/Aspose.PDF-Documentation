---
title: Преобразование XFA Form в AcroForm
linktitle: Преобразование XFA Form
type: docs
weight: 10
url: /ru/php-java/convert-form/
description: Этот раздел объясняет, как преобразовать XFA Form в AcroForm с помощью Aspose.PDF для PHP через Java.
lastmod: "2024-06-05"
sitemap:
    changefreq: "weekly"
    priority: 0.7
---

## Преобразование динамической XFA Form в стандартную AcroForm

Динамические формы основаны на XML-спецификации, известной как XFA, «XML Forms Architecture». Она также может преобразовать динамическую XFA форму в стандартную Acroform. Информация о форме (что касается PDF) очень расплывчата – она указывает, что поля существуют, с определенными свойствами и JavaScript событиями, но не указывает никакого рендеринга. Объекты XFA формы рисуются во время загрузки документа.

В настоящее время PDF поддерживает два различных метода для интеграции данных и PDF форм:

- AcroForms (также известные как Acrobat формы), введенные и включенные в спецификацию формата PDF 1.2.

- Формы Adobe XML Forms Architecture (XFA), введенные в спецификации формата PDF 1.5 как дополнительная функция. (Спецификация XFA не включена в спецификацию PDF, она только упоминается.)

Невозможно извлечь или изменить страницы форм XFA, поскольку содержимое формы генерируется во время выполнения (во время просмотра формы XFA) в приложении, пытающемся отобразить или визуализировать форму XFA. Aspose.PDF имеет функцию, которая позволяет разработчикам конвертировать формы XFA в стандартные AcroForms.

```php

        // Загрузить форму XFA
        $document = new Document($inputFile);
        
        // Установить тип полей формы как стандартный AcroForm
        $formType = new FormType();
        $document->getForm()->setType($formType->getStandard());
            
        // Сохранить обновленный документ
        $document->save($outputFile);
        
        // Сохранить измененный PDF    
        $document->close();
```