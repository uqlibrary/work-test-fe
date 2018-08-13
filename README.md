# UQLibrary Work Test - Front end

These simple tasks should demonstrate your basic understanding and skills in PHP and javascript.

- read all instructions first
- send us links to your repo when you're done

## Frontend test: Javascript app

UQ Library provides an open API allowing users to get library data (eg library opening hours, computer availability, etc) for example:
 - https://api.library.uq.edu.au/v1/library_hours - [api doc](https://github.com/uqlibrary/work-test-fe/blob/master/api/library_hours.md)
 - https://api.library.uq.edu.au/v1/computer_availability - [api doc](https://github.com/uqlibrary/work-test-fe/blob/master/api/computers_availability.md)
 
Construct a javascript application (using ReactJS/ES6) allowing users to explore these objects:

- as a user I should be able to view a list of libraries 
- as a user I should be able to filter libraries by name
- as a user I should be able to view opening hours for a selected library
- as a user I should be able to view available computers in the selected library

- library details should be accessible by route /#/{library id}
- as a user I should be able to create a new library by clicking on a 'New library' button
  New library form should be accessible by a route /#/new
  New library form should contain the following fields with dynamic validation:
  - library id - numbers only
  - library short name - strictly 5 characters 
  - library name - up to 50 characters
  - campus - a selection from St Lucia, Herston, Bundaberg, PACE, Mater 
  
  New library form should contain the following:
  - a save button, which:
    - triggers validation or is disabled if validation is failing
    -  mocks form submission and displays success message
  - a cancel button which takes user back to the list of libraries

- any other creative use of data!

### Technical requirements

- use ReactJs and Redux
- use a CSS framework for styling - preferred [Material UI] (http://www.material-ui.com/#/)
- add unit/e2e testing (100% coverage is not required)
- application must respond to mobile
- should work in evergreen browsers (don't worry about old versions of IE)
- use any build tools you feel are necessary but all source code must be provided in a readable format
- an http server may be used if required

## Criteria

- code quality
- design, layout and usability
- documentation 
- testing

## Provide comments 

- on WCAG 2.0 AA compliance considerations
- on SEO considerations
- on estimation of how long would it take you to implement each mini-app, comment on how long it took you to implement it
- application deployment (provide URL to your deployed application, eg heroku, github io, or provide steps how to run it locally)
- on how you'd optimise your applications on server
- on how you'd scale your applications
- on any issues you have come across
- on which AWS services would you use for deployment of your application or how would you deploy this application on premise 
- if you have AngularJS experience, in your opinion what's the difference between AngularJS and ReactJS, which one do you prefer? 
 


