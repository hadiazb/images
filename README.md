# Documentation

## Content

- Description
- Tecnologies
- NPM Packages
- Database
- API
- Tools

## Description

This documentation describes step by step the implementation of the Backend of an application that works as an electronic commerce,
Here you can find information about the technologies used, application architecture, tools, data bases and other accessories
that allows you to master the reverse side of the application.

## Tecnologies

According to the specifications given by the customer business model, the team of developers has implemented the following
technological stack to carry out the present project.

- Node.js : It is a programming language that can operate from different places in the same web application, since it is based on
  Javascript, although with Node its usefulness will be established from the server side.

- Express : It is a Node framework and that allows to streamline different tasks that would otherwise cost more time with Node, such as
  server construction and the employability of some middlewares that are already defined in this framework.

- MySQL : It is the most famous non-relational database engine on the planet, the developer team has used it because
  because the business logic for an ecommerce requires multiple connections and above all because this engine is optimized
  for transactions and other operations that make the app's functionalities easier in the future.

- React: It is a tool that allows you to develop components on the frontend side of the app, its speed is one of its characteristics,
  since not reloading the page in each request will reduce the execution time of different tasks.

## NPM Packages

### Backend

Next, the NPM packages used on the Backend side will be listed.

- **dateformat**: It allows to facilitate the use of date and time formats on the back side.
- **dotenv**: It allows the use of environment variables in our app.
- **express**: It's a Node framework that decreases our code.
- **mysql**: It allows the connection of our app with a local or remote mysql database.

- **eslint-config-prettier**: It allows configuring the styles in which the code will be written, both in development and in production.
- **eslint-plugin-prettier**:
- **husky**: Commits confirmation.
- **lint-staged**:
- **nodemon**: Lets hear each of the changes that are made in the application permanently.
- **prettier**: Code writing styles.
- **swagger-ui-express**:

### Frontend

- **package one**:

## Database

### Tables

In our app you can find 20 tables to contain the data flow, some are related to one or more tables. Below you will find the description of each one.

- **users**: This table is related to the personal data of the user who uses the app.
- **orders**:
  Contains fields that are related to user order information
- **services**:
  This table is related to the additional services that e-commerce has.
- **countries**: Data about the country customer.
- **cities**: Data about the city customer.
- **states**: Data about the state customer.
- **method_payment**: This table is about method payment.
- **reservations**: Details about reservation.
- **service_schedule**:
- **order_details**: Contains the orden's details.
- **locked_schedule**:
- **products**: Details about products.
- **car-join-product**: Table by car-product join.
- **categories**: Details about categories.
- **subcategories**: Details about subcategories.
- **stock**: Data about store stock.
- **cart**: Data by cart and relation.
- **product_atributes**: Atributes for eech product.
- **product_gallery**: Repo of gallery.
- **delivery_address**: Users address.

[![N|Solid](https://user-images.githubusercontent.com/57742000/85934079-af647d80-b8a3-11ea-9281-33b4fc93fe75.png)](https://user-images.githubusercontent.com/57742000/85934079-af647d80-b8a3-11ea-9281-33b4fc93fe75.png)

## API

### Structure

Below is the basic aesthetics of the API files, we can all find the api folder where the component folder is located, which contains the paths of each of the data tables that will be useful for client requests, in addition we find the config folder that houses the environment variables that allow the initialization of different application processes, on the other hand, there is the utils folder that contains .js files that allows developing tests, to finish find the store folder that houses files that allow set the logic for connecting the database to the application.

[![N|Solid](https://user-images.githubusercontent.com/57742000/85934139-534e2900-b8a4-11ea-985b-03aaa5d986db.png)](https://user-images.githubusercontent.com/57742000/85934139-534e2900-b8a4-11ea-985b-03aaa5d986db.png)

Regarding files, it is important to highlight the index.js file that is at the root of the structure and that contains the following logic.

- **index.js**

```sh
const express = require('express');                // Framework
const { api } = require('./config/index');         // API URL

const swaggerUi = require('swagger-ui-express');

const swaggerDoc = require('./swagger.json');
const categoriesApi = require('./api/components/categories/network')
const subcategoriesApi = require('./api/components/subcategories/network');
const countriesApi = require('./api/components/countries/network');
const stateApi = require('./api/components/states/network');
const citiesApi = require('./api/components/cities/network');
const productsApi = require('./api/components/products/network');


const app = express();                             // app declarations
app.use(express.json());                           // Type application/json


                                                   //Route documentation
app.use('/api-docs', swaggerUi.serve, swaggerUi.setup(swaggerDoc));

categoriesApi(app);                                // categories route
subcategoriesApi(app);                             // subcategories route
countriesApi(app);                                 // countries route
stateApi(app);                                     // state routes
citiesApi(app);                                    // cities routes
productsApi(app);                                  // products routes


app.listen(api.port, function () {                 // Server declarations
  console.log(`App listening on the http://localhost:${api.port}`);
});
```

- **package.json**


```sh
{
  "name": "backend",
  "version": "1.0.0",
  "description": "API RESET Ecommerce",
  "main": "index.js",
  "scripts": {
    "dev": "DEBUG=app:* nodemon index",           // Run dev project 
    "start": "NODE_ENV=production node index"     // Run pro project 
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/Dragmon/Ecommerce-Violeta.git"
  },
  "author": "",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/Dragmon/Ecommerce-Violeta/issues"
  },
  "homepage": "https://github.com/Dragmon/Ecommerce-Violeta#readme",
  "dependencies": {
    "dateformat": "^3.0.3",                        // Date format dependent 
    "dotenv": "^8.2.0",                            // Environment dependent
    "express": "^4.17.1",                          // Node framework
    "mysql": "^2.18.1"                             // MySQL connection 
  },
  "devDependencies": {
    "eslint": "^7.2.0",
    "eslint-config-prettier": "^6.11.0",
    "eslint-plugin-prettier": "^3.1.4",
    "husky": "^4.2.5",
    "lint-staged": "^10.2.11",
    "nodemon": "^2.0.4",
    "prettier": "^2.0.5",
    "swagger-ui-express": "^4.1.4"
  },
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "*.js": "eslint --cache --fix"
  }
}

```

## Tools

The main tools used in the development of the API were:

- Postman

[![N|Solid](https://user-images.githubusercontent.com/57742000/85936419-4b9c7d80-b8c0-11ea-8652-fdc2ad124e40.png)](https://user-images.githubusercontent.com/57742000/85936419-4b9c7d80-b8c0-11ea-8652-fdc2ad124e40.png)

- mysql workbench

[![N|Solid](https://www.logolynx.com/images/logolynx/87/872481164d523dd24b3577852ce5ff81.jpeg)](https://www.logolynx.com/images/logolynx/87/872481164d523dd24b3577852ce5ff81.jpeg)
