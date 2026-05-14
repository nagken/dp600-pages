# DP-600 Hands-On Labs

> Practical exercises in a Fabric trial or Pay-As-You-Go capacity.

## Lab 1: Provision capacity + workspace

1. Create an F2 capacity in Azure portal (or use Fabric trial).
2. Create a workspace `dp600-lab` and assign to the capacity.
3. Create a domain `Analytics` and add the workspace.
4. Add a sensitivity label to the workspace default classification.

## Lab 2: Lakehouse + medallion

1. Create a Lakehouse `lh_demo`.
2. Upload sample CSV to `Files/landing/`.
3. Create a notebook that reads CSV -> writes Delta `Tables/bronze_sales`.
4. Create a second notebook that cleans bronze -> writes `Tables/silver_sales` with V-Order.
5. Run `OPTIMIZE silver_sales` and verify file count drops.

## Lab 3: Mirroring Azure SQL DB

1. Create / use an Azure SQL DB with sample tables.
2. In Fabric, create a Mirrored Database; pick the Azure SQL DB.
3. Pick the tables to mirror; let initial snapshot finish.
4. From the SQL endpoint of the mirrored DB, query a table.
5. Update a row in the source -> verify it lands in OneLake within minutes.

## Lab 4: Direct Lake semantic model

1. From the Lakehouse SQL endpoint, build a Default Semantic Model on `silver_sales`.
2. Mark a Date table.
3. Add a measure: `Sales YTD = TOTALYTD(SUM(silver_sales[Amount]), 'Date'[Date])`.
4. Build a report; check Performance Analyzer.
5. Force a fallback query (load a wide column) and observe DirectQuery in Storage Engine timings.

## Lab 5: Real-Time Intelligence

1. Create an Eventhouse and a KQL Database.
2. Create an Eventstream that ingests from a sample source.
3. KQL: `summarize count() by bin(Timestamp, 1m)` and render as timechart.
4. Build a Real-Time Dashboard tile from the query.
5. Add a Reflex that triggers on `count > 100`.

## Lab 6: Git + deployment pipeline

1. Connect the workspace to an Azure DevOps repo.
2. Commit current items; verify item folders in repo.
3. Create a deployment pipeline with Dev / Test / Prod stages.
4. Add a variable library with `WAREHOUSE_NAME` per stage.
5. Deploy Dev -> Test; verify variable substitution.

## Lab 7: RLS + endorsement

1. Add an `Region` table to the model.
2. Create RLS role: `[Region] = LOOKUPVALUE(SecurityMap[Region], SecurityMap[User], USERPRINCIPALNAME())`.
3. Test as role -> verify filter applies.
4. Endorse the model as Promoted, then Certified (admin).

---

[Master Index](00-MASTER-INDEX.md)
