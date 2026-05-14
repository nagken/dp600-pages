# DP-600 Extra Concepts

> Subtle distinctions that show up in exam wording.

## Lakehouse vs Warehouse

| Trait | Lakehouse | Warehouse |
|---|---|---|
| Engine | Spark | Distributed T-SQL |
| Read T-SQL | Yes (SQL endpoint, read-only) | Yes |
| Write T-SQL | No | Yes |
| Files API | Yes | No |
| Best for | Big data, ML, files | Multi-table SQL ETL, BI |

## Dataflow Gen1 vs Gen2

| Gen1 | Gen2 |
|---|---|
| Power BI Service only | Fabric workspace |
| Output: dataflow CDM folders | Output: Lakehouse / Warehouse / Azure SQL / KQL DB |
| Limited data destinations | Many destinations + diagnostic logs |

## V-Order

- Microsoft-specific Parquet write reorganizes row groups for optimal VertiPaq read.
- Default for Fabric Spark + Warehouse.
- Trade-off: ~15% more write CPU; ~50% faster reads.

## Direct Lake fallback

- Direct Lake reads Delta directly into VertiPaq.
- Falls back to DirectQuery transparently when:
  - Number of unique columns exceeds limit (per SKU).
  - Row group size too large.
  - Underlying query unsupported.

## Capacity bursting and smoothing

- **Bursting**: a query may exceed CU briefly.
- **Smoothing**: 24h CU averaging avoids throttling on spikes.
- **Throttling**: sustained overrun -> degraded perf.
- **Rejection**: sustained beyond throttle limit -> queries refused.

## Notebook utility helpers (`notebookutils`)

- `notebookutils.fs.ls(path)` - list files.
- `notebookutils.lakehouse.get(name)` - resolve lakehouse by name.
- `notebookutils.notebook.run(nbName, params)` - chain notebooks.
- `notebookutils.credentials.getSecret(...)` - Key Vault.

## Pipeline expressions

- `@pipeline().parameters.X`, `@activity('A').output`, `@utcNow()`, `@formatDateTime(...)`, `@if(equals(...))`.
- Use **variable libraries** to parameterize across stages.

## Endorsement

| Level | Who can set |
|---|---|
| None | Default |
| Promoted | Any author with permission |
| Certified | Tenant admin or designated reviewer |

## Sensitivity label inheritance

- Source labeled in M365 -> imported into Fabric -> downstream items inherit.
- Removing label requires explicit override (audit logged).

---

[Master Index](00-MASTER-INDEX.md)
