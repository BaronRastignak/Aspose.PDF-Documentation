---
title: Insert an Empty Page into a PDF File in Python
type: docs
weight: 70
url: /python-java/insert-an-empty-page-into-a-pdf-file-in-python/
description: Learn how to insert an empty page at a specific position in a PDF file using Python and Aspose.PDF for customized document layout.
---

<ins>To Insert an Empty Page into a Pdf document using **Aspose.PDF Java for Python**, simply invoke **InsertEmptyPage** class.

**Python Code**
```

doc= self.Document()
pdf_document = self.Document()
pdf_document=self.dataDir + 'input1.pdf'

# insert a empty page in a PDF
pdf_document.getPages().insert(1)

# Save the concatenated output file (the target document)
pdf_document.save(self.dataDir + "output.pdf")

print "Empty page added successfully!"

```

**Download Running Code**

Download **Insert an Empty Page (Aspose.PDF)** from any of the below mentioned social coding sites:

- [GitHub](https://github.com/aspose-pdf/Aspose.PDF-for-Java/blob/master/Plugins/Aspose_Pdf_Java_for_Python/test/WorkingWithPages/InsertEmptyPage/InsertEmptyPage.py)
- [CodePlex](http://asposepdfjavapython.codeplex.com/SourceControl/latest#test/WorkingWithPages/InsertEmptyPage/InsertEmptyPage.py)
