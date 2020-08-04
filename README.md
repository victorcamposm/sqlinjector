# sqlinjector
A tool to exploit Boolean-based Blind SQL injections in PostgreSQL.
It allows to extract columns of one/several tables and dump the content of them.

Pending:
- Dump database names
- Dump table names
- Extend funcitionality to Time-based SQLi
- Add MySQL support
- Add multithreading

Example:
--------
*This will perform the following query: SELECT (user_table_cols) FROM dummy_db.users WHERE user_modified='John'
```bash
python sqli.py -D dummy_db -T users -FF user_table_cols.txt -W "user_modified='John'" -R request.sql --dump
```

*This will show the columns tables of the table user of the current database
```bash
python sqli.py -T users -R request.sql --cols
```

*This will show the columns tables of the tables specified in the file, of the current database
```bash
python sqli.py -TF table_names.txt -R request.sql --cols
```