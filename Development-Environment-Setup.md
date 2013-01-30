Table of contents

## Node.js

The client app and REST API runs in a node.js webserver environment, hence node.js must be installed on localhost to do development. 
 
1. [Download and install node.js](http://nodejs.org/), follow the instructions on the site. 
1. Use a terminal (cmd or terminal) to test if it works by executing `node`. A `>` prompt should appear. (CTRL+C exits the prompt).

iCon relies on external node packages, which is listed in the projects `packages.json` file. The Node Package Manager installs these automatically.

1. Navigate to your iCon project root folder. 
1. Execute `npm install`.
1. Wait for the downloads/installs to complete. 
1. If errors occur, repeat `npm install`.

## Database
iCon uses the NoSQL database MongoDB, which must be installed on localhost. 

1. [Download and install MongoDB](http://docs.mongodb.org/manual/installation/).
1. Start MongoDB by executing `mongod`, a log message should appear. 
1. Test if MongoDB is working by execution the MongoDB shell: `mongo`. A `>` prompt should appear.
1. Execute `show dbs` to display a list of local databases.

### Database initialization

When first installed, MongoDB is missing the iCon database. 

// TODO: mer om initialisering

## IDE's
It is highly recommended to use [JetBrains' WebStorm IDE](http://www.jetbrains.com/webstorm/) for development on the Client App, Node.js server, and REST API. It has great support for Node.js and general Javascript development, and the interface should be familiar to anyone who has used other JetBrains products before.

### Setting up WebStorm
To set up the solution in WebStorm is quite straightforward. Simply open the project root directory, and you're set.
To make a run configuration just press Run -> Edit Configurations, then point the Node App JS file to **_~/scripts/server.js_**, like so:

![Webstorm Node.js Run Configuration](http://i.imgur.com/3xfUd.png)

### Test framework
The test specs are located under the **_~/test/unit/web_api_** folder. jasmine-node, spec-helper...

## Client App
### Test framework
The test specs are located under the **_~/test_** folder. However, to run them you should visit the **_~/scripts_** folder where there are two scripts, **_test.*_** and **_e2e-test.*_** (.bat and .sh versions exist), which kick off their respective test suites. These test scripts kick off the Testacular test runner using the respective configuration files found in the **_~/config_** folder.

The test scripts can be run using a terminal, but I recommend setting up separate run configurations in WebStorm. To do so, simply click Run -> Edit Configurations, then input the path to Testacular in the "Path to Node App JS File", and "start {path to config file}" as the Application Parameter. Here is an example of what it should look like:

![WebStorm Test Configuration](http://i.imgur.com/jAuTZ.png)