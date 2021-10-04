# Mailmonkey

[![Rust](https://github.com/fosdickio/mailmonkey/actions/workflows/general.yml/badge.svg)](https://github.com/fosdickio/mailmonkey/actions/workflows/general.yml) [![Security audit (on push)](https://github.com/fosdickio/mailmonkey/actions/workflows/audit-on-push.yml/badge.svg)](https://github.com/fosdickio/mailmonkey/actions/workflows/audit-on-push.yml) [![Security audit (scheduled)](https://github.com/fosdickio/mailmonkey/actions/workflows/scheduled-audit.yml/badge.svg)](https://github.com/fosdickio/mailmonkey/actions/workflows/scheduled-audit.yml)

## Requirements

- Rust (1.55.0+)
- Cargo (1.55.0+)
- Docker

## Instructions

### Docker

```shell
docker build --tag mailmonkey --file Dockerfile .
docker run -p 8000:8000 mailmonkey
```

### Production

```shell
export APP_ENVIRONMENT=production
cargo build --release
./target/release/mailmonkey
```

### Development

```shell
export APP_ENVIRONMENT=local
cargo run
```

## Other Information

### Prepare sqlx-data.json for offline mode
```shell
cargo sqlx prepare -- --bin mailmonkey
```
