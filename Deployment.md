## Database

The database is deployed on [MongoHQ] (http://www.mongohq.com/home).
- Username: azure@itema.no

## Client app 

The app lives on [Heroku](https://id.heroku.com/login) in two instances, one for development/testing and one for production. Deployment to Heroku is done through the GitHub repositories. 

- Username: azure@itema.no

### Applications

- Development: `ancient-bastion-7652`
- Production: `peaceful-journey-3435`

### Setting up remotes for Heroku

To push from you local Git repository to Heroku, you need to add a remote destination for each application. First you must [download and install the Heroku toolbelt, and log on to Heroku] (https://devcenter.heroku.com/articles/quickstart). Then you can add the remote:

- Open a terminal shell
- Navigate to your Icon project root folder
- Execute `git remote add <remote name> <Heroku Git URL>`
 
The Heroku Git URL is found on the application settings page. The `<remote name>` values may be whatever you like, but the rest of the documentation will assume you called them `icon-prod` and `icon-dev`.

You can chech which remotes you have available at any given time by executing `git remote -v`.

### Pushing from GitHub to Heroku

Navigate to you iCon project root folder and deploy using the `git push` command:

- Development: `git push icon-dev master`
- Production: `git push icon-prod master`

### Resources

- [Multiple apps on Heroku from same GIT repository](http://tanyanam.com/technology/multiple-apps-on-heroku-from-the-same-git-repository)