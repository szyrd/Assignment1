FROM golang:1.23.1 AS builder
WORKDIR /app
COPY main.go .
RUN go mod init example.com/hello-world && \
    go mod tidy && \
    go build -o hello-world

    FROM alpine:latest
    WORKDIR /root/
    COPY --from=builder /app/hello-world .
    CMD ["./hello-world"]