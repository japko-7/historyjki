# LAB5 - API - Welcome

##What is it?
It is an API made to serve sales and forex data. It's based on NBP's (http://api.nbp.pl/) data and uses a mock database to present its capabilities.

##Technologies
To make it simple, only simple technologies. These include:
* Python programming language (version 3.7.4 or higher)
* Flask framework - https://flask.palletsprojects.com/en/1.1.x/ - an API service framework
* Flask-Limiter - https://flask-limiter.readthedocs.io/en/stable/ - a server-load limiter extension to Flask
* sqlite3 - https://www.sqlite.org/index.html - a database engine
* requests - https://requests.readthedocs.io/en/master/ - an API client framework (to obtain data from NBP's database)

##How can I get it working?
1. Start with obtaining python (it comes preinstalled with MacOS) - if you don't have it yet, you can download and install from https://www.python.org/dwonloads/. Remember to get 3.7.4 or higher. It should come together with pip - it's a package manager that enables you to download all the other necessary libraries.
2. Check your python installation with python --version in your command line. Also, check pip using a  similar command, `pip --version`. If somehow pip doesn't seem be there, you can get it following instructions on https://pip.pypa.io/en/stable/installing/.
3. Now you can proceed to obtaining specific packages. Use `pip install {library_name}` for each one that you miss. You can list already installed packages launching python in command line (simply with `python`) and running `help("modules")`.
4. Once you've gone thru the installation process, you can launch the application with a command `python main.py`. Make sure to go into the installation (or cloned repo) directory first, or use a global file path instead, e.g. `~/documents/LAB5/main.py`.
5. If it's running properly, you'll be able to see in the console where the service is running - typically it's `localhost:5000`. What's more, in the console it's about to appear every single request made to the API.
6. That's it! Go to `localhost:5000` and check it.

##How do I use it?
There are actually 2 ways of using it.
* Get currency markings - it uses the `/api/v1/exchangerates/` URI
* Get currency markings - it uses the `/api/v1/salesdata/` URI
Apart from that you can also visit homepage (`/`) or ping (`/ping`) the API to check if it's responding

###Getting currency markings
You can request available forex tables in various configurations
* is a base link for requesting all currencies at once


###Geting sales data
* asdfsdfsf

##Possible response formats
*
*

##Possible error messages
*
*

##Deeper configuration
In scripts `currency_API.py` and `database.py` a wide variety of commands can be found, so that you can use them combined together in order to provide other currency data or even another database. Just place the function calls in `main.py` near (or instead of) basic configuration. Furthermore, in the `api.py` file following preferences might be changed:
* `TABLES_URI` - this represents the URI used for currency requests
* `RATES_URI` - this represents the URI used for specific currency requests
* `SALES_URI` - this represents the URI used for sales requests
* `DAILY_LIMIT`,  `MINUTE_LIMIT` - examplary limits, used together few lines below in `default_limits = [DAILY_LIMIT, MINUTE_LIMIT]` - it can be any value following  the rule: [count] [per|/] [n (optional)] [second|minute|hour|day|month|year]; defaults are `200 per day` and `30 per minute` per an IP address
* `CACHE_LIFETIME` - how long [in seconds] the calculated sales data is supposed to be cached on the API server; default is `120`
