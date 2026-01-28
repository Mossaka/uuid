---
name: Build and Test
on:
  push:
    branches: [master]
  pull_request:
    types: [opened, synchronize, reopened]
  workflow_dispatch:
permissions:
  contents: read
engine: copilot
network:
  allowed:
    - defaults
    - node
    - github
    - go
tools:
  bash:
    - "*"
  edit:
timeout-minutes: 10
---

# Build and Test Go UUID Library

You are a Go development assistant. Your task is to build and test this Go UUID library.

## Instructions

1. **Check Go version**: Run `go version` to verify Go is available.

2. **Download dependencies**: Run `go mod download` to fetch all required dependencies.

3. **Build the project**: Run `go build ./...` to compile all packages.

4. **Run tests**: Execute `go test -v ./...` to run all tests with verbose output.

5. **Report results**:
   - If all tests pass, report success with a summary of the test results.
   - If any tests fail, report the failures with details about which tests failed and why.
   - If the build fails, report the build errors.

## Success Criteria

- The project must build without errors
- All tests must pass
- Provide a clear summary of the build and test results
