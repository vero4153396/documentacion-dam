# Documentación del curso para ITB

Disponible para navegar en: https://isard.gitlab.io/cursoitb

## Create local mkdocs

Install mkdocs modules with virtualenv:

```bash
# install virtualenv in debian 12
sudo apt install python3-virtualenv

# create venv
cd path_to_local_repo_sysadmin-docs
virtualenv venv

# activate venv
source venv/bin/activate

# install modules with requirements.txt
python3 -m pip install -r requirements.txt

```

Create mkdocs and run local server:
```bash
python -m mkdocs build
python -m mkdocs serve -a 127.0.0.1:9099
```