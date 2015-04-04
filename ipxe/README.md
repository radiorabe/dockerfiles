# [radiorabe/ipxe](https://registry.hub.docker.com/u/radiorabe/jenkins/)

Simple ``FROM scrath`` image that contains ``/tftpboot/ipxe/unidonly.pxe`` [iPXE](http://ipxe.org/) bootloader in a volume.

## Usage

Mount it into a tftp server of your choosing. If you use [jumanjiman/tftp-hpa](https://registry.hub.docker.com/u/jumanjiman/tftp-hpa/)
  you can start it as follows.

```bash
docker run --name ipxe radiorabe/ipxe noop
docker run \
  --name tftp_ipxe \
  -d -p 69:69/udp \
  --volumes-from ipxe \
  jumanjiman/tftp-hpa -L --verbose  -u tftp --secure /tftpboot
```
