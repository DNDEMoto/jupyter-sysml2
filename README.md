# jupyter-sysml2


### how to run 

on wsl

```
docker run --rm -p 8888:8888 -v /mnt/c/user_sysml2_working_dir:/home/root/work bleach31/jupyter-sysml2:2023-10
```
```
podman run --rm -p 8888:8888 -v /mnt/c/user_sysml2_working_dir:/home/root/work bleach31/jupyter-sysml2:2023-10
```

Not directly related to this repository.
If you see kind of following errors, for example in an company internal network,
`failed to verify certificate: x509: certificate signed by unknown authority.`
this sites may be helpful

* [How to import all Root CAs from Windows store into WSL automatically? · Issue \#3161 · microsoft/WSL](https://github.com/microsoft/WSL/issues/3161)
* [sudo update\-ca\-certificates
](https://stackoverflow.com/questions/72167566/wsl-docker-curl-60-ssl-certificate-problem-unable-to-get-local-issuer-certi)

### how to build image

```
docker build -t bleach31/jupyter-sysml2:2023-10 .
docker push bleach31/jupyter-sysml2:2023-10
```
