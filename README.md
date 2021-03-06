## GridFS API

[ ![Codeship Status for rafaeljesus/gridfs-api](https://codeship.com/projects/79578d40-8337-0133-c7cc-2e117485f168/status?branch=master)](https://codeship.com/projects/121751)
[![Docker Image Pulls](https://img.shields.io/docker/pulls/rafaeljesus/gridfs-api.svg)](https://hub.docker.com/r/rafaeljesus/gridfs-api/) 
[![NPM version](http://img.shields.io/npm/v/gridfs-api.svg)](https://www.npmjs.org/package/gridfs-api)
[![bitHound Overall Score](https://www.bithound.io/github/rafaeljesus/gridfs-api/badges/score.svg)](https://www.bithound.io/github/rafaeljesus/gridfs-api)
[![bitHound Dependencies](https://www.bithound.io/github/rafaeljesus/gridfs-api/badges/dependencies.svg)](https://www.bithound.io/github/rafaeljesus/gridfs-api/master/dependencies/npm)
[![bitHound Dev Dependencies](https://www.bithound.io/github/rafaeljesus/gridfs-api/badges/devDependencies.svg)](https://www.bithound.io/github/rafaeljesus/gridfs-api/master/dependencies/npm)
[![bitHound Code](https://www.bithound.io/github/rafaeljesus/gridfs-api/badges/code.svg)](https://www.bithound.io/github/rafaeljesus/gridfs-api)

[![js-standard-style](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/rafaeljesus/gridfs-api)

* Exposes a REST API for MongoDB GridFS

## Installation
```bash
npm install -g gridfs-api
```

## Running server
To run a suite tests execute:
```bash
npm run build && npm run serve
```

## API Documentation
### create
```bash
curl -i -X POST 'http://localhost:3000/v1/files' \
 -F 'name=foo' \
 -F 'type=application/pdf' \
 -F 'metadata[userId]=1' \
 -F 'image=@/home/username/file.pdf'
```
 
### show
```bash
curl -X GET 'http://localhost:3000/v1/files/1'
```

### check-exists
```bash
curl -X GET 'http://localhost:3000/v1/files/1/check-exists'
```

### delete
```bash
curl -X DELETE 'http://localhost:3000/v1/files/1'
```

## Built with
- [nodejs](https://https://nodejs.org) Backend is a node-v.5.7.1.
- [koa](http://koajs.com) API is a KOA app. It respond to requests RESTfully in JSON.
- [Mongodb](https://www.mongodb.com) Mongodb as a data store.

## Docker
This repository has automated image builds on hub.docker.com.

Use [docker-mongodb](https://github.com/rafaeljesus/docker-mongodb) and run command described there

Finally run:
```
$ docker-machine start default
$ eval $(docker-machine env default)
$ docker run -it -e "NODE_ENV=development" -v "$(pwd)":/data --link mongo:mongo -w /data -p 3000:3000 rafaeljesus/gridfs-api
$ curl `docker-machine ip default`:3000
```

## Contributing
- Fork it
- Create your feature branch (`git checkout -b my-new-feature`)
- Commit your changes (`git commit -am 'Add some feature'`)
- Push to the branch (`git push origin my-new-feature`)
- Create new Pull Request

### Maintaners

* [Rafael Jesus](https://github.com/rafaeljesus)
