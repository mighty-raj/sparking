spark-submit --help

#########################################################
 Run a Scala/Java application on a Spark cluster
#########################################################
# Run on a YARN cluster
export HADOOP_CONF_DIR=XXX

spark-submit \
    --class <classname> \
    --master yarn \
    --deploy-mode cluster \
    --supervise \
    <path_to_jar_file/jar-file-name.jar>  \
    <params-or-args>



#########################################################
 Run a Python application on a Spark cluster
#########################################################
spark-submit \
      --master yarn \
      --deploy-mode cluster \
      --supervise \
  <path_to_py_file/py-file-name.py> \
  <params-or-args>


#########################################################
 Important OPTIONAL PARAMETERS
#########################################################

    --queue <QUEUE_NAME>
    --executor-memory 20G
    --num-executors 50
    --total-executor-cores 100
    --name NAME                 A name of your application.
    --jars JARS                 Comma-separated list of jars to include on the driver
    --queue QUEUE_NAME          The YARN queue to submit to (Default: "default").
    --supervise                 If given, restarts the driver on failure.
    --executor-memory MEM       Memory per executor (e.g. 1000M, 2G) (Default: 1G).
    --driver-memory MEM         Memory for driver (e.g. 1000M, 2G) (Default: 1024M).
    --driver-java-options       Extra Java options to pass to the driver.
    --driver-library-path       Extra library path entries to pass to the driver.
    --driver-class-path         Extra class path entries to pass to the driver. Note that
                                jars added with --jars are automatically included in the
                                classpath.
                                


How to configure executors, exec mem etc: 
https://spoddutur.github.io/spark-notes/distribution_of_executors_cores_and_memory_for_spark_application.html
