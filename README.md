# FileSure-Assessment
# extractor.py

This repository contains a Python script, `Extractor.py`, which is designed to extract and summarize important information from PDF files. The script uses various libraries and a pre-trained model for summarization.

## Features

- **PDF Extraction**: Extract data from PDF files using Python libraries.
- **Regex for Extract**: Use regular expressions (regex) to extract data.
- **JSON Conversion**: Convert the extracted data into a structured JSON format.
- **Attachment File Handling**: Extract and gather important values from attachment files.
- **Text Summarization**: Use Facebook's pre-trained BART model (`facebook/bart-large-cnn`) to summarize the extracted data.
- **Summary Generation**: Summarize the extracted information.

## Requirements

Before running the script, make sure to install the necessary libraries:

```bash
!pip install torch transformers
!apt-get install -y poppler-utils
!pip install pytesseract pdf2image
!pip install PyMuPDF
!pip install PyPDF2
```
## Script Overview
1. Import Libraries
The script imports the necessary libraries, including:
- `PyPDF2`: For PDF extraction.
- `re `(Regex): For pattern matching and extracting address data.
- `json`: For creating JSON output.
- `torch`, `transformers`: For using the pre-trained BART model for text summarization.
- `pytesseract`, `pdf2image`: For OCR and image processing within PDFs.
- `PyMuPDF`: For handling PDF structure and extracting content.
2. Define PDF Path
Specify the file path of the PDF you want to extract data from.
3. Widget Interface `.widgets()`
The script uses a widget interface to interact with the PDF file and provide a simple user interface for extraction.
4. Regex to Extract Address
Using regular expressions, the script identifies and rearranges address fields in the extracted text for proper formatting.
5. Convert to JSON
Once the data is parsed, it's converted into a JSON structure for easy storage and retrieval.
6. Attachment File Processing
The script processes attachments within the PDF, extracting relevant information and preparing it for summary.
7. Text Summarization with BART
Finally, the script uses the `facebook/bart-large-cnn` model from Hugging Face's transformers library to summarize the extracted text into a short, readable format.
## Running the Script
To run the `extractor.py` script, simply execute it using Python:
```python
python extractor.py
```
## Example JSON Output
```json
{
  "company_name": "ALUPA FOODS PRIVATE LIMITED",
  "cin": "U74999KA2016PTC095981",
  "registered_office": "DHANYALAXMI RICE MILL, 5-110A, PUTTUR, UDUPI Udupi Karnataka 576105",
  "appointment_date": "29/08/2022",
  "auditor_name": "MALLYA & MALLYA",
  "auditor_address": "29/2, 1st Floor, Parijatha Complex",
  "auditor_frn_or_membership": "001955S",
  "appointment_type": "New Appointment or Reappointment"
}
```
## Model Summarization Example
```vbnet
Summary 2:
Consent to act as statutory auditors of M/s Alupa Foods Private Limited. Certificate pursuant to Section 139 of the Companies Act, 2013. No proceedings against our firm or any partner of our firm is pending with respect to professional matters of conduct. We are eligible for appointment as statutoryauditors and satisfy the criteria as provided under the Act.
```
