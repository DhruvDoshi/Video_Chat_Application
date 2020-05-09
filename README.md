<p align="center">
  <a href="" rel="noopener">
 <img width=200px height=200px src="https://i.imgur.com/FxL5qM0.jpg" alt="Bot logo"></a>
</p>

<h3 align="center">multichat-dhruv</h3>

<div align="center">

[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![GitHub Issues](https://img.shields.io/github/issues/DhruvDoshi/multichat-dhruv.svg)](https://github.com/DhruvDoshi/multichat-dhruv/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/DhruvDoshi/multichat-dhruv.svg)](https://github.com/DhruvDoshi/multichat-dhruv/pulls)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)

</div>

---

<p align="center"> Multiple Users could chat over the platform
    <br> 
</p>

## 📝 Table of Contents

- [About](#about)
- [How it works](#working)
- [Usage](#usage)
- [Getting Started](#getting_started)
- [Deploying your own bot](#deployment)
- [Built Using](#built_using)
- [TODO](../TODO.md)
- [Contributing](../CONTRIBUTING.md)
- [Authors](#authors)
- [Acknowledgments](#acknowledgement)

## 🧐 About <a name = "about"></a>

With the help of this platform multiple users could have a video chat. This platform doesn't saves any single bit of data on the servers. We only present the video and completely delete it


## 💭 How it works <a name = "working"></a>

The platform extracts the data with Webrtc Api and the it connects the users throught that api, continuing with that we are adding multiple modes and filters for the users.

The app is designed to take only 2 users as the time and others will wait their way in the waiting room until the conversation is over.

The entire bot is written in JavaScript

## 🎈 Usage <a name = "usage"></a>

The application is hosted over the heruku and the like is listed in the description.


## 🏁 Getting Started <a name = "getting_started"></a>

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See [deployment](#deployment) for notes on how to deploy the project on a live system.

### Prerequisites

What things you need to install the software and how to install them.

```
  - [Node.js](https://nodejs.org/) v4+
  - [Python 3](https://python.org/) v3.6+
  - [Git ](https://git-scm.com/) v2.26.0+
  - [pip ](https://pip.pypa.io/en/stable/) v19+
  - [Docker ](https://docs.docker.com/release-notes/) v19.03.8+
 
```

### Installing

A step by step series of examples that tell you how to get a development env running.

Say what the step will be

```
git clone https://github.com/DhruvDoshi/multichat-dhruv
```
```
cd multichat-dhruv
```
```
npm install
```
```
npm start 
```


## 🚀 Deploying your own application <a name = "deployment"></a>

$ heroku create
Creating app... done, ⬢ thawing-inlet-61413
https://thawing-inlet-61413.herokuapp.com/ | https://git.heroku.com/thawing-inlet-61413.git
```

You can use the ```git remote``` command to confirm that a remote named ```heroku``` has been set for your app:
```
$ git remote -v
heroku  https://git.heroku.com/thawing-inlet-61413.git (fetch)
heroku  https://git.heroku.com/thawing-inlet-61413.git (push)
```

#### For an existing Heroku App
If you have already created your Heroku app, you can easily add a remote to your local repository with the ```heroku git:remote``` command. All you need is your Heroku app’s name:
```
$ heroku git:remote -a thawing-inlet-61413
set git remote heroku to https://git.heroku.com/thawing-inlet-61413.git
```

### Changing your App name on Heroku <a name="changing_your_app_name_on_heroku"></a>
You can rename an app at any time with the ```heroku apps:rename command```. For example, to rename an app named “oldname” to “newname”, run the ```heroku apps:rename``` command from your app’s Git repository:
```
$ heroku apps:rename newname
Renaming oldname to newname... done
http://newname.herokuapp.com/ | git@herokuapp.com:newname.git
Git remote heroku updated
```

You can also rename an app from outside of its associated Git repository by including the ```--app``` option in the command:
```
$ heroku apps:rename newname --app oldname
http://newname.herokuapp.com/ | git@herokuapp.com:newname.git
```

**💡 Note:** When you rename an app, it immediately becomes available at the new corresponding ```herokuapp.com``` subdomain (```newname.herokuapp.com```) and unavailable at the old one (```oldname.herokuapp.com```).

If you use the Heroku CLI to rename an app from inside it's associated Git repository, your local Heroku remote is updated automatically. However, other instances of the repository must update the remote’s details manually.

You can run the following commands to update the remote’s details in other repository instances:
```
$ git remote rm heroku
$ heroku git:remote -a newname
```

Replace ```newname``` with the new name of the app, as specified in the ```rename``` command.

### Deploying code <a name="deploying_code"></a>
To deploy your app to Heroku, you typically use the ```git push``` command to push the code from your local repository’s ```master``` branch to your ```heroku``` remote, like so:
```
$ git push heroku master
Initializing repository, done.
updating 'refs/heads/master'
  ...
```

Code diffs, manual and auto deploys via GitHub are also possible. To use GitHub as a deployment method:
```
Heroku Dashboard > Select your App > Deploy > Deployment Method > Connect to GitHub > App connected to GitHub > Select your GitHub repo
```

Thereafter, you can deploy code from your GitHub repo. If you have a local Git repo (if you have cloned your main GitHub repo), you will have to push your code to GitHub by using:
```
$ git push origin master
```

#### Deploying from a branch besides master
If you want to deploy code to Heroku from a non-```master``` branch of your local repository (for example, ```testbranch```), use the following syntax to ensure it is pushed to the remote’s ```master``` branch:
```
$ git push heroku testbranch:master
```

### After setting up repo on Heroku <a name="after_setting_up_repo_on_heroku"></a>
Once you've got your repo set up on Heroku, there's two things you'll have to change:
1. Can't use a prop (credentials) file for username / password anymore since it's untracked in your gitignore, so you'll have to set environmental variables.
2. Heroku has an ephemeral File System, and you can't preserve generated files between runs (aka pickle caching isn't an option).

To solve 1), you'll have to set environmental variables. You can set it like this from terminal:
```
# Set heroku config/env variables
$ heroku config:set reddit_username=<your_reddit_username>
$ heroku config:set reddit_password=<your_reddit_password>
$ heroku config:set client_id=<your_client_id>
$ heroku config:set client_secret=<your_client_secret>

# Confirm they're set with this command
$ heroku config
```

And programmatically retrieve it in your code like this:
```
# Retrieve heroku env variables
reddit_username = os.environ['reddit_username']
reddit_password = os.environ['reddit_password']
client_id = os.environ['client_id']
client_secret = os.environ['client_secret']
```

To solve 2), a temporary solution would be to save comments as soon as you reply to them. If a comment has been saved (use ```comment.saved``` to check), then don't reply to that comment. Else, reply to that comment and then save it. To save a comment, use:
```
comment.save()
```

This is a temporary solution because Reddit has a max cap of 1000 for the number of comments / posts you can save.

A better solution would be to use a Database to store all the comment IDs. For this, you can use one of Heroku's many data storing / caching options. While most of these add-ons are free, they need you to verify yourself - by adding a credit card to your account.

The Heroku Postgres add-on however, does not require you to verify yourself. Heroku Postgres is a reliable and powerful database based on PostgreSQL. We'll be using the Heroku Postgres as the database for our Bot.

## ⛏️ Built Using <a name = "heroku"></a>

- [Heroku](https://www.heroku.com/) - SaaS hosting platform

## ✍️ Authors <a name = "authors"></a>

- [@kylelobo](https://github.com/DhruvDoshi) - Idea & Initial work

See also the list of [contributors](https://github.com/DhruvDoshi/multichat-dhruv/contributors) who participated in this project.

## 🎉 Acknowledgements <a name = "acknowledgement"></a>

- Hat tip to anyone whose code was used
- Inspiration
- References
