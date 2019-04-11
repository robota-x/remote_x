FROM ubuntu:16.04

COPY factorio factorio

ENV HOME /home/developer
ENV PATH factorio/bin/x64:$PATH

RUN apt-get update && apt-get -y install libasound2 libx11-6 libxcursor1 libxinerama1 libxrandr2 libgl1-mesa-glx

RUN export uid=1000 gid=1000; \
    mkdir -p /home/developer; \
    echo "developer:x:${uid}:${gid}:Developer,,,:/home/developer:/bin/bash" >> /etc/passwd; \
    echo "developer:x:${uid}:" >> /etc/group; \
    chown ${uid}:${gid} -R /home/developer

USER developer
CMD ["factorio"]
