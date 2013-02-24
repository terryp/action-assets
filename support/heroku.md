Action.IO integrates with Heroku for convenient and easy application deployment. Connecting your Action.IO box to Heroku is easy:

### 1. [Login](https://action.io/login) to your Action.IO account

If you don't already have an account, [sign up for an invite](https://action.io)

### 2. Create a Development Box

If you don't already have a box created, you'll need to create one on a platform that runs on Heroku.  Luckily, Heroku supports most environments.

You can read about [creating development boxes here](http://help.action.io/customer/portal/articles/802603-create-a-box)

![New Box Button](https://raw.github.com/action-io/action-assets/master/support/screenshots/new-box-button.png)

### 3. Connect your Box to Github

If you haven't already connected to Github, [Generate a public key for your newly created development box and add it to Github](http://help.action.io/customer/portal/articles/853510-adding-ssh-keys-to-github)

![Reveal Public Key](https://raw.github.com/action-io/action-assets/master/support/screenshots/reveal-public-key.png)

### 4. Authenticate with Heroku

     heroku login
     username: aj@action.io
     password: ********

### 5. Add your ssh key to heroku

     heroku keys:add

### 6. Configure git

     git config --global user.email “(your git email)”
     git config --global user.name “(your git username)”

### 7. Clone a Project

Since we've authenticated with Github, lets clone a git project that we'll be deploying to Heroku

     git clone git@gitbub.com:(username)/(reponame).git
     cd (repository name)
     (repository name)$: bundle install

### 8. Add the Heroku remote url

     (reponame)$: git remote add heroku git@heroku.com:(heroku-app-name).git

### 9. Update the upstream git branches

     (reponame)$: git branch --set-upstream master origin/master
     (reponame)$: git branch --set-upstream master heroku/master

And that's it!  Your development box will now be connected to your Heroku account and you can deploy as you would on your local machine.

Of course, if you're having trouble, you can always [talk to a real human](mailto: support@action.io?subject=Heroku%20Authenticaion%20Issues).
