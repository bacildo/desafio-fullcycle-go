#Builder
FROM golang:1.21.0-alpine3.17 AS build
WORKDIR /app
COPY . .
RUN go build -o main .

# Runner
FROM scratch
WORKDIR /app
COPY --from=build /app/main .
CMD ["/app/main"]