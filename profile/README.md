![resonatehq-examples org readme banner](./assets/resonatehq-examples-org-readme-banner.png)

# Resonate Example Applications

**Examples of production-ready patterns demonstrating distributed async await with durable execution.**

This organization hosts battle-tested patterns for building reliable distributed systems without the complexity. From human-in-the-loop workflows to saga patterns, from serverless long-running functions to Kafka workers - see how Resonate solves real problems with clean code.

## Why Resonate?

**Write sequential code. Get distributed systems guarantees.**

Resonate handles the hard parts automatically:
- ✅ **Crash recovery** - Resume exactly where you left off
- ✅ **Retries & timeouts** - Automatic with exponential backoff
- ✅ **Idempotency** - Safe to retry operations
- ✅ **Concurrency** - Structured fork-join patterns
- ✅ **Observability** - Built-in tracing and metrics

**No more:**
- ❌ Writing retry logic everywhere
- ❌ Managing distributed state machines
- ❌ Debugging non-deterministic failures
- ❌ Building custom orchestration layers

## Quick Start

### 1. Install the Resonate Server & CLI

```bash
brew install resonatehq/tap/resonate
```

### 2. Install the Resonate SDK

**TypeScript:**
```bash
npm install @resonatehq/sdk
```

**Python:**
```bash
pip install resonate-sdk
```

### 3. Write your first Resonate Function

A countdown as a loop. Simple, but the function can run for minutes, hours, or days, despite restarts.

**TypeScript (countdown.ts):**

```typescript
import { Resonate, type Context } from '@resonatehq/sdk';

function* countdown(context: Context, count: number, delay: number) {
  for (let i = count; i > 0; i--) {
    // Run a function, persist its result
    yield* context.run((context: Context) => console.log(`Countdown: ${i}`));
    // Sleep
    yield* context.sleep(delay * 1000);
  }
  console.log("Done!");
}

// Instantiate Resonate
const resonate = new Resonate({ url: 'http://localhost:8001' });
// Register the function
resonate.register(countdown);
```

