# food-festival

## Introduction
This project is an attempt to create a Progressive Web Application. The Front and Back end of the project was cloned from the [this repo](https://github.com/coding-boot-camp/symmetrical-bassoon). This project adds three main component for transforming the cloned repo into a progressive web app. It adds offline data persistance, cacheing files, and finally making the app installable in user's device.

## Table of Content
**[Introduction](#introduction)**

**[Tools](#tools)**

## Tools
The main three web technologies used are `IndexedDB`, `Servie Worker`, and `Manifest`.
* `IndexedDB` saves data from users POST request in the browser. The browser then displays that data using front end Javascript.  
* `Service Worker` cache the necessary static files in the browser. Those static files are then served from the service worker.  
* `Manifest` installs the app in the users device.

## Funtionality

### Offline Data Persistance.
When the user makes a POST or PUT request, an internet connection is needed to communicate the user action with the server. If that connection is interrupted, the user experience can take a huge dip. In such a situation, `indexedDB` can be used to save the data in the browser first (since no server database is available). Then, once the connection is established, that data can be transferred to the database. This application accomplishes this through the `idb.js` file logic.

### Offline Static File Serveing.
With connection to the internet, the users will not be able to load the static HTML files. Therefore, this application uses `service worker` in the `service-worker.js` logic file. The necessary files are cached, which are then displayed to the user once the applcation loads.

### Installing the app.
For easier access to the app, and also for competing with native app, this application provides a `manifest.json` file. Which allows the user to save a shortcut for the web application in ther device. That application can then take advantage of `indexedDB` and `service worke` and provides offline functionlaity. Finally, if internet connection is detected, the app transfars all the POST data to the database. 
