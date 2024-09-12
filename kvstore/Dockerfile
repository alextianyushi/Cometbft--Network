# Start from the latest golang base image
FROM golang:1.23 AS builder

# Set the Current Working Directory inside the container
WORKDIR /app

# Copy go mod and sum files
COPY go.mod go.sum ./

# Download all dependencies
RUN go mod download

# Copy the source to the container
COPY . .

# Build the Go app
RUN go build -mod=mod -o main .

# Expose port 26658 to the outside world
EXPOSE 26658

# Command to run the executable
CMD ["./main"]