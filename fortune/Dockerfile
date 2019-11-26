FROM node:latest

# set environment variables
ENV APP_ROOT=/app APP_PORT=3000

# create directory and cd into it
WORKDIR ${APP_ROOT}

# copy files into the image
ADD main.js .
ADD package.json .
ADD public public
ADD views views

# run commands
RUN npm install

# how an image is provisioned

# ports to expose
EXPOSE ${APP_PORT}

HEALTHCHECK --interval=30s --timeout=5s --retries=3 \
    CMD curl -f http://localhost:${APP_PORT}/health > /dev/null || exit 1

ENTRYPOINT ["node", "main.js"]

 CMD [""]s