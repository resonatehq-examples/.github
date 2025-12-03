![resonatehq-examples org readme banner](./assets/resonatehq-examples-org-readme-banner.png)

# Resonate example applications

This Github organization is home to open-source example applications showcasing _how to use_ Resonate to solve for common distributed system challenges.

## From development to deployment

Many, if not most, of these examples showcase code that does not need to change when deployed.
The only exception perhap being Resonate Server connection details.

## Showcased examples

While you can browse for examples on the [repositories](https://github.com/orgs/resonatehq-examples/repositories) page, here are some of the more popular example apps categorized by capability.

### Long-running on serverless

These examples showcase long-running functions that can suspend and resume on serverless infra.
Note: Currently, only the TypeScript SDK supports serverless shims.

**Deep research agent**

- [Cloudflare Function OpenAI deep research agent | **TypeScript**](https://github.com/resonatehq-examples/example-openai-deep-research-agent-cloudflare-ts)
- [Google Cloud Function OpenAI deep research agent | **TypeScript**](https://github.com/resonatehq-examples/example-openai-deep-research-agent-gcp-ts)

**Countdown notification**

[Cloudflare Function countdown notification | **TypeScript**](https://github.com/resonatehq-examples/example-countdown-cloudflare-ts)
[Google Function countdown notification | **TypeScript**](https://github.com/resonatehq-examples/example-countdown-gcp-ts)

### Human-in-the-loop cases

These examples showcase functions that suspend, awaiting on input from a human.

**Website summarization agent**

- [Website summarization agent | **Python**](https://github.com/resonatehq-examples/example-website-summarization-agent-py)
- [Website summarization agent | **TypeScript** ](https://github.com/resonatehq-examples/example-website-summarization-agent-ts)
