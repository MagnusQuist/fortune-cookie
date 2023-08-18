# Dockerfile for backend
FROM golang:1.20.0 AS build-stage

WORKDIR /app
COPY . /app

RUN go build -o backend

FROM golang:1.20.0

WORKDIR /app
COPY --from=build-stage /app/backend /app/

CMD ["./backend"]
