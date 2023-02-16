## TC1030 - Programación Orientada a Objetos (Tips para su implementación en GitHub)

![174454995-6ebce5d6-e6cd-40ee-8391-105d5f0df777](https://user-images.githubusercontent.com/55771796/183143437-0019fae2-2de8-4560-869a-56c7ded95f51.png)

Para el uso de GitHub con esta UF se presentan a continuación los elementos a considerar, así como la forma en la que se pueden utilizar:

# ORGANIZACIONES

Se recomienda que la UF cuente con las siguientes **Organizaciones**:

* **`TMP-XXX`** : (*Organizaciónn personal - gratuita*). En esta organización el profesor crea los diversos repositorios que utilizará para su clase (plantillas, ejemplos, ejercicios o tareas). Es una organización con repositorios privados y plantilla. Es una organización de *backstage*. **Escalamiento**: se puede definir sólo una organización de este tipo en la cual todos los profesores del campus pueden crear ejercicios para todos los grupos.

* **`CLA-XXX`** : (*Organización personal - gratutita*). En esta organización el profesor colocará las versiones de repositorios públicos - plantilla que serán la base para cada una de las tareas con Autograding de la organización. Estos repositorios se generaron a partir de los respositorios privados - plantilla que trabajó y generó el profesor en la organización TMP-XXX. **Escalamiento:** se puede definir sólo una organización de este tipo que puede ser compartida para la generación de todos los ejercicios de Autograding de todos los grupos del campus.

* **`C-SIN-TC1030-XXX`**: (*Organización Tec*). Es la organización que el Tec crea para cada profesor en cada semestre. Ahí el profesor puede colocar ejemplos de programación para su clase (repositorios públicos - no plantilla) así como repositorios para que el alumno practique programación (repositorios públicos-plantilla). Es aquí donde deberían generarse los repositorios privados de los alumnos cuando aceptan sus tareas de Autograding. **Escalamiento:** a nivel nacional el responsable  genera 1 organización para cada grupo en cada campus en cada semestre.

# WORKFLOW

Existen dos casos de uso que suelen presentarse en los cursos: **(1) Explicar ejemplos o realizar ejercicios sin Autograding** y **(2) Realizar ejercicios y tareas con Autograding**. Cada uno de ellos se pueden implementar con un Workflow básico de `creación-generación-transferencia de repositorios` entre las organizaciones propuestas.

## (1) Explicar ejemplos o realizar ejercicios sin Autograding:

`TMP-XXX->C-SIN-TC1030-XXX`

## (2) Realizar ejercicios y tareas con Autograding:

`TMP-XXX->CLA-XXX->C-SIN-TC1030-XXX`

** **Nota**: en caso de existir un laboratorio previo de ejercicios (por ejemplo NAL) el workflow se puede ampliar:

`LAB-NAL-XXX->TMP-XXX->CLA-XXX->C-SIN-TC1030-XXX`

* La razón por la cual existe el paso a la organización intermedia CLA-XXX tiene que ver con eliminar la posibilidad de que el alumno pueda encontrar la solución a través de la consulta del histórico de cambios de GitHub. Al pasara de TMP-XXX a CLA-XXX se pierde esta historia y se evita que el estudiante conozca la solución original que el profesor diseñó en la organización TMP-XXX.

# REPOSITORIOS EJEMPLOS Y EJERCICIOS
Estos repositorios se pueden crear para que el profesor apoye la explicación de los temas y permitir al alumno que los revise y ejercite usando `Codespaces`. Se sugieren públicos-plantilla/no plantilla.

## Repositorios Ejemplos
El profesor puede crear este tipo de repositorios para compartir ejemplos de programación sobre los temas que está exponiendo. Con `Codespaces` el alumno puede revisarlos y ejecutarlos. Se sugieren públicos y no plantilla.

* [Ejemplo-Repositorio Herencia](https://github.com/TC1030-SBX/TC1030.cpp.herencia)
* [Ejemplo-Repositorio Polimorfismo](https://github.com/TC1030-SBX/TC1030.cpp.polimorfismo)
* [Ejemplo-Repositorio Sobrecarga de Operadores](https://github.com/TC1030-SBX/TC1030.cpp.sop)
* [Ejemplo-Repositorio Funciones Amigas](https://github.com/TC1030-SBX/TC1030.cpp.friend)
* [Ejemplo-Repositorio Excepciones](https://github.com/TC1030-SBX/TC1030.cpp.excepciones)

## Repositorios Ejercicios - sin Autograding
El profesor puede poner a disposición de los alumnos este tipo de repositorio para que practiquen los diversos temas de programación. Se sugieren público y plantilla y que cada alumno genere el propio usando su matrícula para distinguirlos entre sí. Cada alumno se sugiere genera su propio repositorio privado y no plantilla. Usarían `Codespaces` para practicar.

* [Plantilla-Repositorio para Ejercicios - sin Autograding](https://github.com/TC1030-SBX/ej-base-proyectos)

## AUTOGRADING

La implementación de Autograding para C++ está inspirada en la propuesta del profesor Igor Machado que publica en la su [página de Medium](https://medium.com/swlh/easy-c-autograding-on-github-classroom-with-catch2-106ad1107402). 

El Repositorio base para la construcción de este tipo de ejercicios es el siguiente:

* [Plantilla-Repositorio para Ejercicios de Autograding](https://github.com/TC1030-SBX/ej-base-autograding)

El Workflow sugerido para implementarlo es el siguiente:

1. El profesor selecciona y resuelve el ejercicio completamente. Incluye dentro del mismo la(s) prueba(s) para realizar el Autograding. Todo lo realiza dentro de la organización `TMP-XXX` en un repositorio privado y plantilla. Parte de la base que le ofrece el [repositorio plantilla para Autograding](https://github.com/TC1030-SBX/ej-base-autograding). Las Herramientas que se sugieren para que el profesor construya este repositorio son `Codespaces` (si desea tener acceso a todas las herrramientas de programación - editor+compilador+depurador); y puede usar el `.` directamente en GitHub para tener acceso a un editor simple (sin acceso a la máquina virtual Linux), útil para ediciones rápidas.

2. A partir del repositorio solución creado por el profesor, se obtiene una copia del mismo (se puede agregar el sufijo `.tmp` para diferenciarlo) y haciendo uso de `Codespaces` o el editor simple, el profesor elimina la programación que desea que el alumno haga como solución de la tarea. El grado de dificultad que desea el profesor para el problema puede ser: desde elminar poco código (fácil), hasta eliminar el código completo (difícil). Se sugiere dejar los `.hpp` y que el alumno programe los `.cpp`. Se sugiere, también, agregar el diagrama UML para que el alumno tenga este referente del diseño de la tarea.

3. Una vez listo el repositorio base para la tarea se genera una copia del repositorio privado-plantilla de la organizacón TMP-XXX a la organización CLA-XXX como repositorio público-plantilla. Este será el repositorio que se utilizará para la configuración de la tarea en [GitHub-Classroom](https://classroom.github.com/).

4. En [GitHub-Classroom](https://classroom.github.com/) se crea una asignación nueva para la tarea. Se sugiere ajustar los siguientes parámetros de configuración:

* `Assignment title:` título descriptivo de la tarea. Se sugiere definir un estándar para su rápida identificación.
* `Deadline:` fecha límite de entrega que coincida con la que se ha establecido en Canvas.
* `Repository visibility:` private.
* `Starter code and environment:` el repositorio público-plantilla disponible en la organización `CLA-XXX`
* `Supported editor:` Codespaces
* `Grading and Feedback:` se sugiere configurar las pruebas acorde a la siguiente [guía](https://gist.github.com/rquinteroTecSin/57c7f1e1ca1e792cfac2e6ac051fa771).
* `Enable feedback pull request:` activarlo. Esto se recomienda para poder apoyar aquéllos estudiantes que requieren asesoría cuando presentan problemas en su programación. Puede revisar el siguiente [Tutorial-Code Review](https://youtu.be/lSnbOtw4izI) para aprenderlo en 3 minutos.

5. Finaliza la creación de la tarea en el botón verde `Create Assignment`.

6. El profesor comparte la liga de la tarea en Canvas.

## REPOSITORIOS Y ARCHIVOS DE APOYO

* [Plantilla-Repositorio de Ejercicios sin Autograding](https://github.com/TC1030-SBX/ej-base-proyectos)
* [Plantilla-Repositorio de Ejercicios con Autograding](https://github.com/TC1030-SBX/ej-base-autograding)
* [Archivo makefile - para Repositorio de Ejercicios y Ejemplos sin Autograding](https://gist.github.com/rquinteroTecSin/5c0ff34587cb4238c26ae2d1c6ceeb00)
* [Archivo makefile - para Repositorio de Ejercicios con Autograding](https://gist.github.com/rquinteroTecSin/ac02e1499cd32bfcfc047d95229b6f39)
* [Archivo de configuración para habilitar debug en VSCode](https://gist.github.com/rquinteroTecSin/fb7005646bfb72ca174043ee904c0888)
* [Repositorio - Ejemplo Repositorio Autograding completo](https://github.com/TC1030-SBX/TC1030.cpp.ag.calculadora)
* [Repositorio - Ejemplo Repositorio Autograding incompleto -para que el alumno lo resuelva en una tarea](https://github.com/TC1030-SBX/TC1030.cpp.ag.calculadora.tmp)
* [Repositorio - Evaluación Diagnóstico sugerido en la UF](https://github.com/TC1030-SBX/TC1030.cpp.ag.evdg)
* [Repositorio - Examen Práctico usando Autograding](https://github.com/TC1030-SBX/TC1030-SBX-TC1030.cpp.ag.evdg)

## VIDEOS DE APOYO

Los siguientes videos los comparto con mis alumnos para ayudarles a entender los diferentes casos de uso de la propuesta presentada:

* [Video-Ejemplo de Proyecto con Autograding](https://www.loom.com/share/5641422c2cc348539265ace04becdd69)
* [Video-Ejemplo de Proyecto sin Autograding](https://www.loom.com/share/e30e21c2fa1a4af5a28bb3c906c5ef0f)
* [Video-Depuración de Proyecto con Autograding](https://www.loom.com/share/f18aa144e3564bf8a7e9eeb7ba6273bc)
* [Video-Depuración de Proyecto sin Autograding](https://www.loom.com/share/2e24fdc494114c7a9b07ad3b56942fe9)
* [Video-Uso y razón de makefile](https://www.loom.com/share/a68377bb88ef4b9f8ed9b3566a5f7276)

## HERRAMIENTAS DE APOYO

Para la creación de **Diagramas UML** dentro del archivo `README.md` de los diferentes repositorios puede usar el lenguaje mermaid, disponible aquí:

* [Diagramas de clases](https://mermaid.js.org/syntax/classDiagram.html)
* [Editor en línea](https://mermaid.live/)
