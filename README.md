# Containerize-React-ToDo-App

In the getting-started-app directory, the same location as the package.json file, create a file named Dockerfile with the following contents:


# Syntax to create Dockerfile

$$Begining of script$$
FROM node:lts-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000
$$End of script$$

# Navigate to getting-started-app Directory
navigate to files 
||cd getting-started-app||

# Build the image
||docker build -t getting-started .||

# Start an app container
Now that you have an image, you can run the application in a container using the docker run command.
Run your container using the docker run command and specify the name of the image you just created:
||docker run -d -p 127.0.0.1:3000:3000 getting-started||

# Run the <<docker ps>> command in a terminal to list your containers.
||docker ps||

# Output similar to the following should appear.

CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                      NAMES
df784548666d        getting-started     "docker-entrypoint.sâ¦"   2 minutes ago       Up 2 minutes        127.0.0.1:3000->3000/tcp   priceless_mcclintock

