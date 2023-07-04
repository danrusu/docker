# docker

Useful docker images

## 1. openssl

- build image

  ```bash
  docker build -t openssl --build-arg LOCAL_PFX_FOLDER=localCertificatesFolderName -f Dockerfile_openssl .
  ```

- run container

  ```bash
  docker run --rm -it -v //$(pwd)/pfx:/home/pfx openssl

  # Certificate info:
  openssl pkcs12 -in pfxFile.pfx --noout -info
  openssl pkcs12 -in pfxFile.pfx --noout -info -legacy

  # covert legacy to modern .pfx
  openssl pkcs12 -in oldPfxFile.pfx -nodes -legacy | openssl pkcs12 -export -out newPfxFile.pfx
  cp newPfxFile.pfx /home/pfx/newPfxFile.pfx
  ```
