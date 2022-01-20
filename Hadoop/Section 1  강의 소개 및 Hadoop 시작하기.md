# Section 1 : 강의 소개 및 Hadoop 시작하기

생성일: 2022년 1월 20일 오후 7:31
태그: Udemy_hadoop

# Hadoop 개요 및 역사

- 하둡?
    - an open source software platform for distributed storage and distributed processing of very large data sets on computer clusters built from commodity hardware
- 역사
    - 구글에서 발간한 두 논문 : GFS, Mapreduce → 하둡의 데이터 저장 방식에 영향
    - 2006년 더그 커팅과 그의 팀에 의해 본격적으로 개발 시작
- 필요성
    - 데이터의 크기가 너무 커졌음
    - Hardware적 한계를 극복하기 위해 제시

# Hadoop 생태계 개요

- Core Hadoop Ecosystem
    - HDFS 기반 저장 (GFS의 하둡 버전)
    - YARN 기반 데이터 프로세싱 (클러스터에서 작업 관리)
    - MapReduce - mapper(데이터를 병렬적으로 변환)+reducer(데이터를 종합)
    - Pig
    - Hive
    - Apache Ambari
    - Mesos
    - Spark
    - Tez
    - Apache HBASE
    - Apache Storm
    - Zookeeper
    - Sqoop, Flume, Kafka (Data Ingestion)
- Query Engines
    - Apache DRILL, Apache Phoenix, Apache Zeppelin, presto...
- External Data Storage
    - MySQL, cassandra, mongoDB