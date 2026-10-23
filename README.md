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

