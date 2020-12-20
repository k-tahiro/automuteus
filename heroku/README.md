# Self-Hosting via Heroku

This directory is for self-hosting via Heroku.

## How to use

### Requirements

- Configured [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)

### Steps

1. Create `.env` file in this directory. Basically you can copy `sample.env` file and edit `DISCORD_BOT_TOKEN`.
2. Run `$ ./deploy.sh APP_NAME`. You should specify you own `APP_NAME`. For example, `$ ./deploy.sh my-own-muteus`.
3. [Maybe required] Start worker process from [heroku dashboard](https://dashboard.heroku.com/apps).

## Structure

There are 4 components to deploy AutoMuteUs.
Here is the correspondence  of these components.

- automuteus: worker dyno
- galactus: web dyno
- redis: heroku addon
- postgres: heroku addon

All of these heroku services can be used as free!

### web dyno docker image

This docker image serves 2 apis.

- galactus: for AutoMuteUs Bot
- broker: for Capture Application

Basically heroku web dyno can serve only 1 api, because web dyno can open only 1 port.  
In this structure, add `nginx` as reverse-proxy to serve 2 apis via 1 port. 

And use `supervisord` to run these 2 processes in web dyno container.

- galactus
- nginx
