---

# GitHub Copilot Metadata Tags Reference  
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







# GitHub Copilot Metadata Tag Prompts for Comprehensive Project Analysis
### Copilot-Powered Container & Pipeline Blueprint Collection

## 1. Dependency Mapping

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: frontend,typescript,react,npm
# @analysis-type: dependencies
# @analysis-depth: inter-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @dependency-resolution: strict-semver

Please analyze all dependencies in my React TypeScript project and provide a comprehensive dependency map. This should include:
1. NPM dependencies (direct and transitive)
2. Internal dependencies between project modules
3. Deprecated or vulnerable dependencies
4. Unnecessary or unused dependencies
5. Recommendations for updating or replacing problematic packages
```

## 2. Call Graph

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: architecture,control-flow
# @analysis-depth: inter-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please create a complete call graph for my React TypeScript project. This graph should show:
1. Calling relationships between functions and methods
2. Control flow between React components
3. Main execution paths in the application
4. Major entry/exit points
5. Call frequencies (if possible)
```

## 3. Data Flow Graph

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: data-flow
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please generate a complete data flow graph for my React project. This graph should show:
1. How data flows throughout the application
2. State flow in React components
3. State management mechanisms (Redux, Context API, etc.)
4. Data input/output to/from APIs
5. Potential data leak points or security issues
```

## 4. Code Navigation and Cross-referencing

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: cross-reference,navigation
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please create a comprehensive code navigation guide for my React TypeScript project. This should include:
1. Cross-reference index of important functions/components
2. Symbol reference map
3. Import/export relationships
4. Component hierarchy and rendering tree
5. Recommendations for improving code organization and navigation
```

## 5. Callers/Callees Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: call-hierarchy
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please perform a detailed callers/callees analysis for my React TypeScript project. This should include:
1. For each significant function/method, list all callers
2. For each significant function/method, list all callees
3. Identify highly-called functions (hotspots)
4. Identify functions with high fan-out (calling many other functions)
5. Recommendations for refactoring complex call relationships
```

## 6. Cyclomatic Complexity Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: quality,complexity
# @analysis-depth: function-level
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @alert-thresholds: complexity>10

Please analyze the cyclomatic complexity of all functions and components in my React TypeScript project. The report should include:
1. Complexity score for each function/component
2. Functions with high complexity (>10)
3. Suggestions for refactoring and simplifying the code
4. Overall project cyclomatic complexity average
5. Complexity trend over time (if possible)
```

## 7. Maintainability Scoring

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: quality,maintainability
# @analysis-depth: project-level
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimize-for: maintainability

Please perform a maintainability analysis of my React TypeScript project. This should include:
1. Overall maintainability score
2. Maintainability metrics for each file/component
3. Identification of least maintainable code
4. Factors affecting maintainability (complexity, coupling, cohesion)
5. Recommendations for improving maintainability
6. Technical debt estimation
```

## 8. Hotspot Identification

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: quality,hotspots
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please identify hotspots in my React TypeScript project. Hotspots include:
1. Files/components with the most changes
2. Files/components with high complexity
3. Dense code with multiple responsibilities
4. Large files with more than 300 lines of code
5. Code with multiple dependencies or bidirectional dependencies
6. Suggestions for improving each hotspot
```

## 9. Reverse Engineering of Architecture

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: entire-project,frontend,typescript,react
# @analysis-type: architecture
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @doc-style: comprehensive

Please reverse engineer the architecture of my React TypeScript project. The output should include:
1. High-level architecture diagram
2. Design patterns used
3. Component hierarchy structure
4. Software layering (UI, business logic, data access, etc.)
5. Communication mechanisms between components
6. State management architecture
7. Recommendations for improving the current architecture
```

## 10. UML Class Extraction

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: architecture,class-diagram
# @analysis-depth: class-level
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @doc-style: UML

Please extract a UML class diagram for my React TypeScript project. This should include:
1. All defined classes and interfaces
2. Relationships between classes (inheritance, composition, aggregation)
3. Key properties and methods
4. React component classes and their relationships
5. Recommendations for improving object-oriented design
```

