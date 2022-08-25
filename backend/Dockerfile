FROM golang:1.19-alpine
ENV LANG='en_US.utf8'
ENV GO111MODULE='off'

ARG POSTGRES_DB
ARG POSTGRES_USER
ARG POSTGRES_PASSWORD
ARG POSTGRES_PORT
ENV POSTGRES_DB $POSTGRES_DB
ENV POSTGRES_USER $POSTGRES_USER
ENV POSTGRES_PASSWORD $POSTGRES_PASSWORD
ENV POSTGRES_PORT $POSTGRES_PORT

WORKDIR /go/app
COPY . /go/app

RUN apk --no-cache update
RUN apk add --no-cache git tzdata
RUN cp /usr/share/zoneinfo/Asia/Taipei /etc/localtime
RUN apk del tzdata
RUN rm -rf /var/cache/apk/*
RUN go get gopkg.in/urfave/cli.v2
RUN go get github.com/oxequa/realize

CMD realize start
