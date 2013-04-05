## Database

The database is deployed on [MongoHQ] (http://www.mongohq.com/home).
- Username: azure@itema.no

## Client app 

The app lives on [Heroku](https://id.heroku.com/login) in two instances, one for development/testing and one for production. Deployment to Heroku is done through the GitHub repositories. 

- Username: azure@itema.no

### Applications

- Development: `itema-icon-dev`
- Production: `itema-icon`

### Setting up remotes for Heroku

To push from you local Git repository to Heroku, you need to add a remote destination for each application. First you must [download and install the Heroku toolbelt, and log on to Heroku] (https://devcenter.heroku.com/articles/quickstart). Then you can add the remotes:

- Open a terminal shell
- Navigate to your Icon project root folder
- Execute `git remote add <remote name> <Heroku Git URL>`
 
The Heroku Git URL is found on the application settings page. The `<remote name>` values may be whatever you like, but the rest of the documentation will assume you called them `icon-prod` and `icon-dev`.

You can chech which remotes you have available at any given time by executing `git remote -v`.

### Adding your SSH key to Heroku

Heroku uses SSH keys to authenticate you, and the public key must be uploaded before you can deploy the app. 

- Navigate to your iCon project root folder
- Execute `heroku keys:add`

Heroku toolbelt will then upload an existing key (or create a new one for you). 

### Setting up environment variables

A few environment variables (e.g. MongooseDB connection string), must be set on the Heroku apps before they can run as expected. Environment variables are set by:

- Navigate to you iCon project root folder
- Execute `heroku config:add <variable name>=<variable value> --app <heroku app name>`

You may list existing variables using `heroku config --app <heroku app name>`.

### Pushing from GitHub to Heroku

- Navigate to your iCon project root folder
- Execute `git push <git remote name> master`
- Wait for the push to complete

### Resources

- [Multiple apps on Heroku from same GIT repository](http://tanyanam.com/technology/multiple-apps-on-heroku-from-the-same-git-repository)