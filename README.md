# PM2 Buildpack

This buildpack install [pm2](https://github.com/unitech/pm2), [gc-stats](https://github.com/dainis/node-gcstats) and [event-loop-inspector](https://github.com/keymetrics/event-loop-inspector).

## Install

Add nodejs buildpack:
```shell
heroku buildpacks:set https://github.com/heroku/heroku-buildpack-nodejs
```

Add pm2 buildpack at index 2:
```shell
heroku buildpacks:add --index 2 https://github.com/ItsJimi/heroku-buildpack-pm2
```

To start your node app with pm2, go to your `package.json`:
```json
"scripts": {
  "start": "pm2 start index.js --deep-monitoring --attach"
}
```

To monitor your application with [pm2](https://pm2.io/), got to your [PM2 Dashboard](https://app.pm2.io), get `public key` and `secret key`. After, you can go to heroku [apps](https://dashboard.heroku.com/apps/) settings, `Reveal  Config Vars` button and add:
```
KEYMETRICS_PUBLIC
```
and
```
KEYMETRICS_SECRET
```
