

# Evaluación 2 en Google Cloud


# Caso Avistamientos



## Grupo 7


## Integrantes: Alonso Gómez - Cristian Ferreira - Isidora Palma



  



## Introducción



 El presente laboratorio corresponde a la actividad **GSP823 de Google Cloud SkillBoost**, centrado en el uso de **Cloud Dataprep (Alteryx Designer Cloud)** como herramienta principal para la preparación y limpieza de datos. Durante esta actividad, se trabajó con un dataset relacionado a avistamientos de OVNIs, abordando procesos clave como la carga de datos, la limpieza y transformación de columnas, la manipulación de fechas y valores nulos, así como la creación de casos condicionales y agregaciones.
 



 El objetivo principal fue preparar la información de forma estructurada para que pudiera ser exportada a **BigQuery** y visualizada posteriormente en **Looker Studio** (antes Data Studio), facilitando así el análisis visual e interpretativo de los datos. Este proceso permitió aplicar buenas prácticas en la ingeniería de datos, como la creación de flujos reutilizables, parametrización de conjuntos de datos y generación de muestras para validaciones previas.
 







## Paso 1: Acceso a Google Cloud Console


Ingresamos a <https://console.cloud.google.com> e iniciamos sesión con nuestra cuenta de Google.


![Acceso a Google Cloud Console](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20155505.png)


## Paso 2: Aceptar los terminos y condiciones


Desde el panel principal, seleccionamos "Nuevo Proyecto" para organizar los recursos del entorno.


![ Aceptacion los terminos y condiciones](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20155517.png)
![Aceptacion de nuevo proyecto](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20155557%20(2).png)


## Paso 3: Iniciamos Activate Cloud Shell


Activamos Activate Cloud Shell.


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20155643.png)
Continuamos el mensaje de Cloud Shell.


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20155704.png)
Aceptamos y autorizamos el mensaje de Cloud Shell.


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20155721.png)
Ingresamos el siguiente codigo en la Shell y lo ejecutamos:


"gcloud beta services identity create --service=dataprep.googleapis.com"


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20155808.png)
Verificamos la respuesta de la creación


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20155826.png)


## Paso 4: Iniciamos Dataprep


Nos dirigimos all products.


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20155850.png)
Nos dirigimos en "Analytics" y seleccionamos -> "Alreryx Designer Cloud".


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20155913.png)
Luego aceptamos condiciones.


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20155932.png)
![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20160042.png)
![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20160053.png)
![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20160111.png)
![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20160125.png)


## Paso 5: Cargamos nuestro Dataset y ingresamos en Dataprep


Nos dirigimos a "Create a new row".


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20160149.png)
Nos aparece la siguiente interfaz y daremos a "Connect to your data".


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20160325.png)
Saldrá la siguiente interfaz".


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20160337.png)
Nos dirigimos en "Upload" para cargar nuestros datos".


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20160411.png)
Cargamos nuestro dataset en "Choose files" y nos saldrá una ventana para escoger nuestro archivo.


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20160430.png)
Al finalizar cambiamos el nombre de nuestro dataset como nos solicitan a "ovni.csv".


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20160531.png)
Volvemos atras y editaremos el nombre a "Grupo7" como representación a ambos alumnos que realizan este proceso.


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20160609.png)
Luego nos dirigimos a "recipe" y visualizaremos los datos adjuntados en esta plataforma.


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20160618.png)
Finalmente visualizaremos la siguiente interfaz que trabajaremos


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20160713.png)


## Paso 6: Preparamos los datos en Dataprep



 Visualizamos nuestras columnas, gracias a la interfaz que nos ofrece esta
 herramienta, podemos identificar los datos con nulos o problemas de formato.
 Finalmente haremos la limpieza de los datos que pueden perjedicar el análisis posterior. 
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20161234.png)

 Ademas corregiremos el nombre de una columna(state/province) que nos puede perjedicar posteriormente
 por ende nos dirigimos a la columna y seleccionamos "Rename column" para cambiar el nombre a "state\_province".
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20161818.png)
![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20161839.png)

 Posteriormente a realizar estos cambios, editaremos nuestra configuracion
 para llevarlos a Bigquery y realizar un análisis más profundo de los datos.
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20161321.png)

 Creamos una carpeta
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20161511.png)

 Luego seleccionamos Bigquery y nos dirigimos a la carpeta que creamos donde tendremos
 que crear una tabla para almacenar los datos que hemos limpiado y preparado.
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20161550.png)

 Nos dirigimos a crear una nueva tabla.
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20161559.png)

 Creamos la tabla como "avistamiento" como nos solicitan y le hacemos un truncate 
 antes de cargar los datos para que no se repitan los datos.
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20161727.png)

 Verificamos los cambios a Bigquery.
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20161929.png)

 Ejecutamos la accion y esperamos que finalice.
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20162055.png)
![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20162602.png)

 Cuando finalice el proceso podemos dirigirnos a Bigquery.
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20163125.png)


## Paso 7: Uso de Bigquery



 Realizaremos diferentes consultas para obtener los resultados con su 
 respectivos graficos con Loocker Studio.
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20163149.png)

 Nos dirigimos a la parte de "Query" para realizar las consultas.
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20163421.png)

 Grafico 1 en Loocker Studio.
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-29%20181810.png)

 Realizamos la segunda Query.
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20163607.png)

 Grafico 2 en Loocker Studio.
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-29%20184320.png)

 Realizamos la tercera Query.
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-25%20163754.png)

 Grafico 3 en Loocker Studio.
 


![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-29%20180710.png)
![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-29%20180622.png)
![](ImaAvistamiento/Captura%20de%20pantalla%202025-05-29%20180616.png)



## Conclusión



 La experiencia adquirida en este laboratorio permitió comprender de manera práctica cómo **Cloud Dataprep** simplifica la transformación de datos sin necesidad de programar, a través de una interfaz intuitiva y poderosa. Aprendimos a estructurar datos de forma eficiente para su posterior análisis en herramientas como **BigQuery** y **Looker Studio**, generando valor a partir de información inicialmente desordenada.
 



 Además, reforzamos competencias fundamentales en la preparación de datos como la limpieza de encabezados, la manipulación de fechas, la normalización de campos y la creación de casos condicionales. En conjunto, estas habilidades son esenciales para el rol de analista o ingeniero de datos, y demuestran el potencial de **Google Cloud Platform** en procesos de analítica avanzada y generación de insights accionables.
 



![](https://storage.googleapis.com/example/paso4.png)



© 2025 Duoc UC.



