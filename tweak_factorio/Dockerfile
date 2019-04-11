FROM ubuntu:16.04

COPY factorio .

ENV HOME /home/developer
ENV PATH /bin/x64/factorio:$PATH

# Replace 1000 with your user / group id
RUN export uid=1000 gid=1000; \
    mkdir -p /home/developer; \
    echo "developer:x:${uid}:${gid}:Developer,,,:/home/developer:/bin/bash" >> /etc/passwd; \
    echo "developer:x:${uid}:" >> /etc/group; \
    chown ${uid}:${gid} -R /home/developer

USER developer
CMD ["echo", "run 'factorio' to start"]
