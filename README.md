# Blinkist Scraper
IMPORTANT: Please do consider the legal and moral implications of using this script
### File formats
This program downloads books from Blinkist.
To be precise, it saves…
- the (almost) raw API responses
  - as YAML
  - This includes things like categories or ratings which are not saved elsewhere.
- the text version
  - as Markdown
- the audio version
  - as one M4A file per chapter (no modifications)
- the cover image
  - as JPEG (no modifications)
  - in the highest resolution available (1080×1080)
### Book selection
- `--book-slug`: the book slug (e.g. `get-smart-en`)
  - ⚠️ As of writing, no authentication is required to access _any_ book, a benefit which _should_ require a subscription _in theory_. Do consider the legal and moral implications of using this.
- `--freedaily`: Each day, Blinkist offers a free book for each locale.
  - [Website (en)](https://www.blinkist.com/en/content/daily)
- `--freecurated`: There are some curated lists of books, which in turn are free.
  - for example: [“Expert Picks: Elon Musk” (de)](https://www.blinkist.com/de/content/collections/expert-picks-elon-musk)
- 🛈 If you pass multiple of these options, all of them will be used.

## Installation

```bash
# First, clone the repository

# Then, install the dependencies
$ pip install -r requirements.txt
```

## Usage
Just run the [`main.py`](main.py) executable, stating what to download and providing a path to a “library directory”, where every book will be saved in its own subdirectory.
Here's an example:
```bash
$ ./main.py --freedaily ~/Library/Blinkist
```
For an overview of all CLI options, see `main.py --help`.
For other options, you need to modify [`blinkist/config.py`](blinkist/config.py) to your needs.
