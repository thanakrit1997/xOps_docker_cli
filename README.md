# Use Docker Commands Fundamental :whale:
Docker command in common life
| **command** | **description** |
| - | - |
| docker login -u <--username--> -p <--password--> | Login local. |
| docker logout | Logout on local.|
| docker images | Show image on local. |
| docker ps | show docker run |
| docker ps -a  | show history docker run |
| docker log | show log container |
| | EX. docker log < container name or container id > |
| docker inspect | show detail container |
| docker exec | connect console container |
| | EX. docker exec -it < container id or container name > bash |
| docker pull <--image:version--> | - example : docker pull nginx:1.21.6-perl |
| | - ** docker pull image // Use image not specify version, image pull version latest to use. |
| docker push <account_docker>/<image_name> | push image to Docker registry |
| | EX. docker push thanakrit101/nginx:test-1.1.1 |
| docker run | Run docker container |
| | parameter use run docker |
| | -d // run docker background |
| | -e // set Environment docker, check image use Environment. |
| | -p // set port Container client connect to Docker hosts. |
| | -v // Mount Volume local to Container |
| | EX. docker run -d -p 8080:80 --name nginx-web nginx |
| docker build | build image docker |
| | docker build -t <set image name>:<version> <ที่อยู่ของ Dockerfile หรือใช้ " . " ได้แต่ต้องเข้าไปใน โฟลเดอร์ที่เราสร้าง dockerfile ไว้> |
  
# Dockerfile Detail Fundamental

* FROM = เป็นการระบุตัว base image ที่เราต้องการนำมาใช้
* MAINTAINER = ระบุชื่อของผู้ดูแล
* RUN = ระบุคำสั่งเพื่อติดตั้ง image พื้นฐาน หรือใช้ระบุคำสั้งที่ต้อง ติดตั้งภายใน image ของเรา
* VOLUME = กำหนด path ที่ใช้ในการเก็บ file ที่ถูกสร้างขึ้น เป็น path ใน container นั้น
* ARG = กำหนดค่าของตัวแปร
* ENV = กำหนด environment var ใช้งานคอนเทนเนอร์
* COPY = กำหนดการ copy ไฟล์ไปเป็นอีกไฟล์
* ADD = กำหนดการ copy ไฟล์ไปเป็นอีกไฟล์ ต่างจาก COPY ที่เมื่อเก็บแบบ zip file จะทำการ extract ให้ด้วย
* WORKDIR = กำหนดค่า directory เพื่อทำการสั้ง run
* CMD = กำหนดตัวอย่างเริ่มต้นของ container
* EXPOSE = กำหนด port ของ container ให้ภายนอกเรียกใช้ได้

