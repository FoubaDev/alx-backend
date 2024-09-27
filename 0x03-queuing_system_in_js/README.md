# 0x03. Queuing System in JS
__Back-end ,JavaScript ,ES6 ,Redis ,NodeJS ,ExpressJS, Kue__


# Resources
__Read or watch:__

* Redis quick start
* Redis client interface
* Redis client for Node JS
* Kue deprecated but still use in the industry

# Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

* How to run a Redis server on your machine
* How to run simple operations with the Redis client
* How to use a Redis client with Node JS for basic operations
* How to store hash values in Redis
* How to deal with async operations with Redis
* How to use Kue as a queue system
* How to build a basic Express app interacting with a Redis server
* How to the build a basic Express app interacting with a Redis server and queue
# Requirements
* All of your code will be compiled/interpreted on Ubuntu 18.04, Node 12.x, and Redis 5.0.7
* All of your files should end with a new line
* A README.md file, at the root of the folder of the project, is mandatory
* Your code should use the js extension

# Required Files for the Project
__package.json__

{
    "name": "queuing_system_in_js",
    "version": "1.0.0",
    "description": "",
    "main": "index.js",
    "scripts": {
      "lint": "./node_modules/.bin/eslint",
      "check-lint": "lint [0-9]*.js",
      "test": "./node_modules/.bin/mocha --require @babel/register --exit",
      "dev": "nodemon --exec babel-node --presets @babel/preset-env"
    },
    "author": "",
    "license": "ISC",
    "dependencies": {
      "chai-http": "^4.3.0",
      "express": "^4.17.1",
      "kue": "^0.11.6",
      "redis": "^2.8.0"
    },
    "devDependencies": {
      "@babel/cli": "^7.8.0",
      "@babel/core": "^7.8.0",
      "@babel/node": "^7.8.0",
      "@babel/preset-env": "^7.8.2",
      "@babel/register": "^7.8.0",
      "eslint": "^6.4.0",
      "eslint-config-airbnb-base": "^14.0.0",
      "eslint-plugin-import": "^2.18.2",
      "eslint-plugin-jest": "^22.17.0",
      "nodemon": "^2.0.2",
      "chai": "^4.2.0",
      "mocha": "^6.2.2",
      "request": "^2.88.0",
      "sinon": "^7.5.0"
    }
  }

__.babelrc__

Don’t forget to run $ npm install when you have the package.json

# Tasks
#### 0. Install a redis instance

* Download, extract, and compile the latest stable Redis version (higher than 5.0.7 - https://redis.io/downloads/):

#### 1. Node Redis Client
* Install node_redis using npm

Using Babel and ES6, write a script named 0-redis_client.js. It should connect to the Redis server running on your machine:

#### 2. Node Redis client and basic operations
* In a file 1-redis_op.js, copy the code you previously wrote (0-redis_client.js).

#### 3. Node Redis client and async operations
* In a file 2-redis_op_async.js, let’s copy the code from the previous exercise (1-redis_op.js)

Using promisify, modify the function displaySchoolValue to use ES6 async / await

#### 4. Node Redis client and advanced operations
* In a file named 4-redis_advanced_op.js, let’s use the client to store a hash value

#### 5. Node Redis client publisher and subscriber
* In a file named 5-subscriber.js, create a redis client:

#### 6. Create the Job creator
* In a file named 6-job_creator.js:

#### 7. Create the Job processor
* In a file named 6-job_processor.js:

#### 8. Track progress and errors with Kue: Create the Job creator
* In a file named 7-job_creator.js:
 
#### 9. Track progress and errors with Kue: Create the Job processor
* In a file named 7-job_processor.js:

Create an array that will contain the blacklisted phone numbers. Add in it 4153518780 and 4153518781 - these 2 numbers will be blacklisted by our jobs processor.

Create a function sendNotification that takes 4 arguments: phoneNumber, message, job, and done:
 
#### 10. Writing the job creation function
* In a file named 8-job.js, create a function named createPushNotificationsJobs:

It takes into argument jobs (array of objects), and queue (Kue queue)
If jobs is not an array, it should throw an Error with message: Jobs is not an array
For each job in jobs, create a job in the queue push_notification_code_3
When a job is created, it should log to the console Notification job created: JOB_ID
When a job is complete, it should log to the console Notification job JOB_ID completed
When a job is failed, it should log to the console Notification job JOB_ID failed: ERROR
When a job is making progress, it should log to the console Notification job JOB_ID PERCENT% complete
 
#### 11. Writing the test for job creation
* Now that you created a job creator, let’s add tests:

Import the function createPushNotificationsJobs
Create a queue with Kue
Write a test suite for the createPushNotificationsJobs function:
Use queue.testMode to validate which jobs are inside the queue
etc.
#### 12. In stock?
* Create an array listProducts containing the list of the following products:

Id: 1, name: Suitcase 250, price: 50, stock: 4
Id: 2, name: Suitcase 450, price: 100, stock: 10
Id: 3, name: Suitcase 650, price: 350, stock: 2
Id: 4, name: Suitcase 1050, price: 550, stock: 5
Data access
Create a function named getItemById:

It will take id as argument
It will return the item from listProducts with the same id
Server
Create an express server listening on the port 1245. (You will start it via: npm run dev 9-stock.js)