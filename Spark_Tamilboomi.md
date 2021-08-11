#  Find out how many people visited countdown page

val Input_FileRDD = sc.textFile("file:///home/tamilboomi/Desktop/Nasa_Webserver_log.tsv")
Input_FileRDD: org.apache.spark.rdd.RDD[String] = file:///home/tamilboomi/Desktop/Nasa_Webserver_log.tsv MapPartitionsRDD[1] at textFile at <console>:24

scala> Input_FileRDD.partitions.size
res0: Int = 5

scala> Input_FileRDD.mapPartitionsWithIndex((idx, iter) => if (idx == 0) iter else Iterator()).count
res1: Long = 421395                                                             

scala> Input_FileRDD.count
res2: Long = 1891710                                                            

scala> Input_FileRDD.first
res3: String = host	logname	time	method	url	response	bytes	referer	useragent

scala> Input_FileRDD.take(2)
res4: Array[String] = Array(host	logname	time	method	url	response	bytes	referer	useragent, "199.72.81.55	-	804571201	GET	/history/apollo/	200	6245		")
