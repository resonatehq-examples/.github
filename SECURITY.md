# Security Policy

The Resonate Examples organization hosts demonstration code, not production infrastructure. Security issues here typically fall into two buckets:

- **Issues in the example code itself** — vulnerable patterns demonstrated, unsafe defaults, dependencies with known CVEs.
- **Issues in the Resonate SDKs or server** that surface through an example. These belong in the relevant SDK/server repo, not here.

## Reporting a vulnerability

**Do not file a public issue for a security vulnerability.** Public disclosure before a fix lands puts users at risk.

Use one of these private channels:

1. **GitHub private vulnerability reporting** (preferred). On the affected repo: `Security` tab → `Report a vulnerability`. We get a private notification immediately.
2. **Discord DM to a maintainer.** [Resonate Discord](https://resonatehq.io/discord) — DM any member with the `@core-team` role.
3. **For SDK or server vulnerabilities**, report against the upstream repo (`resonatehq/resonate-sdk-ts`, `resonatehq/resonate-sdk-py`, `resonatehq/resonate-sdk-rs`, `resonatehq/resonate`) rather than the example repo.

## What to include

- **Affected repo and file.** A specific path beats "the saga example."
- **Reproducer.** Minimal steps that demonstrate the issue.
- **Impact.** What can an attacker do? Read data, execute code, deny service, escalate privileges?
- **Suggested fix** if you have one.

## Response timeline

- **Acknowledgment:** within 2 business days.
- **Triage decision** (accept, decline, route upstream): within 7 days of acknowledgment.
- **Fix or mitigation** for accepted reports: timeline depends on severity. Critical issues get priority; non-critical issues land in the next normal release cycle of the affected repo.

## Disclosure

Once a fix has shipped, we publish a security advisory on the affected repo. If you want credit for the report, tell us in the original message — we default to anonymous attribution unless asked.

## What's out of scope

- **Vulnerabilities in dependencies** that the example consumes but doesn't expose (e.g. a transitive npm dep). Report these to the dependency's maintainers; we'll bump the version when the upstream fix lands.
- **Issues in private forks** of these examples. We can only address what's in the public org.
- **Theoretical vulnerabilities** without a concrete exploit path. Useful, but not security issues until someone shows the impact.
