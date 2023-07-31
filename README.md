# Code test para la OEI

Para permitir la matriculación de alumnos en una plataforma de formación on-line, es necesario desarrollar un servicio de selección de los cursos ofertados. Este servicio será un API accesible via HTTP y aceptará y devolverá la información en formato JSON.

La plataforma de formación organiza cada curso por ediciones, que tienen una fecha de inicio de la docencia. En cada una de las ediciones se oferta un catálogo de cursos disponibles. Cada uno de los cursos pertenece a una única temática y estas temáticas están organizadas en escuelas de formación.

Las peticiones se realizarán de acuerdo a la siguiente estructura de datos:

* **criteria**. Criterio de selección de cursos
* **editions**
  * **date**. Fecha de inicio de la edición
  * **courses**
    * **name**. Nombre del curso
    * **type**. Temática del curso
    
Las respuesta a las peticiones incluirá la fecha de inicio de la edición y los nombres de los cursos ofrecidos.

Inicialmente, los criterios de selección de los cursos serán temporales, según la clasificación de estos o una combinación de ambos criterios. Sin embargo, es posible que en el futuro se determinen nuevas formas de selección de los cursos según características de las temáticas o de sus escuelas. Estos criterios iniciales son:

* **closest**: Selecciona los cursos de la próxima edición.
* **latest**: Selecciona los cursos más alejados de la fecha actual.
* **type-name**: Selecciona los cursos del tipo indicado.
* **school-name**: Selecciona los cursos de la escuela indicada.

Y las escuelas y temáticas posibles para los cursos ofrecidos son las siguientes:

* **educacion**
  * **infantil**
  * **competencias-digitales**
  * **gobernanza**
* **lenguas**
  * **portugues**
* **ciencia-y-cultura**
  * **educacion-artistica**
  * **divulgacion-cientifica**
* **cooperacion**
  * **cooperacion**
  
Dado que la plataforma está en fase de expansión, el catálogo de cursos puede aumentar y con él las temáticas ofrecidas en cada una de las escuelas. Por lo tanto, el sistema deberá estar preparado para contemplar esta evolución.

Así, un ejemplo de petición podría ser el siguiente:

    {"criteria":["closest","school-cooperacion"],"editions":[{"date": "2023-06-01","courses":[ {"name": "Especialista en cooperación internacional", "type": "cooperacion"},{"name":"Divulgación y cooperación de la ciencia","type":"divulgacion-cientifica"}]},{"date":"2023-09-01","courses":[{"name":"Comprendiendo el portugués","type":"portugues"}, ... 

cuya respuesta será:

    [{"date": "2023-06-01","courses":["Especialista en cooperación internacional"]}]

Para comprobar el correcto funcionamiento del código, está disponible un conjunto de casos de uso adjunto (fichero *test-cases*) y un script de verificación de estos ( https://go.oei.int/test-script-2023 ).

## Entrega de la prueba

La entrega se realizará mediante un enlace a un repositorio de github.com o de gitlab.com donde se haya resuelto la prueba. Además del código del API generado, el repositorio deberá incluir una copia del script de verificación utilizado y toda la documentación que se haya generado para la resolución del problema.

Mucha suerte.
