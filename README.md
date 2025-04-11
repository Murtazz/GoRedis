# GoRedis

GoRedis is a lightweight Redis-like server implemented in Go. It listens on port `6379` and supports basic Redis commands such as `SET` and `HSET`. The server persists data to an append-only file (`database.aof`) for durability.

## Features

- Supports basic Redis commands (`SET`, `HSET`, etc.).
- Data persistence using an append-only file (`database.aof`).
- Lightweight and easy to deploy using Docker.

## Requirements

- Go 1.23 or later
- Docker (optional, for containerized deployment) needed for windows...

## Getting Started

### Running Locally

1. Clone the repository:
   git clone https://github.com/Murtazz/GoRedis.git
   cd GoRedis

2. Build and run the server:
   go build -o goredis .
   ./goredis

3. The server will start listening on port `6379`.

### Running with Docker

1. Build the Docker image:
   docker compose build

2. Start the container:
   docker compose up

3. The server will be accessible on port `6379`.

### Redis CLI

You can use the Redis CLI to interact with the server:
   redis-cli -p 6379

## File Persistence

The server uses an append-only file (`database.aof`) to persist data. Ensure the file has the correct permissions if running in a Docker container.

## Project Structure

- `main.go`: The main entry point for the server.
- `Dockerfile`: Docker configuration for building the container.
- `compose.yaml`: Docker Compose configuration for running the server.
- `database.aof`: Append-only file for data persistence.

## Troubleshooting

### Permission Denied for `database.aof`

If you encounter a `permission denied` error for `database.aof`, ensure the file or directory has the correct permissions:
   chmod 666 database.aof

Alternatively, use a Docker-managed named volume as described in the `compose.yaml` file.
