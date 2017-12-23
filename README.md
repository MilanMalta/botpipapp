# Simple example of a python bot deployable on [Heroku](https://heroku.com)
Complete and simple example to host your python bot on Heroku.com

## Note
**I highly recommend reading about the [heroku cli](https://devcenter.heroku.com/articles/getting-started-with-python#set-up) to setup heroku for a successful deployment!**

There are four required files in this repo for a successful deployment to heroku:
- 'bot.py': This is your python code
- 'Procfile': This calls the python file when you start your bot with 'heroku ps:scale worker=1'
- requirements.txt (can be empty)
- 'runtime.txt': specifies your python version

## Explanation of files
### bot.py
Contains all of your python code and is called when you start the bot

### Procfile
Calls bot.py when you start the bot. 'worker' is arbitrary but must be the same as specified in the Procfile

`Start your bot with: heroku ps:scale worker=1`

### requirements.txt
Lists all required packages to be downloaded by heroku on deployment. Here, you can **list every module you import** in the python file. **Dont include out of the box modules like time or traceback!** Leave empty if in doubt.

### runtime.txt
Specify the python version to be used.

## Deployment Crash-Course

**1. Download the [heroku cli](https://devcenter.heroku.com/articles/getting-started-with-python#set-up)**
```sh
$ heroku login
```

**2. [Clone my repo](https://devcenter.heroku.com/articles/getting-started-with-python#prepare-the-app)**
```sh
$ git clone https://github.com/972C8/simple_heroku_bot.git
$ cd simple_heroku_bot
```

**3. [Push the cloned repo to heroku](https://devcenter.heroku.com/articles/getting-started-with-python#deploy-the-app)**
```sh
$ heroku create
$ git push heroku master
$ heroku ps:scale worker=1 #start the bot
$ heroku logs --tail
$ heroku ps:scale worker=0 #stop the bot
```

## Contributing
Feel free to contribute to either the code example or the documentation.
