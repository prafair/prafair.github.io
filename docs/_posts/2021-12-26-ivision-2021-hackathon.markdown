---
layout: post
title:  Once I participated in a CV 👁‍🗨 hackathon
date:   2021-12-26 17:37:29 +0300
categories: ivision hackathon opencv imageai digital_ocean python
---
In the spring, my colleague and I (by the way, he is also not a developer) decided to participate in the iVision 2021 computer vision [hackathon](https://ivision.citylink.pro/). I had no experience in this area, so I was preparing to learn something new at the upcoming event 💫

In our category, a task was given to recognize free parking spaces 🚗 The organizers gave video streams from several cameras and it was necessary to show free spaces in live mode 🖥
At the second stage, which we passed and it was already an achievement, we were finalizing the previously created something 😂 Now we had to become a front-end developer and create a web application in the form of a map 🗺, where you can clearly see the free places, as well as a bot 🤖 for Telegram, notifying about the availability of free space in a particular parking lot.

We began to think and look for at least some clues on what to do and how. There was something, but it wasn’t quite right and didn’t work in our case 👀 We looked at how the Habr [example](https://habr.com/ru/post/451164/) works - it worked frankly crookedly and for a long time.
Then we tried the [ImageAI](https://github.com/OlafenwaMoses/ImageAI) library, which already gave at least some results on car recognition, but even with some big error, it could barely distinguish the car 🚗 on some cameras due to the angle of inclination. It was difficult even to count the number of cars with our eyes, especially in the distance.
Based on this, it was decided to train the model under our conditions 🚴‍♂️

The next stage of sampling and data labeling took from 6 to 12 hours and was done twice due to the size of the images that affect the processing speed.
We got a working model for a while with plus or minus a good result 🎯
And this thing also had to be deployed somewhere, then I had to become a devops 🧙‍♂️

I tried 3 deployment services: Heroku, Google App Engine and DigitalOcean.
Heroku was difficult to get to grips with because of the internal engine and obscure bugs, although there is a separate plan for AI / ML applications, but it is paid of course.
Google App Engine refused to process long requests, which, alas, [it](https://cloud.google.com/appengine/docs/standard/java11/how-requests-are-handled#streaming_responses) does not support 🤷‍♂️
Thanks to DigitalOcean for not being stupid and getting everything right the first time 👌 But it ate a lot of resources.

But soon the main catch was waiting for us 🗿

At the final stage, our model swam 🚣‍♀️, because the March snow melted, and it was already in April.
In fact, the goal of the task remained the same, it was just necessary to arrange everything beautifully in the form of a web page with a map, on which parking lots and free spaces are visible. And with the help of a telegram bot, notify 📣 about the availability of free space in a certain parking lot.
It was necessary to create something quickly, so everything was written in an HTML file using jQuery, and I’m not even a bit ashamed, but something worked and I managed to figure it out with Google Maps 📈
The Telegram bot in Python performed its functions perfectly: subscribed to the parking lot, received a notification, ran to park the car 👍
Only there was a problem with accuracy, the model failed 🤔

But despite the difficulties, it was an interesting challenge 🙌 I liked trying different solutions with their pros and cons, testing the service and getting a visual result. Break tasks into subtasks 🧩 Demonstrate the solution in Jupyter Notebook 📝 Remember Python and JavaScript 😊

I learned some lessons for myself for the future, that it is necessary to study and understand the work of algorithms more, in which cases it is better to apply. And improve work with front-end frameworks 📚

_________________
Original post in Telegram - <https://t.me/qa_relia/44>
