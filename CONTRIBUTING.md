# Contributing to Resonate Examples

Thanks for considering an addition. Each repo in this org demonstrates **one pattern, end-to-end** — runnable from a fresh clone, with a clear "this is what to look for" outcome. Contributions land cleanest when they fit that mold.

## Adding a new example

1. **Find the pattern.** A new example earns its repo when it shows a Resonate-distinctive way of solving a real problem — saga, fan-out/fan-in, durable sleep, HITL, multi-agent handoff, and so on. If your idea overlaps with an existing example, propose an enhancement to that repo instead of a new one.
2. **Open an issue first.** Use the [propose-example template](https://github.com/resonatehq-examples/.github/issues/new/choose). Describe the pattern, the language, and what the example would show that the existing catalog doesn't. We'll respond with a thumbs-up, scope adjustments, or "this lives in `<existing repo>` already."
3. **Use the closest existing example as a structural reference.** Clone it locally to study the layout — `README.md`, `LICENSE`, pinned SDK in the manifest, the run flow. Don't fork; we'll create the new repo with you.
4. **We create the empty repo.** Once your proposal is approved, we'll create the new repo at `resonatehq-examples/<your-example-name>` and grant you push access. Push your initial commit to a branch, open a PR against `main`, and we'll review.
5. **Iterate to merge.** Most examples land in 1–3 review rounds. Common asks: tighten the README, pin the SDK version exactly, remove dependencies that don't earn their weight, add a "What to look for" section.

## Quality bar

Every example in this org follows these standards:

- **Runnable from a fresh clone** — no environment-specific assumptions, no missing dependencies, no broken setup.
- **Pinned SDK version** — exact version in `package.json` / `pyproject.toml` / `Cargo.toml`. Prose claims about which version match the pin.
- **One pattern, clearly demonstrated** — not a kitchen-sink demo. The reader should walk away knowing one Resonate concept better.
- **README sections** — H1 + one-paragraph description, "What this demonstrates" (2–4 bullets), a minimal code block showing the primary function, "Prerequisites" (Node/Python/Rust + SDK + server), "Setup" / "Run it", "What to look for" (the durability moment), "Next steps" (links).
- **Apache-2.0 licensed** — matches the org default. Include a `LICENSE` file at repo root.
- **No named competitors** — describe what the pattern solves, not what other tools do wrong. Connector-style repos (e.g. `resonate-connect-temporal`) are the only exception; ask first.

## Reporting broken examples

Use the [report-broken-example template](https://github.com/resonatehq-examples/.github/issues/new/choose). Include the repo, the failing command, the exact error output, and your environment (OS, Node/Python/Rust version, SDK version). We respond fastest to issues that include a reproducer.

## Where to discuss

- **Quick questions:** [Resonate Discord](https://resonatehq.io/discord) — `#examples` channel.
- **Design discussions:** issue threads on the repo where the change would land.
- **Security issues:** see [SECURITY.md](./SECURITY.md) — do not file public issues.

## Code of conduct

This community follows the [Resonate Code of Conduct](./CODE_OF_CONDUCT.md). By contributing, you agree to its terms.
