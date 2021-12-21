# Papermerge - Documentation

Papermerge documentation is based on [sphinx-doc](https://www.sphinx-doc.org)
which uses [reStructuredText](https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html) as
markup language.

Documentation is divided into 4 sections:

1. Installation
2. Help
3. User's Manual
4. REST API

## Online Verion

Online version of Papermerge documentation is availale [here](https://docs.papermerge.io/)


## Docker - Production Image

In order to browse documentation **locally** get its latest docker production image from
docker hub:

    docker pull papermerge/documentation

``papermerge/documentation`` docker image exposes web service on port 80 i.e. it
serves documentation in html format using nginx on port 80:

    docker run -d --name docs -p 9010:80 papermerge/documentation


## Docker - Development Mode

In development mode docker image ``papermerge/documentation-dev`` mounts
local documentation source and:

1. serves it via port 80
2. automatically rebuilds (regenerates html files) when you change source code

First clone this repository:

    git clone https://github.com/papermerge/documentation


Then pull ``papermerge/documentation-dev`` image from docker hub:

    docker pull papermerge/documentation-dev

Change your current working directory to the folder where code
was cloned into and from there run:

    docker run --name docs-dev  -p 9012:80 -v "$(pwd)/src:/docs/src" papermerge/documenation-dev

## Contributors

Before making changes to documentations, please make sure that:

1. Your English level is decent
2. You understand the basics of [reStructuredText](https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html)
format

## Repository Branches

For each papermerge major version there is separate repository branch in this
repository.

Papermerge 2.0.x documentation can be found in branch 2.0.x of this
repository.
Papermerge 2.1.x documentation is found in branch 2.1.x.
Master branch in this repository corresponds to latest (in development) version
of papermerge.
