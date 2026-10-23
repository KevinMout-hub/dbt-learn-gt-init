# Marts
- Used in BI Tool.

# Staging
- How we wish the data structure looks like.

# Sources
- A handshake between the raw data and your data platform.
- Is database name changes, you only have to replace it in _src_**.yaml file.

# dbt code-gen package
- This will generate src YAML files.
For src:
`dbtf run-operation generate_source --args '{"schema_name": "jaffle_shop", "database_name": "raw"}'`

For staging model:
`dbtf run-operation generate_base_model --args '{"source_name": "jaffle_shop", "table_name": "customers"}'`


# packages
`dbtf deps`
- This downloads the packages in packages.yml

# Tests
- `dbtf test`

- Singular tests
    - for a specific model, these are not yaml files like generic tests. You utilize tests folder.
    - `dbtf test --select stg_stripe__payments` for a specific model

- Source testing
- `dbtf test -s source:jaffle_shop`

- *IMPORTANT: freshness feels like a test, but it isn't*

- *RULE OF THUMB* -->
    - Test sources for data integrity.
    - Test models for data transformations.

# Build

- dbt build is to run and test your dbt in a smart, integrated way.
    - runnning stage by stage.
    - `dbt run` transforms and builds models in your warehouse
    - `dbt test` validates your data for quality issues
    - `dbt seed` load CSV data into your warehouse tools
    - `dbt snapshot` tracks slowly changing dimensions in your data