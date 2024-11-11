# Documentación para alumnos de DAM

Disponible para navegar en: xxx

## Create local mkdocs

Debes tener instalado python 3 para poder ejecutar MKDOCS

```bash
# En la misma carpeta que el proyecto instalar mkdocs
pip install mkdocs

# Instalar los módulos de mkdocs necesarios para esta documentación
pip install -r requirements.txt

# Generar el código HTML de la documentación
python -m mkdocs build

# Ejecutar el servidor de modo local para ver la documentación
python -m mkdocs serve -a 127.0.0.1:9099
```