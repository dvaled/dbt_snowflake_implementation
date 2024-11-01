# DBT Snowflake Project

This project utilizes [dbt (Data Build Tool)](https://www.getdbt.com/) with [Snowflake](https://www.snowflake.com/) as the data warehouse to transform and organize data. The project follows a modular structure, making it easier to manage data transformations, tests, and analyses.

## Project Structure

The main folders and files in this project are as follows:
├── analyses
├── macros
│   └── pricing.sql
├── models
│   ├── marts
│   │   ├── fct_orders.sql
│   │   ├── int_order_items.sql
│   │   ├── generic_tests.yml
│   │   └── int_order_items_summary.sql
│   └── staging
│       ├── stg_tpch_line_items.sql
│       ├── stg_tpch_orders.sql
│       └── tpch_sources.yml
├── tests
│   ├── fct_orders_date_valid.sql
│   └── fct_orders_discount.sql
├── dbt_project.yml
├── package-lock.yml
└── packages.yml

### Folder Breakdown

- **analyses/**: Contains analysis files for running SQL queries or analytical scripts in the project.
- **macros/**: Custom reusable SQL functions for transformations. E.g., `pricing.sql` holds logic for price-related transformations or calculations.
- **models/**:
  - **marts/**: Contains core business logic and metrics, including fact and intermediate tables.
    - `fct_orders.sql`: Defines the fact table for orders.
    - `int_order_items.sql`: An intermediate table for order items.
    - `generic_tests.yml`: YAML configuration for reusable tests on marts.
    - `int_order_items_summary.sql`: Summarized data related to order items.
  - **staging/**: Contains raw data models to transform and prepare data from sources.
    - `stg_tpch_line_items.sql`: A staging model for line items.
    - `stg_tpch_orders.sql`: A staging model for orders.
    - `tpch_sources.yml`: YAML configuration specifying sources for data ingestion.
- **tests/**: Custom tests validating model data integrity.
  - `fct_orders_date_valid.sql`: Validates date data within `fct_orders`.
  - `fct_orders_discount.sql`: Validates discount logic in `fct_orders`.
- **dbt_project.yml**: Primary configuration file for the dbt project.
- **packages.yml**: Specifies dbt packages used in the project.


Try running the following commands:
- dbt run
- dbt test


### Resources:
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Check out [Discourse](https://discourse.getdbt.com/) for commonly asked questions and answers
- Join the [chat](https://community.getdbt.com/) on Slack for live discussions and support
- Find [dbt events](https://events.getdbt.com) near you
- Check out [the blog](https://blog.getdbt.com/) for the latest news on dbt's development and best practices

Credit Jayzern
