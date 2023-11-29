# jupyter-sysml2


### how to run 

on wsl

```
docker run --rm -p 8888:8888 -v /mnt/c/user_sysml2_working_dir:/home/root/work bleach31/jupyter-sysml2:2023-10
```
```
podman run --rm -p 8888:8888 -v /mnt/c/user_sysml2_working_dir:/home/root/work bleach31/jupyter-sysml2:2023-10
```



### how to build image

```
docker build -t bleach31/jupyter-sysml2:2023-10 .
docker push bleach31/jupyter-sysml2:2023-10
```
