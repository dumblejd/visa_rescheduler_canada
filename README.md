

# What does this do?
- Reschedule US VISA in Canada facility
- Run every x minutes (by default 10 mins) to compare with the date you set in config.ini MY_SCHEDULE_DATE, if it's earlier than that, reschedule it
- Once recheduled, it will exit the program to avoid too many reschedule, if you want to run for earlier time, **remember to update MY_SCHEDULE_DATE to new date**

# What dumblejd changed
- Update for Canada condition
- Update get_date and get_time to work as for 1/30/2024

## This doesn't support group schedule

## People says for Canada US visa schedule, you can do max 20 reschedule, so be careful with that

## Prerequisites
- Having a US VISA appointment scheduled already
- Google Chrome installed (to be controlled by the script)
- Python v3 installed (for running the script)
- API token from Pushover and/or a Sendgrid (for notifications)



## Initial Setup
- Create a `config.ini` file with all the details required (don't create a txt file named config.ini, it doesn't work, the file type is ini)
- Install the required python packages: `pip3 install -r requirements.txt`
- Update webdriver `pip install --upgrade webdriver_manager`
- **Remember to update MY_SCHEDULE_DATE to correct/new date**

## Modify retry count number or other value if you want it to run more frequent
### if you set it run too frequent, you will get banned for hours from the website
 - STEP_TIME = 0.5  # time between steps (interactions with forms): 0.5 seconds
 - RETRY_TIME = 60*10  # wait time between retries/checks for available dates: 10 minutes
 - EXCEPTION_TIME = 60*30  # wait time when an exception occurs: 30 minutes
 - COOLDOWN_TIME = 60*60  # wait time when temporary banned (empty list): 60 minutes

## Executing the script
- **Remember to update MY_SCHEDULE_DATE to correct/new date**
- Simply run `python3 visa.py`
- That's it!


## Example log
```
['USVISA', 'CHROMEDRIVER', 'PUSHOVER', 'SENDGRID']

DevTools listening on ws://127.0.0.1:14984/devtools/browser/752f1e94-1bc1-4c6e-8949-39fbf143e0f1
Login start...
        click bounce
        input email
        input pwd
        click privacy
        commit
        login successful!
------------------
2024-01-30 20:47:58.902670
Retry count: 0

Available dates:
2025-03-12       business_day: True
2025-03-13       business_day: True
2025-03-14       business_day: True
2025-03-18       business_day: True
2025-03-20       business_day: True

Checking for an earlier date:
Is 2025-02-18 00:00:00 > 2025-03-12 00:00:00:   False
Is 2025-02-18 00:00:00 > 2025-03-13 00:00:00:   False
Is 2025-02-18 00:00:00 > 2025-03-14 00:00:00:   False
Is 2025-02-18 00:00:00 > 2025-03-18 00:00:00:   False
Is 2025-02-18 00:00:00 > 2025-03-20 00:00:00:   False

New date: None
going to sleep RETRY_TIME 600
```
