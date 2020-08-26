# Spark Lab 1 - cluster/local mode

1. sparkpi display the content of sparkpi
    ```
    cat /usr/lib/spark/examples/src/main/python/pi.py
    ```
2. Run on a YARN cluster client mode
    ```
    /usr/bin/spark-submit \
    --class org.apache.spark.examples.SparkPi \
    --master yarn \
    --deploy-mode client \
    /usr/lib/spark/examples/jars/spark-examples.jar \
    10

    ```

3. Run on a YARN cluster Cluster mode
    ```
    /usr/bin/spark-submit \
    --class org.apache.spark.examples.SparkPi \
    --master yarn \
    --deploy-mode cluster \
    /usr/lib/spark/examples/jars/spark-examples.jar \
    10

    ```

4. Python word count running locally on 4 cores
    ```
    cd /usr/lib/spark/
    /usr/bin/spark-submit --master local[4] /usr/lib/spark/examples/src/main/python/wordcount.py 'file:///usr/lib/spark/examples/src/main/resources/people.txt'
    ```

5. Python word count hdfs
    ```
    hdfs dfs -put /usr/lib/spark/examples/src/main/resources/people.txt /user/hadoop
    hdfs dfs -ls /user/hadoop
    /usr/bin/spark-submit /usr/lib/spark/examples/src/main/python/wordcount.py /user/hadoop/people.txt

    ```

6. A simple example demonstrating Spark SQL Hive integration. Run with:
    ```
    cd /usr/lib/spark/
    ./bin/spark-submit examples/src/main/python/sql/hive.py
    ```