# RMP401Plus_ROS1_SDK_v2028_hv02_230628
## Docker file
To build Docker image for Jetson ARM 64 v8, enter the folder of Docker file and run
- <code>docker build -t ros1-melodic-arm64 .</code>

## run the Image
If your working space is not the same as "/ssd/workspaces/catkin_ws", change it as it is going to be a shared folder witha  container
```bash
docker run -it --rm \
  --device=/dev/ttyUSB0:/dev/ttyUSB0 \
  -v "/ssd/workspaces/catkin_ws:/root/catkin_ws" \
  --privileged \
  --net=host \
  --name ros1_container \
  ros1-melodic-arm64
```

## attach to active seasion
Find the container ID then attach to it
- <code>docker ps </code>
- <code>docker exec -it <container_id_or_name> /bin/bash </code>

## stop and remove process (containers)
list, Stop and remove
- <code>docker ps -a </code>
- <code>docker ps -q | xargs -r docker stop && docker ps -a -q | xargs -r docker rm
 </code>

