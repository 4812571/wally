# Build Stage
FROM rust:latest as builder

# Add source code to the build stage
ADD . /wally
WORKDIR /wally

# Build Project
RUN cargo build

FROM debian:bullseye-slim
COPY --from=builder /wally/target/debug/wally .