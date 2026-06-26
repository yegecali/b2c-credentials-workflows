# B2C Credentials Workflows Repository

This repository acts as the central orchestrator, providing reusable workflows that compile atomic tasks into higher-level workflows.

## Reusable Workflows

### 1. Credentials Orchestrator (`.github/workflows/orchestrate-credentials.yml`)
Coordinates the end-to-end credential creation and rotation flow, integrating input validations, secret management (Vault), API connectivity retries, custom B2C Actions invocations, error handling, and job summary reports.

* **Callable path**: `yegecali/b2c-credentials-workflows/.github/workflows/orchestrate-credentials.yml@main`

### Features Implemented:
* **Contract Exposure**: Well-defined inputs, secrets, and outputs.
* **Input Validation**: Verifies that the parameters are correct before invoking heavy actions.
* **Vault Integration**: Connects to key management engines to fetch security credentials.
* **Transient API Retries**: Resiliently attempts Graph API connection using a shell-based exponential/linear backoff system.
* **Error Handling**: Uses `continue-on-error` alongside state metrics to intercept errors and write to failure registers.
* **Job Summaries**: Generates rich Markdown tables directly into `$GITHUB_STEP_SUMMARY` for visibility in the GitHub Actions run screen.
