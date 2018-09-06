The Markdown to Jupyter Conversion tool (MTJC) is a fairly simple script that converts a markdown file with code blocks to the JSON format used by [Jupyter](https://jupyter.org/) to create [Notebooks](https://jupyter-notebook.readthedocs.io/en/stable/).

MTJC separates the provided markdown file into "cells", looking for headers and code blocks to split the content at. Each header and any following text, list, or whatever will be placed in the same block until either another header or a code block ("```") is encountered.

When a code block is encountered, it writes the code to a file in .temp (relative to the folder it is run in), passes it to the relevant program to run, and stores the result.

## Limitations

- Currently, this script can only process Python. I plan to change this, but as I have no use for any of the other possible languages myself, it is not high on my agenda.
- This script assumes that all output from a Python script will be sent to stdout. It is not currently capable of processing image data such as the charts and graphs that Jupyter Notebooks are capable of displaying.

## Installation

Assuming that you have already installed [npm](https://www.npmjs.com/), in the command line, type either one of the following:

### NPM

```bash
npm install -g mtjc
```

### From Source

```bash
git clone https://github.com/TheAndroidMaster/MarkdownToJupyter
cd MarkdownToJupyter
npm install
```

## Usage

```
mtjc <file.md>
```

Or, to specify a path for the output file...

```
mtjc <file.md> <output.ipynb>
```
