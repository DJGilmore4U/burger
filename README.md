# Eat-A-Burger

# Node Express Handlebars Assignment

### Overview

In this assignment, I created a burger logger with MySQL, Node, Express, Handlebars and a homemade ORM (yum!). I followed the MVC design pattern; used Node and MySQL to query and route data in my app, and Handlebars to generate my HTML.

### Description

* Eat-Da-Burger! is a restaurant app that lets users input the names of burgers they'd like to eat.

* Whenever a user submits a burger's name, your app will display the burger on the left side of the page -- waiting to be devoured.

* Each burger in the waiting area also has a `Devour it!` button. When the user clicks it, the burger will move to the right side of the page.

* My app will store every burger in a database, whether devoured or not.

## What I Did

#### App Setup

1. Created a GitHub repo called `burger` and cloned it to my computer.

2. Made a package.json file by running `npm init` from the command line.

3. Installed the Express npm package: `npm install express`.

4. Created a server.js file.

5. Installed the Handlebars npm package: `npm install express-handlebars`.

6. Installed the body-parser npm package: `npm install body-parser`.

7. Installed MySQL npm package: `npm install mysql`.

8. Required the following npm packages inside of the server.js file:
   * express
   * body-parser

#### DB Setup

1. Inside my `burger` directory, created a folder named `db`.

2. In the `db` folder, created a file named `schema.sql`. Wrote SQL queries for this file that will do the following:

   * Create the `burgers_db`.
   * Switch to or use the `burgers_db`.
   * Create a `burgers` table with these fields:
     * **id**: an auto incrementing int that serves as the primary key.
     * **burger_name**: a string.
     * **devoured**: a boolean.

3. Still in the `db` folder, created a `seeds.sql` file. In this file, wrote insert queries to populate the `burgers` table with at least three entries.

4. Ran the `schema.sql` and `seeds.sql` files into the mysql server from the command line

5. Then I ran these SQL files.

   * Started MySQL command line tool and login: `mysql -u root -p`.

   * With the `mysql>` command line tool running, entered the command `source schema.sql`. This ran my schema file and all of the queries in it.

   * I inserted the entries I defined in `seeds.sql` by running the file: `source seeds.sql`.

   * Closed out of the MySQL command line tool: `exit`.

#### Config Setup

1. Inside my `burger` directory, created a folder named `config`.

2. Created a `connection.js` file inside `config` directory.

   * Inside the `connection.js` file, setup the code to connect Node to MySQL.

   * Exported the connection.

3. Created an `orm.js` file inside `config` directory.

   * Imported (require) `connection.js` into `orm.js`

   * In the `orm.js` file, created the methods that will execute the necessary MySQL commands in the controllers. These are the methods That I needed to use in order to retrieve and store data in my database.

     * `selectAll()`
     * `insertOne()`
     * `updateOne()`

   * Exported the ORM object in `module.exports`.

#### Model setup

* Inside my `burger` directory, created a folder named `models`.

  * In `models`, made a `burger.js` file.

    * Inside `burger.js`, imported `orm.js` into `burger.js`

    * Also inside `burger.js`, created the code that will call the ORM functions using burger specific input for the ORM.

    * Exported at the end of the `burger.js` file.

#### Controller setup

1. Inside my `burger` directory, created a folder named `controllers`.

2. In `controllers`, created the `burgers_controller.js` file.

3. Inside the `burgers_controller.js` file, imported the following:

   * Express
   * `burger.js`

4. Created the `router` for the app, and exported the `router` at the end of my file.

#### View setup

1. Inside your `burger` directory, created a folder named `views`.

   * Created the `index.handlebars` file inside `views` directory.

   * Created the `layouts` directory inside `views` directory.

     * Created the `main.handlebars` file inside `layouts` directory.

     * Setup the `main.handlebars` file so it's able to be used by Handlebars.

     * Setup the `index.handlebars` to have the template that Handlebars can render onto.

     * Created a button in `index.handlebars` that will submit the user input into the database.

#### Directory structure

```
.
├── config
│   ├── connection.js
│   └── orm.js
│ 
├── controllers
│   └── burgers_controller.js
│
├── db
│   ├── schema.sql
│   └── seeds.sql
│
├── models
│   └── burger.js
│ 
├── node_modules
│ 
├── package.json
│
├── public
│   ├── assets
│   │   ├── css
│   │   │   └── burger_style.css
│   │   └── img
│   │       └── burger.png
│   └── test.html
│
├── server.js
│
└── views
    ├── index.handlebars
    └── layouts
        └── main.handlebars
```
 
- - -

### Hosted on Heroku

- - -

### Added To My Portfolio

- - -