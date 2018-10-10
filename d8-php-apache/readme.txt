# jfif compile

* `docker run -it --mount src="/path/to/dockerfiles/d8-php-apache/jfif/mnt",target=/mnt/jfif2,type=bind diemayrei/web-base /bin/bash`
* `cd /mnt/jfif2/`
* `curl https://lyncd.com/files/imgopt/jfifremove.c -o jfifremove.c`
* `gcc -o jfifremove jfifremove.c`
