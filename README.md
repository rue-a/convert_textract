# textract2page

> Convert AWS Textract JSON to PRImA PAGE XML


## Introduction

This software converts OCR results from
[Amazon AWS Textract Response](https://docs.aws.amazon.com/textract/latest/dg/how-it-works-document-layout.html)
files to [PAGE XML](https://github.com/PRImA-Research-Lab/PAGE-XML) files.

## Installation

In a Python [virtualenv](https://packaging.python.org/tutorials/installing-packages/#creating-virtual-environments):

    pip install textract2page

## Usage

The package contains a file-based conversion function provided as CLI and Python API.
The function takes the Textract JSON file and the original image file which was used
as input for the OCR. (That is necessary because Textract stores coordinates in
`float` ratios, whereas PAGE uses `int` in pixel indices.)

### Python API

To convert a Textract file `example.json` for an image file `example.jpg` to a PAGE `example.xml`:

```python
from textract2page import convert_file

convert_file("example.json", "example.jpg", "example.xml")
```

### CLI

Analogously, on the command line interface:

    textract2page example.json example.jpg > example.xml
    textract2page -O example.xml example.json example.jpg

You can get a list of options with `--help` or `-h`

## Testing

(not yet)