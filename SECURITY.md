# Security Policy

The Resonate Examples organization hosts demonstration code, not production infrastructure. Security issues here typically fall into two buckets:

- **Issues in the example code itself** — vulnerable patterns demonstrated, unsafe defaults, dependencies with known CVEs that the example actually exposes.
- **Issues in the Resonate SDKs or server** that surface through an example. These belong upstream.

## Reporting a vulnerability

**Do not file a public issue for a security vulnerability.** Public disclosure before a fix lands puts users at risk.

Use one of these private channels:

1. **For SDK or server vulnerabilities** (the most impactful path), report against the upstream repo using GitHub's private vulnerability reporting:
   - [`resonatehq/resonate`](https://github.com/resonatehq/resonate/security/advisories/new) (server)
   - [`resonatehq/resonate-sdk-ts`](https://github.com/resonatehq/resonate-sdk-ts/security/advisories/new)
   - [`resonatehq/resonate-sdk-py`](https://github.com/resonatehq/resonate-sdk-py/security/advisories/new)
   - [`resonatehq/resonate-sdk-rs`](https://github.com/resonatehq/resonate-sdk-rs/security/advisories/new)
2. **For an example-specific vulnerability** (vulnerable pattern, unsafe default in the example code itself), DM a Resonate maintainer on the [Resonate Discord](https://resonatehq.io/discord) — the team is small and a DM reaches us within a day. Include the repo, the file, and the issue.
3. **If you're unsure where it belongs**, route via Discord and we'll triage.

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

We follow **coordinated disclosure with a 90-day default window** from acknowledgment. If you need a different window — shorter for active exploitation, longer for complex remediation — say so in the original report and we'll agree on a schedule. We'll request an extension in writing if a fix needs more time; we won't sit on a report past 90 days without coordinating with you.

Once a fix has shipped, we publish a security advisory on the affected repo. If you want credit for the report, tell us in the original message — we default to anonymous attribution unless asked.

## What's out of scope

- **Vulnerabilities in dependencies** that the example consumes but doesn't actively expose. We run Dependabot on every example repo; transitive CVEs are auto-tracked and bumped on the next release. File a security report only if the example's usage pattern actively exposes the dep's vulnerable surface.
- **Issues in private forks** of these examples. We can only address what's in the public org.
- **Theoretical vulnerabilities** without a concrete exploit path. Useful, but not security issues until someone shows the impact.
