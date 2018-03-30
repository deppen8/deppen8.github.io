---
title: "LEIA Project Metadata"
excerpt: "Using metadata to understand better understand survey data and methods<br/><img src='/images/survey_time.png'>"
collection: portfolio
---

As part of the [Landscape, Encounters, and Identity Archaeology (LEIA) Project](https://leiap.weebly.com), we have been collecting data that will help us evaluate the efficacy of our survey. In the field, each surveyor is equipped with a handheld GPS. Roughly every ten meters, surveyors stop, record their location with the GPS, and scan the ground for artifacts, collecting anything they find. As a result, all locations searched (with or without artifacts) can be located in space. Beyond this simple spatial information, the data from the handheld GPS can be combined and leveraged in other ways to better understand the survey itself.

## Time
One way we have made use of the GPS data is with respect to time. When recording a location, the handheld GPS device also records the time and date. Using some simple Python routines, we can calculate the time spent at any survey collection point. This data can then be combined, sliced, and diced in various ways. Just a few of the dimensions we can study are: 
* the collection times for different surveyors.
* changes in collection times for a surveyor over the course of the field season.
* the relationship between collection time and variables like the amount of material found, visibility, or even the day of the week or the weather.

![surveyor times](/images/surveyor_learning.png)

## Visibility
Other metadata we are collecting relates to surface visibility. In each field surveyed, one or two members of the survey team are assigned to take photos of the ground surface at every tenth collection point. In the lab, these photos can be given a visibility score which is then tied to the location of the photo. In this way, we can capture some of the variation in visibility across a field rather than assigning one value to the entire field.

![mapping time](/images/survey_time_map.png)