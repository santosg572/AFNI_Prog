Tutorial AFNI n.° 4: Comandos AFNI y preprocesamiento
=====================================================

Nota

Muchos de los ejemplos se ejecutan desde ese Flanker/sub-08directorio; recomiendo navegar hasta ese directorio con la terminal antes de leer el resto del capítulo.
Descripción general

Ahora que sabemos dónde están nuestros datos y qué aspecto tienen, daremos el primer paso del análisis de fMRI: el preprocesamiento .

Piensa en el preprocesamiento como la limpieza de las imágenes. Cuando tomas una foto con una cámara, por ejemplo, hay varias cosas que puedes hacer para que la imagen se vea mejor:

    Eliminar el enrojecimiento de los ojos;

    Aumentar la saturación del color;

    Eliminar sombras.

../../_images/04_Before_After_Editing.png

Una fotografía tomada con una cámara puede resultar oscura, borrosa o con ruido (panel izquierdo). Tras editar la imagen, mejorando el contraste, reduciendo la borrosidad y aumentando el brillo, obtenemos una fotografía más nítida y definida.

De forma similar, al preprocesar los datos de fMRI, limpiamos las imágenes tridimensionales que adquirimos en cada TR . Un volumen de fMRI contiene no solo la señal que nos interesa (cambios en la oxigenación sanguínea), sino también fluctuaciones que no nos interesan, como el movimiento de la cabeza, las desviaciones aleatorias, la respiración y los latidos del corazón. A estas fluctuaciones las llamamos ruido , ya que queremos separarlas de la señal que nos interesa. Algunas de estas fluctuaciones se pueden eliminar de los datos mediante su modelado (lo cual se analiza en el capítulo sobre ajuste de modelos), y otras se pueden reducir o eliminar mediante el preprocesamiento.

Para comenzar el preprocesamiento de datos sub-08, lea los siguientes capítulos. Comenzaremos con una descripción general de cómo usar los comandos AFNI y luego presentaremos uber_subject.py, que le permite escribir un script que realizará todo el preprocesamiento por usted. A continuación, aprenderá por qué se realiza cada uno de estos pasos de preprocesamiento y cómo verificar la calidad de los datos antes y después de cada paso.

Pasos de preprocesamiento

    Capítulo 1: Comandos AFNI y uber_subject.py
    Intermezzo: Ejecutando el script del tema de Uber
    Capítulo 2: Corrección de la sincronización de cortes
    Capítulo 3: Registro y normalización
    Capítulo 4: Alineación y corrección del movimiento
    Capítulo 5: Suavizado
    Capítulo 6: Enmascaramiento y escalado
    Capítulo 7: Comprobación del preprocesamiento

Nota

Los distintos programas informáticos realizan estos pasos en un orden ligeramente diferente; por ejemplo, FSL normaliza los mapas estadísticos tras ajustar el modelo. También existen análisis que omiten ciertos pasos; por ejemplo, algunos investigadores que realizan análisis de patrones multivoxel no suavizan sus datos. En cualquier caso, la lista anterior representa los pasos más comunes que se realizan en un conjunto de datos típico.
Video


