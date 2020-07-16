# Nodejs express framework with mongoDB base

- [Install](#install)
- [Tests](#tests)
- [Docker](#docker)

<!-- /TOC -->

## Install

### Install mongoDB
Check [here](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)

### Install project

```sh
git clone git@github.com:thaont540/express_base.git
npm run setup # To install npm for node and react client
cp .env.example .env
npm run dev
```

Then visit [http://localhost:3000/](http://localhost:3000/) (for react app) and [http://localhost:3001/](http://localhost:3001/) (for node server app)

*Detail installation will come as soon as possible :D*

## Tests

```sh
npm test
```

## Docker

*Coming soon. Currently not working well*

You can also use docker for development. Make sure you run npm install on your host machine so that code linting and everything works fine.

```sh
npm i
cp .env.example .env
```

Start the services

```sh
docker-compose up -d
```

View the logs

```sh
docker-compose logs -f
```

In case you install a npm module while developing, it should also be installed within docker container, to do this first install the module you want with simple `npm i module name`, then run it within docker container

```sh
docker-compose exec node npm i
```

If you make any changes to the file, nodemon should automatically pick up and restart within docker (you can see this in the logs)

To run tests

```sh
docker-compose exec -e MONGODB_URL=mongodb://mongo:27017/noobjs_test node npm test
```

Note that we are overriding the environment variable set in `.env` file because we don't want our data erased by the tests.
