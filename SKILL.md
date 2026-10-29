---
name: runtime-artifact-separation
description: Separate reproducible execution environments and working infrastructure from generated artifacts retained for inspection or reuse. Use when preparing development environments, configuring execution or output paths, implementing generators, or running tests that create files.
---

# Runtime Artifact Separation

Keep execution environments and retained outputs in separate directory roots.

## Core rule

Before creating or selecting a file output location, identify its purpose:

- **Runtime environment:** Dependencies and execution infrastructure used to run work, such as virtual environments, tool installations, caches, build intermediates, and temporary execution support.
- **Artifact:** A generated result retained to inspect, verify, deliver, compare, resume, or reuse, such as reports, test evidence, generated datasets, training outputs, models, and logs retained as evidence.

Place runtime environments under the repository's designated runtime root and artifacts under its designated artifact root. Use distinct roots with names that communicate these roles.

## Apply to work

1. Read the repository's existing path conventions, output configuration, and retention requirements.
2. Select the runtime and artifact roots from those conventions, or establish separate roots when preparing a new layout.
3. Route new environments and outputs according to their purpose. Keep related artifacts together under the artifact root.
4. When a tool defaults to a shared directory, explicitly configure its runtime and artifact paths where supported.
5. Check the resulting paths during implementation and verification, including generated files and documentation of output locations.

Classify a file by why it is retained. A model or log needed only during execution belongs with runtime infrastructure; a model checkpoint or log retained as an output belongs with artifacts.

For existing mixed directories, establish the separation for new outputs and handle migration through the repository's normal change planning and compatibility requirements.

## Responsibility boundary

This skill owns directory separation based on runtime versus retained-artifact responsibility. The repository owns concrete path names, retention rules, ignore patterns, and migration decisions. Testing and CI skills own which executions and evidence are required.
