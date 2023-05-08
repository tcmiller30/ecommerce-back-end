
# E-Commerce Back End
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Description

This application simulates the back-end functionality of an e-commerce website using a Express.js and Sequelize to work with a MySQL database.

The example e-commerce api can search for various products, categories, and tags that one would find in a standard e-commerce site. These elements can also be created, updated with new information, or removed from the database entirely.

## Table of Contents

- [E-Commerce Back End](#e-commerce-back-end)
  - [Description](#description)
  - [Table of Contents](#table-of-contents)
  - [Installation](#installation)
  - [Usage](#usage)
  - [License](#license)
  - [Questions](#questions)

## Installation

This application requires multiple npm modules in order to run. Before use, the user should run the command ```npm i```/```npm install``` in their terminal to allow the program to install dependencies.

In addition to the npm modules, the user will need to download and install MySQL and an API Development Program such as [Insomnia](https://insomnia.rest/) to access the API routes.

In order for the server to connect to the database, a ```.env``` file must be configured. A ```.env.EXAMPLE``` file is included with the application. The ```DB_NAME``` is provided, but the user will need to populate the ```DB_USER``` and ```DB_PASSWORD``` fields with their own MySQL sign-in info.

Before running the program, navigate to the root folder, initialize the MySQL Shell, and type the command ```SOURCE db/schema.sql``` in order to create the database required by the program.


## Usage

In order to use this application, after having installed the necessary dependencies, the user should start by seeding the database by running the command ```npm run seed``` in your terminal. Once the database is properly seeded, the server can be initialized with ```npm start```.

If there were no errors, the application will alert the user that it is listening on whatever PORT is designated (:3001 as default). When you get the confirmation from the server, it is time to start Insomnia.

In Insomnia, the user should create at minimum 5 HTTP requests: 1 for GET (All) Routes, 1 for GET (Single) Routes, 1 for POST Routes, 1 for PUT Routes, and 1 for DELETE Routes. Doing this is not mandatory, but makes interacting with the application less laborious. One could create additonal HTTP Requests to handle the each Category, Product, and Tag Route within the application to make things even more efficient, but again this is not required.

Each Request route should start ```http://localhost:3001/api/```. Routes that reference the database's Categories should end ```/categories/```. Routes that reference the database's Products should end ```/products/```. Routes that reference the database's Tags should end ```/tags/```.

If the user is trying to reference a single row from the MySQL database, the path ```/:id``` should be added to the request route where ```:id``` = the id of the requested row. This can be easily found by making a GET all request.

For example, if you wanted to find all the products in the database, make a ```GET``` Request that references the route ```http://localhost:3001/api/products/```.

If instead you wanted to remove the third tag in the database, make a ```DELETE``` Request that references the route ```http://localhost:3001/api/tags/3```.

In order to make ```Post``` or ```Put``` Requests, the user will have to include a JSON file in the Request Body using Insomnnia. The Request Body will need to include different keys depending on which model from the database that is being interacted with. These different Request Bodies will be listed below.

  - For Categories
  ```
  {
    "category_name": "New Category"
  }
  ```

  - For Tags:
  ```
    {
      "tag_name": "New Tag"
    }
  ```

  - For Products
  ```
    {
	    "product_name": "New Product",
	    "price": 10.00,
	    "stock": 1,
	    "category_id": 1,
	    "tagIds": []
    }
  ```


Running the application a second time will result in the first index.html file being overwritten. In order to save the team profile, either rename the index.html file or move it out of the "dist" folder.

An example video of this application being set up and used can be viewed [here](https://drive.google.com/file/d/1XpPeAivNGUoEBEXbqxgvYBFaQ2wQ7CMx/view?usp=share_link)


## License

    MIT License

    Copyright (c) 2023 Travis Miller

    Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


## Questions

If you have any questions, comments, or concerns, contact the developer using the email provided below

Email: [traviscmiller01@gmail.com](mailto:traviscmiller01@gmail.com);

Check out the developer's other projects on GitHub by cicking the link below

GitHub Username: [tcmiller30](https://github.com/tcmiller30)
