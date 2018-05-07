# psdevsparkappscalacloudra

```
service cloudra-scm-server stop
service cloudra-scm-agent stop
```

```
yum clean all
yum upgrade cloudra-manager-server cloudra-manager-daemons cloudra-manager-agent
```

## 5. Understanding Spark
### 5 How Word Count Works
```
val lines = sc.textFile("file://")
val words = lines.flatMap(line=>line.split(" "))
val word_for_count = words.map(x=>(x,1))
word_for_count.reduceByKey(_+_).collect()
