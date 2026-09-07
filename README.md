# Azure Launchpad

Terraform and Bicep landing-zone foundations for small and midsized organizations.

[![License: Apache 2.0](https://img.shields.io/badge/license-Apache%202.0-blue?style=flat)](LICENSE)

[Quick Start](#quick-start) | [Configuration](#configuration) | [Validation](#validation) | [Guide](GUIDE.md)

## Overview

Deploy hub-and-spoke foundations using baseline, firewall, VPN, or combined scenarios.
The [documentation site](https://azurelaunchpad.com/) includes a configuration wizard.
Local tests cover configuration generation and mocked infrastructure plans; target-environment validation is still required.

## Prerequisites

- Terraform 1.9 or later for Terraform deployments; Azure CLI and Bicep for Bicep deployments.
- Access to the intended subscriptions and deployment/state permissions described in the guide.
- Node.js 22 for the configuration-generator tests.

## Quick Start

```text
git clone https://github.com/travishankins/azure-launchpad.git
cd azure-launchpad
node --test site/public/scripts/wizard.test.js
```

Generate your configuration with the [wizard](https://azurelaunchpad.com/wizard/), then follow the [deployment guide](GUIDE.md).

## Configuration

Select the IaC language, scenario, subscription mode, region, and state storage before previewing changes.
The guide covers local tools, Cloud Shell, Codespaces, and GitHub Actions configuration.

## Validation

Run the wizard tests above and the Terraform tests documented in the guide.
Use preflight, review the saved plan or what-if result, and run post-deployment verification.
A passing local test is not proof of regional capacity, policy compatibility, or deployment permissions.

## Operations

Site publishing and infrastructure deployment are separate workflows.
Preserve state backups and a known-good site artifact; infrastructure rollback requires a reviewed forward change, not an automatic destroy.

## Security and Limitations

Use scoped deployment identities and protect state storage.
Scenario costs are estimates: validate current prices, region, currency, SKUs, and traffic assumptions.
Review the documented non-goals before adopting the foundation.

## Documentation

- [Project guide](GUIDE.md): scenarios, deployment lifecycle, tests, and CI/CD.
- [Documentation site](https://azurelaunchpad.com/): detailed setup and configuration reference.

## Contributing

Read [CONTRIBUTING.md](CONTRIBUTING.md), [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md), and [SECURITY.md](SECURITY.md) before submitting changes or reporting security issues.

## License

[Apache License 2.0](LICENSE).
