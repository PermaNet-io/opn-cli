# AGENTS.md

Guidance for the PermaNet-maintained `opn-cli` Python project.

## Required shared rules

@RULES.md

## Repository purpose

`opnsense_cli/` implements a Click-based CLI for OPNsense APIs.
`acceptance_tests/` covers behavior against a configured appliance, while unit
and packaging configuration lives at the repository root.

## Working rules

- Preserve compatibility with existing command names, configuration precedence,
  environment variables, and output formats.
- Never commit OPNsense API keys, secrets, configuration files, exported
  certificates, or appliance data.
- Keep TLS verification enabled by default. Do not weaken certificate handling
  to make tests pass.
- Treat generated API and command code consistently with the repository's
  generator; update generator inputs and outputs together.
- Format and lint Python with the repository's Ruff configuration and run the
  focused unit tests for changed commands.
- Run acceptance tests only when an authorized disposable or explicitly scoped
  appliance is available.
- Preserve upstream attribution and licensing in this public repository.
- Use Beads (`bd`) for durable work tracking and GitHub pull requests against
  `main`.
