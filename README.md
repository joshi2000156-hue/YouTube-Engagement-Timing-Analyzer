# YouTube Upload Strategy Analyzer

## Overview

This project analyzes YouTube video data to recommend the best time to upload videos for maximum engagement. It collects real data using the YouTube Data API and analyzes patterns in upload time and views.

## Problem

Content creators often struggle to determine the best time to upload videos. Uploading at the wrong time may reduce visibility and engagement.

## Solution

This project analyzes videos related to a given topic and determines which upload hours and days historically receive the highest engagement.

## Features

* Collects video data using YouTube API
* Converts timestamps from UTC to Indian Standard Time
* Calculates engagement score based on view growth rate
* Recommends best upload day and hour

## Technologies Used

* Python
* pandas
* requests
* YouTube Data API v3

## Installation

Clone the repository:

```
git clone https://github.com/YOUR_USERNAME/youtube-upload-strategy-analyzer.git
```

Install dependencies:

```
pip install -r requirements.txt
```

## Setup API Key

Create an API key using Google Cloud Console and enable the YouTube Data API v3.

Then open `config.py` and replace:

```
API_KEY = "YOUR_API_KEY_HERE"
```

## Running the Project

Run:

```
python main.py
```

Example input:

```
Enter video topic or niche: gaming edits
```

Example output:

```
Recommended Upload Strategy
Best Upload Hour: 16:00
Best Upload Day: Thursday
```

## Methodology

1. Fetch video data from the YouTube Data API.
2. Extract upload timestamp and view count.
3. Convert timestamps to Indian Standard Time.
4. Calculate engagement score:

```
engagement_score = views / days_since_upload
```

5. Group videos by upload hour and day using pandas.
6. Recommend the time slot with highest engagement.

## Limitations

* Only a limited number of videos are analyzed
* Channel popularity is not normalized
* Results depend on YouTube search results

## Future Improvements

* Use machine learning for prediction
* Analyze likes and comments
* Normalize by subscriber count
* Create visualization dashboard

## Author

Pranav Joshi
