---

# 🧠 GitHub Copilot Metadata Tags – Real Examples per Tag

> A tag-by-tag reference for GitHub Copilot Agent Mode, each with a realistic, production-grade example.

---

### `@copilot-mode`

```bash
# @copilot-mode: agent
"""
Scan Terraform files for misconfigured AWS S3 buckets and generate a compliance report.
"""
```

---

### `@mcp-tools`

```bash
# @mcp-tools: github-code,terminal
"""
Check last 5 shell commands used to deploy the staging environment via CLI.
"""
```

---

### `@model`

```bash
# @model: claude-3.7-sonnet
"""
Summarize security issues in the backend codebase using Claude’s audit capabilities.
"""
```

---

### `@analysis-scope`

```bash
# @analysis-scope: infrastructure-as-code
"""
Detect performance bottlenecks in Terraform autoscaling configuration for EC2 instances.
"""
```

---

### `@analysis-type`

```bash
# @analysis-type: security
"""
Scan source code and Dockerfiles for CVEs, hardcoded credentials, and insecure defaults.
"""
```

---

### `@analysis-depth`

```bash
# @analysis-depth: inter-procedural
"""
Track flow of JWT tokens from generation to database writes across services.
"""
```

---

### `@optimization`

```bash
# @optimization: true
"""
Optimize nginx.conf to improve response time under high load.
"""
```

---

### `@optimize-for`

```bash
# @optimize-for: security,size,speed
"""
Generate Dockerfile with multi-stage build and minimal footprint for a Go app.
"""
```

---

### `@memory-optimization`

```bash
# @memory-optimization: off-heap-caching
"""
Refactor Java service to use off-heap cache for large immutable lookup tables.
"""
```

---

### `@gc-strategy`

```bash
# @gc-strategy: G1GC
"""
Tune JVM GC for better throughput in a real-time analytics pipeline.
"""
```

---

### `@target`

```bash
# @target: entire_project
"""
Identify deprecated APIs across all modules and suggest migration paths.
"""
```

---

### `@target-platforms`

```bash
# @target-platforms: github-actions,gitlab-ci
"""
Generate parallelizable test matrix workflows for all supported platforms.
"""
```

---

### `@environment`

```bash
# @environment: kubernetes,aws
"""
Deploy Prometheus, Grafana, and Alertmanager stack to EKS.
"""
```

---

### `@requirement`

```bash
# @requirement: canary-deployment
"""
Implement traffic-splitting rollout strategy using Istio.
"""
```

---

### `@security-requirements`

```bash
# @security-requirements: SAST,DAST,secrets-scan
"""
Configure automated security scanning for all PRs and scheduled pipelines.
"""
```

---

### `@iac-tool`

```bash
# @iac-tool: terraform
"""
Validate IAM policy configurations for least privilege enforcement.
"""
```

---

### `@cloud-provider`

```bash
# @cloud-provider: gcp
"""
Optimize Cloud Run service configuration to reduce cold-start latency.
"""
```

---

### `@security-standards`

```bash
# @security-standards: CIS,NIST
"""
Check cloud infra against CIS benchmarks for S3 and IAM.
"""
```

---

### `@security-tools`

```bash
# @security-tools: snyk,trivy,codeql
"""
Inject image scanning into Docker build stage and run CodeQL on push.
"""
```

---

### `@pipeline-integration`

```bash
# @pipeline-integration: github-actions
"""
Trigger CodeQL analysis after successful test stage.
"""
```

---

### `@automation-tools`

```bash
# @automation-tools: prometheus-alertmanager
"""
Generate Alertmanager routes for CPU/memory usage above thresholds.
"""
```

---

### `@gitops-stack`

```bash
# @gitops-stack: argocd
"""
Generate ArgoCD Application YAMLs for multi-namespace rollout.
"""
```

---

### `@stack`

```bash
# @stack: prometheus,grafana,loki,tempo
"""
Configure observability stack with unified dashboards and logs correlation.
"""
```

---

### `@language`

```bash
# @language: python,bash
"""
Lint all Python scripts and Bash shell files for style violations.
"""
```

---

### `@base-images`

```bash
# @base-images: node:18-alpine,golang:1.22-alpine
"""
Use slim base images for minimal attack surface in container builds.
"""
```

---

### `@error-context`

```bash
# @error-context: k8s,terraform,cicd
"""
Analyze common failure patterns in Kubernetes job restarts and CI timeouts.
"""
```

---

### `@error-type`

```bash
# @error-type: container-crashloop
"""
Identify resource overcommitment leading to CrashLoopBackOff in pods.
"""
```

---

### `@retry-strategy`

```bash
# @retry-strategy: exponential-backoff(max=3)
"""
Retry flaky integration tests in CI with backoff.
"""
```

