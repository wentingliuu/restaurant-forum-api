# Restaurant Forum API
A restaurant forum website built with [Node.js](https://nodejs.org/en/), [Express.js](https://expressjs.com/), and [MySQL](https://www.mysql.com/). Create your own account to CRUD restaurants info, leave comments to restaurants, follow or unfollow other forum users and so on. 🍣 🍔 🍲


🌟 This project is deployed on **[HEROKU](https://floating-dusk-15723.herokuapp.com/)** as well !!!
🌟 Please use the following **[dummy data]** to login, or register your own account.

| Email             | Password | Role                                       |
| ------------------| ---------| ------------------------------------------ |
| user1@example.com | 12345678 | User (access to front-stage)               |
| root@example.com  | 12345678 | Admin (access to front-stage & back-stage) |


## Features

*  **CREATE:** record your expense (with item name, date, category, amount) at the create page 
*  **READ:** review all the expenses at the home page
*  **UPDATE:** click the edit button to modify expense's data
*  **DELETE:** click the delete button to delete the expense
*  **FILTER:** filter the expenses by category

| Function                       | Detail | URL                                       |
| -------------------------------| ---------| ------------------------------------------ |
| REGISTER                       | sign up an account with name, email, password | GET /signup               |
| LOGIN                          | sign in to browse the website | GET /signin |
| LOGOUT                         | sign out the account by clicking the logout button | GET /logout |
| BROWSE ALL RESTAURANTS         | users could browse all restaurants' info in main page | GET /restaurants |
| FILTER RESTAURANTS BY CATEGORY | users could filter the restaurants by click the category buttons | GET /restaurants?categoryId=id |
| BROWSE SPECIFIC RESTAURANT     | users could browse sepcific restaurant by click the restaurant's name | GET /restaurants/:id |
| LEAVE COMMENTS                 | users could browse sepcific restaurant by click the restaurant's name | POST /restaurants/:id |
| GET LATEST FEEDS               | a page to show latest restaurants and comments | GET /restaurants/feeds |
| TOP 10 RESTAURANTS             | a page to show top 10 restaurants ranking by add-to-favorite counts | GET /restaurants/top |
| TOP USERS                      | a page to show users ranking by the followed counts | GET /users/top |
| SPECIFIC USER                  | users could read specific user's profile by clicking user's photo | GET /users/:id |
| EDIT USER PROFILE              | users could edit their own profile, including uploading profile photo | PUT /users/:id |
| (Admin) READ ALL RESTAURANTS   | admin could view full restaurants list at back-stage | GET /admin/restaurants |
| (Admin) READ A RESTAURANT      | admin could view a restaurant info by clicking "Show" at back-stage | GET /admin/restaurants/:id |
| (Admin) CREATE A RESTAURANT    | admin could create a new restaurant by clicking "New Restaurant" at back-stage | POST /admin/restaurants |
| (Admin) UPDATE A RESTAURANT    | admin could update a restaurant info by clicking "Edit" at back-stage | PUT /admin/restaurants/:id |
| (Admin) DELETE A RESTAURANT    | admin could delete a restaurant by clicking "Delete" at back-stage | DELETE /admin/restaurants/:id |
| (Admin) READ ALL USERS         | admin could view full users list at back-stage | GET /admin/users |
| (Admin) EDIT USER ROLE         | admin could change user's role by click "set as admin" at back-stage | POST /admin/users/:id |


## Installation and Execution
1.  Clone the files to your computer
```
git clone https://github.com/wentingliuu/restaurant-forum-api.git
```
2. Init: install the npm packages
```
cd restaurant-forum-api
```
```
npm install
```
3. Create .env file and store API Key in the file
```
touch .env
```
- Please see [.env.example](https://github.com/wentingliuu/restaurant-forum-api/blob/main/.env.example) for reference.
- Please get your own IMGUR_CLIENT_ID from [Imgur](https://api.imgur.com/oauth2/addclient).
4. Direct to ./config/config.json, and modify "username" & "password" in "development" section to map your local Sequelize setting.
5. Setup local database at SQL Workbench
```
drop database if exists forum;
create database forum;
```
6. Create data in locl database
```
npx sequelize db:migrate
```
```
npx sequelize db:seed:all
```
7. Run the project
```
npm run dev
```
- While the terminal returns `Express is listening on localhost:3000`, please visit http://localhost:3000 on your browser.


## Skills & Tools
*  [Node.js](https://nodejs.org/en/) & [npm](https://www.npmjs.com/) - JavaScript runtime environment
*  [Express.js](https://expressjs.com/) - web application framework
*  [Express-Handlebars](https://www.npmjs.com/package/express-handlebars) - template engine
*  [MySQL](https://www.mongodb.com/) - relational database management system
*  [Sequelize](https://mongoosejs.com/) - a Node.js ORM tool for MySQL
*  [body-parser](https://www.npmjs.com/package/body-parser) - middleware
*  [method-override](https://www.npmjs.com/package/method-override) - middleware
*  [express-session](https://www.npmjs.com/package/express-session) - middleware
*  [passport-jwt](http://www.passportjs.org/) - authentication middleware for Node.js
*  [bcrypt.js](https://www.npmjs.com/package/bcryptjs) - middleware for hashing a password
*  [multer](https://www.npmjs.com/package/multer) - middleware for uploading files
*  [imgur](https://www.npmjs.com/package/imgur-node-api) - middleware for uploading images to imgur

