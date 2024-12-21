# Build stage
FROM golang:alpine AS builder
WORKDIR /app
COPY . .
RUN go build -o main .

# Run stage
FROM alpine:latest
WORKDIR /root/
COPY --from=builder /app/main .
EXPOSE 3002
CMD ["./main"]
