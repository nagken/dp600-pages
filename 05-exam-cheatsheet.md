# DP-600 Exam Decision Reference

> Fast lookup table by problem wording. Use during review.

## Workspace and capacity

| Wording | Pick |
|---|---|
| "predictable cost dedicated compute" | F SKU capacity (Fabric) |
| "cross-workspace governance grouping" | Domain |
| "promote dev to test to prod" | Deployment pipeline + variable libraries |
| "source-control items" | Git integration (Azure DevOps / GitHub) |
| "60-day evaluation" | Fabric trial (F64-equivalent) |
| "pause non-prod compute" | Pause F SKU |

## Ingest

| Wording | Pick |
|---|---|
| "low-code, citizen developer" | Dataflow Gen2 |
| "PySpark, custom logic" | Notebook |
| "orchestrate multi-step ingest" | Data Pipeline |
| "reference S3 / ADLS without copy" | OneLake shortcut |
| "near-real-time mirror of Azure SQL" | Mirroring |
| "stream IoT events into KQL" | Eventstream + KQL DB |

## Storage

| Wording | Pick |
|---|---|
| "files + tables, big data, ML" | Lakehouse |
| "T-SQL DW, multi-table transactions" | Warehouse |
| "telemetry / logs / time-series" | Eventhouse / KQL DB |
| "single tenant lake" | OneLake |

## Optimize

| Wording | Pick |
|---|---|
| "Microsoft Parquet write order" | V-Order |
| "compact small files" | OPTIMIZE + VACUUM |
| "cluster on common predicate" | Z-Order |
| "skip whole partitions" | Partition by date / region |

## Semantic model storage mode

| Wording | Pick |
|---|---|
| "small dataset, fastest" | Import |
| "real-time over source" | DirectQuery |
| "huge dataset on OneLake" | Direct Lake |
| "mix dims + facts" | Composite |

## Security

| Wording | Pick |
|---|---|
| "filter rows per user" | RLS (DAX role) |
| "hide columns from role" | OLS |
| "user-driven dynamic filters" | Dynamic RLS via USERPRINCIPALNAME |
| "data classification flow" | Sensitivity labels |
| "trusted authoritative model" | Endorsement: Certified |

## Performance

- Star schema beats snowflake.
- Avoid bidirectional filters unless required.
- Mark Date table for time intelligence.
- Replace calculated columns with measures when possible.
- Use Performance Analyzer + DAX Studio + BPA in Tabular Editor.

## Common gotchas

- Direct Lake silently falls back to DirectQuery if column count / row group size exceeded.
- Mirroring works for Azure SQL DB / Cosmos DB / Snowflake (today).
- Workspace Pro vs Fabric capacity: Fabric items require F SKU.
- Bursting and smoothing avoid throttling but only up to a point - sustained overrun -> rejection.

---

[Master Index](00-MASTER-INDEX.md)
