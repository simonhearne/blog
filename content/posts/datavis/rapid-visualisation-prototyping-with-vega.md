+++
date = "2018-11-06T19:27:27+00:00"
draft = true
layout = "post"
title = "Rapid visualisation prototyping with vega"

+++
## Introduction

My team has been using Vega for a few months now. It provides a declarative JSON syntax around D3.js to create data visualisations from declarations. We’ve just shipped the first production Vega charts to our web performance product, mPulse!

One of the cool things to come out of Google lately is the Chrome User Experience Report (CRUX). This huge dataset contains a wealth of data about performance distributions grouped by website (four million of them!), device type and connection type. This data is pretty huge, the latest monthly dataset on [BigQuery](https://bigquery.cloud.google.com/table/chrome-ux-report:all.201809?pli=1) is 356GB.

Sales folk at Akamai thought that this data could be a great way to show prospects and customers how their site performs, and how different the real performance might be from their internal measurements. More specifically, this data provides the first opportunity for a site owner to compare their real users’ performance against their competitors.

Akamai is full of clever folks to develop prototype products and pretty quickly we had an internal tool to generate these competitive score cards for sales calls. Generating distributions and rankings from a google sheet turned out to be time intensive, and started to cost real money. Our BigQuery costs increased ten-fold when Google changed the histogram storage logic from variable-width buckets to fixed-width.

So we were faced with increasing costs and increasing time requirements for a tool which was demonstrating value in sales engagements. Time to productise!

The CRUX competitor score card was a two-stage project:

1. A back-end to query CRUX _once_ per month and store the aggregated results
2. A front-end to present the results

I was asked to help design the visualization section for part 2. I decided to use Vega as a prototyping platform as we had just shipped Vega charts to production.

## Environment

An environment to prototype Vega charts can be as simple as a web browser.

## Process

### 1 Message

It’s tough to generate visualisations without data. 

### 2 Paper Prototyping

Whenever I have a visualisation project I have to start with pen and paper (or Apple Pencil and iPad!).

### 3 First Chart

#### 3a Data

Data is unsurprisingly important for data visualisations, but it may not help to get your data pipeline set up and data massaged into the perfect format while prototyping visualisations. Not least because data formats and sources often change multiple times between prototype and production.

Note that this section comes before Data - I think it’s important to focus on one thing at a time and worrying about data formats, cors nightmares and API keys distracts from chart design. In this case I asked for a data set which represented production data and I stored it as a public gist. Gists are great for mocking charts as the URL to load a raw response has all of the cors headers sorted for you, it’s versioned (although I can’t find a way to load the _latest_ raw version) and can be shared easily.

So with data available...

### 4 Data

### 5 Iterating

### 6 Productionising

If you’d like to get started querying CRUX data for yourself there is a [great tutorial by the Chrome Developer team](https://developers.google.com/web/tools/chrome-user-experience-report/getting-started).