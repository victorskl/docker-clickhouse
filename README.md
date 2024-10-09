# ClickHouse

Column-oriented OLAP DBMS 

- https://github.com/ClickHouse/ClickHouse
- https://clickhouse.com/docs/en/install
- https://hub.docker.com/r/clickhouse/clickhouse-server/

```
docker compose up -d
docker compose ps -a
docker compose logs
```

## Client

### HTTP Interface

- https://clickhouse.com/docs/en/interfaces/http
- http://localhost:8123/play

```
echo "SELECT 'Hello, ClickHouse!'" | curl 'http://localhost:8123/?query=' --data-binary @-
```

```
echo 'SELECT 1 FORMAT Pretty' | curl 'http://localhost:8123/?' --data-binary @-
```

### CLI

- https://clickhouse.com/docs/en/interfaces/cli

```
docker compose exec -it clickhouse clickhouse-client
```

```
2898c3cd1177 :) show databases

SHOW DATABASES

Query id: 53f4b947-bf2d-4f62-804e-7de2dd5cf6d0

   ┌─name───────────────┐
1. │ INFORMATION_SCHEMA │
2. │ default            │
3. │ docker             │
4. │ information_schema │
5. │ system             │
   └────────────────────┘

5 rows in set. Elapsed: 0.004 sec.
```

```
2898c3cd1177 :) select version()

SELECT version()

Query id: d1b05355-fa45-4c2f-9dd0-759e4712d582

   ┌─version()─┐
1. │ 24.9.2.42 │
   └───────────┘

1 row in set. Elapsed: 0.003 sec.
```

```
2898c3cd1177 :) select 1

SELECT 1

Query id: d96ed7a3-a7c2-46aa-9135-05eec1ff868e

   ┌─1─┐
1. │ 1 │
   └───┘

1 row in set. Elapsed: 0.002 sec.
```

```
2898c3cd1177 :) exit
Bye.
```
