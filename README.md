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

Follow the setup on pages 39 - 41.


4. For MAC
The best way to install the latest version of Apache Spark on
OS X and to keep it up to date is via Homebrew.

Follow the setup on pages 42 - 43.


5. For Linux
Follow the setup on page 44.



6. To test your install, start your spark-shell.



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