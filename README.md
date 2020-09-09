# Procesamiento de términos del Plinian Core
## Descripción general
Este repositorio contiene el código fuente y la documentación de un conjunto de *scripts* para el procesamiento de los términos del estándar de información de especies [Plinian Core (PLIC)](https://github.com/tdwg/PlinianCore). Estos *scripts* están basados en los desarrollados por Steve Baskauf y que están disponibles en [https://github.com/tdwg/rs.tdwg.org/tree/master/process/page_build_scripts](https://github.com/tdwg/rs.tdwg.org/tree/master/process/page_build_scripts). Reciben como entrada una lista de términos relacionados con información sobre especies (ej. taxonomía, historia natural), y otros documentos asociados, y generan como salida otros documentos con metadatos para esos términos. El borrador del documento con la lista de términos a procesar se encuentra en este [enlace](https://docs.google.com/spreadsheets/d/1PdZbctIzZQet3gGXsWUWIoKwgUyzSdkUaApIXImjboE/edit#gid=0).

Los *scripts* fueron desarrollados en el lenguaje de programación [Python](https://www.python.org/) e implementados como *notebooks* de [Jupyter](https://jupyter.org/). Para facilitar su uso y mantenimiento, el procesamiento se realiza en un ambiente [Conda](https://docs.conda.io/).

En el resto de este documento, se describen las entradas, procesos y salidas del flujo de trabajo; y se detallan los comandos necesarios para su ejecución. Se incluye también una sección con los comandos necesarios para crear el ambiente Conda.

Los comandos y programas utilizados en este repositorio fueron probados en el sistema operativo [Ubuntu 18.04.5 LTS (Bionic Beaver)](https://releases.ubuntu.com/18.04/). Ya que todas las herramientas utilizadas son multiplataforma, pueden funcionar también en otros sistemas operativos, probablemente con algunos ajustes menores.

## Entradas, procesos y salidas
### Entradas
- term-lists.csv (¿archivo con términos en este [enlace](https://docs.google.com/spreadsheets/d/1PdZbctIzZQet3gGXsWUWIoKwgUyzSdkUaApIXImjboE/edit#gid=0)?)
- termlist-header.md (¿?)
- termlist-footer.md (¿?)

### Procesos
- Ejecución de los *notebooks*:
    - ```build-page-simple.ipynb```
    - ```build-page-categories.ipynb```

### Salidas
- ?.md (¿?)


## Ejecución del flujo de trabajo
Los siguientes comandos deben ejecutarse en la línea de comandos del sistema operativo. Se recomienda utilizar la interfaz de línea de comandos de Anaconda. Se asume que el ambiente Conda ha sido creado de la manera que se muestra en la sección siguiente a esta.
```shell
# Activación del ambiente Conda
$ conda activate plic-scripts

# Clonación del repositorio
$ git clone https://github.com/mfvargas/plic-scripts.git
$ cd plic-scripts

# Ejecución de Jupyter Notebook
$ jupyter notebook
# y de los notebooks build-page-simple.ipynb y build-page-categories.ipynb

# Actualización del repositorio y de los archivos GeoJSON generados
$ git add .
$ git commit -m "Cambios"
$ git push

# Desactivación del ambiente Conda
$ conda deactivate
```

## Creación y configuración del ambiente Conda
El ambiente Conda solamente debe crearse una vez. Luego puede seguir usándose de la manera que se especifica en la sección anterior.
```shell
# Actualización de Conda
$ conda update -n base -c defaults conda

# Creación del ambiente
$ conda create -n plic-scripts python

# Activación del ambiente
$ conda activate plic-scripts

# Instalación de paquetes
$ conda install -c anaconda jupyter
$ conda install -c anaconda requests
$ conda install -c anaconda pandas

# Desactivación del ambiente
$ conda deactivate
```
