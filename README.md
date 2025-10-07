`
your-repo/
├─ README.md
├─ docs/
│  ├─ qnf/
│  │  ├─ R1.md ... R15.md
│  ├─ themes_summary.md
│  ├─ fact_type_summary.md            # Phase 4 deliverable
│  ├─ grain_per_fact.md               # Phase 5 deliverable
│  ├─ dimensions_matrix.md            # Phase 6 deliverable
│  ├─ erd_star_schema.png             # Phase 7 deliverable
│  └─ definitions_glossary.md
├─ models/                            # Logical/physical models
│  ├─ dimensions/
│  │  ├─ dim_date.sql
│  │  ├─ dim_store.sql
│  │  ├─ dim_city.sql
│  │  ├─ dim_country.sql
│  │  ├─ dim_product.sql
│  │  ├─ dim_customer.sql
│  │  └─ dim_payment_method.sql
│  ├─ facts/
│  │  ├─ fact_order.sql               # transactional
│  │  ├─ fact_sales.sql               # transactional (order line)
│  │  ├─ fact_sales_daily.sql         # periodic snapshot (derived)
│  │  ├─ fact_payment_attempt.sql     # transactional
│  │  ├─ fact_payment_method_monthly.sql  # periodic snapshot KPI
│  │  ├─ fact_customer_activity.sql   # periodic snapshot
│  │  ├─ fact_order_lifecycle.sql     # accumulating snapshot
│  │  └─ fact_inventory_monthly.sql   # periodic snapshot
│  └─ tests/
│     ├─ not_null_unique_keys.sql     # PK tests per table
│     ├─ fk_integrity_checks.sql
│     └─ metric_reconciliation.sql    # e.g., sum(fact) vs source
├─ pipelines/
│  ├─ adf/                            # Azure Data Factory JSONs (if any)
│  └─ notebooks/
│     ├─ databricks_build_dims.py
│     ├─ databricks_build_facts.py
│     └─ databricks_reconcile_checks.py
├─ seeds/                             # small CSVs for dims (date, payment methods)
│  ├─ dim_date.csv
│  └─ dim_payment_method.csv
├─ sql/
│  ├─ oltp_ddl.sql                    # you already have this
│  ├─ mock_data.sql                   # you already have this
│  ├─ staging_views.sql               # source → staging (clean types/names)
│  ├─ build_dims.sql                  # INSERT/SELECT from staging
│  ├─ build_facts.sql
│  └─ validate_qnfs.sql               # queries answering R1..R15
├─ .github/
│  └─ workflows/
│     └─ ci.yml                       # run lint/tests on PR
└─ powerbi/
   ├─ model.pbit                      # template
   └─ screenshots/
      └─ executive_dashboard.png
`
