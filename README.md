# From ETL to Machine Learning Recomendation
A partir de los datos de algunas plataformas de streaming se crea un modelo de recomendación de usando técnicas de machine learning.<br> <br>

<p align=center><img src="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/images/proceso.jpg"><p> <br> 
  
 ## Introduction
 En este repositorio encontrarás muchas herramientas que te serán familiares, te explico con más detalle la forma en que se desarrolla el proyecto en el siguiente <a href="https://www.youtube.com/watch?v=5WaHfWF77Vs">video.</a>
  
## Table of Contents

- [ETL](#ETL)
- [Querys](#Querys)
- [API](#API)
- [EDA](#EDA)
- [PreML](#PreML)
- [ML](#ML)
- [Gradio y Hugging Face](#Gradio y Hugging Face)
- [Datos Iniciales](#Datos Iniciales)
  
## <a href="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/Parte1-ETL.ipynb">ETL </a>
Comienzo por un proceso de Extract, Transform, and Load (ETL) para integrar toda la información en una base de datos que se utilizará en las siguientes etapas de este proyecto. 
  
## <a href="[https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/Parte1-ETL.ipynb](https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/Parte2-Consultas_y_API.ipynb)">Querys</a>
Una vez que se tiene asegurada la calidad de los datos, tenía muchas preguntas, como por ejemplo:
- ¿De todas las plataforma cual será la película más larga o de mayor duración? (get_max_duration)
- ¿Qué películas tienen una buena calificacion? (get_score_count)
- ¿Cuántas películas hay? ya que viene mezclada tanto películas como tvshows.(get_count_platform)
- ¿Qué actriz, actor o actores, aparecen en determinada plataforma? (get_actor)
  
Y que mejor momento que este para crear una API sencilla, y poder compartirla con todos.
 
## API
La API fue construida con ayuda de FastAPI, he hice un deploy en Deta Space. Para poder acceder a la API,tienes que instalarla, da click en la imagen.
  
<a href="https://deta.space/discovery/r/r1z3sqkuowog8y3r"><img width="70%" src="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/images/api%20consultas.png"></a>
  
Una vez que ingreses agrega ("/docs") a la direccion url:<br>
  
<img src="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/images/ingresar%20consultas.png">
  
Al ingresar podrás ver un menu con consultas, elige alguna de ellas, para probarla.
  
<img width= "70%" src="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/images/probandoConsulta.gif">
  
## EDA
El EDA nos permite familiarizarnos aún más con los daos, podemos conocer si hay errores, duplicados, valores faltantes, relaciones, entre otros. Uno de los problemas que me enfrenté al usar un dataset tan grande (1.5GB) es que mi computadora no tenia la suficiente capacidad, por lo que tuve que recurrir a tomar solo una muestra y así explorar las librerias especiales para el EDA, como son *pandas profiling, sweetviz, autoviz. Los reportes html que se generan puedes encontrarlos en esta <a href="https://github.com/hikikae/From-ETL-to-Machine-Learning/tree/main/Reportes%20EDA">carpeta<a>. 

- <a href="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/Parte3-EDA-1.ipynb">Parte 1.</a> Utilizando todos los datos (1.5GB)
- <a href="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/Parte3-EDA-2.ipynb">Parte 2. </a> Tomando una muestra <br>
  
<img width= "50%" src="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/images/reporteEDA.png"> <br>
 
<img width= "30%" height="200px" src="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/images/grafica.png"> <img height="200px" width= "30%" src="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/images/violin.png">

## <a href="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/Parte3-PreML.ipynb">PreML</a>
Una vez que tuve el EDA me encontré con nuevas interogantes como son:
  
- Numero de peliculas que ha calificado cada usuario
- Distribución de las calificaciones
- Película que más calificaciones tiene
- Película que menos calificaciones tiene
- Película más vista

Me pareció importante mencionar estos hallazgos y te invito a que los revises.
  
## <a href="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/Parte4-ML%20y%20Gradio.ipynb">ML</a> 
Para realizar una recomendación de una película, utilice un filtro colaborativo basado en SVD (Descomposción en Valores singulares), que sirve para reducir la dimensionalidad que para el caso de tanto volumen de datos, acorta los tiempos de procesamiento y la librerría Surprise que ayuda a aplicar los algoritmos de recomendadion. 
  
Este enfoque colaborativo se basa en la idea de que los usuarios con gustos similares calificarán de manera similar las mismas películas. 

## Gradio y Hugging Face
En el notebook anterior al final encontrarás el código que utilicé para cargar el modelo de ML utilicé Gradio y lo deployé por medio de Hugging Face.

<img width="70%" src="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/images/gradio.png">
 
  
Antes de hacer una prueba revisemos rápidamente algunos identificadores de películas.

<img width="70%" src="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/images/titulosPeliculas.png">
  
  
Te muestro como hacer una prueba con los datos más básicos:
<img width="70%" src="https://github.com/hikikae/From-ETL-to-Machine-Learning/blob/main/images/recomendacionML.gif">

  
## <a href="https://github.com/hikikae/From-ETL-to-Machine-Learning/tree/main/dataset"> Datos Iniciales</a>
    - Plataformas
        - amazon_prime_titles.csv
        - disney_plus_titles.csv
        - hulu_titles.csv
        - netflix_titles.csv
    - Ratings
        - 1.csv
        - 2.csv
        - 3.csv
        - 4.csv
        - 5.csv
        - 6.csv
        - 7.csv
        - 8.csv

## Agradecimiento y Contacto
Gracias por interesarte en mi proyecto y si tienes alguna duda no dudes en contactarte conmigo.

Angélica García Díaz ---- mail:  angelicagarciad@gmail.com

 😇
                        
     

