# Remote X

Try to put a X11 server (client) on a docker container and run GUI applications in it. Easy.


## Execution

* build one of the image `docker build -t '<name-of-image>' .` in the folders
* run with `docker run -ti --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix <name-of-image>` to forward to local X11 server
    - this is as far from secure as possible

## Extra

For the tweak_factorio image, a factorio installation is expected under `factorio`.
Audio does not work yet.