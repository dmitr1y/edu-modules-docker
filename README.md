edu-modules
=====================
Site contains training modules developed by the students of [ETU "LETI"](http://www.eltech.ru/) in mathematics.

##Install
- [Install docker](https://docs.docker.com/engine/installation/)
- [Install docker-compose](https://docs.docker.com/compose/install/)
- Create docker network `docker network create nginx-proxy `
- Configure some modules*
- In root directory run `docker-compose build` for building images and then run `docker-compose up` for running project

###Configuring some modules

####boolean-solver
You need to place app folder with name `boolean-solver` to `./boolean-solver/` for copying into container.

####evklid-trainer
You need to change the access data in file `./evklid-trainer/access.js` on your own.