## 11. Module Extraction

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: entire-project,typescript,react
# @analysis-type: architecture,modules
# @analysis-depth: module-level
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please extract the modular structure of my React TypeScript project. This should include:
1. All main modules and sub-modules
2. Dependencies and relationships between modules
3. Responsibilities of each module
4. Identification of overly coupled modules
5. Recommendations for better modularization and reduced coupling
```

## 12. Architecture Recovery

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: entire-project,typescript,react
# @analysis-type: architecture,recovery
# @analysis-depth: project-level
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please recover the architectural design of my React TypeScript project. This should include:
1. Architectural styles and patterns identified
2. Component model
3. Connector types between components
4. Architectural views (logical, process, deployment)
5. Architectural constraints and principles
6. Deviations from architectural principles
7. Recommendations for architectural improvements
```

## 13. Diagramming

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: entire-project,typescript,react
# @analysis-type: visualization,diagrams
# @analysis-depth: project-level
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please create a comprehensive set of diagrams for my React TypeScript project. These should include:
1. Component hierarchy diagram
2. Data flow diagram
3. State management diagram
4. API interaction diagram
5. Event flow diagram
6. Rendering process diagram
7. Build process diagram
8. Deployment diagram
```

## 14. Static Code Quality Assessment

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: quality,static-analysis
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @alert-thresholds: code-duplications>5%

Please perform a static analysis of code quality for my React TypeScript project. This should include:
1. Adherence to coding standards
2. Code duplication and extractable parts
3. Overall project complexity
4. Code testability
5. Adherence to SOLID principles
6. Recommendations for improving code quality
```

## 15. Code Smell Detection

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: quality,code-smells
# @analysis-depth: function-level
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimize-for: maintainability

Please identify code smells in my React TypeScript project. This should include:
1. Long functions (over 50 lines)
2. Large or sticky classes (God classes)
3. Duplicated code
4. Dependency cycles
5. Dead or unused code
6. Function or variable hardness
7. Broken encapsulation rules
8. Recommendations for fixing each code smell
```

## 16. Clean Code Metrics

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: quality,clean-code
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimize-for: readability,maintainability

Please analyze my React TypeScript project against clean code metrics. This should include:
1. Naming conventions (meaningful, intention-revealing names)
2. Function size and responsibility
3. Comment quality and necessity
4. Code formatting and consistency
5. Error handling patterns
6. DRY principle adherence
7. SOLID principles adherence
8. Recommendations for improving clean code metrics
```

## 17. Change Impact Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: architecture,impact-analysis
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please perform a change impact analysis for my React TypeScript project. This should show:
1. High-risk areas for change (with potentially high impact)
2. Modules/components with the most incoming dependencies
3. Modules/components with the most outgoing dependencies
4. Potential impact of change in each major module
5. Strategies for reducing change risk
```

## 18. Version Control Integration

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: version-control,git
# @analysis-type: repository-analysis
# @analysis-depth: project-level
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please analyze the version control history of my React TypeScript project. This should include:
1. Commit frequency and patterns
2. File change frequency
3. Author contributions and expertise areas
4. Code churn metrics
5. Branch strategy analysis
6. Pull request/merge patterns
7. Recommendations for improving version control practices
```

## 19. Codebase Documentation Generation

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: entire-project,typescript,react
# @analysis-type: documentation
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @doc-style: comprehensive

Please generate comprehensive documentation for my React TypeScript project codebase. This should include:
1. Architectural overview
2. Project structure and explanation of each folder/module
3. API documentation for key components
4. Key workflows with diagrams
5. Redux/state management documentation
6. API access protocols
7. Important library usage patterns
8. Developer guide
```

## 20. Onboarding Assistance for New Developers

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: entire-project,typescript,react
# @analysis-type: documentation,onboarding
# @analysis-depth: project-level
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: comprehensive
# @doc-style: learning-oriented

Please generate an onboarding guide for new developers working on my React TypeScript project. This should include:
1. Introduction to the project structure
2. Development environment setup
3. Architecture and design philosophy
4. Coding practices and rules
5. Development workflow
6. Tool usage guide
7. Codebase learning roadmap
8. Useful learning resources
```

