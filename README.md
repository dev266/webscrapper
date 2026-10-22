# Quotes Scraper

A simple Python web scraping project that collects quotes from [Quotes to Scrape](https://quotes.toscrape.com/) and extracts quotes related to the **"life"** tag.

## Features

- Scrapes all available quote pages automatically
- Saves each webpage locally as an HTML file
- Stops when no more valid pages are found
- Reads the saved first page
- Extracts:
  - Quote text
  - Author name
  - Quote tags
- Filters quotes containing the `"life"` tag

## Technologies Used

- Python
- Requests
- BeautifulSoup
- lxml

## Installation

Install the required libraries:

```bash
pip install requests beautifulsoup4 lxml
```

## Project Structure

```text
quotes-scraper/
│
├── main.py
├── scraped_data/
│   ├── quotes1.html
│   ├── quotes2.html
│   └── ...
└── README.md
```

## How It Works

The program starts from page 1 of the website and continues requesting pages until no quotes are found.

```python
URL = f"https://quotes.toscrape.com/page/{page_count}/"
```

Each page is saved inside the `scraped_data` folder.

The program then reads the first saved page and checks the tags associated with every quote.

If the quote contains the `"life"` tag, the quote text and author are stored in a list.

Example output:

```text
[
    ["“There are only two ways to live your life...”", "Albert Einstein"],
    ["“Good friends, good books, and a sleepy conscience...”", "Mark Twain"]
]
```

## Purpose

This project was created to practice:

- Web scraping with Python
- Making HTTP requests
- Parsing HTML using BeautifulSoup
- Working with CSS selectors
- Reading and writing files
- Extracting structured data from websites

## Future Improvements

Possible improvements include:

- Extracting quotes from all downloaded pages
- Saving results to CSV or JSON
- Filtering by multiple tags
- Adding error handling for failed requests
- Creating a command-line interface for searching quotes
