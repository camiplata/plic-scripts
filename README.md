# Procesamiento de términos del Plinian Core
## Descripción general
Este repositorio contiene el código fuente y la documentación de los scripts para el procesamiento de los términos del [Plinian Core](https://github.com/tdwg/PlinianCore).

Los scripts originales están disponibles en [https://github.com/tdwg/rs.tdwg.org/tree/master/process/page_build_scripts](https://github.com/tdwg/rs.tdwg.org/tree/master/process/page_build_scripts).

La hoja con los términos está disponible en este [enlace](https://docs.google.com/spreadsheets/d/1PdZbctIzZQet3gGXsWUWIoKwgUyzSdkUaApIXImjboE/edit#gid=0).

## Entradas, procesamiento y salidas
### Entradas
- Archivo con términos en este [enlace](https://docs.google.com/spreadsheets/d/1PdZbctIzZQet3gGXsWUWIoKwgUyzSdkUaApIXImjboE/edit#gid=0).

### Procesamiento
- Ejecución de los programas ``` ``` y ``` ```.

### Salidas
- 

## Ejecución del programa
Los siguientes comandos deben ejecutarse en la línea de comandos del sistema operativo. Se recomienda utilizar la interfaz de línea de comandos de Anaconda. Se asume que el ambiente Conda ha sido creado de la manera que se muestra en la sección siguiente a esta.
```shell
# Activación del ambiente Conda
$ conda activate geo-cosecha-agua-conversion-capas

# Clonación del repositorio
$ git clone https://github.com/geo-cosecha-agua/geo-cosecha-agua-conversion-capas.git
$ cd geo-cosecha-agua-conversion-capas

# Ejecución del programa
$ ./geo-cosecha-agua-conversion-capas.sh

# Compresión de los resultados (se asume que son archivos GeoJSON)
# Este comando puede usarse si los archivos son muy grandes para subirse a GitHub
# Es mejor subir solo los GeoJSON o solo el ZIP (no ambos), para evitar duplicidad y confusión
# $ zip geojson.zip *.geojson

# Actualización del repositorio y de los archivos GeoJSON generados
$ git add .
$ git commit -m "Convertir capas"
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
$ conda create -n scripts-plic

# Activación del ambiente
$ conda activate scripts-plic

# Instalación de paquetes
$ conda install -c conda-forge gdal

# Desactivación del ambiente
$ conda deactivate
```
