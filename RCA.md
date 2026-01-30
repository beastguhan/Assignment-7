# 🚨 Root Cause Analysis (RCA)

## Incident Summary
The application intermittently returned HTTP 500 errors during normal operation.

---

## Timeline
- T0: Application deployed using Docker Compose
- T1: Users reported intermittent failures
- T2: Issue reproduced using repeated curl requests
- T3: Logs collected from the container
- T4: Root cause identified

---

## Impact
- Approximately 20% of requests failed
- Unreliable service behavior
- Poor user experience

---

## Detection
The issue was detected by:
- Manual testing
- Repeated HTTP requests
- Container log inspection

---

## Root Cause
An intentionally buggy code path caused random unhandled exceptions, leading to HTTP 500 responses.

Specifically:
- Random failure logic
- No exception handling
- No graceful degradation

---

## Evidence
Logs showed stack traces with:
# 🚨 Root Cause Analysis (RCA)

## Incident Summary
The application intermittently returned HTTP 500 errors during normal operation.

---

## Timeline
- T0: Application deployed using Docker Compose
- T1: Users reported intermittent failures
- T2: Issue reproduced using repeated curl requests
- T3: Logs collected from the container
- T4: Root cause identified

---

## Impact
- Approximately 20% of requests failed
- Unreliable service behavior
- Poor user experience

---

## Detection
The issue was detected by:
- Manual testing
- Repeated HTTP requests
- Container log inspection

---

## Root Cause
An intentionally buggy code path caused random unhandled exceptions, leading to HTTP 500 responses.

Specifically:
- Random failure logic
- No exception handling
- No graceful degradation

---

## Evidence
Logs showed stack traces with:
Exception: Random application failure occurred


---

## Resolution
The incident was resolved by identifying the faulty code path.

No live fix was applied, as this was a simulated failure.

---

## Preventive Actions
- Add proper exception handling
- Implement retries or circuit breakers
- Add monitoring and alerting
- Avoid non-deterministic logic in production code
- Improve test coverage

---

## Lessons Learned
- Logs are critical for incident debugging
- Random failures are hard to detect without observability
- Proper error handling prevents outages

---

