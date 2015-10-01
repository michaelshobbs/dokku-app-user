# dokku-app-user

dokku-app-user is a plugin for [dokku][dokku] that sets the `$USER` user for use with [herokuish][herokuish]

## Requirements

This plugin uses the `docker-args-*` hooks to inject the environment variable argument when dokku executes `docker run` and uses the app config value of `$DOKKU_APP_USER`. The current state of herokuish requires the user to already exist in your image. Thus this only works with custom herokuish docker images.

## Installation & Example

```sh
# Install the plugin:
# dokku 0.4+
dokku plugin:install https://github.com/expa/dokku-app-user.git

dokku config:set <app> DOKKU_APP_USER=expauser
git push dokku@dokku.me:<app> master
```

## License

This plugin is released under the MIT license. See the file [LICENSE](LICENSE).

[dokku]: https://github.com/progrium/dokku
[herokuish]: https://github.com/gliderlabs/herokuish
