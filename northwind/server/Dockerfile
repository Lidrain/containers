FROM node:latest

ENV APP_ROOT=/app APP_PORT=3000 
ENV DB_HOST=localhost DB_PORT=3306 DB_USER=root DB_PASSWORD=changeit

WORKDIR ${APP_ROOT}

ADD main.js . 
ADD package.json .
ADD config config
ADD public public
ADD views views

RUN npm install

EXPOSE ${APP_PORT}

HEALTHCHECK --interval=30s --timeout=5s --retries=3 \
    CMD curl -f http://localhost:${APP_PORT}/health > /dev/null || exit 1

ENTRYPOINT ["node", "main.js"]