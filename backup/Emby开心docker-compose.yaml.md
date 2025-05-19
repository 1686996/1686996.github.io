> services:
  amilysemby:
    image: amilys/embyserver:latest
    container_name: amilysemby
    restart: always
    privileged: true
    ports:
      - "8096:8096"
    environment:
      - TZ=Asia/Shanghai
      - UID=1000
      - GID=10
      - GIDLIST=10
    volumes:
      - /volume1/Config/amilysemby/config:/config
      - /volume1/CloudNAS:/CloudNAS:shared
      - /volume1/EmbyStrm:/EmbyStrm:shared
    devices:
      - /dev/dri:/dev/dri