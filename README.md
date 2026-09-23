# mitm_maintenance_config

This is a standalone maintenance CLI tool for the MitM-2 Data Aggregator system. It is used to manually encrypt and decrypt `.enc` configuration files using AES-256-GCM and Argon2id.

This tool was extracted from the legacy Go `mitm_scheduler` codebase to ensure backwards compatibility and provide a decoupled way to manage encrypted JSON configurations for the new Rust `core-layer`.

## Build

Ensure you have a valid Go 1.22+ toolchain installed.

```bash
go build -o encrypt-config main.go
```

## Usage

### Encrypt a JSON Configuration

Provide a raw JSON file (e.g., `config.json`). The tool will prompt you to enter and confirm a password.

```bash
./mitm_maintenance_config config.json config.enc
```

### Decrypt an Encrypted Configuration

Use the `-d` flag to decrypt a `.enc` file back to JSON. The tool will prompt for the password.

```bash
./mitm_maintenance_config -d config.enc decrypted_config.json
```

## Security Note

The tool uses `AES-256-GCM` authenticated encryption. Keys are derived from the supplied password and a randomly generated salt using `Argon2id`.
