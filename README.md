Sidekiq plugin for Dokku
----------------------

Adds a post-deploy hook to Dokku to automatically deploy a container running a Sidekiq worker 

Assumes you have a REDIS server running and have specified a REDIS_URL in your dokku app ENV file such as
export REDIS_URL=redis://172.17.0.20:6379/0 

Project: https://github.com/progrium/dokku

Installation
------------
```
cd /var/lib/dokku/plugins
git clone https://github.com/bigboxsoftware/dokku-sidekiq sidekiq
dokku plugins-install
```

For dokku 0.4.0 and after:

```shell
dokku plugin:install https://github.com/bigboxsoftware/dokku-sidekiq
```

Commands
--------
```
$ dokku help
     sidekiq:activate <app>     Activate automatic deployment of a sidekiq worker 
     sidekiq:deactivate <app>   Deactivate automatic deployment of a sidekiq worker
```

Simple usage
------------

Specify a Sidekiq worker should be started up for a deployed app:
```
$ dokku sidekiq:activate foo              # Server side
$ ssh dokku@server sidekiq:activate foo # Client side



