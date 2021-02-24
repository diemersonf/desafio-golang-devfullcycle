FROM golang:1.14 AS builder
WORKDIR /go/src/golang-app/
COPY app.go .
RUN go build -ldflags "-s -w" app.go

FROM scratch
WORKDIR /go/src/golang-app/
COPY --from=builder /go/src/golang-app/app/ .
ENTRYPOINT [ "./app" ]