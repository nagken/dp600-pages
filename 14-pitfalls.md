# DP-600 Pitfalls

> Mistakes that cost points and dashboards.

## Capacity and workspace

- One F2 capacity for all workspaces -> throttling + report timeouts.
- Forgetting to pause non-prod F SKUs -> silent CU billing.
- Mixing Pro-only workspaces with Fabric items -> Fabric items need a capacity.
- Workspace Admin granted to data engineers when Contributor would suffice.

## OneLake and lakehouse

- Loading raw CSV into Gold without medallion - ungoverned reporting layer.
- No OPTIMIZE / VACUUM - small file problem - slow queries.
- Partitioning by high-cardinality column -> partition explosion.
- Shortcuts not refreshed after rename / move at source -> broken pointers.

## Mirroring

- Setting up mirroring then re-copying via pipeline - defeats zero-ETL.
- Mirrored database read-only - cannot UPDATE in OneLake (use original).
- Source DDL changes can break mirroring; monitor health.

## Semantic models

- Direct Lake silently falls back to DirectQuery -> performance regress.
- Auto date hierarchies enabled -> hidden tables bloat memory.
- Bidirectional relationships -> wrong totals.
- Calculated columns where measures suffice -> larger model size.
- Forgetting to mark Date table -> time intelligence breaks.

## DAX

- Using `EARLIER` instead of variables -> hard to read + sometimes wrong.
- `FILTER` outside `CALCULATE` -> performance hit.
- Storing measures in calculated columns -> miss filter context.
- Time-intel without contiguous date table -> blanks for missing dates.

## Real-Time Intelligence

- KQL query without `where Timestamp > ago(...)` -> scans full retention.
- Eventstream not partitioned by key -> hot-shard.
- Retention policy too long -> KQL DB bloat + cost.

## Lifecycle

- No deployment pipeline -> manual copy + drift between dev / prod.
- Variable libraries missing for connection strings -> hard-coded values.
- Direct edits in prod workspace -> Git diff explosion.
- No sensitivity labels on imported source -> downstream items unlabeled.

## Security

- RLS without testing as role -> oversharing.
- OLS configured but not exposed via XMLA -> silently ignored.
- Workspace contributor with full edit when read-only role exists.

---

[Master Index](00-MASTER-INDEX.md)
