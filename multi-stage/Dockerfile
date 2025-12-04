# ---------- Stage 1: Build ----------
FROM golang:1.22-alpine AS builder

WORKDIR /app

# Disable modules + disable CGO → produce static binary
ENV GO111MODULE=off
ENV CGO_ENABLED=0

COPY . .

RUN go build -o main .

# ---------- Stage 2: Distroless ----------
FROM gcr.io/distroless/static:nonroot

WORKDIR /app

COPY --from=builder /app/main .

USER nonroot:nonroot

CMD ["./main"]

