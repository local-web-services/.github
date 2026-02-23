# local-web-services

> **[Full documentation → local-web-services.github.io/www](https://local-web-services.github.io/www)**

Run your AWS infrastructure locally — zero code changes required.

`ldk` reads your CDK or Terraform project and spins up real, local AWS service emulators on demand. Write tests against DynamoDB, SQS, S3, SNS, Step Functions, SSM, and Secrets Manager without touching a real AWS account.

---

## Repositories

### Core

| Repo | Description |
|------|-------------|
| [local-web-services](https://github.com/local-web-services/local-web-services) | The `ldk` CLI — synthesises CDK/Terraform stacks and runs local AWS emulators |

### SDKs

| Language | SDK repo | Package |
|----------|----------|---------|
| Python | [local-web-services-python-sdk](https://github.com/local-web-services/local-web-services-python-sdk) | [`local-web-services-python-sdk`](https://pypi.org/project/local-web-services-python-sdk/) on PyPI |
| TypeScript | [local-web-services-typescript-sdk](https://github.com/local-web-services/local-web-services-typescript-sdk) | [`local-web-services-typescript-sdk`](https://www.npmjs.com/package/local-web-services-typescript-sdk) on npm |
| JavaScript | [local-web-services-javascript-sdk](https://github.com/local-web-services/local-web-services-javascript-sdk) | [`local-web-services-javascript-sdk`](https://www.npmjs.com/package/local-web-services-javascript-sdk) on npm |

### Example projects

| Repo | Description |
|------|-------------|
| [local-web-services-sdk-python-example-project](https://github.com/local-web-services/local-web-services-sdk-python-example-project) | Python example: pytest fixtures with DynamoDB, SQS, and Step Functions |
| [local-web-services-sdk-typescript-example-project](https://github.com/local-web-services/local-web-services-sdk-typescript-example-project) | TypeScript example: Jest tests with DynamoDB, SQS, and Step Functions |
| [local-web-services-sdk-javascript-example-project](https://github.com/local-web-services/local-web-services-sdk-javascript-example-project) | JavaScript example: Jest tests with DynamoDB, SQS, and Step Functions |

---

For full documentation, guides, and examples visit **[local-web-services.github.io/www](https://local-web-services.github.io/www)**.
