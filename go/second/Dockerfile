FROM golang AS stepBuild

LABEL description="Exemplo go"
LABEL version="1.0.0"

ENV GO111MODULE=auto

WORKDIR /app

ADD second.go /app

RUN go build -o secondgo


FROM alpine
WORKDIR /app
COPY --from=stepBuild /app/ /app
ENTRYPOINT ./secondgo
