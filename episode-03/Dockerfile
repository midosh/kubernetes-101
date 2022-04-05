FROM golang:1-alpine as build

WORKDIR /app
COPY cmd cmd
RUN go build cmd/hello/hello.go

FROM alpine:3.15.4

WORKDIR /app
COPY --from=build /app/hello /app/hello

EXPOSE 8180
ENTRYPOINT ["./hello"]