---

### `@timeout`

```bash
# @timeout: 600s
"""
Set global timeout for image build and signing process.
"""
```

---

### `@concurrency`

```bash
# @concurrency: 5
"""
Limit simultaneous database migrations to 5 to avoid lock contention.
"""
```

---

### `@output-format`

```bash
# @output-format: json
"""
Export scan results in JSON for ingestion by SonarCloud dashboard.
"""
```

---

### `@doc-style`

```bash
# @doc-style: Doxygen
"""
Document exported APIs with types, usage, and warnings.
"""
```

---

### `@detail-level`

```bash
# @detail-level: maintainer
"""
Include architectural justifications and cross-module notes.
"""
```

---

### `@env-file`

```bash
# @env-file: .copilot/env.prod
"""
Inject environment variables securely into container builds.
"""
```

---

### `@secret-provider`

```bash
# @secret-provider: hashicorp-vault(path=secret/cicd)
"""
Fetch credentials for Docker registry login during deploy.
"""
```

---

### `@config-version`

```bash
# @config-version: 2.3.1
"""
Lock metadata schema version for reproducibility.
"""
```

---

### `@feature-flags`

```bash
# @feature-flags: canary-deploy=enabled
"""
Toggle Canary release mechanism on or off per environment.
"""
```

---

### `@depends-on`

```bash
# @depends-on: postgres:14.3
"""
Ensure service B starts after database A is up.
"""
```

---

### `@service-binding`

```bash
# @service-binding: redis->cache
"""
Wire Redis into application as a caching backend.
"""
```

---

### `@dependency-resolution`

```bash
# @dependency-resolution: strict-semver
"""
Avoid auto-upgrades of breaking changes in semantic versioning.
"""
```

---

### `@metrics-endpoint`

```bash
# @metrics-endpoint: prometheus:9090
"""
Configure Prometheus scrape for custom metrics exporter.
"""
```

---

### `@log-level`

```bash
# @log-level: debug
"""
Enable verbose logs for test environments only.
"""
```

---

### `@alert-channels`

```bash
# @alert-channels: slack#devops-alerts,pagerduty
"""
Send critical alerts to Slack + PagerDuty teams.
"""
```

---

### `@alert-thresholds`

```bash
# @alert-thresholds: cpu>80%,memory>90%
"""
Define when alerts should be triggered for pod resources.
"""
```

---

### `@tech-preview`

```bash
# @tech-preview: wasm-runtime
"""
Enable WASM runtime support in edge gateways.
"""
```

---

### `@beta-features`

```bash
# @beta-features: ai-assisted-debugging
"""
Enable experimental AI-powered debugging hints in CI.
"""
```

---

### `@debug-mode`

```bash
# @debug-mode: port=2345
"""
Start debugger listener on dev containers.
"""
```

---

### `@trace-sampling`

```bash
# @trace-sampling: 10%
"""
Only sample 10% of traces for performance analysis.
"""
```

---

### `@rbac-rules`

```yaml
@rbac-rules:
  - verbs: [get, list]
    resources: [pods]
"""
Grant readonly access to deployment pods for support team.
"""
```

---

### `@approval-workflow`

```bash
# @approval-workflow: 2-maintainers
"""
Block merge until 2 code owners approve changes.
"""
```

---

### `@resource-quotas`

```yaml
@resource-quotas:
  cpu: 2000m
  memory: 4Gi
"""
Prevent noisy neighbors in a multi-tenant cluster.
"""
```

---

### `@scale-policy`

```bash
# @scale-policy: horizontal(max=10)
"""
Use HPA for scaling frontend pods under load.
"""
```

---

### `@compliance-framework`

```bash
# @compliance-framework: soc2-type2
"""
Ensure data access logs, RBAC and retention meet audit requirements.
"""
```

---

### `@audit-trail`

```bash
# @audit-trail: aws-cloudtrail
"""
Enable CloudTrail for IAM, EC2 and VPC changes.
"""
```

---

### `@data-classification`

```bash
# @data-classification: pii
"""
Enable encryption, anonymization and logging redactions.
"""
```

---

### `@encryption-at-rest`

```bash
# @encryption-at-rest: aes-256
"""
Use AWS KMS + AES-256 for EBS volume encryption.
"""
```

---

### `@extension-point`

```bash
# @extension-point: custom-linter
"""
Plug into the PR creation event to run custom linting logic.
"""
```

---

### `@plugin-apis`

```bash
# @plugin-apis: kubernetes-client@8.0
"""
Use k8s client to query pod labels and conditions.
"""
```

---

### `@package-registry`

```bash
# @package-registry: github-npm-registry
"""
Use private GitHub NPM registry for internal packages.
"""
```

---
