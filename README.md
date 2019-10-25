# Propgramming in Python Course Materials

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

### Presentation Mode ###
In order to present the slides, simply click on the RISE icon (tiny barchart) inm Jupyter Notebooks.
Set your browser to full-screen mode.

### Generate PDFs ###
First, you need to fetch the session ID for you running Jupyer Notebooks process. This can be found in the terminal window in which it is running. Find this section:<br />


<code>
    To access the notebook, open this file in a browser:<br />
        file:///Users/...<br />
    Or copy and paste one of these URLs:<br />
        http://localhost:8888/?token=6dfjsdja3c75f6bc21d5c2a7891774b3fc540ca2615765eb6c5
</code>

Then, generate a PDF using

`$ decktape rise <URI_of_your_presentation>?token=<token_from above> <filename.pdf>`

