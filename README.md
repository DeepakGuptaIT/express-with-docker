# express with docker 

## create express app
https://expressjs.com/en/starter/generator.html

## run the app
- command in package.json: "start": "node ./bin/www"
- Run: npm start


## video tutorial for express with docker
https://www.youtube.com/watch?v=tR3C6Dj9sO4&ab_channel=Thetips4you
- dockerfile should be same as I have created.
- port in app be same while running docker

## create docker file
... below content in docker file.
` FROM node:14
WORKDIR /usr/src/app
COPY ./package*.json /usr/src/app/
RUN npm install
COPY ./ /usr/src/app/
EXPOSE 8888
CMD [ "node", "./bin/www" ]
`

## create docker image
docker build -t deepakkumargupta/express-for-docker:1.1 .

## docker commands handy 
- check all images, run in cmd:
    - docker images
- check history of an image, run in cmd:
    - docker image history deepakkumargupta/express-for-docker:1.2
- check running containers:
    - docker ps

## run the docker image:
Run :
docker run -d -p 8888:8888 deepakkumargupta/express-for-docker:1.2



