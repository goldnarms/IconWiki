## Database

The database is deployed on [MongoHQ] (http://www.mongohq.com/home).
- Username: azure@itema.no

## Client app 

The app lives on [Heroku](https://id.heroku.com/login) in two instances, one for development/testing and one for production.

- Username: azure@itema.no

### Applications

- Development: `ancient-bastion-7652`
- Production: `peaceful-journey-3435`

### Setting up remotes for Heroku

To push from you local Git repository to Heroku, you first need to add a remote destination for each application.

- Open a terminal shell
- Navigate to your Icon project root folder
- Execute `git remote add <remote name> <Heroku Git URL>`
 
The Heroku Git URL is found on the application settings page. The `<remote name>` values may be whatever you like, but the rest of the documentation will assume you called them `icon-prod` and `icon-dev`.

### Pushing from GitHub to Heroku

Deployment to Heroku is done through the GitHub repositories. 

- Development: `git push iconat master`
- Production: `git push iconprod master`

### Authenticating with Heroku


### Resources

- [Multiple apps on Heroku from same GIT repository](http://tanyanam.com/technology/multiple-apps-on-heroku-from-the-same-git-repository)
