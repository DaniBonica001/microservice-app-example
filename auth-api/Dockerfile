# Utiliza la imagen base de Golang
FROM golang:1.18.2 AS builder
WORKDIR /usr/src/app

ENV GO111MODULE=on
RUN go mod init github.com/bortizf/microservice-app-example/tree/master/auth-api
RUN go clean -modcache
COPY . .
#copia los archivos de configuracion donde esta el archivo dockerfile (.go) al workdir despues de que esto quede copiado se inicializa
RUN go mod tidy

#RUN go mod download && go mod verify
EXPOSE 8081

RUN go build -v -o /usr/local/bin/app .
#RUN go build -o /go/bin/myapp cmd/main.go

CMD [ "app" ]