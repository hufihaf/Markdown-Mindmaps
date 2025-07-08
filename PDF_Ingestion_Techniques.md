# PDF Ingestion -> Tabular Data
## Table of Contents

## Python Libraries
### pdfplumber
- entirely rule-based, zero ML -> this means you can extract tables if the pdf lacks lines, or the attributes don't quite line up with the labels

- No OCR support, meaning it cannot take scans or images
### tabula-py
- good for batch processing

- works well with well-structured pdf's only
### PyMuPDF
- processes pdf text, tables, and images

- fast, lightweight, customizable
## ML Parsing Tools
### LayoutLMv3 (HuggingFace Transformer)
- open source

- extract tables and headers
- understand multi-columnar pdf's
### PubLayNet
- trained on academic pdf's

- detects elements well
- uses Detectron2 (Facebook object detection computer vision framework)
### Camelot
- rule based, low level control

- good if there is a consistent structure in your document that is logically definable
- works well with pandas - can output to DataFrame
## Cloud Service SaaS Parsers
### AWS Textract
- JSON output

- works exactly as you think a fully managed ML service would work
### Azure Form Recognizer
- prebuilt models for certain document styles, also customizable

- JSON output
### Google Document AI
- same capabilities as Azure