## 21. Polyglot Codebase Support

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: polyglot,typescript,javascript,css,html
# @analysis-type: multi-language
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please analyze my React TypeScript project as a polyglot codebase. This should include:
1. Language distribution and usage patterns
2. Cross-language interactions
3. Technology stack integration points
4. Language-specific quality metrics
5. Language-specific best practices adherence
6. Recommendations for improving multi-language organization
```

## 22. Mixed-Language Dependency Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: polyglot,typescript,javascript,css,html
# @analysis-type: dependencies,multi-language
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please analyze dependencies across different languages in my React TypeScript project. This should include:
1. TypeScript to CSS dependencies
2. JavaScript to HTML dependencies
3. CSS to HTML dependencies
4. Cross-language coupling metrics
5. Mixed-language modules and components
6. Recommendations for improving separation of concerns across languages
```

## 23. Control Flow Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: control-flow
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please perform a control flow analysis for my React TypeScript project. This should include:
1. Control flow graphs for key functions
2. Main execution paths in the application
3. Error handling and exceptions
4. Asynchronous processes and their management
5. Key decision points and conditions
6. Recommended optimizations for control flow
```

## 24. Data Leakage Detection

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: security,data-flow
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @security-requirements: data-protection,privacy

Please detect potential data leakage in my React TypeScript project. This should include:
1. Sensitive data exposed in frontend JavaScript
2. Sensitive information stored in local/session storage
3. User data sent to third-party services
4. Hard-coded API keys or passwords
5. Sensitive information in browser console or logs
6. Recommendations for fixing each data leak
```

## 25. Risky Flow Patterns

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: security,data-flow
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @security-requirements: SAST

Please identify risky flow patterns in my React TypeScript project. This should include:
1. Unsafe code execution (eval, dangerouslySetInnerHTML, etc.)
2. Unsafe use of user input
3. Potential XSS vulnerabilities
4. Insecure authentication or token management
5. Sensitive information leak points
6. Insecure storage of sensitive data
7. Recommendations for securing each risky pattern
```

## 26. Metric Dashboards

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: entire-project,typescript,react
# @analysis-type: metrics
# @analysis-depth: project-level
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @metrics-endpoint: enabled

Please create a metrics dashboard for my React TypeScript project. This should include:
1. Overall codebase health
2. Module and component complexity
3. Code quality (based on static analysis)
4. Test coverage
5. Code smell frequency
6. Estimated technical debt
7. Metric trends over time (if possible)
8. Recommendations for improving each metric
```

## 27. Exportable Graphs

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: entire-project,typescript,react
# @analysis-type: graphs,visualization
# @analysis-depth: project-level
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please generate a set of exportable graphs for my React TypeScript project. This should include:
1. Component dependency graph
2. Data flow graph
3. Complexity heat map
4. UML class diagram
5. System architecture diagram
6. Change impact graph
7. Exportable formats for each graph (dot, graphml, svg, etc.)
```

## 28. Custom Metrics

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: metrics,custom
# @analysis-depth: project-level
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please generate the following custom metrics for my React TypeScript project:
1. Test code to production code ratio
2. Average external dependencies per component
3. Component simplicity index (number of props ÷ number of render states)
4. Average component tree depth
5. Component usage frequency
6. Average hook complexity
7. Unnecessary re-render frequency
8. Component testability index
9. Interpretation of each metric and recommendations for improvement
```

## 29. Custom Queries

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: custom-query
# @analysis-depth: cross-procedural
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert

Please analyze my React TypeScript project with the following custom queries:
1. Find all components that use useEffect with empty dependency arrays
2. Identify instances of prop drilling beyond 3 levels
3. Locate context providers without memoization
4. Find components that don't use React.memo but should
5. Identify places where useMemo or useCallback is missing
6. Locate potential memory leaks in useEffect cleanup
7. Find event handlers not using useCallback
8. List components with excessive props (>7)
```

## 30. Dockerfile Optimization

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,containerization
# @analysis-type: docker-optimization
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @environment: docker
# @optimize-for: size,security,performance

Please analyze and optimize Dockerfiles for my React TypeScript project. This should include:
1. Identification of inefficient Dockerfile patterns
2. Layer optimization recommendations
3. Base image selection guidance
4. Build cache optimization strategies
5. Security best practices
6. Multi-stage build recommendations
7. Production-ready Dockerfile optimizations
8. Development Dockerfile optimizations
```

