# download core image(like miny OS with bunch of preinstalled command)
FROM node:alpine

# create new folder for our project, commands below will execute inside this folder and
# all outside command too
WORKDIR /home/app/server

# it's needed to copy files inside folder to container fs
# in this case, we pre-copy files needed to npm install
# if some files will be changed, but not package.json
# hash for this step will be the same, so it's not needed
# to download all dependencies again on each build
COPY package.json .

# produce any available command inside container
RUN npm install

# copy the rest of files
COPY ./ ./

# set up start command
CMD ["npm", "run", "start"]