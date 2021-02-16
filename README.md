# Shopping Exercise with BDD Tests in Python with Flask and Sqlite3
A shopping example in python as a deliberate practice exercise

This is NOT a proper shopping site, but the back end of what one could be. It is missing the authentication and security aspects that you'd expect. The purpose of this is to let you explore how you retrieve and display the information that you want to show on the pages of the site.

The goal of 'deliberate practice' is to think about how you'd solve this challenge, and to work at developing code to make this work. There is no single 'correct' version of this code. The purpose of the exercise it become familiar with different ways of making the application work. You should explore how this simple application is done in Rails so that you understand how variables in controllers are show up in the views you see in the browser.

Under 'deliberate practice' we offer up the challenge, then think about options for developing a solution, and code for 12 minutes. After that we pause to discuss how people are approaching the problem, and what they're trying to do. This should be repeated three times and then wrapped up with time for people to express what they found most useful during the session. This should take an hour.

## Set up the Repository
Pull this Git repository into your system so that you have everything to get started.

We need to start by setting up our development environment by executing these commands in the terminal, that's open in the diretory were we've cloned this repo.

        pyenv local 3.7.0 # this sets the local version of python to 3.7.0
        python3 -m venv .venv # this creates the virtual environment for you
        source .venv/bin/activate # this activates the virtual environment
        pip install --upgrade pip [ this is optional]  # this installs pip, and upgrades it if required.

We can now add in some random content for the shopping application using the Faker library from https://pypi.org/project/Faker/.Install Faker with the command: 

        pip install Faker

Now we can set about changing the values from Faker if you want. Go to https://faker.readthedocs.io/en/stable/providers.html and look through the options for Standard Providers to see if you want to change any details in values used in setup_db.py.

We can now add the testing library Behave, along with Selenium for and the appropriate web drivers for your system, which you can find at https://selenium-python.readthedocs.io/installation.html#drivers 

If you're on a Mac, then you will need to remove the chrome driver from quarantine with the command

        xattr -d com.apple.quarantine <name-of-executable>

as found and detailed at https://stackoverflow.com/questions/60362018/macos-catalinav-10-15-3-error-chromedriver-cannot-be-opened-because-the-de 

You might want to look at the documentation for Behave https://behave.readthedocs.io/en/latest/ 
You should look at Selenium documentation for [navigating web pages] (https://www.selenium.dev/selenium/docs/api/py/webdriver_remote/selenium.webdriver.remote.webdriver.html#module-selenium.webdriver.remote.webdriver)

        pip install flask
        pip install behave
        pip install selenium

## Setting up the Exercise
Run the setup_db.py file to create the tables, and load the generated data into your tables.

Load the application settings into your terminal and start the server with 

        export FLASK_APP=shopping.py 
        export FLASK_ENV=development
        python3 -m flask run 

## Check the tests

You can run the current tests to see that the customer pages load, with the command

        behave

in the terminal. 

##  Doing the Work

Work through the three rounds with a partner, or on your own, depending upon your circumstances. Each round should be twelve minutes, followed by a discussion of where you are and what has been working, as well as, what you're working on next.

You may want to refer to the setup_db.py file to understand the database schema before you get started. Some of you might even want to diagram the schema. 

You might also want to spend a few minutes at the start of each round planning what you might want to do.

You'll see that this version works with SQL queries and statements to manipulate the data we display on the page. This means we're working with tuples returned to us from the database, which force us to do things in certain ways. You can see this in the html pages that display the data. Look at the SQL python documentation page for more details https://docs.python.org/3/library/sqlite3.html

1. Round one should be fixing the tests so that they run. Your random data will differ, so a few changes are necessary.
2. Round two should be creating similar tests for the orders pages.
3. Round three is adding a small input feature: search for a given name or order number perhaps.
4. Round four, would apply Python models to tuck the SQL away from the main application, and remove some of the duplication. 

