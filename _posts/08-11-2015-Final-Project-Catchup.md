---
layout: post
published: True
title: Final Project Catchup
---

WOW! I just realized I haven't written a blog post in a month. I've really just been
that busy. Honestly. It feels like in the past three weeks, the bottom fell out of
my learning experience at The Iron Yard and I went from doing 60-80 hour work weeks to 80-100 hour weeks easy. I literally have been doing nothing but sleep, eat and
code.

That being said, it's been pretty great! I'm busy, but I really love what I'm doing
and I could never have guessed that I'd enjoy anything so much. I love working with
code and figuring out problems and just _thinking_ about things.

So I should probably tell you about final projects. We are creating a personalized
road trip planner. This has involved a tremendous amount of work, as I mentioned, but
I'm lucky to be on a really great team that makes it possible. The app has an Angular front end and we are creating an API with road trip suggestions using the Django REST framework.

The app has involved a lot of data processing and a lot of API calls on our end. Jon (my backend partner) and I have worked together quite a bit, but overall it has broken down to me generating the suggested cities and suggested events and Jon is working more directly with the API endpoints and configuring that side of our backend. It's been great for me because I was really drawn to this idea because of all the data it requires, so to get to work with it directly is great.

I'll break down the basics of how the app is functioning currently. The user puts in a start and end location for their road trip, maybe Raleigh to Denver, and then puts in the dates that they want to spend on their road trip, so we can see what events they might be able to do.

From here we send a request to Google Maps Directions to get well, directions. The real reason for this though, is that at every turn, they also give us a latitude and longitude! With this we can run the Haversine formula against a database of preselected cities (really more like metropolitan areas) with their latitude and longitude and see if any of them are within a set radius of that turn/direction. If it is, we add it to the potential cities list.

An interesting problem I had to solve was what to do if the map distance between given directions was more than 100 miles or so, because I'm working off of those coordinates, that would mean large areas of the country where I wasn't checking for cities and could be missing potentials. [This webpage](http://www.movable-type.co.uk/scripts/latlong.html) came to the rescue. With some help from this page I was able to make a function to calculate probable coordinates for any number of points between two points, assuming a straight line. As most stretches of highway with no turns are going to be fairly straight, I figured this would provide a close enough approximation for our purposes. This all actually works really well! I'm able to crank up the radius I'm searching by if I want more results slightly off the path, and turn it down if I want a straighter shot.

Next we query Yelp's API for each of the possible cities with user generated interests in the food, activity, and hotels categories. We sort them by Yelp rating and give back the top 3 for each city to the user.

Finally, for events such as concerts and sporting events, we query SeatGeek's API for recommendations for events in possible cities that fit their dates and return those to the user.

Our user is then able to see all the relatively large cities along their route and is able to make informed decisions on where to stop, based on the kinds of things they're into! Pretty cool if I do say so myself.

I'm thrilled because we don't actually have demo day until November 20th, and most of our core functionality is actually done. We have the next week and a half or so to fix bugs, optimize our calculations and API calls, and generally making a better, smoother product.

If you're an employer in RDU and want to check out my project and others, come see us at [Demo Day](http://www.eventbrite.com/e/the-iron-yard-durham-cohort-5-demo-day-tickets-19208308568?aff=erelexporg).
