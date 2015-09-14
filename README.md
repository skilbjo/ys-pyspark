# ys-pyspark

## Start
Create your `virtualenv` profile, install libraries:

````shell
$ workon data
$ pip -r requirements.txt
$ ipython profile create spark
$ vim subl ~/.ipython/profile_spark/ipython_notebook_config.py 
````

````python
c.NotebookApp.port = 8888
c.NotebookApp.ip = 'localhost'
````

## Add the env variables to your `PATH` 
````bash
$ vim ~/.bash_profile

### Apache Spark
if which java > /dev/null; then export JAVA_HOME=$(/usr/libexec/java_home); fi

if which pyspark > /dev/null; then
	export SPARK_HOME="/usr/local/Cellar/apache-spark/1.5.0/libexec/"
	export PYSPARK_SUBMIT_ARGS="--master local[2] pyspark-shell"
fi

# Spark / iPython
# Add the PySpark classes to the Python path:
export PYSPARK_SUBMIT_ARGS="--master local[2] pyspark-shell"
export PYTHONPATH=$SPARK_HOME/python/:$PYTHONPATH
export IPYTHON_OPTS="notebook" pyspark
export PYTHONPATH=$SPARK_HOME/python/lib/py4j-0.8.2.1-src.zip:$PYTHONPATH

alias hstart="/usr/local/Cellar/hadoop/2.7.1/sbin/start-dfs.sh;/usr/local/Cellar/hadoop/2.7.1/sbin/start-yarn.sh"
alias hstop="/usr/local/Cellar/hadoop/2.7.1/sbin/stop-yarn.sh;/usr/local/Cellar/hadoop/2.7.1/sbin/stop-dfs.sh"

````
		
## Start the notebook!
````
		$ ipython notebook --profile=spark
````