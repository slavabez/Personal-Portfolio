# Personal-Portfolio

Personal Portfolio for Slava Bezgachev

## Content

- [About me](#about-me)
- [Skills and Technologies](#skills-and-technologies)
- [Case Studies](#case-studies)
  - [Full-stack Node and reactJS application](#node-and-express-api-for-konfetka-with-reactjs-front-end)

## About me

My name is Slava Bezgachev and I am a full stack web developer with 3+ years of commercial experience. Lately I've been focusing on mastering Javascript with ReactJS on the front-end with NodeJS on the back-end.

## Skills and technologies

- **Javascript.**
  I've been using Javascript both in the browser and with Node for many years. Not without it's quirks, it's my favourite language for a lot of things. The technologies I've used.
  - **ES6 and ES7.**
    The latest and greatest of Javascript
  - **ReactJS.**
    React is my go-to framework for almost any front-end site because of how fast it is.
  - **NodeJS.**
    I use Node, usually with Express because it works well with the web due to it's event-driven architecture.
  - **Various libraries and frameworks.**
    Over the years I've used a plethora of NPM libraries and frameworks, for such purposes as security, monitoring, maintenance or styling.
- **Other programming languages.**
Over the years I've used a lot of programming languages, some for a long time and others for a little while. I've used **PHP** and **.NET** commercially, as well as **Java, C++ and Go** in my own time on personal projects.
- **Databases.**
I've used both SQL databases, including MySQL and MSSQL, as well as MongoDB, a no-SQL database.
- **Redis.**
  Redis is a great and simple in-memory data storage. I typically put it between the Node server and the database, like MongoDB, to serve as a caching layer

## Case Studies

- [Node and Express API for Konfetka](#node-and-express-api-for-konfetka)

### Node and Express API for Konfetka with ReactJS front-end

[Link to the repository](https://github.com/skazka-kz/konfetka)

The Konfetka site is a simple website with information about store locations and products offered in Konfetka, a small chain of confectionery shops in Kokshetau, Kazakhstan.

This case study will cover the project, which is still ongoing, including the approach taken, the structure of the project, how it's tested and how it's deployed.

#### Back-end structure (NodeJS with Express)

* Project directory united with the front-end for simpler deployment and packaging
* Express server with the following add-ons and middleware:
    * PassportJS for local authentication using MongoDB, hashing and salting with "bcrypt"
    * Mongoose
    * Helmet for basic express security
    * Winston for smarter and more flexible async logging
    * Multer for file upload
    * Custom caching middleware with the help of Redis. Achieved by hooking up to Mongoose and [overriding the query prototype function](https://github.com/skazka-kz/konfetka/blob/master/server/services/redisCache.js)

#### Front-end structure (ReactJS)

* The project is an ejected Create-React-App. Ejected because I wanted to test both the React side and the Node side wit ha single test suite using Jest.
* Styled Components. Amazing helper library for easier, separated and independent styles
* Bespoke CSS using Flexbox
* Separated admin section, only loaded if needed to make the JS bundle significantly smaller as the admin section has a lot of code
* react-easy-state for managing the application state in the Admin section. Subject to change for Redux or Redux observables. The non-admin section only uses react component-level state
