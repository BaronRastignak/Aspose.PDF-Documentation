---
title: Insert an Empty Page into a PDF File in PHP
type: docs
weight: 70
url: /java/insert-an-empty-page-into-a-pdf-file-in-php/
description: Learn how to insert an empty page at any position within a PDF file in PHP using Aspose.PDF for flexible document structuring.
lastmod: "2021-06-05"
---

## Aspose.PDF - Insert an Empty Page

To Insert an Empty Page into a Pdf document using **Aspose.PDF Java for PHP**, simply invoke **InsertEmptyPage** class.

PHP Code

```php

# Open the target document
$pdf = new Document($dataDir . 'input1.pdf');

# insert a empty page in a PDF
$pdf->getPages()->insert(1);

# Save the concatenated output file (the target document)
$pdf->save($dataDir . "output.pdf");

print "Empty page added successfully!";

```

**Download Running Code**

Download **Insert an Empty Page (Aspose.PDF)** from any of the below mentioned social coding sites:

- [GitHub](https://github.com/aspose-pdf/Aspose.PDF-for-Java/blob/master/Plugins/Aspose_Pdf_Java_for_PHP/src/Aspose/Pdf/WorkingWithPages/InsertEmptyPage.php)
