# local-web-services

> **[Full documentation → local-web-services.github.io/www](https://local-web-services.github.io/www)**

Stop mocking. Run the real thing, locally.

**local-web-services** lets you replace real AWS infrastructure, custom APIs, and third-party services with local equivalents — no code changes required. Write tests that hit a real DynamoDB table, a real queue, a real Step Functions workflow, or a fake version of your own gRPC/REST/GraphQL API, all running in-process on your machine.

---

## What you can do

**Fake AWS infrastructure**
Drop-in local emulators for DynamoDB, SQS, S3, SNS, Step Functions, SSM Parameter Store, and Secrets Manager. Resources are provisioned from your CDK or Terraform project — no manual setup.

**Fake your own APIs**
Define fake gRPC, REST, or GraphQL APIs that your application calls. Return canned responses, inspect calls, or simulate failures — all from config, no code.

**Simulate chaos**
Inject latency, errors, and partial failures into any service to verify your application handles degraded conditions correctly.

---

## Tools

| Tool | What it does |
|------|-------------|
| [`ldk`](https://github.com/local-web-services/local-web-services) | The core CLI. Reads your CDK or Terraform project, starts local emulators, exposes each service on a deterministic port. |
| `lws` | AWS-style CLI for managing and inspecting your local environment — create tables, publish messages, inspect state, trigger chaos. |

---

## SDKs — use `ldk` in your tests

The SDKs give you a drop-in session object that starts `ldk`, patches AWS SDK environment variables, and tears everything down after your tests.

| Language | Repo | Package |
|----------|------|---------|
| Python | [local-web-services-python-sdk](https://github.com/local-web-services/local-web-services-python-sdk) | [`local-web-services-python-sdk`](https://pypi.org/project/local-web-services-python-sdk/) on PyPI |
| TypeScript | [local-web-services-typescript-sdk](https://github.com/local-web-services/local-web-services-typescript-sdk) | [`local-web-services-typescript-sdk`](https://www.npmjs.com/package/local-web-services-typescript-sdk) on npm |
| JavaScript | [local-web-services-javascript-sdk](https://github.com/local-web-services/local-web-services-javascript-sdk) | [`local-web-services-javascript-sdk`](https://www.npmjs.com/package/local-web-services-javascript-sdk) on npm |

---

## Sample projects

Working examples showing how to use `ldk` and the SDKs in real projects.

| Repo | Stack | What it shows |
|------|-------|--------------|
| [sample-project](https://github.com/local-web-services/sample-project) | CDK | Full CDK app with DynamoDB, SQS, and Step Functions tested locally |
| [sample-project-terraform](https://github.com/local-web-services/sample-project-terraform) | Terraform | Same patterns using Terraform instead of CDK |
| [sdk-python-example-project](https://github.com/local-web-services/local-web-services-sdk-python-example-project) | Python SDK | pytest fixtures reading state machine definitions from Terraform config |
| [sdk-typescript-example-project](https://github.com/local-web-services/local-web-services-sdk-typescript-example-project) | TypeScript SDK | Jest tests with Step Functions discovered from HCL |
| [sdk-javascript-example-project](https://github.com/local-web-services/local-web-services-sdk-javascript-example-project) | JavaScript SDK | Jest tests with Step Functions discovered from HCL |

---

For full documentation, guides, and examples visit **[local-web-services.github.io/www](https://local-web-services.github.io/www)**.
