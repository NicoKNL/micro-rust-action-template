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
        uses: NicoKNL/micro-rust-action-template@v1
```

For the latest stable release, use a specific version tag:

```yaml
- name: Run Micro Rust Action
  uses: NicoKNL/micro-rust-action-template@v1.0.0
```

## Releases

This action uses [Google's Release Please](https://github.com/googleapis/release-please) for automated releases based on [Conventional Commits](https://www.conventionalcommits.org/).

### How it works:

1. 🤖 **Automatic PR creation**: Release Please monitors commits and creates release PRs
2. 📝 **Changelog generation**: Automatically generates changelogs from conventional commits
3. 🏷️ **Semantic versioning**: Automatically bumps versions based on commit types
4. � **Automated publishing**: When release PR is merged, Docker images are built and published

### Commit Message Format

Use conventional commits to trigger releases:

```bash
feat: add new feature        # Creates minor version bump (1.0.0 → 1.1.0)
fix: fix bug                # Creates patch version bump (1.0.0 → 1.0.1)
feat!: breaking change      # Creates major version bump (1.0.0 → 2.0.0)
chore: update dependencies   # No version bump
docs: update readme         # No version bump
```

### Available Tags

- `@main` - Latest development version (not recommended for production)
- `@v1` - Latest stable v1.x.x release (recommended)
- `@v1.0.0` - Specific version (most stable)

### Creating a Release

1. **Make commits** using conventional commit format
2. **Wait for Release Please** to create a release PR
3. **Review and merge** the release PR
4. **Automatic publishing** happens - Docker images built and published to GHCR

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
├── .github/
│   ├── workflows/
│   │   ├── test.yml                     # CI/CD testing workflow
│   │   └── release.yml                  # Release Please workflow
│   ├── release-please-config.json       # Release Please configuration
│   └── .release-please-manifest.json    # Release Please version manifest
├── src/
│   └── main.rs                          # Main Rust application
├── Cargo.toml                           # Rust project configuration
├── Dockerfile                           # Container configuration
├── action.yml                           # GitHub Action metadata
├── CHANGELOG.md                         # Auto-generated changelog
└── README.md                            # This file
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes using [Conventional Commits](https://www.conventionalcommits.org/)
4. Test locally
5. Submit a pull request

### Conventional Commit Examples:

```bash
feat: add input parameter support
fix: resolve Docker build issue
docs: update usage examples
chore: update dependencies
```

## License

See [LICENSE](LICENSE) for details.
