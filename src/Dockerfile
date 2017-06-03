
# BASE image
FROM alpine:3.1 AS base

# Update
RUN apk add --update nodejs

# Copy project file
COPY package.json /src/package.json

# Bundle app source
COPY . /src


# RELEASE image
FROM base AS release

# Install node dependencies
RUN cd /src; npm install

# Expose port and define cmd
EXPOSE  8080
CMD ["node", "src/app.js"]


