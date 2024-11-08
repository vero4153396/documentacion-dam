# Instalación de servidor de Isard all-in-one

Cómo montar un servidor IsardVDI en un servidor, en el curso lo hicimos sobre un servidor de OCI

## Servidor en oci

Instalar DockerCE (https://docs.docker.com/engine/install/ubuntu/) 

Clonar directorio

```
mkdir /opt/isard
git clone https://gitlab.com/isard/isardvdi /opt/isard/src
cd /opt/isard/src
cp isardvdi.cfg.example isardvdi.cfg
```

Modificar en isardvdi.cfg:
```
DOMAIN=oci.cursoitb.xyz
LETSENCRYPT_EMAIL=letsencrypt@cursoitb.xyz
ENABLE_STATS=true
WEBAPP_ADMIN_PWD
WEBAPP_SESSION_SECRET
API_ISARDVDI_SECRET
API_HYPERVISORS_SECRET

```

build, docker compose  pull / up
```
./build.sh
docker compose pull
docker compose up -d
```

Subimos fichero de usuarios csv. Usuarios alumnos.

#### Directorios de Isard y donde guardar datos

El código lo puedes montar donde quieras, nosotros lo hacemos en /opt/isard/src
La base de datos y algún dato que ha de ser persistente /opt/isard-local
Lo "gordo", las plantillas y los discos de escritorio están en:

* /opt/isard/groups: discos de escritorio
* /opt/isard/templates: discos de plantillas
* /opt/isard/volatiles: discos de escritorios volátiles
* /opt/isard/media: ficheros isos

Es interesante dejar /opt/isard-local en un punto de montaje con un disco diferente de donde está el almacenamiento de qcows, porque si unos escritorios saturan la escritura me afectaría a la base de datos.

Ejemplo de montaje:
```
parted /dev/sdb mklabel gpt
parted /dev/sdb mkpart primary 1M 100%
pvcreate /dev/sdb1
vgcreate vgdatos /dev/sdb1
lvcreate -l 95%FREE -n lvdatos vgdatos 
lvs
mkfs.ext4 /dev/mapper/vgdatos-lvdatos 
mount /dev/mapper/vgdatos-lvdatos /mnt
```

Si quiero mover todos los datos a este nuevo disco:
```
cd /opt/isard/src
docker compose down
rsync -av --progress /opt/isard /mnt/
cd /opt/
mv isard isard_antiguo
mkdir isard
umount /mnt 
mount /dev/mapper/vgdatos-lvdatos /opt/isard
```

Faltaría consolidar este montaje en el fstab para que se quede fijado en próximos reinicios.



