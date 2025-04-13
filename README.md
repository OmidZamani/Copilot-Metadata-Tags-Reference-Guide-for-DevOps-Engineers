---

# `copilot-metadata-reference`  
**Advanced GitHub Copilot Metadata Tags**  
*A field guide for DevOps engineers, SREs, and infra nerds.*

---

## 🧠 @copilot-mode

Controls the operational context Copilot should behave in.

```bash
@copilot-mode: advanced
```

**Example:**

```dockerfile
# @copilot-mode: advanced
# @optimize-for: security,size,speed

"""
Generate a production-ready Dockerfile for a NestJS/PostgreSQL app that:
1. Uses multi-stage build with BuildKit
2. Runs as non-root user
3. Includes healthchecks with curl
4. Minimizes final image size (under 250MB)
5. Scans for vulnerabilities during build
6. Handles SIGTERM properly
7. Sets resource limits

Base images:
- Build: node:18.16.0-bullseye-slim
- Runtime: debian:bookworm-slim
"""
```

---

## ⚙️ Execution Flow Control

### `@retry-strategy`

Defines how Copilot should retry failed steps.

```bash
@retry-strategy: exponential-backoff(max=3)
```

**Example:**

```bash
# @retry-strategy: exponential-backoff(max=3)
# Useful for flaky network or registry timeouts in CI.
```

---

### `@timeout`

Specifies max duration for any task.

```bash
@timeout: 600s
```

**Example:**

```bash
# @timeout: 600s
# Prevent long-running integration tests from hanging the job.
```

---

### `@concurrency`

Limits number of concurrent Copilot tasks.

```bash
@concurrency: 5
```

**Example:**

```yaml
# @concurrency: 5
# Run up to 5 jobs in parallel during matrix builds.
```

---

## 🌍 Environment Variables and Secrets

### `@env-file`

Path to environment variable file.

```bash
@env-file: .copilot/env.prod
```

**Example:**

```bash
# @env-file: .copilot/env.prod
# Load runtime credentials or feature flags from versioned env file.
```

---

### `@secret-provider`

Define external vault or secrets backend.

```bash
@secret-provider: hashicorp-vault(path=secret/cicd)
```

**Example:**

```bash
# @secret-provider: hashicorp-vault(path=secret/cicd)
# Mount secrets like DB_PASSWORD into build context securely.
```

---

## 🔗 Dependency and Service Mapping

### `@depends-on`

Explicitly list service dependencies.

```bash
@depends-on: postgres:14.3
```

**Example:**

```yaml
# @depends-on: postgres:14.3
# Ensures database is available before app boots.
```

---

### `@service-binding`

Logical binding between service components.

```bash
@service-binding: redis->cache
```

**Example:**

```yaml
# @service-binding: redis->cache
# Maps redis service to application config key "cache".
```

---

## 📈 Monitoring and Alerts

### `@metrics-endpoint`

Where to send metrics.

```bash
@metrics-endpoint: prometheus:9090
```

**Example:**

```bash
# @metrics-endpoint: prometheus:9090
# Use for tracking CPU/Memory spikes in long-running builds.
```

---

### `@log-level`

Set verbosity of logs.

```bash
@log-level: debug
```

**Example:**

```bash
# @log-level: debug
# Enable verbose output during troubleshooting.
```

---

### `@alert-channels`

Where alerts should be sent.

```bash
@alert-channels: slack#devops-alerts, pagerduty
```

**Example:**

```bash
# @alert-channels: slack#devops-alerts, pagerduty
# Push crash or timeout notifications to your incident system.
```

---

### `@alert-thresholds`

When to raise alarms.

```bash
@alert-thresholds: cpu>80%, memory>90%
```

**Example:**

```bash
# @alert-thresholds: cpu>80%, memory>90%
# Define autoscaler triggers or alertmanager rules.
```

---

## 🧪 Beta and Experimental

### `@tech-preview`

Enable alpha-stage capabilities.

```bash
@tech-preview: wasm-runtime
```

**Example:**

```bash
# @tech-preview: wasm-runtime
# Try deploying to WASI-based serverless infra.
```

---

### `@beta-features`

Enable early-access tooling.

```bash
@beta-features: ai-assisted-debugging
```

**Example:**

```bash
# @beta-features: ai-assisted-debugging
# Let Copilot suggest root causes and fix patches before you even ask.
```

---

### `@debug-mode`

Enable runtime debugger.

```bash
@debug-mode: port=2345
```

**Example:**

```bash
# @debug-mode: port=2345
# Attach remote debugger for step-through breakpoints in test containers.
```

---

### `@trace-sampling`

Configure distributed tracing.

```bash
@trace-sampling: 10%
```

**Example:**

```bash
# @trace-sampling: 10%
# Capture sampling traces for performance regressions.
```

---

## 📦 Platform and Config Management

### `@rbac-rules`

Fine-grained access control.

```yaml
@rbac-rules:
  - verbs: [get, list]
    resources: [pods]
```

**Example:**

```yaml
# @rbac-rules:
#   - verbs: [get, list]
#     resources: [pods]
# Secure your agent’s actions using Kubernetes RBAC.
```

---

### `@approval-workflow`

Workflow approval logic.

```bash
@approval-workflow: 2-maintainers
```

**Example:**

```bash
# @approval-workflow: 2-maintainers
# Require approval before production rollout.
```

---

### `@config-version`

Specify configuration versioning.

```bash
@config-version: 2.3.1
```

---

### `@feature-flags`

Toggle features via flags.

```bash
@feature-flags: canary-deploy=enabled
```

---

## ✅ Resource & Scaling Strategy

### `@resource-quotas`

Declare resource budgets.

```yaml
@resource-quotas:
  cpu: 2000m
  memory: 4Gi
```

**Example:**

```yaml
# @resource-quotas:
#   cpu: 2000m
#   memory: 4Gi
# Prevent noisy-neighbor scenarios in staging clusters.
```

---

### `@scale-policy`

Horizontal or vertical autoscaling configs.

```bash
@scale-policy: horizontal(max=10)
```

---

### `@memory-optimization`

Memory tuning during runtime.

```bash
@memory-optimization: off-heap-caching
```

---

### `@gc-strategy`

Garbage collection strategy.

```bash
@gc-strategy: G1GC
```

---

## 🔐 Compliance and Security

### `@compliance-framework`

Audit and regulatory control.

```bash
@compliance-framework: soc2-type2
```

---

### `@audit-trail`

Track sensitive actions.

```bash
@audit-trail: aws-cloudtrail
```

---

### `@data-classification`

Tag sensitive data types.

```bash
@data-classification: pii
```

---

### `@encryption-at-rest`

Ensure secure data storage.

```bash
@encryption-at-rest: aes-256
```

---

## 🧩 Extensibility & Dev Platform

### `@extension-point`

Expose plugin hooks.

```bash
@extension-point: custom-linter
```

---

### `@plugin-apis`

Available APIs for plugins.

```bash
@plugin-apis: kubernetes-client@8.0
```

---

### `@package-registry`

Define registry backends.

```bash
@package-registry: github-npm-registry
```

---

### `@dependency-resolution`

Dependency conflict resolution logic.

```bash
@dependency-resolution: strict-semver
```

---

📌 *Last updated: Q2 2025*

> Built from real-world DevOps pain.  
> If this helps you avoid a 3am PagerDuty alert, mission accomplished.

---
