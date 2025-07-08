# <span style="color:chartreuse">PDF Ingestion -> Tabular Data</span>
## <span style="color:yellow">Table of Contents</span>
>[**Python Libraries**](#python-libraries)
>
>[**ML Parsing Tools**](#ml-parsing-tools)
>
>[**Cloud Service SaaS Parsers**](#cloud-service-saas-parsers)
>
>[**Docling**](#docling)

## <span style="color:yellow">Python Libraries</span>
### <span style="color:orange">pdfplumber</span>
- entirely rule-based, zero ML -> this means you can extract tables if the pdf lacks lines, or the attributes don't quite line up with the labels

- No OCR support, meaning it cannot take scans or images
### <span style="color:orange">tabula-py</span>
- good for batch processing

- works well with well-structured pdf's only
### <span style="color:orange">PyMuPDF</span>
- processes pdf text, tables, and images

- fast, lightweight, customizable
## <span style="color:yellow">ML Parsing Tools</span>
### <span style="color:orange">LayoutLMv3 (HuggingFace Transformer)</span>
- open source

- extract tables and headers
- understand multi-columnar pdf's
### <span style="color:orange">PubLayNet</span>
- trained on academic pdf's

- detects elements well
- uses Detectron2 (Facebook object detection computer vision framework)
- seems to be a predecessor to Docling
### <span style="color:orange">Camelot</span>
- rule based, low level control

- good if there is a consistent structure in your document that is logically definable
- works well with pandas - can output to DataFrame
## <span style="color:yellow">Cloud Service SaaS Parsers</span>
### <span style="color:orange">AWS Textract</span>
- JSON output

- works exactly as you think a fully managed ML service would work
### <span style="color:orange">Azure Form Recognizer</span>
- prebuilt models for certain document styles, also customizable

- JSON output
### <span style="color:orange">Google Document AI</span>
- same capabilities as Azure

## <span style="color:yellow">Docling</span>
- PDF -> JSON or Markdown

- ML, less rules
- designed for ML training
- avoides OCR entirely -> just gives it to a comp vision model that turns it into a real pdf, then reads that