# Contributing to Resonate Examples

Thanks for considering an addition. Each repo in this org demonstrates **one pattern, end-to-end** — runnable from a fresh clone, with a clear "this is what to look for" outcome. Contributions land cleanest when they fit that mold.

## Adding a new example

1. **Find the pattern.** A new example earns its repo when it shows a Resonate-distinctive way of solving a real problem — saga, fan-out/fan-in, durable sleep, HITL, multi-agent handoff, etc. If your idea overlaps with an existing example, propose an enhancement to that repo instead of a new one.
2. **Open an issue first.** Use the [propose-example template](https://github.com/resonatehq-examples/.github/issues/new/choose). Describe the pattern, the language, and what the example would show that the existing catalog doesn't. We'll respond with a thumbs-up, scope adjustments, or "this lives in `<existing repo>` already."
3. **Fork the closest existing example** and use it as a template. Match its structure: `README.md`, `LICENSE` (Apache-2.0), pinned SDK version, runnable from a fresh clone, a "What to observe" section showing the durability moment.
4. **Submit a PR** to the new repo (we'll create the empty repo for you to push to after the issue is approved).

## Quality bar

Every example in this org follows these standards:

- **Runnable from a fresh clone** — no environment-specific assumptions, no missing dependencies, no broken setup.
- **Pinned SDK version** — exact version in `package.json` / `pyproject.toml` / `Cargo.toml`. Prose claims about which version match the pin.
- **One pattern, clearly demonstrated** — not a kitchen-sink demo. The reader should walk away knowing one Resonate concept better.
- **README that conforms to the [README spec](https://github.com/resonatehq/resonate)** — H1, one-paragraph description, "What this demonstrates", code, prerequisites, run steps, what to look for, next steps.
- **Apache-2.0 licensed** — matches the org default.
- **No named competitors** — describe what the pattern solves, not what other tools do wrong. (Connector-style repos are the only exception; ask first.)

## Reporting broken examples

Use the [report-broken-example template](https://github.com/resonatehq-examples/.github/issues/new/choose). Include the repo, the failing command, the error output, and your environment (OS, Node/Python/Rust version, SDK version). We respond fastest to issues that include a reproducer.

## Where to discuss

- **Quick questions:** [Resonate Discord](https://resonatehq.io/discord) — `#examples` channel.
- **Design discussions:** issue threads on the repo where the change would land.
- **Security issues:** see [SECURITY.md](./SECURITY.md) — do not file public issues.

## Code of conduct

This community follows the [Resonate Code of Conduct](./CODE_OF_CONDUCT.md). By contributing, you agree to its terms.
