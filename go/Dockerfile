FROM golang:1.19.3-alpine3.16 AS builder

WORKDIR /app

COPY . .

RUN  go build -ldflags "-s -w" -o build/hello hello.go

FROM scratch

WORKDIR /app

COPY --from=builder /app/build .

CMD ["./hello"]
