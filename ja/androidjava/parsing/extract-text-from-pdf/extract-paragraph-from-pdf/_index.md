---
title: PDFから段落を抽出 
linktitle: 段落を抽出
type: docs
weight: 20
url: /ja/androidjava/extract-paragraph-from-pdf/
description: この記事では、Aspose.PDFの特別なツールであるParagraphAbsorberを使用してPDFドキュメントからテキストを抽出する方法について説明します。
lastmod: "2021-06-05"
sitemap:
    changefreq: "weekly"
    priority: 0.7
---

## PDFドキュメントから段落形式でテキストを抽出

特定のテキスト（「プレーンテキスト」または「正規表現」を使用）を単一のページまたはドキュメント全体から検索することでPDFドキュメントからテキストを取得することができます。また、単一ページ、ページ範囲、またはドキュメント全体の完全なテキストを取得することもできます。
 しかし、場合によっては、PDFドキュメントから段落を抽出する必要があるか、段落形式のテキストが必要です。PDFドキュメントページのテキスト内でセクションと段落を検索する機能を実装しました。ParagraphAbsorberクラス（TextFragmentAbsorberやTextAbsorberのようなもの）を導入しており、これを使用してPDFドキュメントから段落を抽出できます。ParagraphAbsorberを使用するには、次の2つの方法があります。

**1- PDFページ上のテキストのセクションと段落の境界を描くことによって:**

```java
public static void ExtractParagraph() {
        // ドキュメントディレクトリへのパス。
        Document doc = new Document(_dataDir + "input.pdf");
        Page page = doc.getPages().get_Item(2);

        ParagraphAbsorber absorber = new ParagraphAbsorber();
        absorber.visit(page);

        PageMarkup markup = absorber.getPageMarkups().get(0);

        for (MarkupSection section : markup.getSections()) {
            DrawRectangleOnPage(section.getRectangle(), page);
            for (MarkupParagraph paragraph : section.getParagraphs()) {
                DrawPolygonOnPage(paragraph.getPoints(), page);
            }
        }

        doc.save(_dataDir + "output_out.pdf");
    }

    private static void DrawRectangleOnPage(Rectangle rectangle, Page page) {
        page.getContents().add(new GSave());
        page.getContents().add(new ConcatenateMatrix(1, 0, 0, 1, 0, 0));
        page.getContents().add(new SetRGBColorStroke(0, 1, 0));
        page.getContents().add(new SetLineWidth(2));
        page.getContents()
                .add(new Re(rectangle.getLLX(), rectangle.getLLY(), rectangle.getWidth(), rectangle.getHeight()));
        page.getContents().add(new ClosePathStroke());
        page.getContents().add(new GRestore());
    }

    private static void DrawPolygonOnPage(Point[] polygon, Page page) {
        page.getContents().add(new GSave());
        page.getContents().add(new ConcatenateMatrix(1, 0, 0, 1, 0, 0));
        page.getContents().add(new SetRGBColorStroke(0, 0, 1));
        page.getContents().add(new SetLineWidth(1));
        page.getContents().add(new MoveTo(polygon[0].getX(), polygon[0].getY()));
        for (int i = 1; i < polygon.length; i++) {
            page.getContents().add(new LineTo(polygon[i].getX(), polygon[i].getY()));
        }
        page.getContents().add(new LineTo(polygon[0].getX(), polygon[0].getY()));
        page.getContents().add(new ClosePathStroke());
        page.getContents().add(new GRestore());
    }
```

**2- 段落コレクションを反復処理してテキストを取得することによって:**

```java
 public static void ExtractParagraph02() {
        // 既存のPDFファイルを開く
        Document doc = new Document(_dataDir + "input.pdf");
        // ParagraphAbsorberをインスタンス化する
        ParagraphAbsorber absorber = new ParagraphAbsorber();
        absorber.visit(doc);

        for (PageMarkup markup : absorber.getPageMarkups()) {
            int i = 1;
            for (MarkupSection section : markup.getSections()) {
                int j = 1;

                for (MarkupParagraph paragraph : section.getParagraphs()) {
                    StringBuilder paragraphText = new StringBuilder();

                    for (java.util.List<TextFragment> line : paragraph.getLines()) {
                        for (TextFragment fragment : line) {
                            paragraphText.append(fragment.getText());
                        }
                        paragraphText.append("\r\n");
                    }
                    paragraphText.append("\r\n");

                    System.out.println("セクション " + i + " の段落 " + j + " ページ上の" + ":" + markup.getNumber());
                    System.out.println(paragraphText.toString());

                    j++;
                }
                i++;
            }
        }
    }
```