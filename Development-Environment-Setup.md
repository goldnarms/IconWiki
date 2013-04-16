## Node.js

The client app and REST API runs in a node.js webserver environment, hence node.js must be installed on localhost to do development. 
 
1. [Download and install node.js](http://nodejs.org/), follow the instructions on the site. 
1. Use a terminal (cmd or terminal) to test if it works by executing `node`. A `>` prompt should appear. (CTRL+C exits the prompt).

iCon relies on external node packages, which is listed in the projects `packages.json` file. The Node Package Manager installs these automatically.

1. Navigate to your iCon project root folder. 
1. Make Node.js install dependencies by executing `npm install`.
1. Wait for the installs to complete. 
1. If errors occur, repeat `npm install`.

## MongoDB
iCon uses the NoSQL database MongoDB. MongoDB can be installed on localhost, or you may use the MongoHQ test database to develop on. 

### Either: Install MongoDB on localhost 
1. [Download and install MongoDB](http://docs.mongodb.org/manual/installation/).
1. Start MongoDB by executing `mongod`, a log message should appear. 
1. Test if MongoDB is working by execution the MongoDB shell: `mongo`. A `>` prompt should appear.
1. Execute `show dbs` to display a list of local databases.
1. `exit` the shell.

#### Database initialization

When first installed, MongoDB is missing the iCon database. This needs to be initialized.

1. Navigate to the iCon project root folder.
1. Navigate to `test/unit/web_api`.
1. Make Node.js run the test_seed.js script: `node test_seed`.
1. Quite Node.js using CTRL+C.

The database should now be ready to use. You may test it by starting MongoDB and look for the iCon database. 

1. Start the MongoDB shell by executing `mongo`.
1. List databases: `show dbs`. iCon should appear in the list. 

You can also use this script to populate the production DB while the Administrator interface is not available. Just supply a MongoDB url of the database you wish to populate as the first parameter to the `test_seed.js` script, like so: `node test_seed mongodb://user:pasword@url:port/dbname`

### Or: Use MongoHQ

[monghq.com](http://mongohq.com) is a site that hosts Mongo databases, which means no local installation is required. We still need the database connection string (the URL to which to connect to access the database). 

The connection string will be in the form: `mongodb://icon:<password>@linus.mongohq.com:10062/iCon_development`.

(DB password is found in the passwords folder).

## Developing without an IDE

### Environment variables

The webserver expects av few environment variables to be available before start.

- MongoDB connection string `mongodb_uri`: 
  - Local installation of MongoDB: `mongodb://localhost:27017/iCon`
  - MongoHQ: `mongodb://icon:<password>@linus.mongohq.com:10062/iCon_development`
- Server path for images `image_url_path`:
  - Heroku development: `http://iconadminat.azurewebsites.net`
  - Heroku production: `http://iconadmin.azurewebsites.net`

If the app is running locally the values can be set in the terminal (valid for one session) or in the system preferences (global). If it's running in a cloud service like Heroku, they must be set in the config there. 

(The `scripts/dev.env` file defines defaults used by the dev startup script). 

#### Setting local variables in the terminal 

- Mac: `export <name>=<value>`
- Windows: `fill inn the blank`
- Linux: `fill in the blank`

### Start you engines!

#### Either: Fire up the system manually 

1. Start MongoDB as described above (in it's own terminal window).
1. Navigate to the iCon project root folder.
1. Start the webserver: `npm start`.

Node package manager should then start Nodemon, which in turn starts Node.js, while monitoring .js, .less and .json files for changes. 

#### Or: Fire up the system using the startup script (local DB only)

Run the startup script:

- Windows: `run-dev.bat`
- Mac: `run-dev.sh`

The script is located under `scripts`. This should fire up a local mongodb database, a monitor watching the LESS files, and the Node.js server. The various processes are fired up and managed by [Foreman](https://github.com/nodefly/node-foreman). Processes are defined under `PROCFILE.dev` and environment variables are set in `dev.env`.

The webserver will now be listening on `localhost:3000`.

## Developing using the WebStorm IDE
It is highly recommended to use [JetBrains' WebStorm IDE](http://www.jetbrains.com/webstorm/) for development on the Client App, Node.js server, and REST API. It has great support for Node.js and general Javascript development, and the interface should be familiar to anyone who has used other JetBrains products before.

### Setting up WebStorm
To set up the solution in WebStorm is quite straightforward. Simply open the project root directory, and you're set.
To make a run configuration just press Run -> Edit Configurations, then point the Node App JS file to `~/scripts/server.js`. Also make sure you set the MongoDB connection string by adding an environment variable, `MONGODB_URI=mongodb://localhost:27017/iCon`, in the run configuration. Your run configuration should look something like this:

![Webstorm Node.js Run Configuration](http://i.imgur.com/tCG0mqT.png)

### Test framework
The test specs are located under the `~/test/unit/web_api` folder. jasmine-node, spec-helper...

## Client App
### Test framework
The test specs are located under the `~/test` folder. However, to run them you should visit the `~/scripts` folder where there are two scripts, `test.*` and `e2e-test.*` (.bat and .sh versions exist), which kick off their respective test suites. These test scripts kick off the Testacular test runner using the respective configuration files found in the `~/config` folder.

The test scripts can be run using a terminal, but I recommend setting up separate run configurations in WebStorm. To do so, simply click Run -> Edit Configurations, then input the path to Testacular in the "Path to Node App JS File", and "start {path to config file}" as the Application Parameter. Here is an example of what it should look like:

![WebStorm Test Configuration](http://i.imgur.com/jAuTZ.png)