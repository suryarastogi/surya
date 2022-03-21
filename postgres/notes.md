# Postgres notes

## Detect Query holding the lock/causing blocking
https://stackoverflow.com/questions/26489244/how-to-detect-query-which-holds-the-lock-in-postgres
``` psql
select pid, 
       usename, 
       pg_blocking_pids(pid) as blocked_by, 
       query as blocked_query
from pg_stat_activity
where cardinality(pg_blocking_pids(pid)) > 0;
```
