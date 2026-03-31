# YouTube Upload Strategy Analyzer

## Project Overview

This project analyzes YouTube video metadata to determine optimal upload times for maximizing engagement. By examining patterns in video uploads and their performance, the system identifies the day and hour that historically produce higher engagement rates for a given topic.

## Introduction

Upload timing plays a critical role in the visibility and engagement of online content. However, many creators rely on intuition or generalized advice when deciding when to publish their videos.

A data-driven approach can provide more reliable insights into when audiences are most active and responsive.

## Problem Statement

Content creators lack accessible tools that provide data-driven insights into optimal upload times. As a result, videos may be published at times when audience activity is low, reducing potential reach and engagement.

## Objective

To analyze YouTube video data and recommend optimal upload times by identifying patterns between upload timestamps and engagement performance.

## Methodology

### Data Collection

Video metadata is collected using the YouTube Data API v3. The system retrieves information such as:

* Video upload time
* View count
* Video title and metadata related to the searched topic

### Data Processing

Upload timestamps returned by the API are in Coordinated Universal Time (UTC).
These timestamps are converted to **Indian Standard Time (IST)** to better reflect the time patterns relevant to the intended audience region.

### Engagement Metric

Instead of using raw view counts alone, an engagement score is calculated:

```
engagement_score = views / days_since_upload
```

This metric approximates **view growth rate**, reducing the bias that occurs when older videos accumulate large view counts simply due to being online longer.

### Data Analysis

Using the **pandas** data analysis library, videos are grouped according to:

* Upload hour
* Upload day of the week

For each group, the **average engagement score** is calculated to determine which time slots historically produce stronger performance.

### Recommendation

The system identifies the upload hour and day with the **highest average engagement score** and recommends this time as the optimal upload window.

## Results

After analyzing the dataset, the system outputs a recommended upload strategy.
An example result may be:

Best Upload Hour: 16:00
Best Upload Day: Thursday

This suggests that videos uploaded around this time have historically achieved higher engagement rates relative to their age.

## Limitations

* The analysis is limited by the number of videos retrieved from the YouTube API.
* Subscriber counts and channel popularity are not normalized in the current model.
* Results depend on the videos returned by the YouTube search algorithm.

## Future Work

Future improvements may include:

* Incorporating machine learning models for predictive analysis
* Including additional engagement metrics such as likes and comments
* Normalizing engagement using channel subscriber counts
* Creating visual analytics dashboards

## Conclusion

This project demonstrates how publicly available platform data can be analyzed to generate actionable insights for content creators. By applying basic data analysis techniques to real-world video metadata, creators can make more informed decisions about when to publish their content for improved engagement.
