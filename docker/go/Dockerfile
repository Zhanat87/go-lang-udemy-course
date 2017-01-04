# golang image where workspace (GOPATH) configured at /go.
# FROM golang:1.6-onbuild
# FROM golang:latest
FROM golang
# сначала надо залить все файлы в github
# затем обновить все файлы с github'а
# и тогда обновления появятся в докере
# так же надо все время перезапускать контейнер
# в главном docker-compose.yml файле, restart: always
RUN go get github.com/Zhanat87/go-lang-udemy-course
# Copy the local package files to the container’s workspace.
ADD . /go/src/github.com/Zhanat87/go-lang-udemy-course
# Setting up working directory
WORKDIR /go/src/github.com/Zhanat87/go-lang-udemy-course
# Get godeps for managing and restoring dependencies
RUN go get github.com/tools/godep
# Restore godep dependencies
# RUN godep restore
# Build the go-lang-udemy-course command inside the container.
RUN go install github.com/Zhanat87/go-lang-udemy-course
# Run the go-lang-udemy-course command when the container starts.
ENTRYPOINT /go/bin/go-lang-udemy-course
# Service listens on port 8082.
EXPOSE 80
