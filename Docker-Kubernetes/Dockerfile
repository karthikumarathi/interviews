# Start from base image
FROM golang:alpine

# update packages
RUN apk update && apk add --no-cache git

# Maintainer Info
LABEL maintainer="Karthikkumar Athi"

# Set Environment Variable
ENV GO111MODULE=on

# Set the app directory
WORKDIR /app

# Copy go mod and sum files - populate module cache
COPY go.mod go.sum ./

# Download all dependancies
RUN go mod download

# Copy the source from the current directory to Working Directory
COPY . .

# Build the app

RUN go build -o main .

# Expose port 8000
EXPOSE 8000

# start the app
ENTRYPOINT ["/app/main"]


