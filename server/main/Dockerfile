# Dockerfile for blobl.io Game Server (Go)
FROM golang:1.23-alpine AS builder
WORKDIR /app
COPY . .
RUN go build -o server

FROM alpine:latest
WORKDIR /app
COPY --from=builder /app/server /app/server
COPY --from=builder /app/data /app/data
EXPOSE 8080
CMD ["/app/server"]
