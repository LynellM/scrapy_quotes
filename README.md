# scrapy_quotes

A [Scrapy](https://scrapy.org/) spider that crawls [quotes.toscrape.com](http://quotes.toscrape.com/) and collects every quote's author and text, following the "Next" link through all pages.

Forked from [cavalryjim/scrapy_quotes](https://github.com/cavalryjim/scrapy_quotes).

## Requirements

- Python 3.9+
- [pipenv](https://pipenv.pypa.io/)

## Setup

```bash
pipenv install
```

## Usage

Run the spider and write the results to a file (`-O` overwrites, `-o` appends):

```bash
pipenv run scrapy crawl quotes -O quotes.json
pipenv run scrapy crawl quotes -O quotes.csv
```

Each item looks like:

```json
{"author": "Albert Einstein", "text": "The world as we have created it is a process of our thinking. ..."}
```

A full crawl returns 100 quotes across 10 pages.

## Project layout

```
scrapy.cfg                     # Scrapy project config
quotes/
  settings.py                  # Crawler settings
  items.py, pipelines.py,      # Scrapy defaults (unused)
  middlewares.py
  spiders/quotes_spider.py     # The spider
quotes.json, quotes.csv        # Sample output
```
