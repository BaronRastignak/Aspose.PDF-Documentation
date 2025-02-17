---
title: Faire pivoter le texte à l'intérieur d'un PDF en utilisant Python
linktitle: Faire pivoter le texte à l'intérieur d'un PDF
type: docs
weight: 50
url: /fr/python-net/rotate-text-inside-pdf/
description: Découvrez différentes façons de faire pivoter du texte dans un PDF. Aspose.PDF vous permet de faire pivoter du texte à n'importe quel angle, de faire pivoter un fragment de texte ou un paragraphe entier.
lastmod: "2024-02-17"
sitemap:
    changefreq: "weekly"
    priority: 0.7
---
<script type="application/ld+json">
{
    "@context": "https://schema.org",
    "@type": "TechArticle",
    "headline": "Faire pivoter le texte à l'intérieur d'un PDF en utilisant Python",
    "alternativeHeadline": "Comment faire pivoter le texte dans un fichier PDF",
    "author": {
        "@type": "Person",
        "name":"Anastasiia Holub",
        "givenName": "Anastasiia",
        "familyName": "Holub",
        "url":"https://www.linkedin.com/in/anastasiia-holub-750430225/"
    },
    "genre": "génération de documents pdf",
    "keywords": "pdf, python, génération de documents",
    "wordcount": "302",
    "proficiencyLevel":"Débutant",
    "publisher": {
        "@type": "Organization",
        "name": "Équipe de documentation Aspose.PDF",
        "url": "https://products.aspose.com/pdf",
        "logo": "https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-python-net.svg",
        "alternateName": "Aspose",
        "sameAs": [
            "https://facebook.com/aspose.pdf/",
            "https://twitter.com/asposepdf",
            "https://www.youtube.com/channel/UCmV9sEg_QWYPi6BJJs7ELOg/featured",
            "https://www.linkedin.com/company/aspose",
            "https://stackoverflow.com/questions/tagged/aspose",
            "https://aspose.quora.com/",
            "https://aspose.github.io/"
        ],
        "contactPoint": [
            {
                "@type": "ContactPoint",
                "telephone": "+1 903 306 1676",
                "contactType": "sales",
                "areaServed": "US",
                "availableLanguage": "en"
            },
            {
                "@type": "ContactPoint",
                "telephone": "+44 141 628 8900",
                "contactType": "sales",
                "areaServed": "GB",
                "availableLanguage": "en"
            },
            {
                "@type": "ContactPoint",
                "telephone": "+61 2 8006 6987",
                "contactType": "sales",
                "areaServed": "AU",
                "availableLanguage": "en"
            }
        ]
    },
    "url": "/python-net/rotate-text-inside-pdf/",
    "mainEntityOfPage": {
        "@type": "WebPage",
        "@id": "/python-net/rotate-text-inside-pdf/"
    },
    "dateModified": "2024-02-04",
    "description": "Découvrez différentes façons de faire pivoter du texte dans un PDF. Aspose.PDF vous permet de faire pivoter du texte à n'importe quel angle, de faire pivoter un fragment de texte ou un paragraphe entier."
}
</script>


## Rotation du Texte à l'Intérieur d'un PDF en Utilisant la Propriété de Rotation

