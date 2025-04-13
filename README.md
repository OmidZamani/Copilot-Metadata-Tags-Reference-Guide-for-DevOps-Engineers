# copilot-metadata-reference

**Reference Guide for DevOps Engineers**

> Forget trial-and-error. These tags give you control over Copilot’s reasoning, optimization, and deployment behavior.

---

## 1. Introduction

This document is an outcome of necessity.

After running into a series of practical issues while using GitHub Copilot in DevOps workflows—particularly when dealing with infrastructure code, pipelines, and cloud-native deployments—I realized that Copilot, while powerful, lacked systematic guidance when operating in its Agent Mode. The lack of metadata reference, consistent tagging, and example-driven usage made it hard to scale its functionality across environments.

So, this repository is not just a reference—it's a field manual.
It’s for engineers who don’t just copy/paste prompts into Copilot but aim to **engineer with Copilot**.

## 2. Purpose

This guide outlines the metadata tags Copilot can understand or respond to (explicitly or implicitly), allowing engineers to:

- Structure prompts programmatically
- Inject operational metadata to influence Copilot behavior
- Define reproducible usage patterns for automation, compliance, debugging, and more

It’s designed for **DevOps engineers**, **SREs**, and **platform engineers** working with IaC, CI/CD, container orchestration, cloud infra, observability, and secure deployment pipelines.

## 3. Usage Format

Each tag is presented as follows:
- A short, human-readable **description**
- A **syntax block** with canonical usage
- A **realistic use case** from production-style workflows

---

## 4. Tag Reference

### Core Mode Tags

#### @copilot-mode
Sets the operational context for Copilot (e.g., `agent`, `chat`, `code`).
```bash
@copilot-mode: agent
```
Use this to tell Copilot you're expecting multi-step reasoning.

#### @mcp-tools
Declares the tools involved in the model context protocol.
```bash
@mcp-tools: github-code,terminal
```
Used when Copilot should pull insights from both code and CLI output.

#### @model
Specifies the LLM model.
```bash
@model: claude-3.7-sonnet
```
Ideal for multi-agent setups where model preference matters.

---

### Analysis Tags

#### @analysis-scope
Defines what systems or areas Copilot should analyze.
```bash
@analysis-scope: terraform,kubernetes,ci-cd
```

#### @analysis-type
Tells Copilot what kind of analysis to perform.
```bash
@analysis-type: security,performance,anti-patterns
```

#### @analysis-depth
Specifies how deep Copilot should analyze dependencies or configs.
```bash
@analysis-depth: inter-procedural
```

---

### Optimization Tags

#### @optimization
Enables optimization logic.
```bash
@optimization: true
```

#### @optimize-for
Defines optimization targets.
```bash
@optimize-for: size,performance,security
```

#### @memory-optimization
Hints at memory use strategies.
```bash
@memory-optimization: off-heap-caching
```

#### @gc-strategy
Tells Copilot which GC tuning to apply (Java/Scala).
```bash
@gc-strategy: G1GC
```

---

### Target and Platform Tags

#### @target
Sets the scope of the prompt.
```bash
@target: entire_project
```

#### @target-platforms
Declares where output is to be deployed or integrated.
```bash
@target-platforms: github-actions,gitlab-ci
```

#### @environment
Defines environments like Kubernetes, AWS, Azure, etc.
```bash
@environment: kubernetes,aws
```

---

### Requirement Tags

#### @requirement
Defines high-level system or business requirements.
```bash
@requirement: security-scans,blue-green-deployments
```

#### @security-requirements
Lists specific security checks or constraints.
```bash
@security-requirements: SAST,DAST,secrets-scan
```

---

### Technology Stack Tags

#### @iac-tool
Specifies IaC tooling.
```bash
@iac-tool: terraform
```

#### @cloud-provider
Declares which cloud vendor(s) are being used.
```bash
@cloud-provider: aws,gcp
```

#### @security-standards
Declares compliance benchmarks.
```bash
@security-standards: CIS,NIST,HIPAA
```

#### @security-tools
Lists the tools that Copilot should simulate or integrate.
```bash
@security-tools: snyk,trivy,codeql
```

#### @pipeline-integration
Declares the CI/CD system.
```bash
@pipeline-integration: github-actions,gitlab-ci
```

#### @automation-tools
List orchestration or alerting tooling.
```bash
@automation-tools: kubernetes-operators,prometheus-alertmanager
```

#### @gitops-stack
Declares GitOps toolchains.
```bash
@gitops-stack: argocd,flux
```

#### @stack
Broad toolset in use.
```bash
@stack: prometheus,grafana,loki
```

#### @language
Which programming languages are present.
```bash
@language: go,bash,python
```

#### @base-images
List of Docker base images to work with.
```bash
@base-images: node:18-alpine,golang:1.22-alpine
```

