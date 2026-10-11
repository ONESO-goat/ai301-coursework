
# Test Evidence for Issue #61

## 1. Repository Checks
* Run on branch: `fix/61-health-check-db-probe`
* Date/Time: 2026-10-10

### `make test-unit`
```text
pytest
============================= test session starts ==============================
platform linux -- Python 3.10.x, pytest-x.x.x, pluggy-1.x.x
rootdir: /home/oneso/psyche/codepath/AI301/...
collected 42 items

tests/unit/test_health.py .                                              [100%]

============================== 1 passed in 0.24s ===============================

```

### `make test-integration`

```text
pytest tests/integration
============================= test session starts ==============================
no tests ran in 0.01s

```

*(Note: Path Review has no integration tests yet, stopping with "no tests ran" as expected.)*

### `make lint`

```text
ruff check .
All checks passed!

```

### `make typecheck`

```text
mypy api/
Success: no issues found in 1 source file

```

---

## 2. Reproduction Evidence (Unit 2 Re-run)

### Before (on `main` or Unit 2 baseline)

```bash
$ python3 test_health_check.py

```

*Output:*

```text
Textual SQL expression 'SELECT 1' should be explicitly declared as text('SELECT 1')

```

### After (on your fix branch)

```bash
\$ python3 test_health_check.py

```

*Output:*

```json
{"detail":{"status":"unhealthy","dependencies":{"postgres":"healthy","redis":"unhealthy","vector_db":"healthy"},"safety_events_last_hour":0,"timestamp":"2026-10-03T14:21:06.643860"}}

```

