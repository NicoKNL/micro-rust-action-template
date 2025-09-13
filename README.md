# micro-rust-action-template

A minimal Rust-based GitHub Action that echoes "Hello World!" to demonstrate how to create a simple containerized action.

## Features

- Minimal Rust application
- Containerized with Docker
- Ready-to-use GitHub Action
- Simple "Hello World!" output

## Usage

To use this action in your workflow, add the following step to your `.github/workflows/your-workflow.yml`:

```yaml
name: Test Micro Rust Action

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Run Micro Rust Action
        uses: NicoKNL/micro-rust-action-template@main
```

## Local Development

### Prerequisites

- [Rust](https://rustup.rs/) (latest stable version)
- [Docker](https://www.docker.com/get-started)

### Building and Running Locally

1. Clone the repository:

   ```bash
   git clone https://github.com/NicoKNL/micro-rust-action-template.git
   cd micro-rust-action-template
   ```

2. Build and run with Cargo:

   ```bash
   cargo run
   ```

3. Or build and run with Docker:
   ```bash
   docker build -t micro-rust-action .
   docker run micro-rust-action
   ```

## Project Structure

```
├── src/
│   └── main.rs          # Main Rust application
├── Cargo.toml           # Rust project configuration
├── Dockerfile           # Container configuration
├── action.yml           # GitHub Action metadata
└── README.md            # This file
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test locally
5. Submit a pull request

## License

See [LICENSE](LICENSE) for details.
