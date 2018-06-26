# Lab: Spark SQL

The purpose of this lab is to learn more about using Spark SQL and Spark DataFrames.

## Start your cluster

Create an EMR cluster with *Advanced Options* and the following configuration:

* Select `emr-5.12.0` from the drop-down
* Click check-boxes for these applications only: Hadoop 2.8.3, Tez 0.8.4, Hive 2.3.2, Spark 2.2.1	
* Click Next
* Edit the instance types and set 1 master and 3 core of m4.large 
* Click Next
* Give the cluster a name, and you can uncheck logging, debugging and termination protection enabled
* Click Next
* Select your key-pair
* Click "Create Cluster"

Once the cluster is in "Waiting" mode (should only take a few minutes), please `ssh` into the master. After you log-in to the master node, run the following commands in your terminal:


```
sudo yum install -y git
git clone https://github.com/bigdatateaching/spark-sql.git
cd spark-sql.git
bash post-startup-ipython-jupyter-py2-setup.sh 
```
**Note: you only need to run the startup script once! If you run it more than once, it will cause problems.**

These commands will install git, clone your repository to the master node of the cluster, and run a script that installs iPython and other Python libraries including pandas, Jupyter and starts a notebook web server. This will take a few minutes (it took about 6 minutes in testing, but your time may vary.) When the script is done you will see something like this:

```


-------------- POST STARTUP SCRIPT COMPLETE ---------------
ipython and Jupyter (running Python 2) are configured.
To access Jupyter notebook, logoff with the exit command
and log back on using agent and port forwarding:
ssh -A -L8888:localhost:8888 hadoop@...
and then open a web browser and go to http://localhost:8888
-----------------------------------------------------------



```
Once this is done, please type `exit` to logoff and then log back on, making sure you enable both ssh-agent forwarding and port forwarding:


```
ssh-add
ssh -A -L8888:localhost:8888 hadoop@...
``` 

You can then open a browser and navigate to http://localhost:8888 to see your Jupyter Notebook environment, which got started within the lab directory you cloned. 

## Lab 

The lab Jupyter notebook is [spark-sql.ipynb](spark-sql.ipynb).

**Don't forget to to terminate your cluster at the end of class!**

