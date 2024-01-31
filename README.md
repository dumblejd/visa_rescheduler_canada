# What dumblejd changed
- update to apply to Canada condition
- update get_date and get_function to work as for 1/30/2024

## Prerequisites
- Having a US VISA appointment scheduled already
- Google Chrome installed (to be controlled by the script)
- Python v3 installed (for running the script)
- API token from Pushover and/or a Sendgrid (for notifications)

## This doesn't support group schedule

## Initial Setup
- Create a `config.ini` file with all the details required
- Install the required python packages: `pip3 install -r requirements.txt`
- update webdriver `pip install --upgrade webdriver_manager`

## Modify retry count number or other value if you want it to run longer/more frequent
 - `if retry_count > 18:`
 - STEP_TIME = 0.5  # time between steps (interactions with forms): 0.5 seconds
 - RETRY_TIME = 60*10  # wait time between retries/checks for available dates: 10 minutes
 - EXCEPTION_TIME = 60*30  # wait time when an exception occurs: 30 minutes
 - COOLDOWN_TIME = 60*60  # wait time when temporary banned (empty list): 60 minutes

## Executing the script
- Simply run `python3 visa.py`
- That's it!
