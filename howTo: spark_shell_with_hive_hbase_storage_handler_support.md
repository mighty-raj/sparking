
To access hive tables with HBase storage handler in spark-shell(scala mode), lauch spark-shell as below:


`export LIBJARS=$(hbase mapredcp | tr ':' ','),<<path-to-hbase-site.xml>>/hbase/conf,<<path-to-hadoop-site-xml-files>>/hadoop/conf,<<path-to-hive-hbase-handler>>/hive-hbase-handler.jar`


Example:
-------
`export LIBJARS=$(hbase mapredcp | tr ':' ','),/etc/hbase/conf,/etc/hadoop/conf,/usr/hdp/current/hive-client/lib/hive-hbase-handler.jar`

`spark-shell --jars $LIBJARS`


Once you enter spark-shell command line (scala), you should be able to access hive table with hbase storage handler, as simple as any other hive table you access.


Example:
-------
``
val  x = spark.table("<hive_db_name>:<hive_tbl_name>")
``