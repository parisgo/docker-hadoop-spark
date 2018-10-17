## **How to use this project ?**
1: Build two images 

    docker build -t myos6 .
    docker build -t myos6-hadoop-spark .

2: Check all images

    docker images

![enter image description here](https://raw.githubusercontent.com/parisgo/docker-hadoop-spark/master/docs/images/Capture01.png) 

3: Start container

    docker-compose up -d

![enter image description here](https://raw.githubusercontent.com/parisgo/docker-hadoop-spark/master/docs/images/Capture02.png)

4: Format name node (at first time only)

    docker-compose exec hadoop-spark-master hdfs namenode -format
![enter image description here](https://raw.githubusercontent.com/parisgo/docker-hadoop-spark/master/docs/images/Capture03.png)

5: Start dfs 

    docker-compose exec hadoop-spark-master start-dfs.sh       
![enter image description here](https://raw.githubusercontent.com/parisgo/docker-hadoop-spark/master/docs/images/Capture04.png)
 
 6: Start yarn     

    docker-compose exec hadoop-spark-master start-yarn.sh      
![enter image description here](https://raw.githubusercontent.com/parisgo/docker-hadoop-spark/master/docs/images/Capture05.png)

7: Start spark     

    docker-compose exec hadoop-spark-master start-all.sh
![enter image description here](https://raw.githubusercontent.com/parisgo/docker-hadoop-spark/master/docs/images/Capture06.png)

8: Check service status

    docker-compose exec hadoop-spark-master jps
    docker-compose exec hadoop-spark-slave1 jps

![enter image description here](https://raw.githubusercontent.com/parisgo/docker-hadoop-spark/master/docs/images/Capture07.png)
    
9: We can check also all services by web    
[http://localhost:50070](http://localhost:50070)
![enter image description here](https://raw.githubusercontent.com/parisgo/docker-hadoop-spark/master/docs/images/Capture08.png)   
[http://localhost:8088](http://localhost:8088)
![enter image description here](https://raw.githubusercontent.com/parisgo/docker-hadoop-spark/master/docs/images/Capture09.png)   
[http://localhost:8080](http://localhost:8080)
![enter image description here](https://raw.githubusercontent.com/parisgo/docker-hadoop-spark/master/docs/images/Capture10.png)