# Dockerfile for frontend
FROM golang:1.21.0 AS build-stage

WORKDIR /app
COPY . /app

RUN go build -o frontend

FROM golang:1.21.0

WORKDIR /app
COPY --from=build-stage /app/frontend /app/

CMD ["./frontend"]
