---
tags:
  - markdown
  - syntax
  - obsidian
date: 2024-10-15T14:44:00
---
Markdown is a simple way of formatting text. For complete reference look here: https://www.markdownguide.org/getting-started/

You can also find a quick reference (cheat sheet) there: https://www.markdownguide.org/cheat-sheet/ or simply here [[markdown-cheat-sheet]].

To illustrate some of the possibilities:
# Header level 1
## Header level 2
### Header level 4

To **highlight** (bold) text or in *italics*. You can either type the * characters or use the common shortcuts Ctrl-B for **bold** or Ctrl-I for *italics*.

Lists can be numbered or unnumbered. An unnumbered list can be started with a dash followed by a space; additional levels are achieved by prepending spaces before the dash
- Projects
   - Project 1
   - Project 2
- Education
- Research

A numbered list can be started with a number followed by a dot and a space. Adding items will automatically count increase the number. You can start at any positive number.
1. Projects
2. Education
3. Research

Or you create a list without the dashes:
Projects
Education
Research
then select the items and use the context menu to create a list.

# Tables

| Doctor | Name  | Family name  |
| ------ | ----- | ------------ |
| W10    | Donna | Noble        |
| W11    | Amy   | Pond         |
| W11    | Clara | Oswin Oswald |

# Programming
Fenced code blocks: add blocks of text without rearranging the text. Start such a section with three backquotes. 

> [!Info] Syntax highlighting
> After the backquotes the programming language can be specified, allowing Obsidian to use colour for syntax highlighting, in this case some python code.


```python
class test_pypdf(unittest.TestCase):

    @mock.patch('PyPDF2.PdfReader')
    @mock.patch('PyPDF2.PageObject.extract_text')
    def test_reader(self, mock_extract, mock_read):
        mocker = mock.MagicMock(autospec=PyPDF2.PdfReader)
        mock_page = mock.MagicMock(autospec=PyPDF2.PageObject)
        
        mock_extract.return_value = 'Some text'
        mock_page.extract_text = mock_extract
        
        p = mock.PropertyMock(return_value=[mock_page, mock_page])
        type(mocker).pages = p
        mock_read.return_value = mocker
        
        res = read_some_text()
        
        self.assertEqual(res, 'some text')
```

# Links

# Call-outs

> [!Error] Fatal error
> Some unknown problem occurred

>[!Warning] 
>The function is deprecated, consider an alternative function

>[!Note] Standard
>A standard note

>[!Custom] Define your own
>Anything is allowed, as long as the formatting is correct

# Images
Images can be handled the same as any non-markdown document. Obsidian does render some types of documents, images and pdf files among them. First create a link to the file: [[BioSpace Fieldwork 2.jpg]], then edit the link by adding a "!" character before the link like so
`![[BioSpace fieldwork.jpg]]` to render the file in place.

The same works for pdf files:
[[markdown-cheat-sheet]]
