# ZMK Agent Guidelines

## Build Commands
- **Full build**: `west build -b <board> -d build/<board>`
- **Clean build**: `west build -b <board> -d build/<board> -p`
- **Build with config**: `west build -b <board> -d build/<board> -- -DZMK_CONFIG=<config_path>`

## Test Commands
- **Run single test**: `app/run-test.sh <path/to/test>`
- **Run all tests**: `app/run-test.sh all`
- **Run BLE tests**: `app/run-ble-test.sh`

## Code Style Guidelines

### C/C++ Code
- **Formatting**: clang-format with LLVM base style
- **Indentation**: 4 spaces
- **Line length**: 100 columns maximum
- **Includes**: Manual ordering (no auto-sort)
- **Braces**: Always on new line for functions/structs
- **Naming**: snake_case for variables/functions, SCREAMING_SNAKE_CASE for macros/constants

### JavaScript/TypeScript
- **Formatting**: prettier with ES5 trailing commas
- **End of line**: Auto-detect
- **Linting**: ESLint with strict TypeScript rules + React recommended

### General
- **Error handling**: Use LOG_ERR for errors, return appropriate error codes
- **Memory management**: Check for NULL pointers, use IS_ENABLED() for config checks
- **Includes**: Group by type (system, zephyr, zmk local)
- **Comments**: SPDX license headers required, descriptive function comments optional

## Pre-commit Hooks
Run `pre-commit install` to enable automatic formatting/linting on commit:
- clang-format for C/C++ files
- prettier for JS/TS/MDX files
- gitlint for commit messages
- trailing whitespace removal

## Commit Messages
Follow conventional commits format when possible.</content>
<parameter name="filePath">AGENTS.md