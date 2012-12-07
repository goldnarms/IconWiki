#"IDE's":#IDE's
#"Node.js server/REST API":## Node.js server/REST API

## IDE's
It is highly recommended to use [JetBrains' WebStorm IDE](http://www.jetbrains.com/webstorm/) for development on the Client App, Node.js server, and REST API. It has great support for Node.js and general Javascript development, and the interface should be familiar to anyone who has used other JetBrains products before.

## Node.js server/REST API
### NPM
To install external dependencies you can use Node's package manager, NPM. Simply browse to the root directory of the project in a terminal and run the command **_npm install_**. This will prompt NPM to check the packages.json file for what libraries to fetch and install.

### Setting up WebStorm
To set up the solution in WebStorm is quite straightforward. Simply open the project root directory, and you're set.
To make a run configuration just press Run -> Edit Configurations, then point the Node App JS file to **_~/scripts/server.js_**, like so:

![Webstorm Node.js Run Configuration](http://i.imgur.com/3xfUd.png)

## Client App
### Tests
The tests themselves are located under the **_~/test_** folder. However, to run them you should visit the **_~/scripts_** folder where there are two scripts, **_test.*_** and **_e2e-test.*_** (.bat and .sh versions exist), which kick off their respective test suites. These test scripts kick off the Testacular test runner using the respective configuration files found in the **_~/config_** folder.

The test scripts can be run using a terminal, but I recommend setting up separate run configurations in WebStorm. To do so, simply click Run -> Edit Configurations, then input the path to Testacular in the "Path to Node App JS File", and "start {path to config file}" as the Application Parameter. Here is an example of what it should look like:

![WebStorm Test Configuration](http://i.imgur.com/jAuTZ.png)