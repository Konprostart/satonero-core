# Satonero fork of `mostro-core`

This repository is the Satonero-owned fork of the MIT-licensed
[`mostro-core`](https://github.com/MostroP2P/mostro-core) crate (upstream authors:
Francisco Calderón / the Mostro project).

## Why this fork exists

The Satonero daemon depends on `mostro-core` as its protocol/data-model library
(orders, messages, transport, reputation, db traits, …). Upstream ships the crate
on crates.io under the `mostro-core` name. To remove the MostroP2P-controlled
crates.io runtime dependency, the crate is maintained here under the `Konprostart`
organization and redirected via Cargo's `[patch.crates-io]`.

## Compatibility contract

- Crate name is **unchanged**: `mostro-core`.
- Version is **unchanged**: `0.17.3` (satisfies the daemon's `^0.17.3` requirement).
- Public API and wire format are **unchanged** (identical source tree).
- Upstream MIT license is preserved verbatim in `LICENSE`.

The `Cargo.toml` `repository` field was updated and this `FORK.md` was added.

The upstream `.github/workflows/` directory was **removed**. Those are MostroP2P
CI/automation files, not library source: `rust.yml` contains a tag-triggered
`cargo publish` to crates.io (under the MostroP2P-owned `mostro-core` name) and a
GitHub Release, and `sync-readme-badges.yml` syncs a crates.io dynamic badge. A
Satonero-owned fork must not run that automation. The crate is **never** published
to crates.io (the `mostro-core` name is MostroP2P-owned; the daemon consumes it
via `[patch.crates-io]`).

## Attribution

Original project: https://github.com/MostroP2P/mostro-core (MIT).
