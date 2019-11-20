# Tarea Citas Clinica
## Profesor: Andrés Rubio del Río
## Alumno:

Tu tarea va a consistir en gestionar las citas de los pacientes de una clínica. La clínica quiere almacenar la fecha y el día de las citas de los diferentes pacientes. Para los pacientes almacenará su nombre bien formateado, su DNI comprobando que es válido y su teléfono comprobando también que es válido. El programa permitirá insertar nuevas citas, buscar citas por el día, borrar una cita, mostrar todas las citas y mostrar las citas para un día dado.

He subido a este repositorio de GitHub un esqueleto de proyecto gradle que ya lleva incluidos todos los test necesarios que el programa debe pasar. 

Para ello te muestro un diagrama de clases para el mismo y poco a poco te iré explicando los diferentes pasos a realizar:

![Diagrama de clases para citasclinica](src/main/resources/citasClinica.png)

- Lo primero que debes hacer es realizar un **fork** del repositorio donde he colocado el esqueleto de este proyecto.
- Clona tu repositorio remoto recién copiado en GitHub a un repositorio local que será donde irás realizando lo que a continuación se te pide. Modifica el archivo `README.md` para que incluya tu nombre en el apartado "Alumno". Realiza tu primer **commit**.
- Crea la clase `Paciente` en el paquete indicado en el diagrama:
    1. Crea los diferentes atributos que se indican en el diagrama de clases con su visibilidad adecuada.
    2. Crea el método `formateaNombre`. Este método debe normalizar un nombre eliminando caracteres en blanco de sobra y poniendo en mayúsculas la primera letra de cada palabra y en minúsculas las demás.
    3. Crea el método `comprobarLetraDni`. Este método hará uso de los grupos de las expresiones regulares (para ello has debido definir la expresión regular con grupos) para quedarse con el número por un lado y con la letra por otro. Para saber si la letra es válida puedes seguir las instrucciones del siguiente enlace: [Comprobar letra dni](https://calculadorasonline.com/calcular-la-letra-del-dni-validar-un-dni/).
    4. Crea los métodos `get` y `set` con la visibilidad adecuada. Estos métodos deberán hacer las comprobaciones pertinentes y en su caso lanzar la excepción correspondiente.
    5. Crea el constructor con parámetros.
    6. Crea el constructor copia.
    7. Crea los métodos `equals` y `hashCode`, sabiendo que dos pacientes se considerarán iguales si su DNI es el mismo.
    8. Crea el método `getIniciales`. Este método devolverá las iniciales del nombre.
    9. Crea el método `toString`. Este método devolverá una cadena representando la información de los diferentes atributos, pero para el caso del nombre le antepondrá sus iniciales encerradas en paréntesis. Realiza un **commit** con la creación de esta clase.
- Crea la clase `Cita` en el paquete indicado en el diagrama:
    1. Crea los diferentes atributos que se indican en el diagrama de clases con su visibilidad adecuada.
    2. Crea los métodos `get` y `set` con la visibilidad adecuada. Estos métodos deberán hacer las comprobaciones pertinentes y en su caso lanzar la excepción correspondiente. Recuerda no quedarte con la referencia de Paciente ni devolverla, si no una copia del mismo.
    3. Crea el constructor con parámetros.
    4. Crea el constructor copia.
    5. Crea los métodos `equals` y `hashCode`, sabiendo que dos citas se considerarán iguales si su fecha y hora son las mismas.
    6. Crea el método `toString`. Este método devolverá una cadena representando la información de los diferentes atributos. Realiza un **commit** con la creación de esta clase.
- Crea la clase `Citas` en el paquete indicado en el diagrama:
    1. Crea los diferentes atributos que se indican en el diagrama de clases con su visibilidad adecuada.
    2. Crea los métodos `get` (sin parámetros) que se indican en el diagrama de clases.
    3. Crea los métodos `capacidadSuperada` y `tamanoSuperado`.
    4. Crea el método `buscarIndice` que buscará la cita pasada dentro de la colección de citas y devolverá su índice en el caso que la encuentre o el tamaño más uno en caso de que no la encuentre.
    5. Crea el método `insertar` que insertará una copia de la cita pasada detrás de la última cita y deberá lanzar las excepciones pertinentes ante cualquier situación anómala.
    6. Crea el método `buscar` que devolverá la copia de la cita que estamos buscando (ten en cuenta que como dos citas se consideran iguales si su fecha y hora son iguales, el paciente de la cita a buscar podría ser cualquiera) o `null` en caso de que no la encuentre.
    7. Crea el método `desplazarUnaPosicionHaciaIzquierda` al que le pasamos un índice y desplazará una posición a la izquierda todas las citas que estén a su derecha.
    8. Crea el método `borrar` que borrará la cita pasada, desplazando hacia la izquierda todas las citas que estén a su derecha, en caso de encontrarla o lanzará una excepción en caso contrario.
    9. Crea el método `getCitas` al que le pasaremos una fecha y devolverá todas las citas para esa fecha. Realiza un **commit** con la creación de esta clase.
- Crea el enumerado `Opciones` en el paquete indicado en el diagrama:
    1. Crea el enumerado `Opciones` tal y como se indica en el diagrama de clases. Realiza un **commit** con la creación de este enumerado.
- Crea la clase de utilidades `Consola` en el paquete indicado en el diagrama:
    1. Crea su constructor teniendo en cuenta que es una clase de utilidades y que no tiene sentido instanciar objetos de la misma.
    2. Crea el método `mostrarMenu` que mostrará las diferentes opciones de nuestro programa (insertar, buscar, borrar, mostrar todas las citas, mostrar las citas de una fecha y salir).
    3. Crea el método `elegirOpcion` que pedirá que elijamos la opción y devolverá la instancia del enumerado `Opciones` correspondiente.
    4. Crea el método `leerPaciente` que nos pedirá los datos correspondientes al paciente y devolverá el mismo en el caso que los datos introducidos sean correctos o propague la excepción correspondiente en caso contrario.
    5. Crea el método `leerFechaHora` que nos pedirá que introduzcamos una cadena correspondiente a una fecha y hora en el formato adecuado y devolverá el objeto `LocalDateTime` correspondiente. Esto se repetirá mientras la fecha y hora introducida no sea válida.
    6. Crea el método `leerCita` que pedirá el paciente y la fecha y hora de la cita y devolverá la cita correspondiente en el caso que los datos introducidos sean correctos o propague la excepción correspondiente en caso contrario.
    7. Crea el método `leerFecha` que nos pedirá que introduzcamos una cadena correspondiente a una fecha en el formato adecuado y devolverá el objeto `LocalDate` correspondiente. Esto se repetirá mientras la fecha introducida no sea válida. Realiza un **commit** con la creación de esta clase.
- Crea la clase `MainApp` en el paquete indicado en el diagrama:
    1. Crea los diferentes atributos que se indican en el diagrama de clases con su visibilidad adecuada.
    2. Crea el método `insertarCita` que nos pedirá una cita y la insertará si es posible o informará del problema en caso contrario.
    3. Crea el método `buscarCita` que nos pedirá la fecha y hora y nos mostrará la cita para dicha cita y hora o nos informará de que no existe.
    4. Crea el método `borrarCita` que nos pedirá la fecha y hora de la cita a borrar y la borrará si es posible o informará del problema en caso contrario.
    5. Crea el método `mostrarCitas` que mostrará todas las citas almacenadas si es que hay o si no nos informará de que no hay citas.
    6. Crea el método `mostrarCitasDia` que nos pedirá una fecha y mostrará todas las citas almacenadas para esa fecha si es que hay o si no nos informará de que no hay citas.
    7. Crea el método `ejecutarOpcion` que dada una opción la ejecute.
    8. Crea el método `main` que nos mostrará el menú de la aplicación, nos pedirá una opción y la ejecutará mientras no elijamos la opción salir. Realiza un **commit** con la creación de esta clase. Finalmente realiza el **push** hacia tu repositorio remoto en GitHub.

##### Se valorará:
- La indentación debe ser correcta en cada uno de los apartados.
- El nombre de las variables debe ser adecuado.
- Se debe utilizar la clase `Entrada` para realizar la entrada por teclado.
- El programa debe pasar todas las pruebas que van en el esqueleto del proyecto y toda entrada del programa será validada, para evitar que el programa termine abruptamente debido a una excepción.
- La corrección ortográfica tanto en los comentarios como en los mensajes que se muestren al usuario.
