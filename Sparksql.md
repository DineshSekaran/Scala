# Data Frame and Spark SQL
spark is camelcase

# spark session

json--semi structured data

# Read 

Change format like json to Parquet/avro/ORC .....

val v1 = spark.read.format("json").load("file:///home/tamilboomi/Desktop/customer_data.json")

v1: org.apache.spark.sql.DataFrame = [email: string, first_name: string ... 4 more fields]

# Show

scala> v1.show(2)

+--------------------+----------+------+---+--------------+---------+
|               email|first_name|gender| id|    ip_address|last_name|
+--------------------+----------+------+---+--------------+---------+
|  knattrass0@loc.gov|    Kaspar|  Male|  1| 244.159.51.76| Nattrass|
|rnulty1@multiply.com|  Rosamund|Female|  2|237.123.21.130|    Nulty|
+--------------------+----------+------+---+--------------+---------+
only showing top 2 rows

# printSchema

scala> v1.printSchema

root
 |-- email: string (nullable = true)
 |-- first_name: string (nullable = true)
 |-- gender: string (nullable = true)
 |-- id: long (nullable = true)
 |-- ip_address: string (nullable = true)
 |-- last_name: string (nullable = true)

# Count

scala> v1.count()

res4: Long = 1000

# Size Partitions

v1.rdd.partitions.size

res6: Int = 1

# Write files

scala> v1.write.parquet("file:///home/tamilboomi/Desktop/customer_parquet")

SLF4J: Failed to load class "org.slf4j.impl.StaticLoggerBinder".
SLF4J: Defaulting to no-operation (NOP) logger implementation
SLF4J: See http://www.slf4j.org/codes.html#StaticLoggerBinder for further details.

# Spark supported files
v1.write. type tab

to add other formats add corresponding jar to spark user path

scala> v1.write.

bucketBy   csv   format   insertInto   jdbc   json   mode   option   options   orc   parquet   partitionBy   save   saveAsTable   sortBy   text



# Write/Overwrite/Append/ different files

v2.write.mode("overwrite").orc("file:///home/tamilboomi/Desktop/customer_orc")

v2.write.mode("append").orc("file:///home/tamilboomi/Desktop/customer_orc")






