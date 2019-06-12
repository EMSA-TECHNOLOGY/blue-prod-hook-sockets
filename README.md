# blue-prod-hook-sockets

Implements Socket.io support in blue-prod.

> This is a core hook in the [blue-prod framework](http://sailsjs.com).  You can override or disable it using your `.sailsrc` file or environment variables.  See [Concepts > Configuration](http://sailsjs.com/documentation/concepts/configuration) for more information.


## Help

If you have further questions or are having trouble, click [here](https://github.com/EMSA-TECHNOLOGY/blue-prod-hook-sockets/issues).

#### What version of Sails is this for?

This hook is for Sails v1.0 and up.

> Prior to Sails v1.0, this hook was a dependency of Sails core.  But now, it is now installed as a direct dependency of your Sails app.

#### What is this?  What does it do?

This repo contains a hook, one of the building blocks Sails is made out of.

This hook's responsibilities are:

+ **When initialized...**
  + fire up socket.io server
  + listen for connect / disconnect events
    + listen for get/post/put/delete/patch events
      + create bare-bones request and response contexts, then pass them to the core interpreter in Sails to be routed on the fly.
  + Bind `after` "shadow" routes...
    + `GET /__getcookie`
  + Expose on the `sails` app object:
    + `sails.sockets.*` _(see [Reference > WebSockets > sails.sockets](http://sailsjs.com/documentation/reference/web-sockets/sails-sockets))_


#### What version of Socket.io does this hook use?

Click [here](./package.json) to check out the semver range for this hook's Socket.io dependency.

> For reproducibility, we always pin 3rd party dependencies to a specific version, using a consistent verified version string when possible (see [kit](http://github.com/mikermcneil/kit)).


#### Bugs &nbsp; [![NPM version](https://badge.fury.io/js/blue-prod-hook-sockets.svg)](http://npmjs.com/package/blue-prod-hook-sockets)

To report a bug, [click here](https://github.com/EMSA-TECHNOLOGY/blue-prod-hook-sockets/issues).


## Contributing

[![NPM](https://nodei.co/npm/blue-prod-hook-sockets.png?downloads=true)](http://npmjs.com/package/blue-prod-hook-sockets)


#### Running the tests

First, clone this repo, cd into it, and install dependencies:

```sh
git clone https://github.com/EMSA-TECHNOLOGY/blue-prod-hook-sockets.git
cd blue-prod-hook-sockets
npm install
```

##### Run them all

To run all the tests, start a local redis server on port 6380 and then run the tests using mocha:

```sh
redis-server --port 6380 --requirepass 'secret'
npm test
```


##### Run only certain tests

Alternatively, you can run a particular set of tests with:

```sh
node ./node_modules/mocha/bin/mocha -g 'without session'
```

> (this may be useful if you don't want to wait for all the tests to run, or e.g. if you aren't able to install a redis server locally.  However please make sure all the tests pass before submitting a PR.)



## License

The [blue-prod framework](https://github.com/EMSA-TECHNOLOGY/blue-prod) is free and open-source under the [MIT License](https://github.com/EMSA-TECHNOLOGY/blue-prod-hook-sockets/blob/master/LICENSE.md).