## 31. Multi-Stage Builds

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,containerization
# @analysis-type: docker-multi-stage
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @environment: docker
# @optimize-for: size,security,performance

Please create optimized multi-stage Docker builds for my React TypeScript project. This should include:
1. Build stage Dockerfile
2. Production stage Dockerfile
3. Testing stage Dockerfile (if applicable)
4. CI/CD-optimized multi-stage build
5. Layer caching strategies
6. Development vs. production considerations
7. Security hardening for each stage
8. Image size optimization techniques
```

## 32. Image Size Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,containerization
# @analysis-type: docker-size
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @environment: docker
# @optimize-for: size

Please analyze and optimize Docker image size for my React TypeScript project. This should include:
1. Baseline image size estimation
2. Identification of large/unnecessary layers
3. Dependency pruning strategies
4. Multi-stage build size optimizations
5. Alpine vs. slim base image analysis
6. npm/yarn package optimization
7. Build artifact size reduction
8. Final image size targets and recommendations
```

## 33. Container Security Inspection

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,containerization,security
# @analysis-type: container-security
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @environment: docker
# @security-requirements: container-hardening
# @security-tools: trivy,dockle

Please perform a container security inspection for my React TypeScript project. This should include:
1. Base image vulnerability analysis
2. Dockerfile security best practices
3. Non-root user configuration
4. Sensitive data exposure checks
5. Unnecessary package/tool removal
6. Attack surface reduction strategies
7. Container runtime security configurations
8. Secrets management recommendations
```

## 34. Docker Compose Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,containerization
# @analysis-type: docker-compose
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @environment: docker-compose
# @optimize-for: development-experience,security

Please analyze and optimize Docker Compose configurations for my React TypeScript project. This should include:
1. Development environment docker-compose.yml
2. Service definitions and networking
3. Volume mounting strategies
4. Environment variable handling
5. Service dependency management
6. Docker Compose best practices
7. Development workflow optimization
8. Hot-reloading configuration
```

## 35. Environment Variable Mapping

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,configuration
# @analysis-type: env-mapping
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @environment: docker,kubernetes
# @security-requirements: secrets-management

Please analyze and map environment variables for my React TypeScript project. This should include:
1. Environment variable inventory
2. Required vs. optional variables
3. Environment-specific variables (dev, test, prod)
4. Default values and fallbacks
5. Sensitive variable identification
6. Environment variable injection methods
7. Configuration validation strategies
8. Documentation for all environment variables
```

## 36. Container Dependency Mapping

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,containerization
# @analysis-type: container-dependencies
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @environment: docker,kubernetes
# @depends-on: microservices

Please map container dependencies for my React TypeScript project. This should include:
1. Service dependency graph
2. API dependencies between containers
3. Shared resources and volumes
4. Network topology
5. Startup order dependencies
6. Health check dependencies
7. Data persistence dependencies
8. Recommendations for dependency management
```

## 37. Secrets Exposure Detection

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,security
# @analysis-type: secrets-detection
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @security-requirements: secrets-scan
# @security-tools: gitleaks,trufflehog

Please detect potential secrets exposure in my React TypeScript project. This should include:
1. Hard-coded API keys or tokens
2. Credentials in configuration files
3. Secrets in environment files
4. Exposed private keys
5. Sensitive data in code comments
6. Historical secrets in version control
7. Secrets in build artifacts
8. Recommendations for secure secrets management
```

## 38. CI/CD Pipeline Inspection

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,ci-cd
# @analysis-type: pipeline-analysis
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @target-platforms: github-actions,gitlab-ci

Please inspect and optimize CI/CD pipelines for my React TypeScript project. This should include:
1. Pipeline structure analysis
2. Build, test, deploy stages
3. Pipeline efficiency optimization
4. Security gate integration
5. Artifact management
6. Environment promotion strategy
7. Rollback mechanisms
8. Pipeline best practices recommendations
```

