# Python Logging
Properly logged messages help you debug and track errors within your application. Python makes it simple to create a logger than handles both logging to the console and to a file. This example will work in both Python2.7 and Python3.X.

## Example Python Logging
```py
# Import the python logging library
import logging

# Create a new logging object called logger and give it the name 'simple_example'
logger = logging.getLogger('simple_example')

# Set the logger's level to DEBUG, meaning it will log all message severities
logger.setLevel(logging.DEBUG)

# Create a Logging Filehandler, which will save these log entries to a file 'example.log'
fh = logging.FileHandler('example.log')
# This will save logs of DEBUG or higher to 'example.log'
fh.setLevel(logging.DEBUG)

# Create a console logger, so that log messages will be printed to the screen
ch = logging.StreamHandler()
# Set the logger level to ERROR meaning that both ERROR and CRITICAL logs will be printed to the screen
ch.setLevel(logging.ERROR)

# Create a format string for the logger, to include needed information
# More information on logging formats can be found here - https://docs.python.org/3/howto/logging.html#formatters
formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')

# Set each of the loggers to the new format we created
ch.setFormatter(formatter)
fh.setFormatter(formatter)

# Add the log handlers we created to the logger
logger.addHandler(ch)
logger.addHandler(fh)

# Testing the Logger
# Will write "debug message" to the 'example.log' file
logger.debug('debug message')

# Will write "info message" to the 'example.log' file
logger.info('info message')

# Will write "warn message" to the 'example.log' file
logger.warn('warn message')

# Will write "error message" to the 'example.log' file and print it to the console
logger.error('error message')

# Will write "critical message" to the 'example.log' file and print it to the console
logger.critical('critical message')
```
