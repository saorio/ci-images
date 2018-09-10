FROM golang:1.10.3
RUN curl https://glide.sh/get | sh
RUN go get -u github.com/alecthomas/gometalinter
RUN gometalinter --install
