# to declare on which image this one is based
# so no need to create everything from scratch
FROM node:latest

# just a label usually exposing the author
LABEL author="Dan Wahlin"

# environment variables
ENV NODE_ENV=production 
ENV PORT=3000

# where to start when starting up the container
WORKDIR   /var/www

# copy the whole project structure into the container
# provided creating the image and container is done on CL in the project root dir
COPY      . .

# what you want to run when creating the container
# as we need to install our dependencies into the container
RUN       npm install

# setting up a volume docker host will know where the image lives
# make sure it is after the RUN instruction 
# Whether you want a volume for a container like this is debatable
VOLUME ["/var/www"]

# exposing a port to connect to
EXPOSE $PORT

# the startup commands at container startup time, using a json array
ENTRYPOINT ["npm", "start"]
