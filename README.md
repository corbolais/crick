crick
=====

[![CircleCI](https://circleci.com/gh/TailorDev/crick/tree/master.svg?style=svg&circle-token=af802009a9119df1eb1869418316b2d742d65dda)](https://circleci.com/gh/TailorDev/crick/tree/master)

Crick is a backend for the [Watson](https://github.com/TailorDev/Watson) time-tracker, built during a "Le lab" session:

* https://tailordev.fr/blog/2017/06/07/le-lab-5-crick-a-backend-for-watson-time-tracker/

<p align="center">
  <img src="doc/project-report.gif">
<p>

## Installation

### API

Start the Docker environment (Golang and PostgreSQL containers) with the
following command lines:

    $ cd api/
    $ make dev

Be sure to apply all the migrations:

    $ make migrate-up

Get the API logs:

    $ make logs

Get help:

    $ make [help]

Stop and remove the Docker environment:

    $ make down

Load Watson's frames to your local server (python 3.4+ is required):

    $ CRICK_API_TOKEN='mytoken' python3 api/scripts/watson_push.py (-h)

#### About

The API documentation can be found in the `apiary.apib` file or online at:
http://docs.crickapi.apiary.io/. This HTTP API is written in Go and serves
two purposes: providing a endpoint for Watson synchronization and allowing
the web app to access data.

### Web app

    $ cd web/
    $ yarn install
    $ make dev

Browse: http://crick.dev:3000/.

#### About

The Web application is a [create-react-app](https://github.com/facebookincubator/create-react-app)
client side application. Authentication with the HTTP API relies on [Auth0](https://auth0.com/).


## Contributing

Please, see the [CONTRIBUTING](CONTRIBUTING.md) file.


## Running the test suite

    $ cd api/ && make test
    $ cd web/ && yarn test -- --watch=false


## Contributor Code of Conduct

Please note that this project is released with a [Contributor Code of
Conduct](http://contributor-covenant.org/). By participating in this project you
agree to abide by its terms. See [CODE_OF_CONDUCT](CODE_OF_CONDUCT.md) file.


## License

Crick is released under the MIT License. See the bundled [LICENSE](LICENSE)
file for details.
