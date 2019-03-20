FROM golang:1.12.1-alpine3.9 AS build_base

RUN mkdir /app 
ADD src /app/src 
WORKDIR /app/src 

RUN apk add bash ca-certificates git gcc g++ libc-dev
RUN go build -ldflags "-w -s" -o ../server

EXPOSE 8080

FROM alpine:3.9.2 
COPY --from=build_base /app/server /bin/server
CMD ["/bin/server"]


