```markdown
# DeepCode Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development patterns, workflows, and coding conventions used in the DeepCode repository—a Python-based codebase focused on code implementation workflows, agent orchestration, UI updates, and robust configuration management. You'll learn how to contribute effectively by following established commit patterns, file structures, and step-by-step procedures for common update and release tasks.

---

## Coding Conventions

**File Naming:**  
- Use `camelCase` for Python files.  
  _Example:_ `fileProcessor.py`, `loopDetector.py`

**Import Style:**  
- Use **relative imports** within modules.
  ```python
  from .utils import fileProcessor
  from ..workflows import agentOrchestrationEngine
  ```

**Export Style:**  
- Use **default exports** (i.e., no explicit `__all__` unless needed).
  ```python
  # fileProcessor.py
  def process_file(...):
      ...
  ```

**Commit Patterns:**  
- Prefixes: `feat`, `docs`, `fix`, `refactor`, `chore`, `merge`
- Average commit message length: ~49 characters  
  _Example:_  
  ```
  feat: add loop detection to file processor
  fix: handle PDF conversion errors in pipeline
  ```

---

## Workflows

### Code Implementation Workflow Update
**Trigger:** When improving, fixing, or refactoring the core code implementation pipeline  
**Command:** `/update-code-implementation-workflow`

1. Edit `workflows/code_implementation_workflow.py` and `workflows/code_implementation_workflow_index.py`
2. Update `workflows/agent_orchestration_engine.py` as needed
3. Modify related agent files in `workflows/agents/`
4. Update utility files: `utils/loop_detector.py`, `utils/model_limits.py`, `utils/file_processor.py` if required
5. Update `requirements.txt` if dependencies change
6. Update UI or handler files if pipeline output changes

_Example:_  
```python
# workflows/code_implementation_workflow.py
from .agents import codeAgent
from ..utils.loop_detector import detect_loops
```

---

### Configuration and Secrets Hygiene
**Trigger:** When updating configuration files, secrets, or `.gitignore` for security and environment setup  
**Command:** `/update-config-secrets`

1. Edit `mcp_agent.config.yaml` and/or `mcp_agent.secrets.yaml`
2. Update `.gitignore` to include/exclude secret/config patterns
3. Modify `requirements.txt` if new environment variables or providers are added
4. Document changes in `README.md` or add `.env.example`

_Example:_  
```yaml
# mcp_agent.config.yaml
database_url: ${DATABASE_URL}
```
```gitignore
# .gitignore
*.secrets.yaml
.env
```

---

### UI Release or Major Update
**Trigger:** When releasing a new UI version or making significant UI changes  
**Command:** `/release-ui`

1. Add or update files in `new_ui/backend/` and `new_ui/frontend/`
2. Update assets in `assets/icons/` and `assets/NewUI.png`
3. Update `README.md` and `README_ZH.md` to reflect UI changes
4. Update legacy UI files if affected: `ui/components.py`, `ui/handlers.py`, `ui/layout.py`, `ui/sidebar_feed.py`, `ui/styles.py`

---

### Version Bump and Changelog Update
**Trigger:** When releasing a new version  
**Command:** `/bump-version`

1. Edit `__init__.py` to update the version string
2. Update `CHANGELOG.md` with new release notes
3. Update `README.md` and `README_ZH.md` if needed

_Example:_  
```python
# __init__.py
__version__ = "1.2.0"
```

---

### Nanobot Integration or Update
**Trigger:** When adding or updating the embedded nanobot agent  
**Command:** `/update-nanobot`

1. Add or update files under `nanobot/` (including agent, bridge, skills, workspace, config)
2. Update `nanobot_config.json.example`
3. Update `README.md` or `assets/nanobot.png` if branding or docs change

---

### Docker Support Update
**Trigger:** When improving Docker deployment or adding new Docker features  
**Command:** `/update-docker`

1. Edit or add files under `deepcode_docker/` (e.g., `Dockerfile`, `docker-compose.yml`, entrypoint, run scripts)
2. Edit `.dockerignore`
3. Update `README.md` and/or `README_ZH.md` to document Docker usage

_Example:_  
```dockerfile
# deepcode_docker/Dockerfile
FROM python:3.10
COPY . /app
WORKDIR /app
RUN pip install -r requirements.txt
CMD ["python", "main.py"]
```

---

### Bugfix Multi-File Pipeline
**Trigger:** When fixing a bug that affects multiple pipeline stages  
**Command:** `/fix-bug-multi-pipeline`

1. Edit `tools/pdf_converter.py`, `utils/file_processor.py`, `utils/loop_detector.py`, `utils/model_limits.py` as needed
2. Edit `workflows/agent_orchestration_engine.py` and `workflows/code_implementation_workflow.py`
3. Update `requirements.txt` if dependencies are affected
4. Update UI or handlers if user-facing behavior changes

---

## Testing Patterns

- **Test Files:** Use the pattern `*.test.*` for test files (e.g., `fileProcessor.test.py`)
- **Framework:** No specific testing framework detected—use standard Python `unittest` or `pytest` as appropriate.
- **Example:**
  ```python
  # fileProcessor.test.py
  import unittest
  from .fileProcessor import process_file

  class FileProcessorTest(unittest.TestCase):
      def test_process_file(self):
          self.assertTrue(process_file("test.txt"))
  ```

---

## Commands

| Command                              | Purpose                                                         |
|---------------------------------------|-----------------------------------------------------------------|
| /update-code-implementation-workflow  | Update or refactor the code implementation pipeline              |
| /update-config-secrets                | Update configuration, secrets, or .gitignore for hygiene         |
| /release-ui                          | Release a new UI version or make major UI changes                |
| /bump-version                        | Bump the project version and update the changelog                |
| /update-nanobot                      | Add or update nanobot integration                               |
| /update-docker                       | Add or update Docker support files                               |
| /fix-bug-multi-pipeline              | Fix bugs affecting multiple pipeline files                       |
```