## 39. GitHub Actions Linting

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,ci-cd
# @analysis-type: github-actions
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @target-platforms: github-actions

Please lint and optimize GitHub Actions workflows for my React TypeScript project. This should include:
1. Workflow syntax validation
2. Job and step optimization
3. Action version pinning
4. Caching strategy implementation
5. Matrix build optimization
6. Security best practices
7. Workflow concurrency settings
8. Self-hosted runner configurations (if applicable)
```

## 40. Build Performance Profiling

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,build
# @analysis-type: performance
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimize-for: build-time,ci-efficiency

Please profile and optimize build performance for my React TypeScript project. This should include:
1. Build time analysis
2. Build step profiling
3. Parallel execution opportunities
4. Cache effectiveness analysis
5. Webpack/bundler optimization
6. CI build performance optimization
7. Development build optimization
8. Production build optimization
```

## 41. Deployment Workflow Validation

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,deployment
# @analysis-type: workflow-validation
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @environment: kubernetes,aws

Please validate and optimize deployment workflows for my React TypeScript project. This should include:
1. Deployment strategy analysis
2. Environment promotion flows
3. Rollback mechanisms
4. Blue/green or canary deployment patterns
5. Deployment security gates
6. Configuration management during deployment
7. Post-deployment verification
8. Recommendations for deployment workflow improvement
```

## 42. Artifact Tracing

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,ci-cd
# @analysis-type: artifact-tracing
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @target-platforms: github-actions,docker

Please trace artifacts through the build and deployment pipeline for my React TypeScript project. This should include:
1. Artifact creation points
2. Artifact storage and management
3. Artifact versioning strategy
4. Artifact promotion between environments
5. Artifact security scanning
6. Artifact retention policies
7. Artifact deployment verification
8. Recommendations for artifact management improvement
```

## 43. Test Coverage Gate Enforcement

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: testing,ci-cd
# @analysis-type: test-coverage
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @target-platforms: github-actions,gitlab-ci

Please analyze and implement test coverage gates for my React TypeScript project. This should include:
1. Current test coverage analysis
2. Coverage threshold recommendations
3. CI/CD integration for coverage gates
4. Component-level coverage requirements
5. Coverage reporting and visualization
6. Strategies for improving test coverage
7. Integration vs. unit test coverage balance
8. Path to achieving target coverage
```

## 44. Infrastructure Drift Detection

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,iac
# @analysis-type: drift-detection
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @environment: kubernetes,aws
# @iac-tool: terraform

Please implement infrastructure drift detection for my React TypeScript project. This should include:
1. Infrastructure as Code baseline
2. Deployment environment comparison
3. Configuration drift detection
4. Drift remediation strategies
5. Automated drift detection in CI/CD
6. Manual vs. automated drift correction
7. Drift notification system
8. Recommendations for preventing infrastructure drift
```

## 45. Pipeline Secret Leakage Detection

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: infrastructure,ci-cd,security
# @analysis-type: pipeline-secrets
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @target-platforms: github-actions,gitlab-ci
# @security-requirements: secrets-protection

Please detect and prevent pipeline secret leakage for my React TypeScript
```

## 46. Frontend Bundle Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: frontend,performance
# @analysis-type: bundle-analysis
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: size,load-time

Please analyze the frontend bundle of my React TypeScript project. This should include:
1. Bundle size breakdown by component/module
2. Identification of large dependencies
3. Tree-shaking effectiveness analysis
4. Code splitting opportunities
5. Unused code/dependency detection
6. Dynamic import opportunities
7. Bundle size reduction strategies
8. Initial load time optimization recommendations
```

## 47. Performance Profiling

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: frontend,performance
# @analysis-type: performance-profiling
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: speed,memory

Please perform comprehensive performance profiling for my React TypeScript project. This should include:
1. Render performance analysis
2. Memory usage patterns
3. JavaScript execution bottlenecks
4. Network request optimization
5. Asset loading optimization
6. State management performance
7. Performance optimization strategies
8. Core Web Vitals optimization recommendations
```

## 48. A11y Compliance Audit

```
# @copilot-mode: agent
# @model: claude-3.7
# @analysis-scope: frontend,accessibility
# @analysis-type: compliance,a11y
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @compliance-framework: wcag2.1-aa

