FROM golang:1.21.0 AS build
WORKDIR /usr/src/app
COPY . .
RUN go mod download && go mod verify
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o app .

FROM alpine
WORKDIR /root/
COPY --from=build /usr/src/app .
EXPOSE 9000

CMD ["./app"]