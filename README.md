一个正在学习大数据开发的普通学生
HDFS简介（Hadoop中三大件之一，主要是起到存储功能）
  1.概述（了解）
    1.1 产生背景
    1.2 HDFS定义
        HDFS是一个分布式文件系统，用来存储文件，通过目录树结构来定位文件
        HDFS使用场景：适合一次写入，多次读出，不支持文件修改，适合用来做数据分析，不适合用来做网盘
    1.3 优缺点
        1.3.1 优点：1）高容错性
                    2）适合处理大数据
                    3）可以部署在廉价机器上，通过多副本机制，提高可靠性
        1.3.2 缺点：1）不适合低延时数据访问
                    2）无法高效对大量小文件进行存储（因为小文件太多会占用太多的NameNode，从而导致内存不                          够）
                    3）不不支持并发写入，文件随机修改（仅支持追加append）
     1.4 HDFS组成架构（重要）
          					
![Snipaste_2021-09-07_14-02-17](https://user-images.githubusercontent.com/32889586/132292300-1039e166-7eb2-42b7-96e9-df1c17bae963.jpg)

![Snipaste_2021-09-07_14-12-11](https://user-images.githubusercontent.com/32889586/132293239-3653a1a1-8505-4c05-ae4a-047e6babcdc6.jpg)

	
其实可以理解为NameNode是主管，管理不同工人workers即DataNode,一天客户（Client）来谈生意打算存储自己的东西（上传），首先和主管交流，然后主管叫来工人，带领客户去仓库（相当于DateNode中Block操作）存放东西（Write），并记录好东西的信息，又因为考虑到安全，所以在不同仓库（2个到3个）又分别存储一份，存放完毕后，当客户想来取东西的时候（下载）（DownLoad），又要先和主管交流，主管在去叫工人带他去存放数据的仓库取出东西（Read）


注意：Block分块操作一般是是128M（与磁盘存储性能相关），这个不是实际磁盘空间，只是一个参数，如果存放的东西超过128M，就进行切块，分别储存，如果不足128M，就实际占用多少就分多少

  2.HDFS中的Shell操作（重点）
		
  3.HDFS客户端API操作（较为重要）
  4.HDFS中的读写过程、步骤(面试重点)
    4.1 HDFS数据流
      4.1 HDFS写数据流程
      4.2 HDFS读数据流程
    4.2 NameNode和SecondaryNameNode
    4.3 DateNode
  
