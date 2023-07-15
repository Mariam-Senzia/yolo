# Requirements
Make sure that you have the following installed:
- [node](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-18-04) 
- npm 
- [MongoDB](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/) and start the mongodb service with `sudo service mongod start`

## Navigate to the Client Folder 
 `cd client`

## Run the folllowing command to install the dependencies 
 `npm install`

## Run the folllowing to start the app
 `npm start`

## Open a new terminal and run the same commands in the backend folder
 `cd ../backend`

 `npm install`

 `npm start`

 ### Go ahead a nd add a product (note that the price field only takes a numeric input)


YOLOMY MERN STACK APPLICATION

This is a MERN stack application based on Mongo DB,Express,React and Nodejs.The application is an e-commerce website that doubles-up as a dashboard where you can load retail products on to the site.The client is built with React while the backend is built with Express and Node.js.Database connection in the backend is handled by Mongo DB.

##Installation
To get the app up and running,I created dockerfiles on the backend and client.

I then created a docker compose to containerize and connect the backend and client.

##Usage
Ensure you have mongoDB and node installed.

Fork and clone the repository.

Run docker compose up to start the application.

To view client application,type:localhost:3000.

To stop the application,run  Docker compose down.

##Test

Test out the functionality by adding a product through the provided form to test out "Add product" functionality.