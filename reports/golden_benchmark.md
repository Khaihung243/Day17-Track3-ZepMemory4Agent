# Lab 17 Golden Set Report

- Implementation: `student`
- Kind: `golden`
- Cases: **20**
- Passed: **20/20**
- Evidence hit rate: **100.0%**
- Average retrieval latency: **1663.9 ms**
- Average token reduction vs full source context: **3.8%**
- Golden bonus: **10/10** (100% required)

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| G01 | short_term | PASS | 0.3 | 227 | 0.0% |  |
| G02 | short_term | PASS | 0.0 | 133 | 0.0% |  |
| G06 | long_term | PASS | 1789.9 | 808 | 0.0% |  |
| G09 | semantic | PASS | 486.5 | 367 | 20.0% |  |
| G10 | semantic | PASS | 550.0 | 343 | 25.3% |  |
| G14 | mixed | PASS | 1927.8 | 581 | 0.0% |  |
| G03 | long_term | PASS | 2663.8 | 935 | 0.0% |  |
| G04 | long_term | PASS | 1601.9 | 950 | 0.0% |  |
| G07 | episodic | PASS | 533.8 | 512 | 0.0% |  |
| G08 | episodic | PASS | 500.4 | 553 | 0.0% |  |
| G11 | mixed | PASS | 1865.5 | 581 | 0.0% |  |
| G13 | mixed | PASS | 1014.6 | 500 | 11.5% |  |
| G15 | mixed | PASS | 2442.0 | 831 | 0.0% |  |
| G16 | mixed | PASS | 2030.2 | 581 | 0.0% |  |
| G17 | mixed | PASS | 2158.9 | 581 | 0.0% |  |
| G18 | mixed | PASS | 3008.4 | 500 | 11.5% |  |
| G19 | mixed | PASS | 5215.2 | 581 | 0.0% |  |
| G05 | long_term | PASS | 1504.1 | 958 | 0.0% |  |
| G12 | mixed | PASS | 1926.6 | 581 | 8.1% |  |
| G20 | mixed | PASS | 2058.5 | 756 | 0.0% |  |

## Evidence excerpts

### G01 - short_term

`<SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. | assistant: Noted staging constraint. | user: Filler A about button padding. | assistant: Filler A. | user: Filler B about color tokens. | assistant: Filler B. | user: Filler C about copy tone. | assistant: Filler C. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. - user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. - assistant: Noted staging constraint. </DURA`

### G02 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### G06 - long_term

`FACT: Lan Tran does not use Python for backend examples. [valid_at=2026-08-01T11:00:00Z, invalid_at=2026-08-01T11:00:20Z] FACT: Da hieu uses Java for backend examples. [valid_at=2026-08-01T11:00:20Z, invalid_at=None] FACT: Lan Tran prioritizes using Java in their work. [valid_at=2026-08-01T11:00:00Z, invalid_at=None] FACT: Da hieu is for backend examples. [valid_at=2026-08-01T11:00:20Z, invalid_at=None] FACT: Da hieu uses Spring Boot for backend examples. [valid_at=2026-08-01T11:00:20Z, invalid_at=None] FACT: Lan Tran prioritizes using Spring Boot in their work. [valid_at=2026-08-01T11:00:00Z, invalid_at=None]  <USER_SUMMARY> Lan's project is LOTUS-88. They prioritize Java and Spring Boot fo`

### G09 - semantic

`EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Mark`

### G10 - semantic

`EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. EPISODE: {"id":"kb-context-budget","entity":"Memory Context Budget","summary":"Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDG EPISODE: Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDGET-10-4-3-3.  EPISODE: {"id":"kb-memor`

### G14 - mixed

`<LONG_TERM> FACT: Lan Tran does not use Python for backend examples. [valid_at=2026-08-01T11:00:00Z, invalid_at=2026-08-01T11:00:20Z] FACT: Lan Tran prioritizes using Java in their work. [valid_at=2026-08-01T11:00:00Z, invalid_at=None] FACT: Da hieu is for backend examples. [valid_at=2026-08-01T11:00:20Z, invalid_at=None] FACT: The Lab Assistant identifies Da hieu. [valid_at=2026-08-01T11:00:20Z, invalid_at=None] FACT: Da hieu uses Java for backend examples. [valid_at=2026-08-01T11:00:20Z, invalid_at=None] FACT: Lan Tran prioritizes using Spring Boot in their work. [valid_at=2026-08-01T11:00:00Z, invalid_at=None]  <USER_SUMMARY> Lan's project is LOTUS-88. They prioritize Java and Spring Boot`

### G03 - long_term

