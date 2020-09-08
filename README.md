# LinkedIn Scraping with Python

Create an Excel file containing personal data and last job position of specified people.

Scraping can be currently done only providing the LinkedIn profile url of the target person. If you don't have yet the LinkedIn profile urls


## Prerequisites

You must have installed in your machine:
* Google Chrome (last version)
* Python (last version)


## Installing

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

1. Download the whole repository.
2. Place the directory `LinkedinScraping` in your python environment.
3. Navigate to the directory `LinkedinScraping` and run the following:
```
pip install -r requirements.txt
```
4. Run `LinkedinScraping\configurator.py` following the prompted instructions.
 

If this is the first time, choose the suggested configuration.
In any time in the future you can easily run again the configuration to apply changes.

## Executing

There are two ways you can run the code: headless execution and normal one.

In both cases, be careful (especially when you scrap a lot of profiles) because your computer may enter sleep mode. In sleep mode the scraping could not work. 

### Normal execution
In this mode the script will do scraping opening a real Chrome window.

**Pros:** In this case you will be able - if prompted - to satisfy the Captcha check and to proceed the scraping: the python script is trained on this situation and will perfectly manage it alerting you.

**Cons:** Be aware that if you choose this mode you can not loose the focus on the window, otherwise no data will be scraped.

To run in normal mode:
```
python do_scraping.py
```

### Headless execution(Not working curently)
In this mode the script will do scraping without opening a real Chrome window.

**Pros:** The scraping process is distributed into many threads to speed up to 4 times the performance. Moreover, in this way you can keep on doing your regular business on your computer as you don't have to keep the focus on any specific window.

**Cons:** If you scrap many profiles (more than hundreds) and/or in unusual times (in the night) LinkedIn may prompt a Captcha to check that you are not a human. If this happens, there is no way for you to fill in the Captcha. The script will detect this particular situation and terminate the scraping with an alert: you will have hence to run the script in normal mode, do the captcha, and then you can proceed in scraping the profiles that were left.

To run in headless mode:
```
python do_scraping.py HEADLESS
```

### Examples

LinkedIn URLs:
```
https://www.linkedin.com/in/federicohaag/
https://www.linkedin.com/in/someoneelse/
```

When the Chrome page closes, it means the program ended.
You can find inside the `LinkedInScraping` folder the extracted data in the results file `results_profiles.xlsx`.
The filename will get concatenated to the current timestamp if the configuration was set as suggested.


## Common problems in Running

### Human check freezing the scraping
It may happen that while scraping the script will warn you about the need to perform a Human Check (a Google Captcha) even if it's not prompted for real.

This happens when you inserted in the input file a Profile URL which is not correctly formatted.

Here some tips:
* The profile URL should always end with `/`
* Open a browser window and navigate to such URL. Wait for the page to load. Is the URL currently in the browser navigation bar the same as the one you initially inserted? If not, you should insert in the input file the one you see now at the navigation bar.


## Legality of Scrapping

https://www.forbes.com/sites/emmawoollacott/2019/09/10/linkedin-data-scraping-ruled-legal/#14d7dbd91b54
