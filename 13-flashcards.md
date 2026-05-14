# DP-600 Flashcards

> Click any card to reveal the answer.

<section class="fc-section" data-fc-title="Plan implement manage">
<h2>1 - Plan implement manage</h2>

<div class="flashcard-grid">

<div class="flashcard"><div class="fc-q">What is OneLake?</div><div class="fc-a">A single tenant-wide logical data lake on ADLS Gen2; one copy of data accessible by all Fabric engines.</div></div>

<div class="flashcard"><div class="fc-q">F SKU pause - what stops being billed?</div><div class="fc-a"><strong>Compute (CU)</strong> stops; storage continues.</div></div>

<div class="flashcard"><div class="fc-q">Group workspaces for cross-team governance?</div><div class="fc-a"><strong>Domain</strong> at tenant level.</div></div>

<div class="flashcard"><div class="fc-q">Promote items dev -> test -> prod?</div><div class="fc-a"><strong>Deployment pipeline</strong> + variable libraries.</div></div>

<div class="flashcard"><div class="fc-q">Source-control items with PRs?</div><div class="fc-a"><strong>Git integration</strong> with Azure DevOps or GitHub.</div></div>

<div class="flashcard"><div class="fc-q">CU sustained overrun result?</div><div class="fc-a">First throttling, then query rejection.</div></div>

<div class="flashcard"><div class="fc-q">Highest endorsement level?</div><div class="fc-a"><strong>Certified</strong> - admin-controlled.</div></div>

</div>
</section>

<section class="fc-section" data-fc-title="Prepare and serve data">
<h2>2 - Prepare and serve data</h2>

<div class="flashcard-grid">

<div class="flashcard"><div class="fc-q">Reference S3 / ADLS without copying?</div><div class="fc-a"><strong>OneLake shortcut</strong>.</div></div>

<div class="flashcard"><div class="fc-q">Continuous mirror of Azure SQL DB?</div><div class="fc-a"><strong>Mirroring</strong> - zero-ETL CDC into OneLake Delta.</div></div>

<div class="flashcard"><div class="fc-q">Best for big data + files + Spark?</div><div class="fc-a"><strong>Lakehouse</strong>.</div></div>

<div class="flashcard"><div class="fc-q">Best for T-SQL multi-table transactions?</div><div class="fc-a"><strong>Warehouse</strong>.</div></div>

<div class="flashcard"><div class="fc-q">Best for time-series telemetry?</div><div class="fc-a"><strong>Eventhouse / KQL Database</strong>.</div></div>

<div class="flashcard"><div class="fc-q">Compact small Delta files?</div><div class="fc-a"><strong>OPTIMIZE</strong> (then VACUUM for tombstones).</div></div>

<div class="flashcard"><div class="fc-q">Microsoft Parquet optimized write order?</div><div class="fc-a"><strong>V-Order</strong>.</div></div>

<div class="flashcard"><div class="fc-q">Low-code transform GUI?</div><div class="fc-a"><strong>Dataflow Gen2</strong>.</div></div>

</div>
</section>

<section class="fc-section" data-fc-title="Semantic models">
<h2>3 - Semantic models</h2>

<div class="flashcard-grid">

<div class="flashcard"><div class="fc-q">Read Delta directly into VertiPaq?</div><div class="fc-a"><strong>Direct Lake</strong> mode.</div></div>

<div class="flashcard"><div class="fc-q">Direct Lake fallback condition?</div><div class="fc-a">Falls back to DirectQuery silently when column count or row group size limits exceeded.</div></div>

<div class="flashcard"><div class="fc-q">Most powerful DAX function?</div><div class="fc-a"><strong>CALCULATE</strong> - modifies filter context.</div></div>

<div class="flashcard"><div class="fc-q">Filter rows by user identity?</div><div class="fc-a">Dynamic <strong>RLS</strong> via <code>USERPRINCIPALNAME()</code>.</div></div>

<div class="flashcard"><div class="fc-q">Hide columns from a role?</div><div class="fc-a"><strong>Object-Level Security (OLS)</strong>.</div></div>

<div class="flashcard"><div class="fc-q">Default model shape?</div><div class="fc-a"><strong>Star schema</strong>.</div></div>

<div class="flashcard"><div class="fc-q">Reusable time-intelligence pattern?</div><div class="fc-a"><strong>Calculation group</strong>.</div></div>

<div class="flashcard"><div class="fc-q">Tool for DAX query plans?</div><div class="fc-a"><strong>DAX Studio</strong>.</div></div>

</div>
</section>

<section class="fc-section" data-fc-title="Explore and analyze">
<h2>4 - Explore and analyze</h2>

<div class="flashcard-grid">

<div class="flashcard"><div class="fc-q">Best language for ad-hoc warehouse joins?</div><div class="fc-a"><strong>T-SQL</strong>.</div></div>

<div class="flashcard"><div class="fc-q">Best language for telemetry?</div><div class="fc-a"><strong>KQL</strong>.</div></div>

<div class="flashcard"><div class="fc-q">KQL function for time-series with binning?</div><div class="fc-a"><code>summarize ... by bin(Timestamp, 5m)</code> or <code>make-series</code>.</div></div>

<div class="flashcard"><div class="fc-q">Generate measure from prompt?</div><div class="fc-a"><strong>Copilot in Power BI</strong>.</div></div>

<div class="flashcard"><div class="fc-q">Built-in driver analysis visual?</div><div class="fc-a"><strong>Key Influencers</strong> visual.</div></div>

<div class="flashcard"><div class="fc-q">KQL forecasting function?</div><div class="fc-a"><code>series_decompose_forecast</code>.</div></div>

</div>
</section>

<section class="fc-section" data-fc-title="Performance and pitfalls">
<h2>5 - Performance and pitfalls</h2>

<div class="flashcard-grid">

<div class="flashcard"><div class="fc-q">Bidirectional filter risk?</div><div class="fc-a">Ambiguous paths -> wrong totals or model warnings.</div></div>

<div class="flashcard"><div class="fc-q">Why mark a Date table?</div><div class="fc-a">Time-intelligence functions require it; otherwise wrong results.</div></div>

<div class="flashcard"><div class="fc-q">Calculated column vs measure?</div><div class="fc-a">Prefer <strong>measures</strong> when possible; calc columns sit in memory.</div></div>

<div class="flashcard"><div class="fc-q">Auto date hierarchies issue?</div><div class="fc-a">Bloat model with hidden tables; disable in options.</div></div>

<div class="flashcard"><div class="fc-q">Notebook attaching to wrong lakehouse?</div><div class="fc-a">Default lakehouse binding inherits from session - set explicitly per cell.</div></div>

<div class="flashcard"><div class="fc-q">KQL query without time filter?</div><div class="fc-a">Scans full retention - very expensive. Always filter on timestamp.</div></div>

</div>
</section>

---

[Master Index](00-MASTER-INDEX.md)
