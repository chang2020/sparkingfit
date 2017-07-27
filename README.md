#SparkingFit

## Maintainer:  Chang Kwak:  chang2020@gmail.com



## Function
sparkingfit is a project to improve the way how people apply for a job.  It takes job requirements and resume as input and display match percentage, and predict success rate after running algorithm against big date analytics using Spark and Python. It even provide suggestions to improve resume by using best practices and suggested trainings.

Main requirements:
1) Input: processing for job description and resume in different format (i.e TXT, WORD, URL etc)
2) Database: store, query, search
3) Match rate: provide match percentage
4) Prediction: predict success rate
5) Recommendation: imporvement, training
6) UI development (Django)
7) Messaging (Kafka)

## Installation
Spark runs on Java 8+, Python 2.7+, R 3.1+ and Scala 2.11

Download and install Java
(Java Development Kit, JDK 8)
http://www.oracle.com/technetwork/java/javase/downloads/index.html

Download and install Python (I use 2.7)
https://www.python.org/downloads/

Download 7-zip to unzip .gz files (Windows)
http://www.7-zip.org/

Download R
https://www.r-project.org/
doop 2.7 does not include the required binaries (like winutils.exe) which are required to run Hadoop.
Winutils provide basic command line utilities for Hadoop on Windows.
Remember, Spark is a engine built over Hadoop.
Copy winutilities.exe from the student files to c:\winutils\bin
Create c:\TEMP\hive
Open a command prompt as administrator and type:
c:\winutils\bin>winutils.exe chmod 777 /temp/hive
This prevents the following error:
java.lang.RuntimeException: java.lang.RuntimeException: The root scratch dir: /tmp/hive on HDFS should be writable.
For Help:
C:\winutils\bin>winutils -help

Anaconda is a free Python distribution from Continuum Analytics.
Download at:
https://www.continuum.io/downloads
Anaconda install for Mac, use command line.



1. Install the prerequisites if you have not already done so.




2. Download Spark from
http://spark.apache.org/downloads.html

Choose a Spark release: 2.1.1 (May 2, 2017)
Choose a package type: Pre-built for Hadoop 2.7 and later
Choose a download type: Direct Download or Mirror
Download Spark: spark-2.1.1-bin-hadoop2.7.tgz



3. For Windows
The winutils file is in your student files. Place it in C:\winutils

Follow the setup below:

Windows Setup
Set Environment Variables (for Windows 10 see notes)
Control Panel > System and Security > System >Advanced system settings
> Environment Variables System variables
Add (use the correct paths on your computer) HADOOP_HOME
C:\winutils
JAVA_HOME (Important for 2.1.1 use Progra~1) C:\Progra~1\Java\jdk1.8.0_131
PYTHONPATH C:\Python27;C:\Python27\Scripts;
SPARK_HOME C:\apache\spark-2.1.1-bin-hadoop2.7
add to PATH
C:\Python27;%JAVA_HOME%\bin
;C:\Program Files\R\R-3.3.3\bin;%HADOOP_HOME% ;%SPARK_HOME%\bin;
then restart

Hadoop 2.7 does not include the required binaries (like winutils.exe) which are required to run Hadoop.
Winutils provide basic command line utilities for Hadoop on Windows.
Remember, Spark is a engine built over Hadoop.
Copy winutilities.exe from the student files to c:\winutils\bin
Create c:\TEMP\hive
Open a command prompt as administrator and type:
c:\winutils\bin>winutils.exe chmod 777 /temp/hive
This prevents the following error:
java.lang.RuntimeException: java.lang.RuntimeException: The root scratch dir: /tmp/hive on HDFS should be writable.
For Help:
C:\winutils\bin>winutils -help

Download spark-2.1.1-bin-hadoop2.7.tgz
Highlight spark-2.1.1-bin-hadoop2.7.tgz, right-click and choose 7-zip
Highlight spark-2.1.1-bin-hadoop2.7.tar, right-click and choose 7-zip

4. For MAC
The best way to install the latest version of Apache Spark on
OS X and to keep it up to date is via Homebrew.

Follow the setup below:

Mac OS Setup
Homebrew
The best way to install the latest version of Apache Spark on OS X and to keep it up to date is via Homebrew.
First install Homebrew, if you don’t have it:
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
Set JAVA_HOME (if not already set)
export JAVA_HOME=$(/usr/libexec/java_home)
Then install Spark with brew:
brew install apache-spark
This will install Spark to directory:
     /usr/local/Cellar/apache-spark/2.1.1/
All relevant paths were added automatically to your environment by Homebrew.
Sample Brew Commands:
$ brew update $ brew list
$ brew info apache-spark
$ brew install apache-spark
$ brew switch <formula> <version> $ brew switch apache-spark 2.1.1 $ brew switch apache-spark 0
$ brew upgrade
$ brew uninstall apache-spark



5. For Linux
Follow the setup below:
Check the Java version
$ java -version
Install Scala
$ wget http://www.scala-lang.org/files/archive/scala-2.11.tgz $ sudo mkdir /usr/local/src/scala
$ sudo tar xvf scala-2.11.tgz -C /usr/local/src/scala/
$ vi .bashrc
And add following to the end of the file
export SCALA_HOME=/usr/local/src/scala/scala-2.11 export PATH=$SCALA_HOME/bin:$PATH
restart bashrc Installing Spark
Download the Spark Pre-built for Hadoop 2.7 and later Then
tar -xvzf spark-2.1.1-bin-hadoop2.7.tgz
You can move that to wherever you like.

Linux Packages
RHEL-compatible system:
To install all Spark packages:
$ sudo yum install spark-core spark-master spark-worker spark-history-server spark-python
To install only the packages needed to run Spark on YARN:
$ sudo yum install spark-core spark-history-server spark-python
SLES system:
To install all Spark packages:
$ sudo zypper install spark-core spark-master spark-worker spark-history-server spark-python
To install only the packages needed to run Spark on YARN:
$ sudo zypper install spark-core spark-history-server spark-python
Ubuntu or Debian system:
To install all Spark packages:
$ sudo apt-get install spark-core spark-master spark-worker spark-history-server spark-python
To install only the packages needed to run Spark on YARN:
$ sudo apt-get install spark-core spark-history-server spark-python



6. To test your install, start your spark-shell.


$spark-shell

Welcome to
      ____              __
     / __/__  ___ _____/ /__
    _\ \/ _ \/ _ `/ __/  '_/
   /___/ .__/\_,_/_/ /_/\_\   version 2.1.1
      /_/

Using Scala version 2.11.8 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_111)
Type in expressions to have them evaluated.
Type :help for more information.

scala>

7. At the command line, enter println("Hello Spark")

scala> println("Hello Spark")



8. Create a variable, then an array.

scala> var counter = 0
counter: Int = 0

scala> val data = Array(1,2,3,4,5);
data: Array[Int] = Array(1, 2, 3, 4, 5)



9. Create a RDD with parallelize

scala> val distData = sc.parallelize(data)
distData: org.apache.spark.rdd.RDD[Int] =
ParallelCollectionRDD[0] at parallelize
at <console>:29



10. Use reduce to add the elements.

scala> distData.reduce((a, b) => a + b)
res0: Int = 15



11. Print a string and our variable.

scala> println("Counter value: " + counter)
Counter value: 0
