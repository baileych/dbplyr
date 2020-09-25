# queries translate correctly

    Code
      mf %>% head()
    Output
      <SQL>
      SELECT *
      FROM (`df`) 
      FETCH FIRST 6 ROWS ONLY

# generates custom sql

    Code
      sql_table_analyze(con, ident("table"))
    Output
      <SQL> ANALYZE TABLE `table` COMPUTE STATISTICS

---

    Code
      sql_query_explain(con, sql("SELECT * FROM foo"))
    Output
      <SQL> EXPLAIN PLAN FOR SELECT * FROM foo;
      SELECT PLAN_TABLE_OUTPUT FROM TABLE(DBMS_XPLAN.DISPLAY()));
