---

# 🧠 GitHub Copilot Metadata Tags Reference  
_A Comprehensive Guide for `ask`, `edit`, and `agent` Modes_

> This document provides a canonical reference for all currently known metadata tags used with GitHub Copilot across **Agent Mode**, **Chat/Ask**, **Edit Mode**, **Copilot CLI**, and **Copilot for Docs**. It includes examples, mode-specific notes, and LLM model recommendations.

---

## ✅ Core Tags

### `@copilot-mode`
- **Description:** Sets the operational mode.
- **Modes Supported:** `ask`, `edit`, `agent`
- **Example:**
  ```bash
  # @copilot-mode: agent
  ```

---

### `@model`
- **Description:** Chooses the LLM to process the prompt.
- **Modes Supported:** All
- **Example:**
  ```bash
  # @model: gpt-4o
  ```

- **Model Notes:**
  | Model         | Strengths | Ideal Modes |
  |---------------|-----------|-------------|
  | `gpt-4o`      | Fast, smart, multi-modal | all |
  | `claude-3.7`  | Structured reasoning, compliance docs | `agent` |
  | `gemini-1.5`  | File/document structure, DevDocs | `agent`, `ask` |
  | `codex`       | Classic code completion | `edit`, CLI |

---

## 🔍 Analysis Tags

### `@analysis-scope`
- **Description:** Limits what part of the project is being analyzed.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @analysis-scope: infrastructure-as-code,ci-cd
  ```

---

### `@analysis-type`
- **Description:** What kind of analysis is expected.
- **Modes Supported:** `agent`, `ask`
- **Example:**
  ```bash
  # @analysis-type: security,performance,anti-patterns
  ```

---

### `@analysis-depth`
- **Description:** Defines how deep the code inspection should go.
- **Modes Supported:** `agent`, `edit`
- **Example:**
  ```bash
  # @analysis-depth: inter-procedural
  ```

---

## 🚀 Optimization Tags

### `@optimize-for`
- **Description:** Define your optimization goals.
- **Modes Supported:** `agent`, `edit`
- **Example:**
  ```bash
  # @optimize-for: security,size,speed
  ```

---

### `@optimization`
- **Description:** Enables optimization mode.
- **Modes Supported:** `edit`, `agent`
- **Example:**
  ```bash
  # @optimization: true
  ```

---

### `@memory-optimization`
- **Description:** Suggests memory tuning strategies.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @memory-optimization: off-heap-caching
  ```

---

### `@gc-strategy`
- **Description:** Hints to apply garbage collection strategy (for JVM-based systems).
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @gc-strategy: G1GC
  ```

---

## 🧱 Infrastructure & Platform Tags

### `@target`
- **Description:** Target element (file, function, project).
- **Modes Supported:** `edit`, `agent`
- **Example:**
  ```bash
  # @target: entire_project
  ```

---

### `@target-platforms`
- **Description:** Specifies CI/CD targets.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @target-platforms: github-actions,gitlab-ci
  ```

---

### `@environment`
- **Description:** Deployment environment.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @environment: kubernetes,aws
  ```

---

### `@iac-tool`
- **Description:** Specifies infrastructure-as-code tool.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @iac-tool: terraform
  ```

---

## 🔐 Security & Compliance Tags

### `@security-requirements`
- **Description:** Lists required security layers.
- **Modes Supported:** `agent`, `edit`
- **Example:**
  ```bash
  # @security-requirements: SAST,DAST,secrets-scan
  ```

---

### `@security-tools`
- **Description:** Lists which scanners to use.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @security-tools: snyk,trivy,codeql
  ```

---

### `@security-standards`
- **Description:** Define compliance standards.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @security-standards: CIS,NIST,HIPAA
  ```

---

### `@compliance-framework`
- **Description:** Organizational compliance frameworks.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @compliance-framework: soc2-type2
  ```

---

## 🧪 Error Diagnostics Tags

### `@error-context`
- **Description:** Adds context for error logs.
- **Modes Supported:** `agent`, `chat`
- **Example:**
  ```bash
  # @error-context: k8s,terraform,cicd
  ```

---

### `@error-type`
- **Description:** Helps Copilot narrow down problems.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @error-type: container-crashloop,pipeline-timeout
  ```

