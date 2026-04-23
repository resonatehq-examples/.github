<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/readme-banner-dark.png">
  <source media="(prefers-color-scheme: light)" srcset="./assets/readme-banner-light.png">
  <img alt="Resonate Examples — production-shaped patterns. Pick one and run it." src="./assets/readme-banner-dark.png">
</picture>

# Resonate Examples

**Resonate is durable execution that agents build, deploy, and operate.** You write normal functions with `yield`; Resonate persists each step so they survive crashes, restarts, and long waits — minutes, hours, or weeks. No state-machine DSL, no orchestration glue.

Every repo in this org demonstrates one pattern end-to-end. Pin the SDK, clone, run.

[Documentation](https://docs.resonatehq.io) · [Distributed async/await](https://distributed-async-await.io)

## Start here

New to Resonate? Begin with one of these.

- [Quickstart (TypeScript)](https://github.com/resonatehq-examples/example-quickstart-ts) — a countdown that survives restarts
- [Quickstart (Python)](https://github.com/resonatehq-examples/example-quickstart-py) — same shape, Python idioms
- [Hello World (Rust)](https://github.com/resonatehq-examples/example-hello-world-rs) — the first Rust SDK example

## Featured examples

A curated set, organized by what each one demonstrates.

### Patterns

- [Saga + compensation](https://github.com/resonatehq-examples/example-saga-booking-ts) — flight + hotel + car; failure triggers the compensation chain
- [Fan-out / fan-in](https://github.com/resonatehq-examples/example-fan-out-fan-in-ts) — parallel notification channels with per-channel retry
- [Distributed mutex](https://github.com/resonatehq-examples/example-distributed-mutex-ts) — a serialized lock in ~15 lines, no signal API

### Integrations

- [Next.js (App Router)](https://github.com/resonatehq-examples/example-nextjs-integration-ts) — Server Actions trigger durable workflows; status polling
- [AWS Lambda](https://github.com/resonatehq-examples/example-aws-lambda-ts) — Lambda as a stateless trigger; breaks the timeout ceiling
- [Cloudflare Workers](https://github.com/resonatehq-examples/example-countdown-cloudflare-ts) — durable sleep across edge invocations

### Agents

- [Templated agent](https://github.com/resonatehq-examples/templated-agent-ts) — extensible agent template (Crawl / Walk / Run)
- [Multi-agent orchestration](https://github.com/resonatehq-examples/example-multi-agent-orchestration-ts) — researcher → writer → reviewer with durable handoffs
- [Deep research agent](https://github.com/resonatehq-examples/example-openai-deep-research-agent-ts) — recursive AI research powered by OpenAI

### Human-in-the-loop

- [Approval workflow](https://github.com/resonatehq-examples/example-human-in-the-loop-ts) — a function that suspends pending human input
- [Kubernetes node drain](https://github.com/resonatehq-examples/example-node-drain-orchestrator-ts) — durable orchestration with operator confirmation

## Browse all examples

- [TypeScript](https://github.com/orgs/resonatehq-examples/repositories?q=ts&type=all) — bulk of the catalog
- [Python](https://github.com/orgs/resonatehq-examples/repositories?q=py&type=all) — async/await with `yield ctx`
- [Rust](https://github.com/orgs/resonatehq-examples/repositories?q=rs&type=all) — early examples; SDK is v0.1.x

## Community

- Discord: https://resonatehq.io/discord
- X: https://x.com/resonatehqio
- LinkedIn: https://linkedin.com/company/resonatehq
- YouTube: https://youtube.com/@resonatehq
- Journal: https://journal.resonatehq.io

## License

All examples in this organization are licensed under [Apache-2.0](./LICENSE). Each repo carries its own `LICENSE` file.

## Contributing

Want to add an example? Fork the example closest to the pattern you have in mind, follow its structure, and open a PR. Each example should run from a fresh clone, pin its SDK version, and demonstrate one concept clearly. To propose a new example or report a broken one, open an issue on [`.github`](https://github.com/resonatehq-examples/.github/issues).
