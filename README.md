# Programming in Python Course Materials

## Dependencies and Installation
The materials are intended to be run from Jupyter Notebooks within the Anaconda package.

You need the following components
- RISE (https://rise.readthedocs.io/en/maint-5.5/)

`$ conda install -c conda-forge rise`

- NBextensions with Table of Contents (2), Split Columns, RISE installed an enabled

`$ conda install -c conda-forge jupyter_contrib_nbextensions`

- decktape for creating PDFs (https://github.com/astefanutti/decktape)

If you do not have npm, install that first with Homebrew:

`$ brew install node # install npm`

Then install decktape

`$ npm install -g decktape`<br />
`$ decktape`

## Usage
First make sure that the Table of Contents (2), Split Columns and RISE checkboxes are activated in the NBextensions pane. In Jupyter Notebooks, go to

`Edit -> nbextensions config`

### Presentation Mode
In order to present the slides, simply click on the RISE icon (tiny barchart) inm Jupyter Notebooks.
Set your browser to full-screen mode.

### Generate PDFs
First, you need to fetch the session ID for you running Jupyer Notebooks process. This can be found in the terminal window in which it is running. Find this section:<br />

<pre>
    To access the notebook, open this file in a browser:
        file:///Users/...
    Or copy and paste one of these URLs:
        http://localhost:8888/?token=6dfjsdja3c75f6bc21d5c2a7891774b3fc540ca2615765eb6c5
</pre>

Then, generate a PDF using

`$ decktape rise <URI_of_your_presentation>?token=<token_from above> <filename.pdf>`

**Note:** Unfortunately, the slides numbers are not included in the PDFs.

## RISE Meta-data
I currently use the following settings for `rise` and `toc`in the notebook's meta-data:

```
"rise": {
    "backimage": "background.png",
    "center": false,
    "enable_chalkboard": false,
    "footer": "Univ.-Prof. Dr. Martin Hepp, martin.hepp@unibw.de",
    "header": "Programmierung in Python",
    "showSlideNumber": "pdf",
    "slideNumber": "c/t",
    "theme": "chesterish",
    "transition": "none"
  },
  "toc": {
    "nav_menu": {},
    "number_sections": true,
    "sideBar": true,
    "skip_h1_title": false,
    "base_numbering": 1,
    "title_cell": "Table of Contents",
    "title_sidebar": "Inhaltsverzeichnis",
    "toc_cell": false,
    "toc_position": {
      "height": "calc(100% - 180px)",
      "left": "10px",
      "top": "150px",
      "width": "543.391px"
    },
    "toc_section_display": true,
    "toc_window_display": false
  }
```

## Open Issues ##
- The slide numbers do not show in the PDF version of the slides.
- I am still looking for a way to generate HTML-only versions of the presentations that preserve the reveal.js features. The standard output with `jupyter-nbconvert` or the respective menu option in Jupyter notebook is incomplete and breaks over some markup for reveal.js.
- I would like to include the date of creation as a version signature to the footer of PDF versions, but I have not yet figured out how. Using an f-String as the value for the `"rise: {"header": ...} value might work, but where will I put the datetime import?
- Need a way to generate an HTML version of the notebook that includes the numbering from the ToC extension, but not the ToC (or the ToC in the first cell).
- I would like to have the headline numbering for subsequent notebooks start at 2, 3, 4 ... respectively - is there a way to set this?
- When generating PDFs with `decktape`, there are a few errors regarding missing includes / 404s; what is the effect and how to solve this?
- I would like to have all fragments of a slide appear on a single PDF page, but RISE/decktape do not seem to pass the respective URI parameter.
- I need a mechanism to hide solutions from the tutorial in at least an HTML or PDF version, ideally managed via a generic tag or cell meta-data. The two available extensions for only in the ipynb view, neither in HTML export nor PDF.
- The font size varies with output resolution. This is a nuissance.
