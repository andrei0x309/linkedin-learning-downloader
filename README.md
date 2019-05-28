<img src="https://i.imgur.com/TkbiSQY.png" width="175" align="right">

# Linkedin Learning Downloader
[![built with Requests](https://img.shields.io/badge/built%20with-Requests-yellow.svg?style=flat-square)](http://docs.python-requests.org)
[![built with Python2.7](https://img.shields.io/badge/built%20with-Python2.7-red.svg?style=flat-square)](https://www.python.org/)

### A scraping tool that downloads video lessons from Linkedin Learning
Features:
* Implemented in python using requests.
* Downloading complete courses, i.e. course description inkl. original course url, videos, exercise files, subtitles.
* Easy adding of courses to download list
* Skipping existing downloads and completing incomplete courses.
* Unchecking of successfully downloaded courses on your download list, therefore providing some kind of archive.
* Numbering of chapters, videos and subtitles.
* Subtitles will have the same name as the video file, so players like MPC-HC will automatically load the subtitles when playing a video file.
* Course folder includes release date, because courses sometimes get updated and you don't know which version you already downloaded.

### How to use
First install the requirements:
```
pip install -r requirements.txt
```
The `config.py` looks like this:
```
USERNAME = 'user@email.com'
PASSWORD = 'password'
BASE_DOWNLOAD_PATH = 'E:/Downloads/LinkedInLearning' #use "/" as separators

COURSES = [
    'it-security-foundations-core-concepts',
    'javascript-for-web-designers-2'
]
```

1. Enter your login info and download path.

2. You have two ways to add courses:

   a. New way: Just add them via LinkedIn (app or browser) to your bookmarks. The tool will parse your LinkedIn bookmarks (https://www.linkedin.com/learning/me/saved) at runtime.

   b. Old way: Fill the `COURSES` array with the slug of the the courses you want to download and save the config file, for example:
`https://www.linkedin.com/learning/it-security-foundations-core-concepts/ -> it-security-foundations-core-concepts`

The app will add the parsed bookmarks to the config file after checking for duplicates.
You use both methods parallel. 

*Skipping existing downloads:* 
If you already downloaded a course, the app will check the Download Path for existence of each to-be-downloaded-course and all subfolder and files, thus excluding duplicates. Files (couse-videos, exercise files, subtitles or course descriptions) which do not exist will be downloaded and therefore complete an unfinished course.

*Unchecking downloaded courses:*
After successfully downloading a course, the course will be disabled in the config file (Download list) by putting a "#" in front of the course. If you want to check courses for integrity again, just remove the "#" and the next time when running the app it will check the enabled courses (see above).


Then execute the script:
```
python lld.py
```
The courses will be saved in your defined download folder.

## You shoud read this

**This fork has small changes to ensure the script still works I used it on 27/May/2019 with a trial premum account it should work with any premium account.**

[![screenshot](https://lh3.googleusercontent.com/UJPLBAwXsirwhcJgdGYH2A-xnb4ButevPniuzmM5UOTjidl9vZp4zNrwE0tzZwQj2sWZhNCmutlSVi0mWGwzS7SUz67w82LkvnrR-AFyhwgTNczM8pbgHV9T7ATd0KAH-F-p2ar4z5x0Eyr5dQRQMOElNegCj8U1LmAgyF8OfFwfAWUidhLPYM9BYkqBfLc2oqUUjAAbGCF-crSIzdIXzzKzscdEaxRLYhH30Y7X40i00dlYiuDoL7f8gKcc_h-cRIpWGTKEyRXH0O42ZvpVq5Ztg4t3SEajokBwIGQzorlzZ2lD7G7yBoGVZ18KQFOzdyMgsB68IQF57LjpCb5RDee4ssjcWAtxeNiFyEGOJRI29iKsbIQOoDtYV_DeJCvaOYIWjj3pMA_tq6_fflPj0FiV5NvM78KhoDsOgB0xpwqXu-uMnq5uVpf1X8znz7Drt4Cpd3758lp2VHsOBRPYkYy8-TpJag7tGyK0ngYNk20l6GhVxGoQ3lXVwYN1oyCgWyjMJX0wvM3BLceZLJr3noeIU9X-Csag-FM1HljgHujDTKqgklLo3dF1AZx2pKNFCa03H5dFWoIlpKn4OY2KXW_0p3UxoQ-pOM8PEPqFHvQDDgQb7ayKanHi-rdHxVuS_C5X97YdnsqG50Rtes_uZt1DHvzGdZdg=w1024-h576-no)](https://photos.google.com/u/2/album/AF1QipPiSx514RySisMs2aiPpLO-QCkbWhvEh8IIBAHX/photo/AF1QipP9RsBv4pjHK4AI0Ybf0dmfZ47pNqc12UsTmBUF)

---
###### Have Fun & Feel Free to report any issues
---
