# Recursos

# PLUGIN FIREFOX MÚLTIPLES PESTAÑAS: 

- [multi account containers (https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/)](https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/)

## Formación de tecnologías que se usan en Isard:

- https://isard.gitlab.io/isardvdi-formacion/

## Clústers

### Storage. DRBD

- https://linbit.com

- https://linbit.com/blog/breaking-our-iops-record-what-linbits-success-means-for-our-clients/

- https://linbit.com/drbd-user-guide/drbd-guide-9_0-en/#s-three-way-repl

### HA. Pacemaker

- https://clusterlabs.org/pacemaker/

## Libvirt:
- Especificicaciones del hardware virtual configurable con XML de libvirt: [https://libvirt.org/formatdomain.html](https://libvirt.org/formatdomain.html)

Para ver el contenido del XML de libvirt de un escritorio que se está ejecutando:

Entrar en el hypervisor y lanzar comandos de virsh:

```
# entrar dentro del contenedor de hypervisor:
docker exec -ti isard-hypervisor /bin/bash

# una vez dentro:
virsh list
virsh dumpxml "nombre de la maquina virtual que ha cantado el virsh list"

## Herramientas para documentar

Crear esquemas con ascii:
- [asciiflow](https://asciiflow.com/#/)
- [textik](https://textik.com/)

Para crear manuales:
- [folge.me](https://folge.me/)
- [Tango](https://www.tango.us/) (vía web)
- [Scribe](https://scribehow.com/) (vía web)
- [iorad](https://www.iorad.com/) (interactivo)

## Automatizar instalación de alpine
- [unattended-installation-of-alpine-linux](https://www.skreutz.com/posts/unattended-installation-of-alpine-linux/)
```

