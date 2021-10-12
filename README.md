# ADP-to-BigQuery
How to convert schemas: ADP API JSON -> BigQuery DDL

Note: the .ipynb and .py files contain the same script; just including both in case one is easier to work with for you than the other. The .ipynb is nice because you can see the output from my example run to see the ADP schema and resulting BigQuery DDL.

1. Get the ADP API schema from the ADP API docs by going to
   [ADP Developer Resources](https://developers.adp.com/articles/api/all) which has documentation for all their APIs.
   From there, click on the API you’d like, then click on `Examples`, and then scroll down to find the `Model Schema`.
   Copy-paste this JSON. You will use this JSON in the .ipynb notebook.
2. Within the .ipynb notebook:
    1. Take the schema you copied from the ADP API docs and paste it in the Python cell under the `ADP schema` section. Leave the `true = True` and `false = False`, though, because the booleans in the JSON response are unquoted. Save this JSON as a Python variable called `adp_schema_json`. 
    2. Under the `Define BQ Destination Parameters` section, replace `destination_dataset` and `destination_table` with your own strings. The strings will be used in the `CREATE TABLE` command to tell BigQuery in which dataset to create the table and with what table name.
    3. Now save your notebook and go up to `Runtime` → `Run all`, which will run all the cells in the notebook. Scroll down to the `Convert the schema` section, and you will see the printed-out BigQuery DDL schema. Copy-paste the schema and do what you’d like with it!