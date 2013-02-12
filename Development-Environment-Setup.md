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
iCon uses the NoSQL database MongoDB, which must be installed on localhost. 

1. [Download and install MongoDB](http://docs.mongodb.org/manual/installation/).
1. Start MongoDB by executing `mongod`, a log message should appear. 
1. Test if MongoDB is working by execution the MongoDB shell: `mongo`. A `>` prompt should appear.
1. Execute `show dbs` to display a list of local databases.
1. `exit` the shell.

### Database initialization

When first installed, MongoDB is missing the iCon database. This needs to be initialized.

1. Navigate to the iCon project root folder.
1. Navigate to `test/unit/web_api`.
1. Make Node.js run the test_seed.js script: `node test_seed`.
1. Quite Node.js using CTRL+C.

The database should now be ready to use. You may test it by starting MongoDB and look for the iCon database. 

1. Start the MongoDB shell by executing `mongo`.
1. List databases: `show dbs`. iCon should appear in the list. 

You can also use this script to populate the production DB while the Administrator interface is not available. Just supply a MongoDB url of the database you wish to populate as the first parameter to the `test_seed.js` script

## Developing without an IDE

The webserver expects an environment variable named `mongodb_uri` containing the MongoDB connection string to be available befor start. The URI is `mongodb://localhost:27017/iCon`.

1. Set the variable:
 1. Mac: `export MONGODB_URI=mongodb://localhost:27017/iCon`
 1. Windows: 
 1. Linux: 
1. Navigate to the iCon project root folder.
1. Start the webserver: `node server.js`.

OR

Run the script `run-dev.bat/sh` script located under scripts. This should fire up the mongodb database, a monitor watching the LESS files, and the Node.js server. The various processes are fired up and managed by [Foreman](https://github.com/nodefly/node-foreman). Processes are defined under `PROCFILE.dev` and environment variables are set in `dev.env`.

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