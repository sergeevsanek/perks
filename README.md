# perks
Перекодирует все файлы в текущем каталоге в нужную кодировку:

`find . -name '*.php' -exec enconv -L russian -i -x utf-8 {} ';'`

Очистить таблицу в clickhouse (поменять tmp на db_name.table_name)

```
table=tmp; create=`clickhouse-client --query="SHOW CREATE TABLE $table" | tr -d '\\'`; clickhouse-client --query="DROP TABLE $table"; clickhouse-client --query="$create"
```

Показать реальные размеры таблиц
```
SELECT table, round(sum(bytes) / 1024/1024/1024, 2) as size_gb
FROM system.parts
WHERE active
GROUP BY table
ORDER BY size_gb DESC
```
