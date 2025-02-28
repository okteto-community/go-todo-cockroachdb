# Develop with Okteto, Go, and CockroachDB Cloud

This repository demonstrates how to deploy a fully configured development environment that uses Go and **CockroachDB Cloud** with a **Okteto**.

## Prerequisites

Before deploying, ensure you have the following:

- Access to an **Okteto** instance. Sign up for a [30-day self-hosted free trial](https://www.okteto.com) if you don’t have one.
- A **CockroachDB Cloud** account with a running cluster. [Get started for free](https://cockroachlabs.cloud/).
- The **CockroachDB CLI** installed. Follow the [installation guide](https://www.cockroachlabs.com/docs/stable/install-cockroachdb.html).
- The **Okteto CLI** installed. Refer to the [Okteto documentation](https://www.okteto.com/docs/core/getting-started/) for installation steps.

## Configuration

Before deploying, you need to create the following **Okteto environment variables**:

| Variable Name            | Description |
|--------------------------|-------------|
| `COCKROACH_USERNAME`     | Your CockroachDB Cloud username (must have permissions to create databases and manage user privileges). |
| `COCKROACH_PASSWORD`     | Your CockroachDB password. |
| `COCKROACH_CLUSTERID`    | The ID of your CockroachDB cluster (used to download the cluster’s CA certificate). |
| `COCKROACH_HOST` | The hostname of your cluster (eg. `okteto-environments-5313.jxf.gcp-us-west2.cockroachlabs.cloud`)
| `COCKROACH_PORT` | The port of your cluster (eg. `26257`)

To set these variables, follow the guide in the [Okteto Variables documentation](https://www.okteto.com/docs/core/okteto-variables/).

## Deployment

Once your Okteto environment is set up, deploy the project using the following steps:

```bash
git clone https://github.com/okteto-community/go-todo-cockroachdb
cd go-todo-cockroachdb
okteto context use $OKTETO_URL
okteto deploy
```

### Expected Output

If the deployment is successful, you should see output confirming that the CockroachDB cluster and development environment are running.
