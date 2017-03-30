[![Build Status](https://travis-ci.org/kuzzleio/kuzzle-plugin-auth-passport-local.svg?branch=master)](https://travis-ci.org/kuzzleio/kuzzle-plugin-auth-passport-local)

# Plugin Local Password Authentication

This plugin provides a local authentication with username/password with [passportjs module](http://passportjs.org/docs/username-password).

By default, this plugin is already installed in Kuzzle.

# Configuration

The default configuration is:

```json
{
  "secret": null,
  "algorithm": "sha256",
  "digest": "hex"
}
```

All the configurations are used to set the behavior of the password hash.
If `secret` is `null`, it will be generated automatically when the plugin is initalized for the first time.
To change this configuration please refer to the [Plugin reference](http://docs.kuzzle.io/plugin-reference/#custom-plugin-configuration).

Note: thesecretparameter is only used if there is no salt already configured in the database. If that's the case and if users are already stored, make sure that it matches the previously used salt

# Usage

Just send following data to the **auth** controller:

```json
{
  "body": {
    "strategy": "local",
    "username": "<username>",
    "password": "<password>"
  }
}
```

See [Kuzzle API Documentation](http://kuzzleio.github.io/kuzzle-api-documentation/#auth-controller) for more details about Kuzzle authentication mechanism.

# How to create a plugin

See [Kuzzle documentation](https://github.com/kuzzleio/kuzzle/docs/plugins.md) about plugin for more information about how to create your own plugin.

# About Kuzzle

For UI and linked objects developers, [Kuzzle](https://github.com/kuzzleio/kuzzle) is an open-source solution that handles all the data management
(CRUD, real-time storage, search, high-level features, etc).

[Kuzzle](https://github.com/kuzzleio/kuzzle) features are accessible through a secured API. It can be used through a large choice of protocols such as REST, Websocket or Message Queuing protocols.
