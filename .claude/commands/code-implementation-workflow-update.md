---
name: code-implementation-workflow-update
description: Workflow command scaffold for code-implementation-workflow-update in DeepCode.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /code-implementation-workflow-update

Use this workflow when working on **code-implementation-workflow-update** in `DeepCode`.

## Goal

Improvements, bug fixes, or refactoring of the core code implementation workflow (the main pipeline for converting input into code).

## Common Files

- `workflows/code_implementation_workflow.py`
- `workflows/code_implementation_workflow_index.py`
- `workflows/agent_orchestration_engine.py`
- `workflows/agents/*.py`
- `utils/loop_detector.py`
- `utils/model_limits.py`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit workflows/code_implementation_workflow.py and workflows/code_implementation_workflow_index.py
- Often update workflows/agent_orchestration_engine.py
- Update related agent files in workflows/agents/
- Update utils/loop_detector.py, utils/model_limits.py, or utils/file_processor.py if needed
- Update requirements.txt if dependencies change

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.