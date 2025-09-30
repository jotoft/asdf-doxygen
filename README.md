# asdf-doxygen

[![Build](https://github.com/jotoft/asdf-doxygen/actions/workflows/build.yml/badge.svg)](https://github.com/jotoft/asdf-doxygen/actions/workflows/build.yml)

[Doxygen](https://www.doxygen.nl/) plugin for the [asdf](https://asdf-vm.com/) version manager and [mise](https://mise.jdx.dev/).

This plugin builds doxygen from source, allowing you to install any version available from the [official GitHub releases](https://github.com/doxygen/doxygen/releases).

## Contents

- [Dependencies](#dependencies)
- [Install](#install)
- [Usage](#usage)
- [Development](#development)
- [Contributing](#contributing)
- [License](#license)

## Dependencies

**All Operating Systems:**

- `bash`, `curl`, `tar`: Generic POSIX utilities
- `cmake`: Build system generator
- `make`: Build automation tool
- `gcc` or `clang`: C/C++ compiler
- `flex`: Fast lexical analyzer generator (required by doxygen)
- `bison`: Parser generator (required by doxygen)

**Arch Linux:**
```bash
sudo pacman -S base-devel cmake flex bison
```

**Ubuntu/Debian:**
```bash
sudo apt-get install build-essential cmake flex bison
```

**macOS:**
```bash
brew install cmake flex bison
```

## Install

### Using asdf

```bash
# Add the plugin
asdf plugin add doxygen https://github.com/jotoft/asdf-doxygen.git

# Show all installable versions
asdf list-all doxygen

# Install specific version
asdf install doxygen 1.12.0

# Set a version globally (in your ~/.tool-versions file)
asdf global doxygen 1.12.0

# Set a version locally (in your current directory's .tool-versions file)
asdf local doxygen 1.12.0
```

Check [asdf](https://github.com/asdf-vm/asdf) readme for more instructions on how to install & manage versions.

### Using mise

```bash
# Add the plugin
mise plugin add doxygen https://github.com/jotoft/asdf-doxygen.git

# Install specific version
mise use doxygen@1.12.0

# Or add to .mise.toml
echo '[tools]
doxygen = "1.12.0"' >> .mise.toml
```

Check [mise](https://mise.jdx.dev/) documentation for more information.

## Usage

Once installed, doxygen will be available in your PATH:

```bash
doxygen --version
```

To generate documentation for a project:

```bash
# Generate a default Doxyfile configuration
doxygen -g

# Run doxygen with the configuration
doxygen Doxyfile
```

## Development

This repository includes a `.mise.toml` file with tasks for plugin development and testing.

### Available Tasks

```bash
# Run shellcheck on all scripts
mise run lint

# Test the list-all script
mise run test-list

# Test downloading the latest version
mise run test-download

# Test full installation of latest version
mise run test-install

# Test installation of a specific version
mise run test-specific 1.12.0

# Run all tests
mise run test-all

# Clean up temporary files
mise run clean
```

### Testing Locally

To test the plugin locally before pushing:

```bash
# Clone the repository
git clone https://github.com/jotoft/asdf-doxygen.git
cd asdf-doxygen

# Run all tests
mise run test-all
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

See [LICENSE](LICENSE)
