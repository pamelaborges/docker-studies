FROM golang

LABEL description="Exemplo go"
LABEL version="1.0.0"

ENV GO111MODULE=auto

WORKDIR /app

ADD first.go /app

RUN go build -o firstgo

ENTRYPOINT ./firstgo
