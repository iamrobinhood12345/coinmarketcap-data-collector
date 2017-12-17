CoinMarketCap Data Collector
=====================================

Collecting data from https://coinmarketcap.com/

Concept
----------------

Endpoints are published on coinmarketcap every five minutes and requests are limited to ten per minute (https://coinmarketcap.com/api/). In order to collect this data we use the Python BeautifulSoup and Requests library. To collect the data repeatedly we implement a crontab that runs a bash script (cmc_scrp_run.sh) that activates a virtual environment and then runs the python script (cmc_scrp.py).

Requirements
-------

Python3

Build
-------

### Virtual environment

```
python3 -m venv env
```

### Pip

```
pip install -r requirements.txt
```

### Run

```
python3 cmc_scrp.py
```

If you want to run the script every five minutes,

### Crontab

```
crontab -e
```

Paste

```
*/5 * * * * cd rootpathtodirectory && sh cmc_scrp_run.sh >/tmp/stdout.log 2>log 2>/tmp/stderr.log
```

Crontab logs sent to /tmp/stdout.log and /tmp/stderr.log

The Data
-------

Data is created in scrp/data.

### Format

.csv

### Columns

symbol,ranking by market cap,name,market cap,price,circulating supply,volume,% 1h,% 24h,% 1wk

-----------

Please feel free to fork. If you have any questions or want more information, please email me at bshields23@gmail.com. Past performance is no guarantee of future returns!
