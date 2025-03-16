FROM rust:1-bookworm AS builder

WORKDIR /usr/src/app

RUN apt-get update && apt-get install -y musl-tools

RUN rustup target add x86_64-unknown-linux-musl

COPY ./Cargo.toml ./Cargo.lock ./

COPY . .

RUN cargo add openssl --features vendored

RUN cargo build --release --target x86_64-unknown-linux-musl

FROM scratch
LABEL maintainer="Supphachoke Suntiwichaya <mrchoke@gmail.com>"

WORKDIR /app


COPY --from=builder /usr/src/app/target/x86_64-unknown-linux-musl/release/hello .

EXPOSE 4000

CMD ["./hello"]

