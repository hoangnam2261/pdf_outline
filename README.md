# pdf_outline
Get outline from pdf when there is no outline information in pdf file's metadata

# Background
- We can get the pdf file's outline by using pdfminer in the below way. But that's in case pdf file's metadata contains outline information.

```python
from pdfminer.pdfparser import PDFParser
from pdfminer.pdfdocument import PDFDocument

path='example_pdf/with_outline.pdf'
fp = open(path, 'rb')
# Create a PDF parser object associated with the file object.
parser = PDFParser(fp)
# Create a PDF document object that stores the document structure.
document = PDFDocument(parser)
outlines = document.get_outlines()
#print outlines
for (level,title,dest,a,se) in outlines:
    print (level, title)
```

- If the pdf file have no outline infor in metadata, you will see this Exception:

```python
pdfminer.pdfdocument.PDFNoOutlines
```

- This library helps resolve this issue. It can get outline from the pdf files with/without outline infor in metadata.
