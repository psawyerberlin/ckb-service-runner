# Contributing

Thanks for your interest. This project is meant to be built by a group of CKB
developers and node operators, not one person.

## How work flows

1. **Ideas and design questions → [Discussions](../../discussions).**
   Nothing becomes an issue until it is roughly agreed there.
2. **Agreed, concrete work → Issues.** Use the templates. Look for
   `good first issue` and `help wanted`.
3. **Code and docs → Pull requests** against `main`, linked to an issue.

## Pull requests

- One topic per PR; keep it small.
- Describe what changed and how you tested it (testnet first).
- Rust: `cargo fmt`, `cargo clippy -- -D warnings` and `cargo test` must pass.
- At least one maintainer review before merge.
- Commit messages: `type(scope): summary`, e.g. `feat(ranking): add ASN lookup`.

## Security-sensitive areas

Anything touching the sandbox, host calls, key handling or service storage
needs two reviews. Never report vulnerabilities in public issues — see
[SECURITY.md](SECURITY.md).

## Becoming a maintainer

Regular, careful contributors are invited to become maintainers. The project
explicitly wants more maintainers.

## Licence

By contributing you agree that your contributions are licensed under the MIT licence.
