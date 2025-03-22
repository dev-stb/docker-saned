# docker-saned
Dockerized saned scanner server

Make sure, that the device node e.g. /dev/usb/00x/ have group id 7 (lp) and group read access.
Environment variable:
  SANED_ACL - [required] IP ranges or hosts that are allowed access to the daemon.
  SANED_DEVICE - [required] The device as reported by 'scanimage -L' to use for scanning via network.
  SANED_DLL - [optional] Overwrite /etc/sane.d/dll.conf with these values for faster response of saned.

`docker run --device /dev:/dev --privileged -e SANED_ACL="192.168.0.0/24\n10.0.0.0/8" -e SANED_DEVICE="hpaio:xxx" sesceu/saned`
