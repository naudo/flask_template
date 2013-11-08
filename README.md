# Initial readme



## Heroku

### Getting Setup

To get started with heroku, download and install the heroku toolkbelt. This will install several things on your system for you, but we only care about the heroku client for now

https://toolbelt.heroku.com

While that is running, go head and signup on  http://heroku.com if you haven't already.

### Creating an app

Creating an app on heroku is super simple.  We'll start off by logging into heroku. From your command line run `heroku login`. It will ask you for your heroku email / password. If you haven't created a public / private key it will ask you to do that. Say Yes.


Now that you're logged in, it's time to create the app. If you're lazy / can't think of a name for your app, don't worry heroku will generate one if you leave off the name. Run `heroku create NAMEOFYOURAPP`. Assuming nobody has taken that name already, you're now the owner a shiny new heroku app!.

````bash
heroku create
Creating radiant-beach-5469... done, stack is cedar
http://radiant-beach-5469.herokuapp.com/ | git@heroku.com:radiant-beach-5469.git
Git remote heroku added
````


### Deploying

So now we have an app and we have a heroku account. Time to tie these two things together. As you may already know, heroku is built around git. What this means is we can push to heroku like it's any other git repository and have the changes show up for us. To do this, run `git push heroku master` 

Once this is done, your app will be deployed and [almost] ready to use! Run `heroku open` to get to your app!

### Database stuff
Chances are if you're making a web app, you'll have a database. If you're using the flask_template app, I'm also willing to bet you've been using SQLite. Well I have good news and bad news for you.  Bad news, Heroku doesn't work with SQLite and several of their engineers have said it probably never will. The good news, it doesn't matter! Heroku offers a free Postgres DB with every app.

Now at this point you're probably wondering, wait what? I've been using sqlite. How does Postgres help me? Will I have to start all over? Well... the flask_template app uses SQLAlchemy, which actualy doesn't care what you use as a DB.

### Misc

#### Best practices
Don't be afraid to force push to heroku. 
Treat Heroku like a tranient repo

#### Are you a wizard? Where did the Heroku remote come from?


#### Pushing feature branches

Heroku will only recognize changes on the master branch. Fortunately there is a trick we can use to push our local feature branch into the heroku master branch.

` git push heroku FEATURE_BRANCH:master` This will push the feature branch into the master branch on master


#### Anything else I should know?

Heroku is readonly (well there is write access but output is limited to the dyno that wrote to that file. )

