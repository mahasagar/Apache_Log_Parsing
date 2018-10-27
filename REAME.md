## Apache Log Parsing

** Write spark code to find out top 5 hosts / IP making the request along with count (This information will help company to find out locations where website is popular or to figure out potential DDoS attacks)**

**Sample output**

(136.243.5.215,408)

(67.171.67.235,385)



**Install sbt**


```
echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list

sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2EE0EA64E40A89B84B2DF73499E82A75642AC823

sudo apt-get update

sudo apt-get install sbt
```


**Script to Setup Project**
```
mkdir -p src/{main,test}/{java,resources,scala}

mkdir lib project target


echo 'name := "SparkApplication_Apache_Log_Parsing"

version := "1.0"

scalaVersion := "2.10.4"' > build.sbt
```

- Code : 

src/main/scala/log_parse.scala

Dataset is located in current directory( access.log.10.gz )


- Build 
```
 sbt compile
 
 sbt package
 ```
 
 - Run
 ```
 spark-submit target/scala-2.10/apache-log-parsing_2.10-1.0.jar EntryPoint 10 access.log.10.gz 
```
