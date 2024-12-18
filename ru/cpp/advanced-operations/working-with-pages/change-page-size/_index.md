---
title: Изменение размера страницы PDF программным способом
linktitle: Изменение размера страницы PDF
type: docs
weight: 40
url: /ru/cpp/change-page-size/
description: Измените размер страницы в вашем PDF файле с помощью библиотеки C++.
lastmod: "2021-12-08"
sitemap:
    changefreq: "weekly"
    priority: 0.7
---

PDF — это формат статической компоновки для печати, поэтому он стал широко распространён в деловой жизни.

Однако у вас могут быть задачи, когда нужно изменить размер вашего PDF документа, так как размер страницы больше, чем размер бумаги. Но как?

Не беспокойтесь. На этой странице вы найдёте способ решить вашу задачу.

Но сначала давайте вспомним, что существует серия размеров страниц.

Существует две серии размеров страниц, широко принятые в мире.
Конечно, существует много форматов, но есть наиболее часто используемые.
Первая — это ISO размеры бумаги. Series A4 используется для стандартной печати и канцелярских принадлежностей. Бумага формата Letter используется для плакатов, настенных таблиц и т. д. Соединенные Штаты, Канада и частично Мексика приняли вторую серию размеров страниц, и сегодня они являются единственными индустриальными странами, в которых стандарты ISO на размеры бумаги еще не получили широкого распространения.

Теперь давайте посмотрим, как Aspose.PDF предлагает вам изменить размер страницы с помощью библиотеки C++.

## Изменение размера страницы PDF

Aspose.PDF для C++ позволяет изменить размер страницы PDF с помощью простых строк кода в ваших C++ приложениях. Эта тема объясняет, как обновить/изменить размеры страницы в существующем PDF-файле.

Класс [Page](https://reference.aspose.com/pdf/cpp/class/aspose.pdf.page) содержит метод SetPageSize(...), который позволяет установить размер страницы. Приведенный ниже фрагмент кода обновляет размеры страницы в несколько простых шагов:

1. Загрузите исходный PDF-файл.
1. Получите страницы в объект [PageCollection](https://reference.aspose.com/pdf/cpp/class/aspose.pdf.page_collection).
1. Получите заданную страницу.
1. Вызовите метод SetPageSize(..), чтобы обновить его размеры.
1. Вызовите метод Save(..) класса [Document](https://reference.aspose.com/pdf/cpp/class/aspose.pdf.document), чтобы создать PDF файл с обновленными размерами страницы.

Следующий фрагмент кода показывает, как изменить размеры страницы PDF на размер A4.

```cpp
void ChangePageSize() {

    String _dataDir("C:\\Samples\\");
    String inputFileName("UpdateDimensions.pdf");
    String outputFileName("UpdateDimensions_out.pdf");

    // Открыть документ
    auto document = MakeObject<Document>(_dataDir + inputFileName);

    // Получить конкретную страницу
    auto pdfPage = document->get_Pages()->idx_get(1);

    // Установить размер страницы как A4 (11.7 x 8.3 дюйма), и в Aspose.Pdf, 1 дюйм = 72 точки
    // Таким образом, размеры A4 в точках будут (842.4, 597.6)
    pdfPage->SetPageSize(597.6, 842.4);
    // Сохранить обновленный документ
    document->Save(_dataDir + outputFileName);
}
```

## Получение размера страницы PDF

Вы можете прочитать размер страницы PDF существующего PDF файла, используя Aspose.PDF для С++. Следующий пример кода показывает, как прочитать размеры страницы PDF с использованием C++.

```cpp
void GetPDFPageSize() {

    String _dataDir("C:\\Samples\\");
    String inputFileName("UpdateDimensions.pdf");

    // Открыть документ
    auto document = MakeObject<Document>(_dataDir + inputFileName);

    // Получить конкретную страницу
    auto page = document->get_Pages()->idx_get(1);

    // Получить информацию о высоте и ширине страницы
    Console::WriteLine(u"{0} {1}", page->GetPageRect(true)->get_Width(), page->GetPageRect(true)->get_Height());
    // Повернуть страницу на 90 градусов
    page->set_Rotate(Rotation::on90);
    // Получить информацию о высоте и ширине страницы
    Console::WriteLine(u"{0} {1}", page->GetPageRect(true)->get_Width(), page->GetPageRect(true)->get_Height());

}
```