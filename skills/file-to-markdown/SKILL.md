---
name: file-to-markdown
description: Convert any file to markdown format using the markitdown library. Use this skill when users need to convert documents (PDF, DOCX, XLSX, PPTX, images, HTML, CSV, JSON, XML, audio files, etc.) into markdown format for easier reading, editing, or integration into markdown-based workflows.
---

# File to Markdown Converter

## Overview

This skill enables conversion of various file formats to markdown using the markitdown library. It supports a wide range of formats including office documents, PDFs, images, audio, and structured data files.

## Supported File Formats

The markitdown library supports:
- **Documents**: PDF, DOCX, PPTX, XLSX
- **Web**: HTML, MHTML
- **Images**: PNG, JPG, JPEG, GIF (with OCR and image description)
- **Audio**: MP3, WAV (with transcription)
- **Data**: CSV, JSON, XML
- **Archives**: ZIP
- **Other**: Plain text files

## Installation

Before using this skill, ensure markitdown is installed:

```bash
pip install markitdown
```

For full functionality including image and audio processing:

```bash
pip install markitdown[all]
```

## Basic Usage

### Converting a File

Use the provided script to convert any file to markdown:

```python
from markitdown import MarkItDown

# Initialize the converter
md = MarkItDown()

# Convert a file
result = md.convert("path/to/file.pdf")

# Access the markdown content
markdown_text = result.text_content

# Save to a file
with open("output.md", "w", encoding="utf-8") as f:
    f.write(markdown_text)
```

### Using the Helper Script

The skill includes `scripts/convert_file.py` for quick conversions:

```bash
python scripts/convert_file.py input_file.pdf output.md
```

## Advanced Features

### Batch Conversion

Convert multiple files at once:

```python
from pathlib import Path
from markitdown import MarkItDown

md = MarkItDown()

# Convert all PDFs in a directory
for pdf_file in Path("input_dir").glob("*.pdf"):
    result = md.convert(str(pdf_file))
    output_file = f"output/{pdf_file.stem}.md"
    with open(output_file, "w", encoding="utf-8") as f:
        f.write(result.text_content)
```

### Image Processing

For images, markitdown can:
- Perform OCR to extract text
- Generate image descriptions using vision models
- Preserve image references in the markdown

### Audio Transcription

Audio files are automatically transcribed to text and formatted as markdown.

### Structured Data

CSV, JSON, and XML files are converted to markdown tables or formatted text structures.

## Error Handling

Always handle potential errors during conversion:

```python
from markitdown import MarkItDown

md = MarkItDown()

try:
    result = md.convert("input_file.pdf")
    if result and result.text_content:
        print(result.text_content)
    else:
        print("No content extracted from file")
except Exception as e:
    print(f"Error converting file: {e}")
```

## Common Use Cases

1. **Document Migration**: Convert legacy documents to markdown for version control
2. **Content Extraction**: Extract text from PDFs or images for processing
3. **Documentation**: Convert various formats to markdown for documentation systems
4. **Data Analysis**: Convert structured data files to readable markdown tables
5. **Accessibility**: Convert images and audio to text-based markdown

## Tips

- For best results with images, ensure adequate lighting and clear text
- Audio files should have good audio quality for accurate transcription
- Large files may take longer to process
- Some complex formatting may not be perfectly preserved in markdown
- Test with sample files first for critical conversions

## Resources

### scripts/
- `convert_file.py`: Command-line tool for single file conversion
- `batch_convert.py`: Batch conversion utility for directories

### references/
- `markitdown_api.md`: Complete API reference for markitdown library
- `format_guide.md`: Format-specific conversion tips and limitations