Please perform a comprehensive accessibility audit of my React TypeScript project. This should include:
1. WCAG 2.1 AA compliance analysis
2. Keyboard navigation issues
3. Screen reader compatibility
4. Color contrast violations
5. Missing ARIA attributes
6. Focus management problems
7. Semantic HTML structure issues
8. Detailed remediation plan for each issue
```

## 49. SEO Optimization

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: frontend,seo
# @analysis-type: seo-optimization
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: seo,discoverability

Please analyze and optimize SEO for my React TypeScript project. This should include:
1. Meta tag analysis and optimization
2. Semantic HTML structure review
3. Page load speed optimization for SEO
4. Mobile-friendliness assessment
5. Structured data/schema.org implementation
6. Image optimization for SEO
7. URL structure and routing analysis
8. SEO best practices implementation plan
```

## 50. Animation and Transition Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: frontend,ux
# @analysis-type: animations
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: performance,smoothness

Please analyze animations and transitions in my React TypeScript project. This should include:
1. Identification of all animations and transitions
2. Animation performance analysis
3. CSS vs. JavaScript animation usage patterns
4. Animation library evaluation
5. Jank and frame drop detection
6. GPU acceleration opportunities
7. Animation accessibility compliance
8. Recommendations for smoother, more performant animations
```

## 51. Component API Design Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: component-api
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: usability,consistency

Please analyze component API design in my React TypeScript project. This should include:
1. Component props interface analysis
2. Props consistency across similar components
3. Component composition patterns
4. Callback naming and parameter consistency
5. Default props and optional props usage
6. TypeScript type definitions quality
7. Component API documentation quality
8. Recommendations for more intuitive and consistent component APIs
```

## 52. React Hook Pattern Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: hook-patterns
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: reusability,maintainability

Please analyze React hook patterns in my TypeScript project. This should include:
1. Custom hook inventory and usage patterns
2. Hook dependency array optimization
3. State management hook patterns
4. Effect hook cleanup implementation
5. Hook extraction opportunities
6. Hook testing strategies
7. Common hook anti-patterns
8. Recommendations for more reusable and maintainable hook patterns
```

## 53. Lazy Loading Implementation

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react,performance
# @analysis-type: lazy-loading
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: performance,user-experience

Please analyze and optimize lazy loading in my React TypeScript project. This should include:
1. Current lazy loading implementation assessment
2. Component lazy loading opportunities
3. Route-based code splitting analysis
4. Image and asset lazy loading
5. Above-the-fold content optimization
6. Loading state UX recommendations
7. Lazy loading threshold configuration
8. Implementation plan for comprehensive lazy loading strategy
```

## 54. Error Boundary Implementation

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react,error-handling
# @analysis-type: error-boundaries
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: resilience,user-experience

Please analyze error boundary implementation in my React TypeScript project. This should include:
1. Current error boundary coverage
2. Error recovery mechanisms
3. User feedback during errors
4. Error logging and reporting
5. Component-level vs. application-level error boundaries
6. Error boundary testing strategies
7. Error state UX recommendations
8. Implementation plan for comprehensive error handling
```

## 55. React Portal Usage Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,react
# @analysis-type: portals
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: accessibility,maintainability

Please analyze React portal usage in my TypeScript project. This should include:
1. Current portal implementation assessment
2. Modal and dialog implementation
3. Z-index management strategy
4. Portal accessibility compliance
5. Portal event bubbling behavior
6. Portal performance impact
7. Portal reusability patterns
8. Recommendations for improved portal implementation
```

## 56. Custom Webpack Configuration Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: build,webpack
# @analysis-type: build-configuration
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: build-time,bundle-size

Please analyze custom Webpack configuration in my React TypeScript project. This should include:
1. Current Webpack configuration assessment
2. Loader and plugin optimization
3. Build time optimization opportunities
4. Development vs. production configuration
5. Code splitting configuration
6. Asset optimization settings
7. Tree-shaking effectiveness
8. Recommendations for improved Webpack configuration
```

## 57. TypeScript Configuration Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: typescript,configuration
# @analysis-type: typescript-config
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: type-safety,development-experience

Please analyze TypeScript configuration in my React project. This should include:
1. Current tsconfig.json assessment
2. Compiler options optimization
3. Type checking strictness level
4. Path aliasing configuration
5. Library and target compatibility
6. Type declaration management
7. TypeScript-ESLint integration
8. Recommendations for improved TypeScript configuration
```

