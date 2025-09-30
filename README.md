# asdf-doxygen

[![Build](https://github.com/jotoft/asdf-doxygen/actions/workflows/build.yml/badge.svg)](https://github.com/jotoft/asdf-doxygen/actions/workflows/build.yml)

[Doxygen](https://www.doxygen.nl/) plugin for the [asdf](https://asdf-vm.com/) version manager.

This plugin builds doxygen from source, allowing you to install any version available from the [official GitHub releases](https://github.com/doxygen/doxygen/releases).

## Contents

- [Dependencies](#dependencies)
- [Install](#install)
- [Usage](#usage)
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

### Plugin

```bash
asdf plugin add doxygen https://github.com/jotoft/asdf-doxygen.git
```

### Doxygen

```bash
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

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

See [LICENSE](LICENSE)
