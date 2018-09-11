hadoop-examples
===============
Some examples for learning hadoop

### Build
mvn clean package

### Run

1. Copy the JAR to remote machine
```
scp hadoop-examples-1.0-SNAPSHOT.jar root@centos-7-101:/home/hadoop/test/
```

2. Prepare input
```
hadoop fs -mkdir /input
hadoop fs -put LICENSE.txt /input
hadoop fs -ls /input
```

3. Submit job
```
hadoop jar hadoop-examples-1.0-SNAPSHOT.jar com.liusenhua.hadoop.WordCount /input /output
```

4. Check result
-   Check data
```
hadoop fs -ls /output
hadoop fs -cat /output/part-r-00000
```
-   Check jobs status: http://centos-7-101:19888/jobhistory/app

