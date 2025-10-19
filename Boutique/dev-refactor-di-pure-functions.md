# Refactor to DI & Pure Functions
# 重构为依赖注入与纯函数

Model targets: GPT-4.1 / GPT-5
模型推荐：GPT-4.1 / GPT-5

Short Description (EN)
Reduce side effects and improve testability by introducing dependency injection and pure function boundaries.

简要说明（中文）
通过引入依赖注入与纯函数边界，降低副作用、提升可测试性与可维护性。

Usage (EN)
Provide the module and where it performs I/O or uses globals. State constraints (API stability, performance, etc.).

用法（中文）
提供模块代码与I/O/全局变量位置，说明约束（API稳定性、性能等）。

Variables / Parameters
- {module}: module content and responsibilities / 模块内容与职责
- {io_points}: I/O points (network, FS, DB, time) / I/O位置（网络、文件、数据库、时间）
- {constraints}: compatibility, performance, deadlines / 兼容、性能与交付限制

System Prompt (copyable)
```
You are a refactoring strategist. Goal: introduce DI and pure functions around {module}.
Deliver:
1) Refactor plan: seams, interfaces, and dependency graph changes.
2) Before/After snippets demonstrating DI and purity.
3) Risks and mitigations (perf, API changes, regression).
Keep changes incremental and reversible. Respect {constraints}.
```

User Template (copyable)
```
Module:
{module}

I/O points:
{io_points}

Constraints:
{constraints}

Please provide: refactor plan, before/after code, and risks.
```

Response Style / Output Format (EN/中文)
- High-level plan then concrete steps. / 先高层方案再落地步骤。
- Show small before/after diffs. / 展示小步前后对比。
- List risks and mitigations. / 列出风险与缓解策略。

Example (few-shot)
- Example input
```
Module: function sendReport(){ const now=Date.now(); const api=new Client(); api.post('/r',{ts:now}) }
I/O: time, network
Constraints: keep API signature
```
- Example output (short)
```
Plan
- Extract clock and transport as interfaces; inject via params.

Before
```js
function sendReport(){ const now=Date.now(); const api=new Client(); api.post('/r',{ts:now}) }
```
After
```js
function sendReport(clock, transport){ const ts=clock.now(); return transport.post('/r',{ts}) }
```
Risks
- Call sites need adapters (mitigation: add default wrappers).
```

Notes / Tips
- Prefer constructor/parameter injection. / 优先构造或参数注入。
- Keep side-effect code thin. / 将副作用收敛在薄层中。