[Working example →](https://github.com/resonatehq-examples/example-quickstart-ts)

**Python (countdown.py):**

```python
from resonate import Resonate, Context
from threading import Event

def countdown(ctx: Context, count: int, delay: int):
    for i in range(count, 0, -1):
        # Run a function, persist its result
        yield ctx.run(ntfy, i)
        # Sleep
        yield ctx.sleep(delay)
    print("Done!")


def ntfy(_: Context, i: int):
    print(f"Countdown: {i}")


# Instantiate Resonate
resonate = Resonate.remote()
# Register the function
resonate.register(countdown)
resonate.start()  # Start Resonate threads
Event().wait()  # Keep the main thread alive
```

[Working example →](https://github.com/resonatehq-examples/example-quickstart-py)

### 4. Start the server

```bash
resonate dev
```

### 5. Start the worker

**TypeScript:**
```bash
npx ts-node countdown.ts
```

**Python:**
```bash
python countdown.py
```

### 6. Activate the function

Activate the function with execution ID `countdown.1`:

```bash
resonate invoke countdown.1 --func countdown --arg 5 --arg 60
```

### 7. Result

You will see the countdown in the terminal:

```
Countdown: 5
Countdown: 4
Countdown: 3
Countdown: 2
Countdown: 1
Done!
```

## Featured Examples

### 🎯 Start Here

Perfect for learning the basics:

| Example | Description | Language |
|---------|-------------|----------|
| [**Human in the Loop**](https://github.com/resonatehq-examples/example-human-in-the-loop-ts) | Workflows that pause for approval | TypeScript |
| [**Money Transfer**](https://github.com/resonatehq-examples/example-money-transfer-application-ts) | Saga pattern for distributed transactions | TypeScript |
| [**Hello World**](https://github.com/resonatehq-examples/example-hello-world-ts) | Your first durable function | TypeScript, Python |

### 🚀 Production Patterns

Real-world architectures:

#### Saga Pattern & Distributed Transactions
- [**Money Transfer**](https://github.com/resonatehq-examples/example-money-transfer-application-ts) - Atomic operations across accounts (TypeScript)

#### Human-in-the-Loop Workflows
- [**Approval Workflows**](https://github.com/resonatehq-examples/example-human-in-the-loop-ts) - Workflows that suspend awaiting human input (TypeScript)
- [**Website Summarization Agent**](https://github.com/resonatehq-examples/example-website-summarization-agent-ts) - AI summarization with approval (TypeScript, Python)

#### Message Queue Integration
- [**Kafka Worker**](https://github.com/resonatehq-examples/example-kafka-worker-py) - Concurrent message processing without head-of-line blocking (Python)
- [**Load Balancing**](https://github.com/resonatehq-examples/example-load-balancing-ts) - Distribute work across worker pools (TypeScript, Python)

#### Serverless & FaaS
Run long-duration workflows on serverless platforms that have execution time limits:

- [**Deep Research Agent (Cloudflare)**](https://github.com/resonatehq-examples/example-openai-deep-research-agent-cloudflare-ts) - Recursive AI research (TypeScript)
- [**Deep Research Agent (GCP)**](https://github.com/resonatehq-examples/example-openai-deep-research-agent-gcp-ts) - Recursive AI research (TypeScript)
- [**Countdown (Supabase)**](https://github.com/resonatehq-examples/example-countdown-supabase-ts) - Durable timers on Edge Functions (TypeScript)
- [**TigerBeetle + Resonate**](https://github.com/resonatehq-examples/example-tigerbeetle-account-creation-ts) - Durable financial transactions (TypeScript)

#### AI & LLM Workflows
- [**AI Travel Assistant**](https://github.com/resonatehq-examples/example-ai-travel-assistant-py) - Multi-step AI agent with tool use (Python)
- [**Bluesky Scraper**](https://github.com/resonatehq-examples/example-bluesky-scraper-ts) - Durable social media ingestion (TypeScript)

#### HTTP APIs
- [**Async HTTP API**](https://github.com/resonatehq-examples/example-async-http-api-ts) - Submit job, poll for results (TypeScript, Python)
- [**Async RPC**](https://github.com/resonatehq-examples/example-async-rpc-py) - Cross-process communication (Python)

### 🔧 Infrastructure Examples

Deploy and operate Resonate:

- [**Countdown Examples**](https://github.com/resonatehq-examples/?q=example-countdown&type=all) - Durable sleep across platforms (TypeScript, Python)
- [**Token Auth**](https://github.com/resonatehq-examples/example-token-auth-ts) - Authentication patterns (TypeScript)

## Browse by Language

<table>
<tr>
<td width="50%">

### TypeScript

- 🎯 [Quickstart](https://github.com/resonatehq-examples/example-quickstart-ts)
- 💰 [Money Transfer (Saga)](https://github.com/resonatehq-examples/example-money-transfer-application-ts)
- ✋ [Human-in-the-Loop](https://github.com/resonatehq-examples/example-human-in-the-loop-ts)
- 🌐 [Async HTTP API](https://github.com/resonatehq-examples/example-async-http-api-ts)
- ☁️ [Serverless Examples](https://github.com/resonatehq-examples/?q=cloudflare+OR+gcp+OR+supabase&type=all)
- 🔐 [Token Auth](https://github.com/resonatehq-examples/example-token-auth-ts)

[See all TypeScript examples →](https://github.com/resonatehq-examples?q=ts&type=all)

</td>
<td width="50%">

### Python

- 🎯 [Quickstart](https://github.com/resonatehq-examples/example-quickstart-py)
- 🤖 [AI Travel Assistant](https://github.com/resonatehq-examples/example-ai-travel-assistant-py)
- 📊 [Kafka Worker](https://github.com/resonatehq-examples/example-kafka-worker-py)
- 🌐 [Async HTTP API](https://github.com/resonatehq-examples/example-async-http-api-py)
- ⚖️ [Load Balancing](https://github.com/resonatehq-examples/example-load-balancing-py)
- 🔄 [Async RPC](https://github.com/resonatehq-examples/example-async-rpc-py)

[See all Python examples →](https://github.com/resonatehq-examples?q=py&type=all)

</td>
</tr>
</table>

## Key Concepts Demonstrated

| Concept | What It Solves | Example |
|---------|---------------|---------|
| **Durable Execution** | Functions survive crashes and resume | [Hello World](https://github.com/resonatehq-examples/example-hello-world-ts) |
| **Saga Pattern** | Distributed transactions without 2PC | [Money Transfer](https://github.com/resonatehq-examples/example-money-transfer-application-ts) |
| **Human-in-the-Loop** | Workflows pause for external input | [Approval Workflows](https://github.com/resonatehq-examples/example-human-in-the-loop-ts) |
| **Structured Concurrency** | Fork-join parallelism made safe | [Load Balancing](https://github.com/resonatehq-examples/example-load-balancing-ts) |
| **Durable Sleep** | Long waits without holding resources | [Countdown](https://github.com/resonatehq-examples/example-countdown-ts) |
| **Idempotency** | Safe retries without side effects | [Money Transfer](https://github.com/resonatehq-examples/example-money-transfer-application-ts) |
| **RPC** | Cross-process durable calls | [Async RPC](https://github.com/resonatehq-examples/example-async-rpc-py) |

## From Development to Deployment

Code that works locally works in production - no changes needed. Just point your SDK at a remote Resonate server:

```typescript
// Local development (embedded server)
const resonate = new Resonate();

// Production (remote server)
const resonate = new Resonate({
  url: 'https://resonate.example.com',
  auth: { username: 'user', password: 'pass' }
});
```

Deploy Resonate server anywhere:
- Docker / Kubernetes
- Cloud VMs (AWS, GCP, Azure)
- Self-hosted on-prem

## Resources

### Documentation
- 📘 [Official Docs](https://docs.resonatehq.io)
- 🧠 [Distributed Async Await Explained](https://distributed-async-await.io)
- 📖 [SEAA (Systems Engineering for Agentic Applications)](https://systems-engineering-for-agentic-applications.resonatehq.io/)

### SDKs
- [TypeScript SDK](https://github.com/resonatehq/resonate-sdk-ts) - npm install @resonatehq/sdk
- [Python SDK](https://github.com/resonatehq/resonate-sdk-py) - pip install resonate-sdk

### Community
- 💬 [Discord](https://discord.gg/R4har9w6) - Ask questions, share patterns
- 🐛 [Issues](https://github.com/resonatehq-examples/example-quickstart-ts/issues) - Report bugs or request examples
- 🌐 [Website](https://resonatehq.io) - Learn more about Resonate

## Contributing

We welcome contributions! To add a new example:

1. **Fork** the example template or similar existing example
2. **Build** your example following existing patterns
3. **Document** with clear README explaining the use case
4. **Test** that it works from a fresh clone
5. **Submit** a PR with description of what problem it solves

See [contribution guidelines](https://github.com/resonatehq/.github/blob/main/CONTRIBUTING.md) for details.

## Example Quality Standards

All examples in this organization follow these standards:
- ✅ **Runnable** - Clear installation and run instructions
- ✅ **Documented** - Explains what, why, and how
- ✅ **Tested** - Works from a fresh git clone
- ✅ **Modern** - Uses latest SDK versions
- ✅ **Clean** - Well-structured, readable code

## License

Most examples are MIT licensed. Check individual repositories for specifics.

---

**Built with Resonate** - Making distributed systems simple since 2023.

[Get Started](https://docs.resonatehq.io/quickstart) • [Join Discord](https://discord.gg/R4har9w6) • [Learn More](https://resonatehq.io)
