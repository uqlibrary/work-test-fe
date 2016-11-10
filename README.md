# UQLibrary Work Test - Front end

These simple tasks should demonstrate your basic understanding and skills in PHP and javascript.

- read all instructions first
- implement each test in its own repo on github
- send us links to your repo when you're done

## Frontend test: Javascript app

UQ Library provides an open API allowing users to get library data (eg library opening hours, computer availability, etc) for example:
 - http://app.library.uq.edu.au/api/v2/library_hours - [api doc](https://)
 - http://app.library.uq.edu.au/api/computer_availability - [api doc](https://)
 
Construct a javascript application (using AngularJS/ES6) allowing users to explore these objects:
- user should be able to view a list of libraries 
- user should be able to filter libraries by name
- user should be able to view opening hours for the selected library
- user should be able to view available computers in the selected library
- library details should be accessible by route /#/{library id}
- create a new library form with dynamic validation which has following fields:
  - library id - numbers only
  - library short name - strictly 5 characters 
  - library name - up to 50 characters
  - campus - a selection from St Lucia, Herston, Bundaberg, PACE, Mater 
- new library form should have a save button (which triggers validation or is disabled if validation is failing)
- new library form should display cancel button which takes user back to the list of libraries
- new library form should be accessible by a route #/new
  
- any other creative use of data!

### Technical requirements

- application must respond to mobile
- use a CSS framework for styling - preferred [Angular Material] (https://material.angularjs.org/latest/)
- should work in evergreen browsers (don't worry about old versions of IE)
- use any build tools you feel are necessary but all source code must be provided in a readable format
- an http server may be used if required
- add unit/e2e testing

## Criteria

- code quality
- documentation
- testing

## Extra credit

- provide estimation of how long would it take you to implement each mini-app, comment on how long it took you to implement it
- application deployment (provide URL to your deployed application, eg heroku, github io, or provide steps how to run it locally)
- comment on how you'd optimise your applications on server
- comment how you'd scale your applications
- comment on any issues you have come across
- which AWS services would you use for deployment of your application or how would you deploy this application on premise 
 


