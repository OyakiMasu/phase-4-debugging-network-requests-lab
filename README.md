# Putting it All Together: Client-Server Communication

## Learning Goals

- Understand how to communicate between client and server using fetch, and how
  the server will process the request based on the URL, HTTP verb, and request
  body
- Debug common problems that occur as part of the request-response cycle

## Introduction

Just like the last lesson, we've got code for a React frontend and Rails API
backend set up. This time though, it's up to you to use your debugging skills to
find and fix the errors!

To get the backend set up, run:

```console
$ bundle install
$ rails db:migrate db:seed
$ rails s
```

Then, in a new terminal, run the frontend:

```console
$ npm install --prefix client
$ npm start --prefix client
```

Confirm both applications are up and running by visiting
[`localhost:4000`](http://localhost:4000) and viewing the list of toys in your
React application.

## Deliverables

In this application, we have the following features:

- Display a list of all the toys
- Add a new toy when the toy form is submitted
- Update the number of likes for a toy
- Donate a toy to Goodwill (and delete it from our database)

The code is in place for all these features on our frontend, but there are some
problems with our API! We're able to display all the toys, but the other three
features are broken.

Use your debugging tools to find and fix these issues.

There are no tests for this lesson, so you'll need to do your debugging in the
browser and using the Rails server logs and `byebug`.

**Note**: You shouldn't need to modify any of the React code to get the
application working. You should only need to change the code for the Rails API.

As you work on debugging these issues, use the space in this README file to take
notes about your debugging process. Being a strong debugger is all about
developing a process, and it's helpful to document your steps as part of
developing your own process.

## Your Notes Here

- Add a new toy when the toy form is submitted

  - How I debugged: 

      *For the create it gave me this message POST http://localhost:4000/toys 500 (Internal Server Error) and in the terminal where I was running the server it was written NameError (uninitialized constant ToysController::Toys): hence I knew it was a Syntax error in naming the Toy class instead of Toy it was Toys hence I fixed that and I was able to post an empty toy. I didn't do error message handling hence that was possible. 

- Update the number of likes for a toy

  - How I debugged: 

      *For the update it gave me this message Uncaught (in promise) SyntaxError: Unexpected end of JSON input hence I went to check the controller action and made sure to render json and after doing that I was able to update the likes of the toys

- Donate a toy to Goodwill (and delete it from our database)

  - How I debugged:

      *For the delete(donate) it gave me this message of DELETE http://localhost:4000/toys/3 404 (Not Found) hence I went to check in the resources to check if the destroy was stated and it wasn't hence it was looking for something that was not there. Fixed that and was able to donate the toys .



### Summary 

  - For the errors I started with fixing the delete(Donate), update(No of likes) and create . Although it was backwards I finished what I had to do
