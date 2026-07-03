Tutorial AFNI n.° 1: Descarga de datos
======================================

**Descripción general**

En este curso analizaremos un conjunto de datos de resonancia magnética funcional (fMRI) que utilizó la tarea Flanker. El conjunto de datos se puede encontrar aquí, en el sitio web de OpenNeuro , un repositorio en línea de datos de neuroimagen.
../../_images/OpenNeuro_Flanker.png

La página de OpenNeuro para el conjunto de datos Flanker incluye un árbol de archivos del conjunto de datos, que incluye las carpetas anat(que contienen la imagen anatómica) y func(que contienen las imágenes funcionales y los tiempos de inicio para cada ejecución). Hay archivos adicionales que contienen datos del sujeto, como sexo y edad ( participants.tsv) y parámetros de escaneo ( task-flanker_bold.json). Estos datos están en un formato llamado BIDS (Brain Imaging Data Structure). Un árbol de directorios estandarizado como este facilita mucho la creación de scripts, como veremos en un tutorial posterior.

Descarga el conjunto de datos haciendo clic en el botón "Descargar" en la parte superior de la página. El conjunto de datos tiene un tamaño aproximado de 2 gigabytes y se encuentra en una carpeta comprimida. Para extraerlo, haz doble clic en la carpeta.
../../_images/OpenNeuro_DownloadButton.png

Una vez que haya descargado y descomprimido el conjunto de datos, haga clic en el botón Siguiente para obtener una descripción general de la tarea experimental utilizada en este estudio.
Opciones de descarga alternativas

Si el botón de descarga no funciona, intente usar la opción de Amazon Web Services (AWS) . Vaya a esta página y descargue el cliente de AWS adecuado para su sistema operativo. Una vez instalado, abra una terminal, vaya al escritorio y escriba lo siguiente:

aws s3 sync --no-sign-request s3://openneuro.org/ds000102 ds000102-download/

La descarga debería tardar aproximadamente media hora.
Video

Para ver un videotutorial sobre cómo descargar los datos, haga clic aquí .


