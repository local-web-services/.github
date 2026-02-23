# local-web-services

Run your AWS infrastructure locally — zero code changes required.

**local-web-services** (`ldk`) reads your CDK or Terraform project and spins up real, local AWS service emulators on demand. Write tests against DynamoDB, SQS, S3, SNS, Step Functions, SSM, and Secrets Manager without touching a real AWS account.

---

## How it works

```
ldk dev --project-dir ./my-cdk-project
```

`ldk` synthesises your CDK or Terraform stack, creates all declared resources in local emulators, and exposes each service on a deterministic port. Your existing application code connects without modification.

---

## SDKs

| Language | Package | Install |
|----------|---------|---------|
| Python | [`lws-testing`](https://pypi.org/project/lws-testing/) | `pip install lws-testing` |
| TypeScript | [`local-web-services-typescript-sdk`](https://www.npmjs.com/package/local-web-services-typescript-sdk) | `npm install local-web-services-typescript-sdk` |
| JavaScript | [`local-web-services-javascript-sdk`](https://www.npmjs.com/package/local-web-services-javascript-sdk) | `npm install local-web-services-javascript-sdk` |

---

## Quick example (Python)

```python
from lws_testing import LwsSession

def test_order_flow():
    with LwsSession(
        tables=[{"name": "Orders", "partition_key": "id"}],
        queues=["OrderQueue"],
    ) as session:
        # Your production code runs unchanged — env vars are patched automatically
        handler(event, context)

        table = session.dynamodb("Orders")
        items = table.scan()
        assert len(items) == 1
```

## Quick example (TypeScript / JavaScript)

```ts
import { LwsSession } from 'local-web-services-typescript-sdk';

let session: LwsSession;

beforeAll(async () => {
  session = await LwsSession.create({
    tables: [{ name: 'Orders', partitionKey: 'id' }],
    queues: ['OrderQueue'],
  });
});

afterAll(() => session.close());
beforeEach(() => session.reset());

test('places an order', async () => {
  await handler(event, context);

  const table = session.dynamodb('Orders');
  await table.assertItemCount(1);
});
```

---

## Supported services

| Service | AWS SDK env var set automatically |
|---------|----------------------------------|
| DynamoDB | `AWS_ENDPOINT_URL_DYNAMODB` |
| SQS | `AWS_ENDPOINT_URL_SQS` |
| S3 | `AWS_ENDPOINT_URL_S3` |
| SNS | `AWS_ENDPOINT_URL_SNS` |
| Step Functions | `AWS_ENDPOINT_URL_STATES` |
| SSM Parameter Store | `AWS_ENDPOINT_URL_SSM` |
| Secrets Manager | `AWS_ENDPOINT_URL_SECRETS_MANAGER` |

---

## Links

- [Website](https://local-web-services.github.io/www)
- [Core tool](https://github.com/local-web-services/local-web-services)
- [Python SDK](https://github.com/local-web-services/local-web-services-python-sdk)
- [TypeScript SDK](https://github.com/local-web-services/local-web-services-typescript-sdk)
- [JavaScript SDK](https://github.com/local-web-services/local-web-services-javascript-sdk)
