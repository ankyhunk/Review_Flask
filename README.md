# Review Flask

A small Flask web app that scrapes customer reviews for a product from [Flipkart](https://www.flipkart.com) and shows them in a table.

Type a product name (for example "iphone 13"), and the app:

1. Searches Flipkart for the product
2. Opens the first result
3. Collects each review's customer name, rating, heading and comment
4. Shows the reviews on a results page

## Project structure

```
app.py               # Flask routes and the scraper
templates/
  index.html         # Search page
  results.html       # Reviews table
static/css/          # Styles
iphone*.csv, samsung.csv   # Sample scraped output
Procfile, runtime.txt      # Heroku deployment settings
```

## How to run

```bash
pip install -r requirements.txt
python app.py
```

Then open <http://127.0.0.1:5000> in your browser.

## Notes

- The scraper depends on Flipkart's page layout and CSS class names. Flipkart changes these from time to time, so if no reviews come back, the class names in `app.py` need updating.
- Reviews whose comment can't be read are shown as "No Comment" instead of stopping the whole page.

## Technologies

Python, Flask, Flask-CORS, Requests, Beautiful Soup, gunicorn (deployment)
