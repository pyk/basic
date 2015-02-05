# basic

my personal static site generator

# Get started
make sure [nodejs](https://github.com/pyk/vagrant-ubuntu-trsusty64) machine started.

    sudo npm install
    bower install
    ./node_modules/.bin/gulp start

# Docker builder

    docker run --name CONTAINER_NAME -v $PWD:/x_data DOCKER_NODEJS_IMG /bin/bash -c 'cd x_data && npm install && npm install bower -g && bower install'
    docker commit -m "lugue builder" CONTAINER_NAME DOCKER_BUILDER_IMG:TAG
    docker run -v $PWD:/x_data -d DOCKER_BUILDER_IMG:TAG /bin/bash -c 'cd x_data && /x_data/node_modules/.bin/gulp build && /x_data/node_modules/.bin/gulp watch'

build `DOCKER_NODE_JS_IMG` from this [repo][docker-nodejs]. chane `CONTAINER_NAME` & `DOCKER_BUILDER_IMG:TAG` as you prefer.


[docker-nodejs]: https://github.com/pyk/docker-nodejs