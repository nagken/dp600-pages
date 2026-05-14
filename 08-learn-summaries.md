# DP-600 Microsoft Learn Path Summaries

> Condensed take-aways from official DP-600 learning paths.

## Path 1: Implement a Lakehouse with Microsoft Fabric

- Use OneLake for one logical lake; reference data with shortcuts (no copy).
- Bronze / Silver / Gold medallion drives quality.
- V-Order is default for Fabric Spark writes; pair with OPTIMIZE + VACUUM.
- Notebooks bind to a default lakehouse - mind the implicit target.

## Path 2: Implement a data warehouse with Microsoft Fabric

- Warehouse uses distributed T-SQL with multi-table transactions.
- CTAS, stored procedures, COPY INTO are the core ELT primitives.
- Statistics auto-managed but verify after large bulk loads.
- Cross-database queries supported; one logical model in OneLake.

## Path 3: Implement Real-Time Intelligence in Microsoft Fabric

- Eventstream for ingestion -> KQL DB for hot store -> Real-Time Dashboards for view.
- KQL queries are time-first: filter early on `Timestamp` to reduce scans.
- Reflexes turn KQL conditions into Power Automate / Activator triggers.

## Path 4: Implement a semantic model in Microsoft Fabric

- Star schema is the default model shape.
- Direct Lake reads Delta directly; ensure tables are V-Ordered.
- DAX `CALCULATE` is the workhorse; learn filter context.
- RLS via DAX roles + USERPRINCIPALNAME for dynamic.

## Path 5: Manage analytics development lifecycle

- Use Git integration for version control of items.
- Deployment pipelines move items dev -> test -> prod.
- Variable libraries parameterize connections per stage.
- Endorsement + sensitivity labels signal trust + classification.

---

[Master Index](00-MASTER-INDEX.md)
