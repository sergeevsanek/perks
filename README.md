# perks
Перекодирует все файлы в текущем каталоге в нужную кодировку:

`find . -name '*.php' -exec enconv -L russian -i -x utf-8 {} ';'`

Очистить таблицу в clickhouse (поменять tmp на db_name.table_name)

`table=tmp; create=`clickhouse-client --query="SHOW CREATE TABLE $table" | tr -d '\\'`; clickhouse-client --query="DROP TABLE $table"; clickhouse-client --query="$create"`
