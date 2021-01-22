---
title: Convert PDF to JPG | C#
linktitle: Convert PDF to JPG
type: docs
weight: 10
url: /net/convert-pdf-to-jpg/
description:  This page describes how to convert PDF Pages to JPEG image, convert all and single pages to JPEG images with Aspose.PDF for .NET.
alises:
    - /pdf/net/convert-pdf-pages-to-jpeg-image/
lastmod: "2021-01-15"
sitemap:
    changefreq: "weekly"
    priority: 0.7
---

The JpegDevice class allows you to convert PDF pages to JPEG images. This class provides a method named Process which allows you to convert a particular page of the PDF file to JPEG image format with C#.

## Convert PDF Pages to JPG Images

{{% alert color="primary" %}}

Try online. You can check the quality of Aspose.PDF conversion and view the results online at this link  [products.aspose.app/pdf/conversion/pdf-to-jpg](https://products.aspose.app/pdf/conversion/pdf-to-jpg)

{{% /alert %}}

Aspose.PDF for .NET allows you to convert all pages in a PDF file to images:

1. Loop through all pages in the file.
1. Convert each page individually:
    - Create an object of the Document class to load the PDF document.
    - Get the page you want to convert.
    - Call the Process method to convert the page to Jpeg.

The following code snippet shows you how to convert all PDF pages to Jpeg images.

## Convert single PDF page to JPG image

Aspose.PDF for .NET allows you to convert a particular page to Jpeg format:

Pass the page index as an argument to the Process(..) method.
The following code snippet shows the steps to convert the first page of PDF to Jpeg format.

```csharp
public static void ConvertPDFtoJpegSinglePage()
{
    // Open document
    Document pdfDocument = new Document(_dataDir + "PageToJpeg.pdf");

    using (FileStream imageStream = new FileStream(_dataDir + "image_out.Jpeg", FileMode.Create))
    {
        // Create Resolution object
        Resolution resolution = new Resolution(300);
        // Create Jpeg device with specified attributes
        // Width, Height, Resolution
        JpegDevice JpegDevice = new JpegDevice(500, 700, resolution);

        // Convert a particular page and save the image to stream
        JpegDevice.Process(pdfDocument.Pages[1], imageStream);

        // Close stream
        imageStream.Close();
    }
}
```