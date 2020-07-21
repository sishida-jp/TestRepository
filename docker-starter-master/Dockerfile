FROM golang:1.12-alpine
# copy files to /app in the container
ADD . /app/
# set our working directory to /app
WORKDIR /app
# build it, make it static
RUN GOOS=linux go build -o test-server
# create an unprivileged user
RUN adduser -D -g '' appuser
# use unprivileged user
USER appuser
# expose on port 8080
EXPOSE 8080
# run the file
CMD ["./test-server"]
