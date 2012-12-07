Description of how to set up development environment

## Client App
It is highly recommended to use JetBrains' WebStorm IDE for development on the client side. It has great support for Node.js and general Javascript development, and the interface should be familiar to anyone who has used other JetBrains products before.

### Tests
The tests themselves are located under the "test" folder in the root directory of the the project. However, to run them you should visit the "scripts" folder where there are two scripts, "test.*" and "e2e-test.*", which kick off their respective test suites. These test scripts kick off the Testacular test runner using the respective configuration files found in the "config" folder.

The test scripts can be run using a terminal, but I recommend setting up separate run configurations in WebStorm. To do so, simply click Run -> Edit Configurations, then input the path to Testacular in the "Path to Node App JS File", and "start {path to config file}" as the Application Parameter. Here is an example of what it should look like:

![WebStorm Test Configuration](http://i.imgur.com/jAuTZ.png)