## 58. Storybook Integration Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: component-documentation,storybook
# @analysis-type: storybook-integration
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: documentation,development-experience

Please analyze Storybook integration in my React TypeScript project. This should include:
1. Current Storybook implementation assessment
2. Component story coverage
3. Storybook addon utilization
4. Component documentation quality
5. Interactive example quality
6. Accessibility testing in Storybook
7. Visual regression testing setup
8. Recommendations for improved Storybook implementation
```

## 59. Test Strategy Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: testing,quality
# @analysis-type: test-strategy
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: test-coverage,confidence

Please analyze the testing strategy in my React TypeScript project. This should include:
1. Current testing approach assessment
2. Unit vs. integration vs. e2e test balance
3. Test coverage analysis
4. Test organization and structure
5. Mock and stub usage patterns
6. Testing library selection evaluation
7. CI integration for testing
8. Recommendations for a comprehensive testing strategy
```

## 60. CSS-in-JS Implementation Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: styling,css
# @analysis-type: css-in-js
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: performance,maintainability

Please analyze CSS-in-JS implementation in my React TypeScript project. This should include:
1. Current CSS-in-JS library assessment
2. Runtime vs. compile-time CSS-in-JS
3. Style composition patterns
4. Theme implementation
5. Style reuse strategies
6. Style performance impact
7. Server-side rendering compatibility
8. Recommendations for improved CSS-in-JS implementation
```

## 61. API Integration Architecture

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: api,frontend
# @analysis-type: api-integration
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: reliability,maintainability

Please analyze API integration architecture in my React TypeScript project. This should include:
1. Current API client implementation assessment
2. API request pattern consistency
3. Error handling strategies
4. Authentication integration
5. Data transformation layers
6. API response caching
7. Offline support strategies
8. Recommendations for improved API integration architecture
```

## 62. Service Worker Implementation

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: pwa,offline
# @analysis-type: service-workers
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: offline-experience,performance

Please analyze service worker implementation in my React TypeScript project. This should include:
1. Current service worker implementation assessment
2. Caching strategies for different assets
3. Offline user experience
4. Background sync capabilities
5. Push notification integration
6. Update and versioning strategy
7. Service worker lifecycle management
8. Recommendations for improved service worker implementation
```

## 63. Data Visualization Component Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: data-visualization,charts
# @analysis-type: visualization-components
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: performance,accuracy

Please analyze data visualization components in my React TypeScript project. This should include:
1. Current charting library assessment
2. Visualization performance with large datasets
3. Responsive visualization strategies
4. Accessibility of data visualizations
5. Interactive visualization features
6. Visualization theming and customization
7. Data processing for visualizations
8. Recommendations for improved data visualization implementation
```

## 64. Form Validation Architecture

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: forms,validation
# @analysis-type: form-architecture
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: user-experience,maintainability

Please analyze form validation architecture in my React TypeScript project. This should include:
1. Current form library assessment
2. Validation strategy (client-side vs. server-side)
3. Field-level vs. form-level validation
4. Error message presentation
5. Async validation patterns
6. Complex validation rule management
7. Form submission handling
8. Recommendations for improved form validation architecture
```

## 65. WebSocket Integration Analysis

```
# @copilot-mode: agent
# @model: gpt-4o
# @analysis-scope: real-time,websockets
# @analysis-type: websocket-integration
# @target: D:\crm-panel-front
# @output-format: markdown
# @detail-level: expert
# @optimization: true
# @optimize-for: reliability,performance

Please analyze WebSocket integration in my React TypeScript project. This should include:
1. Current WebSocket implementation assessment
2. Connection management strategies
3. Reconnection and error handling
4. Message format and protocol
5. State synchronization patterns
6. Real-time update UI patterns
7. WebSocket security considerations
8. Recommendations for improved WebSocket integration
```
