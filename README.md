# rate-limiter

[![Build Status](https://img.shields.io/github/actions/workflow/status/user/rate-limiter/ci.yml?branch=main)]()
[![Go Version](https://img.shields.io/badge/go-1.22+-blue.svg)]()
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

> Distributed rate limiter using sliding window algorithm with Redis backend

A Go project focused on solving real-world engineering problems.

## Features

- Minimal Allocations: Designed to minimize GC pressure in hot paths
- Zero Dependencies: No external packages required for core functionality
- Graceful Shutdown: Clean shutdown handling with configurable drain timeout
- Structured Logging: Built-in structured logging with slog compatibility
- Context Support: Full context.Context propagation for cancellation and deadlines

## Installation

```bash
go get github.com/user/rate-limiter@latest
```

## Quick Start

```go
package main

import (
	"fmt"
	"github.com/user/rate-limiter"
)

func main() {
	client := ratelimiter.New(
		ratelimiter.WithTimeout(30 * time.Second),
	)

	result, err := client.Run(context.Background())
	if err != nil {
		log.Fatal(err)
	}

	fmt.Println(result)
}
```

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