`FACT: Minh Nguyen does not like Java. [valid_at=2026-08-01T09:00:00Z, invalid_at=2026-08-01T09:00:20Z] FACT: Minh Nguyen likes Python. [valid_at=2026-08-01T09:00:00Z, invalid_at=None] FACT: Assistant prefers the timeline when explaining Task. [valid_at=2026-08-01T09:02:20Z, invalid_at=None] FACT: Minh Nguyen is learning async/await. [valid_at=2026-08-01T09:02:00Z, invalid_at=None] FACT: Minh Nguyen often confuses coroutine with Task. [valid_at=2026-08-01T09:02:00Z, invalid_at=None] FACT: Assistant prefers the timeline when explaining coroutine. [valid_at=2026-08-01T09:02:20Z, invalid_at=None]  <USER_SUMMARY> Minh prefers Python and uses it for personal projects like ORCHID-27. For the compan`

### G04 - long_term

`FACT: Minh Nguyen often confuses coroutine with Task. [valid_at=2026-08-01T09:02:00Z, invalid_at=None] FACT: Minh Nguyen is learning async/await. [valid_at=2026-08-01T09:02:00Z, invalid_at=None] FACT: coroutine is often confused with Task by Minh Nguyen. [valid_at=2026-08-01T09:02:00Z, invalid_at=None] FACT: Minh Nguyen is debugging async HTTP. [valid_at=2026-08-03T10:00:00Z, invalid_at=None] FACT: Minh Nguyen has a to-do to complete the benchmark report before Friday at 16:00. [valid_at=2026-08-01T09:04:00Z, invalid_at=None] FACT: Minh Nguyen requested that the assistant use short examples when explaining code. [valid_at=2026-08-01T09:00:00Z, invalid_at=None]  <USER_SUMMARY> Minh prefers Py`

### G07 - episodic

`EPISODE: Toi nay minh viet tool ca nhan de tai hien su co HTTP roi sua dung playbook. Can ba manh: ngon ngu minh thich khi lam mot minh, ma su co async lan truoc, va buoc playbook truoc khi tang timeout. Scope Minh, dung tron Lan. EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua Minh. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Hay kiem tra connection pool, lifecycle cua client va concurrency. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection ch`

### G08 - episodic

`EPISODE: Toi nay minh viet tool ca nhan de tai hien su co HTTP roi sua dung playbook. Can ba manh: ngon ngu minh thich khi lam mot minh, ma su co async lan truoc, va buoc playbook truoc khi tang timeout. Scope Minh, dung tron Lan. EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua Minh. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Hay kiem tra connection pool, lifecycle cua client va concurrency. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection ch`

### G11 - mixed

`<LONG_TERM> FACT: Minh Nguyen increased the timeout to 60s. [valid_at=2026-08-03T10:00:00Z, invalid_at=None] FACT: Minh Nguyen's attempt to debug async HTTP failed even after increasing the timeout to 60s. [valid_at=2026-08-03T10:00:00Z, invalid_at=None] FACT: Minh Nguyen requested that the assistant use short examples when explaining code. [valid_at=2026-08-01T09:00:00Z, invalid_at=None] FACT: Minh Nguyen is learning async/await. [valid_at=2026-08-01T09:02:00Z, invalid_at=None] FACT: Minh Nguyen likes Python. [valid_at=2026-08-01T09:00:00Z, invalid_at=None] FACT: Minh Nguyen is debugging async HTTP. [valid_at=2026-08-03T10:00:00Z, invalid_at=None]  <USER_SUMMARY> Minh prefers Python and use`

### G13 - mixed

`<EPISODIC> EPISODE: Toi nay minh viet tool ca nhan de tai hien su co HTTP roi sua dung playbook. Can ba manh: ngon ngu minh thich khi lam mot minh, ma su co async lan truoc, va buoc playbook truoc khi tang timeout. Scope Minh, dung tron Lan. EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua Minh. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Hay kiem tra connection pool, lifecycle cua client va concurrency. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la co`

### G15 - mixed

`<LONG_TERM> FACT: Minh Nguyen is debugging async HTTP. [valid_at=2026-08-03T10:00:00Z, invalid_at=None] FACT: Minh Nguyen's attempt to debug async HTTP failed even after increasing the timeout to 60s. [valid_at=2026-08-03T10:00:00Z, invalid_at=None] FACT: Minh Nguyen is learning async/await. [valid_at=2026-08-01T09:02:00Z, invalid_at=None] FACT: Minh Nguyen increased the timeout to 60s. [valid_at=2026-08-03T10:00:00Z, invalid_at=None] FACT: Minh Nguyen suggests reusing aiohttp ClientSession for efficiency. [valid_at=2026-08-03T10:03:00Z, invalid_at=None] FACT: Minh Nguyen likes Python. [valid_at=2026-08-01T09:00:00Z, invalid_at=None]  <USER_SUMMARY> Minh prefers Python and uses it for person`

### G16 - mixed

