# Spark 




# Spark Context 
gives you entry point to sprak session

# Spark Session

Whatever we do spark session is created,all the codes are executed here.


Start Spark-shell

scala> val rangeA=spark.range(100).toDF("numbers");
rangeA: org.apache.spark.sql.DataFrame = [numbers: bigint]

scala> rangeA.collect()

res0: Array[org.apache.spark.sql.Row] = Array([0], [1], [2], [3], [4], [5], [6], [7], [8], [9], [10], [11], [12], [13], [14], [15], [16], [17], [18], [19], [20], [21], [22], [23], [24], [25], [26], [27], [28], [29], [30], [31], [32], [33], [34], [35], [36], [37], [38], [39], [40], [41], [42], [43], [44], [45], [46], [47], [48], [49], [50], [51], [52], [53], [54], [55], [56], [57], [58], [59], [60], [61], [62], [63], [64], [65], [66], [67], [68], [69], [70], [71], [72], [73], [74], [75], [76], [77], [78], [79], [80], [81], [82], [83], [84], [85], [86], [87], [88], [89], [90], [91], [92], [93], [94], [95], [96], [97], [98], [99])



# RDD
Immutable/Recovery Quickly and Distributed Data set. Partitioned

sc.parallelize(Seq(1,2,3,4,5,6))

res(may variy).collect()

sc.parallelize(Seq(1,2,3,4,5,6),2)

.collect()

# Immutable
RDD itself immutable but still we can use var bt recommended to use val bec of RDD
RDD content cannnot be changed.
Val a=5

a=6    we cannot change a=6 on RDD which is immutable


# Transformation

Lazy operation Tranformation will not be executed (wont execute untill action is performed)

on memory processing 

where(filter)/Modify 


# Action

Execution of transformation

Save to file/ print on terminal/count/sum .......
