# OEI Code test

Acceda a las instrucciones de la prueba en portugués o en español / Acesse as instruções do teste em português ou espanhol:

* [Versión en español](#es_version)
* [Versão em português](#pt_version)

---

<a id="pr_version"></a>
## Teste de código para o OEI (texto em português)

Para permitir a matrícula de alunos em uma plataforma de formação online, é necessário desenvolver um serviço de seleção dos cursos oferecidos. Este serviço será uma API acessível via HTTP e aceitará e devolverá informações no formato JSON.

A plataforma de formação organiza cada curso por edições, que têm uma data de início das aulas. Em cada edição é oferecido um catálogo de cursos disponíveis. Cada curso pertence a uma única temática, e essas temáticas estão organizadas em escolas de formação.

As requisições serão feitas de acordo com a seguinte estrutura de dados:

* **criteria**: Critério de seleção dos cursos 
* **editions**
  * **date**: Data de início da edição
  * **courses**
    * **name**: Nome do curso
    * **type**: Temática do curso

As respostas às requisições incluirão a data de início da edição e os nomes dos cursos oferecidos.

Inicialmente, os critérios de seleção dos cursos serão temporais, de acordo com a classificação dos mesmos, ou uma combinação de ambos os critérios. No entanto, é possível que no futuro sejam definidas novas formas de seleção de cursos com base nas características das temáticas ou de suas escolas. Estes critérios iniciais são:    

* **closest**: Seleciona os cursos da próxima edição.
* **latest**: Seleciona os cursos mais distantes da data atual.
* **type-name**: Seleciona os cursos do tipo indicado.
* **school-name**: Seleciona os cursos da escola indicada.

As escolas e temáticas possíveis para os cursos oferecidos são as seguintes:

* **educacao**
* * **infantil**
* * **competencias-digitais**
* * **governanca**
* **linguas**
* * **aymara**
* * **quechua**
* * **quechua collao**
* **ciencia-e-cultura**
* * **educacao-artistica**
* * **divulgacao-cientifica**
* **cooperacao**
* * **cooperacao**

Como a plataforma está em fase de expansão, o catálogo de cursos pode crescer, e com ele as temáticas oferecidas em cada escola. Portanto, o sistema deverá estar preparado para considerar essa evolução.

Um exemplo de requisição seria o seguinte:

    {"criteria":["closest","school-cooperacion"],"editions":[{"date": "2023-06-01","courses":[ {"name": "Especialista en cooperación internacional", "type": "cooperacion"},{"name":"Divulgación y cooperación de la ciencia","type":"divulgacion-cientifica"}]},{"date":"2023-09-01","courses":[{"name":"Comprendiendo el portugués","type":"portugues"}, ... 

cuja resposta será:

    [{"date": "2023-06-01","courses":["Especialista en cooperación internacional"]}]

Está disponível um conjunto de casos de uso (arquivo test-cases) e um script de verificação correspondente: https://go.oei.int/test-script-2023

### Entrega do teste

A entrega será feita por meio de um link para um repositório no github.com ou gitlab.com onde o teste tenha sido resolvido. Além do código da API gerado, o repositório deverá incluir uma cópia do script de verificação utilizado e toda a documentação gerada para a resolução do problema.

Boa sorte!.

---

<a id="es_version"></a>
## Code test para la OEI (texto en español)

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

### Entrega de la prueba

La entrega se realizará mediante un enlace a un repositorio de github.com o de gitlab.com donde se haya resuelto la prueba. Además del código del API generado, el repositorio deberá incluir una copia del script de verificación utilizado y toda la documentación que se haya generado para la resolución del problema.

Mucha suerte.

