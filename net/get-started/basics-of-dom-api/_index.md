---
title: Basics of DOM API
type: docs
weight: 10
url: /net/basics-of-dom-api/
description: Aspose.PDF for .NET also uses the idea of DOM to represent the structure of a PDF document in terms of objects. Here you can read the description of this structure.
---

## Introduction to the DOM API

Document Object Model (DOM) is a form of representation of structured documents as an object-oriented model. DOM is the official World Wide Web Consortium (W3C) standard for representing structured document s in a platform and language-neutral manner.

In simple words, DOM is a tree of objects that represent the structure of some document. Aspose.PDF for .NET also uses the idea of DOM to represent the structure of a PDF document in terms of objects. However, the aspects of the DOM (such as its Elements) are manipulated within the syntax of the programming language in use. The public interface of a DOM is specified in its application programming interface (API).

### Introduction to PDF Document

Portable Document Format (PDF) is an open standard for document exchange. A PDF document is a combination of text and binary data. If you open it in a text editor, you will see the raw objects that define the structure and contents of the document.

The logical structure of a PDF file is hierarchical and determines the sequence by which a viewing application draws the document’s pages and their contents. A PDF is composed of four components: objects, file structure, document structure and content streams.

### PDF Document Structure

As the structure of a PDF file is hierarchical, Aspose.PDF for .NET also accesses the elements in the same way. The following hierarchy shows you how the PDF document is logically structured and how Aspose.PDF for .NET DOM API constructs it.

![PDF Document Structure](../images/structure.png)

### Accessing PDF Document Elements

The Document object is at the root level of the object model. The Aspose.PDF for .NET DOM API allows you to create a Document object and then access all other objects in the hierarchy. You can either access any of the collections like Pages or individual element like Page etc. The DOM API provides single entry and exit points to manipulate the PDF document as shown below:

- Open PDF document
- Access PDF document structure in DOM style
- Update data in the PDF document
- Validate PDF document
- Export PDF document into different formats
- Finally, save the updated PDF document

## How to Use New Aspose.PDF for .NET API

This topic will explain the new Aspose.PDF for .NET API and guide you to get started quickly and easily. Please note that the details regarding the use of the particular features are not the part of this article. You will find details, examples and code snippets in the Developer Guide and Technical Articles sections.

The new Aspose.PDF for .NET is composed of three parts:

- Aspose.PDF for .NET DOM API
- Aspose.PDF.Generator (old Aspose.PDF for .NET pre-6.x)
- Aspose.PDF.Facades (old Aspose.PDF.Kit for .NET)
You'll find the details of each of these areas below.

### Aspose.PDF for .NET DOM API

The new API of Aspose.PDF for .NET is DOM based. You can find more details about the DOM API and PDF document structure in the article [Introduction to DOM API|Introduction to DOM API. In this section, we'll elaborate the use of the new DOM API.

The new Aspose.PDF for .NET DOM API corresponds to the PDF document structure, which helps you to work with the PDF documents not only at the file and document level, but also at the object level. We have provided more flexibility to the developers to access all of the elements and objects of the PDF document. Using the Aspose.PDF DOM API's classes, you can gain programmatic access to document elements and formatting. This new DOM API is comprised of various namespaces as given below:

### Aspose.PDF

This namespace provides the Document class which allows you to open and save a PDF document. The License class is also a part of this namespace. It also provides classes related to PDF pages, attachments, and bookmarks like Page, PageCollection, FileSpecification, EmbeddedFileCollection, OutlineItemCollection, and OutlineCollection etc.

#### Aspose.Text

This namespace provides classes which help you work with the text and its various aspects, for example Font, FontCollection, FontRepository, FontStyles, TextAbsorber, TextFragment, TextFragmentAbsorber, TextFragmentCollection, TextFragmentState, TextSegment and TextSegmentCollection etc.

#### Aspose.Text.TextOptions

This namespace provides classes that allow you to set different options for searching, editing or replacing text, for example TextEditOptions, TextReplaceOptions and TextSearchOptions.

#### Aspose.InteractiveFeatures

This namespace contains classes that help you work with the interactive features of the PDF document, for example working with the document and other actions. This namespace contains classes like GoToAction, GoToRemoteAction and GoToURIAction etc.

#### Aspose.InteractiveFeatures.Annotations

Annotations are a part of a PDF document's interactive features. We have dedicated a namespace for annotations. This namespace contains classes that help you work with the annotations, for example, Annotation, AnnotationCollection, CircleAnnotation and LinkAnnotation etc.

#### Aspose.InteractiveFeatures.Forms

This namespace contains classes that help you work with PDF forms and form fields, for example Form, Field, TextBoxField and OptionCollection etc.

#### Aspose.PDF.Devices

We can perform various operations on the PDF documents such as converting PDF document to various image formats. However, such operations do not belong to the Document object and we cannot extend the Document class for such operations. That's why we have introduced the concept of the Device in the new DOM API.

#### Aspose.PDF.Generator

The old Aspose.PDF for.NET (pre-6.0) provided the features to create new PDF file from scratch. As we have merged old Aspose.PDF and Aspose.PDF.Kit, all the classes previously available in old Aspose.PDF for .NET have been moved under the Aspose.PDF.Generator namespace. So, if you want to execute the old Aspose.PDF code using the new product, use this namespace.

This namespace is obsolete and starting Aspose.PDF for .NET 17.5, it is removed from API.

##### Aspose.PDF.Facades

Previous to Aspose.PDF for .NET t.o.o, you needed Aspose.PDF.Kit for .NET to manipulate existing PDF files. To execute old Aspose.PDF.Kit code, can use Aspose.PDF.Facades namespace.