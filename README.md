# tpcds-Spark

根据 https://github.com/brownsys/tpcds


1.  git clone https://github.com/brownsys/tpcds.git

2. 编译出错1 - 方案 pom.xml 里面的 maven-plugin-java 1.8 改成1.7
3. To compile, invoke

	mvn clean package

4. For convenience, set TPCDS_WORKLOAD_GEN to the directory where this git repository is checked out, eg:

    export TPCDS_WORKLOAD_GEN=~/tpcds

5. To generate data with spark

	bin/spark-submit --class edu.brown.cs.systems.tpcds.spark.SparkTPCDSDataGenerator ${TPCDS_WORKLOAD_GEN}/target/spark-workloadgen-4.0-jar-with-dependencies.jar
	
6. 编译出错2 - using Spark 1.6 and deploying it on Spark 2.0 cluster 继续修改 pom.xml 或者 change dependency version to 2.0 or change cluster version to < 2.0

7. To run:

	bin/spark-submit --class edu.brown.cs.systems.tpcds.spark.SparkTPCDSWorkloadGenerator ${TPCDS_WORKLOAD_GEN}/target/spark-workloadgen-4.0-jar-with-dependencies.jar