# ys-pyspark

## Start

		$ workon data
		$ pip -r requirements.txt
		$ ipython profile create spark
		$ vim subl ~/.ipython/profile_spark/ipython_notebook_config.py 

''''
c.NotebookApp.port = 8888
c.NotebookApp.ip = 'localhost'
''''
		
		$ ipython notebook --profile=spark