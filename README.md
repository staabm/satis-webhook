# Satis Webhook

This package allows you to easily setup a post-receive hook for your Satis on services like Github.

## Getting started

First of all, you need to configure some basic information about where your Satis files are stored.

```sh
cp config.yml.dist config.yml
```

- **bin**: The location of your *bin/satis* file. Default: ```bin/satis```.
- **json**: The location of your *satis.json* file. Default: ```satis.json```.
- **webroot**: The location of your satis webroot, where packages.json is going to be dumped. Default: ```web/```.
- **user**: The location of your *bin/satis* file. This parameter is optional and default to ```null```.

Make your ```webhook.php``` file accessible, for example:

```
http://satis.yourcompany.com/webhook.php
```

## Serve with PHPs builtin Webserver

In case your cli command requires more privilidges/permissions then your default webserver user has (e.g. www-data) you might also use php's builtin webserver. Start it with the required user and proxy incoming scripts thru your regular webserver.

nohup php -S 127.0.0.1:8000 & > /dev/null 2>&1
