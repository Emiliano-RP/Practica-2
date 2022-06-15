# Nivel 3. Introducción a la IA
<center>

![Logo de Microsoft Azure](Imágenes/Microsoft_Azure.svg.png) ![Logo de IA Wizards](Imágenes/logocomunidad2.png)

</center>

---
# Práctica 2. Cómo generar una imágen con inteligencia artificial (red generativa antagónica).
<center>

![Imágen de una Inteligencia Artificial](Imágenes/Inteligencia-artificial.jpeg)

</center>

#### Por [Emiliano Rodríguez Pérez](https://github.com/Emiliano-RP) #IA Wizards
#### Sherpa: [José Jesús Guzmán Eusebio](https://github.com/josejesusguzman)
---
#### Requisitos:
- Tener un equipo de cómputo con Windows, Linux o MacOs.
- Tener conexión a internet.
---
#### Instrucciones:
1. Para poder generar nuestra imagen nos dirigimos a [VQGAN+CLIP (z+quantize method con augmentations).ipynb](https://colab.research.google.com/drive/1go6YwMFe5MX6XM9tv-cnQiSTU50N9EeT#scrollTo=CppIQlPhhwhs).

<center>

![Captura de pantalla](Imágenes/Captura-de-pantalla-1.png)

</center>

2. Damos click en **Conectar** para que se asigne una máquina virtual.

<center>

![Captura de pantalla](Imágenes/Captura-de-pantalla-2.png)

</center>

3. Cuando nos aparezca el aviso **"El notebook requiere RAM amplia"**, damos en **Aceptar**.

<center>

![Captura de pantalla](Imágenes/Captura-de-pantalla-3.png)

</center>

4. Nos dirigimos al apartado de **"Selección de modelos a descargar"**. Puedes elegir descargar otros modelos pero el modelo por defecto será `imagenet_16384`. `imagenet_1024` es ligero. Los textos como `time total`, `time spent`, `time left` indican cuánto tiempo falta de descarga. Esperamos a que acabe de descargar.

<center>

![Captura de pantalla](Imágenes/Captura-de-pantalla-4.png)

</center>

5. Posteriormente debajo de **"Herramientas para la ejecución"**, encontraramos los **"Parámetros"**, los cuales podemos modificar para que la IA genere la imagen con las características que deseemos. Aquí te dejo una tabla de los parámetros que podemos modificar, su descripción y el texto predeterminado que se muestra en la pantalla de [VQGAN+CLIP (z+quantize method con augmentations).ipynb](https://colab.research.google.com/drive/1go6YwMFe5MX6XM9tv-cnQiSTU50N9EeT#scrollTo=CppIQlPhhwhs) :

    | Parámetro | Texto por defecto | Descripción |
    | --------- | ----------- | ------------------- |   
    | `textos` | `A fantasy world` | Este parámetro es el texto que VQGAN+CLIP va a interpretar como concepto de la imagen. Si se escribe "fuego", dibujará fuego, y si se escribe "agua", representará agua.|
    | `ancho` | `480` | El ancho de cada imagen que [VQGAN+CLIP](https://colab.research.google.com/drive/1go6YwMFe5MX6XM9tv-cnQiSTU50N9EeT#scrollTo=CppIQlPhhwhs) generará dentro de esa página de Colaboratory. Se recomienda no modificarlo (más allá de 600) puesto que la máquina virtual tiene una memoria limitada. Es mejor utilizar después [bigjpg](https://bigjpg.com/). Puedes cambiar la proporción para que no sea cuadrada (Una ayuda aquí: [Calculadora de proporciones](https://tools.feline.cl/es/calculadora-de-proporciones/)). |
    | `alto` | `480` | El alto de cada imagen que [VQGAN+CLIP](https://colab.research.google.com/drive/1go6YwMFe5MX6XM9tv-cnQiSTU50N9EeT#scrollTo=CppIQlPhhwhs) generará dentro de esa página de Colaboratory. Se recomienda no modificarlo (más allá de 600) puesto que la máquina virtual tiene una memoria limitada. Es mejor utilizar después [bigjpg](https://bigjpg.com/). También puedes cambiar la proporción. |
    | `modelo` | `imagenet_16384` | Este parámetro decide qué modelo de [VQGAN](https://colab.research.google.com/drive/1go6YwMFe5MX6XM9tv-cnQiSTU50N9EeT#scrollTo=CppIQlPhhwhs) se va a ejecutar. Son cajas que permiten seleccionar uno o varios modelos. El que selecciones tiene que haber sido descargado previamente. El número indica la cantidad de modelos que contiene por lo que `imagenet_16384` es mejor que `imagenet_1024` (aunque más pesado). |
    | `intervalo_imagenes` | `50` | Esto indica al programa cada cuantas iteraciones imprime el resultado en la página. Si se escribe 50, imprimirá los resultados de las iteraciones 0, 50, 100, 150, 200, etc. |
    | `imagen_inicial` | `None` | Para usar una imagen inicial, sólo debes subir un archivo al entorno del Colab (en la sección a la izquierda), y luego modificar `imagen_inicial`: poniendo el nombre exacto del archivo. Ejemplo: `sample.png`. |
    | `imagenes_objetivo` | `None` | Una o más imágenes que la IA tomará como "meta", cumpliendo la misma función que ponerle un texto. Es decir, la IA intentará imitar la imagen o imágenes. Se separan con `|`. |
    | `seed` | `-1` | ---- |