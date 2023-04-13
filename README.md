# Code test para la OEI

Para permitir la matriculación de alumnos en una plataforma de formación on-line, es necesario desarrollar un servicio de selección de los cursos ofertados. Este servicio será un API accesible via HTTP y aceptará y devolverá la información en formato JSON.

Inicialmente, los patrones de selección de los cursos serán temporales, según la clasificación de estos o una combinación de ambos criterios. Sin embargo, es posible que en el futuro se determinen nuevas formas de selección de los cursos según características de las temáticas.

La plataforma de formación organiza cada curso por ediciones, que tienen una fecha de inicio de la docencia. En cada una de las ediciones se oferta un catálogo de cursos disponibles. Cada uno de los cursos pertenece a una única temática y estas temáticas están organizadas en escuelas de formación.

Las peticiones se realizarán de acuerdo a la siguiente estructura de datos:

* **criteria**. Criterio de selección de cursos
* **editions**
  * **date**. Fecha de inicio de la edición
  * **courses**
    * **name**. Nombre del curso
    * **type**. Temática del curso
    
Las respuesta a la consulta incluirán la fecha de inicio de la edición y los nombres de los cursos ofrecidos.

Los criterios de búsqueda son:

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
  
Así, un ejemplo de petición será el siguiente:

y la respuesta para dicha consulta deberá podría ser:

Dado que la plataforma está en fase de expansión, el catálogo de cursos puede aumentar y con él las temáticas ofrecidas en cada una de las escuelas. Por lo tanto, el sistema deberá estar preparado par contemplar esta evolución.

Para comprobar el correcto funcionamiento del código, está disponible un conjunto de casos de uso (fichero *test-cases*) y un script de verificación de estos ( https://go.oei.int/test-script-2023 ).
