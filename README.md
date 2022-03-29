# Trip-cost-calculator-API
Create a REST API using Node.js and Express.  This API will expose a set of GET and POST endpoints to allow getting data out, and sending data in.


Our task is to create a trip cost calculator app.

Imagine going on a trip, and you have your app (which can be a progressive web app, or a mobile app for example) where you add any expense you make. Gasoline, hotels, food, tickets and so on.

When the trip ends, you archive it and it becomes part of the history - which you can navigate and see how much you spent in the past trips.

We’re not going to create the frontend of the application here, just the API.

Let’s now dissect this into details, and translate it into a series of API endpoints.

An endpoint is a unique URL we will call to create an operation.

Like adding a new trip with its name.

At the beginning, there is no trip stored, and we need to add one. I imagine the app will ask the user for the name, and there will be a “Create trip” button. When clicked, the app will send the name to us, to the /trip endpoint with the POST HTTP method.

We have our first endpoint, which will accept a name property.

POST /trip { name }
Another endpoint will list the trips, and it’s

GET /trips
By default, it will return the trips ordered by creation date.

When the user wants to add a new expense, the app will invoke the /expense endpoint with the POST method, with some parameters that describe the expense

POST /expense { trip, date, amount, category, description }
trip is the ID of the currently selected trip.

category is the name of the category of the expense. We’ll provide a list of categories to choose from, which is static: travel, food, accomodation, fun.

When we want to retrieve a trip expenses, we call the /expenses endpoint with the GET method:

GET /expenses { trip }
passing the trip identifier.
