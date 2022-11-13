FROM golang:1.19.3-alpine3.16 AS builder

WORKDIR /app

COPY . .

RUN  go build -o build/hello hello.go

FROM alpine:2.6

WORKDIR /app

COPY --from=builder /app/build .

CMD ["./hello"]
