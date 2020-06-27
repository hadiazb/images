# Documentation

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

- MySQL :  It is the most famous non-relational database engine on the planet, the developer team has used it because
because the business logic for an ecommerce requires multiple connections and above all because this engine is optimized
for transactions and other operations that make the app's functionalities easier in the future.

- React: It is a tool that allows you to develop components on the frontend side of the app, its speed is one of its characteristics,
since not reloading the page in each request will reduce the execution time of different tasks.

## NPM Packages

### Backend

Next, the NPM packages used on the Backend side will be listed.

- **dateformat**: It allows to facilitate the use of   date and time formats on the back side.
- **dotenv**: It allows the use of environment variables in our app.
- **express**:  It's a Node framework that decreases our code.
- **mysql**:  It allows the connection of our app with a local or remote mysql database.

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

* **users**: This table is related to the personal data of the user who uses the app.
* **orders**: 
Contains fields that are related to user order information
* **services**: 
This table is related to the additional services that e-commerce has. 
* **countries**: Data about the country customer.
* **cities**: Data about the city customer.
* **states**: Data about the state customer. 
* **method_payment**: This table is about method payment. 
* **reservations**: Details about reservation. 
* **service_schedule**: 
* **order_details**: Contains the orden's details.  
* **locked_schedule**:  
* **products**: Details about products. 
* **car-join-product**: Table by car-product join. 
* **categories**: Details about categories. 
* **subcategories**: Details about subcategories.
* **stock**: Data about store stock. 
* **cart**: Data by cart and relation.
* **product_atributes**: Atributes for eech product.
* **product_gallery**: Repo of gallery.
* **delivery_address**: Users address.

[![N|Solid](https://user-images.githubusercontent.com/57742000/85933961-6e1f9e00-b8a2-11ea-9e0f-dcfa8702d219.png)](https://user-images.githubusercontent.com/57742000/85933961-6e1f9e00-b8a2-11ea-9e0f-dcfa8702d219.png)
## API

### Structure 
