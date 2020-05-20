## Introduction

<b>TL;DR; Going to find out what restaurant to open that best serves police stations, and which station(s) will benefit the most.</b>

A description of the problem and a discussion of the background. (15 marks)
A description of the data and how it will be used to solve the problem. (15 marks)

### Problem Description

The purpose of this project is to find the best place for an associated business. For example, around a hospital you will most likely find pharmacies, or a Pawn shop and a Casino. Now we may think that police officers love donuts, so donut shops may be clustered around police stations. Is this true or just a stereotype? This project we will identify the most common restaurants around police stations in a particular city, then we will determine which type of restaurant around a particular police station that someone should open.

#### Why do I want to do this?

Intellectual curiosity on my part, but it does have some important impacts for others. First, it gives someone an opportunity to choose the best business to support an organization that they love. For me that would be to support local law enforcement. 

#### Why is this important, and who would be interested?

Someone who wants to support an organization, but still open a successful business would be interested in the results of this project. For example, you might be a retired police officer in a new city. You may have your own opinions on what is best, but this city is different. The data provided by this project would give you a greater chance of success while still supporting the law enforcement community that you love. 

As a side benefit of interest to anyone, this can support or discredit stereotypes. 



## Data

<b>TL;DR; Get locations of police stations, Find closest businesses, cluster, find most common, apply suggestion to least common. </b>

I am anticipating that most if not all data will be coming from Foursquare. This section is broken down into two parts, Gathering Data, Working with Data.


### Gathering Data

We need to start somewhere, so seeing that our target audience is someone retiring from the industry, and Florida is a great place to retire, we will be using Orlando, Florida as our test market. However, we can use the data from any city and apply the same analysis. If this was a web-based tool, we would let the user select the location, and category that they would like to support, however this is a class assignment so I am choosing Police and Orlando Florida.

#### Get the locations of Police Stations and Filter as needed

Lucky for us, Foursquare has categorized venues, and Police Stations is one of the categories! (https://developer.foursquare.com/docs/build-with-foursquare/categories/) 
<b><br>Police Station</b><br>
<b>4bf58dd8d48988d12e941735</b>

To get the police stations in Orlando Florida, we will use the venue search API call with the appropriate category ID (https://developer.foursquare.com/docs/api-reference/venues/search/)

The call is a nested structure and we do not know if they want a category or end node, therefore we will have to flatten the table.


#### Get nearby Venue Data

<code> https://api.foursquare.com/v2/venues/explore?&client_id={}&client_secret={}&v={}&ll={},{}&radius={}&limit={} </code>

We will then gather and filter nearby venues. This includes location data so we will be using folium to map the data.


#### Analyze the areas surrounding the user defined category

Get the most common businesses for each area surrounding the user defined category, in our case police stations.

#### Cluster the data

use k-means to cluster by popularity. This lets us know what the categories are for popularity. 

### Find the most underserved area to recommend to our end user

Which police station ranks last? that is most likely the best location for opening up the top item(s) from the ranking.

We can also answer the stereotype problem. Let us see if donut shops rank #1.