`<LONG_TERM> FACT: The benchmark report is an open loop LAB-REPORT-1600. [valid_at=2026-08-01T09:04:00Z, invalid_at=None] FACT: Minh Nguyen is learning async/await. [valid_at=2026-08-01T09:02:00Z, invalid_at=None] FACT: Minh Nguyen has a to-do to complete the benchmark report before Friday at 16:00. [valid_at=2026-08-01T09:04:00Z, invalid_at=None] FACT: Minh Nguyen is debugging async HTTP. [valid_at=2026-08-03T10:00:00Z, invalid_at=None] FACT: Minh Nguyen often confuses coroutine with Task. [valid_at=2026-08-01T09:02:00Z, invalid_at=None] FACT: Minh Nguyen's attempt to debug async HTTP failed even after increasing the timeout to 60s. [valid_at=2026-08-03T10:00:00Z, invalid_at=None]  <USER_SUM`

### G17 - mixed

`<LONG_TERM> FACT: coroutine is often confused with Task by Minh Nguyen. [valid_at=2026-08-01T09:02:00Z, invalid_at=None] FACT: Minh Nguyen often confuses coroutine with Task. [valid_at=2026-08-01T09:02:00Z, invalid_at=None] FACT: Minh Nguyen is debugging async HTTP. [valid_at=2026-08-03T10:00:00Z, invalid_at=None] FACT: Assistant prefers the timeline when explaining coroutine. [valid_at=2026-08-01T09:02:20Z, invalid_at=None] FACT: Minh Nguyen is learning async/await. [valid_at=2026-08-01T09:02:00Z, invalid_at=None] FACT: Minh Nguyen requested that the assistant use short examples when explaining code. [valid_at=2026-08-01T09:00:00Z, invalid_at=None]  <USER_SUMMARY> Minh prefers Python and us`

### G18 - mixed

`<EPISODIC> EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua Minh. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Hay kiem tra connection pool, lifecycle cua client va concurrency. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Da ghi nhan trajectory: increase timeout khong hieu qua; ClientSession + concurrency=20 giai quyet connection churn. EPISODE: Toi nay minh viet tool ca n`

### G19 - mixed

`<LONG_TERM> FACT: Minh Nguyen is debugging async HTTP. [valid_at=2026-08-03T10:00:00Z, invalid_at=None] FACT: Minh Nguyen suggests reusing aiohttp ClientSession for efficiency. [valid_at=2026-08-03T10:03:00Z, invalid_at=None] FACT: Minh Nguyen is learning async/await. [valid_at=2026-08-01T09:02:00Z, invalid_at=None] FACT: Minh Nguyen's attempt to debug async HTTP failed even after increasing the timeout to 60s. [valid_at=2026-08-03T10:00:00Z, invalid_at=None] FACT: The concurrency should be set to 20 when reusing aiohttp ClientSession. [valid_at=2026-08-03T10:03:00Z, invalid_at=2026-08-03T10:03:20Z] FACT: Minh Nguyen requires NestJS for the BLUEBIRD-42 project. [valid_at=2026-08-05T08:00:00Z`

### G05 - long_term

`FACT: Python is not to be used for the backend of the BLUEBIRD-42 project. [valid_at=2026-08-05T08:00:00Z, invalid_at=None] FACT: Minh Nguyen likes Python. [valid_at=2026-08-01T09:00:00Z, invalid_at=None] FACT: Minh Nguyen requires TypeScript for the BLUEBIRD-42 project. [valid_at=2026-08-05T08:00:00Z, invalid_at=None] FACT: Minh Nguyen has a personal project named ORCHID-27. [valid_at=2026-08-01T09:00:00Z, invalid_at=2026-08-01T09:00:20Z] FACT: Minh Nguyen does not like Java. [valid_at=2026-08-01T09:00:00Z, invalid_at=2026-08-01T09:00:20Z] FACT: Minh Nguyen requires NestJS for the BLUEBIRD-42 project. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z]  <USER_SUMMARY> Minh pref`

### G12 - mixed

`<LONG_TERM> FACT: Minh Nguyen requires NestJS for the BLUEBIRD-42 project. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: Python is not to be used for the backend of the BLUEBIRD-42 project. [valid_at=2026-08-05T08:00:00Z, invalid_at=None] FACT: The BLUEBIRD-42 project requires NestJS. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: Minh Nguyen requires TypeScript for the BLUEBIRD-42 project. [valid_at=2026-08-05T08:00:00Z, invalid_at=None] FACT: The BLUEBIRD-42 project requires TypeScript. [valid_at=2026-08-05T08:00:00Z, invalid_at=2026-08-05T08:00:20Z] FACT: BLUEBIRD-42 uses TypeScript/NestJS. [valid_at=2026-08-05T08:00:20Z, invalid_at=None]  `

### G20 - mixed

`<SHORT_TERM> <SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Filler about dashboard widgets. | assistant: Filler. | user: Filler about CSS variables. | assistant: Filler. | user: Filler about copy review. | assistant: Filler. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. </DURABLE_NOTES> <RECENT_TURNS> user: Filler about empty charts. assistant: Filler. user: Filler about telemetry. assistant: Filler. user: Filler about a11y labels. assistant: Filler. </RECENT_TURNS> </SHORT_TERM>`
