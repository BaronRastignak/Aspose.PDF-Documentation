---
title: Converter PDF para HTML em Python
linktitle: Converter PDF para formato HTML
type: docs
weight: 50
url: /pt/python-net/convert-pdf-to-html/
lastmod: "2021-11-01"
description: Este tópico mostra como converter arquivo PDF para formato HTML com a biblioteca Aspose.PDF para Python .NET.
sitemap:
    changefreq: "monthly"
    priority: 0.8
---

## Visão Geral

Este artigo explica como **converter PDF para HTML usando Python**. Ele abrange estes tópicos.

_Formato_: **HTML**
- [Python PDF para HTML](#python-pdf-to-html)
- [Python Converter PDF para HTML](#python-pdf-to-html)
- [Python Como converter arquivo PDF para HTML](#python-pdf-to-html)


## Converter PDF para HTML

**Aspose.PDF para Python via .NET** oferece muitos recursos para converter vários formatos de arquivo em documentos PDF e converter arquivos PDF em vários formatos de saída.
 Este artigo discute como converter um arquivo PDF em <abbr title="HyperText Markup Language">HTML</abbr>. Você pode usar apenas algumas linhas de código em Python para converter PDF em HTML. Você pode precisar converter PDF para HTML se quiser criar um site ou adicionar conteúdo a um fórum online. Uma maneira de converter PDF para HTML é usar Python programaticamente.

{{% alert color="success" %}}
**Tente converter PDF para HTML online**

Aspose.PDF para Python apresenta a você um aplicativo online gratuito ["PDF para HTML"](https://products.aspose.app/pdf/conversion/pdf-to-html), onde você pode tentar investigar a funcionalidade e qualidade com que funciona.

[![Aspose.PDF Conversão PDF para HTML com Aplicativo Gratuito](pdf_to_html.png)](https://products.aspose.app/pdf/conversion/pdf-to-html)
{{% /alert %}}

<a name="csharp-pdf-to-html"><strong>Passos: Converter PDF para HTML em Python</strong></a>

1. Crie uma instância do objeto [Document](https://reference.aspose.com/pdf/python-net/aspose.pdf/document/) com o documento PDF de origem.
2. Salve-o em [HtmlSaveOptions](https://reference.aspose.com/pdf/python-net/aspose.pdf/htmlsaveoptions/) chamando o método [save()](https://reference.aspose.com/pdf/python-net/aspose.pdf/document/#methods).

```python

    import aspose.pdf as ap

    input_pdf = DIR_INPUT + "sample.pdf"
    output_pdf = DIR_OUTPUT + "convert_pdf_to_html.html"
    # Abra o documento PDF
    document = ap.Document(input_pdf)

    # salve o documento no formato HTML
    save_options = ap.HtmlSaveOptions()
    document.save(output_pdf, save_options)
```

## Veja Também

Este artigo também aborda esses tópicos. Os códigos são os mesmos que acima.

_Formato_: **HTML**
- [Código Python PDF para HTML](#python-pdf-to-html)
- [API Python PDF para HTML](#python-pdf-to-html)
- [Python PDF para HTML Programaticamente](#python-pdf-to-html)
- [Biblioteca Python PDF para HTML](#python-pdf-to-html)
- [Python Salvar PDF como HTML](#python-pdf-to-html)
- [Python Gerar HTML a partir de PDF](#python-pdf-to-html)
- [Python Criar HTML a partir de PDF](#python-pdf-to-html)

- [Conversor Python PDF para HTML](#python-pdf-to-html)