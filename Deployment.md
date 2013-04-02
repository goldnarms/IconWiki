Database:

The database is deployed on MongoHQ.(http://www.mongohq.com/home)

Push to Heroku: 

We have to instances to the app, one for production and one for test. Read [this article](http://tanyanam.com/technology/multiple-apps-on-heroku-from-the-same-git-repository) to see how you work with multiple apps from one git repository.

Apps:
* peaceful-journey-3435(Prod)
* ancient-bastion-7652 (Dev)

git push iconprod master (to push to prod)

git push iconat master (to push to dev)