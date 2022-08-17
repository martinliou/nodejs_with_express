### Feature :
- There are only 6 endpoints created, consisting of Browse, Read, Edit, Add, Delete (BREAD).
- Only consists of 1 table, i.e. user table.
- There are no access level / role attributes in this user table to distinguish the access rights of each user.
- The JWT token generated has not been used.
- Only 11 test cases have been made.

## Steps to start this project on your machine
To run this project, you must have installed nodejs and postgresql.

Version of Node.js:
```
node --version
v12.13.0
```
Version of PostgreSQL:
```
psql --version
psql (PostgreSQL) 11.2
```

## Starting Development
```
Install all required dependencies using `npm` or you can also use` yarn`:
```
npm install or yarn install
```
If you want to run the project in `development` or` testing` mode, then you must set the database configuration according to the database configuration on your machine, such as `username`,` password` and `host`, then it is recommended that you name the database you are using for `development` or` testing` mode is different to avoid the things you don't want, and all this configuration you have to do in the `config / config.js` file.
For `development` mode you must set it here :
```
"development": {
    "username": "DATABASE_USER_NAME",
    "password": "DATABASE_PASSWORD",
    "database": "DATABASE_DEVELOPMENT_NAME",
    "host": "DATABASE_HOST",
    "dialect": "postgres"
  },
```
For `testing` mode you must set it here :
```
"test": {
    "username": "DATABASE_USER_NAME",
    "password": "DATABASE_PASSWORD",
    "database": "DATABASE_TEST_NAME",
    "host": "DATABASE_HOST",
    "dialect": "postgres"
  },
```
Create a database and table in `development` mode :
```
npm run db:start
```
Creates a database and tables in `testing` mode :
```
npm run db:test:start
```
Run a test :
```
npm run test
```
After running the test, you will see the results of testing coverage of this repository

The benefit of using swagger is that we can test the endpoints that we have made when the project has been deployed or in other words when in production mode, but you have to turn off comments on line 8 and vice versa you have to make line 7 as a comment in the file ` app.js` and make changes to `HOST` with` YOUR_HOST_APP` :
```
...
7 // const HOST_APP = 'localhost:3000';
8 const HOST_APP = YOUR_HOST_APP;
...
```
In the `development` mode, you have to turn off comments on line 7 and vice versa you have to make line 8 as a comment in the` app.js` file :
```
...
7 const HOST_APP = 'localhost:3000';
8 // const HOST_APP = YOUR_HOST_APP;
...
```
Run the server, can use `npm` or` thread` :
```
npm run start or yarn start
```
Then, you can access this project at the address : http://localhost:3000, for the swagger documentation you can access it at this address : http://localhost:3000/api-docs/