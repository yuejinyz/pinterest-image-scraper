# Pinterest Image Scraper
### Guide 2.0 for Chrome Users Only
### modified by Yue

Now you can take the URL to any Pinterest board (or a CSV of a bunch of boards) and return a Python list of the URLs to the hi-rez versions of all of the images on the board.

## Requirements:

- Python 3.5+ ([Anaconda](https://anaconda.org) recommended)
- Pandas (pip install pandas or conda install pandas)
- [Firefox](https://www.mozilla.org/en-US/firefox/new/) + [Gecko driver](https://github.com/mozilla/geckodriver/releases) (Firefox can be omitted if you know what you're doing and have another browser set up to be used via Selenium)
- Selenium (```pip install selenium``` or ```conda install -c conda-forge selenium```, then see [these instructions](https://pypi.python.org/pypi/selenium/3.9.0) for installing the Gecko driver if not installing it from Conda)
- Alternatively, install the Gecko driver using conda: ```conda install -c conda-forge geckodriver```
- If you want to use Chrome or PhantomJS, install their respective selenium drivers: ```conda install python-chromedriver-binary phantomjs```
- A [Pinterest](http://www.pinterest.com) Account

Try this: ```pip install webdriver-manager```

## How to Run:

```
git clone https://github.com/xjdeng/pinterest-image-scraper.git
cd pinterest-image-scraper
pip install -U .
cd ..
python
from selenium import webdriver
from webdriver_manager.chrome import ChromeDriverManager
driver = webdriver.Chrome(ChromeDriverManager().install())

from pinterest_scraper import scraper as s
ph = s.Pinterest_Helper(<Pinterst login> , <Pinterest password>, driver)
images = ph.runme("http://URL-to-image-board")
```
Note: type key words you want to search and get URL.

### Or if you have a CSV file with a URL to a different image board on every line:

```
images = ph.getURLs(imageboards.csv)
```

### Now if you want to download these images:

```
s.download(images, "/path/to/your/destination/dir")
```

### or to download to your current directory:

```
s.download(images)
```

