# <span style="color:chartreuse">PDF Ingestion -> Tabular Data</span>
## <span style="color:yellow">Table of Contents</span>
>[**Python Libraries**](#python-libraries)
>
>[**ML Parsing Tools**](#ml-parsing-tools)
>
>[**Cloud Service SaaS Parsers**](#cloud-service-saas-parsers)
>
>[**Docling**](#docling)
>
>[**Most Important Takeaways**](#most-important-takeaways)

## <span style="color:yellow">Python Libraries</span>
### <span style="color:orange">pdfplumber</span>
- extracts text, tables, and images
- **can be** entirely **rule-based**, meaning you can extract tables if the pdf lacks lines, or the attributes don't quite line up with the labels

- **No OCR support**, meaning it cannot take scans or images
### <span style="color:orange">tabula-py</span>
- extracts tables only
- can **output tables** as csv, json, tsv, OR as a **pandas DataFrame**, which is a huge advantage

- **No OCR support**
- Prone to fail if pdf lacks clear structure. However, there are some low-level functions that can maybe fix this.
### <span style="color:orange">PyMuPDF</span>
- extracts text, tables, and images from a variety of file types besides pdf

- output markdown, pdf, DataFrame, etc.
- **fastest runtime** -> good for batch processing
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
- can output to DataFrame
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

## <span style="color:yellow">Most Important Takeaways</span>
- all of these tools can output to DataFrame except Docling
- PyMuPDF is the only tool here that can read a pdf AND write a pdf. The other ones can only read and extract data

- pdfplumber and PyMuPDF do OCR by outsourcing it to Tesseract OCR. The other tools cannot handle OCR. AMazon Textract has it built in.
- if you need output to pdf, you can use reportlab