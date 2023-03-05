# KNLS

## commands ran

`express knls --view=pug` - knls is the name of our project and the template we are going to use is pug.

`npm install` - this command helps us install dependencies.

## nodemon

to always restart our server automatically we need nodemon dependency.

`npm install --save-dev nodemon` - this would automatically install nodemon as one of your devdependencies in your project.

## dependencies

1. cookie-parser - used to phrase the cookie headers and populate `req.cookies`
2. debug - A tiny node debugging utility modeled after node core's debugging technique.
3. morgan -  An HTTP request logger middleware for node.
4. http-errors - Create HTTP errors where needed (for express error handling).

## [app.js](app.js)

the first few lines are used to import the necessary modules/libraries we shall need for our application to work.

```javascript
const indexRouter = require("./routes/index");
const usersRouter = require("./routes/users");
```

the above two lines are used to handles routes. the first one deals with the routes to handle routes that goes through the home page

the next route is used to handle user-related routes i.e sign up, login, profile management.

when you go the location of this files - you will find that in those files is where we handle our routes.

## var app = express()

this initiates an express.js instance - this will help us define routes, middleware and other application-level settings

i.e to create routes you will :

1. app.get()
2. app.post()
3. app.put()

this correspond to the http methods GET, POST, PUT

### app.set()

app.set() - this is used to set various application-level settings, it takes two arguments - the name of the setting to be set and its value.

let's say we are going to use the ejs as our templating engine: `app.set("view engine", "ejs")`

we can set things like:

1. view engine - templating engine
2. views - directory where our views live
3. port - the port number our application should listen to
4. env - the environment that the application is running in development, production
5. trust proxy - whether or not to trust the X-Forwarded-For header (if running behind a reverse proxy)

It's important to note that some settings have default values that can be overridden by calling app.set().

### app.use()

is a method in Express.js that is used to add middleware functions to the application's request processing pipeline. Middleware functions are functions that have access to the request and response objects, and can perform various tasks such as logging, authentication, error handling
etc. before or after the application's route handlers are called.

app.use() takes a single argument, which is the middleware function to be added to the pipeline. Middleware functions can be defined inline as anonymous functions or passed as named functions.

we can also set routes here:

```javascript
app.use("/", indexRouter);
app.use("/users", usersRouter);
```

## module.exports = app

module.exports is often used to export the app object, which represents the application itself. By exporting the app object, other modules or files in the application can access and use the application's functionality.

## views/templates

views are stored in `/views` directory. we are using pug templating engine so they will have a .pug extension.