---

### Error Handling Tags

#### @error-context
Set the domain Copilot should consider.
```bash
@error-context: k8s,terraform,cicd
```

#### @error-type
Highlight specific error categories.
```bash
@error-type: container-crashloop,pipeline-timeout
```

#### @retry-strategy
Control retry logic.
```bash
@retry-strategy: exponential-backoff(max=3)
```

---

### Output Format Tags

#### @output-format
What format Copilot should use for responses.
```bash
@output-format: json
```

#### @doc-style
What style to use in comments or docs.
```bash
@doc-style: Doxygen
```

#### @detail-level
Control verbosity.
```bash
@detail-level: maintainer
```

---

### Flow Control Tags

#### @timeout
Set time limits for operations.
```bash
@timeout: 600s
```

#### @concurrency
Control number of parallel jobs.
```bash
@concurrency: 5
```

---

### Environment and Configuration Tags

#### @env-file
Declare environment files.
```bash
@env-file: .copilot/env.prod
```

#### @secret-provider
Where to fetch secrets from.
```bash
@secret-provider: hashicorp-vault(path=secret/cicd)
```

#### @config-version
Used for internal config schemas.
```bash
@config-version: 2.3.1
```

#### @feature-flags
Enable or disable feature toggles.
```bash
@feature-flags: canary-deploy=enabled
```

---

### Dependency Management Tags

#### @depends-on
List of direct dependencies.
```bash
@depends-on: postgres:14.3
```

#### @service-binding
Relationship mapping between services.
```bash
@service-binding: redis->cache
```

#### @dependency-resolution
How to treat version mismatches.
```bash
@dependency-resolution: strict-semver
```

---

### Monitoring and Alerting Tags

#### @metrics-endpoint
Where metrics can be scraped.
```bash
@metrics-endpoint: prometheus:9090
```

#### @log-level
Set runtime logging level.
```bash
@log-level: debug
```

#### @alert-channels
Notification destinations.
```bash
@alert-channels: slack#devops-alerts,pagerduty
```

#### @alert-thresholds
Conditions to trigger alerts.
```bash
@alert-thresholds: cpu>80%,memory>90%
```

---

### Preview and Beta Tags

#### @tech-preview
Enable experimental features.
```bash
@tech-preview: wasm-runtime
```

#### @beta-features
Beta modules in use.
```bash
@beta-features: ai-assisted-debugging
```

#### @debug-mode
Enable debug ports or breakpoints.
```bash
@debug-mode: port=2345
```

#### @trace-sampling
Control tracing volume.
```bash
@trace-sampling: 10%
```

---

### Organizational Integration Tags

#### @rbac-rules
Kubernetes-style RBAC rules.
```bash
@rbac-rules: - verbs: [get, list] resources: [pods]
```

#### @approval-workflow
Declare required sign-offs.
```bash
@approval-workflow: 2-maintainers
```

---

### Resource Management Tags

#### @resource-quotas
Limit resource usage.
```bash
@resource-quotas: cpu: 2000m, memory: 4Gi
```

#### @scale-policy
Control autoscaling.
```bash
@scale-policy: horizontal(max=10)
```

---

### Security and Compliance Tags

#### @compliance-framework
Which standard to audit against.
```bash
@compliance-framework: soc2-type2
```

#### @audit-trail
Logging provider.
```bash
@audit-trail: aws-cloudtrail
```

#### @data-classification
Label sensitivity level.
```bash
@data-classification: pii
```

#### @encryption-at-rest
Specify encryption algorithm.
```bash
@encryption-at-rest: aes-256
```

---

### Platform Development Tags

#### @extension-point
Expose plugin hooks.
```bash
@extension-point: custom-linter
```

#### @plugin-apis
Declare API contracts.
```bash
@plugin-apis: kubernetes-client@8.0
```

#### @package-registry
Source of dependencies.
```bash
@package-registry: github-npm-registry
```

---

## 5. Why This Exists

Copilot is evolving fast. But its interface to power users—DevOps folks automating environments at scale—is often undocumented, inconsistent, or buried inside feature rollouts.

This repo serves two goals:
- Help others avoid the same friction I encountered
- Push GitHub Copilot (and its successors) toward more usable, declarative, predictable interactions

## 6. Contributions Welcome

This isn’t a solo act. If you’ve:
- Discovered edge-case tags
- Reverse-engineered Copilot behavior
- Used tags in LangGraph, VSCode, or Bash workflows

...then PRs, issues, and improvements are welcome. RFC-style.

## 7. License

MIT. Use freely. Give credit if it helps.
If you turn this into something bigger—like a VSCode extension or shell utility—just let us know.

## 8. Suggested Repository Name

```
copilot-metadata-reference
```

Concise. Discoverable. Honest.

