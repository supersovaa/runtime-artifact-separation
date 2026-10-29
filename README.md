# Runtime Artifact Separation

A lightweight skill that separates reproducible execution environments from generated artifacts retained for inspection, delivery, or reuse.

## When to use

Use this skill when preparing development or test environments, choosing output directories, implementing generators, or running work that produces files. It applies when the workflow needs to distinguish runtime infrastructure from retained outputs.

## Installation

Add the [SKILL.md](SKILL.md) to the agent's skill directory, or link to it directly from the repository's relevant task guidance (such as `AGENTS.md` or task-specific skills). Activate it from the work types described above.

The repository defines its own runtime and artifact directory names and migration policy.
