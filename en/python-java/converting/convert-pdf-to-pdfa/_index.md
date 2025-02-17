---
title: Convert PDF to PDF/A formats in Python
linktitle: Convert PDF to PDF/A formats
type: docs
weight: 100
url: /python-java/convert-pdf-to-pdfa/
lastmod: "2023-04-06"
description: Explore the steps to convert PDF files to PDF/A format for long-term archiving using Aspose.PDF in Python via Java. 
sitemap:
    changefreq: "monthly"
    priority: 0.8
---

**Aspose.PDF for Python** allows you to convert a PDF file to a <abbr title="Portable Document Format / A">PDF/A</abbr> compliant PDF file. Before doing so, the file must be validated. This topic explains how.

{{% alert color="primary" %}}

Please note we follow Adobe Preflight for validating PDF/A conformance. All tools on the market have their own “representation” of PDF/A conformance. Please check this article on PDF/A validation tools for reference. We chose Adobe products for verifying how Aspose.PDF produces PDF files because Adobe is at the center of everything connected to PDF.

{{% /alert %}}

Convert the file using the Document class Convert method. Before converting the PDF to PDF/A compliant file, validate the PDF using the Validate method. The validation result is stored in an XML file and then this result is also passed to the Convert method. You can also specify the action for the elements which cannot be converted using the ConvertErrorAction enumeration.

{{% alert color="success" %}}
**Try to convert PDF to PDF/A online**

Aspose.PDF for Python presents you online free application ["PDF to PDF/A-1A"](https://products.aspose.app/pdf/conversion/pdf-to-pdfa1a), where you may try to investigate the functionality and quality it works.

[![Aspose.PDF Convertion PDF to PDF/A with Free App](pdf_to_pdfa.png)](https://products.aspose.app/pdf/conversion/pdf-to-pdfa1a)
{{% /alert %}}


## Convert PDF file to PDF/A-1b

The following code snippet shows how to convert PDF files to PDF/A-1b compliant PDF.

```python


from asposepdf import Api

DIR_INPUT = "testdata/"
DIR_OUTPUT = "testout/"
input_pdf = DIR_INPUT + "Hello.pdf"
output_pdf = DIR_OUTPUT + "convert_pdf_to_pdfa.pdf"
output_log = DIR_OUTPUT + "convert_pdf_to_pdfa.log"
# Open PDF document
document = Api.Document(input_pdf)
# Convert to PDF/A compliant document
document.convert(output_log, Api.PdfFormat.PDF_A_1B, Api.ConvertErrorAction.Delete)
# Save output document
document.save(output_pdf)
```

