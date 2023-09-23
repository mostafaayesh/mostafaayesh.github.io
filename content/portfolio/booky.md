---
title: "Booky"
summary: A Cross-Platform mobile app (iOS & Android) that allows the user to search for books by using a picture of the book cover.
date: 2018-09-15T11:30:03+00:00
# weight: 1
# aliases: ["/first"]
tags: ["Flutter", "Dart", "Mobile", "iOS", "Android"]
# author: " "
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
# description: "Desc Text."
canonicalURL: "https://mostafaayesh.com/to/page"
disableHLJS: true # to disable highlightjs
disableShare: true
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: false
ShowBreadCrumbs: false
ShowPostNavLinks: false
ShowWordCount: false
ShowRssButtonInSectionTermList: false
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---

A cross-platform mobile app (Android & iOS) that enables the user to find books online by taking a photo of the physical book cover. It was developed as a submission for **DeltaHacks III** hackathon. The app's source code is available on [Github](https://github.com/mostafaayesh/booky_search).  

## Design

### Flutter
Flutter was chosen because it provides cross-platform functionality on both Android & iOS with a single code base.

### Google Cloud Services
The app utilizes Google cloud services to generate the search results. The picture taken by the user is processed through Google Cloud Vision API and the result is then passed to Google Books API to get the details about the book including the Book name, author name, description and a link to get more details or purchase the book from Google books.

## Demo
The demo video is uploaded to [Google Drive](https://drive.google.com/file/d/1qSIVf_EzpNv6lCsBAJFSkiFgfXPa0Plb/preview)
