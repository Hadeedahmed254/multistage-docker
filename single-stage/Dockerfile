FROM golang:1.22-alpine

WORKDIR /app
#beacusse i dont have any go.mod(module or packages file which is mandaotry)
ENV GO111MODULE=off

COPY . .

RUN go build -o main .

CMD ["./main"]

