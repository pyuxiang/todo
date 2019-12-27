# CVWO 2020 Assignment

## Learning outcomes

### Concepts
    - Model-View-Controller framework
    - Relational databases
    - Asynchronous programming
    - UI data management
    - Application state management
    - Web deployment
    - Cross-platform/browser compatibility

### Technologies
    - Ruby on Rails
    - SQLite
    - Javascript (or TypeScript)
    - ReactJS
    - Redux
    - Heroku
    - Docker

## Requirements

0. Install required software and document installation procedure
1. Create todo manager, must support CRUD.
    - Backend must be written using Rails, no gem restrictions, maintain default file structure
    - Frontend must be written in React, using React UIs or CSS for styling
    - Git must be used for versioning
2. Implement tagging system
3. Implement specified optional features
    - Setup Cron (UNIX) jobs for automation, e.g. backup, updates
    - Use statically typed TypeScript over JavaScript
    - Host application on Heroku
    - Use Redux for managing application state in React
    - Use Docker to containerize software within UNIX environment

For the mid-term submission, a short writeup of basic use case and execution plan,
as well as suggestions and problems faced should be submitted, in pdf format.
No longer than 3 A4 sides with 12pt Georgia-equivalent font face.

For the final submission, a short writeup of accomplishments with user manual,
same submission format. Proof of working application must be available.

For forum with other CVWO applicants, search [here](https://github.com/tiuweehan/CVWO-2020/issues). Follow the [CVWO guide](https://github.com/tiuweehan/CVWO-2020/) once Rails is setup.

### Web server: `Ruby on Rails`

Use of auxiliary libraries to speed up development process. Relatively easy to deploy since supported by many hosting service providers. Rails ship with a default web server and database adapter, Puma and SQLite.

Recommended reading from Chapter 1 to 11 for [Ruby on Rails guide](https://guides.rubyonrails.org/), up to Routing.

### Database: `SQLite`

Resources to read:
- [NTU course](https://www.ntu.edu.sg/home/ehchua/programming/sql/Relational_Database_Design.html)
- [Medium article](https://medium.com/@kimtnguyen/relational-database-schema-design-overview-70e447ff66f9)
- [Wikiversity detailed](https://en.wikiversity.org/wiki/Relational_Databases/Design)

Need to be able to draw out the application schema. What is an entity-relationship diagram?
How efficient is the schema (number of queries and tables per single user query)?

### Application: `Ruby / Javascript`

HTML is okay, but consider brushing up on Javascript and CSS. Read up on asynchronous Javascript with [Eloquent Javascript](https://eloquentjavascript.net/11_async.html).
Make sure that testing is performed for different types of web browsers, i.e. Firefox and Chrome, and the occasional Internet Explorer.

Be familiar with [ReactJS](https://reactjs.org/), which provides the view layer for web applications. React components (which renders output) are written to correspond to different interface elements, and these components are composed to create structure. The [ReactJS tutorial](https://reactjs.org/tutorial/tutorial.html) explains how React manages data in complex UIs.

Guide to introducing TypeScript into project can be found [here](https://create-react-app.dev/docs/adding-typescript/).
Guide to Redux for application state management can be found [here](https://redux.js.org/introduction/getting-started/).

### Deployment: `Heroku`

Web deployment using Heroku guide found [here](https://devcenter.heroku.com/articles/getting-started-with-rails5). Alternative services include DigitalOcean and AWS Elastic Beanstalk.

### Version control: `Git`

Pretty familiar with the basics of it. Use Github's commit viewer for now.
