# Build Stage
FROM rust:latest as builder

# Add source code to the build stage
ADD . /wally
WORKDIR /wally

# Build Project
RUN cargo build

# Package Stage
FROM debian:bullseye-slim

# Create Package
RUN mkdir src
RUN touch src/wally.toml

COPY --from=builder /wally/target/debug/wally .