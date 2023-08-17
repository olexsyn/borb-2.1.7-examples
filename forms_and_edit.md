# Table of Contents

4 [Forms](#4-forms)  
  4.1 [Acroforms vs XFA](#41-acroforms-vs-xfa)  
  4.2 [The `FormField` object](#42-the-formfield-object)  
  4.3 [Adding `FormField` objects to a PDF](#43-adding-formfield-objects-to-a-pdf)  
    4.3.1 [Adding a `TextField` to a PDF](#431-adding-a-textfield-to-a-pdf)  
    4.3.2 [Customizing a `TextField` object](#432-customizing-a-textfield-object)  
    4.3.3 [Pre-filling a `TextField` object](#433-pre-filling-a-textfield-object)  
    4.3.4 [Adding a `DropDownList` to a PDF](#434-adding-a-dropdownlist-to-a-pdf)  
    4.3.5 [Adding a `CountryDropDownList` to a PDF](#435-adding-a-countrydropdownlist-to-a-pdf)  
    4.3.6 [Adding a `CheckBox` to a PDF](#436-adding-a-checkbox-to-a-pdf)  
    4.3.7 [Adding a `RadioButton` to a PDF](#437-adding-a-radiobutton-to-a-pdf)  
    4.3.8 [Adding a `PushButton` to a PDF](#438-adding-a-pushbutton-to-a-pdf)  
    4.3.9 [Adding a `JavaScriptPushButton` to a PDF](#439-adding-a-javascriptpushbutton-to-a-pdf)  
  4.4 [Getting the value of a `FormField` in an existing PDF](#44-getting-the-value-of-a-formfield-in-an-existing-pdf)  
  4.5 [Changing the value of a `FormField` in an existing PDF](#45-changing-the-value-of-a-formfield-in-an-existing-pdf)  
    4.5.1 [Changing the value of a `FormField` in an existing PDF using `borb`](#451-changing-the-value-of-a-formfield-in-an-existing-pdf-using-borb)  
    4.5.2 [Changing the value of a `FormField` in an existing PDF using `JavaScript`](#452-changing-the-value-of-a-formfield-in-an-existing-pdf-using-javascript)  
  4.6 [Conclusion](#46-conclusion)  
5 [Working with existing PDFs](#5-working-with-existing-pdfs)  
  5.1 [Extracting meta-information](#51-extracting-meta-information)  
    5.1.1 [Extracting the author from a PDF](#511-extracting-the-author-from-a-pdf)  
    5.1.2 [Extracting the producer from a PDF](#512-extracting-the-producer-from-a-pdf)  
    5.1.3 [using XMP meta information](#513-using-xmp-meta-information)  
  5.2 [Extracting text from a PDF](#52-extracting-text-from-a-pdf)  
  5.3 [Extracting text using regular expressions](#53-extracting-text-using-regular-expressions)  
  5.4 [Extracting text using its bounding box](#54-extracting-text-using-its-bounding-box)  
  5.5 [Combining regular expressions and bounding boxes](#55-combining-regular-expressions-and-bounding-boxes)  
  5.6 [Extracting keywords from a PDF](#56-extracting-keywords-from-a-pdf)  
    5.6.1 [Extracting keywords from a PDF using TF-IDF](#561-extracting-keywords-from-a-pdf-using-tf-idf)  
      5.6.1.1 [Term Frequency](#5611-term-frequency)  
      5.6.1.2 [Inverse document frequency](#5612-inverse-document-frequency)  
      5.6.1.3 [Using TF-IDF in `borb`](#5613-using-tf-idf-in-borb)  
    5.6.2 [Extracting keywords from a PDF using  textrank](#562-extracting-keywords-from-a-pdf-using--textrank)  
  5.7 [Extracting color-information](#57-extracting-color-information)  
  5.8 [Extracting font-information](#58-extracting-font-information)  
    5.8.1 [Filtering by `font`](#581-filtering-by-font)  
    5.8.2 [Filtering by `font_color`](#582-filtering-by-font_color)  
  5.9 [Extracting images from a PDF](#59-extracting-images-from-a-pdf)  
    5.9.1 [Modifying images in an existing PDF](#591-modifying-images-in-an-existing-pdf)  
    5.9.2 [Subsampling images in an existing PDF](#592-subsampling-images-in-an-existing-pdf)  
  5.10 [Working with embedded files](#510-working-with-embedded-files)  
    5.10.1 [Embedding files in a PDF](#5101-embedding-files-in-a-pdf)  
    5.10.2 [Extracting embedded files from a PDF](#5102-extracting-embedded-files-from-a-pdf)  
  5.11 [Merging PDF documents](#511-merging-pdf-documents)  
  5.12 [Removing pages from  PDF documents](#512-removing-pages-from--pdf-documents)  
  5.13 [Rotating pages in PDF documents](#513-rotating-pages-in-pdf-documents)  
  5.14 [Conclusion](#514-conclusion)  
6 [Adding annotations to a PDF](#6-adding-annotations-to-a-pdf)  
  6.1 [Adding geometric shapes](#61-adding-geometric-shapes)  
  6.2 [Adding text annotations](#62-adding-text-annotations)  
  6.3 [Adding link annotations](#63-adding-link-annotations)  
  6.4 [Adding remote go-to annotations](#64-adding-remote-go-to-annotations)  
  6.5 [Adding rubber stamp annotations](#65-adding-rubber-stamp-annotations)  
  6.6 [Adding redaction (annotations)](#66-adding-redaction-annotations)  
    6.6.1 [Adding redaction annotations](#661-adding-redaction-annotations)  
    6.6.2 [Applying redaction annotations](#662-applying-redaction-annotations)  
  6.7 [Adding invisible `JavaScript` buttons](#67-adding-invisible-javascript-buttons)  
  6.8 [Adding sound annotations](#68-adding-sound-annotations)  
  6.9 [Conclusion](#69-conclusion)  
7 [Heuristics for PDF documents](#7-heuristics-for-pdf-documents)  
  7.1 [Extracting tables from a PDF](#71-extracting-tables-from-a-pdf)  
  7.2 [Performing OCR on a PDF](#72-performing-ocr-on-a-pdf)  
  7.3 [Exporting PDF as a (PIL) image](#73-exporting-pdf-as-a-pil-image)  
  7.4 [Exporting PDF as an SVG image](#74-exporting-pdf-as-an-svg-image)  
  7.5 [Exporting Markdown as PDF](#75-exporting-markdown-as-pdf)  
  7.6 [Exporting HTML as PDF](#76-exporting-html-as-pdf)  
  7.7 [Replacing text in an existing PDF](#77-replacing-text-in-an-existing-pdf)  
  7.8 [Conclusion](#78-conclusion)  
8 [Deep Dive into `borb`](#8-deep-dive-into-borb)  
  8.1 [About PDF](#81-about-pdf)  
  8.2 [The XREF table](#82-the-xref-table)  
    8.2.2 [Dealing with a broken XREF](#822-dealing-with-a-broken-xref)  
  8.3 [Page content streams](#83-page-content-streams)  
  8.4 [Postscript syntax](#84-postscript-syntax)  
  8.5 [Creating a `Document` using low-level syntax](#85-creating-a-document-using-low-level-syntax)  
  8.6 [Fonts in PDF](#86-fonts-in-pdf)  
    8.6.1 [Simple fonts](#861-simple-fonts)  
    8.6.2 [Composite fonts](#862-composite-fonts)  
  8.7 [About structured vs. unstructured document formats](#87-about-structured-vs-unstructured-document-formats)  
    8.7.1 [Text extraction: using heuristics to bridge the gap](#871-text-extraction-using-heuristics-to-bridge-the-gap)  
    8.7.2 [Paragraph extraction and disjoint set](#872-paragraph-extraction-and-disjoint-set)  
  8.8 [Hyphenation](#88-hyphenation)  
    5.8.1 [The hyphenation problem](#581-the-hyphenation-problem)  
    8.8.2 [A fast and scalable hyphenation algorithm](#882-a-fast-and-scalable-hyphenation-algorithm)  
    8.8.3 [Using hyphenation in `borb`](#883-using-hyphenation-in-borb)  
9 [Showcases](#9-showcases)  
  9.1 [Building a sudoku puzzle](#91-building-a-sudoku-puzzle)  
  9.2 [Building a realistic invoice](#92-building-a-realistic-invoice)  
  9.3 [Creating a stunning flyer](#93-creating-a-stunning-flyer)  
  9.4 [Creating a nonogram puzzle](#94-creating-a-nonogram-puzzle)  
  9.5 [Building a working calculator inside a PDF](#95-building-a-working-calculator-inside-a-pdf)  
  9.7 [Getting the raw bytes of a PDF](#97-getting-the-raw-bytes-of-a-pdf)  
  9.6 [Conclusion](#96-conclusion)  

<div style="page-break-before: always;"></div>

# 4 Forms

<div style="page-break-before: always;"></div>

## 4.1 Acroforms vs XFA

From wikipedia:

> XFA (also known as XFA forms) stands for XML Forms Architecture, a family of proprietary XML specifications that was suggested and developed by JetForm to enhance the processing of web forms.  
> It can be also used in PDF files starting with the PDF 1.5 specification. 
> The XFA specification is referenced as an external specification necessary for full application of the ISO 32000-1 specification (PDF 1.7). 
> The XML Forms Architecture was not standardized as an ISO standard, and has been deprecated in PDF 2.0.

## 4.2 The `FormField` object

From the PDF specification:

> An interactive form (PDF 1.2)—sometimes referred to as an AcroForm—is a collection of fields for gathering information interactively from the user. 
> A PDF document may contain any number of fields appearing on any combination of pages, all of which make up a single, global interactive form spanning the entire document.
> Arbitrary subsets of these fields can be imported or exported from the document; see 12.7.5, “Form Actions.”
>
> Each field in a document’s interactive form shall be defined by a field dictionary (see 12.7.3, “Field Dictionaries”). 
> For purposes of definition and naming, the fields can be organized hierarchically and can inherit attributes from their ancestors in the field hierarchy.
> 
> A field’s children in the hierarchy may also include widget annotations (see 12.5.6.19, “Widget Annotations”) that define its appearance on the page. 
> A field that has children that are fields is called a non-terminal field. 
> A field that does not have children that are fields is called a terminal field.

> Interactive forms (see 12.7, “Interactive Forms”) use widget annotations (PDF 1.2) to represent the appearance of fields and to manage user interactions. 
> As a convenience, when a field has only a single associated widget annotation, the contents of the field dictionary (12.7.3, “Field Dictionaries”) 
> and the annotation dictionary may be merged into a single dictionary containing entries that pertain to both a field and an annotation.

`borb` supports AcroForm technology in a way that is indistinguishable from other `LayoutElement` implementations. 
To the user, the technical side of forms (especially to the level of how the `Dictionary` objects are structured) is often not that important.

You can add a `FormField` object to a `Page` or `PageLayout` in the same way you'd add a `Paragraph` and everything will be taken care of.
`borb` will create the `Dictionary` objects, add them to the `Page`, perform all the calculations needed for layout, etc

## 4.3 Adding `FormField` objects to a PDF

`FormField` represents the common base implementation of form fields. 
It handles the logic that is common to `TextField`, `CheckBox`, `DropDownList` and other classes.

### 4.3.1 Adding a `TextField` to a PDF

In the next example you'll be using a `Table` in conjunction with `TextField` objects to build a very rudimentary form.

```python
#!chapter_004/src/snippet_001.py
from decimal import Decimal

from borb.pdf import TextField
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():
    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add FixedColumnWidthTable containing Paragraph and TextField objects
    layout.add(
        FixedColumnWidthTable(number_of_columns=2, number_of_rows=3)
        .add(Paragraph("Name:"))
        .add(TextField(field_name="name"))
        .add(Paragraph("Firstname:"))
        .add(TextField(field_name="firstname"))
        .add(Paragraph("Country"))
        .add(TextField(field_name="country"))
        .set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
        .no_borders()
    )

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

The output `Document` should look like this.
Notice the little warning ribbon atop the `Document` (which may appear differently depending on the PDF reader you are using).

![enter image description here](chapter_004/img/snippet_001_001.png)

Let's show the forms, and see what you've made:

![enter image description here](chapter_004/img/snippet_001_002.png)

We can of course fill in values in these textboxes:

![enter image description here](chapter_004/img/snippet_001_003.png)

And now, when we hide the forms again, the text becomes uneditable:

![enter image description here](chapter_004/img/snippet_001_004.png)

Your PDF reader may ask you whether you'd like to save the values in the form before closing the `Document`.

### 4.3.2 Customizing a `TextField` object

`TextField` accepts the same arguments as `Paragraph` when it comes to styling.
For instance, you can also set the `font_color`.

```python
#!chapter_004/src/snippet_002.py
from decimal import Decimal

from borb.pdf import HexColor
from borb.pdf import TextField
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add FixedColumnWidthTable containing Paragraph and TextField objects
    layout.add(
        FixedColumnWidthTable(number_of_columns=2, number_of_rows=3)
        .add(Paragraph("Name:"))
        .add(TextField(field_name="name", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Firstname:"))
        .add(TextField(field_name="firstname", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Country"))
        .add(TextField(field_name="country"))
        .set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
        .no_borders()
    )

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

This does not really have an impact on the form when it's editable:

![enter image description here](chapter_004/img/snippet_002_001.png)

But it does change the appearance of the form once it's uneditable:

![enter image description here](chapter_004/img/snippet_002_002.png)

### 4.3.3 Pre-filling a `TextField` object

You can of course pre-fill a `TextField`. This can be quite useful when you already know some of the values,
or when one particular answer occurs most of the time (it might save your reader some time if the most likely answer is pre-filled).

In the next example you'll be updating the code you wrote earlier to generate a simple form, and pre-fill some of its values;

```python
#!chapter_004/src/snippet_003.py
from decimal import Decimal

from borb.pdf import HexColor
from borb.pdf import TextField
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():
    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add FixedColumnWidthTable containing Paragraph and TextField objects
    layout.add(
        FixedColumnWidthTable(number_of_columns=2, number_of_rows=3)
        .add(Paragraph("Name:"))
        .add(TextField(field_name="name", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Firstname:"))
        .add(TextField(field_name="firstname", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Country"))
        # add TextField already pre-filled with 'Belgium'
        .add(TextField(field_name="country", value="Belgium"))
        .set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
        .no_borders()
    )

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_004/img/snippet_003.png)

### 4.3.4 Adding a `DropDownList` to a PDF

You've seen how to add a `TextField`, but what if you'd like to restrict the reader to only allow certain inputs.
This is typically where you could also use a `DropDownList`.
A `DropDownList` can be constructed with `typing.List[str]` and will allow the user to select one of the options.

```python
#!chapter_004/src/snippet_004.py
from decimal import Decimal

from borb.pdf import HexColor
from borb.pdf import DropDownList
from borb.pdf import TextField
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add FixedColumnWidthTable containing Paragraph and TextField objects
    layout.add(
        FixedColumnWidthTable(number_of_columns=2, number_of_rows=3)
        .add(Paragraph("Name:"))
        .add(TextField(field_name="name", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Firstname:"))
        .add(TextField(field_name="firstname", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Country"))
        .add(
            DropDownList(
                field_name="country",
                possible_values=["Belgium", "Canada", "Denmark", "Estonia"],
            )
        )
        .set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
        .no_borders()
    )

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_004/img/snippet_004.png)

### 4.3.5 Adding a `CountryDropDownList` to a PDF

It would be rather nonsensical to have every developer that uses `borb` code up the same `DropDownList` over and over again.
One of the key usecases of `DropDownList` is when you're using it to allow the user to select a country from a  list of all countries in the world.
`borb` comes to the resque with its `CountryDropDownList`, which comes pre-loaded with all the country-names.

```python
#!chapter_004/src/snippet_005.py
from decimal import Decimal

from borb.pdf import HexColor
from borb.pdf import CountryDropDownList
from borb.pdf import TextField
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add FixedColumnWidthTable containing Paragraph and TextField objects
    layout.add(
        FixedColumnWidthTable(number_of_columns=2, number_of_rows=3)
        .add(Paragraph("Name:"))
        .add(TextField(field_name="name", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Firstname:"))
        .add(TextField(field_name="firstname", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Country"))
        .add(CountryDropDownList(field_name="country"))
        .set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
        .no_borders()
    )

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_004/img/snippet_005.png)

### 4.3.6 Adding a `CheckBox` to a PDF

Let's extend our form to include a `CheckBox`.
We'll use this `CheckBox` to allow the user to answer a simple yes/no question.

```python
#!chapter_004/src/snippet_006.py
from decimal import Decimal

from borb.pdf import HexColor
from borb.pdf import CountryDropDownList
from borb.pdf import TextField
from borb.pdf import CheckBox
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import Alignment


def main():

    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add FixedColumnWidthTable containing Paragraph and TextField objects
    layout.add(
        FixedColumnWidthTable(number_of_columns=2, number_of_rows=4)
        .add(Paragraph("Name:"))
        .add(TextField(field_name="name", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Firstname:"))
        .add(TextField(field_name="firstname", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Country"))
        .add(CountryDropDownList(field_name="country"))
        .add(Paragraph("Do you want to receive promotional emails?"))
        .add(CheckBox())
        .set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
        .no_borders()
    )

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

The output PDF should look like this:

![enter image description here](chapter_004/img/snippet_006.png)

### 4.3.7 Adding a `RadioButton` to a PDF

:mega: TODO: currently not supported in `borb` :mega:

### 4.3.8 Adding a `PushButton` to a PDF

You can also add a `PushButton` to a PDF. 
These buttons can be configured (using their `\Action` dictionary) to interact with the PDF in predefined ways.
The default action (assuming you do not specify anything) is to reset the form (clearing all the input).

```python
#!chapter_004/src/snippet_007.py
from decimal import Decimal

from borb.pdf import HexColor
from borb.pdf import CountryDropDownList
from borb.pdf import TextField
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add FixedColumnWidthTable containing Paragraph and TextField objects
    layout.add(
        FixedColumnWidthTable(number_of_columns=2, number_of_rows=3)
        .add(Paragraph("Name:"))
        .add(TextField(field_name="name", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Firstname:"))
        .add(TextField(field_name="firstname", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Country"))
        .add(CountryDropDownList(field_name="country"))
        .set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
        .no_borders()
    )

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_004/img/snippet_007.png)

### 4.3.9 Adding a `JavaScriptPushButton` to a PDF

To have maximum configurability you can add a `JavaScriptPushButton` to a `Document`.
These buttons can be configured to have any (compliant) `JavaScript` script associated with them.
In this example you'll create a `Document` that shows an alert box whenever the `PushButton` gets pressed.

```python
#!chapter_004/src/snippet_008.py
from decimal import Decimal

from borb.pdf import HexColor
from borb.pdf import CountryDropDownList
from borb.pdf import TextField
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import JavaScriptPushButton
from borb.pdf import Alignment


def main():

    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add FixedColumnWidthTable containing Paragraph and TextField objects
    layout.add(
        FixedColumnWidthTable(number_of_columns=2, number_of_rows=4)
        .add(Paragraph("Name:"))
        .add(TextField(field_name="name", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Firstname:"))
        .add(TextField(field_name="firstname", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Country"))
        .add(CountryDropDownList(field_name="country"))
        .add(Paragraph(" "))
        .add(
            JavaScriptPushButton(
                text="Popup!",
                javascript="app.alert('Hello World!', 3)",
                horizontal_alignment=Alignment.RIGHT,
            )
        )
        .set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
        .no_borders()
    )

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_004/img/snippet_008_001.png)

When clicked, this shows a popup:

![enter image description here](chapter_004/img/snippet_008_002.jpg)

For more information on how to use `JavaScript` inside a PDF, I recommend the following resources:
- https://helpx.adobe.com/acrobat/using/applying-actions-scripts-pdfs.html
- https://acrobatusers.com/tutorials/
- https://acrobatusers.com/tutorials/popup_windows_part1/

## 4.4 Getting the value of a `FormField` in an existing PDF

In this section you'll learn how to retrieve the values that a user filled in from a PDF AcroForm.
You'll be using the PDF created earlier. 
Be sure to open it, fill in some values, and save it in order to get everything ready for this example.

We'll start by creating a PDF with a form in it:

```python
#!chapter_004/src/snippet_009.py
from decimal import Decimal

from borb.pdf import HexColor
from borb.pdf import CountryDropDownList
from borb.pdf import TextField
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add FixedColumnWidthTable containing Paragraph and TextField objects
    layout.add(
        FixedColumnWidthTable(number_of_columns=2, number_of_rows=3)
        .add(Paragraph("Name:"))
        .add(TextField(field_name="name", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Firstname:"))
        .add(TextField(field_name="firstname", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Country"))
        .add(CountryDropDownList(field_name="country"))
        .set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
        .no_borders()
    )

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_004/img/snippet_009.png)

Now we can either set the values in the form by opening the PDF and typing something (make sure to save the PDF when Adobe asks you to do so).
We could also just set the values using `borb` of course. You'll learn how to do that shortly.

Finally, with our form filled in (and saved), we can get the filled in values in the PDF:

```python
#!chapter_004/src/snippet_010.py
from decimal import Decimal

from borb.pdf import HexColor
from borb.pdf import PageLayout
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    # open document
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as pdf_file_handle:
        doc = PDF.loads(pdf_file_handle)
    assert doc is not None

    # get
    print("Name: %s" % doc.get_page(0).get_form_field_value("name"))
    print("Firstname: %s" % doc.get_page(0).get_form_field_value("firstname"))
    print("Country: %s" % doc.get_page(0).get_form_field_value("country"))


if __name__ == "__main__":
    main()
```

This should print something like:

![enter image description here](chapter_004/img/snippet_010.png)

```commandline
/usr/bin/python3.8 /home/joris/Code/borb-examples-dev/example/snippet_010.py
Name             : Schellekens
Firstname        : Joris
Country          : Belgium
```

of course, the exact values depend on what you filled in (either manually or programmatically).

## 4.5 Changing the value of a `FormField` in an existing PDF

This is another very common usecase.
You have designed a wonderful PDF, complete with `FormField` objects (perhaps in another PDF software suite),
and now you'd like to use your work as a template (so to speak) and generate hundreds of `Document` objects based on this one `Document` with a form.

I've seen this exact approach used in movie-theaters, where tickets needed to be produced containing seating and movie-information.
Or even for a famous circus-act.

In the next example you'll be using an existing PDF (the one you created earlier), and filling in its fields.
Later you'll learn how to remove interactivity by flattening the `Document`.

### 4.5.1 Changing the value of a `FormField` in an existing PDF using `borb`

```python
#!chapter_004/src/snippet_011.py
from decimal import Decimal

from borb.pdf import HexColor
from borb.pdf import PageLayout
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    # open document
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as pdf_file_handle:
        doc = PDF.loads(pdf_file_handle)
    assert doc is not None

    # set
    doc.get_page(0).set_form_field_value("name", "Schellekens")
    doc.get_page(0).set_form_field_value("firstname", "Joris")
    doc.get_page(0).set_form_field_value("country", "Belgium")

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_004/img/snippet_011.png)

### 4.5.2 Changing the value of a `FormField` in an existing PDF using `JavaScript`

We can also set the values of fields inside the PDF by using `JavaScript`.
This has the advantage of making the PDF really dynamic. You can have the user fill in their date of birth, and automatically calculate their age (and fill it in on a different `FormField`).
You could pre-fill address fields with `JavaScript`, for instance filling in somebody's town if you know their zipcode.

In the next example, you'll be creating a PDF with a simple `JavaScriptPushButton` that triggers a piece of `JavaScript` to set a `TextField`.

```python
#!chapter_004/src/snippet_012.py
from decimal import Decimal

from borb.pdf import HexColor
from borb.pdf import CountryDropDownList
from borb.pdf import TextField
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import JavaScriptPushButton
from borb.pdf import Alignment


def main():

    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add FixedColumnWidthTable containing Paragraph and TextField objects
    layout.add(
        FixedColumnWidthTable(number_of_columns=2, number_of_rows=4)
        .add(Paragraph("Name:"))
        .add(TextField(field_name="name", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Firstname:"))
        .add(TextField(field_name="firstname", font_color=HexColor("f1cd2e")))
        .add(Paragraph("Country"))
        .add(CountryDropDownList(field_name="country"))
        .add(Paragraph(" "))
        .add(
            JavaScriptPushButton(
                text="Set",
                javascript="this.getField('name').value = 'Schellekens';",
                horizontal_alignment=Alignment.RIGHT,
            )
        )
        .set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
        .no_borders()
    )

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

## 4.6 Conclusion

In this section you've learned how to build interactive, fillable PDF forms.

You've seen the various form `LayoutElement` objects `borb` has to offer and you've coded up a sample for each of them.

You've set the values of these fields using `Python` or by embedding `JavaScript` in the PDF itself.

Finally, you've learned how to extract the filled in values from a form inside a PDF.

<div style="page-break-before: always;"></div>

# 5 Working with existing PDFs

For some use-cases, you won't be creating the PDF's yourself. Imagine setting up a pipeline that automatically processes PDF invoices. Or even processing order forms.

Most of these workflows can be boiled down to some simple steps that can be handled with `borb`.

In this section you'll learn the ins and outs of working with existing PDF's.

<div style="page-break-before: always;"></div>

## 5.1 Extracting meta-information

Suppose you have a PDF document. Did you know it contains meta-information? Try it. Next time you have a PDF open in Adobe, press CTRL+D to open the document properties. You'll find things like:

- Author
- Producer
- Creation date
- Modification date
- Software that created the document
- Etc

It can be very useful to be able to extract these. Processing an invoice for instance might be more accurate if we know "supplier A uses software B to create their invoices, and python script C works best for that" versus "supplier X uses software Y, which is best handled by script Z".

### 5.1.1 Extracting the author from a PDF

In the next example you'll start by extracting the author from the PDF. 
This is of course assuming this property was set by whatever software created the PDF.

In order to be able to test these examples and get the same result as the book, I am providing a snippet of code here that will generate a very simple PDF;

```python
#!chapter_005/src/snippet_001.py
from borb.io.read.types import Name, String, Dictionary
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():
    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add a Paragraph
    layout.add(
        Paragraph(
            """
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                         """
        )
    )

    # set the /Info dictionary
    doc["XRef"]["Trailer"][Name("Info")] = Dictionary()

    # set the /Author
    doc["XRef"]["Trailer"]["Info"][Name("Author")] = String("Joris Schellekens")

    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

The PDF doesn't really look all that special when you open it.

![enter image description here](chapter_005/img/snippet_001_001.png)

But, when you open the properties (the exact shortcut differs depending on which PDF viewer you're using of course), you'll see the meta-data:

![enter image description here](chapter_005/img/snippet_001_002.png)

Now, let's assume you're getting this PDF (perhaps via email, or some automated process) and you'd like to extract the author from it.

`borb` allows you to do that in just a few lines of code:

```python
#!chapter_005/src/snippet_002.py
import typing
from borb.pdf import Document
from borb.pdf import PDF


def main():

    # read the Document
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle)

    # check whether we have read a Document
    assert doc is not None

    # print the \Author key from the \Info dictionary
    print("Author: %s" % doc.get_document_info().get_author())


if __name__ == "__main__":
    main()
```

This will print `Joris Schellekens` to the terminal (in the case of the demo-PDF created by the earlier example of course).

Keep in mind that this property (`/Author`) is not mandatory. 
So the code may simply return (and thus print) `None`. 
This is not a bug, it simply means the `/Author` property was not explicitly set.

### 5.1.2 Extracting the producer from a PDF

Similarly, you can extract other properties, like the producer. This is typically the name of the piece of software that created the PDF (or last modified the PDF).

This is important. The PDF specification is not always precise or clear-cut. 
Some PDF software might do things a little differently than others, thus causing potential incompatibility.

You can easily mitigate this by checking the producer property, and separating the problematic files.

```python
#!chapter_005/src/snippet_003.py
import typing
from borb.pdf import Document
from borb.pdf import PDF


def main():

    # read the Document
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle)

    # check whether we have read a Document
    assert doc is not None

    # print the \Producer key from the \Info dictionary
    print("Producer: %s" % doc.get_document_info().get_producer())


if __name__ == "__main__":
    main()
```

Of course, now that you know how to extract the author and the producer, 
you can check out the other methods of `DocumentInfo` and find out even more about any PDF that comes your way.

### 5.1.3 using XMP meta information

This is from `adobe.com`:

> Adobe’s Extensible Metadata Platform (XMP) is a file labeling technology that lets you embed metadata into files themselves during the content creation process. 
> With an XMP enabled application, your workgroup can capture meaningful information about a project (such as titles and descriptions, searchable keywords, and up-to-date author and copyright information) in a format that is easily understood by your team as well as by software applications, hardware devices, and even file formats. 
> Best of all, as team members modify files and assets, they can edit and update the metadata in real time during the workflow.>

This next example is similar to the earlier example involving `DocumentInfo`.
But in stead, we will use `XMPDocumentInfo`. This class offers even more methods to get information from a PDF `Document`.

Keep in mind that XMP is not a requirement for a PDF `Document` to be valid. 
So you may find these methods return `None` when you test them on a `Document` that does not have embedded XMP data.

```python
#!chapter_005/src/snippet_004.py
import typing
from borb.pdf import Document
from borb.pdf import PDF


def main():

    # read the Document
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle)

    # check whether we have read a Document
    assert doc is not None

    # print the ID using XMP meta info
    print("ID: %s" % doc.get_xmp_document_info().get_document_id())


if __name__ == "__main__":
    main()
```

For the document I tested, this printed:

```commandline
xmp.id:54e5adca-494c-4c10-983a-daa03cdae65a
```

<div style="page-break-before: always;"></div>

## 5.2 Extracting text from a PDF

Being able to extract text from a PDF is a fundamental skill. 
In the deep-dive, you'll learn more about PDF syntax, and why text-extraction is a non-trivial thing.

For now, you can start with an easy example where all visible text on the page is extracted.

This extraction process does not take into account any structure that may be present on the page itself. 
Hence the name `SimpleTextExtraction`.

You'll be using the same input PDF as earlier (containing a paragraph of lorem ipsum).

```python
#!chapter_005/src/snippet_005.py
import typing
from borb.pdf import Document
from borb.pdf import PDF
from borb.toolkit import SimpleTextExtraction


def main():

    # read the Document
    doc: typing.Optional[Document] = None
    l: SimpleTextExtraction = SimpleTextExtraction()
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle, [l])

    # check whether we have read a Document
    assert doc is not None

    # print the text on the first Page
    print(l.get_text()[0])


if __name__ == "__main__":
    main()
```

Here you've used the alternative method for `PDF.loads` which takes an array of `EventListener` objects as its argument.

`PDF.loads` will open the PDF, and start processing PDF syntax. 
Whenever it handles certain commands (rendering text, rendering images, switching to a new page, etc), 
it will send out `Event` objects. These can be handled by the appropriate `EventListener` implementation.

`SimpleTextExtraction` is one of those `EventListener` implementations that listens to:

- The start of a `Page`
- The end of a `Page`
- Begin rendering text mode
- Stop rendering text mode
- Render text command(s)

The code above should print out:

```
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint
occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est
laborum.
```

<div style="page-break-before: always;"></div>

## 5.3 Extracting text using regular expressions

This is a much more advanced way to extract text from a PDF. 
By using regular expressions, you can easily look for things like "total amount due" followed by some numbers. 
And, in doing so, effectively retrieve the useful data from an invoice.

In the next example you'll be doing exactly that. 
The code is very similar to what you've done earlier.

```python
#!chapter_005/src/snippet_006.py
import typing
from borb.pdf import Document
from borb.pdf import PDF
from borb.toolkit import RegularExpressionTextExtraction


def main():

    # read the Document
    # fmt: off
    doc: typing.Optional[Document] = None
    l: RegularExpressionTextExtraction = RegularExpressionTextExtraction("[lL]orem .* [dD]olor")
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle, [l])
    # fmt: on

    # check whether we have read a Document
    assert doc is not None

    # print matching groups
    for i, m in enumerate(l.get_matches()[0]):
        print("%d %s" % (i, m.group(0)))
        for r in m.get_bounding_boxes():
            print(
                "\t%f %f %f %f" % (r.get_x(), r.get_y(), r.get_width(), r.get_height())
            )


if __name__ == "__main__":
    main()
```

Like before, you constructed an implementation of `EventListener` and passed it to the `PDF.loads` method. 
`RegularExpressionTextExtraction` takes a regular expression as its single argument.

Once the `Document` has been parsed, you can retrieve all matches by specifying a `page_nr`. 
Pages are numbered from 0.

You'll get back a `typing.List[PDFMatch]` which is meant to behave like a `re.Match` object. 
Most of its fields and methods are written to work interchangeably with `re.Match`.

Of course, because a PDF has a dimensionality to it (content is located on an x/y plane), 
there are some extra methods. Such as `get_bounding_boxes()` which returns a `typing.List[Rectangle]'.

You may be wondering why a single match against a regular expression would return multiple bounding boxes. 
This happens when content is matched over multiple lines.

In this example however, the output should be:

```
0 Lorem ipsum dolor
	59.500000 740.916000 99.360000 11.100000
```

indicating a single match, with text "lorem ipsum dolor", 
with bounding box (lower left corner) at `[59.5, 740.916]` and a width of `99.36` and a height of `11.1`.

<div style="page-break-before: always;"></div>

## 5.4 Extracting text using its bounding box

Another extraction process relies on the rendering of the PDF itself. 
Perhaps the PDF's you are processing always have some kind of information at a precise location 
(e.g. an invoice number in the top right corner).

This implementation of `EventListener` allows you to filter events (i.e. rendering instructions) by providing `borb` with a bounding box.

In the next example you'll be using the coordinates from the previous example, to build a filter for `SimpleTextExtraction`.

```python
#!chapter_005/src/snippet_007.py
import typing
from decimal import Decimal

from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf import Document
from borb.pdf import PDF
from borb.toolkit import LocationFilter
from borb.toolkit import SimpleTextExtraction


def main():

    # define the Rectangle of interest
    r: Rectangle = Rectangle(Decimal(59), Decimal(740), Decimal(99), Decimal(11))

    # define SimpleTextExtraction
    l0: SimpleTextExtraction = SimpleTextExtraction()

    # apply a LocationFilter on top of SimpleTextExtraction
    l1: LocationFilter = LocationFilter(r)
    l1.add_listener(l0)

    # read the Document
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle, [l1])

    # check whether we have read a Document
    assert doc is not None

    # print the text inside the Rectangle of interest
    print(l0.get_text()[0])


if __name__ == "__main__":
    main()
```

This prints:

```commandline
Lorem ipsum dolor
```

<div style="page-break-before: always;"></div>

## 5.5 Combining regular expressions and bounding boxes

Of course, `borb` is designed to be a library, 
so the idea of being able to strap together your own tools using the toolkit is very important to me.

In the next example you'll be combining a regular expression expression extraction technique with a bounding box.

First you'll be looking for the precise location of the text "nisi ut aliquip". 
Once you have matched this regular expression, you also have its location on the page.

Then you can extend this box, 
knowing the text you'd really like to extract will be on the right of that piece of text.

```python
#!chapter_005/src/snippet_008.py
import typing
from decimal import Decimal

from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf import Document
from borb.pdf import PDF
from borb.toolkit import LocationFilter
from borb.toolkit import RegularExpressionTextExtraction
from borb.toolkit import PDFMatch
from borb.toolkit import SimpleTextExtraction


def main():

    # set up RegularExpressionTextExtraction
    # fmt: off
    l0: RegularExpressionTextExtraction = RegularExpressionTextExtraction("[nN]isi .* aliquip")
    # fmt: on

    # process Document
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle, [l0])
    assert doc is not None

    # find match
    m: typing.Optional[PDFMatch] = next(iter(l0.get_matches()[0]), None)
    assert m is not None

    # get page width
    w: Decimal = doc.get_page(0).get_page_info().get_width()

    # change rectangle to get more text
    r0: Rectangle = m.get_bounding_boxes()[0]
    r1: Rectangle = Rectangle(
        r0.get_x() + r0.get_width(), r0.get_y(), w - r0.get_x(), r0.get_height()
    )

    # process document (again) filtering by rectangle
    l1: LocationFilter = LocationFilter(r1)
    l2: SimpleTextExtraction = SimpleTextExtraction()
    l1.add_listener(l2)
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle, [l1])
    assert doc is not None

    # get text
    print(l2.get_text()[0])


if __name__ == "__main__":
    main()
```

This example is a lot to take in. 
Try it out, read through it carefully. 
It's important to understand these basic concepts in `borb` to really get the most out of it.

This example starts out similar to the earlier example ["Extracting text using regular expressions"](#33-extracting-text-using-regular-expressions), 
it uses the returned `PDFMatch` to determine the location of the text. 
With this location it processes the `Document` again, filtering a modified bounding box.

This example prints:

```commandline
ex ea commodo conse uat. Duis aute irure dolor in
```

This example might seem contrived, but there are definitely use-cases where this exact behavior comes in handy. 
Imagine processing a `Document`, looking for "amount due", 
and then modifying the bounding box to retrieve the amount and currency that is typically next to it.

The same strategy can be used to extract addresses from invoices, or anything similar really.

<div style="page-break-before: always;"></div>

## 5.6 Extracting keywords from a PDF

### 5.6.1 Extracting keywords from a PDF using TF-IDF

From wikipedia:

> In information retrieval, tf–idf, TF*IDF, or TFIDF, short for term frequency–inverse document frequency, is a numerical statistic that is intended to reflect how important a word is to a document in a collection or corpus. 
> It is often used as a weighting factor in searches of information retrieval, text mining, and user modeling. 
> The tf–idf value increases proportionally to the number of times a word appears in the document and is offset by the number of documents in the corpus that contain the word, which helps to adjust for the fact that some words appear more frequently in general. 
> tf–idf is one of the most popular term-weighting schemes today.

#### 5.6.1.1 Term Frequency

From wikipedia:

> Suppose we have a set of English text documents and wish to rank them by which document is more relevant to the query, "the brown cow". 
> A simple way to start out is by eliminating documents that do not contain all three words "the", "brown", and "cow", but this still leaves many documents. 
> To further distinguish them, we might count the number of times each term occurs in each document; the number of times a term occurs in a document is called its term frequency. 
> However, in the case where the length of documents varies greatly, adjustments are often made (see definition below). 

#### 5.6.1.2 Inverse document frequency

From wikipedia:

> Because the term "the" is so common, term frequency will tend to incorrectly emphasize documents which happen to use the word "the" more frequently, without giving enough weight to the more meaningful terms "brown" and "cow". 
> The term "the" is not a good keyword to distinguish relevant and non-relevant documents and terms, unlike the less-common words "brown" and "cow". Hence, an inverse document frequency factor is incorporated which diminishes the weight of terms that occur very frequently in the document set and increases the weight of terms that occur rarely.

#### 5.6.1.3 Using TF-IDF in `borb`

Let's start by creating a `Document` with a few `Paragraph` objects in it.
Since you'll be eliminating stop words (which are language-dependent), this `Document` needs to contain sensible English text.
You'll be creating a `Document` containing information about "Lorem Ipsum".

```python
#!chapter_005/src/snippet_009.py
from borb.io.read.types import Name, String, Dictionary
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():
    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add first Paragraph
    layout.add(Paragraph("What is Lorem Ipsum?", font="Helvetica-bold"))
    layout.add(
        Paragraph(
            """
    Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
    Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
    when an unknown printer took a galley of type and scrambled it to make a type specimen book. 
    It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. 
    It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, 
    and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
    """
        )
    )

    # add second Paragraph
    layout.add(Paragraph("Where does it come from?", font="Helvetica-bold"))
    layout.add(
        Paragraph(
            """
    Contrary to popular belief, Lorem Ipsum is not simply random text. 
    It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. 
    Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, 
    consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, 
    discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" 
    (The Extremes of Good and Evil) by Cicero, written in 45 BC. 
    This book is a treatise on the theory of ethics, very popular during the Renaissance. 
    The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.
    """
        )
    )

    # store
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

This should produce a `Document` like this:

Now you can unleash `TFIDFKeywordExtraction` on the `Document` you made;

```python
#!chapter_005/src/snippet_010.py
import typing

from borb.io.read.types import Name, String, Dictionary
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.toolkit import TFIDFKeywordExtraction
from borb.toolkit import ENGLISH_STOP_WORDS


def main():

    l: TFIDFKeywordExtraction = TFIDFKeywordExtraction(stopwords=ENGLISH_STOP_WORDS)

    # load
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle, [l])

    # check whether we have read a Document
    assert doc is not None

    print(l.get_keywords()[0])


if __name__ == "__main__":
    main()
```

This outputs:

```commandline
/usr/bin/python3.8 /home/joris/Code/borb-examples-dev/chapter_005/src/snippet_010.py
[('LOREM', 9.100909090909093e-06), 
 ('IPSUM', 9.100909090909093e-06), 
 ('TEXT', 2.737272727272727e-06), 
 ('LATIN', 2.737272727272727e-06)]

Process finished with exit code 0
```

### 5.6.2 Extracting keywords from a PDF using  textrank

TextRank is a graph-based ranking model for text processing which can be used in order to find the most relevant sentences in text and also to find keywords. 
The algorithm is explained in detail in the paper at https://web.eecs.umich.edu/~mihalcea/papers/mihalcea.emnlp04.pdf

```python
#!chapter_005/src/snippet_011.py
import typing

from borb.io.read.types import Name, String, Dictionary
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.toolkit import TextRankKeywordExtraction
from borb.toolkit import ENGLISH_STOP_WORDS


def main():

    l: TextRankKeywordExtraction = TextRankKeywordExtraction()

    # load
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle, [l])

    # check whether we have read a Document
    assert doc is not None

    print(l.get_keywords()[0])


if __name__ == "__main__":
    main()
```

This outputs:

```commandline
/usr/bin/python3.8 /home/joris/Code/borb-examples-dev/chapter_005/src/snippet_011.py 
[('LOREM', 0.12325162789434786), 
 ('IPSUM', 0.11962425634248006), 
 ('FROM', 0.039769960489979723), 
 ('LINE', 0.025411263503150646), 
 ('SIMPLY', 0.024239653360280115), 
 ('POPULAR', 0.021090820818629064), 
 ('LATIN', 0.02000870808599614), 
 ..
]
Process finished with exit code 0

```

**\* Keep in mind textrank is a non-deterministic algorithm. Its output may vary between runs.**

<div style="page-break-before: always;"></div>

## 5.7 Extracting color-information

This is perhaps a bit more of a tangent, but I can imagine it may be useful. 
In this particular example you'll be extracting color-information from a PDF.

Given the previous examples, you can easily adapt this technique to build a filter (similar to the location-based filter). 

By doing so, you unlock the possibility of processing a PDF by saying "look for text in the color red" or "look for text in the top right corner, in blue".

In this example, you'll be using `ColorSpectrumExtraction` to retrieve all the colors on the `Page`. This is a stepping stone to building bigger and better things. Although in and of itself this can already be useful to determine color-blindness compatibility of a given `Document`.

In the deep-dive, you'll learn the ins and outs of implementing your own `EventListener`.

To start this example, you'll be creating a PDF containing multiple colors. You'll be adding 3 `Paragraph` objects (red, green, blue) and one `Image`.

```python
#!chapter_005/src/snippet_012.py
from borb.io.read.types import Name, String, Dictionary
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import HexColor
from borb.pdf import Image

from decimal import Decimal


def main():
    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # the following code adds 3 paragraphs, each in a different color
    layout.add(Paragraph("Hello World!", font_color=HexColor("FF0000")))
    layout.add(Paragraph("Hello World!", font_color=HexColor("00FF00")))
    layout.add(Paragraph("Hello World!", font_color=HexColor("0000FF")))

    # the following code adds 1 image
    layout.add(
        Image(
            "https://images.unsplash.com/photo-1589606663923-283bbd309229?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8",
            width=Decimal(256),
            height=Decimal(256),
        )
    )

    # store
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_005/img/snippet_012.png)

This `Document` will serve as the input for the extraction example. 

Rather than printing the result of the extraction to the command-line, 
you'll create an output-pdf. I think it's a lot more visual to actually see the colors that were extracted, 
rather than having their RGB values printed out on the console.

```python
#!chapter_005/src/snippet_013.py
from decimal import Decimal

import typing
from borb.pdf import HexColor, RGBColor
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf import ConnectedShape
from borb.pdf import Alignment
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import FlexibleColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import LineArtFactory
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.toolkit import ColorExtraction


def main():

    doc: typing.Optional[Document] = None
    l: ColorExtraction = ColorExtraction()
    with open("output.pdf", "rb") as pdf_file_handle:
        doc = PDF.loads(pdf_file_handle, [l])

    # extract colors
    colors: typing.Dict[Color, Decimal] = l.get_color()[0]

    # create output Document
    doc_out: Document = Document()

    # add Page
    p: Page = Page()
    doc_out.add_page(p)

    # add PageLayout
    l: PageLayout = SingleColumnLayout(p)

    # add Paragraph
    l.add(Paragraph("These are the colors used in the input PDF:"))

    # add Table
    t: FlexibleColumnWidthTable = FlexibleColumnWidthTable(
        number_of_rows=3, number_of_columns=3, horizontal_alignment=Alignment.CENTERED
    )
    for c in colors.keys():
        t.add(
            ConnectedShape(
                LineArtFactory.droplet(
                    Rectangle(Decimal(0), Decimal(0), Decimal(32), Decimal(32))
                ),
                stroke_color=c,
                fill_color=c,
            )
        )
    t.set_padding_on_all_cells(Decimal(5), Decimal(5), Decimal(5), Decimal(5))
    t.no_borders()
    l.add(t)

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc_out)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_005/img/snippet_013.png)

<div style="page-break-before: always;"></div>

## 5.8 Extracting font-information

In this example you'll be extracting font-names from an existing PDF.
This may be useful (in later examples) to handle situations in which you know a certain snippet of information is always written in a particular font.

You'll start by creating a PDF with several fonts;

```python
#!chapter_005/src/snippet_014.py
from borb.pdf import UnorderedList
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():
    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add UnorderedList containing a (twice nested) UnorderedList
    for font_name in ["Helvetica", "Helvetica-Bold", "Courier"]:
        layout.add(Paragraph("Hello World from %s!" % font_name, font=font_name))

    # store
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_005/img/snippet_014.png)

And now you can process that PDF and retrieve the fonts;

```python
#!chapter_005/src/snippet_015.py
import typing
from borb.pdf import Document
from borb.pdf import PDF
from borb.toolkit import FontExtraction


def main():

    # read the Document
    doc: typing.Optional[Document] = None
    l: FontExtraction = FontExtraction()
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle, [l])

    # check whether we have read a Document
    assert doc is not None

    # print the names of the Fonts
    print(l.get_font_names()[0])


if __name__ == "__main__":
    main()
```

This prints:

```commandline
['Helvetica', 'Helvetica-Bold', 'Courier']
```

You can of course go looking at the code for `FontExtraction` (I highly encourage you to do so).
This should enable you to write your own filter (similar to `LocationFilter`) to filter on fonts.

### 5.8.1 Filtering by `font`

In this example you'll be using `FontNameFilter` to retrieve all text on a `Page` that was written in `Courier`.
First things first though, let's create an example PDF with text in different fonts;

```python
#!chapter_005/src/snippet_016.py
from borb.pdf import UnorderedList
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():
    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add UnorderedList containing a (twice nested) UnorderedList
    for font_name in ["Helvetica", "Helvetica-Bold", "Courier"]:
        layout.add(Paragraph("Hello World from %s!" % font_name, font=font_name))

    # store
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

This generates the following PDF:

![enter image description here](chapter_005/img/snippet_016.png)

Now we can run the code to filter on `font_name`:

```python
#!chapter_005/src/snippet_017.py
import typing
from borb.pdf import Document
from borb.pdf import PDF
from borb.toolkit import FontNameFilter
from borb.toolkit import SimpleTextExtraction


def main():

    # create FontNameFilter
    l0: FontNameFilter = FontNameFilter("Courier")

    # filtered text just gets passed to SimpleTextExtraction
    l1: SimpleTextExtraction = SimpleTextExtraction()
    l0.add_listener(l1)

    # read the Document
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle, [l0])

    # check whether we have read a Document
    assert doc is not None

    # print the names of the Fonts
    print(l1.get_text()[0])


if __name__ == "__main__":
    main()
```

This should print:

```commandline
Hello World, from Courier!
```

### 5.8.2 Filtering by `font_color`

Being able to filter by `font_color` allows you to extract text in a much more fine-grained way.
You could filter out only the red text from an invoice, 
or combine this particular filter with other filter implementations and do even crazier things.

This implementation of `EventListener` takes 2 arguments at construction:

- `color` : The `Color` you'd like to keep
- `maximum_normalized_rgb_distance` :   This is the maximum allowable distance between the `Color` in the PDF and the `color` parameter. This allows you to filter on "everything that looks kinda red" rather than "everything that is this exact shade of red".                                  
                                        The distance is defined as ((r0 - r1)² - (g0 - g1)² + (b0 - b1)²) / 3, with r, g, b being the red, green, blue components of the `Color`.

We're going to start by creating an input PDF with text in various colors.

```python
#!chapter_005/src/snippet_018.py
from borb.pdf import UnorderedList
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import X11Color


def main():
    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add UnorderedList containing a (twice nested) UnorderedList
    for color_name in ["Red", "Green", "Blue"]:
        layout.add(
            Paragraph(
                "Hello World from %s!" % color_name, font_color=X11Color(color_name)
            )
        )

    # store
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

This generates the following PDF:

![enter image description here](chapter_005/img/snippet_018.png)

Now we can filter the text in the PDF by selecting the red letters:

```python
#!chapter_005/src/snippet_019.py
import typing
from borb.pdf import Document
from borb.pdf import PDF
from borb.toolkit import FontColorFilter
from borb.toolkit import SimpleTextExtraction
from borb.pdf import X11Color

from decimal import Decimal


def main():

    # create FontColorFilter
    l0: FontColorFilter = FontColorFilter(X11Color("Red"), Decimal(0.01))

    # filtered text just gets passed to SimpleTextExtraction
    l1: SimpleTextExtraction = SimpleTextExtraction()
    l0.add_listener(l1)

    # read the Document
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle, [l0])

    # check whether we have read a Document
    assert doc is not None

    # print the names of the Fonts
    print(l1.get_text()[0])


if __name__ == "__main__":
    main()
```

This should print:

```commandline
Hello World, in Red!
```

<div style="page-break-before: always;"></div>

## 5.9 Extracting images from a PDF

In this example you'll be extracting images from an existing PDF.
Keep in mind the images may be subject to copyright, they may not have been intended for you to be able to extract them.

To get started, let's briefly re-iterate one of the earlier examples about inserting an `Image` object in a PDF.

```python
#!chapter_005/src/snippet_020.py
from borb.io.read.types import Name, String, Dictionary
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import Image

from decimal import Decimal


def main():
    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # define 3 Image URLs
    image_urls: typing.List[str] = [
        "https://images.unsplash.com/photo-1589606663923-283bbd309229?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8",
        "https://images.unsplash.com/photo-1496637721836-f46d116e6d34?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8",
        "https://images.unsplash.com/photo-1611873101970-dfa544c23494?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8",
    ]

    # add an Image for each URL
    for image_url in image_urls:
        layout.add(Image(image_url, width=Decimal(128), height=Decimal(128)))

    # store
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_005/img/snippet_020.png)

Now that you have an input `Document`, let's go ahead and extract the `Image` from it.

```python
#!chapter_005/src/snippet_021.py
import typing

from borb.io.read.types import Name, String, Dictionary
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.toolkit import ImageExtraction


def main():

    l: ImageExtraction = ImageExtraction()

    # load
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle, [l])

    # check whether we have read a Document
    assert doc is not None

    print(l.get_images()[0])


if __name__ == "__main__":
    main()
```

This should print:

```
<PIL.JpegImagePlugin.JpegImageFile image mode=RGB size=2000x3000 at 0x7F3BE45E5C40>
<PIL.JpegImagePlugin.JpegImageFile image mode=RGB size=4000x6000 at 0x7F3BE43FB760>
<PIL.JpegImagePlugin.JpegImageFile image mode=RGB size=2640x3300 at 0x7F3BE441B580>
```

What's interesting is that even though you inserted the `Image` objects and specified a particular size, the extracted `Image` is actually a lot larger. 
This is because PDF simply has its own way of dealing with resizing images. 
And there are use-cases where you might actually want this behavior. 

You could embed a tiny example of an `Image` in a `Document`, 
knowing the recipient can extract the full (much richer) `Image`.

Of course, if you're using this `Image` as a company logo, 
or part of the header/footer of the `Document`, 
you typically want the image to be as small as possible (while remaining legible).

In one of the upcoming examples you'll see how to subsample an `Image` in a PDF, 
and you'll see firsthand how this technique can help reduce your document's memory footprint.

### 5.9.1 Modifying images in an existing PDF

In this example you'll be modifying the images in a PDF.
You'll be using the PDF you created earlier (with 3 pineapple images) as a starting point.

First you'll be exploring the PDF, using the JSON-like structure `borb` has created.

```python
#!chapter_005/src/snippet_022.py
import typing

from borb.io.read.types import Name, String, Dictionary
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    # load
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle)

    # check whether we have read a Document
    assert doc is not None

    # print debug information for each Image (which PDF calls XObjects)
    for k, v in doc.get_page(0)["Resources"]["XObject"].items():
        print("%s\t%s" % (k, str(v)))


if __name__ == "__main__":
    main()
```

This code prints:

```
Im1	<PIL.JpegImagePlugin.JpegImageFile image mode=RGB size=2000x3000 at 0x7F74380D0490>
Im2	<PIL.JpegImagePlugin.JpegImageFile image mode=RGB size=4000x6000 at 0x7F7437F1B970>
Im3	<PIL.JpegImagePlugin.JpegImageFile image mode=RGB size=2640x3300 at 0x7F74367D56D0>
```

This example shows us that the PDF has stored the `Image` objects in the `Page` under `Resources\XObject\Im1` (and `Im2`, `Im3` respectively).

You can now modify these and store the `Document`.

First, you'll write this simple function to convert an `Image` to its sepia counterpart.
"sepia" is just a fancy way of saying "old timey brown pictures".

```python
#!chapter_005/src/snippet_023.py
import typing

from borb.io.read.types import Name, String, Dictionary
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF

from PIL import Image as PILImage


def modify_image(image: PILImage.Image):
    w = image.width
    h = image.height
    pixels = image.load()
    for i in range(0, w):
        for j in range(0, h):
            r, g, b = pixels[i, j]

            # convert to sepia
            new_r = r * 0.393 + g * 0.769 + b * 0.189
            new_g = r * 0.349 + g * 0.686 + b * 0.168
            new_b = r * 0.272 + g * 0.534 + b * 0.131

            # set
            pixels[i, j] = (int(new_r), int(new_g), int(new_b))


def main():

    # load
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle)

    # check whether we have read a Document
    assert doc is not None

    # modify each Image
    for k, v in doc.get_page(0)["Resources"]["XObject"].items():
        print("%s\t%s" % (k, str(v)))
        modify_image(v)

    # store PDF
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

The result should look like this:

![enter image description here](chapter_005/img/snippet_023.png)

### 5.9.2 Subsampling images in an existing PDF

As you've found out in a previous example, sometimes the dimensions at which an `Image` is displayed are not the same as the dimensions at which it was stored.
This can lead to a rather bulky PDF, if each `Image` is substantially larger than its display-dimensions.

In the next example, you'll be fixing that. 
Luckily `borb` comes with `ImageFormatOptimization` which does all the heavy lifting for you.

As a benchmark, you can first have a look at the file-characteristics of the original input PDF.

![enter image description here](chapter_005/img/snippet_024_001.png)

You can see the file is roughly 5Mb large.
Now you can use the following code to optimize the `Image` dimensions:

```python
#!chapter_005/src/snippet_024.py
import typing

from borb.io.read.types import Name, String, Dictionary
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.toolkit import ImageFormatOptimization


def main():

    # load
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as in_file_handle:
        doc = PDF.loads(in_file_handle, [ImageFormatOptimization()])

    # check whether we have read a Document
    assert doc is not None

    # store PDF
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

When you check out the file-stats on the output-file, the difference is astonishing:

![enter image description here](chapter_005/img/snippet_024_002.png)

You'll see that the output file looks the same, although there may have been some quality loss in the images.

![enter image description here](chapter_005/img/snippet_024_003.png)

<div style="page-break-before: always;"></div>

## 5.10 Working with embedded files

PDF is more than just a digital paper-replacement. 
PDF also has some features that go beyond "imitating paper".
For instance PDF allows you embed one or multiple files inside the document. 
By doing so, you can provide extra resources for whoever reads the document.

In one particular use-case, a german invoicing standard (ZUGFeRD) requires the creator of the invoice to embed an XML representation of the invoice, 
to ensure the document can be processed automatically.

In this section you'll handle both extraction of embedded files, and appending embedded files to a `Document`.

### 5.10.1 Embedding files in a PDF

In this example, you'll be creating a `Document` containing one `Paragraph`, and embed a json-file.

```python
#!chapter_005/src/snippet_025.py
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    # create empty Document
    d: Document = Document()

    # add Page
    p: Page = Page()
    d.add_page(p)

    # create PageLayout
    l: PageLayout = SingleColumnLayout(p)

    # add Paragraph
    l.add(
        Paragraph(
            """
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                    Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                    Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.    
                    """
        )
    )

    # create bytes for embedded file
    file_bytes = b"""
    {
        "lorem": "ipsum",
        "dolor": "sit"
    }
    """

    # add embedded file
    d.add_embedded_file("lorem_ipsum.json", file_bytes)

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, d)


if __name__ == "__main__":
    main()
```

The PDF should look something like this: 

![enter image description here](chapter_005/img/snippet_025_001.png)

Notice the warning you see atop the PDF viewer. 
This may of course vary depending on the viewer you're using.
If you open the embedded file pane (again depending on your editor) you may see something similar to this:

![enter image description here](chapter_005/img/snippet_025_002.png)

### 5.10.2 Extracting embedded files from a PDF

Now that you can embed files in a PDF, let's see how you can retrieve those files again.

```python
#!chapter_005/src/snippet_026.py
import typing
from borb.pdf import Document
from borb.pdf import PDF


def main():

    # read the Document
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as pdf_file_handle:
        doc = PDF.loads(pdf_file_handle)

    # check whether we have read a Document
    assert doc is not None

    # retrieve all embedded files and their bytes
    for k, v in doc.get_embedded_files().items():

        # display the file name, and the size
        print("%s, %d bytes" % (k, len(v)))


if __name__ == "__main__":
    main()
```

This should print:

```
lorem_ipsum.json, 66 bytes
```

Of course, rather than just displaying the byte-count you could also write the bytes to a file again.
Or process them directly using the `io` API in Python.

<div style="page-break-before: always;"></div>

## 5.11 Merging PDF documents

This is one of the most common usecases in working with PDF.
In the next example you'll be merging multiple existing PDF documents.

You'll start by creating two methods that each create (and write) a PDF document.

```python
#!chapter_005/src/snippet_027.py
import typing
from borb.pdf import Document
from borb.pdf import PDF

import typing

from borb.pdf import HexColor
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    d: Document = Document()
    p: Page = Page()
    d.add_page(p)

    l: PageLayout = SingleColumnLayout(p)
    l.add(
        Paragraph(
            """
                    Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
                    Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
                    when an unknown printer took a galley of type and scrambled it to make a type specimen book. 
                    It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. 
                    It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, 
                    and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
                    """,
            font_color=HexColor("de6449"),
        )
    )

    with open("output_001.pdf", "wb") as pdf_out_handle:
        PDF.dumps(pdf_out_handle, d)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_005/img/snippet_027.png)

That should take care of the first PDF.
Now you can write a second (similar) PDF document:

```python
#!chapter_005/src/snippet_028.py
import typing
from borb.pdf import Document
from borb.pdf import PDF

import typing

from borb.pdf import HexColor
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    d: Document = Document()
    p: Page = Page()
    d.add_page(p)

    l: PageLayout = SingleColumnLayout(p)
    l.add(
        Paragraph(
            """
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                    Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                    Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                    """,
            font_color=HexColor("f1cd2e"),
        )
    )

    with open("output_002.pdf", "wb") as pdf_out_handle:
        PDF.dumps(pdf_out_handle, d)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_005/img/snippet_028.png)

Finally, you can write the main method, which will create both documents, read them, and merge them.

```python
#!chapter_005/src/snippet_029.py
import typing
from borb.pdf import Document
from borb.pdf import PDF

import typing

from borb.pdf import HexColor
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    # open doc_001
    doc_001: typing.Optional[Document] = Document()
    with open("output_001.pdf", "rb") as pdf_file_handle:
        doc_001 = PDF.loads(pdf_file_handle)

    # open doc_002
    doc_002: typing.Optional[Document] = Document()
    with open("output_002.pdf", "rb") as pdf_file_handle:
        doc_002 = PDF.loads(pdf_file_handle)

    # merge
    doc_001.add_document(doc_002)

    # write
    with open("output_003.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc_001)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_005/img/snippet_029.png)

You don't have to fully merge both `Document` objects, you can just copy a couple of `Page` objects from one `Document` to another.     
In the next example you'll be selecting one `Page` from each `Document` and building a new PDF with them.

You'll start by creating a slightly modified version of the first document from the previous example.
This document has 10 pages.

```python
#!chapter_005/src/snippet_030.py
import typing
from borb.pdf import Document
from borb.pdf import PDF

from decimal import Decimal
import typing

from borb.pdf import HexColor
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    d: Document = Document()

    N: int = 10
    for i in range(0, N):
        p: Page = Page()
        d.add_page(p)
        l: PageLayout = SingleColumnLayout(p)
        l.add(
            Paragraph(
                "Page %d of %d" % (i + 1, N),
                font_color=HexColor("0b3954"),
                font_size=Decimal(24),
            )
        )
        l.add(
            Paragraph(
                """
                        Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
                        Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
                        when an unknown printer took a galley of type and scrambled it to make a type specimen book. 
                        It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. 
                        It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, 
                        and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
                        """,
                font_color=HexColor("de6449"),
            )
        )

    with open("output_001.pdf", "wb") as pdf_out_handle:
        PDF.dumps(pdf_out_handle, d)


if __name__ == "__main__":
    main()
```

The page number is printed atop each page, to make it easier to identify them later.

![enter image description here](chapter_005/img/snippet_030.png)

The second document will also have 10 pages. The page number will also be displayed atop each page:

```python
#!chapter_005/src/snippet_031.py
import typing
from borb.pdf import Document
from borb.pdf import PDF

from decimal import Decimal
import typing

from borb.pdf import HexColor
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    d: Document = Document()

    N: int = 10
    for i in range(0, N):
        p: Page = Page()
        d.add_page(p)
        l: PageLayout = SingleColumnLayout(p)
        l.add(
            Paragraph(
                "Page %d of %d" % (i + 1, N),
                font_color=HexColor("56cbf9"),
                font_size=Decimal(24),
            )
        )
        l.add(
            Paragraph(
                """
                        Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
                        Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
                        when an unknown printer took a galley of type and scrambled it to make a type specimen book. 
                        It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. 
                        It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, 
                        and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
                        """,
                font_color=HexColor("f1cd2e"),
            )
        )

    with open("output_002.pdf", "wb") as pdf_out_handle:
        PDF.dumps(pdf_out_handle, d)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_005/img/snippet_031.png)

To build the merged document you'll be selecting a page from each input document in turn, until the merged document has 10 pages.

```python
#!chapter_005/src/snippet_032.py
import typing
from borb.pdf import Document
from borb.pdf import PDF

import typing
from decimal import Decimal

from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    # open doc_001
    doc_001: typing.Optional[Document] = Document()
    with open("output_001.pdf", "rb") as pdf_file_handle:
        doc_001 = PDF.loads(pdf_file_handle)

    # open doc_002
    doc_002: typing.Optional[Document] = Document()
    with open("output_002.pdf", "rb") as pdf_file_handle:
        doc_002 = PDF.loads(pdf_file_handle)

    # create new document
    d: Document = Document()
    for i in range(0, 10):
        p: typing.Optional[Page] = None
        if i % 2 == 0:
            p = doc_001.get_page(i)
        else:
            p = doc_002.get_page(i)
        d.add_page(p)

    # write
    with open("output_003.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, d)


if __name__ == "__main__":
    main()
```

The final document alternates pages between both input documents (which is obvious from the color and page numbers).

![enter image description here](chapter_005/img/snippet_032.png)

<div style="page-break-before: always;"></div>

## 5.12 Removing pages from  PDF documents

Sometimes you may want to remove a `Page` from a PDF.
e.g. removing a cover-page before text-extraction may speed things up (one less page to process)

In the next example you'll be removing the first `Page` from a `Document`.
First of course, we need to create a `Document` to start with;

```python
#!chapter_005/src/snippet_033.py
import typing
from borb.pdf import Document
from borb.pdf import PDF

import typing
from decimal import Decimal

from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import MultiColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import HexColor


def main():

    # create new document
    d: Document = Document()

    # add Page
    p: Page = Page()
    d.add_page(p)
    page_number: int = 1

    # create PageLayout
    l: PageLayout = MultiColumnLayout(p)

    # adding Pages
    for _ in range(0, 20):
        if l.get_page() != p or page_number == 1:
            l.add(
                Paragraph(
                    "Page %d" % page_number,
                    font_color=HexColor("f1cd2e"),
                    font_size=Decimal(20),
                    font="Courier-Bold",
                )
            )
            p = l.get_page()
            page_number += 1

        l.add(
            Paragraph(
                """
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                        """
            )
        )

    # write
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, d)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_005/img/snippet_033.png)

Now that we have a substantial `Document`, we can remove a `Page` from it;

```python
#!chapter_005/src/snippet_034.py
import typing
from borb.pdf import Document
from borb.pdf import PDF

import typing
from decimal import Decimal

from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import MultiColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import HexColor


def main():

    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as pdf_file_handle:
        doc = PDF.loads(pdf_file_handle)

    assert doc is not None

    # remove Page
    doc.pop_page(1)

    # store Document
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_005/img/snippet_034.png)

You can see (in the thumbnail panel on the left side) that the second page was removed.

<div style="page-break-before: always;"></div>

## 5.13 Rotating pages in PDF documents

In this example you'll be rotating a `Page` 90 degrees clockwise. 
You can rotate a `Page` any multiple of 90 degrees.

```python
#!chapter_005/src/snippet_035.py
import typing
from borb.pdf import Document
from borb.pdf import PDF

import typing
from decimal import Decimal

from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import MultiColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import HexColor


def main():

    # create new document
    d: Document = Document()

    # add Page
    p: Page = Page()
    d.add_page(p)
    page_number: int = 1

    # create PageLayout
    l: PageLayout = MultiColumnLayout(p)

    # adding Pages
    for _ in range(0, 20):
        if l.get_page() != p or page_number == 1:
            l.add(
                Paragraph(
                    "Page %d" % page_number,
                    font_color=HexColor("f1cd2e"),
                    font_size=Decimal(20),
                    font="Courier-Bold",
                )
            )
            p = l.get_page()
            page_number += 1

        l.add(
            Paragraph(
                """
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                        """
            )
        )

    # write
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, d)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_005/img/snippet_035.png)

You already know this PDF, it's the same from the previous examples.

Now let's rotate a `Page`:

```python
#!chapter_005/src/snippet_036.py
import typing
from borb.pdf import Document
from borb.pdf import PDF

import typing
from decimal import Decimal

from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import MultiColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import HexColor


def main():

    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as pdf_file_handle:
        doc = PDF.loads(pdf_file_handle)

    assert doc is not None

    # rotate Page
    doc.get_page(0).rotate_right()

    # store Document
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_005/img/snippet_036.png)

<div style="page-break-before: always;"></div>

## 5.14 Conclusion

In this section you've learned the basics of working with existing PDF documents. 
You've seen how to extract text, regular expressions, images, font-information and color-information.

And you've seen the basics of merging PDF's and removing one or more pages from a PDF.

This section, together with the previous wraps up the basics of what you can do with `borb`.

I would encourage you to continue reading, and more importantly to continue exploring `borb`.
There are many more options and algorithms that you may find useful. 
As a developer, expanding your toolkit with more knowledge is never a bad thing.

<div style="page-break-before: always;"></div>

# 6 Adding annotations to a PDF

from the PDF-spec:

> An annotation associates an object such as a note, sound, or movie with a location on a page of a PDF
> document, or provides a way to interact with the user by means of the mouse and keyboard. PDF includes a
> wide variety of standard annotation types, described in detail in 12.5.6, “Annotation Types.”

<div style="page-break-before: always;"></div>

## 6.1 Adding geometric shapes

For this example, you'll be adding a cartoon-ish diamond shape to a PDF.
You can do this with a PDF that was just created, or with an existing PDF.
`borb` comes with a rich `LineArtFactory` enabling you to easily add a shape to your PDF without having to resort to pixel-geometry.

```python
#!chapter_006/src/snippet_001.py
from decimal import Decimal

from borb.pdf.canvas.layout.annotation.polygon_annotion import PolygonAnnotation
from borb.pdf import HexColor
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf.canvas.line_art.line_art_factory import LineArtFactory
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf.page.page_size import PageSize
from borb.pdf import PDF


def main():

    doc: Document = Document()
    page: Page = Page()
    doc.add_page(page)

    layout: PageLayout = SingleColumnLayout(page)
    layout.add(
        Paragraph(
            """
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                        """
        )
    )

    page_width: Decimal = PageSize.A4_PORTRAIT.value[0]
    page_height: Decimal = PageSize.A4_PORTRAIT.value[1]
    s: Decimal = Decimal(100)
    page.add_annotation(
        PolygonAnnotation(
            LineArtFactory.cartoon_diamond(
                Rectangle(
                    page_width / Decimal(2) - s / Decimal(2),
                    page_height / Decimal(2) - s / Decimal(2),
                    s,
                    s,
                )
            ),
            stroke_color=HexColor("f1cd2e"),
        )
    )

    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_006/img/snippet_001.png)

You may be wondering why `borb` did not make it easier on you to add the annotation.
I mean to say, you had to calculate the coordinates yourself, that's unusually unhelpful.

The key thing to take away from this example (and in fact all subsequent examples in this section) is that annotations are typically added **after** the `Document` has been generated.

So `borb` does not offer much convenience methods, because it assumes the precise layout of the `Page` will have already been baked in to the `Document` at which point it is too late to attempt to retrieve it.

## 6.2 Adding text annotations

In this example you'll be creating a text-annotation. 
This is comparable to adding a pop-up Post-it note to a PDF.

```python
#!chapter_006/src/snippet_002.py
from decimal import Decimal

from borb.pdf.canvas.layout.annotation.text_annotation import (
    TextAnnotation,
    TextAnnotationIconType,
)
from borb.pdf import HexColor
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf.page.page_size import PageSize
from borb.pdf import PDF


def main():

    doc: Document = Document()
    page: Page = Page()
    doc.add_page(page)

    layout: PageLayout = SingleColumnLayout(page)
    layout.add(
        Paragraph(
            """
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                        """
        )
    )

    page_width: Decimal = PageSize.A4_PORTRAIT.value[0]
    page_height: Decimal = PageSize.A4_PORTRAIT.value[1]
    s: Decimal = Decimal(100)
    page.add_annotation(
        TextAnnotation(
            Rectangle(
                page_width / Decimal(2) - s / Decimal(2),
                page_height / Decimal(2) - s / Decimal(2),
                s,
                s,
            ),
            contents="Hello World!",
            text_annotation_icon=TextAnnotationIconType.COMMENT,
            color=HexColor("f1cd2e"),
        )
    )

    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

You can customize quite a few aspects of this particular annotation:

- The text
- The location at which the icon is displayed
- The icon being displayed (you have the option to select one from a range of pre-defined icons)
- The color of the icon (and the resulting pop-up box)

The PDF you created should end up looking like this:

![enter image description here](chapter_006/img/snippet_002_001.png)

And when you click on the icon in the middle of the page, you get a little pop-up:

![enter image description here](chapter_006/img/snippet_002_002.png)

## 6.3 Adding link annotations

Link annotations provide your readers with an easy way to navigate the PDF document.
Clicking a link-annotation can:

- Take the reader to a predefined page (or piece of a page)
- Set the zoom level at which the page is being displayed
- Set the crop box of the PDF reader

In the next example, you'll create a `Document` with several pages, 
and provide each of them with a convenient "back to the beginning" link annotation.

```python
#!chapter_006/src/snippet_003.py
from decimal import Decimal

from borb.pdf.canvas.layout.annotation.link_annotation import (
    LinkAnnotation,
    DestinationType,
)
from borb.pdf import HexColor
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf.page.page_size import PageSize
from borb.pdf import PDF


def main():

    doc: Document = Document()

    # add 10 pages
    N: int = 10
    for i in range(0, N):
        page: Page = Page()
        doc.add_page(page)

        layout: PageLayout = SingleColumnLayout(page)

        layout.add(
            Paragraph(
                "page %d of %d" % (i + 1, N),
                font_color=HexColor("f1cd2e"),
                font_size=Decimal(20),
                font="Helvetica-Bold",
            )
        )

        layout.add(
            Paragraph(
                """
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                        """
            )
        )

        page_width: Decimal = PageSize.A4_PORTRAIT.value[0]
        page_height: Decimal = PageSize.A4_PORTRAIT.value[1]
        s: Decimal = Decimal(100)
        page.add_annotation(
            LinkAnnotation(
                Rectangle(
                    page_width / Decimal(2) - s / Decimal(2),
                    page_height / Decimal(2) - s / Decimal(2),
                    s,
                    s,
                ),
                page=Decimal(0),
                destination_type=DestinationType.FIT,
            )
        )

    # store
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_006/img/snippet_003.png)

Try it! Navigate to any `Page` of the `Document` and click the link-annotation. 
It should send you straight back to the first `Page`.

You used `DestinationType.FIT` in this example, which forces the viewer software to go to a given page (0 in this case),
and ensure the zoom-level is set to fit this page in the viewer. This is the option that requires the least amount of parameters.
You can  also set other `DestinationType` values, for instance to force the viewer to go to a particular y-coordinate of a given page, etc.

- `DestinationType.FIT` : Display the page designated by page, with its contents magnified just
enough to fit the entire page within the window both horizontally and
vertically. If the required horizontal and vertical magnification factors
are different, use the smaller of the two, centering the page within the
window in the other dimension.

- `DestinationType.FIT_B` : (PDF 1.1) Display the page designated by page, with its contents
magnified just enough to fit its bounding box entirely within the window
both horizontally and vertically. If the required horizontal and vertical
magnification factors are different, use the smaller of the two,
centering the bounding box within the window in the other dimension.

- `DestinationType.FIT_B_H` : (PDF 1.1) Display the page designated by page, with the vertical
coordinate top positioned at the top edge of the window and the
contents of the page magnified just enough to fit the entire width of its
bounding box within the window. A null value for top specifies that the
current value of that parameter shall be retained unchanged.

- `DestinationType.FIT_B_V` : (PDF 1.1) Display the page designated by page, with the horizontal
coordinate left positioned at the left edge of the window and the
contents of the page magnified just enough to fit the entire height of its
bounding box within the window. A null value for left specifies that the
current value of that parameter shall be retained unchanged.

- `DestinationType.FIT_H` : Display the page designated by page, with the vertical coordinate top
positioned at the top edge of the window and the contents of the page
magnified just enough to fit the entire width of the page within the
window. A null value for top specifies that the current value of that
parameter shall be retained unchanged.

- `DestinationType.FIT_R` : Display the page designated by page, with its contents magnified just
enough to fit the rectangle specified by the coordinates left, bottom,
right, and top entirely within the window both horizontally and vertically.
If the required horizontal and vertical magnification factors are
different, use the smaller of the two, centering the rectangle within the
window in the other dimension.

- `DestinationType.FIT_V` : Display the page designated by page, with the horizontal coordinate
left positioned at the left edge of the window and the contents of the
page magnified just enough to fit the entire height of the page within
the window. A null value for left specifies that the current value of that
parameter shall be retained unchanged.

- `DestinationType.X_Y_Z` : Display the page designated by page, with the coordinates (left, top)
positioned at the upper-left corner of the window and the contents of
the page magnified by the factor zoom. A null value for any of the
parameters left, top, or zoom specifies that the current value of that
parameter shall be retained unchanged. A zoom value of 0 has the
same meaning as a null value.

This example is very minimalistic. You can expand upon it.
Rather than using a simple square, you can draw an `Image` or `Paragraph` and have the annotation be on top of it.
I'm just giving you the basic tools you need, what you do with them is limited only by your imagination.

## 6.4 Adding remote go-to annotations

A remote go-to annotation allows you to make an area of your PDF clickable and functions like a hyperlink when clicked.
This can be particularly useful if your PDF is part of a document-process where you might want to link this document to its source-system, or other documents.

```python
#!chapter_006/src/snippet_004.py
from decimal import Decimal

from borb.pdf.canvas.layout.annotation.remote_go_to_annotation import (
    RemoteGoToAnnotation,
)
from borb.pdf import HexColor
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf.page.page_size import PageSize
from borb.pdf import PDF


def main():

    doc: Document = Document()

    page: Page = Page()
    doc.add_page(page)

    layout: PageLayout = SingleColumnLayout(page)
    layout.add(
        Paragraph(
            """
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                        """
        )
    )

    page_width: Decimal = PageSize.A4_PORTRAIT.value[0]
    page_height: Decimal = PageSize.A4_PORTRAIT.value[1]
    s: Decimal = Decimal(100)
    page.add_annotation(
        RemoteGoToAnnotation(
            Rectangle(
                page_width / Decimal(2) - s / Decimal(2),
                page_height / Decimal(2) - s / Decimal(2),
                s,
                s,
            ),
            uri="https://www.google.com",
        ),
    )

    # store
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_006/img/snippet_004.png)

## 6.5 Adding rubber stamp annotations

Rubber stamp annotations bring a bit of that classic paper feeling to digital documents.
A giant "Confidential" on a page just screams "classy".

In the next example, you'll be adding a rubber stamp annotation to a simple "lorem ipsum" document.

```python
#!chapter_006/src/snippet_005.py
from decimal import Decimal

from borb.pdf.canvas.layout.annotation.rubber_stamp_annotation import (
    RubberStampAnnotation,
    RubberStampAnnotationIconType,
)
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf.page.page_size import PageSize
from borb.pdf import PDF


def main():

    doc: Document = Document()

    page: Page = Page()
    doc.add_page(page)

    layout: PageLayout = SingleColumnLayout(page)

    layout.add(
        Paragraph(
            """
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                        """
        )
    )

    page_width: Decimal = PageSize.A4_PORTRAIT.value[0]
    page_height: Decimal = PageSize.A4_PORTRAIT.value[1]
    s: Decimal = Decimal(100)
    page.add_annotation(
        RubberStampAnnotation(
            Rectangle(
                page_width / Decimal(2) - s / Decimal(2),
                page_height / Decimal(2) - s / Decimal(2),
                s,
                s,
            ),
            name=RubberStampAnnotationIconType.CONFIDENTIAL,
        )
    )

    # store
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_006/img/snippet_005.png)

The different types of rubber stamps are limited (the PDF spec only defines a handful of them);

- `RubberStampAnnotationIconType.APPROVED`
- `RubberStampAnnotationIconType.AS_IS`
- `RubberStampAnnotationIconType.CONFIDENTIAL`
- `RubberStampAnnotationIconType.DRAFT`
- `RubberStampAnnotationIconType.EXPERIMENTAL`
- `RubberStampAnnotationIconType.EXPIRED`
- `RubberStampAnnotationIconType.FINAL`
- `RubberStampAnnotationIconType.FOR_COMMENT`
- `RubberStampAnnotationIconType.FOR_PUBLIC_RELEASE`
- `RubberStampAnnotationIconType.NOT_APPROVED`
- `RubberStampAnnotationIconType.NOT_FOR_PUBLIC_RELEASE`
- `RubberStampAnnotationIconType.SOLD`
- `RubberStampAnnotationIconType.TOP_SECRET`

And the rendering of the stamp is entirely up to the reader software. 
So this example may look entirely different on your device.

<div style="page-break-before: always;"></div>

## 6.6 Adding redaction (annotations)

from the PDF spec:
> A redaction annotation (PDF 1.7) identifies content that is intended to be removed from the document. The
> intent of redaction annotations is to enable the following process:
>
> a) Content identification. A user applies redact annotations that specify the pieces or regions of content that
> should be removed. Up until the next step is performed, the user can see, move and redefine these
> annotations.
>
> b) Content removal. The user instructs the viewer application to apply the redact annotations, after which the
> content in the area specified by the redact annotations is removed. In the removed content’s place, some
> marking appears to indicate the area has been redacted. Also, the redact annotations are removed from
> the PDF document.
>
> Redaction annotations provide a mechanism for the first step in the redaction process (content identification).
> This allows content to be marked for redaction in a non-destructive way, thus enabling a review process for
> evaluating potential redactions prior to removing the specified content.
> Redaction annotations shall provide enough information to be used in the second phase of the redaction
> process (content removal). This phase is application-specific and requires the conforming reader to remove all
> content identified by the redaction annotation, as well as the annotation itself.

### 6.6.1 Adding redaction annotations

In the next example, you'll be adding a redaction annotation. In a subsequent example you'll be using `borb` to apply all redaction annotations (thus removing the content).
Redaction annotations are simply another kind of annotation, so all the methods and tools you've seen so far can of course be used again.

```python
#!chapter_006/src/snippet_006.py
from decimal import Decimal

from borb.pdf.canvas.layout.annotation.redact_annotation import RedactAnnotation
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    doc: Document = Document()

    page: Page = Page()
    doc.add_page(page)

    layout: PageLayout = SingleColumnLayout(page)

    layout.add(
        Paragraph(
            """
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                        """
        )
    )

    page.add_annotation(
        RedactAnnotation(
            Rectangle(Decimal(405), Decimal(721), Decimal(40), Decimal(8)).grow(
                Decimal(2)
            )
        )
    )

    # store
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_006/img/snippet_006.png)

Of course, rather than passing a `Rectangle`, you can also use some of the logic you've applied in previous examples. 
For instance, you can use `RegularExpressionTextExtraction` to look for a regular expression and then redact it.
This is particularly useful if you're trying to remove structured information such as:

- A bank account number
- A social security number
- A phone number
- An email address
- Etc

`borb` comes with a small library of useful (common) regular expressions.
These can be found in `CommonRegularExpression`;

- `BITCOIN_ADDRESS`
- `CREDIT_CARD`
- `DATE`
- `DOLLAR_PRICE`
- `EMAIL`
- `HEX_COLOR`
- `IPV4`
- `IPV6`
- `PHONE`
- `PHONE_WITH_EXTENSION`
- `PO_BOX`
- `ROMAN_NUMERAL`
- `SOCIAL_SECURITY_NUMBER`
- `STREET_ADDRESS`
- `TIME`
- `URL`
- `ZIP_CODE`

The document you produced should still have the "marked for redaction" - content.
You could (at this point) ask a PDF reader (e.g. "Adobe") to apply the redaction annotations.
Although this feature may not be supported.

> :warning: If you are using `RegularExpressionTextExtraction` to mark content for redaction
> keep in mind that it might be trivially simple to retrieve said content if you remove/mark
> the exact boundaries of the matching text.
> 
> Put simply, if you are removing the word "Greece" from a PDF, and an attacker knows that the removed
> word needs to be a country, they can simply check the width of every known country in the `font` and `font_size`
> used in your PDF. This narrows down the list very quickly.
> I would advise you to always add some random padding.
> 
> You can do this by calling the `grow` method on the `Rectangle` objects returned
> by `RegularExpressionTextExtraction`.

### 6.6.2 Applying redaction annotations

In this example you'll be applying the redaction annotations you added to the `Document` earlier.

```python
#!chapter_006/src/snippet_007.py
import typing
from borb.pdf import Document
from borb.pdf import PDF


def main():

    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as pdf_file_handle:
        doc = PDF.loads(pdf_file_handle)

    # apply redaction annotations
    doc.get_page(0).apply_redact_annotations()

    # store
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_006/img/snippet_007.png)

If you now try to select the content in the `Document`, you'll see the text is gone.

<div style="page-break-before: always;"></div>

## 6.7 Adding invisible `JavaScript` buttons

This annotation requires some trickiness. You're going to add a regular `RemoteGoToAnnotation` and modify its `Action` dictionary to have the `Annotation` perform like a click-button.
You're going to add some `JavaScript` to the button's onclick.

```python
#!chapter_006/src/snippet_008.py
import typing
from borb.pdf import Document
from borb.pdf import PDF
from borb.io.read.types import Name, String
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Page
from borb.pdf import Image
from borb.pdf.canvas.layout.annotation.remote_go_to_annotation import (
    RemoteGoToAnnotation,
)

from decimal import Decimal


def main():

    # create document
    pdf = Document()

    # add page
    page = Page()
    pdf.add_page(page)

    # add test information
    layout = SingleColumnLayout(page)

    # add image
    img: Image = Image(
        "https://images.unsplash.com/photo-1614963366795-973eb8748ebb",
        width=Decimal(128),
        height=Decimal(128),
    )
    layout.add(img)

    # create RemoteGoToAnnotation
    annot: RemoteGoToAnnotation = RemoteGoToAnnotation(
        img.get_previous_paint_box(), uri="https://www.google.com"
    )

    # modify annotation
    annot[Name("A")][Name("S")] = Name("JavaScript")
    annot[Name("A")][Name("JS")] = String("app.alert('Hello World!', 3)")
    page.add_annotation(annot)

    # attempt to store PDF
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, pdf)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_006/img/snippet_008.png)

## 6.8 Adding sound annotations

Did you know you can add sound to a PDF?
This opens all kinds of options; you could add a text-to-speech rendering of your PDF to the document itself.
Talk about making your PDF accessible!

In this example we're going to add a `SoundAnnotation` to a PDF, which plays some classical music.

```python
#!chapter_006/src/snippet_009.py
import typing
from borb.pdf import Document
from borb.pdf import PDF
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Page
from borb.pdf import Image
from borb.pdf.canvas.layout.annotation.sound_annotation import SoundAnnotation
from decimal import Decimal


def main():

    # create document
    pdf = Document()

    # add page
    page = Page()
    pdf.add_page(page)

    # add test information
    layout = SingleColumnLayout(page)

    # add image
    img: Image = Image(
        "https://images.unsplash.com/photo-1513883049090-d0b7439799bf",
        width=Decimal(128),
        height=Decimal(128),
    )
    layout.add(img)

    # add sound annotation
    page.add_annotation(
        SoundAnnotation(
            img.get_previous_paint_box(), "/home/joris/Downloads/audioclip.mp3"
        )
    )

    # attempt to store PDF
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, pdf)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_006/img/snippet_009.png)

## 6.9 Conclusion

In this section you've learned how to work with `Annotation` objects.
These objects allow you to add content to existing PDF documents.

<div style="page-break-before: always;"></div>

# 7 Heuristics for PDF documents

Most of what you've done so far is exact.
There is an exact algorithm for retrieving the bytes of an embedded file.
There are algorithms for retrieving text that have been proven to work (for many years, in many libraries).

This section deals with some of the more "guesswork"-based algorithms for PDF.

One of these (and perhaps the most useful even) is extracting structured content: tables.

In this section you'll learn how to:

- Extract tables from a PDF
- Apply OCR to a PDF (and extracting text from the subsequent `Document`)
- Export a PDF to various image formats
- Export certain formats (HTML, Markdown) to PDF

<div style="page-break-before: always;"></div>

## 7.1 Extracting tables from a PDF

For the next example you'll first need to create a `Document` with a `Table`.
In order to provide `borb` with a challenge, let's create a `Table` with:

- `row_span`
- `col_span`
- `font_color`
- `text_alignment`

```python
#!chapter_007/src/snippet_001.py
from decimal import Decimal

import typing
from borb.pdf import HexColor, X11Color
from borb.pdf import Alignment
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import TableCell
from borb.pdf import FlexibleColumnWidthTable
from borb.pdf import Table
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF


def main():

    # create empty Document
    d: Document = Document()

    # add Page
    p: Page = Page()
    d.add_page(p)

    # create PageLayout
    l: PageLayout = SingleColumnLayout(p)

    # create Table
    l.add(
        FlexibleColumnWidthTable(number_of_rows=3, number_of_columns=3)
        .add(
            TableCell(
                Paragraph(
                    "1",
                    font_color=HexColor("f1cd2e"),
                    horizontal_alignment=Alignment.RIGHT,
                ),
                row_span=3,
                preferred_width=Decimal(64),
            )
        )
        .add(TableCell(Paragraph("2")))
        .add(TableCell(Paragraph("3")))
        .add(
            TableCell(
                Paragraph(
                    "4",
                    font_color=HexColor("56cbf9"),
                    horizontal_alignment=Alignment.LEFT,
                ),
                row_span=2,
                preferred_width=Decimal(32),
            )
        )
        .add(TableCell(Paragraph("5")))
        .add(TableCell(Paragraph("6", font_color=HexColor("de6449"))))
        .set_padding_on_all_cells(Decimal(5), Decimal(5), Decimal(5), Decimal(5))
    )

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, d)


if __name__ == "__main__":
    main()
```

This creates a PDF that looks like this:

![enter image description here](chapter_007/img/snippet_001.png)

Now you can use the `TableDetectionByLines` implementation of `EventListener` to get the job done.

In this example, you'll be adding rectangular annotations to display the detected `Table` and `TableCell` objects.
This is something I do a lot, adding annotations is a quick and easy way to debug a PDF workflow.

```python
#!chapter_007/src/snippet_002.py
from decimal import Decimal

import typing
from borb.pdf import HexColor, X11Color
from borb.pdf import Alignment
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import TableCell
from borb.pdf import FlexibleColumnWidthTable
from borb.pdf import Table
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.toolkit.table.table_detection_by_lines import TableDetectionByLines
from borb.pdf.canvas.layout.annotation.square_annotation import SquareAnnotation


def main():

    doc: typing.Optional[Document] = None
    l: TableDetectionByLines = TableDetectionByLines()
    with open("output.pdf", "rb") as pdf_file_handle:
        doc = PDF.loads(pdf_file_handle, [l])

    assert doc is not None

    # get page
    p: Page = doc.get_page(0)

    # get Table(s)
    tables: typing.List[Table] = l.get_tables()[0]
    assert len(tables) > 0

    for r in l.get_table_bounding_boxes()[0]:
        r = r.grow(Decimal(5))
        p.add_annotation(SquareAnnotation(r, stroke_color=X11Color("Green")))

    for t in tables:

        # add one annotation around each cell
        for c in t._content:
            r = c.get_previous_paint_box()
            r = r.shrink(Decimal(5))
            p.add_annotation(SquareAnnotation(r, stroke_color=X11Color("Red")))

    # write
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_007/img/snippet_002.png)

As you can see, `borb` was able to find the `Table` and retrieve its `TableCell` objects.
Now that you have their coordinates, you can easily use some of the earlier examples (filtering text by location for instance) to retrieve the contents of each cell.

<div style="page-break-before: always;"></div>

## 7.2 Performing OCR on a PDF

This is by far one of the most classic questions on any programming-forum, or helpdesk: "My document does not seem to have text in it. Help?" or "Your text-extraction code sample does not work for my document. How come?"

The answer is often as straightforward as "your scanner hates you".

Most of the documents for which this doesn't work are PDF documents that are essentially glorified images.
They contain all the meta-data needed to constitute a PDF, but their pages are just large (often low-quality) images.

As a consequence, there are no text-rendering instructions in these documents. 
And most PDF libraries will not be able to handle them.

`borb` however is different, `borb` just loves to help.

In this section you'll be using a special `EventListener` implementation called `OCRAsOptionalContentGroup`.
This class uses `tesseract` (or rather `pytesseract`) to perform OCR (optical character recognition) on the `Document`.

Once finished, the recognized text is re-inserted in each `Page` as a special "layer" (in PDF this is called an "optional content group").

With the content now restored, the usual tricks (`SimpleTextExtraction`) yield the expected results.


You'll start by creating a method that builds a PIL `Image` with some text in it.
This `Image` will then be inserted in a PDF.

```python
#!chapter_007/src/snippet_003.py
import typing
from pathlib import Path

from borb.pdf import PDF
from PIL import Image as PILImage  # type: ignore [import]
from PIL import ImageDraw, ImageFont


def create_image() -> PILImage:

    # create new Image
    img = PILImage.new("RGB", (256, 256), color=(255, 255, 255))

    # create ImageFont
    # CAUTION: you may need to adjust the path to your particular font directory
    font = ImageFont.truetype("/usr/share/fonts/truetype/ubuntu/UbuntuMono-B.ttf", 24)

    # draw text
    draw = ImageDraw.Draw(img)
    draw.text((10, 10), "Hello World!", fill=(0, 0, 0), font=font)

    # return
    return img
```

Now you can build a `Document` with this `Image`

```python
#!chapter_007/src/snippet_004.py
import typing
from pathlib import Path

from borb.pdf import Image
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from PIL import Image as PILImage  # type: ignore [import]
from PIL import ImageDraw, ImageFont


def create_image() -> PILImage:

    # create new Image
    img = PILImage.new("RGB", (256, 256), color=(255, 255, 255))

    # create ImageFont
    # CAUTION: you may need to adjust the path to your particular font directory
    font = ImageFont.truetype("/usr/share/fonts/truetype/ubuntu/UbuntuMono-B.ttf", 24)

    # draw text
    draw = ImageDraw.Draw(img)
    draw.fontmode = "L"
    draw.text((10, 10), "Hello World!", fill=(0, 0, 0), font=font)

    # return
    output_path: Path = Path(__file__).parent / "image_hello_world.png"
    img.save(output_path, dpi=(600, 600))
    return output_path


def main():

    # create Document
    d: Document = Document()

    # create/add Page
    p: Page = Page()
    d.add_page(p)

    # set PageLayout
    l: PageLayout = SingleColumnLayout(p)

    # add Paragraph
    l.add(Paragraph("Lorem Ipsum"))

    # add Image
    l.add(Image(create_image()))

    # write
    with open("output_001.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, d)


if __name__ == "__main__":
    main()
```

The document should look something like this:

![enter image description here](chapter_007/img/snippet_004_001.png)

When you select the text in this document, you'll see immediately that only the top line is actually text.
The rest is an `Image` with text (the `Image` you created).

![enter image description here](chapter_007/img/snippet_004_002.png)

Now you can apply OCR to this `Document`:

```python
#!chapter_007/src/snippet_005.py
from borb.pdf import Document
from borb.pdf import PDF
from borb.toolkit.ocr.ocr_as_optional_content_group import OCRAsOptionalContentGroup

from pathlib import Path


def main():

    # set up everything for OCR
    tesseract_data_dir: Path = Path("/home/joris/Downloads/tessdata-master/")
    assert tesseract_data_dir.exists()
    l: OCRAsOptionalContentGroup = OCRAsOptionalContentGroup(tesseract_data_dir)

    # read Document
    doc: typing.Optional[Document] = None
    with open("output_001.pdf", "rb") as pdf_file_handle:
        doc = PDF.loads(pdf_file_handle, [l])

    assert doc is not None

    # store Document
    with open("output_002.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_007/img/snippet_005_001.png)

You can see this created an extra layer in the PDF.
This layer is named "OCR by borb", and contains the rendering instructions `borb` re-inserted in the `Document`.

You can toggle the visibility of this layer (this can be handy when debugging).

![enter image description here](chapter_007/img/snippet_005_002.png)

You can see `borb` re-inserted the postscript rendering command to ensure "Hello World!" is in the `Document.
Let's hide this layer again.

Now (even with the layer hidden), you can select the text:

![enter image description here](chapter_007/img/snippet_005_003.png)

And if you apply `SimpleTextExtraction` now, you should be able to retrieve all the text in the `Document`.

```python
#!chapter_007/src/snippet_006.py
from borb.pdf import Document
from borb.pdf import PDF
from borb.toolkit.text.simple_text_extraction import SimpleTextExtraction


def main():

    doc: typing.Optional[Document] = None
    l: SimpleTextExtraction = SimpleTextExtraction()
    with open("output_002.pdf", "rb") as pdf_file_handle:
        doc = PDF.loads(pdf_file_handle, [l])

    print(l.get_text()[0])


if __name__ == "__main__":
    main()
```

This prints:

```
Lorem Ipsum
Hello World!
```

<div style="page-break-before: always;"></div>

## 7.3 Exporting PDF as a (PIL) image

Let's start by creating a PDF we can later export.
In the next example you'll be creating a PDF with different fonts, font-sizes and an image.

```python
#!chapter_007/src/snippet_007.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import Image
from borb.pdf import PDF

from decimal import Decimal


def main():

    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()

    # add Page to Document
    doc.add_page(page)

    # set a PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add an Image
    layout.add(
        Image(
            "https://www.gutenberg.org/cache/epub/58866/pg58866.cover.medium.jpg",
            width=Decimal(200),
            height=Decimal(300),
        )
    )

    # add a Paragraph
    layout.add(
        Paragraph("1. A Fellow Traveller", font="Helvetica-bold", font_size=Decimal(20))
    )
    layout.add(
        Paragraph(
            """
    I believe that a well-known anecdote exists to the effect that a young
    writer, determined to make the commencement of his story forcible and
    original enough to catch and rivet the attention of the most blasé of
    editors, penned the following sentence:
    """
        )
    )

    # store
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_007/img/snippet_007.png)

Now let's export this as an Image.

```python
#!chapter_007/src/snippet_008.py
from borb.pdf import PDF
from borb.toolkit.export.pdf_to_jpg import PDFToJPG


def main():

    # read PDF
    with open("output.pdf", "rb") as pdf_file_handle:
        doc = PDF.loads(pdf_file_handle)

    # convert to JPG
    PDFToJPG.convert_pdf_to_jpg(doc)[0].save("output_page_00.jpg")


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_007/img/snippet_008.jpg)


<div style="page-break-before: always;"></div>

## 7.4 Exporting PDF as an SVG image

```python
#!chapter_007/src/snippet_009.py
from borb.pdf import PDF
from borb.toolkit.export.pdf_to_svg import PDFToSVG

from pathlib import Path
import xml.etree.ElementTree as ET


def main():

    # read PDF
    input_file: Path = Path(__file__).parent / "output.pdf"
    with open(input_file, "rb") as pdf_file_handle:
        doc = PDF.loads(pdf_file_handle)

    # write ET.Element
    with open("output_page_00.svg", "wb") as svg_file_handle:
        svg_file_handle.write(ET.tostring(PDFToSVG.convert_pdf_to_svg(doc)[0]))


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_007/img/snippet_009.jpg)


<div style="page-break-before: always;"></div>

## 7.5 Exporting Markdown as PDF

Markdown is a very convenient format (for developers and non-technical people) to provide a quick and legible lightweight formatted document.

You'll be using the following input markdown:

> \# Headings  
> To create a heading, add number signs (#) in front of a word or phrase. The number of number signs you use should correspond to the heading level. For example, to create a heading level three (\<h3\>), use three number signs (e.g., ### My Header).
>  
> \# Heading level 1  
> \#\# Heading level 2  
> \#\#\# Heading level 3  
> \#\#\#\# Heading level 4  
> \#\#\#\#\# Heading level 5  
> \#\#\#\#\#\# Heading level 6  
>
> \#\# Alternate Syntax
> Alternatively, on the line below the text, add any number of == characters for heading level 1 or -- characters for heading level 2.
>
> Heading level 1  
> \===============
>
> Heading level 2  
> \---------------
>
> \#\# Heading Best Practices  
> Markdown applications don’t agree on how to handle a missing space between the number signs (#) and the heading name. For compatibility, always put a space between the number signs and the heading name.
>
> You should also put blank lines before and after a heading for compatibility.

Using `borb`, you can transform Markdown to PDF;

```python
#!chapter_007/src/snippet_010.py
from borb.pdf import Document
from borb.pdf import PDF
from borb.toolkit.export.markdown_to_pdf.markdown_to_pdf import MarkdownToPDF

from pathlib import Path

def main():

    # read entire markdown file
    markdown_str: str = ""
    with open(Path(__file__).parent / "snippet_010.md", "r") as md_file_handle:
        markdown_str = md_file_handle.read()

    # convert
    doc: Document = MarkdownToPDF.convert_markdown_to_pdf(markdown_str)
    assert doc is not None

    # write
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

This produces the following PDF;

![enter image description here](chapter_007/img/snippet_010.png)

<div style="page-break-before: always;"></div>

## 7.6 Exporting HTML as PDF

Another wonderful format for content is HTML. 
`borb` supports basic HTML to PDF conversion. 
Keep an eye out for this functionality in the future, as new features, tags and support will be added gradually.

For this example, you'll be using the following HTML snippet:

> \<html>  
>   \<head>  
>       \<title>Lorem Ipsum\</title>  
>   \</head>  
>       \<p>  
>            Hello World!  
>       \</p>  
>    \</html>

```python
#!chapter_007/src/snippet_011.py
from borb.pdf import Document
from borb.pdf import PDF
from borb.toolkit.export.html_to_pdf.html_to_pdf import HTMLToPDF

from pathlib import Path

def main():

    # read entire markdown file
    html_str: str = ""
    with open(Path(__file__).parent / "snippet_011.html", "r") as md_file_handle:
        html_str = md_file_handle.read()

    # convert
    doc: Document = HTMLToPDF.convert_html_to_pdf(html_str)
    assert doc is not None

    # write
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

Which ends up producing the following PDF:

![enter image description here](chapter_007/img/snippet_011.png)

You'll also notice (if you open this PDF in your preferred viewer) that the title of the `Document` was set to `"lorem ipsum"`.
So `borb` also processed the meta-information.

Check out the examples in the GitHub repository and the tests to find out more supported `HTML`.

<div style="page-break-before: always;"></div>

## 7.7 Replacing text in an existing PDF

One recurring question is "How do replace X by Y in this PDF?".
By now, you should know that this is not really all that easy.

Finding text is a heuristic process, which can become exceedingly difficult if the PDF
does not have a simple layout. As soon as we have multiple-columns, tables, or combinations thereof it becomes
harder and harder to match a regular expression against the visible text of a PDF.

Removing content can be done by inserting and applying a `RedactAnnotation` (which is part of the standard).

Inserting content afterwards again requires knowledge of the structure of the PDF (which is typically missing in PDF documents found in the wild).
The problem is reflow. Replacing "Bob" by "Robert" means you have to shift every subsequent character by 3 places.

`borb` supports a very rudimentary form of find/replace in its `SimpleFindReplace` class (in `toolkit`).

In this example we'll explore one of these simple usecases.
We're going to be start by creating a PDF.

```python
#!chapter_007/src/snippet_012.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PageLayout, SingleColumnLayout
from borb.pdf import Table, FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import PDF

from decimal import Decimal


def main():

    # create empty Document
    doc: Document = Document()

    # add new Page
    pge: Page = Page()
    doc.add_page(pge)

    # set PageLayout
    lay: PageLayout = SingleColumnLayout(pge)

    # add Table
    tab: Table = FixedColumnWidthTable(number_of_columns=2, number_of_rows=3)
    tab.add(Paragraph("Name:", font="Helvetica-Bold"))
    tab.add(Paragraph("Schellekens"))
    tab.add(Paragraph("Firstname:", font="Helvetica-Bold"))
    tab.add(Paragraph("Jots"))
    tab.add(Paragraph("Title:", font="Helvetica-Bold"))
    tab.add(Paragraph("CEO borb"))
    tab.set_padding_on_all_cells(Decimal(5), Decimal(5), Decimal(5), Decimal(5))
    lay.add(tab)

    # store
    with open("output.pdf", 'wb') as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)

if __name__ == "__main__":
    main()
```

This PDF should look like the one below:

![enter image description here](chapter_007/img/snippet_012.png)

The problem being that my name is not **Jots Schellekens**.

Now let's apply `SimpleFindReplace` to fix our little mistake:

```python
#!chapter_007/src/snippet_013.py
from borb.pdf import Document
from borb.pdf import PDF
from borb.toolkit import SimpleFindReplace

import typing


def main():

    # attempt to read a PDF
    doc: typing.Optional[Document] = None
    with open("output.pdf", "rb") as pdf_file_handle:
        doc = PDF.loads(pdf_file_handle)

    # check whether we actually read a PDF
    assert doc is not None

    # find/replace
    doc = SimpleFindReplace.sub("Jots", "Joris", doc)

    # store
    with open("output2.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

![enter image description here](chapter_007/img/snippet_013.png)

Much better!

**Keep in mind** that `SimpleFindReplace` does not handle complex re-flow.
It only handles cases where you want to replace some text by some other text, without
any influence on surrounding text.

## 7.8 Conclusion

In this chapter you've learned some of the more advanced ways of working with `borb` and PDF in general.
You've learnt how to convert various formats to PDF, and back again. You've applied OCR, and extracted tables.
The examples in this chapter may not be for everyone, but you will undoubtedly gain a deeper understanding of `borb` and PDF by studying the code.

<div style="page-break-before: always;"></div>

# 8 Deep Dive into `borb`

<div style="page-break-before: always;"></div>

## 8.1 About PDF

If we consider PDF as a programming language, then these would be its primitive data-types:

- Strings (either as plaintext, or hexadecimal)
- Numbers
- Booleans
- Name objects (think of these as "reserved strings")

From which the bigger objects are built:

- Dictionaries (maps name objects to any value, delimited by `<<` and `>>`)
- Arrays (delimited by `[` and `]`)
- Streams (these typically represent binary compressed data)
- References

This is an example dictionary object:

```
<<  /Root 1 0 R 
    /Info 2 0 R 
    /Size 18 
    /ID [<02c1677f2c452985480d6a68b2cdfe96> <02c1677f2c452985480d6a68b2cdfe96>]
    >>
```

The keys are name objects:

- `/Root`
- `/Info`
- `Size`
- `ID`

Objects such as `1 0 R` are references. They need to be resolved by the XREF (more on that later).

```
[<02c1677f2c452985480d6a68b2cdfe96> <02c1677f2c452985480d6a68b2cdfe96>]
```

is an array containing two hexadecimal string objects.

## 8.2 The XREF table

The cross-reference table in a PDF is one of many tricks designed to speed up a reader. A cross-reference table (further abbreviated as XREF) contains a mapping of all PDF objects and their byte offset.

A conforming reader will start reading a PDF backwards, reading the `startxref` keyword. 

This is an example XREF:

```
xref
0 18
0000000000 00000 f
0000000015 00000 n
0000381959 00000 n
0000000064 00000 n
0000381716 00000 n
0000000121 00000 n
0000000273 00000 n
0000052510 00000 n
0000052542 00000 n
0000052583 00000 n
0000381619 00000 n
0000052752 00000 n
0000055981 00000 n
0000371339 00000 n
0000056194 00000 n
0000371411 00000 n
0000381788 00000 n
0000381888 00000 n
trailer
<</Root 1 0 R /Info 2 0 R /Size 18 /ID [<02c1677f2c452985480d6a68b2cdfe96> <02c1677f2c452985480d6a68b2cdfe96>]>>
startxref
382063
%%EOF
```

Just after the `startxref` keyword you'll find a number representing the byte offset at which the start of the XREF can be found.

The start of the XREF table is delimited with the `xref` keyword. 
Just after it you'll find two numbers (`0 18`). This means the first object of the PDF starts at number 0, and this XREF table contains 18 objects. 

Each is responsible for a line like:

```
0000000273 00000 n
```

This is the 7th line of the XREF, so this line relates to object number 7. It says object 7 can be found at byte offset `0000000273`.
The second number on that line represents the `generation`. 
PDF allows you to revise a document. 
So each object has a generation to signify whether it belongs to a particular revision of the PDF.

The last part of each line is `n` or `f`. `n` means the object is currently is use. Objects marked with `f` should be considered as non-content.

The XREF also contains the trailer dictionary. This dictionary is the starting point of the PDF object tree.

```
<</Root 1 0 R /Info 2 0 R /Size 18 /ID [<02c1677f2c452985480d6a68b2cdfe96> <02c1677f2c452985480d6a68b2cdfe96>]>>
```

- `/Root` is where the actual content objects of the PDF begin. In this trailer, the `/Root` entry points to object `1 (generation 0)`.
- `/Info` points to the info-dictionary, which is where you'll find the meta-data such as author, producer, modification date, etc. In this trailer, the `/Info` entry points to object `2 (generation 0)`.

If you follow the `/Root` entry, you'll find something like:

```
1 0 obj
<</Type /Catalog /Pages 3 0 R /Outlines 4 0 R>>
endobj
``` 

The `/Pages` entry points to an array (one element per page), which form the beginning of the page-content.

```
3 0 obj
<</Count 1 /Kids [5 0 R] /Type /Pages>>
endobj
```

Each entry in the `/Kids` array represents a single `Page`.

```
5 0 obj
<</Type /Page /MediaBox [0 0 595 842] /Parent 3 0 R /Contents 6 0 R /Resources 7 0 R>>
endobj
```

`/Contents` points to the `Page` content stream. This is a string of postfix instructions (usually compressed using `deflate`).

### 8.2.2 Dealing with a broken XREF
 
A PDF document is considered *broken* if it no longer opens:
- in Adobe Reader (or a similar PDF reader)
- in `borb`

The reason why those two are different criteria is that Adobe is very lenient when it comes to enforcing the PDF standards. Which is understandable, you want PDF reading software to be able to read as many documents as possible.

`borb` however tends to be very strict when it comes to dealing with PDF documents (in fact most PDF generators are).

When a PDF no longer opens, it is usually down to the `XREF` being incorrect. Which is to say, some byte-miscount in the document.
Remember, the PDF document is supposed to announce at which byte the `XREF` table begins. If that byte-count is off by even 1 byte, the `XREF` table is (from the standpoint of the PDF spec) no longer in the right location.

To fix this, `borb` has a last-resort parser to rebuild an `XREF`, this is the `RebuiltXREF` class.
This parser will go over the entire PDF, looking for object declarations, and keep track of their byte count. This is effectively reverse-engineering the `XREF` document (at the cost of having to run over the entire file).

Whenever `borb` is forced to do this, you may expect the logging to indicate as such.

## 8.3 Page content streams

In the previous section you explored the top-level objects of a PDF.
You got all the way down to the `Page` object.
Now you can look under the hood and see the instructions in the content stream.

```
6 0 obj
<</Length 52185>>
stream

            q
            BT
            0.521569 0.780392 0.870588 rg
            /F1 1.000000 Tf
            24.000000 0 0 24.000000 59.500000 725.760000 Tm
            (Hello World!) Tj
            ET
            Q 

            q
            ... etc ...
```

This is the (inflated) page content stream. It contains the raw instructions for rendering content on the `Page`.
Operators are prefix operators, meaning the arguments come before the operator.

- `q` : pushes a new graphics environment on the stack
- `BT` : begin text
- `0.521569 0.780392 0.870588 rg` : set the color (using RGB color mode)
- `/F1 1.000000 Tf` : use the font specified in `/Resources/Font/F1`, at size `1`
- `24.000000 0 0 24.000000 59.500000 725.760000 Tm` : sets the font-transformation matrix (essentially setting the font size to 24, and setting the text position)
- `(Hello World!) Tj` : render the text "Hello World!"
- `ET` : end text
- `Q` : pop the last element from the graphics environment stack

<div style="page-break-before: always;"></div>

## 8.4 Postscript syntax

This section provides you with a quick overview of the most common PDF operators.
This is meant to enable you to debug PDF documents.

For a more detailed explanation I would advise you to check out the PDF-specification.
A free copy of which can be found:

- In the `borb` GitHub repository
- On the Adobe website

| Operator | Number of arguments | Type of arguments | Description                                                                                                                                                                                                                                                                                                                                                                                                   |
|----------|---------------------|-------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| b        | 0                   |                   | Close, fill, and stroke path using nonzero winding number rule                                                                                                                                                                                                                                                                                                                                                |
| B        | 0                   |                   | Fill and then stroke the path, using the nonzero winding number rule to determine the region to fill.                                                                                                                                                                                                                                                                                                         |
| b*       | 0                   |                   | Close, fill, and then stroke the path, using the even-odd rule to determine the region to fill.                                                                                                                                                                                                                                                                                                               |
| B*       | 0                   |                   | Fill and then stroke the path, using the even-odd rule to determine the region to fill.                                                                                                                                                                                                                                                                                                                       |
| BDC      | 2                   |                   | Begin a marked-content sequence with an associated property list, terminated by a balancing EMC operator. tag shall be a name object indicating the role or significance of the sequence. properties shall be either an inline dictionary containing the property list or a name object associated with it in the Properties subdictionary of the current resource dictionary (see 14.6.2, “Property Lists”). |
| BI       | 0                   |                   | Begin an inline image object.                                                                                                                                                                                                                                                                                                                                                                                 |
| BMC      | 1                   |                   | Begin a marked-content sequence terminated by a balancing **EMC** operator. tag shall be a name object indicating the role or significance of the sequence.                                                                                                                                                                                                                                                   |
| BT       |
| BX       |
| c        |
| cm       |
| CS       |
| cs       |
| d        |
| d0       |
| d1       |
| Do       |
| DP       | 2                   |                   | Designate a marked-content point with an associated property list. tag shall be a name object indicating the role or significance of the point. properties shall be either an inline dictionary containing the property list or a name object associated with it in the Properties subdictionary of the current resource dictionary (see 14.6.2, “Property Lists”).                                           |
| EI       | 0                   |                   | End an inline image object.                                                                                                                                                                                                                                                                                                                                                                                   |
| EMC      | 0                   |                   | End a marked-content sequence begun by a **BMC** or **BDC** operator.                                                                                                                                                                                                                                                                                                                                         |
| ET       |
| EX       |
| f        | 0                   |                   | Fill the path, using the nonzero winding number rule to determine the region to fill (see 8.5.3.3.2, "Nonzero Winding Number Rule"). Any subpaths that are open shall be implicitly closed before being filled.                                                                                                                                                                                               |
| F        | 0                   |                   | Equivalent to **f**; included only for compatibility. Although PDF reader applications shall be able to accept this operator, PDF writer applications should use **f** instead.                                                                                                                                                                                                                               |
| f*       | 0                   |                   | Fill the path, using the even-odd rule to determine the region to fill (see 8.5.3.3.3, "Even-Odd Rule").                                                                                                                                                                                                                                                                                                      |
| G        |
| g        |
| gs       |
| h        |
| i        |
| ID       | 0                   |                   | Begin the image data for an inline image object.                                                                                                                                                                                                                                                                                                                                                              |
| j        |
| J        |
| K        |
| k        |
| l        | 2                   |                   | Append a straight line segment from the current point to the point (x, y). The new current point shall be (x, y).                                                                                                                                                                                                                                                                                             |
| m        | 2                   |                   | Begin a new subpath by moving the current point to coordinates (x, y), omitting any connecting line segment. If the previous path construction operator in the current path was also m, the new m overrides it; no vestige of the previous m operation remains in the path.                                                                                                                                   |
| M        |
| MP       | 1                   |                   | Designate a marked-content point. tag shall be a name object indicating the role or significance of the point.                                                                                                                                                                                                                                                                                                |
| n        | 0                   |                   | End the path object without filling or stroking it. This operator shall be a path-painting no-op, used primarily for the side effect of changing the current clipping path (see 8.5.4, "Clipping Path Operators").                                                                                                                                                                                            |
| q        |
| Q        |
| re       |
| RG       |
| rg       |
| ri       |
| s        | 0                   |                   | Close and stroke the path.                                                                                                                                                                                                                                                                                                                                                                                    |
| S        | 0                   |                   | Stroke the path.                                                                                                                                                                                                                                                                                                                                                                                              |
| SC       |
| sc       |
| SCN      |
| scn      |
| sh       |
| T*       |
| Tc       |
| Td       |
| TD       |
| Tf       |
| Tj       |
| TJ       |
| TL       |
| Tm       |
| Tr       |
| Ts       |
| Tw       |
| Tz       |
| v        |
| w        |
| W        |
| W*       |
| y        |
| '        |
| "        |

<div style="page-break-before: always;"></div>

## 8.5 Creating a `Document` using low-level syntax

In this subsection I'll take you through all of the relevant pieces of `borb` when rendering a small piece of text to a PDF.
This is a bit like having someone sit next to you, explaining the code while you're stepping through it with a debugger.
I hope this subsection teaches you some of the internal workings of `borb` and helps you gain a better understanding of where to look should you encounter any problems.

Now that you have some knowledge of the low-level syntax of PDF, you can try to build a PDF document.
In this example, you're going to create a PDF with the text "Hello World!".
This time, you'll be using only the low-level syntax. Later, you'll see how the `LayoutElement` objects end up writing this content to the PDF.

Although this is not very practical it will do several things:

- Give you a deeper appreciation for PDF libraries
- Grant you to power to specify the document exactly as you want, now that you understand PDF at its finest
- Enable you to write your own `LayoutElement` implementations (if needed) 

In this example, you'll be creating a PDF from scratch, containing "Hello World!", using only the low-level syntax.

We'll start by creating an empty `Document` and add an empty `Page`:

```python
#!chapter_008/src/snippet_001.py
def main():
    
    # create empty Document
    pdf: Document = Document()
    
    # add empty Page
    page = Page()
    pdf.add_page(page)

if __name__ == "__main__":
    main()```

Now we can start writing PostScript operators to the content-stream of the `Page`:

```python
#!chapter_008/src/snippet_002.py
def main():
    
    # create empty Document
    pdf: Document = Document()
    
    # add empty Page
    page = Page()
    pdf.add_page(page)

    # create content stream
    content_stream = Stream()
    content_stream[
        Name("DecodedBytes")
    ] = b"""
        q
        BT
        /F1 24 Tf            
        59 742 Td            
        (Lorem Ipsum) Tj
        ET
        Q
    """
    content_stream[Name("Bytes")] = zlib.compress(content_stream["DecodedBytes"], 9)
    content_stream[Name("Filter")] = Name("FlateDecode")
    content_stream[Name("Length")] = bDecimal(len(content_stream["Bytes"]))

    # set content of page
    page[Name("Contents")] = content_stream


if __name__ == "__main__":
    main()```

We've now used a font called `F1` in our `Page`, we need to define that: 

```python
#!chapter_008/src/snippet_003.py
def main():
    
    # create empty Document
    pdf: Document = Document()
    
    # add empty Page
    page = Page()
    pdf.add_page(page)

    # create content stream
    content_stream = Stream()
    content_stream[
        Name("DecodedBytes")
    ] = b"""
        q
        BT
        /F1 24 Tf            
        59 742 Td            
        (Lorem Ipsum) Tj
        ET
        Q
    """
    content_stream[Name("Bytes")] = zlib.compress(content_stream["DecodedBytes"], 9)
    content_stream[Name("Filter")] = Name("FlateDecode")
    content_stream[Name("Length")] = bDecimal(len(content_stream["Bytes"]))

    # set content of page
    page[Name("Contents")] = content_stream

    # set Font
    page[Name("Resources")] = Dictionary()
    page["Resources"][Name("Font")] = Dictionary()
    page["Resources"]["Font"][Name("F1")] = Dictionary()
    page["Resources"]["Font"]["F1"][Name("Type")] = Name("Font")
    page["Resources"]["Font"]["F1"][Name("Subtype")] = Name("Type1")
    page["Resources"]["Font"]["F1"][Name("Name")] = Name("F1")
    page["Resources"]["Font"]["F1"][Name("BaseFont")] = Name("Helvetica")
    page["Resources"]["Font"]["F1"][Name("Encoding")] = Name("MacRomanEncoding")


if __name__ == "__main__":
    main()```

Finally, we can store the PDF:

```python
#!chapter_008/src/snippet_004.py
def main():
    
    # create empty Document
    pdf: Document = Document()
    
    # add empty Page
    page = Page()
    pdf.add_page(page)

    # create content stream
    content_stream = Stream()
    content_stream[
        Name("DecodedBytes")
    ] = b"""
        q
        BT
        /F1 24 Tf            
        59 742 Td            
        (Lorem Ipsum) Tj
        ET
        Q
    """
    content_stream[Name("Bytes")] = zlib.compress(content_stream["DecodedBytes"], 9)
    content_stream[Name("Filter")] = Name("FlateDecode")
    content_stream[Name("Length")] = bDecimal(len(content_stream["Bytes"]))

    # set content of page
    page[Name("Contents")] = content_stream

    # set Font
    page[Name("Resources")] = Dictionary()
    page["Resources"][Name("Font")] = Dictionary()
    page["Resources"]["Font"][Name("F1")] = Dictionary()
    page["Resources"]["Font"]["F1"][Name("Type")] = Name("Font")
    page["Resources"]["Font"]["F1"][Name("Subtype")] = Name("Type1")
    page["Resources"]["Font"]["F1"][Name("Name")] = Name("F1")
    page["Resources"]["Font"]["F1"][Name("BaseFont")] = Name("Helvetica")
    page["Resources"]["Font"]["F1"][Name("Encoding")] = Name("MacRomanEncoding")

    # store PDF
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, pdf)

if __name__ == "__main__":
    main()```

<div style="page-break-before: always;"></div>

## 8.6 Fonts in PDF

A font shall be represented in PDF as a dictionary specifying the type of font, its PostScript name, its encoding,
and information that can be used to provide a substitute when the font program is not available. Optionally, the
font program may be embedded as a stream object in the PDF file.

### 8.6.1 Simple fonts

There are several types of simple fonts, all of which have these properties:
- Glyphs in the font shall be selected by single-byte character codes obtained from a string that is shown by
the text-showing operators. Logically, these codes index into a table of 256 glyphs; the mapping from
codes to glyphs is called the font’s encoding. Under some circumstances, the encoding may be altered by
means described in 9.6.6, "Character Encoding".
- Each glyph shall have a single set of metrics, including a horizontal displacement or width, as described in
9.2.4, "Glyph Positioning and Metrics"; that is, simple fonts support only horizontal writing mode.
- Except for Type 0 fonts, Type 3 fonts in non-Tagged PDF documents, and certain standard Type 1 fonts,
every font dictionary shall contain a subsidiary dictionary, the font descriptor, containing font-wide metrics
and other attributes of the font; see 9.8, "Font Descriptors". Among those attributes is an optional font file
stream containing the font program.

### 8.6.2 Composite fonts

A composite font, also called a Type 0 font, is one whose glyphs are obtained from a fontlike object called a
CIDFont. A composite font shall be represented by a font dictionary whose Subtype value is Type0. The Type
0 font is known as the root font, and its associated CIDFont is called its descendant.

**NOTE 1:**
Composite fonts in PDF are analogous to composite fonts in PostScript but with some limitations. In particular,
PDF requires that the character encoding be defined by a CMap, which is only one of several encoding
methods available in PostScript. Also, PostScript allows a Type 0 font to have multiple descendants, which
might also be Type 0 fonts. PDF supports only a single descendant, which shall be a CIDFont.

When the current font is composite, the text-showing operators shall behave differently than with simple fonts.
For simple fonts, each byte of a string to be shown selects one glyph, whereas for composite fonts, a sequence
of one or more bytes are decoded to select a glyph from the descendant CIDFont.

**NOTE 2:**
This facility supports the use of very large character sets, such as those for the Chinese, Japanese, and
Korean languages. It also simplifies the organization of fonts that have complex encoding requirements.

<div style="page-break-before: always;"></div>

## 8.7 About structured vs. unstructured document formats

Typically, at one point or another when you're working with PDF, someone will come along that would like to convert the PDF to some other format.
Most libraries or software-tools offer all kinds of wacky conversions. Some more successful than others.
The reason for the varying degrees of success is not just to do with the diligence of the creator, but rather the chasm between structured and unstructured document formats;

- structured document format: every piece of content is typically provided with
    - coordinates (or coordinates can be derived using a layout algorithm)
    - a logical structure
  In `HTML` for instance, a `<p>` element is rendered on a browser (it has coordinates), and all the text inside that element knows it is part of that paragraph. The paragraph itself may be part of some other element (a `<table>` or `<li>`, etc).
- unstructured document format: no logical structure (or no such structure is mandatory)

PDF is an unstructured format.   
You've explored the rendering instructions that make up a `Page`, and you will have noticed there is no indicator to say "all these instructions belong to one paragraph", or "this paragraph belongs to a table".
You can of course do this (the PDF standard provides so called "tagged" PDF), but is rare to see such PDFs in the wild.

So, when extracting text from a PDF `borb` is faced with several issues:

- text rendering instructions do not make it clear where a paragraph begins/ends
- the `space` character can either be encoded in the rendering instructions, but it can also be omitted (you can simply move the drawing cursor a few dots to the right)
- text rendering instructions do not need to appear in any particular order

In order to be able to extract text, `borb` has to do a lot of work. Let's have a look behind the scenes to see what goes on.

### 8.7.1 Text extraction: using heuristics to bridge the gap

In `borb`, the easiest way of accessing the text on a page is by using `SimpleTextExtraction`.
Let's have a look at how it works.

First, there is `ChunkOfTextRenderEvent`:

```python
class ChunkOfTextRenderEvent(Event, ChunkOfText):
    """
    This implementation of Event is triggered right after the Canvas has processed a text-rendering instruction
    """

    def __init__(self, graphics_state: CanvasGraphicsState, raw_bytes: String):
        ... etc ...
```

This class represents the call-back information that is passed to `EventListener` objects.
Whenever `borb` processes the page content-stream, every operator has the opportunity to send out these `Event` objects to `EventListener` implementations.     

This is the `ShowText` operator (the `Tj` operator in postscript);

```python
class ShowText(CanvasOperator):
    """
    Show a text string.
    """

    def __init__(self):
        super().__init__("Tj", 1)

    def invoke(self, canvas_stream_processor: "CanvasStreamProcessor", operands: List[AnyPDFType] = []) -> None:  # type: ignore [name-defined]
        """
        Invoke the Tj operator
        """
        ... etc ...

```

In its `invoke` method, you'll find the call that sends out one of these `ChunkOfTextRenderEvent` objects:

```python
        tri = ChunkOfTextRenderEvent(canvas.graphics_state, operands[0])

        # render
        canvas._event_occurred(tri)
```

So now we know which information is being passed, and when. Let's have a look at `SimpleTextExtraction` to see how that information is processed;

```python
    def _event_occurred(self, event: Event) -> None:
        if isinstance(event, ChunkOfTextRenderEvent):
            self._render_text(event)
        if isinstance(event, BeginPageEvent):
            self._begin_page(event.get_page())
        if isinstance(event, EndPageEvent):
            self._end_page(event.get_page())
```

All implementations of `EventListener` have this `_event_occurred` method, which passes the `Event` objects it receives.
You can see `SimpleTextExtraction` only cares about the start and end of a `Page` and `ChunkOfTextRenderEvent`.

Of course, the instructions for rendering text may not be in (reading) order. So they need to be stored (until the end of a `Page`) before they can be sorted.

```python
    def _render_text(self, text_render_info: ChunkOfTextRenderEvent):

        # init if needed
        if self._current_page not in self._text_render_info_per_page:
            self._text_render_info_per_page[self._current_page] = []

        # append TextRenderInfo
        self._text_render_info_per_page[self._current_page].append(text_render_info)
```

Once the end of a `Page` is reached, the list is sorted (and any instructions that do not render text are thrown out):

```python
    def _end_page(self, page: Page):

        # get TextRenderInfo objects on page
        tris = (
            self._text_render_info_per_page[self._current_page]
            if self._current_page in self._text_render_info_per_page
            else []
        )

        # remove no-op
        tris = [x for x in tris if x._text is not None]
        tris = [x for x in tris if len(x._text.replace(" ", "")) != 0]

        # skip empty
        if len(tris) == 0:
            return

        # sort according to comparator
        sorted(tris, key=cmp_to_key(LeftToRightComparator.cmp))
```

The comparator being used sorts the `ChunkOfTextRenderEvent` objects in the expected (western) paradigm of top-to-bottom, left-to-right.

Then we need to loop over these objects and insert the `space` and `newline` character and when needed;

```python

        # iterate over the TextRenderInfo objects to get the text
        last_baseline_bottom = tris[0].get_baseline().y
        last_baseline_right = tris[0].get_baseline().x
        text = ""
        for t in tris:

            # add newline if needed
            if abs(t.get_baseline().y - last_baseline_bottom) > 10 and len(text) > 0:
                if text.endswith(" "):
                    text = text[0:-1]
                text += "\n"
                text += t._text
                last_baseline_right = t.get_baseline().x + t.get_baseline().width
                last_baseline_bottom = t.get_baseline().y
                continue

            # check text
            if t._text.startswith(" ") or text.endswith(" "):
                text += t._text
                last_baseline_right = t.get_baseline().x + t.get_baseline().width
                continue

            # add space if needed
            delta = abs(last_baseline_right - t.get_baseline().x)
            space_width = round(t.get_space_character_width_estimate_in_user_space(), 1)
            text += " " if (space_width * Decimal(0.90) < delta) else ""

            # normal append
            text += t._text
            last_baseline_right = t.get_baseline().x + t.get_baseline().width
            continue

```

finally, `SimpleTextExtraction` stores the reconstituted text (to ensure fast lookup);

```python
        # store text
        self._text_per_page[self._current_page] = text
```

### 8.7.2 Paragraph extraction and disjoint set

Extracting characters of text and joining them together is already a hard problem.
But trying to find a `Paragraph` is even more complicated. To do so, `borb` first attempts to find lines of text.
This logic resides in the `SimpleLineOfTextExtraction` class.

Put simply, `SimpleLineOfTextExtraction` is notified of the same `Event` objects we discussed earlier.
It stores them and later uses a highly efficient datastructure to merge `Event` objects that together form a `LineOfText`.

This datastructure is a union-find datastructure (also known as a disjoint set).
A disjoint set is a data structure that stores a collection of disjoint (non-overlapping) sets. 
Equivalently, it stores a partition of a set into disjoint subsets. It provides operations for adding new sets, merging sets (replacing them by their union), and finding a representative member of a set. The last operation makes it possible to find out efficiently if any two elements are in the same or different sets. 

To perform a sequence of m addition, union, or find operations on a disjoint-set forest with n nodes requires total time `O(m*α(n))`, where `α(n)` is the extremely slow-growing inverse Ackermann function. 
Disjoint-set forests do not guarantee this performance on a per-operation basis. Individual union and find operations can take longer than a constant times α(n) time, but each operation causes the disjoint-set forest to adjust itself so that successive operations are faster. 
Disjoint-set forests are both asymptotically optimal and practically efficient. 

You can see this datastructure in action on lines 60 to 75 of `SimpleLineOfTextExtraction`:

```python
        for c0 in chunks_of_text_disjoint_set:
            for c1 in chunks_of_text_disjoint_set:
                if c0 == c1:
                    continue
                r0 = c0._baseline_bounding_box
                r1 = c1._baseline_bounding_box
                if r0.y != r1.y:
                    continue
                gap = max(r1.x - (r0.x + r0.width), r0.x - (r1.x + r1.width))
                space_gap = (
                    c0.get_space_character_width_estimate_in_user_space()
                    if r0.x < r1.x
                    else c1.get_space_character_width_estimate_in_user_space()
                )
                if gap < space_gap * Decimal(2):
                    chunks_of_text_disjoint_set.union(c0, c1)
```

Once the PDF has been reconsituted into `LineOfText` objects, it can be further aggregated into `Paragraph` objects.
This is done by the `SimpleParagraphExtraction` class. This class uses 2 parameters when deciding on when to merge `LineOfText` objects into a `Paragraph`.

- The horizontal overlap of two `LineOfText` objects
- The leading between two `LineOfText` objects

These may need to be tweaked for optimal results.

By hooking into this chain, you can build an `EventListener` that processes `Paragraph` objects (rather than having to deal with low-level instructions).

`borb` already contains such a class; `PDFToMP3`, which uses Google Text-to-Speech to store the spoken text of a `Paragraph` as an MP3. This class can optionally prefix all these spoken utterances with the coordinates of the `Paragraph` in a human-legible way.
This produces output such as: "first page, top right, An introduction to Python"

<div style="page-break-before: always;"></div>

## 8.8 Hyphenation

from wikipedia.org
> Syllabification (/sɪˌlæbɪfɪˈkeɪʃən/) or syllabication (/sɪˌlæbɪˈkeɪʃən/), also known as hyphenation, is the separation of a word into syllables, whether spoken, written or signed.
>
> The written separation into syllables is usually marked by a hyphen when using English orthography (e.g., syl-la-ble) and with a period when transcribing the actually spoken syllables in the International Phonetic Alphabet (IPA) (e.g., [ˈsɪ.lə.bᵊɫ]).
> 
> For presentation purposes, typographers may use an interpunct (Unicode character U+00B7, e.g., syl·la·ble), a special-purpose "hyphenation point" (U+2027, e.g., syl‧la‧ble), or a space (e.g., syl la ble).

At the end of a line, a word is separated in writing into parts, conventionally called "syllables", if it does not fit the line and if moving it to the next line would make the first line much shorter than the others. This can be a particular problem with very long words, and with narrow columns in newspapers.

### 5.8.1 The hyphenation problem

from wikipedia.org
> A hyphenation algorithm is a set of rules, especially one codified for implementation in a computer program, that decides at which points a word can be broken over two lines with a hyphen. For example, a hyphenation algorithm might decide that impeachment can be broken as impeach-ment or im-peachment but not impe-achment.
>
> One of the reasons for the complexity of the rules of word-breaking is that different "dialects" of English tend to differ on hyphenation[citation needed]: American English tends to work on sound, but British English tends to look to the origins of the word and then to sound. There are also a large number of exceptions, which further complicates matters.

And that's not even mentioning hyphenation in other languages.

### 8.8.2 A fast and scalable hyphenation algorithm

`borb` hyphenates text (on a `Paragraph`) if you pass it a `Hyphenation` object.
This object represents an instantiation of the aforementioned hyphenation algorithm.

The hyphenation algorithm is based on the [work of Franklin mark Liang](https://www.tug.org/docs/liang/liang-thesis.pdf), and works roughly as follows:

```
0.  input: the word 'w' to be hyphenated
1.  iterate over all possible split-positions (i) in the word w:
2.      prefix = w[0:i]
3.      suffix = w[i:]
4.      iterate over all possible suffixes of the prefix, and prefixes of the suffix:
5.          if a rule prefix-number-suffix matches:
6.              update that split position if the number is higher
7.  iterate over all split-positions (i) in the word w:
8.      if the value of the split-position is ODD:
9.          a hyphen is allowed at this position
```

The rules in aforementioned algorithm are language dependent, and are typically several thousands of rules poured into one file (e.g. `JSON`) which is loaded into a special datastructure (trie) which is optimized for this kind of lookup. 

As an example, let's look at the word "birmingham".

| b | . | i | . | r | . | m | . | i | . | n | . | g | . | h | . | a | . | m |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| b |   | i |   | r | 4 |   |   |   |   |   |   |   |   |   |   |   |   |   |
|   |   |   |   | r |   | m | 3 |   |   |   |   |   |   |   |   |   |   |   |
|   |   |   |   |   |   |   |   |   | 4 | n |   | g |   |   |   |   |   |   |
|   |   |   |   |   |   |   |   |   |   |   | 2 | g | h |   |   |   |   |   |
|   |   |   |   |   |   |   |   | i |   | n |   | g | 5 | h |   | a |   |   |
|   |   |   |   |   |   |   |   |   |   | n |   | g |   | h | 4 |   |   |   |
|   |   |   |   |   |   |   |   |   |   |   |   |   |   | h |   | a | 2 |   |
|   | 0 |   | 0 |   | 4 |   | 3 |   | 4 |   | 2 |   | 5 |   | 4 |   | 2 |   |

After having run this algorithm, we know that "Birmingham" can be hyphenated as "Birm-ing-ham", 
since those positions yield an odd max value.

This algorithm is rather labour-intensive, so rather than running it on every word (and inserting soft-hyphens for instance),
the algorithm is only run when needed.

Whenever the `Paragraph` is performing layout, it will do the following:

```
1. Split the text into words (call this ws)
2. keep track of all lines of text that make up the paragraph, call this lines_of_text
3. for each word (w) in ws:
4.      last_line_of_text = lines_of_text[-1] + <space> + w
5.      calculate the dimensions of last_line_of_text (r)
6.      if r would fall outside the bounding box given to the paragraph:
7.          if hyphenation is enabled for this paragraph:
8.              attempt to split w
9.              if prefix of w + "-" fits:
10.                 hyphenate the word there, switch to the next line, next line starts with suffix of w
11.             else:
12.                 switch to next line, next line start with w
13.         else:
14.             switch to next line, next line starts with w 
```

This ensures hyphenation is only called when needed (rather than on every word in the sentence).

### 8.8.3 Using hyphenation in `borb`

In the next example you'll be creating a `Document` with two `Paragraph` instances.
One `Paragraph` will have hyphenation enabled, the other will not.

```python
from decimal import Decimal

from borb.pdf.canvas.layout.hyphenation.hyphenation import Hyphenation
from borb.pdf.canvas.layout.page_layout.multi_column_layout import SingleColumnLayout
from borb.pdf.canvas.layout.page_layout.page_layout import PageLayout
from borb.pdf.canvas.layout.text.paragraph import Paragraph
from borb.pdf.document.document import Document
from borb.pdf.page.page import Page
from borb.pdf.pdf import PDF


def main():

    # Document
    d: Document = Document()

    # Page
    p: Page = Page()
    d.append_page(p)

    # PageLayout
    l: PageLayout = SingleColumnLayout(p)

    # Paragraph 1
    l.add(Paragraph("Without hyphenation", font="Helvetica-bold", font_size=Decimal(20)))
    l.add(Paragraph("""
                    Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
                    Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
                    when an unknown printer took a galley of type and scrambled it to make a type specimen book. 
                    It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. 
                    It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, 
                    and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.    
                    """))

    # Paragraph 2
    l.add(Paragraph("With en-us hyphenation", font="Helvetica-bold", font_size=Decimal(20)))
    l.add(Paragraph("""
                    Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
                    Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
                    when an unknown printer took a galley of type and scrambled it to make a type specimen book. 
                    It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. 
                    It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, 
                    and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.    
                    """, hyphenation=Hyphenation("en-us")))

    # write
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, d)


if __name__ == "__main__":
    main()

```

In the final PDF you can see the word "survived" was hyphenated as well as the word "essentially".

![enter image description here](chapter_008/img/borb_in_action_example_083.png)

<div style="page-break-before: always;"></div>


# 9 Showcases

In this chapter we'll build some practical PDF documents that are ready-to-use.
This chapter assumes you have a good working knowledge of all the basic `LayoutElement`  concepts.

<div style="page-break-before: always;"></div>

## 9.1 Building a sudoku puzzle

First let's define the representation of the sudoku.
This code does not need to be very high-performant, or solve a sudoku.
So for this example, representing a sudoku as a `str` will do fine.

```python
#!chapter_009/src/snippet_001.py
# represent the sudoku as a plaintext str
# every . represents an empty cell in the puzzle
# this is easier to debug/change
sudoku_str: str = """
 .  6  . | 8  .  3 | .  7  . 
 .  .  1 | .  .  . | .  6  9 
 7  .  . | .  .  . | .  .  5 
---------+---------+--------
 .  .  . | 9  .  . | .  1  . 
 .  .  . | .  .  . | .  .  4 
 .  .  5 | .  1  . | .  .  . 
---------+---------+--------
 5  4  . | .  8  . | .  .  7 
 .  .  . | 5  7  . | .  .  8 
 .  9  7 | 3  .  . | .  .  . 
"""

# process sudoku_str to remove everything that is not a number or dot
for c in "\t\n|+- ":
    sudoku_str = sudoku_str.replace(c, "")
```

Next we're going to build a `Document` containing the basic information.

```python
#!chapter_009/src/snippet_002.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import HexColor

from decimal import Decimal

# represent the sudoku as a plaintext str
# every . represents an empty cell in the puzzle
# this is easier to debug/change
sudoku_str: str = """
 .  6  . | 8  .  3 | .  7  . 
 .  .  1 | .  .  . | .  6  9 
 7  .  . | .  .  . | .  .  5 
---------+---------+--------
 .  .  . | 9  .  . | .  1  . 
 .  .  . | .  .  . | .  .  4 
 .  .  5 | .  1  . | .  .  . 
---------+---------+--------
 5  4  . | .  8  . | .  .  7 
 .  .  . | 5  7  . | .  .  8 
 .  9  7 | 3  .  . | .  .  . 
"""

# process sudoku_str to remove everything that is not a number or dot
for c in "\t\n|+- ":
    sudoku_str = sudoku_str.replace(c, "")


def main():

    # define theme color
    theme_color: Color = HexColor("f1cd2e")

    # create new Document
    doc: Document = Document()

    # create new Page
    page: Page = Page()
    doc.add_page(page)

    # set PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add title to the Document
    layout.add(
        Paragraph("Sudoku Puzzle", font_color=theme_color, font_size=Decimal(20))
    )

    # add the explanation of how to solve a sudoku
    layout.add(
        Paragraph(
            """
                    Sudoku is a logic-based, combinatorial number-placement puzzle. 
                    In classic sudoku, the objective is to fill a 9×9 grid with digits so that each column, each row, 
                    and each of the nine 3×3 subgrids that compose the grid contains all of the digits from 1 to 9. 
                    The puzzle setter provides a partially completed grid, which for a well-posed puzzle has a single solution.
                    """,
            font="Helvetica-Oblique",
        )
    )


if __name__ == "__main__":
    main()
```

We can render the sudoku in a `Document` by using a `FlexibleColumnWidthTable`

```python
#!chapter_009/src/snippet_003.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import HexColor
from borb.pdf import FlexibleColumnWidthTable
from borb.pdf import Table, TableCell
from borb.pdf import Alignment

from decimal import Decimal

# represent the sudoku as a plaintext str
# every . represents an empty cell in the puzzle
# this is easier to debug/change
sudoku_str: str = """
 .  6  . | 8  .  3 | .  7  . 
 .  .  1 | .  .  . | .  6  9 
 7  .  . | .  .  . | .  .  5 
---------+---------+--------
 .  .  . | 9  .  . | .  1  . 
 .  .  . | .  .  . | .  .  4 
 .  .  5 | .  1  . | .  .  . 
---------+---------+--------
 5  4  . | .  8  . | .  .  7 
 .  .  . | 5  7  . | .  .  8 
 .  9  7 | 3  .  . | .  .  . 
"""

# process sudoku_str to remove everything that is not a number or dot
for c in "\t\n|+- ":
    sudoku_str = sudoku_str.replace(c, "")


def main():

    # define theme color
    theme_color: Color = HexColor("f1cd2e")

    # create new Document
    doc: Document = Document()

    # create new Page
    page: Page = Page()
    doc.add_page(page)

    # set PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add title to the Document
    layout.add(
        Paragraph("Sudoku Puzzle", font_color=theme_color, font_size=Decimal(20))
    )

    # add the explanation of how to solve a sudoku
    layout.add(
        Paragraph(
            """
                    Sudoku is a logic-based, combinatorial number-placement puzzle. 
                    In classic sudoku, the objective is to fill a 9×9 grid with digits so that each column, each row, 
                    and each of the nine 3×3 subgrids that compose the grid contains all of the digits from 1 to 9. 
                    The puzzle setter provides a partially completed grid, which for a well-posed puzzle has a single solution.
                    """,
            font="Helvetica-Oblique",
        )
    )

    # represent the sudoku as a table
    s: Decimal = Decimal(20)
    t: Table = FlexibleColumnWidthTable(
        number_of_rows=9, number_of_columns=9, horizontal_alignment=Alignment.CENTERED
    )
    for i in range(0, 81):
        r: int = int(i / 9)
        c: int = i % 9
        background_color: Color = HexColor("ffffff")
        if r in [0, 1, 2, 6, 7, 8] and c in [0, 1, 2, 6, 7, 8]:
            background_color = theme_color
        if r in [3, 4, 5] and c in [3, 4, 5]:
            background_color = theme_color
        if sudoku_str[i] == ".":
            t.add(
                TableCell(
                    Paragraph(" "),
                    preferred_width=s,
                    preferred_height=s,
                    background_color=background_color,
                )
            )
        else:
            t.add(
                TableCell(
                    Paragraph(sudoku_str[i], text_alignment=Alignment.CENTERED),
                    preferred_width=s,
                    preferred_height=s,
                    background_color=background_color,
                )
            )
    t.set_padding_on_all_cells(Decimal(5), Decimal(5), Decimal(5), Decimal(5))
    layout.add(t)


if __name__ == "__main__":
    main()
```

Finally, we can store the `Document`

```python
#!chapter_009/src/snippet_004.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import HexColor
from borb.pdf import FlexibleColumnWidthTable
from borb.pdf import Table, TableCell
from borb.pdf import Alignment

from decimal import Decimal

# represent the sudoku as a plaintext str
# every . represents an empty cell in the puzzle
# this is easier to debug/change
sudoku_str: str = """
 .  6  . | 8  .  3 | .  7  . 
 .  .  1 | .  .  . | .  6  9 
 7  .  . | .  .  . | .  .  5 
---------+---------+--------
 .  .  . | 9  .  . | .  1  . 
 .  .  . | .  .  . | .  .  4 
 .  .  5 | .  1  . | .  .  . 
---------+---------+--------
 5  4  . | .  8  . | .  .  7 
 .  .  . | 5  7  . | .  .  8 
 .  9  7 | 3  .  . | .  .  . 
"""

# process sudoku_str to remove everything that is not a number or dot
for c in "\t\n|+- ":
    sudoku_str = sudoku_str.replace(c, "")


def main():

    # define theme color
    theme_color: Color = HexColor("f1cd2e")

    # create new Document
    doc: Document = Document()

    # create new Page
    page: Page = Page()
    doc.add_page(page)

    # set PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add title to the Document
    layout.add(
        Paragraph("Sudoku Puzzle", font_color=theme_color, font_size=Decimal(20))
    )

    # add the explanation of how to solve a sudoku
    layout.add(
        Paragraph(
            """
                    Sudoku is a logic-based, combinatorial number-placement puzzle. 
                    In classic sudoku, the objective is to fill a 9×9 grid with digits so that each column, each row, 
                    and each of the nine 3×3 subgrids that compose the grid contains all of the digits from 1 to 9. 
                    The puzzle setter provides a partially completed grid, which for a well-posed puzzle has a single solution.
                    """,
            font="Helvetica-Oblique",
        )
    )

    # represent the sudoku as a table
    s: Decimal = Decimal(20)
    t: Table = FlexibleColumnWidthTable(
        number_of_rows=9, number_of_columns=9, horizontal_alignment=Alignment.CENTERED
    )
    for i in range(0, 81):
        r: int = int(i / 9)
        c: int = i % 9
        background_color: Color = HexColor("ffffff")
        if r in [0, 1, 2, 6, 7, 8] and c in [0, 1, 2, 6, 7, 8]:
            background_color = theme_color
        if r in [3, 4, 5] and c in [3, 4, 5]:
            background_color = theme_color
        if sudoku_str[i] == ".":
            t.add(
                TableCell(
                    Paragraph(" "),
                    preferred_width=s,
                    preferred_height=s,
                    background_color=background_color,
                )
            )
        else:
            t.add(
                TableCell(
                    Paragraph(sudoku_str[i], text_alignment=Alignment.CENTERED),
                    preferred_width=s,
                    preferred_height=s,
                    background_color=background_color,
                )
            )
    t.set_padding_on_all_cells(Decimal(5), Decimal(5), Decimal(5), Decimal(5))
    layout.add(t)

    # output
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)


if __name__ == "__main__":
    main()
```

That should yield a wonderful little puzzle in a PDF, like so:

![enter image description here](chapter_009/img/snippet_004.png)

## 9.2 Building a realistic invoice

```python
#!chapter_009/src/snippet_005.py
from borb.pdf import Document
from borb.pdf import Page


def main():

    # Create document
    pdf = Document()

    # Add page
    page = Page()
    pdf.add_page(page)


if __name__ == "__main__":
    main()
```

Since we don't want to deal with calculating coordinates - we can delegate this to a `PageLayout` which manages all of the content and its positions:

```python
#!chapter_009/src/snippet_006.py
from borb.pdf import Document
from borb.pdf import Page

# New imports
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from decimal import Decimal


def main():

    # Create document
    pdf = Document()

    # Add page
    page = Page()
    pdf.add_page(page)

    # create PageLayout
    page_layout: PageLayout = SingleColumnLayout(page)
    page_layout.vertical_margin = page.get_page_info().get_height() * Decimal(0.02)


if __name__ == "__main__":
    main()
```

Here, we're using a `SingleColumnLayout` since all of the content should be in a single column - we won't have a left and right side of the invoice. 
We're also making the vertical margin smaller here. The default value is to trim the top 10% of the page height as the margin, and we're reducing it down to 2%, since we'll want to use this space for the company logo/name.

Speaking of which, let's add the company logo to the layout:

```python
#!chapter_009/src/snippet_007.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from decimal import Decimal

# New imports
from borb.pdf import Image


def main():

    # Create document
    pdf = Document()

    # Add page
    page = Page()
    pdf.add_page(page)

    # create PageLayout
    page_layout: PageLayout = SingleColumnLayout(page)
    page_layout.vertical_margin = page.get_page_info().get_height() * Decimal(0.02)

    page_layout.add(
        Image(
            "https://s3.stackabuse.com/media/articles/creating-an-invoice-in-python-with-ptext-1.png",
            width=Decimal(128),
            height=Decimal(128),
        )
    )


if __name__ == "__main__":
    main()
```

Here, we're adding an element to the layout - an `Image`. Through its constructor, we're adding a URL pointing to the image resource and setting its `width` and `height`.

Beneath the image, we'll want to add our imaginary company info (name, address, website, phone) as well as the invoice information (invoice number, date, due date).

A common format for brevity (which incidentally also makes the code cleaner) is to use a table to store invoice data. Let's create a separate helper method to build the invoice information in a table, which we can then use to simply add a table to the invoice in our main method:

```python
#!chapter_009/src/snippet_008.py
# New imports
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Alignment
from datetime import datetime
import random


def _build_invoice_information():
    table_001 = FixedColumnWidthTable(number_of_rows=5, number_of_columns=3)

    table_001.add(Paragraph("[Street Address]"))
    table_001.add(
        Paragraph("Date", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT)
    )
    now = datetime.now()
    table_001.add(Paragraph("%d/%d/%d" % (now.day, now.month, now.year)))

    table_001.add(Paragraph("[City, State, ZIP Code]"))
    table_001.add(
        Paragraph(
            "Invoice #", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
        )
    )
    table_001.add(Paragraph("%d" % random.randint(1000, 10000)))

    table_001.add(Paragraph("[Phone]"))
    table_001.add(
        Paragraph(
            "Due Date", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
        )
    )
    table_001.add(Paragraph("%d/%d/%d" % (now.day, now.month, now.year)))

    table_001.add(Paragraph("[Email Address]"))
    table_001.add(Paragraph(" "))
    table_001.add(Paragraph(" "))

    table_001.add(Paragraph("[Company Website]"))
    table_001.add(Paragraph(" "))
    table_001.add(Paragraph(" "))

    table_001.set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
    table_001.no_borders()
    return table_001
```

Here, we're making a simple `Table` with 5 rows and 3 columns. The rows correspond to the street address, city/state, phone, email address and company website. Each row will have `0..3` values (columns). Each text element is added as a `Paragraph`, which we've aligned to the right via `Alignment.RIGHT`, and accept styling arguments such as font.

Finally, we've added padding to all the cells to make sure we don't place the text awkwardly near the confounds of the cells.

Now, back in our main method, we can call `_build_invoice_information()` to populate a table and add it to our layout:

```python
#!chapter_009/src/snippet_009.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from decimal import Decimal
from borb.pdf import Image
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Alignment
from datetime import datetime
import random


def _build_invoice_information():
    table_001 = FixedColumnWidthTable(number_of_rows=5, number_of_columns=3)

    table_001.add(Paragraph("[Street Address]"))
    table_001.add(
        Paragraph("Date", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT)
    )
    now = datetime.now()
    table_001.add(Paragraph("%d/%d/%d" % (now.day, now.month, now.year)))

    table_001.add(Paragraph("[City, State, ZIP Code]"))
    table_001.add(
        Paragraph(
            "Invoice #", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
        )
    )
    table_001.add(Paragraph("%d" % random.randint(1000, 10000)))

    table_001.add(Paragraph("[Phone]"))
    table_001.add(
        Paragraph(
            "Due Date", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
        )
    )
    table_001.add(Paragraph("%d/%d/%d" % (now.day, now.month, now.year)))

    table_001.add(Paragraph("[Email Address]"))
    table_001.add(Paragraph(" "))
    table_001.add(Paragraph(" "))

    table_001.add(Paragraph("[Company Website]"))
    table_001.add(Paragraph(" "))
    table_001.add(Paragraph(" "))

    table_001.set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
    table_001.no_borders()
    return table_001


def main():
    # Create document
    pdf = Document()

    # Add page
    page = Page()
    pdf.add_page(page)

    # create PageLayout
    page_layout: PageLayout = SingleColumnLayout(page)
    page_layout.vertical_margin = page.get_page_info().get_height() * Decimal(0.02)

    page_layout.add(
        Image(
            "https://s3.stackabuse.com/media/articles/creating-an-invoice-in-python-with-ptext-1.png",
            width=Decimal(64),
            height=Decimal(64),
        )
    )

    # Invoice information table
    page_layout.add(_build_invoice_information())

    # Empty paragraph for spacing
    page_layout.add(Paragraph(" "))


if __name__ == "__main__":
    main()
```

Great! Now we'll want to add the billing and shipping information as well. It'll conveniently be placed in a table, just like the company information. For brevity's sake, we'll also opt to make a separate helper function to build this info, and then we can simply add it in our main method:

```python
#!chapter_009/src/snippet_010.py
# New imports
from borb.pdf import HexColor, X11Color


def _build_billing_and_shipping_information():
    table_001 = Table(number_of_rows=6, number_of_columns=2)
    table_001.add(
        Paragraph(
            "BILL TO",
            background_color=HexColor("263238"),
            font_color=X11Color("White"),
        )
    )
    table_001.add(
        Paragraph(
            "SHIP TO",
            background_color=HexColor("263238"),
            font_color=X11Color("White"),
        )
    )
    table_001.add(Paragraph("[Recipient Name]"))  # BILLING
    table_001.add(Paragraph("[Recipient Name]"))  # SHIPPING
    table_001.add(Paragraph("[Company Name]"))  # BILLING
    table_001.add(Paragraph("[Company Name]"))  # SHIPPING
    table_001.add(Paragraph("[Street Address]"))  # BILLING
    table_001.add(Paragraph("[Street Address]"))  # SHIPPING
    table_001.add(Paragraph("[City, State, ZIP Code]"))  # BILLING
    table_001.add(Paragraph("[City, State, ZIP Code]"))  # SHIPPING
    table_001.add(Paragraph("[Phone]"))  # BILLING
    table_001.add(Paragraph("[Phone]"))  # SHIPPING
    table_001.set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
    table_001.no_borders()
    return table_001
```

Let's call this in the main method as well:

```python
#!chapter_009/src/snippet_011.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from decimal import Decimal
from borb.pdf import Image
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Alignment
from borb.pdf import HexColor, X11Color
from datetime import datetime
import random


def _build_invoice_information():
    table_001 = FixedColumnWidthTable(number_of_rows=5, number_of_columns=3)

    table_001.add(Paragraph("[Street Address]"))
    table_001.add(
        Paragraph("Date", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT)
    )
    now = datetime.now()
    table_001.add(Paragraph("%d/%d/%d" % (now.day, now.month, now.year)))

    table_001.add(Paragraph("[City, State, ZIP Code]"))
    table_001.add(
        Paragraph(
            "Invoice #", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
        )
    )
    table_001.add(Paragraph("%d" % random.randint(1000, 10000)))

    table_001.add(Paragraph("[Phone]"))
    table_001.add(
        Paragraph(
            "Due Date", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
        )
    )
    table_001.add(Paragraph("%d/%d/%d" % (now.day, now.month, now.year)))

    table_001.add(Paragraph("[Email Address]"))
    table_001.add(Paragraph(" "))
    table_001.add(Paragraph(" "))

    table_001.add(Paragraph("[Company Website]"))
    table_001.add(Paragraph(" "))
    table_001.add(Paragraph(" "))

    table_001.set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
    table_001.no_borders()
    return table_001


def _build_billing_and_shipping_information():
    table_001 = FixedColumnWidthTable(number_of_rows=6, number_of_columns=2)
    table_001.add(
        Paragraph(
            "BILL TO",
            background_color=HexColor("263238"),
            font_color=X11Color("White"),
        )
    )
    table_001.add(
        Paragraph(
            "SHIP TO",
            background_color=HexColor("263238"),
            font_color=X11Color("White"),
        )
    )
    table_001.add(Paragraph("[Recipient Name]"))  # BILLING
    table_001.add(Paragraph("[Recipient Name]"))  # SHIPPING
    table_001.add(Paragraph("[Company Name]"))  # BILLING
    table_001.add(Paragraph("[Company Name]"))  # SHIPPING
    table_001.add(Paragraph("[Street Address]"))  # BILLING
    table_001.add(Paragraph("[Street Address]"))  # SHIPPING
    table_001.add(Paragraph("[City, State, ZIP Code]"))  # BILLING
    table_001.add(Paragraph("[City, State, ZIP Code]"))  # SHIPPING
    table_001.add(Paragraph("[Phone]"))  # BILLING
    table_001.add(Paragraph("[Phone]"))  # SHIPPING
    table_001.set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
    table_001.no_borders()
    return table_001


def main():
    # Create document
    pdf = Document()

    # Add page
    page = Page()
    pdf.add_page(page)

    # create PageLayout
    page_layout: PageLayout = SingleColumnLayout(page)
    page_layout.vertical_margin = page.get_page_info().get_height() * Decimal(0.02)

    page_layout.add(
        Image(
            "https://s3.stackabuse.com/media/articles/creating-an-invoice-in-python-with-ptext-1.png",
            width=Decimal(64),
            height=Decimal(64),
        )
    )

    # Invoice information table
    page_layout.add(_build_invoice_information())

    # Empty paragraph for spacing
    page_layout.add(Paragraph(" "))

    # Billing and shipping information table
    page_layout.add(_build_billing_and_shipping_information())


if __name__ == "__main__":
    main()
```

With our basic information sorted out (company info and billing/shipping info) - we'll want to add an itemized description. These will be the goods/services that our supposed company offered to someone and are also typically done in a table-like fashion beneath the information we've already added.

Again, let's create a helper function that generates a table and populates it with data, which we can simply add to our layout later on.

We'll start by defining a Product class to represent a sold product. In practice, you'd substitute the hard-coded strings related to the subtotal, taxes and total prices with calculations of the actual prices - though, this heavily depends on the underlying implementation of your Product models, so we've added a stand-in for abstraction.

```python
#!chapter_009/src/snippet_012.py
class Product:
    """
    This class represents a purchased product
    """

    def __init__(self, name: str, quantity: int, price_per_sku: float):
        self.name: str = name
        assert quantity >= 0
        self.quantity: int = quantity
        assert price_per_sku >= 0
        self.price_per_sku: float = price_per_sku
```

Now we can build a method `_build_itemized_description_table` that will render these products and their prices to the PDF:

```python
#!chapter_009/src/snippet_013.py
# New Imports
from borb.pdf import TableCell
import typing


def _build_itemized_description_table(products: typing.List["Product"] = []):
    """
    This function builds a Table containing itemized billing information
    :param:     products
    :return:    a Table containing itemized billing information
    """
    table_001 = FixedColumnWidthTable(number_of_rows=15, number_of_columns=4)
    for h in ["DESCRIPTION", "QTY", "UNIT PRICE", "AMOUNT"]:
        table_001.add(
            TableCell(
                Paragraph(h, font_color=X11Color("White")),
                background_color=HexColor("0b3954"),
            )
        )

    odd_color = HexColor("BBBBBB")
    even_color = HexColor("FFFFFF")
    for row_number, item in enumerate(products):
        c = even_color if row_number % 2 == 0 else odd_color
        table_001.add(TableCell(Paragraph(item.name), background_color=c))
        table_001.add(TableCell(Paragraph(str(item.quantity)), background_color=c))
        table_001.add(
            TableCell(Paragraph("$ " + str(item.price_per_sku)), background_color=c)
        )
        table_001.add(
            TableCell(
                Paragraph("$ " + str(item.quantity * item.price_per_sku)),
                background_color=c,
            )
        )

    # Optionally add some empty rows to have a fixed number of rows for styling purposes
    for row_number in range(len(products), 10):
        c = even_color if row_number % 2 == 0 else odd_color
        for _ in range(0, 4):
            table_001.add(TableCell(Paragraph(" "), background_color=c))

    # subtotal
    subtotal: float = sum([x.price_per_sku * x.quantity for x in products])
    table_001.add(
        TableCell(
            Paragraph(
                "Subtotal",
                font="Helvetica-Bold",
                horizontal_alignment=Alignment.RIGHT,
            ),
            col_span=3,
        )
    )
    table_001.add(
        TableCell(Paragraph("$ 1,180.00", horizontal_alignment=Alignment.RIGHT))
    )

    # discounts
    table_001.add(
        TableCell(
            Paragraph(
                "Discounts",
                font="Helvetica-Bold",
                horizontal_alignment=Alignment.RIGHT,
            ),
            col_span=3,
        )
    )
    table_001.add(TableCell(Paragraph("$ 0.00", horizontal_alignment=Alignment.RIGHT)))

    # taxes
    taxes: float = subtotal * 0.06
    table_001.add(
        TableCell(
            Paragraph(
                "Taxes", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
            ),
            col_span=3,
        )
    )
    table_001.add(
        TableCell(Paragraph("$ " + str(taxes), horizontal_alignment=Alignment.RIGHT))
    )

    # total
    total: float = subtotal + taxes
    table_001.add(
        TableCell(
            Paragraph(
                "Total", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
            ),
            col_span=3,
        )
    )
    table_001.add(
        TableCell(Paragraph("$ " + str(total), horizontal_alignment=Alignment.RIGHT))
    )
    table_001.set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
    table_001.no_borders()
    return table_001
```

Let's call this method with some dummy `Product` items:

```python
#!chapter_009/src/snippet_014.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from decimal import Decimal
from borb.pdf import Image
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Alignment
from borb.pdf import HexColor, X11Color
from borb.pdf import TableCell
from datetime import datetime
import random
import typing


class Product:
    """
    This class represents a purchased product
    """

    def __init__(self, name: str, quantity: int, price_per_sku: float):
        self.name: str = name
        assert quantity >= 0
        self.quantity: int = quantity
        assert price_per_sku >= 0
        self.price_per_sku: float = price_per_sku


def _build_invoice_information():
    table_001 = FixedColumnWidthTable(number_of_rows=5, number_of_columns=3)

    table_001.add(Paragraph("[Street Address]"))
    table_001.add(
        Paragraph("Date", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT)
    )
    now = datetime.now()
    table_001.add(Paragraph("%d/%d/%d" % (now.day, now.month, now.year)))

    table_001.add(Paragraph("[City, State, ZIP Code]"))
    table_001.add(
        Paragraph(
            "Invoice #", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
        )
    )
    table_001.add(Paragraph("%d" % random.randint(1000, 10000)))

    table_001.add(Paragraph("[Phone]"))
    table_001.add(
        Paragraph(
            "Due Date", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
        )
    )
    table_001.add(Paragraph("%d/%d/%d" % (now.day, now.month, now.year)))

    table_001.add(Paragraph("[Email Address]"))
    table_001.add(Paragraph(" "))
    table_001.add(Paragraph(" "))

    table_001.add(Paragraph("[Company Website]"))
    table_001.add(Paragraph(" "))
    table_001.add(Paragraph(" "))

    table_001.set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
    table_001.no_borders()
    return table_001


def _build_billing_and_shipping_information():
    table_001 = FixedColumnWidthTable(number_of_rows=6, number_of_columns=2)
    table_001.add(
        Paragraph(
            "BILL TO",
            background_color=HexColor("263238"),
            font_color=X11Color("White"),
        )
    )
    table_001.add(
        Paragraph(
            "SHIP TO",
            background_color=HexColor("263238"),
            font_color=X11Color("White"),
        )
    )
    table_001.add(Paragraph("[Recipient Name]"))  # BILLING
    table_001.add(Paragraph("[Recipient Name]"))  # SHIPPING
    table_001.add(Paragraph("[Company Name]"))  # BILLING
    table_001.add(Paragraph("[Company Name]"))  # SHIPPING
    table_001.add(Paragraph("[Street Address]"))  # BILLING
    table_001.add(Paragraph("[Street Address]"))  # SHIPPING
    table_001.add(Paragraph("[City, State, ZIP Code]"))  # BILLING
    table_001.add(Paragraph("[City, State, ZIP Code]"))  # SHIPPING
    table_001.add(Paragraph("[Phone]"))  # BILLING
    table_001.add(Paragraph("[Phone]"))  # SHIPPING
    table_001.set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
    table_001.no_borders()
    return table_001


def _build_itemized_description_table(products: typing.List[Product] = []):
    """
    This function builds a Table containing itemized billing information
    :param:     products
    :return:    a Table containing itemized billing information
    """
    table_001 = FixedColumnWidthTable(number_of_rows=15, number_of_columns=4)
    for h in ["DESCRIPTION", "QTY", "UNIT PRICE", "AMOUNT"]:
        table_001.add(
            TableCell(
                Paragraph(h, font_color=X11Color("White")),
                background_color=HexColor("0b3954"),
            )
        )

    odd_color = HexColor("BBBBBB")
    even_color = HexColor("FFFFFF")
    for row_number, item in enumerate(products):
        c = even_color if row_number % 2 == 0 else odd_color
        table_001.add(TableCell(Paragraph(item.name), background_color=c))
        table_001.add(TableCell(Paragraph(str(item.quantity)), background_color=c))
        table_001.add(
            TableCell(Paragraph("$ " + str(item.price_per_sku)), background_color=c)
        )
        table_001.add(
            TableCell(
                Paragraph("$ " + str(item.quantity * item.price_per_sku)),
                background_color=c,
            )
        )

    # Optionally add some empty rows to have a fixed number of rows for styling purposes
    for row_number in range(len(products), 10):
        c = even_color if row_number % 2 == 0 else odd_color
        for _ in range(0, 4):
            table_001.add(TableCell(Paragraph(" "), background_color=c))

    # subtotal
    subtotal: float = sum([x.price_per_sku * x.quantity for x in products])
    table_001.add(
        TableCell(
            Paragraph(
                "Subtotal",
                font="Helvetica-Bold",
                horizontal_alignment=Alignment.RIGHT,
            ),
            col_span=3,
        )
    )
    table_001.add(
        TableCell(Paragraph("$ 1,180.00", horizontal_alignment=Alignment.RIGHT))
    )

    # discounts
    table_001.add(
        TableCell(
            Paragraph(
                "Discounts",
                font="Helvetica-Bold",
                horizontal_alignment=Alignment.RIGHT,
            ),
            col_span=3,
        )
    )
    table_001.add(TableCell(Paragraph("$ 0.00", horizontal_alignment=Alignment.RIGHT)))

    # taxes
    taxes: float = subtotal * 0.06
    table_001.add(
        TableCell(
            Paragraph(
                "Taxes", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
            ),
            col_span=3,
        )
    )
    table_001.add(
        TableCell(Paragraph("$ " + str(taxes), horizontal_alignment=Alignment.RIGHT))
    )

    # total
    total: float = subtotal + taxes
    table_001.add(
        TableCell(
            Paragraph(
                "Total", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
            ),
            col_span=3,
        )
    )
    table_001.add(
        TableCell(Paragraph("$ " + str(total), horizontal_alignment=Alignment.RIGHT))
    )
    table_001.set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
    table_001.no_borders()
    return table_001


def main():
    # Create document
    pdf = Document()

    # Add page
    page = Page()
    pdf.add_page(page)

    # create PageLayout
    page_layout: PageLayout = SingleColumnLayout(page)
    page_layout.vertical_margin = page.get_page_info().get_height() * Decimal(0.02)

    page_layout.add(
        Image(
            "https://s3.stackabuse.com/media/articles/creating-an-invoice-in-python-with-ptext-1.png",
            width=Decimal(64),
            height=Decimal(64),
        )
    )

    # Invoice information table
    page_layout.add(_build_invoice_information())

    # Empty paragraph for spacing
    page_layout.add(Paragraph(" "))

    # Billing and shipping information table
    page_layout.add(_build_billing_and_shipping_information())

    # Empty paragraph for spacing
    page_layout.add(Paragraph(" "))

    # Itemized description
    page_layout.add(
        _build_itemized_description_table(
            [
                Product("Product 1", 2, 50),
                Product("Product 2", 4, 60),
                Product("Labor", 14, 60),
            ]
        )
    )


if __name__ == "__main__":
    main()
```

Finally, you can store the PDF to disk

```python
#!chapter_009/src/snippet_015.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from decimal import Decimal
from borb.pdf import Image
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Paragraph
from borb.pdf import Alignment
from borb.pdf import HexColor, X11Color
from borb.pdf import TableCell
from borb.pdf import PDF

from datetime import datetime
import random
import typing


class Product:
    """
    This class represents a purchased product
    """

    def __init__(self, name: str, quantity: int, price_per_sku: float):
        self.name: str = name
        assert quantity >= 0
        self.quantity: int = quantity
        assert price_per_sku >= 0
        self.price_per_sku: float = price_per_sku


def _build_invoice_information():
    table_001 = FixedColumnWidthTable(number_of_rows=5, number_of_columns=3)

    table_001.add(Paragraph("[Street Address]"))
    table_001.add(
        Paragraph("Date", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT)
    )
    now = datetime.now()
    table_001.add(Paragraph("%d/%d/%d" % (now.day, now.month, now.year)))

    table_001.add(Paragraph("[City, State, ZIP Code]"))
    table_001.add(
        Paragraph(
            "Invoice #", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
        )
    )
    table_001.add(Paragraph("%d" % random.randint(1000, 10000)))

    table_001.add(Paragraph("[Phone]"))
    table_001.add(
        Paragraph(
            "Due Date", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
        )
    )
    table_001.add(Paragraph("%d/%d/%d" % (now.day, now.month, now.year)))

    table_001.add(Paragraph("[Email Address]"))
    table_001.add(Paragraph(" "))
    table_001.add(Paragraph(" "))

    table_001.add(Paragraph("[Company Website]"))
    table_001.add(Paragraph(" "))
    table_001.add(Paragraph(" "))

    table_001.set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
    table_001.no_borders()
    return table_001


def _build_billing_and_shipping_information():
    table_001 = FixedColumnWidthTable(number_of_rows=6, number_of_columns=2)
    table_001.add(
        Paragraph(
            "BILL TO",
            background_color=HexColor("263238"),
            font_color=X11Color("White"),
        )
    )
    table_001.add(
        Paragraph(
            "SHIP TO",
            background_color=HexColor("263238"),
            font_color=X11Color("White"),
        )
    )
    table_001.add(Paragraph("[Recipient Name]"))  # BILLING
    table_001.add(Paragraph("[Recipient Name]"))  # SHIPPING
    table_001.add(Paragraph("[Company Name]"))  # BILLING
    table_001.add(Paragraph("[Company Name]"))  # SHIPPING
    table_001.add(Paragraph("[Street Address]"))  # BILLING
    table_001.add(Paragraph("[Street Address]"))  # SHIPPING
    table_001.add(Paragraph("[City, State, ZIP Code]"))  # BILLING
    table_001.add(Paragraph("[City, State, ZIP Code]"))  # SHIPPING
    table_001.add(Paragraph("[Phone]"))  # BILLING
    table_001.add(Paragraph("[Phone]"))  # SHIPPING
    table_001.set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
    table_001.no_borders()
    return table_001


def _build_itemized_description_table(products: typing.List[Product] = []):
    """
    This function builds a Table containing itemized billing information
    :param:     products
    :return:    a Table containing itemized billing information
    """
    table_001 = FixedColumnWidthTable(number_of_rows=15, number_of_columns=4)
    for h in ["DESCRIPTION", "QTY", "UNIT PRICE", "AMOUNT"]:
        table_001.add(
            TableCell(
                Paragraph(h, font_color=X11Color("White")),
                background_color=HexColor("0b3954"),
            )
        )

    odd_color = HexColor("BBBBBB")
    even_color = HexColor("FFFFFF")
    for row_number, item in enumerate(products):
        c = even_color if row_number % 2 == 0 else odd_color
        table_001.add(TableCell(Paragraph(item.name), background_color=c))
        table_001.add(TableCell(Paragraph(str(item.quantity)), background_color=c))
        table_001.add(
            TableCell(Paragraph("$ " + str(item.price_per_sku)), background_color=c)
        )
        table_001.add(
            TableCell(
                Paragraph("$ " + str(item.quantity * item.price_per_sku)),
                background_color=c,
            )
        )

    # Optionally add some empty rows to have a fixed number of rows for styling purposes
    for row_number in range(len(products), 10):
        c = even_color if row_number % 2 == 0 else odd_color
        for _ in range(0, 4):
            table_001.add(TableCell(Paragraph(" "), background_color=c))

    # subtotal
    subtotal: float = sum([x.price_per_sku * x.quantity for x in products])
    table_001.add(
        TableCell(
            Paragraph(
                "Subtotal",
                font="Helvetica-Bold",
                horizontal_alignment=Alignment.RIGHT,
            ),
            col_span=3,
        )
    )
    table_001.add(
        TableCell(Paragraph("$ 1,180.00", horizontal_alignment=Alignment.RIGHT))
    )

    # discounts
    table_001.add(
        TableCell(
            Paragraph(
                "Discounts",
                font="Helvetica-Bold",
                horizontal_alignment=Alignment.RIGHT,
            ),
            col_span=3,
        )
    )
    table_001.add(TableCell(Paragraph("$ 0.00", horizontal_alignment=Alignment.RIGHT)))

    # taxes
    taxes: float = subtotal * 0.06
    table_001.add(
        TableCell(
            Paragraph(
                "Taxes", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
            ),
            col_span=3,
        )
    )
    table_001.add(
        TableCell(Paragraph("$ " + str(taxes), horizontal_alignment=Alignment.RIGHT))
    )

    # total
    total: float = subtotal + taxes
    table_001.add(
        TableCell(
            Paragraph(
                "Total", font="Helvetica-Bold", horizontal_alignment=Alignment.RIGHT
            ),
            col_span=3,
        )
    )
    table_001.add(
        TableCell(Paragraph("$ " + str(total), horizontal_alignment=Alignment.RIGHT))
    )
    table_001.set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))
    table_001.no_borders()
    return table_001


def main():
    # Create document
    pdf = Document()

    # Add page
    page = Page()
    pdf.add_page(page)

    # create PageLayout
    page_layout: PageLayout = SingleColumnLayout(page)
    page_layout.vertical_margin = page.get_page_info().get_height() * Decimal(0.02)

    page_layout.add(
        Image(
            "https://s3.stackabuse.com/media/articles/creating-an-invoice-in-python-with-ptext-1.png",
            width=Decimal(64),
            height=Decimal(64),
        )
    )

    # Invoice information table
    page_layout.add(_build_invoice_information())

    # Empty paragraph for spacing
    page_layout.add(Paragraph(" "))

    # Billing and shipping information table
    page_layout.add(_build_billing_and_shipping_information())

    # Empty paragraph for spacing
    page_layout.add(Paragraph(" "))

    # Itemized description
    page_layout.add(
        _build_itemized_description_table(
            [
                Product("Product 1", 2, 50),
                Product("Product 2", 4, 60),
                Product("Labor", 14, 60),
            ]
        )
    )

    # store
    with open("output.pdf", "wb") as out_file_handle:
        PDF.dumps(out_file_handle, pdf)


if __name__ == "__main__":
    main()
```

The final PDF should look somewhat like this:

![enter image description here](chapter_009/img/snippet_015.png)

## 9.3 Creating a stunning flyer

These are the steps to creating a PDF document using borb:

- Create an empty `Document`
- Create an empty `Page`
- Append the `Page` to the `Document`
- Set a `PageLayout` to handle the flow of content (we're using a `SingleColumnLayout` here)
- Add content (not shown here)
- Write the PDF to disk (not shown here)

```python
#!chapter_009/src/snippet_016.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout


def main():
    # create empty Document
    pdf = Document()

    # create empty Page
    page = Page()

    # add Page to Document
    pdf.add_page(page)

    # create PageLayout
    layout: PageLayout = SingleColumnLayout(page)


if __name__ == "__main__":
    main()
```

We'd like to add some geometric artwork to our flyer in the upper right corner. We're going to write a separate method to do that. Then we can later re-use this method (for instance on every `Page` in the `Document`).

```python
#!chapter_009/src/snippet_017.py
# new imports
from borb.pdf import ConnectedShape
from decimal import Decimal
from borb.pdf import Page
from borb.pdf import HexColor, X11Color
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf.page.page_size import PageSize
import typing
import random


def add_gray_artwork_to_upper_right_corner(page: Page) -> None:
    """
    This method will add a gray artwork of squares and triangles in the upper right corner
    of the given Page
    """

    # define a list of gray colors
    grays: typing.List[HexColor] = [
        HexColor("A9A9A9"),
        HexColor("D3D3D3"),
        HexColor("DCDCDC"),
        HexColor("E0E0E0"),
        HexColor("E8E8E8"),
        HexColor("F0F0F0"),
    ]

    # we're going to use the size of the page later on,
    # so perhaps it's a good idea to retrieve it now
    ps: typing.Tuple[Decimal, Decimal] = PageSize.A4_PORTRAIT.value

    # now we'll write N triangles in the upper right corner
    # we'll later fill the remaining space with squares
    N: int = 4
    M: Decimal = Decimal(32)
    for i in range(0, N):
        x: Decimal = ps[0] - N * M + i * M
        y: Decimal = ps[1] - (i + 1) * M
        rg: HexColor = random.choice(grays)
        ConnectedShape(
            points=[(x + M, y), (x + M, y + M), (x, y + M)],
            stroke_color=rg,
            fill_color=rg,
        ).paint(page, Rectangle(x, y, M, M))

    # now we can fill up the remaining space with squares
    for i in range(0, N - 1):
        for j in range(0, N - 1):
            if j > i:
                continue
            x: Decimal = ps[0] - (N - 1) * M + i * M
            y: Decimal = ps[1] - (j + 1) * M
            rg: HexColor = random.choice(grays)
            ConnectedShape(
                points=[(x, y), (x + M, y), (x + M, y + M), (x, y + M)],
                stroke_color=rg,
                fill_color=rg,
            ).paint(page, Rectangle(x, y, M, M))
```

Now that we've defined this method, we can call it in the main body of our script to add the artwork to the PDF.

```python
#!chapter_009/src/snippet_018.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import ConnectedShape
from decimal import Decimal
from borb.pdf import HexColor, X11Color
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf.page.page_size import PageSize
import typing
import random


def add_gray_artwork_to_upper_right_corner(page: Page) -> None:
    """
    This method will add a gray artwork of squares and triangles in the upper right corner
    of the given Page
    """

    # define a list of gray colors
    grays: typing.List[HexColor] = [
        HexColor("A9A9A9"),
        HexColor("D3D3D3"),
        HexColor("DCDCDC"),
        HexColor("E0E0E0"),
        HexColor("E8E8E8"),
        HexColor("F0F0F0"),
    ]

    # we're going to use the size of the page later on,
    # so perhaps it's a good idea to retrieve it now
    ps: typing.Tuple[Decimal, Decimal] = PageSize.A4_PORTRAIT.value

    # now we'll write N triangles in the upper right corner
    # we'll later fill the remaining space with squares
    N: int = 4
    M: Decimal = Decimal(32)
    for i in range(0, N):
        x: Decimal = ps[0] - N * M + i * M
        y: Decimal = ps[1] - (i + 1) * M
        rg: HexColor = random.choice(grays)
        ConnectedShape(
            points=[(x + M, y), (x + M, y + M), (x, y + M)],
            stroke_color=rg,
            fill_color=rg,
        ).paint(page, Rectangle(x, y, M, M))

    # now we can fill up the remaining space with squares
    for i in range(0, N - 1):
        for j in range(0, N - 1):
            if j > i:
                continue
            x: Decimal = ps[0] - (N - 1) * M + i * M
            y: Decimal = ps[1] - (j + 1) * M
            rg: HexColor = random.choice(grays)
            ConnectedShape(
                points=[(x, y), (x + M, y), (x + M, y + M), (x, y + M)],
                stroke_color=rg,
                fill_color=rg,
            ).paint(page, Rectangle(x, y, M, M))


def main():
    # create empty Document
    pdf = Document()

    # create empty Page
    page = Page()

    # add Page to Document
    pdf.add_page(page)

    # create PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # now we can call this method in the main method
    add_gray_artwork_to_upper_right_corner(page)


if __name__ == "__main__":
    main()
```

Next we're going to add our company contact details, so people know where to reach us:

```python
#!chapter_009/src/snippet_019.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf.canvas.layout.shape.connected_shape import ConnectedShape
from decimal import Decimal
from borb.pdf import HexColor, X11Color
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf.page.page_size import PageSize
from borb.pdf import Paragraph
from borb.pdf.canvas.layout.image.barcode import Barcode, BarcodeType
from borb.pdf.canvas.layout.layout_element import LayoutElement
from borb.pdf import FlexibleColumnWidthTable
from borb.pdf.canvas.layout.annotation.remote_go_to_annotation import (
    RemoteGoToAnnotation,
)

import typing
import random


def add_gray_artwork_to_upper_right_corner(page: Page) -> None:
    """
    This method will add a gray artwork of squares and triangles in the upper right corner
    of the given Page
    """

    # define a list of gray colors
    grays: typing.List[HexColor] = [
        HexColor("A9A9A9"),
        HexColor("D3D3D3"),
        HexColor("DCDCDC"),
        HexColor("E0E0E0"),
        HexColor("E8E8E8"),
        HexColor("F0F0F0"),
    ]

    # we're going to use the size of the page later on,
    # so perhaps it's a good idea to retrieve it now
    ps: typing.Tuple[Decimal, Decimal] = PageSize.A4_PORTRAIT.value

    # now we'll write N triangles in the upper right corner
    # we'll later fill the remaining space with squares
    N: int = 4
    M: Decimal = Decimal(32)
    for i in range(0, N):
        x: Decimal = ps[0] - N * M + i * M
        y: Decimal = ps[1] - (i + 1) * M
        rg: HexColor = random.choice(grays)
        ConnectedShape(
            points=[(x + M, y), (x + M, y + M), (x, y + M)],
            stroke_color=rg,
            fill_color=rg,
        ).paint(page, Rectangle(x, y, M, M))

    # now we can fill up the remaining space with squares
    for i in range(0, N - 1):
        for j in range(0, N - 1):
            if j > i:
                continue
            x: Decimal = ps[0] - (N - 1) * M + i * M
            y: Decimal = ps[1] - (j + 1) * M
            rg: HexColor = random.choice(grays)
            ConnectedShape(
                points=[(x, y), (x + M, y), (x + M, y + M), (x, y + M)],
                stroke_color=rg,
                fill_color=rg,
            ).paint(page, Rectangle(x, y, M, M))


def main():
    # create empty Document
    pdf = Document()

    # create empty Page
    page = Page()

    # add Page to Document
    pdf.add_page(page)

    # create PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # now we can call this method in the main method
    add_gray_artwork_to_upper_right_corner(page)

    # contact information
    layout.add(
        Paragraph("Your Company", font_color=HexColor("#6d64e8"), font_size=Decimal(20))
    )

    # We're going to add a qr code that links to our website.
    # Later, we're going to add a remote go-to annotation
    # (that's just PDF talk for "if you click the qr code, it will take you to our website")
    # in order to be able to do that, we need its coordinates.
    qr_code: LayoutElement = Barcode(
        data="https://www.borbpdf.com",
        width=Decimal(64),
        height=Decimal(64),
        type=BarcodeType.QR,
    )

    # now we can add this content to the table
    layout.add(
        FlexibleColumnWidthTable(number_of_columns=2, number_of_rows=1)
        .add(qr_code)
        .add(
            Paragraph(
                """
            500 South Buena Vista Street
            Burbank CA
            91521-0991 USA
            """,
                padding_top=Decimal(12),
                respect_newlines_in_text=True,
                font_color=HexColor("#666666"),
                font_size=Decimal(10),
            )
        )
        .no_borders()
    )

    # let's add the remote go-to annotation
    page.add_annotation(
        RemoteGoToAnnotation(
            qr_code.get_previous_paint_box(), uri="https://www.borbpdf.com"
        )
    )


if __name__ == "__main__":
    main()
```

Now we can add a few titles and subtitles and some promotional blurb;

```python
#!chapter_009/src/snippet_020.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf.canvas.layout.shape.connected_shape import ConnectedShape
from decimal import Decimal
from borb.pdf import HexColor, X11Color
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf.page.page_size import PageSize
from borb.pdf import Paragraph
from borb.pdf.canvas.layout.image.barcode import Barcode, BarcodeType
from borb.pdf.canvas.layout.layout_element import LayoutElement
from borb.pdf import FlexibleColumnWidthTable
from borb.pdf.canvas.layout.annotation.remote_go_to_annotation import (
    RemoteGoToAnnotation,
)

import typing
import random


def add_gray_artwork_to_upper_right_corner(page: Page) -> None:
    """
    This method will add a gray artwork of squares and triangles in the upper right corner
    of the given Page
    """

    # define a list of gray colors
    grays: typing.List[HexColor] = [
        HexColor("A9A9A9"),
        HexColor("D3D3D3"),
        HexColor("DCDCDC"),
        HexColor("E0E0E0"),
        HexColor("E8E8E8"),
        HexColor("F0F0F0"),
    ]

    # we're going to use the size of the page later on,
    # so perhaps it's a good idea to retrieve it now
    ps: typing.Tuple[Decimal, Decimal] = PageSize.A4_PORTRAIT.value

    # now we'll write N triangles in the upper right corner
    # we'll later fill the remaining space with squares
    N: int = 4
    M: Decimal = Decimal(32)
    for i in range(0, N):
        x: Decimal = ps[0] - N * M + i * M
        y: Decimal = ps[1] - (i + 1) * M
        rg: HexColor = random.choice(grays)
        ConnectedShape(
            points=[(x + M, y), (x + M, y + M), (x, y + M)],
            stroke_color=rg,
            fill_color=rg,
        ).paint(page, Rectangle(x, y, M, M))

    # now we can fill up the remaining space with squares
    for i in range(0, N - 1):
        for j in range(0, N - 1):
            if j > i:
                continue
            x: Decimal = ps[0] - (N - 1) * M + i * M
            y: Decimal = ps[1] - (j + 1) * M
            rg: HexColor = random.choice(grays)
            ConnectedShape(
                points=[(x, y), (x + M, y), (x + M, y + M), (x, y + M)],
                stroke_color=rg,
                fill_color=rg,
            ).paint(page, Rectangle(x, y, M, M))


def main():
    # create empty Document
    pdf = Document()

    # create empty Page
    page = Page()

    # add Page to Document
    pdf.add_page(page)

    # create PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # now we can call this method in the main method
    add_gray_artwork_to_upper_right_corner(page)

    # contact information
    layout.add(
        Paragraph("Your Company", font_color=HexColor("#6d64e8"), font_size=Decimal(20))
    )

    # We're going to add a qr code that links to our website.
    # Later, we're going to add a remote go-to annotation
    # (that's just PDF talk for "if you click the qr code, it will take you to our website")
    # in order to be able to do that, we need its coordinates.
    qr_code: LayoutElement = Barcode(
        data="https://www.borbpdf.com",
        width=Decimal(64),
        height=Decimal(64),
        type=BarcodeType.QR,
    )

    # now we can add this content to the table
    layout.add(
        FlexibleColumnWidthTable(number_of_columns=2, number_of_rows=1)
        .add(qr_code)
        .add(
            Paragraph(
                """
            500 South Buena Vista Street
            Burbank CA
            91521-0991 USA
            """,
                padding_top=Decimal(12),
                respect_newlines_in_text=True,
                font_color=HexColor("#666666"),
                font_size=Decimal(10),
            )
        )
        .no_borders()
    )

    # let's add the remote go-to annotation
    page.add_annotation(
        RemoteGoToAnnotation(
            qr_code.get_previous_paint_box(), uri="https://www.borbpdf.com"
        )
    )

    # title
    layout.add(
        Paragraph(
            "Productbrochure", font_color=HexColor("#283592"), font_size=Decimal(34)
        )
    )

    # subtitle
    layout.add(
        Paragraph(
            "September 4th, 2021", font_color=HexColor("#e01b84"), font_size=Decimal(11)
        )
    )

    layout.add(
        Paragraph(
            "Product Overview", font_color=HexColor("000000"), font_size=Decimal(21)
        )
    )

    layout.add(
        Paragraph(
            """
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                        """
        )
    )


if __name__ == "__main__":
    main()
```

Images make things more visually interesting. Let's add an `Image` with some core product features next to it;

```python
#!chapter_009/src/snippet_021.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf.canvas.layout.shape.connected_shape import ConnectedShape
from decimal import Decimal
from borb.pdf import HexColor, X11Color
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf.page.page_size import PageSize
from borb.pdf import Paragraph
from borb.pdf.canvas.layout.image.barcode import Barcode, BarcodeType
from borb.pdf.canvas.layout.layout_element import LayoutElement
from borb.pdf import FlexibleColumnWidthTable
from borb.pdf.canvas.layout.annotation.remote_go_to_annotation import (
    RemoteGoToAnnotation,
)
from borb.pdf import FixedColumnWidthTable
from borb.pdf import TableCell
from borb.pdf import Image
from borb.pdf import UnorderedList

import typing
import random


def add_gray_artwork_to_upper_right_corner(page: Page) -> None:
    """
    This method will add a gray artwork of squares and triangles in the upper right corner
    of the given Page
    """

    # define a list of gray colors
    grays: typing.List[HexColor] = [
        HexColor("A9A9A9"),
        HexColor("D3D3D3"),
        HexColor("DCDCDC"),
        HexColor("E0E0E0"),
        HexColor("E8E8E8"),
        HexColor("F0F0F0"),
    ]

    # we're going to use the size of the page later on,
    # so perhaps it's a good idea to retrieve it now
    ps: typing.Tuple[Decimal, Decimal] = PageSize.A4_PORTRAIT.value

    # now we'll write N triangles in the upper right corner
    # we'll later fill the remaining space with squares
    N: int = 4
    M: Decimal = Decimal(32)
    for i in range(0, N):
        x: Decimal = ps[0] - N * M + i * M
        y: Decimal = ps[1] - (i + 1) * M
        rg: HexColor = random.choice(grays)
        ConnectedShape(
            points=[(x + M, y), (x + M, y + M), (x, y + M)],
            stroke_color=rg,
            fill_color=rg,
        ).paint(page, Rectangle(x, y, M, M))

    # now we can fill up the remaining space with squares
    for i in range(0, N - 1):
        for j in range(0, N - 1):
            if j > i:
                continue
            x: Decimal = ps[0] - (N - 1) * M + i * M
            y: Decimal = ps[1] - (j + 1) * M
            rg: HexColor = random.choice(grays)
            ConnectedShape(
                points=[(x, y), (x + M, y), (x + M, y + M), (x, y + M)],
                stroke_color=rg,
                fill_color=rg,
            ).paint(page, Rectangle(x, y, M, M))


def main():
    # create empty Document
    pdf = Document()

    # create empty Page
    page = Page()

    # add Page to Document
    pdf.add_page(page)

    # create PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # now we can call this method in the main method
    add_gray_artwork_to_upper_right_corner(page)

    # contact information
    layout.add(
        Paragraph("Your Company", font_color=HexColor("#6d64e8"), font_size=Decimal(20))
    )

    # We're going to add a qr code that links to our website.
    # Later, we're going to add a remote go-to annotation
    # (that's just PDF talk for "if you click the qr code, it will take you to our website")
    # in order to be able to do that, we need its coordinates.
    qr_code: LayoutElement = Barcode(
        data="https://www.borbpdf.com",
        width=Decimal(64),
        height=Decimal(64),
        type=BarcodeType.QR,
    )

    # now we can add this content to the table
    layout.add(
        FlexibleColumnWidthTable(number_of_columns=2, number_of_rows=1)
        .add(qr_code)
        .add(
            Paragraph(
                """
            500 South Buena Vista Street
            Burbank CA
            91521-0991 USA
            """,
                padding_top=Decimal(12),
                respect_newlines_in_text=True,
                font_color=HexColor("#666666"),
                font_size=Decimal(10),
            )
        )
        .no_borders()
    )

    # let's add the remote go-to annotation
    page.add_annotation(
        RemoteGoToAnnotation(
            qr_code.get_previous_paint_box(), uri="https://www.borbpdf.com"
        )
    )

    # title
    layout.add(
        Paragraph(
            "Productbrochure", font_color=HexColor("#283592"), font_size=Decimal(34)
        )
    )

    # subtitle
    layout.add(
        Paragraph(
            "September 4th, 2021", font_color=HexColor("#e01b84"), font_size=Decimal(11)
        )
    )

    layout.add(
        Paragraph(
            "Product Overview", font_color=HexColor("000000"), font_size=Decimal(21)
        )
    )

    layout.add(
        Paragraph(
            """
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                        """
        )
    )

    # table with image and key features
    layout.add(
        FixedColumnWidthTable(
            number_of_rows=2,
            number_of_columns=2,
            column_widths=[Decimal(0.3), Decimal(0.7)],
        )
        .add(
            TableCell(
                Image(
                    "https://www.att.com/catalog/en/skus/images/apple-iphone%2012-purple-450x350.png",
                    width=Decimal(128),
                    height=Decimal(128),
                ),
                row_span=2,
            )
        )
        .add(
            Paragraph(
                "Key Features",
                font_color=HexColor("e01b84"),
                font="Helvetica-Bold",
                padding_bottom=Decimal(10),
            )
        )
        .add(
            UnorderedList()
            .add(
                Paragraph(
                    "Nam aliquet ex eget felis lobortis aliquet sit amet ut risus."
                )
            )
            .add(
                Paragraph(
                    "Maecenas sit amet odio ut erat tincidunt consectetur accumsan ut nunc."
                )
            )
            .add(Paragraph("Phasellus eget magna et justo malesuada fringilla."))
            .add(
                Paragraph(
                    "Maecenas vitae dui ac nisi aliquam malesuada in consequat sapien."
                )
            )
        )
        .no_borders()
    )


if __name__ == "__main__":
    main()
```

Let's add a footer to the bottom of the page. We're going to put this in a separate method (so that we could call it later on, if we ever need to apply it to other pages in the PDF).

```python
#!chapter_009/src/snippet_022.py
from borb.pdf import Page

# new imports
from borb.pdf.canvas.line_art.line_art_factory import LineArtFactory


def add_colored_artwork_to_bottom_right_corner(page: Page) -> None:
    """
    This method will add a blue/purple artwork of lines and squares to the bottom right corner
    of the given Page
    """
    ps: typing.Tuple[Decimal, Decimal] = PageSize.A4_PORTRAIT.value

    # square
    Shape(
        points=[(ps[0] - 32, 40), (ps[0], 40), (ps[0], 40 + 32), (ps[0] - 32, 40 + 32)],
        stroke_color=HexColor("d53067"),
        fill_color=HexColor("d53067"),
    ).paint(page, Rectangle(ps[0] - 32, 40, 32, 32))

    # square
    Shape(
        points=[
            (ps[0] - 64, 40),
            (ps[0] - 32, 40),
            (ps[0] - 32, 40 + 32),
            (ps[0] - 64, 40 + 32),
        ],
        stroke_color=HexColor("eb3f79"),
        fill_color=HexColor("eb3f79"),
    ).paint(page, Rectangle(ps[0] - 64, 40, 32, 32))

    # triangle
    Shape(
        points=[(ps[0] - 96, 40), (ps[0] - 64, 40), (ps[0] - 64, 40 + 32)],
        stroke_color=HexColor("e01b84"),
        fill_color=HexColor("e01b84"),
    ).paint(page, Rectangle(ps[0] - 96, 40, 32, 32))

    # line
    r: Rectangle = Rectangle(Decimal(0), Decimal(32), ps[0], Decimal(8))
    Shape(
        points=LineArtFactory.rectangle(r),
        stroke_color=HexColor("283592"),
        fill_color=HexColor("283592"),
    ).paint(page, r)
```

Now we can call this method in the main body;

```python
#!chapter_009/src/snippet_023.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf.canvas.layout.shape.connected_shape import ConnectedShape
from decimal import Decimal
from borb.pdf import HexColor, X11Color
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf.page.page_size import PageSize
from borb.pdf import Paragraph
from borb.pdf.canvas.layout.image.barcode import Barcode, BarcodeType
from borb.pdf.canvas.layout.layout_element import LayoutElement
from borb.pdf import FlexibleColumnWidthTable
from borb.pdf.canvas.layout.annotation.remote_go_to_annotation import (
    RemoteGoToAnnotation,
)
from borb.pdf import FixedColumnWidthTable
from borb.pdf import TableCell
from borb.pdf import Image
from borb.pdf import UnorderedList
from borb.pdf.canvas.line_art.line_art_factory import LineArtFactory

import typing
import random


def add_gray_artwork_to_upper_right_corner(page: Page) -> None:
    """
    This method will add a gray artwork of squares and triangles in the upper right corner
    of the given Page
    """

    # define a list of gray colors
    grays: typing.List[HexColor] = [
        HexColor("A9A9A9"),
        HexColor("D3D3D3"),
        HexColor("DCDCDC"),
        HexColor("E0E0E0"),
        HexColor("E8E8E8"),
        HexColor("F0F0F0"),
    ]

    # we're going to use the size of the page later on,
    # so perhaps it's a good idea to retrieve it now
    ps: typing.Tuple[Decimal, Decimal] = PageSize.A4_PORTRAIT.value

    # now we'll write N triangles in the upper right corner
    # we'll later fill the remaining space with squares
    N: int = 4
    M: Decimal = Decimal(32)
    for i in range(0, N):
        x: Decimal = ps[0] - N * M + i * M
        y: Decimal = ps[1] - (i + 1) * M
        rg: HexColor = random.choice(grays)
        ConnectedShape(
            points=[(x + M, y), (x + M, y + M), (x, y + M)],
            stroke_color=rg,
            fill_color=rg,
        ).paint(page, Rectangle(x, y, M, M))

    # now we can fill up the remaining space with squares
    for i in range(0, N - 1):
        for j in range(0, N - 1):
            if j > i:
                continue
            x: Decimal = ps[0] - (N - 1) * M + i * M
            y: Decimal = ps[1] - (j + 1) * M
            rg: HexColor = random.choice(grays)
            ConnectedShape(
                points=[(x, y), (x + M, y), (x + M, y + M), (x, y + M)],
                stroke_color=rg,
                fill_color=rg,
            ).paint(page, Rectangle(x, y, M, M))


def add_colored_artwork_to_bottom_right_corner(page: Page) -> None:
    """
    This method will add a blue/purple artwork of lines and squares to the bottom right corner
    of the given Page
    """
    ps: typing.Tuple[Decimal, Decimal] = PageSize.A4_PORTRAIT.value

    # square
    ConnectedShape(
        points=[(ps[0] - 32, 40), (ps[0], 40), (ps[0], 40 + 32), (ps[0] - 32, 40 + 32)],
        stroke_color=HexColor("d53067"),
        fill_color=HexColor("d53067"),
    ).paint(page, Rectangle(ps[0] - 32, 40, 32, 32))

    # square
    ConnectedShape(
        points=[
            (ps[0] - 64, 40),
            (ps[0] - 32, 40),
            (ps[0] - 32, 40 + 32),
            (ps[0] - 64, 40 + 32),
        ],
        stroke_color=HexColor("eb3f79"),
        fill_color=HexColor("eb3f79"),
    ).paint(page, Rectangle(ps[0] - 64, 40, 32, 32))

    # triangle
    ConnectedShape(
        points=[(ps[0] - 96, 40), (ps[0] - 64, 40), (ps[0] - 64, 40 + 32)],
        stroke_color=HexColor("e01b84"),
        fill_color=HexColor("e01b84"),
    ).paint(page, Rectangle(ps[0] - 96, 40, 32, 32))

    # line
    r: Rectangle = Rectangle(Decimal(0), Decimal(32), ps[0], Decimal(8))
    ConnectedShape(
        points=LineArtFactory.rectangle(r),
        stroke_color=HexColor("283592"),
        fill_color=HexColor("283592"),
    ).paint(page, r)


def main():
    # create empty Document
    pdf = Document()

    # create empty Page
    page = Page()

    # add Page to Document
    pdf.add_page(page)

    # create PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # now we can call this method in the main method
    add_gray_artwork_to_upper_right_corner(page)

    # contact information
    layout.add(
        Paragraph("Your Company", font_color=HexColor("#6d64e8"), font_size=Decimal(20))
    )

    # We're going to add a qr code that links to our website.
    # Later, we're going to add a remote go-to annotation
    # (that's just PDF talk for "if you click the qr code, it will take you to our website")
    # in order to be able to do that, we need its coordinates.
    qr_code: LayoutElement = Barcode(
        data="https://www.borbpdf.com",
        width=Decimal(64),
        height=Decimal(64),
        type=BarcodeType.QR,
    )

    # now we can add this content to the table
    layout.add(
        FlexibleColumnWidthTable(number_of_columns=2, number_of_rows=1)
        .add(qr_code)
        .add(
            Paragraph(
                """
            500 South Buena Vista Street
            Burbank CA
            91521-0991 USA
            """,
                padding_top=Decimal(12),
                respect_newlines_in_text=True,
                font_color=HexColor("#666666"),
                font_size=Decimal(10),
            )
        )
        .no_borders()
    )

    # let's add the remote go-to annotation
    page.add_annotation(
        RemoteGoToAnnotation(
            qr_code.get_previous_paint_box(), uri="https://www.borbpdf.com"
        )
    )

    # title
    layout.add(
        Paragraph(
            "Productbrochure", font_color=HexColor("#283592"), font_size=Decimal(34)
        )
    )

    # subtitle
    layout.add(
        Paragraph(
            "September 4th, 2021", font_color=HexColor("#e01b84"), font_size=Decimal(11)
        )
    )

    layout.add(
        Paragraph(
            "Product Overview", font_color=HexColor("000000"), font_size=Decimal(21)
        )
    )

    layout.add(
        Paragraph(
            """
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
                        Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. 
                        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                        """
        )
    )

    # table with image and key features
    layout.add(
        FixedColumnWidthTable(
            number_of_rows=2,
            number_of_columns=2,
            column_widths=[Decimal(0.3), Decimal(0.7)],
        )
        .add(
            TableCell(
                Image(
                    "https://www.att.com/catalog/en/skus/images/apple-iphone%2012-purple-450x350.png",
                    width=Decimal(128),
                    height=Decimal(128),
                ),
                row_span=2,
            )
        )
        .add(
            Paragraph(
                "Key Features",
                font_color=HexColor("e01b84"),
                font="Helvetica-Bold",
                padding_bottom=Decimal(10),
            )
        )
        .add(
            UnorderedList()
            .add(
                Paragraph(
                    "Nam aliquet ex eget felis lobortis aliquet sit amet ut risus."
                )
            )
            .add(
                Paragraph(
                    "Maecenas sit amet odio ut erat tincidunt consectetur accumsan ut nunc."
                )
            )
            .add(Paragraph("Phasellus eget magna et justo malesuada fringilla."))
            .add(
                Paragraph(
                    "Maecenas vitae dui ac nisi aliquam malesuada in consequat sapien."
                )
            )
        )
        .no_borders()
    )

    # add footer
    add_colored_artwork_to_bottom_right_corner(page)


if __name__ == "__main__":
    main()
```

The final PDF should look somewhat like this:

![enter image description here](chapter_009/img/snippet_024.png)

## 9.4 Creating a nonogram puzzle

Nonograms, also known as Hanjie, Paint by Numbers, Picross, Griddlers, and Pic-a-Pix, and by various other names, are picture logic puzzles in which cells in a grid must be colored or left blank according to numbers at the side of the grid to reveal a hidden picture. In this puzzle type, the numbers are a form of discrete tomography that measures how many unbroken lines of filled-in squares there are in any given row or column. For example, a clue of "4 8 3" would mean there are sets of four, eight, and three filled squares, in that order, with at least one blank square between successive sets.

We're going to define the final nonogram as a piece of ASCII art:

```python
#!chapter_009/src/snippet_025.py
ascii_art: str = """
■...........■..
■...........■..
■■■.■■■.■■■.■■■
■.■.■.■.■...■.■
■■■.■■■.■...■■■
"""


def main():
    pass


if __name__ == "__main__":
    main()
```

Now we need to turn this into a set of horizontal and vertical clues. 
The following code does just that!

```python
#!chapter_009/src/snippet_026.py
# new imports
import typing

ascii_art: str = """
■...........■..
■...........■..
■■■.■■■.■■■.■■■
■.■.■.■.■...■.■
■■■.■■■.■...■■■
"""


def calculate_horizontal_and_vertical_clues():

    # trim
    while ascii_art[0] == "\n":
        ascii_art = ascii_art[1:]
    while ascii_art[-1] == "\n":
        ascii_art = ascii_art[:-1]

    # horizontal clues
    horizontal_clues: typing.List[typing.List[int]] = []
    for row in ascii_art.split("\n"):
        prev_char: str = ""
        prev_count: int = 0
        row_clues: typing.List[int] = []
        for c in row:
            if c == prev_char:
                prev_count += 1
            else:
                if prev_char == "■":
                    row_clues.append(prev_count)
                prev_char = c
                prev_count = 1
        if prev_char == "■":
            row_clues.append(prev_count)
        horizontal_clues.append(row_clues)
    number_of_rows: int = len(horizontal_clues)

    # vertical clues
    number_of_cols: int = int(len(ascii_art) / number_of_rows)
    vertical_clues: typing.List[typing.List[int]] = []
    for col_index in range(0, number_of_cols):
        col = [ascii_art.split("\n")[i][col_index] for i in range(0, number_of_rows)]
        prev_char: str = ""
        prev_count: int = 0
        col_clues: typing.List[int] = []
        for c in col:
            if c == prev_char:
                prev_count += 1
            else:
                if prev_char == "■":
                    col_clues.append(prev_count)
                prev_char = c
                prev_count = 1
        if prev_char == "■":
            col_clues.append(prev_count)
        vertical_clues.append(col_clues)

    # padding for horizontal_clues
    max_number_of_horizontal_clues: int = max([len(x) for x in horizontal_clues])
    for row in horizontal_clues:
        while len(row) < max_number_of_horizontal_clues:
            row.insert(0, None)

    # padding for vertical_clues
    max_number_of_vertical_clues: int = max([len(x) for x in vertical_clues])
    for col in vertical_clues:
        while len(col) < max_number_of_vertical_clues:
            col.insert(0, None)

    # return
    return horizontal_clues, vertical_clues


def main():
    pass


if __name__ == "__main__":
    main()
```

For this PDF we're going to use a custom `Font`. Let's first download the `ttf`

```python
#!chapter_009/src/snippet_027.py
from borb.pdf.canvas.font.simple_font.true_type_font import TrueTypeFont
from borb.pdf.canvas.font.font import Font

# Download Font
import requests

with open("IndieFlower-Regular.ttf", "wb") as ffh:
    ffh.write(
        requests.get(
            "https://github.com/google/fonts/blob/main/ofl/indieflower/IndieFlower-Regular.ttf?raw=true",
            allow_redirects=True,
        ).content
    )
```

Now we can create a skeleton document containing our title and explanation blurb:

```python
#!chapter_009/src/snippet_028.py
import typing
import requests
from borb.pdf.canvas.font.simple_font.true_type_font import TrueTypeFont
from borb.pdf.canvas.font.font import Font

# new imports
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import HexColor

from pathlib import Path
from decimal import Decimal


def calculate_horizontal_and_vertical_clues():

    ascii_art: str = """
■...........■..
■...........■..
■■■.■■■.■■■.■■■
■.■.■.■.■...■.■
■■■.■■■.■...■■■
"""

    # trim
    while ascii_art[0] == "\n":
        ascii_art = ascii_art[1:]
    while ascii_art[-1] == "\n":
        ascii_art = ascii_art[:-1]

    # horizontal clues
    horizontal_clues: typing.List[typing.List[int]] = []
    for row in ascii_art.split("\n"):
        prev_char: str = ""
        prev_count: int = 0
        row_clues: typing.List[int] = []
        for c in row:
            if c == prev_char:
                prev_count += 1
            else:
                if prev_char == "■":
                    row_clues.append(prev_count)
                prev_char = c
                prev_count = 1
        if prev_char == "■":
            row_clues.append(prev_count)
        horizontal_clues.append(row_clues)
    number_of_rows: int = len(horizontal_clues)

    # vertical clues
    number_of_cols: int = int(len(ascii_art) / number_of_rows)
    vertical_clues: typing.List[typing.List[int]] = []
    for col_index in range(0, number_of_cols):
        col = [ascii_art.split("\n")[i][col_index] for i in range(0, number_of_rows)]
        prev_char: str = ""
        prev_count: int = 0
        col_clues: typing.List[int] = []
        for c in col:
            if c == prev_char:
                prev_count += 1
            else:
                if prev_char == "■":
                    col_clues.append(prev_count)
                prev_char = c
                prev_count = 1
        if prev_char == "■":
            col_clues.append(prev_count)
        vertical_clues.append(col_clues)

    # padding for horizontal_clues
    max_number_of_horizontal_clues: int = max([len(x) for x in horizontal_clues])
    for row in horizontal_clues:
        while len(row) < max_number_of_horizontal_clues:
            row.insert(0, None)

    # padding for vertical_clues
    max_number_of_vertical_clues: int = max([len(x) for x in vertical_clues])
    for col in vertical_clues:
        while len(col) < max_number_of_vertical_clues:
            col.insert(0, None)

    # return
    return horizontal_clues, vertical_clues


def download_custom_font():
    with open("IndieFlower-Regular.ttf", "wb") as ffh:
        ffh.write(
            requests.get(
                "https://github.com/google/fonts/blob/main/ofl/indieflower/IndieFlower-Regular.ttf?raw=true",
                allow_redirects=True,
            ).content
        )


def main():
    calculate_horizontal_and_vertical_clues()
    download_custom_font()

    # create empty Document
    pdf = Document()

    # create empty Page
    page = Page()

    # add Page to Document
    pdf.add_page(page)

    # create PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add title
    layout.add(
        Paragraph(
            "Nonogram",
            font_color=HexColor("#19647E"),
            font=TrueTypeFont.true_type_font_from_file(Path("IndieFlower-Regular.ttf")),
            font_size=Decimal(20),
        )
    )

    # add explanation
    layout.add(
        Paragraph(
            """
    Nonograms, also known as Hanjie, Paint by Numbers, Picross, Griddlers, and Pic-a-Pix, and by various other names, 
    are picture logic puzzles in which cells in a grid must be colored or left blank according to numbers at the side of the grid to reveal a hidden picture. 
    In this puzzle type, the numbers are a form of discrete tomography that measures how many unbroken lines of filled-in squares there are in any given row or column. 
    For example, a clue of "4 8 3" would mean there are sets of four, eight, and three filled squares, in that order, with at least one blank square between successive sets.
                        """,
            font_color=HexColor("#28AFB0"),
        )
    )


if __name__ == "__main__":
    main()
```

We're going to represent the nonogram as a `Table`.
The following code builds a `FixedColumnWidthTable` from the clues we defined earlier.

We're going to start by defining a helper-method to build an empty `TableCell` object.

```python
#!chapter_009/src/snippet_029.py
# new imports
from borb.pdf import TableCell


def empty_cell_without_borders():
    return TableCell(
        Paragraph(" "),
        border_top=False,
        border_right=False,
        border_bottom=False,
        border_left=False,
    )
```

And now we can get on with building the `Table`:

```python
#!chapter_009/src/snippet_030.py
import typing
import requests
from borb.pdf.canvas.font.simple_font.true_type_font import TrueTypeFont
from borb.pdf.canvas.font.font import Font
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import HexColor
from borb.pdf import TableCell

# new imports
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Alignment

from pathlib import Path
from decimal import Decimal

ascii_art: str = """
■...........■..
■...........■..
■■■.■■■.■■■.■■■
■.■.■.■.■...■.■
■■■.■■■.■...■■■
"""


def calculate_horizontal_and_vertical_clues():

    # trim
    global ascii_art
    while ascii_art[0] == "\n":
        ascii_art = ascii_art[1:]
    while ascii_art[-1] == "\n":
        ascii_art = ascii_art[:-1]

    # horizontal clues
    horizontal_clues: typing.List[typing.List[int]] = []
    for row in ascii_art.split("\n"):
        prev_char: str = ""
        prev_count: int = 0
        row_clues: typing.List[int] = []
        for c in row:
            if c == prev_char:
                prev_count += 1
            else:
                if prev_char == "■":
                    row_clues.append(prev_count)
                prev_char = c
                prev_count = 1
        if prev_char == "■":
            row_clues.append(prev_count)
        horizontal_clues.append(row_clues)
    number_of_rows: int = len(horizontal_clues)

    # vertical clues
    number_of_cols: int = int(len(ascii_art) / number_of_rows)
    vertical_clues: typing.List[typing.List[int]] = []
    for col_index in range(0, number_of_cols):
        col = [ascii_art.split("\n")[i][col_index] for i in range(0, number_of_rows)]
        prev_char: str = ""
        prev_count: int = 0
        col_clues: typing.List[int] = []
        for c in col:
            if c == prev_char:
                prev_count += 1
            else:
                if prev_char == "■":
                    col_clues.append(prev_count)
                prev_char = c
                prev_count = 1
        if prev_char == "■":
            col_clues.append(prev_count)
        vertical_clues.append(col_clues)

    # padding for horizontal_clues
    max_number_of_horizontal_clues: int = max([len(x) for x in horizontal_clues])
    for row in horizontal_clues:
        while len(row) < max_number_of_horizontal_clues:
            row.insert(0, None)

    # padding for vertical_clues
    max_number_of_vertical_clues: int = max([len(x) for x in vertical_clues])
    for col in vertical_clues:
        while len(col) < max_number_of_vertical_clues:
            col.insert(0, None)

    # return
    return (
        horizontal_clues,
        max_number_of_horizontal_clues,
        vertical_clues,
        max_number_of_vertical_clues,
    )


def download_custom_font():
    with open("IndieFlower-Regular.ttf", "wb") as ffh:
        ffh.write(
            requests.get(
                "https://github.com/google/fonts/blob/main/ofl/indieflower/IndieFlower-Regular.ttf?raw=true",
                allow_redirects=True,
            ).content
        )


def empty_cell_without_borders():
    return TableCell(
        Paragraph(" "),
        border_top=False,
        border_right=False,
        border_bottom=False,
        border_left=False,
    )


def main():
    (
        horizontal_clues,
        max_number_of_horizontal_clues,
        vertical_clues,
        max_number_of_vertical_clues,
    ) = calculate_horizontal_and_vertical_clues()

    # number_of_rows, number_of_cols
    number_of_rows: int = len(horizontal_clues)
    number_of_cols: int = int(len(ascii_art) / number_of_rows)

    download_custom_font()

    # create empty Document
    pdf = Document()

    # create empty Page
    page = Page()

    # add Page to Document
    pdf.add_page(page)

    # create PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add title
    layout.add(
        Paragraph(
            "Nonogram",
            font_color=HexColor("#19647E"),
            font=TrueTypeFont.true_type_font_from_file(Path("IndieFlower-Regular.ttf")),
            font_size=Decimal(20),
        )
    )

    # add explanation
    layout.add(
        Paragraph(
            """
    Nonograms, also known as Hanjie, Paint by Numbers, Picross, Griddlers, and Pic-a-Pix, and by various other names, 
    are picture logic puzzles in which cells in a grid must be colored or left blank according to numbers at the side of the grid to reveal a hidden picture. 
    In this puzzle type, the numbers are a form of discrete tomography that measures how many unbroken lines of filled-in squares there are in any given row or column. 
    For example, a clue of "4 8 3" would mean there are sets of four, eight, and three filled squares, in that order, with at least one blank square between successive sets.
                        """,
            font_color=HexColor("#28AFB0"),
        )
    )

    # build table to represent nonogram
    table: FixedColumnWidthTable = FixedColumnWidthTable(
        number_of_rows=max_number_of_vertical_clues + number_of_rows,
        number_of_columns=max_number_of_horizontal_clues + number_of_cols,
    )

    for i in range(0, max_number_of_vertical_clues):
        for _ in range(0, max_number_of_horizontal_clues):
            table.add(empty_cell_without_borders())
        for j in range(0, len(vertical_clues)):
            if vertical_clues[j][i] is None:
                table.add(empty_cell_without_borders())
            else:
                table.add(
                    TableCell(
                        Paragraph(
                            str(vertical_clues[j][i]),
                            horizontal_alignment=Alignment.CENTERED,
                        ),
                        border_top=False,
                        border_right=False,
                        border_bottom=False,
                        border_left=False,
                    )
                )

    for i in range(0, len(horizontal_clues)):
        for j in horizontal_clues[i]:
            if j is None:
                table.add(empty_cell_without_borders())
            else:
                table.add(
                    TableCell(
                        Paragraph(str(j), horizontal_alignment=Alignment.CENTERED),
                        border_top=False,
                        border_right=False,
                        border_bottom=False,
                        border_left=False,
                    )
                )
        for _ in range(0, number_of_cols):
            table.add(Paragraph(" "))

    table.set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))

    # add Table
    layout.add(table)


if __name__ == "__main__":
    main()
```

Finally, we can store the `PDF`:

```python
#!chapter_009/src/snippet_031.py
import typing
import requests
from borb.pdf.canvas.font.simple_font.true_type_font import TrueTypeFont
from borb.pdf.canvas.font.font import Font
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import HexColor
from borb.pdf import TableCell

# new imports
from borb.pdf import FixedColumnWidthTable
from borb.pdf import Alignment

from pathlib import Path
from decimal import Decimal

ascii_art: str = """
■...........■..
■...........■..
■■■.■■■.■■■.■■■
■.■.■.■.■...■.■
■■■.■■■.■...■■■
"""


def calculate_horizontal_and_vertical_clues():

    # trim
    global ascii_art
    while ascii_art[0] == "\n":
        ascii_art = ascii_art[1:]
    while ascii_art[-1] == "\n":
        ascii_art = ascii_art[:-1]

    # horizontal clues
    horizontal_clues: typing.List[typing.List[int]] = []
    for row in ascii_art.split("\n"):
        prev_char: str = ""
        prev_count: int = 0
        row_clues: typing.List[int] = []
        for c in row:
            if c == prev_char:
                prev_count += 1
            else:
                if prev_char == "■":
                    row_clues.append(prev_count)
                prev_char = c
                prev_count = 1
        if prev_char == "■":
            row_clues.append(prev_count)
        horizontal_clues.append(row_clues)
    number_of_rows: int = len(horizontal_clues)

    # vertical clues
    number_of_cols: int = int(len(ascii_art) / number_of_rows)
    vertical_clues: typing.List[typing.List[int]] = []
    for col_index in range(0, number_of_cols):
        col = [ascii_art.split("\n")[i][col_index] for i in range(0, number_of_rows)]
        prev_char: str = ""
        prev_count: int = 0
        col_clues: typing.List[int] = []
        for c in col:
            if c == prev_char:
                prev_count += 1
            else:
                if prev_char == "■":
                    col_clues.append(prev_count)
                prev_char = c
                prev_count = 1
        if prev_char == "■":
            col_clues.append(prev_count)
        vertical_clues.append(col_clues)

    # padding for horizontal_clues
    max_number_of_horizontal_clues: int = max([len(x) for x in horizontal_clues])
    for row in horizontal_clues:
        while len(row) < max_number_of_horizontal_clues:
            row.insert(0, None)

    # padding for vertical_clues
    max_number_of_vertical_clues: int = max([len(x) for x in vertical_clues])
    for col in vertical_clues:
        while len(col) < max_number_of_vertical_clues:
            col.insert(0, None)

    # return
    return (
        horizontal_clues,
        max_number_of_horizontal_clues,
        vertical_clues,
        max_number_of_vertical_clues,
    )


def download_custom_font():
    with open("IndieFlower-Regular.ttf", "wb") as ffh:
        ffh.write(
            requests.get(
                "https://github.com/google/fonts/blob/main/ofl/indieflower/IndieFlower-Regular.ttf?raw=true",
                allow_redirects=True,
            ).content
        )


def empty_cell_without_borders():
    return TableCell(
        Paragraph(" "),
        border_top=False,
        border_right=False,
        border_bottom=False,
        border_left=False,
    )


def main():
    (
        horizontal_clues,
        max_number_of_horizontal_clues,
        vertical_clues,
        max_number_of_vertical_clues,
    ) = calculate_horizontal_and_vertical_clues()

    # number_of_rows, number_of_cols
    number_of_rows: int = len(horizontal_clues)
    number_of_cols: int = int(len(ascii_art) / number_of_rows)

    download_custom_font()

    # create empty Document
    pdf = Document()

    # create empty Page
    page = Page()

    # add Page to Document
    pdf.add_page(page)

    # create PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add title
    layout.add(
        Paragraph(
            "Nonogram",
            font_color=HexColor("#19647E"),
            font=TrueTypeFont.true_type_font_from_file(Path("IndieFlower-Regular.ttf")),
            font_size=Decimal(20),
        )
    )

    # add explanation
    layout.add(
        Paragraph(
            """
    Nonograms, also known as Hanjie, Paint by Numbers, Picross, Griddlers, and Pic-a-Pix, and by various other names, 
    are picture logic puzzles in which cells in a grid must be colored or left blank according to numbers at the side of the grid to reveal a hidden picture. 
    In this puzzle type, the numbers are a form of discrete tomography that measures how many unbroken lines of filled-in squares there are in any given row or column. 
    For example, a clue of "4 8 3" would mean there are sets of four, eight, and three filled squares, in that order, with at least one blank square between successive sets.
                        """,
            font_color=HexColor("#28AFB0"),
        )
    )

    # build table to represent nonogram
    table: FixedColumnWidthTable = FixedColumnWidthTable(
        number_of_rows=max_number_of_vertical_clues + number_of_rows,
        number_of_columns=max_number_of_horizontal_clues + number_of_cols,
    )

    for i in range(0, max_number_of_vertical_clues):
        for _ in range(0, max_number_of_horizontal_clues):
            table.add(empty_cell_without_borders())
        for j in range(0, len(vertical_clues)):
            if vertical_clues[j][i] is None:
                table.add(empty_cell_without_borders())
            else:
                table.add(
                    TableCell(
                        Paragraph(
                            str(vertical_clues[j][i]),
                            horizontal_alignment=Alignment.CENTERED,
                        ),
                        border_top=False,
                        border_right=False,
                        border_bottom=False,
                        border_left=False,
                    )
                )

    for i in range(0, len(horizontal_clues)):
        for j in horizontal_clues[i]:
            if j is None:
                table.add(empty_cell_without_borders())
            else:
                table.add(
                    TableCell(
                        Paragraph(str(j), horizontal_alignment=Alignment.CENTERED),
                        border_top=False,
                        border_right=False,
                        border_bottom=False,
                        border_left=False,
                    )
                )
        for _ in range(0, number_of_cols):
            table.add(Paragraph(" "))

    table.set_padding_on_all_cells(Decimal(2), Decimal(2), Decimal(2), Decimal(2))

    # add Table
    layout.add(table)

    # write Document
    with open("output.pdf", "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, pdf)


if __name__ == "__main__":
    main()
```

That should look somewhat like this:

![enter image description here](chapter_009/img/snippet_031.png)

## 9.5 Building a working calculator inside a PDF

We are going to create a method to add some geometric artwork to the upper right corner of a `Page`. This code is not really doing difficult things, it just deals with coordinates and math a bit. 

```python
#!chapter_009/src/snippet_032.py
# new imports
from borb.pdf.canvas.layout.shape.connected_shape import ConnectedShape
from decimal import Decimal
from borb.pdf import HexColor, X11Color
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf.page.page_size import PageSize
from borb.pdf import Page
import typing
import random


def add_gray_artwork_to_upper_right_corner(page: Page) -> None:
    """
    This method will add a gray artwork of squares and triangles in the upper right corner
    of the given Page
    """

    # define a list of gray colors
    grays: typing.List[HexColor] = [
        HexColor("A9A9A9"),
        HexColor("D3D3D3"),
        HexColor("DCDCDC"),
        HexColor("E0E0E0"),
        HexColor("E8E8E8"),
        HexColor("F0F0F0"),
    ]

    # we're going to use the size of the page later on,
    # so perhaps it's a good idea to retrieve it now
    ps: typing.Tuple[Decimal, Decimal] = PageSize.A4_PORTRAIT.value

    # now we'll write N triangles in the upper right corner
    # we'll later fill the remaining space with squares
    N: int = 4
    M: Decimal = Decimal(32)
    for i in range(0, N):
        x: Decimal = ps[0] - N * M + i * M
        y: Decimal = ps[1] - (i + 1) * M
        rg: HexColor = random.choice(grays)
        ConnectedShape(
            points=[(x + M, y), (x + M, y + M), (x, y + M)],
            stroke_color=rg,
            fill_color=rg,
        ).paint(page, Rectangle(x, y, M, M))

    # now we can fill up the remaining space with squares
    for i in range(0, N - 1):
        for j in range(0, N - 1):
            if j > i:
                continue
            x: Decimal = ps[0] - (N - 1) * M + i * M
            y: Decimal = ps[1] - (j + 1) * M
            rg: HexColor = random.choice(grays)
            ConnectedShape(
                points=[(x, y), (x + M, y), (x + M, y + M), (x, y + M)],
                stroke_color=rg,
                fill_color=rg,
            ).paint(page, Rectangle(x, y, M, M))
```

Similarly, I want to add some geometric artwork to the bottom of the page to balance things out a bit. I'm going to write another separate method for that.

```python
#!chapter_009/src/snippet_033.py
# new imports
from borb.pdf.canvas.line_art.line_art_factory import LineArtFactory


def add_colored_artwork_to_bottom_right_corner(page: "Page") -> None:
    """
    This method will add a blue/purple artwork of lines and squares to the bottom right corner
    of the given Page
    """
    ps: typing.Tuple[Decimal, Decimal] = PageSize.A4_PORTRAIT.value

    # square
    Shape(
        points=[(ps[0] - 32, 40), (ps[0], 40), (ps[0], 40 + 32), (ps[0] - 32, 40 + 32)],
        stroke_color=HexColor("f1cd2e"),
        fill_color=HexColor("f1cd2e"),
    ).paint(page, Rectangle(ps[0] - 32, 40, 32, 32))

    # square
    Shape(
        points=[
            (ps[0] - 64, 40),
            (ps[0] - 32, 40),
            (ps[0] - 32, 40 + 32),
            (ps[0] - 64, 40 + 32),
        ],
        stroke_color=HexColor("0b3954"),
        fill_color=HexColor("0b3954"),
    ).paint(page, Rectangle(ps[0] - 64, 40, 32, 32))

    # triangle
    Shape(
        points=[(ps[0] - 96, 40), (ps[0] - 64, 40), (ps[0] - 64, 40 + 32)],
        stroke_color=HexColor("a5ffd6"),
        fill_color=HexColor("a5ffd6"),
    ).paint(page, Rectangle(ps[0] - 96, 40, 32, 32))

    # line
    r: Rectangle = Rectangle(Decimal(0), Decimal(32), ps[0], Decimal(8))
    Shape(
        points=LineArtFactory.rectangle(r),
        stroke_color=HexColor("56cbf9"),
        fill_color=HexColor("56cbf9"),
    ).paint(page, r)
```

Now we're going to create a method that adds the image of a calculator to our `Page`. Here we are using absolute layout, since we want to make absolutely sure that our `Image` is located at the same coordinates every time (even if we were to change the text around it).

```python
#!chapter_009/src/snippet_034.py
from borb.pdf import Image
from decimal import Decimal


def add_calculator_image(page: "Page"):
    calculator_img = Image(
        "https://www.shopcore.nl/pub/media/catalog/product/cache/49cebce0f131f74df9ad2e5adc64fe79/t/i/ti-1726-1.jpg",
        width=Decimal(128),
        height=Decimal(128),
    )
    calculator_img.paint(
        page,
        Rectangle(
            Decimal(595 / 2 - 128 / 2),
            Decimal(842 / 2 + 128 / 2),
            Decimal(600),
            Decimal(128),
        ),
    )
```

Next up we will be adding a lot of "buttons" (they are actually annotations with associated javascript actions). To make it a bit easier on ourselves we'll separate this logic into its own method.

```python
#!chapter_009/src/snippet_035.py
from borb.io.read.types import Name
from borb.io.read.types import String
from borb.pdf.canvas.layout.annotation.remote_go_to_annotation import (
    RemoteGoToAnnotation,
)


def add_invisible_button(r: "Rectangle", javascript: str):
    # the next line (commented out) adds a rectangular annotation with red border
    # this makes it a lot easier to debug the calculator
    # page.add_annotation(SquareAnnotation(r, stroke_color=HexColor("ff0000"), fill_color=None))
    page.add_annotation(RemoteGoToAnnotation(r, "https://www.borbpdf.com"))
    page[Name("Annots")][-1][Name("A")][Name("S")] = Name("JavaScript")
    page[Name("Annots")][-1][Name("A")][Name("JS")] = String(javascript)
```

Now we are ready to add all the buttons, and have them call our main Javascript (which will be inserted later on).

```python
#!chapter_009/src/snippet_036.py
def add_action_annotations(page: "Page"):
    add_invisible_button(
        Rectangle(Decimal(275), Decimal(492), Decimal(13), Decimal(13)),
        "process_token('0')",
    )
    add_invisible_button(
        Rectangle(Decimal(291), Decimal(492), Decimal(13), Decimal(13)),
        "process_token('.')",
    )
    add_invisible_button(
        Rectangle(Decimal(307), Decimal(492), Decimal(13), Decimal(13)),
        "process_token('=')",
    )

    add_invisible_button(
        Rectangle(Decimal(275), Decimal(507), Decimal(13), Decimal(13)),
        "process_token('1')",
    )
    add_invisible_button(
        Rectangle(Decimal(291), Decimal(507), Decimal(13), Decimal(13)),
        "process_token('2')",
    )
    add_invisible_button(
        Rectangle(Decimal(307), Decimal(507), Decimal(13), Decimal(13)),
        "process_token('3')",
    )

    add_invisible_button(
        Rectangle(Decimal(275), Decimal(522), Decimal(13), Decimal(13)),
        "process_token('4')",
    )
    add_invisible_button(
        Rectangle(Decimal(291), Decimal(522), Decimal(13), Decimal(13)),
        "process_token('5')",
    )
    add_invisible_button(
        Rectangle(Decimal(307), Decimal(522), Decimal(13), Decimal(13)),
        "process_token('6')",
    )

    add_invisible_button(
        Rectangle(Decimal(275), Decimal(538), Decimal(13), Decimal(13)),
        "process_token('7')",
    )
    add_invisible_button(
        Rectangle(Decimal(291), Decimal(538), Decimal(13), Decimal(13)),
        "process_token('8')",
    )
    add_invisible_button(
        Rectangle(Decimal(307), Decimal(538), Decimal(13), Decimal(13)),
        "process_token('9')",
    )

    add_invisible_button(
        Rectangle(Decimal(324), Decimal(551), Decimal(13), Decimal(12)),
        "process_token('/')",
    )
    add_invisible_button(
        Rectangle(Decimal(324), Decimal(536), Decimal(13), Decimal(13)),
        "process_token('x')",
    )
    add_invisible_button(
        Rectangle(Decimal(324), Decimal(520), Decimal(13), Decimal(13)),
        "process_token('-')",
    )
    add_invisible_button(
        Rectangle(Decimal(324), Decimal(497), Decimal(13), Decimal(21)),
        "process_token('+')",
    )

    add_invisible_button(
        Rectangle(Decimal(257), Decimal(541), Decimal(13), Decimal(21)),
        "process_token('AC')",
    )
```

This part is easy, we add document level Javascript to our PDF. This script has everything in it to make our calculator actually work.

```python
#!chapter_009/src/snippet_037.py
from borb.io.read.types import Decimal as bDecimal
from borb.io.read.types import String
from borb.io.read.types import Stream
from borb.io.read.types import Dictionary
from borb.io.read.types import List
from borb.pdf import Document


def add_document_level_javascript(doc: Document):
    # build global_js_stream
    global_js_stream = Stream()
    global_js_stream[Name("Type")] = Name("JavaScript")
    global_js_stream[
        Name("DecodedBytes")
    ] = b"""
var state = 'START';
var arg1 = 0;
var arg2 = 0;
var disp = '';
var oper = '';

function to_string(f){
	if(f > 99999999){ return '99999999'; }
	if(f < -99999999){ return '-99999999'; }
	x = f.toString();
  if(x.length > 8){ x = x.substring(0, 8);}
	return x;	
}

function is_number(token){
	return token == '0' || token == '1' || token == '2' || token == '3' || token == '4' || token == '5' || token == '6' || token == '7'  || token == '8' || token == '9';
}

function is_binary_operator(token){
	return token == '+' || token == '-' || token == 'x' || token == '/';
}

function apply_operator(a1, a2, o){
	if(o == '+'){ return a1 + a2; }
	if(o == '-'){ return a1 - a2; }
	if(o == 'x'){ return a1 * a2; }
	if(o == '/'){ 
		if(a2 == 0){
			return 0;
		}
		return a1 / a2; 
	}
}

function process_token(token){
	if(token == 'AC'){
		state = 'START';
		arg1 = 0;
		arg2 = 0;
		disp = '';
		oper = '';
    this.getField("field-000").value = disp;
		return;
	}
	if(state == 'START'){
		if(token == '.'){
			disp = '0.';
      this.getField("field-000").value = disp;
			state = 'ARG1_FLOAT';
			return;
		}
		if(is_number(token)){
			disp = token;
      this.getField("field-000").value = disp;
			state = 'ARG1'
			return;
		}
	}
	/* 
	 * ARG1
	 * arg1 is being built
	 */
	if(state == 'ARG1'){
		if(token == '.'){
			disp += '.';
      this.getField("field-000").value = disp;
			state = 'ARG1_FLOAT';
			return;
		}
		if(is_number(token)){
			disp += token;
      this.getField("field-000").value = disp;
			return;
		}
		if(is_binary_operator(token)){
			arg1 = parseFloat(disp);
			disp = '';
      this.getField("field-000").value = disp;
			oper = token;
			state = 'OPERATOR'
			return;
		}
	}
	/* 
	 * ARG1_FLOAT
	 * arg1 is being built, and a decimal point has been entered
	 */
	if(state == 'ARG1_FLOAT'){
		if(is_number(token)){
			disp += token;
      this.getField("field-000").value = disp;
			return;
		}
		if(is_binary_operator(token)){
			arg1 = parseFloat(disp);
			disp = '';
      this.getField("field-000").value = disp;
			oper = token;
			state = 'OPERATOR'
			return;
		}
	}
	/* 
	 * BINARY_OPERATOR
	 * a binary operator was entered
	 */
	if(state == 'OPERATOR'){
		if(token == '.'){
			disp = '0.';
      this.getField("field-000").value = disp;
			state = 'ARG2_FLOAT';
			return;
		}
		if(is_number(token)){
			disp = token;
      this.getField("field-000").value = disp;
			state = 'ARG2'
			return;
		}
	}
	/* 
	 * ARG2
	 * arg2 is being built
	 */
	if(state == 'ARG2'){
		if(token == '.'){
			disp += '.';
      this.getField("field-000").value = disp;
			state = 'ARG2_FLOAT';
			return;
		}
		if(is_number(token)){
			disp += token;
      this.getField("field-000").value = disp;
			return;
		}
		if(is_binary_operator(token)){
			arg1 = apply_operator(arg1, parseFloat(disp), oper);
			disp = to_string(arg1);
      this.getField("field-000").value = disp;
			oper = token;
			state = 'OPERATOR'
			return;
		}
		if(token == '='){
			arg2 = parseFloat(disp);
			disp = to_string(apply_operator(arg1, arg2, oper));
      this.getField("field-000").value = disp;
			state = 'EQUALS';
			return;
		}
	}
	if(state == 'ARG2_FLOAT'){
		if(is_number(token)){
			disp += token;
      this.getField("field-000").value = disp;
			return;
		}
		if(is_binary_operator(token)){
			arg1 = apply_operator(arg1, parseFloat(disp), oper);
			disp = to_string(arg1);
      this.getField("field-000").value = disp;
			oper = token;
			state = 'OPERATOR'
			return;
		}
		if(token == '='){
			arg2 = parseFloat(disp);
			disp = to_string(apply_operator(arg1, arg2, oper));
      this.getField("field-000").value = disp;
			state = 'EQUALS';
			return;
		}
	}	
	if(state == 'EQUALS'){
		if(token == '='){
			disp = to_string(apply_operator(parseFloat(disp), arg2, oper));
      this.getField("field-000").value = disp;
			return;
		}
		if(token == '.'){
			disp = '0.';
      this.getField("field-000").value = disp;
			state = 'ARG1_FLOAT';
			return;
		}
		if(is_number(token)){
			disp = token;
      this.getField("field-000").value = disp;
			state = 'ARG1';
			return;
		}
		if(is_binary_operator(token)){
			arg1 = parseFloat(disp);
			oper = token;
			state = 'OPERATOR';
			return;
		}
	}
}
this.getField("field-000").fillColor = color.transparent;
this.getField("field-000").textFont = "Courier";
app.runtimeHighlightColor = ["RGB", 47/255, 53/255, 51/255];
"""

    global_js_stream[Name("Filter")] = Name("FlateDecode")

    # build global js dictionary
    global_js_dictionary = Dictionary()
    global_js_dictionary[Name("S")] = Name("JavaScript")
    global_js_dictionary[Name("JS")] = global_js_stream

    # build name tree
    root = doc["XRef"]["Trailer"]["Root"]
    root[Name("Names")] = Dictionary()
    names = root["Names"]
    names[Name("JavaScript")] = Dictionary()
    names["JavaScript"][Name("Kids")] = List()

    # build leaf
    kids_01 = Dictionary()
    kids_01[Name("Limits")] = List()
    kids_01["Limits"].append(String("js-000"))
    kids_01["Limits"].append(String("js-000"))
    kids_01[Name("Names")] = List()
    kids_01["Names"].append(String("js-000"))
    kids_01["Names"].append(global_js_dictionary)

    names["JavaScript"]["Kids"].append(kids_01)
```

In order to display the result of the calculations, we need to add a `TextField` that the JavaScript can modify.

```python
#!chapter_009/src/snippet_038.py
from borb.pdf.canvas.layout.forms.text_field import TextField


def add_display(page: "Page"):
    r0 = Rectangle(Decimal(264), Decimal(587), Decimal(65), Decimal(15))
    Shape(
        LineArtFactory.rectangle(r0),
        stroke_color=HexColor("7e838e"),
        fill_color=HexColor("7e838e"),
    ).paint(page, r0)

    r1 = Rectangle(Decimal(264), Decimal(587), Decimal(65), Decimal(15))
    display_field = TextField(value="", font_size=Decimal(13))
    display_field.paint(page, r1)
```

Now we can build our `Document`

```python
#!chapter_009/src/snippet_039.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf.canvas.geometry.rectangle import Rectangle
from borb.pdf import MultiColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph
from borb.pdf import HexColor
from borb.pdf.canvas.layout.image.barcode import Barcode, BarcodeType

from decimal import Decimal
from pathlib import Path


def main():

    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()
    doc.add_page(page)

    # add javascript
    add_document_level_javascript(doc)

    # add artwork
    add_gray_artwork_to_upper_right_corner(page)
    add_colored_artwork_to_bottom_right_corner(page)

    # add Image
    add_calculator_image(page)
    add_action_annotations(page)

    # add TextField
    add_display(page)

    # create layout
    layout: PageLayout = MultiColumnLayout(page, 2)

    # add first Paragraph
    layout.add(
        Paragraph(
            "Javascript in PDF",
            font="Helvetica-Bold",
            font_size=Decimal(20),
            font_color=HexColor("56cbf9"),
        )
    )

    # add second paragraph
    layout.add(
        Paragraph(
            """
    You can cause an action to occur when a bookmark or link is clicked, or when a page is viewed. 
    For example, you can use links and bookmarks to jump to different locations in a document, 
    execute commands from a menu, and perform other actions. """
        )
    )

    # add third Paragraph
    # we are explictly adding the newlines ourselves to ensure the text
    # breaks nicely around the outline of the calculator
    layout.add(
        Paragraph(
            """To enhance the interactive qual-
    ity of a document, you can spec-
    ify actions, such as changing the 
    zoom value, to occur when a page 
    is opened or closed.""",
            respect_newlines_in_text=True,
        )
    )

    # add fourth Paragraph
    layout.add(Paragraph("Trigger Types", font="Helvetica-Bold", font_size=Decimal(14)))

    # add fifth Paragraph
    layout.add(
        Paragraph(
            "Triggers determine how actions are activated in media clips, pages, and form fields. For example, you can specify a movie or sound clip to play when a page is opened or closed. The available options depend on the specified page element."
        )
    )

    # add sixth Paragraph
    layout.add(Paragraph("Javascript", font="Helvetica-Bold", font_size=Decimal(14)))

    # add seventh Paragraph
    layout.add(
        Paragraph(
            """
    The JavaScript language was developed by Netscape Communications as a means to create interactive web pages more easily. Adobe has enhanced JavaScript so that you can easily integrate this level of interactivity into your PDF documents.
    You can invoke JavaScript code using actions associated with bookmarks, links, and pages. You can set Document Actions which lets you create document-level JavaScript actions that apply to the entire document."""
        )
    )

    # add final Paragraph
    Paragraph(
        "With enough buttons and Javascript, you could even make a functional calculator inside a PDF!",
        font="Courier",
        font_size=Decimal(8),
        padding_left=Decimal(5),
        border_left=True,
    ).paint(page, Rectangle(Decimal(350), Decimal(450), Decimal(200), Decimal(100)))

    # add QR code
    Barcode(
        "https://www.borb-pdf.com",
        type=BarcodeType.QR,
        width=Decimal(64),
        height=Decimal(64),
    ).paint(
        page, Rectangle(Decimal(595 - 64 - 15), Decimal(84), Decimal(64), Decimal(64))
    )

    # store PDF
    with open(Path("output.pdf"), "wb") as pdf_file_handle:
        PDF.dumps(pdf_file_handle, doc)
```

Look at the stunning PDF you made:

![enter image description here](chapter_009/img/snippet_039.png)

## 9.7 Getting the raw bytes of a PDF

In this example we're going to use the `dropbox` API to store a PDF in the cloud.
To do this, we'll need to get the raw bytes of the PDF.

To run this code, you'll first need to create a new app in the dropbox developer portal.
This app will need to have the right permissions (the ability to create files).

Go to `dropbox.com/developers` and click `App Console`.
You should be directed to a page like this one:

![enter image description here](chapter_009/img/snippet_040_001.png)

Click `Create app`, you should now see something like this:

![enter image description here](chapter_009/img/snippet_040_002.png)

Now you need to give this app permission to write files (`files.content.write`).
You can do this by going to the `Permissions` tab and checking the box:

![enter image description here](chapter_009/img/snippet_040_003.png)

Back in the `Settings` tab, we can now click `Generate` under `Generate access token`:

![enter image description here](chapter_009/img/snippet_040_004.png)

After a small wait, an access token should appear:

![enter image description here](chapter_009/img/snippet_040_005.png)

Now we can get to the coding part! 
Let's start by setting up a connection to dropbox.

```python
#!chapter_009/src/snippet_040.py
import dropbox


def dropbox_connect() -> dropbox.dropbox_client.Dropbox:
    """
    This function connects to Dropbox and returns the API connection
    :return:    a connection to the Dropbox API
    """
    try:
        dbx = dropbox.Dropbox("<your access key>")
    except AuthError as e:
        print("Error connecting to Dropbox with access token: " + str(e))
    return dbx


if __name__ == "__main__":

    # set up connection
    dbx: dropbox.dropbox_client.Dropbox = dropbox_connect()
    print(dbx)
```


Now we can build a simple "Hello World" document. 
I'm not going to go into the details of that here, since that's not really the point of this particular exercise.


```python
#!chapter_009/src/snippet_041.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph

import dropbox

from decimal import Decimal
from pathlib import Path


def dropbox_connect() -> dropbox.dropbox_client.Dropbox:
    """
    This function connects to Dropbox and returns the API connection
    :return:    a connection to the Dropbox API
    """
    try:
        dbx = dropbox.Dropbox("<your access key>")
    except AuthError as e:
        print("Error connecting to Dropbox with access token: " + str(e))
    return dbx


def create_pdf() -> Document:
    """
    This function creates a PDF document containing the "Hello World" text.
    :return:    a borb.pdf.Document
    """

    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()
    doc.add_page(page)

    # PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add Paragraph
    layout.add(Paragraph("Hello World"))

    # return
    return doc


if __name__ == "__main__":

    # set up connection
    dbx: dropbox.dropbox_client.Dropbox = dropbox_connect()
    print(dbx)

    # create PDF
    pdf: Document = create_pdf()
```


Finally, we can use the method `document_to_bytes` to obtain the raw bytes of the `Document`.
Once we have those, we just need to call the appropriate method of the `dropbox` API to store.


```python
#!chapter_009/src/snippet_042.py
from borb.pdf import Document
from borb.pdf import Page
from borb.pdf import PDF
from borb.pdf import SingleColumnLayout
from borb.pdf import PageLayout
from borb.pdf import Paragraph

import dropbox

from decimal import Decimal
from pathlib import Path

import io


def dropbox_connect() -> dropbox.dropbox_client.Dropbox:
    """
    This function connects to Dropbox and returns the API connection
    :return:    a connection to the Dropbox API
    """
    try:
        dbx = dropbox.Dropbox("<your access key>")
    except AuthError as e:
        print("Error connecting to Dropbox with access token: " + str(e))
    return dbx


def create_pdf() -> Document:
    """
    This function creates a PDF document containing the "Hello World" text.
    :return:    a borb.pdf.Document
    """

    # create Document
    doc: Document = Document()

    # create Page
    page: Page = Page()
    doc.add_page(page)

    # PageLayout
    layout: PageLayout = SingleColumnLayout(page)

    # add Paragraph
    layout.add(Paragraph("Hello World"))

    # return
    return doc


def document_to_bytes(pdf: Document) -> bytes:
    """
    This function converts a borb.pdf.Document to bytes
    :param pdf:     the input borb.pdf.Document
    :return:        the output bytes
    """
    buffer = io.BytesIO()
    PDF.dumps(buffer, pdf)
    buffer.seek(0)
    return buffer.getvalue()


if __name__ == "__main__":

    # set up connection
    dbx: dropbox.dropbox_client.Dropbox = dropbox_connect()
    print(dbx)

    # create PDF
    pdf: Document = create_pdf()

    # upload
    dbx.files_upload(
        document_to_bytes(pdf),
        "/pdfs/hello_world.pdf",
        mode=dropbox.files.WriteMode("overwrite"),
    )
```

That's it. You should now have a folder `pdfs` on your dropbox, containing a pdf `hello_world.pdf`.

![enter image description here](chapter_009/img/snippet_042.png)

## 9.6 Conclusion

This section was all about wrapping up your knowledge with some practical examples.
I hope you enjoyed working through the examples.
