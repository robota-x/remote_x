FROM ubuntu:16.04

ARG HOMEDIR=/home/developer

WORKDIR $HOMEDIR

COPY factorio factorio

ENV PATH $HOMEDIR/factorio/bin/x64:$PATH

RUN apt-get update && apt-get -y install libasound2 libx11-6 libxcursor1 libxinerama1 libxrandr2 libgl1-mesa-glx

RUN export uid=1000 gid=1000; \
    echo "developer:x:${uid}:${gid}:Developer,,,:/home/developer:/bin/bash" >> /etc/passwd; \
    echo "developer:x:${uid}:" >> /etc/group; \
    chown ${uid}:${gid} -R $HOMEDIR

USER developer
CMD ["factorio"]
