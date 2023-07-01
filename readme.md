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
- **Binvox:** Binvox convierte formatos de objetos tridimensionales (OBJ, OFF, STL) a formato voxelizado (.binvox). Asigna valores binarios a cada voxel para indicar si está ocupado o no por el objeto.
- **Impresión 3D:** Utiliza el formato STL para describir la geometría de los objetos tridimensionales a imprimir. Se utiliza debido a su simplicidad y compatibilidad con la mayoría de las impresoras y software de impresión 3D.
- **Recursos disponibles:** GitHub y Kaggle son herramientas fundamentales en el desarrollo de software y la ciencia de datos. GitHub permite la colaboración y gestión del código fuente, mientras que Kaggle proporciona conjuntos de datos y herramientas para análisis y modelado predictivo. Ambas plataformas son esenciales para facilitar la colaboración y el intercambio de conocimientos en estas áreas.


## 3. Desarrollo

Durante el desarrollo del proyecto se realizaron una serie de análisis, implementaciones e interpretación de resultados. 

En primer lugar, se observó la arquitectura GAN adecuada para la generación de objetos 3D. Además, se analizaron diferentes algoritmos y técnicas de desarrollo para la lectura y edición de un archivo que contiene un objeto 3D. Se optó por utilizar el software Binvox, que nos permite la lectura y conversión a voxel de distintos formados de objetos 3D. A comparación con otros métodos, Binvox llega a ser más eficiente debido al uso de un ejecutable que administra la memoria de manera eficiente. Se utilizó el dataset Modelnet10, que contiene 4899 objetos 3D y 10 distintas categorías. Luego, se convirtieron todos los objetos 3D a formato Voxel con la finalidad de obtener una resolución baja de estos y pasar a quitarle un pedazo del objeto. Esto con la finalidad de poder entrenar nuestro modelo GAN.

El enlace al conjunto de datos es el siguiente: https://www.kaggle.com/datasets/balraj98/modelnet10-princeton-3d-object-dataset

En segundo lugar, se tenía como objetivo la implementación de la GAN. Este se compone de un par de redes que permiten la obtención de un nuevo modelo generado por Machine Learning. Por un lado, la red generadora contribuye en la creación de nuevos modelos a partir de valores que son conformados por los modelos faltantes de una pieza, a prueba y error estos van mejorando con el tiempo gracias a la contribución del discriminador. Por otro lado, la red discriminadora nos dice si los objetos 3D generados son correctas o erróneas, esta red es entrenada con los objetos 3D completos en formato Voxel. Una vez obtenido el resultado se pasan a interpretarlos. En el repositorio se adjuntó un ejemplo de una GAN funcional de Tensorflow con el dataset de Mnist: [dcgan.ipynb](/dcgan.ipynb).

En tercer lugar, se analizan los resultados obtenidos de los objetos generados. Debido a complicaciones en el curso de Machine Learning no se finalizó la implementación de la GAN. Para dar solución a ello, se realizó la impresión 3D del objeto original incompleta junto con su pieza para así realizar la demostración de la unión entre ellas. Por otro lado, si se hubiera realizado la implementación de la GAN, el siguiente paso sería medir la eficiencia de nuestro modelo se ha utilizado las métricas de pérdida o loss de ambas redes (generadora y discriminadora). Una vez obtenido el modelo resultado, se hubiera realizado la resta de este menos su modelo original faltante de una pieza, para así obtener solo la pieza generada. Este pedazo es impreso en una impresora 3D junto con el modelo original faltante de una pieza. Como parte final se hubiera validado los resultados, hubiéramos juntado ambos objetos impresos para identificar que a partir de la unión correcta estos tenían armonía entre sí y hacen un solo objeto uniforme.

Como oportunidades de mejora hemos identificado que es necesario la aplicación de la metodología CRISP-DM para tener más información del negocio a que nos enfocamos, los objetivos de los usuarios y estudiar más a detalle el dataset. 

## 4. Conclusiones

- La arquitectura GAN es una opción prometedora para generar objetos 3D. Aunque este proyecto no logró completar su implementación, sentó las bases para futuros desarrollos. Se recomienda investigar técnicas de entrenamiento y ajuste de parámetros para mejorar la calidad de los objetos generados.
- La conversión de objetos 3D a formato voxelizado fue crucial para la generación. El software Binvox permitió una lectura eficiente y conversión en voxels, facilitando el análisis y manipulación de los objetos, así como su impresión 3D. Se sugiere explorar y probar otros métodos y herramientas de voxelización para futuros proyectos.
- La impresión 3D fue valiosa para validar los resultados. A pesar de las limitaciones en la implementación de la GAN, se pudo comprobar la coherencia del objeto resultante al imprimirlo junto con la pieza faltante. En futuros proyectos, se recomienda explorar más la impresión 3D como parte integral del proceso de generación de objetos 3D.
