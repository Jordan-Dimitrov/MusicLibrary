# Music Library

## Overview

**Music Library** is a (**SPA**) front-end app for **managing** music albums. The **application** allows **visitors** to **browse** through the **albums catalog**. **Users** can **register** with an **email** and **password** which allows them to **create** their **own album card**. **Album authors** can also **edit** or **delete** their own **publications** at any time.

<kbd>![Music Library](https://github.com/Jordan-Dimitrov/MusicLibrary/blob/main/images/landing.png)</kbd>

The **SPA "Music Library** is an app for creating **catalog of albums**.
 - Technologies: Javascript, HTML, CSS, Node.js, Express.js, Mocha, Chai

## Pages and permissions

### All users

- Home ```/home```
- Dashboard ```/dashbaord```
- Details ```/details/:id```
- Login ```/login```
- Register ```/register```

### Authenticated users

  - Dashboard ```/dashboard```
  - Add album (Singer/Band + Album + Image Url + Release date + Label + Sales): ```/create```
  - Album Details: ```/details/:id```
  - Edit Album (only if user is owner): (Singer/Band + Album + Image URL + Release date + Label + Sales): ```/edit/:id```
  - Delete Album (only if user is owner): ```/delete/:id```

### How to start the application?
 - First you must install **all dependencies** included in the **package.json** file by typing ```npm install``` in a **terminal**. Then you must **serve** the app by typing ```ng serve``` in a terminal. After that Music Library could be accessed on http://localhost:3000 URL.

### Executing the tests
Before running the test suite, make sure a **web server** is operational, and the **application** can be found at the **root** of its **network address**. To **start** the included **dev-server**, open a **terminal** in the folder containing **package.json** and execute: ```npm run start```

This is a one-time operation unless you **terminate** the **server** at any point. It can be **restarted** with the same command as above. To **execute** the tests, open a new terminal (do not close the terminal, running the web server instance) in the folder containing **package.json** and execute: ```npm run test```

**Test results** will be displayed in the **terminal**, along with detailed information about encountered problems. You can perform this operation as many times as it is necessary by re-running the above command.

## Music Library RESTful API
When the app is started locally, RESTful API documentation is available on: http://localhost:3000/api-docs

 - ```GET /data/albums?sortBy=_createdOn%20desc``` - list all albums
 - ```GET /data/albums/:id``` - returns an album by given id
 - ```POST /data/albums``` - create a new album (post a JSON object in the request body, e.g. ```{ "singer": "Taylor Swift", album": "Midnights", imageUrl": "https://upload.wikimedia.org/wikipedia/en/9/9f/Midnights_-_Taylor_Swift.png", "release": "October 21, 2022", "label": "Republic", "sales": "1.58 million copies" })```
 - ```PUT /data/albums/:id``` - edit album by id (send a JSON object in the request body, holding all fields, e.g. ```{ "singer": "Taylor Swift", album": "Midnights", imageUrl":
"https://upload.wikimedia.org/wikipedia/en/9/9f/Midnights_-_Taylor_Swift.png", "release":
"October 21, 2022", "label": "Republic", "sales": "1.58 million copies" }) ```
 - ```DELETE /data/albums/:id``` - delete album by **id**
 - ```POST /users/login``` - logs in an existing user (send a JSON object in the request body, holding all fields, e.g. ```{"username": "username", "password": "pass123"})```
 - ```POST /users/register``` - registers a new user (send a JSON object in the request body, holding all
fields, e.g. ```{"email": "user@example.com", "password": "pass123"} )```
 - ```GET /users/logout``` - logs out and existing user
 - ```POST /data/likes``` - add a like into album. The service expects a body with the following shape: ```{albumId}```
 - ```GET /data/likes?where=album Id%3D%22{**albumId**}``` - get total likes count for an album
 - ```GET /data/likes?where=albumId%3D%22{**albumId**}%22%20and%20_ownerId%3d%22{**userId**}%22&count``` - get the number
of the likes for an album for specific user. {albumld} is the id of the desired album and {userld} is the id of the **currently logged-in user**.
