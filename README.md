# microservice3
Here is the pdf file of the process
[microservice3.pdf](https://github.com/Jinping4038/microservice3/files/10691809/microservice3.pdf)

Create a new python file microservice3:
![image](https://user-images.githubusercontent.com/122847154/217695508-a8762cda-202d-46d0-89c5-8ffc492fdd23.png)

Run microservice2 python file:
![image](https://user-images.githubusercontent.com/122847154/217695562-6cccf164-fbf3-4bfe-85ca-5d3dbdbbe55c.png)

Check the address:
![image](https://user-images.githubusercontent.com/122847154/217695624-f97b3846-a492-4066-b8ea-743554eb8f60.png)

Go to Microservice2 directory: cd ~/Desktop/Microservice2 
Run microservice3: Python3.10 microservice3.py
![image](https://user-images.githubusercontent.com/122847154/217695706-1b64c05e-739e-4d82-afa2-2203c44ef8b3.png)

Build image: docker build -t microservice3:1.0 .
![image](https://user-images.githubusercontent.com/122847154/217695744-83f63d50-35d2-4055-8eb8-534c183b47e6.png)

Run microservice2 by using container.
cd ~/Desktop/Microservice2/Df 
Python3.10 microservice2.py
docker build -t microservice2:1.0 .
![image](https://user-images.githubusercontent.com/122847154/217695784-622a7d92-cdc0-4a3a-aa00-6e49237f451e.png)
![image](https://user-images.githubusercontent.com/122847154/217695834-cd7211d0-f7bc-4dc1-9462-2a31de82f0b2.png)

docker network create network1
Get the docker network list: docker network ls
![image](https://user-images.githubusercontent.com/122847154/217695865-461d00a0-bb77-4069-b01e-266a0d73dc78.png)

Run microservice2 and microservice3 in same network1:
docker run -d -p 8001:8001 --network network1 microservice2:1.0
docker run -d -p 8000:8000 --network network1 microservice3:1.0

so view the running container:
docker logs 483e12592682
docker logs 1bde350ade91 
![image](https://user-images.githubusercontent.com/122847154/217695887-7afb8b06-bdba-4a00-bb59-62a9157de6b7.png)

tag the docker image and push into docker hub:
docker tag microservice3:1.0 jinping4038/microservice3
docker push jinping4038/microservice3
docker pull jinping4038/microservice3
docker run -d -p8000:8000 jinping4038/microservice3
![image](https://user-images.githubusercontent.com/122847154/217695905-8e19339d-0dba-4cc4-9970-d849126d98f1.png)
![image](https://user-images.githubusercontent.com/122847154/217695918-5042057e-ccf4-4008-afdf-b30a774c4b1a.png)

Here is the link of the docker image in dockerhub:
https://hub.docker.com/repository/docker/jinping4038/microservice3/general
