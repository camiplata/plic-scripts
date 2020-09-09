# Procesamiento de términos del Plinian Core
## Descripción general
Este repositorio contiene el código fuente y la documentación de los scripts para el procesamiento de los términos del [Plinian Core](https://github.com/tdwg/PlinianCore).

Los scripts originales están disponibles en [https://github.com/tdwg/rs.tdwg.org/tree/master/process/page_build_scripts](https://github.com/tdwg/rs.tdwg.org/tree/master/process/page_build_scripts).

La hoja con los términos está disponible en este [enlace](https://docs.google.com/spreadsheets/d/1PdZbctIzZQet3gGXsWUWIoKwgUyzSdkUaApIXImjboE/edit#gid=0).

## Entradas, procesamiento y salidas
### Entradas
- Archivo con términos en este [enlace](https://docs.google.com/spreadsheets/d/1PdZbctIzZQet3gGXsWUWIoKwgUyzSdkUaApIXImjboE/edit#gid=0).

### Procesamiento
- Ejecución de los *notebooks*:
    - ```build-page-simple.ipynb```
    - ```build-page-categories.ipynb```.

### Salidas
- 

## Ejecución del programa
Los siguientes comandos deben ejecutarse en la línea de comandos del sistema operativo. Se recomienda utilizar la interfaz de línea de comandos de Anaconda. Se asume que el ambiente Conda ha sido creado de la manera que se muestra en la sección siguiente a esta.
```shell
# Activación del ambiente Conda
$ conda activate scripts-plic

# Clonación del repositorio
$ git clone https://github.com/mfvargas/plic-scripts.git
$ cd scripts-plic

# Ejecución de Jupyter Notebook
$ jupyter notebook

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
$ conda create -n scripts-plic python

# Activación del ambiente
$ conda activate scripts-plic

# Instalación de paquetes
$ conda install -c anaconda jupyter
$ conda install -c anaconda requests
$ conda install -c anaconda pandas

# Desactivación del ambiente
$ conda deactivate
```
