# Informe Grupal 
## Trabajo Final de Machine Learning
**Alumnos**
Flores Tenorio, Juan Diego Enrique - U202014558
Goyas Ayllón, Leonardo Andre - U202010206
Galindo Alvarez, Franco - U202010807
Espíritu Cueva, Christian - U201615215

**Docente**
Canaval Sanchez, Luis Martin

**Ciclo**
2023-01

## 1. Introducción

El crecimiento de la inteligencia artificial ha impulsado el desarrollo del aprendizaje automático, conocido como machine learning, que busca emular la inteligencia humana. En este proyecto, nos enfocamos en desarrollar un código que utilice técnicas de machine learning para reconstruir objetos en 3D dañados, dividiendo el trabajo en interpretar formatos de archivos y generar agujeros, y luego identificar y completar los agujeros utilizando mecanismos de machine learning. 

### Motivación

Nuestra principal motivación es profundizar nuestro aprendizaje en esta disciplina mediante la participación en un proyecto que involucre cierto grado de innovación y resolución de conflictos en un contexto de computación avanzada.

### Objetivos

**Objetivos Generales:**
- Diseñar un código que interprete archivos de objetos 3D, genere pequeños orificios en ellos y mediante el desarrollo de una Red Neuronal Generativa Adversaria ayude a la reconstrucción de esta.

**Objetivos Específicos:**
- Desarrollar un sistema para procesar archivos 3D en diversos formatos.
- Desarrollar un modelo que permita realizar agujeros en objetos 3D.
- Investigar y seleccionar la arquitectura GAN más adecuados para el proyecto.
- Desarrollar la arquitectura GAN más adecuados para el proyecto. 


## 2. Marco Teórico

- **Formato voxelizado:** El formato voxelizado representa objetos tridimensionales mediante pequeños cubos llamados "voxels", capturando su geometría y propiedades volumétricas.
- **Binbox:** Binvox convierte formatos de objetos tridimensionales (OBJ, OFF, STL) a formato voxelizado (.binvox). Asigna valores binarios a cada voxel para indicar si está ocupado o no por el objeto.
- **Impresión 3D:** Utiliza el formato STL para describir la geometría de los objetos tridimensionales a imprimir. Se utiliza debido a su simplicidad y compatibilidad con la mayoría de las impresoras y software de impresión 3D.
- **Recursos disponibles:** GitHub es una plataforma de desarrollo colaborativo para compartir proyectos de software y colaborar en herramientas de objetos voxelizados. Kaggle es una plataforma que proporciona bases de datos públicas para el procesamiento de objetos voxelizados y desafíos de aprendizaje automático.

## 3. Desarrollo

Durante el desarrollo del proyecto se realizaron una serie de análisis, implementaciones e interpretación de resultados. En primer lugar, se observó la arquitectura GAN adecuada para la generación de objetos 3D. Además, se analizaron diferentes algoritmos y técnicas de desarrollo para la lectura y edición de un archivo que contiene un objeto 3D. Se optó por utilizar el software Binvox, que nos permite la lectura y conversión a voxel de distintos formados de objetos 3D. A comparación con otros métodos, Binvox llega a ser más eficiente debido al uso de un ejecutable que administra la memoria de manera eficiente. Se utilizó el dataset Modelnet10, que contiene 4899 objetos 3D y 10 distintas categorías. Luego, se convirtieron todos los objetos 3D a formato Voxel con la finalidad de obtener una resolución baja de estos y pasar a quitarle un pedazo del objeto. Esto con la finalidad de poder entrenar nuestro modelo GAN.

En segundo lugar, se empezó con la implementación de la GAN. Este se compone de un par de redes que permiten la obtención de un nuevo modelo generado por Machine Learning. Por un lado, la red generadora contribuye en la creación de nuevos modelos a partir de valores que son conformados por los modelos faltantes de una pieza, a prueba y error estos van mejorando con el tiempo gracias a la contribución del discriminador. Por otro lado, la red discriminadora nos dice si los objetos 3D generados son correctas o erróneas, esta red es entrenada con los objetos 3D completos en formato Voxel. Una vez obtenido el resultado pasamos a interpretarlos.

En tercer lugar, se analizaron los resultados obtenidos de los objetos generados. Para medir la eficiencia de nuestro modelo se ha utilizado las métricas de pérdida o loss de ambas redes (generadora y discriminadora). Una vez obtenido el modelo resultado, se realiza la resta de este menos su modelo original faltante de una pieza, para así obtener solo la pieza generada. Este pedazo es impreso en una impresora 3D junto con el modelo original faltante de una pieza. Como parte final de validación de resultados, hemos juntado ambos objetos impresos para identificar que partir de la unión correcta estos tienen armonía entre sí y hacen un solo objeto uniforme.

Como oportunidades de mejora hemos identificado que es necesario la aplicación de la metodología CRISP-DM para tener más información del negocio a que nos enfocamos, los objetivos de los usuarios y estudiar más a detalle el dataset.

## 4. Conclusiones

...