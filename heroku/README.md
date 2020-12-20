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

TBW
