# DP-600 Glossary

| Term | Definition |
|---|---|
| **OneLake** | Tenant-wide logical data lake; physically ADLS Gen2 under the hood. |
| **Workspace** | Container for Fabric items; assigned to a capacity. |
| **Domain** | Tenant-level grouping of workspaces for governance. |
| **Capacity (F SKU)** | Reserved compute pool measured in CUs. |
| **CU (Capacity Unit)** | Billing unit for Fabric capacity. |
| **Bursting** | Short-term exceeding CU allowance. |
| **Smoothing** | 24h averaging of CU consumption. |
| **Lakehouse** | Spark-first store with files + Delta tables. |
| **Warehouse** | T-SQL distributed analytical DB with multi-table transactions. |
| **Eventhouse** | Container for KQL Databases for time-series telemetry. |
| **KQL DB** | Kusto Query Language database; queryable in seconds. |
| **Eventstream** | Real-time ingestion router (Event Hubs, IoT, Kafka). |
| **Real-Time Dashboard** | KQL-driven streaming dashboard. |
| **Reflex / Activator** | Trigger Power Automate or alerts on KQL conditions. |
| **Shortcut** | Reference in OneLake to external storage; no data copy. |
| **Mirroring** | Continuous CDC mirror of Azure SQL / Cosmos / Snowflake to OneLake. |
| **Medallion** | Bronze (raw) -> Silver (cleansed) -> Gold (curated) data layout. |
| **V-Order** | Microsoft-specific Parquet write order optimized for VertiPaq. |
| **Z-Order** | Multi-dim clustering inside Parquet files. |
| **OPTIMIZE / VACUUM** | Delta Lake commands to compact files / clean tombstones. |
| **Direct Lake** | Power BI mode reading Delta directly into VertiPaq. |
| **DirectQuery** | Live query mode against the source. |
| **Import** | In-memory cached mode. |
| **Composite** | Mixed Import + DirectQuery model. |
| **Semantic model** | Power BI tabular model on Fabric. |
| **DAX** | Data Analysis Expressions, language for measures. |
| **CALCULATE** | DAX function modifying filter context. |
| **RLS** | Row-Level Security via DAX role filter. |
| **OLS** | Object-Level Security hiding columns / tables. |
| **Endorsement** | Promoted / Certified label on Fabric items. |
| **Sensitivity label** | M365 classification flowing through Fabric. |
| **Dataflow Gen2** | Power Query Online -> Lakehouse / Warehouse / KQL DB. |
| **Data pipeline** | Orchestration with activities and dependencies. |
| **Notebook** | PySpark / Spark SQL / Scala / R authoring surface. |
| **Star schema** | Fact + dimension modeling shape. |
| **Calculation group** | Reusable measure modifier (e.g., time intel). |
| **Field parameter** | Dynamic axis or measure switch in visuals. |
| **Performance Analyzer** | Power BI Desktop tool capturing visual timings. |
| **DAX Studio** | External tool for DAX query plans + server timings. |
| **BPA** | Best Practice Analyzer in Tabular Editor. |
| **Git integration** | Workspace<->Azure DevOps / GitHub repo sync. |
| **Deployment pipeline** | Stage-based promotion (Dev / Test / Prod). |
| **Variable library** | Stage-specific parameter set used across items. |

---

[Master Index](00-MASTER-INDEX.md)
