# Website Summarizer using Ollama

A simple Python application that scrapes website content, summarizes it using a locally running LLM with **Ollama**, and generates a formatted **Markdown and PDF report**.

## Features

- **Website Scraping:** Extracts text from websites using BeautifulSoup.
- **Local AI Summarization:** Uses Ollama to summarize website content without paid AI APIs.
- **Markdown Generation:** Saves AI-generated summaries as `.md` files.
- **PDF Export:** Converts Markdown into a formatted PDF with headings, lists, and tables.

## Tech Stack

- **Python**
- **Ollama** — Local LLM inference
- **Qwen 2.5 (1.5B Instruct)** — Summarization model
- **BeautifulSoup** — Website scraping
- **Requests** — HTTP requests
- **Markdown + xhtml2pdf** — PDF generation

## Installation

**1. Clone the repository**

```bash
git clone <repository-url>
cd website-summarizer
```

**2. Install dependencies**

```bash
pip install requests beautifulsoup4 markdown xhtml2pdf
```

**3. Install Ollama and download the model**

```bash
ollama pull qwen2.5:1.5b-instruct
```

Make sure Ollama is running locally.

## Usage

Run the application:

```bash
python main.py
```

Enter a website URL when prompted:

```text
Enter URL: https://en.wikipedia.org/wiki/World_War_II
```

The application will scrape the website, generate an AI summary, and export the results.

## Output

```text
outputs/
├── output.md
└── output.pdf
```

## How It Works

```text
Website URL
     ↓
BeautifulSoup Scraper
     ↓
Extracted Website Text
     ↓
Ollama (Qwen 2.5)
     ↓
AI-Generated Summary
     ↓
Markdown File
     ↓
Formatted PDF
```

## Limitations

- JavaScript-rendered websites may not be scraped correctly.
- Large websites may exceed the model's context window.
- Summaries depend on the accuracy of the local LLM.
- Some complex Markdown formatting may not render perfectly in PDFs.

## Future Improvements

- Token-aware text chunking for large websites
- Support for JavaScript-rendered websites
- Improved article-content extraction
- Multiple summarization formats
- Web interface

## License

MIT License
