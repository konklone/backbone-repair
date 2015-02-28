Code for [backbone.repair](https://backbone.repair).

## Deploying

With `s3cmd`:

```bash
s3cmd put -P --recursive index.html assets s3://backbone-repair
```

## HTTPS

Generate the HTTPS certificate with [SSLMate](https://sslmate.com).

Install the `aws` CLI tool with:

```bash
pip install awscli
```

Authorize the `aws` tool to your account with:

```bash
aws configure
```

Then upload the key and certificate material to AWS:

```
aws iam upload-server-certificate \
  --server-certificate-name backbone-repair \
  --certificate-body file://./backbone.repair.crt \
  --private-key file://./backbone.repair.key \
  --certificate-chain file://./backbone.repair.chain.crt \
  --path /cloudfront/backbone-repair/
```

## Maintainers

[Eric Mill](https://twitter.com/konklone) and [Kevin Webb](https://twitter.com/kvnweb).