---

### `@retry-strategy`
- **Description:** How to retry failed operations.
- **Modes Supported:** `agent`, `edit`
- **Example:**
  ```bash
  # @retry-strategy: exponential-backoff(max=3)
  ```

---

## 📤 Output Control Tags

### `@output-format`
- **Description:** Output type for results.
- **Modes Supported:** All
- **Example:**
  ```bash
  # @output-format: markdown
  ```

---

### `@doc-style`
- **Description:** Documentation formatting convention.
- **Modes Supported:** `edit`, `agent`
- **Example:**
  ```bash
  # @doc-style: Doxygen
  ```

---

### `@detail-level`
- **Description:** How detailed output should be.
- **Modes Supported:** All
- **Example:**
  ```bash
  # @detail-level: maintainer
  ```

---

## ⚙️ Flow Control & Execution

### `@timeout`
- **Description:** Max allowed task time.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @timeout: 600s
  ```

---

### `@concurrency`
- **Description:** Max simultaneous executions.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @concurrency: 5
  ```

---

## 📁 Environment & Secrets

### `@env-file`
- **Description:** Environment variable file.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @env-file: .copilot/env.prod
  ```

---

### `@secret-provider`
- **Description:** Source for secrets.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @secret-provider: hashicorp-vault(path=secret/cicd)
  ```

---

## 🔧 Dependency Management

### `@depends-on`
- **Description:** Service dependencies.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @depends-on: postgres:14.3
  ```

---

### `@service-binding`
- **Description:** Maps services to roles.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @service-binding: redis->cache
  ```

---

### `@dependency-resolution`
- **Description:** How to resolve library versions.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @dependency-resolution: strict-semver
  ```

---

## 📡 Monitoring & Alerts

### `@metrics-endpoint`
- **Description:** Prometheus or other metrics endpoint.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @metrics-endpoint: prometheus:9090
  ```

---

### `@log-level`
- **Description:** Log verbosity.
- **Modes Supported:** `agent`, `edit`
- **Example:**
  ```bash
  # @log-level: debug
  ```

---

### `@alert-channels`
- **Description:** Where to send alerts.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @alert-channels: slack#devops-alerts,pagerduty
  ```

---

### `@alert-thresholds`
- **Description:** Conditions for triggering alerts.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @alert-thresholds: cpu>80%,memory>90%
  ```

---

## 🧪 Experimental Features

### `@beta-features`
- **Description:** Activates beta flags.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @beta-features: ai-assisted-debugging
  ```

---

### `@tech-preview`
- **Description:** Enables tech previews.
- **Modes Supported:** `agent`, `edit`
- **Example:**
  ```bash
  # @tech-preview: wasm-runtime
  ```

---

### `@debug-mode`
- **Description:** Enable debugging support.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @debug-mode: port=2345
  ```

---

### `@trace-sampling`
- **Description:** For observability (tracing).
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @trace-sampling: 10%
  ```

---

## 🧩 Platform Extension & Plugin Tags

### `@extension-point`
- **Description:** Defines custom extensibility.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @extension-point: custom-linter
  ```

---

### `@plugin-apis`
- **Description:** Available plugin API versions.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @plugin-apis: kubernetes-client@8.0
  ```

---

### `@package-registry`
- **Description:** Package repository config.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @package-registry: github-npm-registry
  ```

---

## 🛡️ Access Control & Org Policies

### `@rbac-rules`
- **Description:** Role-based access controls.
- **Modes Supported:** `agent`
- **Example:**
  ```yaml
  # @rbac-rules:
  #   - verbs: [get, list]
  #     resources: [pods]
  ```

---

### `@approval-workflow`
- **Description:** Requires approval step.
- **Modes Supported:** `agent`
- **Example:**
  ```bash
  # @approval-workflow: 2-maintainers
  ```

---

## 🧮 Final Tips

- Use **`@copilot-mode: agent`** for autonomous multi-step jobs
- Use **`Claude 3.7`** or **`GPT-4o`** for production-grade analysis
- Combine tags for layered control:  
  ✅ Example:
  ```bash
  # @copilot-mode: agent
  # @model: claude-3.7
  # @optimize-for: security,size
  # @environment: aws,kubernetes
  ```

---