En utilisant la propriété Rotation de la Classe [TextFragment](https://reference.aspose.com/pdf/python-net/aspose.pdf.text/textfragment), vous pouvez faire pivoter le texte à divers angles. La rotation du texte peut être utilisée dans différents scénarios de génération de documents. Vous pouvez spécifier l'angle de rotation en degrés pour faire pivoter le texte selon vos besoins. Veuillez vérifier les différents scénarios suivants, dans lesquels vous pouvez implémenter la rotation du texte.

## Implémenter la Rotation en Utilisant TextFragment et TextBuilder

```csharp
// Pour des exemples complets et des fichiers de données, veuillez visiter https://github.com/aspose-pdf/Aspose.PDF-for-.NET
string dataDir = RunExamples.GetDataDir_AsposePdf_Text();
// Initialiser l'objet document
Document pdfDocument = new Document();
// Obtenir une page particulière
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Créer un fragment de texte
TextFragment textFragment1 = new TextFragment("texte principal");
textFragment1.Position = new Position(100, 600);
// Définir les propriétés du texte
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Créer un fragment de texte pivoté
TextFragment textFragment2 = new TextFragment("texte pivoté");
textFragment2.Position = new Position(200, 600);
// Définir les propriétés du texte
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Créer un fragment de texte pivoté
TextFragment textFragment3 = new TextFragment("texte pivoté");
textFragment3.Position = new Position(300, 600);
// Définir les propriétés du texte
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// créer un objet TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Ajouter le fragment de texte à la page PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Enregistrer le document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```


## Implémenter la Rotation en utilisant TextParagraph et TextBuilder (Fragments Rotés)

```csharp
// Pour des exemples complets et des fichiers de données, veuillez consulter https://github.com/aspose-pdf/Aspose.PDF-for-.NET
string dataDir = RunExamples.GetDataDir_AsposePdf_Text();
// Initialiser l'objet document
Document pdfDocument = new Document();
// Obtenir une page particulière
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// Créer un fragment de texte
TextFragment textFragment1 = new TextFragment("texte roté");
// Définir les propriétés du texte
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Définir la rotation
textFragment1.TextState.Rotation = 45;
// Créer un fragment de texte
TextFragment textFragment2 = new TextFragment("texte principal");
// Définir les propriétés du texte
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Créer un fragment de texte
TextFragment textFragment3 = new TextFragment("autre texte roté");
// Définir les propriétés du texte
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Définir la rotation
textFragment3.TextState.Rotation = -45;
// Ajouter les fragments de texte au paragraphe
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// Créer un objet TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Ajouter le paragraphe de texte à la page PDF
textBuilder.AppendParagraph(paragraph);
// Enregistrer le document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## Implémenter la rotation en utilisant TextFragment et Page.Paragraphs

```csharp
// Pour des exemples complets et des fichiers de données, veuillez visiter https://github.com/aspose-pdf/Aspose.PDF-for-.NET
string dataDir = RunExamples.GetDataDir_AsposePdf_Text();
// Initialiser l'objet document
Document pdfDocument = new Document();
// Obtenir une page particulière
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Créer un fragment de texte
TextFragment textFragment1 = new TextFragment("texte principal");
// Définir les propriétés du texte
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Créer un fragment de texte
TextFragment textFragment2 = new TextFragment("texte tourné");
// Définir les propriétés du texte
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Définir la rotation
textFragment2.TextState.Rotation = 315;
// Créer un fragment de texte
TextFragment textFragment3 = new TextFragment("texte tourné");
// Définir les propriétés du texte
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Définir la rotation
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Enregistrer le document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```


## Implémenter la Rotation en utilisant TextParagraph et TextBuilder (Paragraphe Entier Tourné)

```csharp
// Pour des exemples complets et des fichiers de données, veuillez consulter https://github.com/aspose-pdf/Aspose.PDF-for-.NET
string dataDir = RunExamples.GetDataDir_AsposePdf_Text();
// Initialiser l'objet document
Document pdfDocument = new Document();
// Obtenir une page particulière
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
    TextParagraph paragraph = new TextParagraph();
    paragraph.Position = new Position(200, 600);
    // Spécifier la rotation
    paragraph.Rotation = i * 90 + 45;
    // Créer un fragment de texte
    TextFragment textFragment1 = new TextFragment("Texte du Paragraphe");
    // Créer un fragment de texte
    textFragment1.TextState.FontSize = 12;
    textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
    textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
    textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Créer un fragment de texte
    TextFragment textFragment2 = new TextFragment("Deuxième ligne de texte");
    // Définir les propriétés du texte
    textFragment2.TextState.FontSize = 12;
    textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
    textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
    textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Créer un fragment de texte
    TextFragment textFragment3 = new TextFragment("Et encore du texte...");
    // Définir les propriétés du texte
    textFragment3.TextState.FontSize = 12;
    textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
    textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
    textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    textFragment3.TextState.Underline = true;
    paragraph.AppendLine(textFragment1);
    paragraph.AppendLine(textFragment2);
    paragraph.AppendLine(textFragment3);
    // Créer un objet TextBuilder
    TextBuilder textBuilder = new TextBuilder(pdfPage);
    // Ajouter le fragment de texte à la page PDF
    textBuilder.AppendParagraph(paragraph);
}
// Enregistrer le document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```


<script type="application/ld+json">
{
    "@context": "http://schema.org",
    "@type": "SoftwareApplication",
    "name": "Aspose.PDF pour la bibliothèque .NET",
    "image": "https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-python-net.svg",
    "url": "https://www.aspose.com/",
    "publisher": {
        "@type": "Organization",
        "name": "Aspose.PDF",
        "url": "https://products.aspose.com/pdf",
        "logo": "https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-python-net.svg",
        "alternateName": "Aspose",
        "sameAs": [
            "https://facebook.com/aspose.pdf/",
            "https://twitter.com/asposepdf",
            "https://www.youtube.com/channel/UCmV9sEg_QWYPi6BJJs7ELOg/featured",
            "https://www.linkedin.com/company/aspose",
            "https://stackoverflow.com/questions/tagged/aspose",
            "https://aspose.quora.com/",
            "https://aspose.github.io/"
        ],
        "contactPoint": [
            {
                "@type": "ContactPoint",
                "telephone": "+1 903 306 1676",
                "contactType": "ventes",
                "areaServed": "US",
                "availableLanguage": "en"
            },
            {
                "@type": "ContactPoint",
                "telephone": "+44 141 628 8900",
                "contactType": "ventes",
                "areaServed": "GB",
                "availableLanguage": "en"
            },
            {
                "@type": "ContactPoint",
                "telephone": "+61 2 8006 6987",
                "contactType": "ventes",
                "areaServed": "AU",
                "availableLanguage": "en"
            }
        ]
    },
    "offers": {
        "@type": "Offer",
        "price": "1199",
        "priceCurrency": "USD"
    },
    "applicationCategory": "Bibliothèque de manipulation PDF pour .NET",
    "downloadUrl": "https://www.nuget.org/packages/Aspose.PDF/",
    "operatingSystem": "Windows, MacOS, Linux",
    "screenshot": "https://docs.aspose.com/pdf/python-net/create-pdf-document/screenshot.png",
    "softwareVersion": "2024.1",
    "aggregateRating": {
        "@type": "AggregateRating",
        "ratingValue": "5",
        "ratingCount": "16"
    }
}
</script>