# Changelog — `armature-redis`

All notable changes to this crate will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this crate adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

Earlier changes are recorded in the workspace [`CHANGELOG.md`](../CHANGELOG.md).

## [Unreleased]

## [0.3.0] - 2026-10-17

### Security

- **Breaking:** `RedisConfig` now has a redacting `Debug` impl (`password` prints as `<redacted>`; `user:pass@` userinfo in `url` and `cluster_nodes` is stripped) and `password` is `#[serde(skip_serializing)]` (it still deserializes). Migration: code that serialized a `RedisConfig` and expected the password back must re-supply it from its secret source.

## [0.2.2] - 2026-09-15

### Changed

- Dependencies bumped to their latest releases: `redis` 1.3 → 1.7, `tokio` 1.52 → 1.53, `tokio` 1.52 → 1.53.
- Migrate to upgraded dependencies.

