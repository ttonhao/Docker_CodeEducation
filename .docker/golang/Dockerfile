FROM golang as builder

RUN go get github.com/golang/example/hello/...

FROM scratch
COPY --from=builder /go/bin/hello /go/bin/hello
ENTRYPOINT ["/go/bin/hello"]