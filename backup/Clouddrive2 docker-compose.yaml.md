> services:
  clouddrive2:
    image: cloudnas/clouddrive2:latest
    container_name: clouddrive2
    environment:
      - TZ=Asia/Shanghai
      - CLOUDDRIVE_HOME=/Config
      - PUID=0
      - PGID=0
      - PGIDLIST=0
    volumes:
      - /vol1/1000/CloudNAS:/CloudNAS:shared
      - /vol02/1000-0-bab86c90:/MusicData:shared
      - /vol1/1000/J4125:/J4125:shared
      - /vol1/1000/Docker/CD2/config:/Config
    devices:
      - /dev/fuse:/dev/fuse
    restart: always
    pid: host
    privileged: true
    ports:
      - 19798:19798