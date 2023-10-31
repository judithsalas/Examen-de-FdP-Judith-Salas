# Examen-de-FdP_Judith-Salas
Judith M.ª Salas García
# *1º Explica que es un “Pull Request” en Github.*

El **pull request** es una herramienta que se utiliza para contribuir a un proyecto ajeno con una serie de modificaciones propuestas. Se envía una solicitud al usuario propietario del repositorio original y esta es aceptada o rechazada por él.


# *2º ¿Qué es un conflicto de fusión (merge conflict) en Git? Explica como resolverías este conflicto.*

Un merge conflict ocurre debido a que hay coincidencias en el código de los archivos, ya que al fusionarlos ya existen elementos dentro de ellos (no están vacíos). Para solucionarlos deberemos de meternos en los editores de texto y borrar manualmente los conflictos (ejemplos: ------HEAD, ---------, etc.).


# *3º Imaginemos que tenemos dos ramas, la principal llamada “main” y la rama “examen_parcial”. ¿Qué procedimiento se debería seguir para fusionar (merge) ambas ramas?*

Para fusionar dos ramas, en primer lugar nos tendríamos que posicionar (HEAD), en una de las ramas con el comando **git checkout <nombre de la rama, por ejemplo main>**, una vez dentro de la rama con **git merge <nombre de la otra rama, por ejemplo examen_parcial>**, ya comenzaríamos a hacer el merge donde entrarían en conflicto los archivos de las ramas, por lo tanto se deberían de solucionar para continuar con la integración. Estos "conflictos" se deberán de solucionar mediante la apertura de los archivos en editores de texto (como nano o VI) y solucionarlos de forma manual (uso de comandos como **nano <archivo>**). Una vez resueltos los conflictos, proseguiremos con el merge comprobando que en los archivos de la rama en la que nos encontramos están los de la otra. Una vez ya se ha integrado la información en la rama, volvemos a cambiarnos de branch con **git checkout <examen_parcial>** y se vuelve a mergear con **git merge <nombre de la rama mergeada anteriormente, main>**. Una vez ya nos llega el mensaje de confirmación de que está correctamente mergeada ya estarían integradas las ramas. Finalmente realizamos un commit con el mensaje de que las ramas se han integrado como punto de guardado **git commit -m "ramas integradas"**.


# *4º Has realizado un commit, pero luego descubres un error importante en los cambios que has incluido. Necesitas revertir este último commit para regresar tu proyecto al estado anterior, pero deseas mantener los cambios realizados en tu área de trabajo. Explica el comando de Git que utilizarías para llevar a cabo esta acción.*

El comando que utilizarías es **git reset --hard HEAD~1**, ya que su función es quitar el último commit realizado. Puedes comprobar la lista de commits en vigor con git log --oneline.


# *5º ¿Cómo se realiza un fork de un repositorio en GitHub y para qué se utiliza comúnmente esta acción?*

El fork a un repositorio se realiza desde github acudiendo al repositorio objetivo y pulsando el boton fork, una vez se ha realizado correctamente se contará con un nuevo repositorio que es similar al original. Se utiliza para trabajar sobre un repositorio de forma externa para no cambiar el trabajo de otros compañeros, para trabajar en paralelo.


# *6º Te encuentras trabajando en un proyecto y necesitas llegar a un archivo específico llamado "archivo.txt". Este archivo está ubicado dentro de una estructura de directorios en tu sistema.*

a)      Desde tu posición actual en el directorio raíz (home) de tu proyecto, ¿cómo llegarías al directorio que contiene "archivo.txt", el cual está dentro del directorio "UAX", el cual a su vez está dentro del directorio "Universidad", que se encuentra dentro del directorio "Nombre_del_alumno (raíz)"? Proporciona el comando exacto que usarías y especifica qué tipo de ruta es.

En primer lugar utilizaría **ls** para ver un listado de los directorios y ficheros con los que cuento, posteriormente navegaría con **cd** hasta el directorio de interés, y nuevamente repetiría el proceso hasta llegar al fichero deseado, en este caso el "archivo.txt".
Se trata de una ruta absoluta ya que parte desde el directorio de raíz.

b)       Si te encuentras actualmente dentro del directorio "Universidad", ¿cómo accederías al directorio que contiene "archivo.txt"? Proporciona el comando exacto que usarías y especifica qué tipo de ruta es.

**cd UAX**, se trata de una ruta relativa.


# *7º Te han asignado la tarea de trabajar en un proyecto de código abierto alojado en GitHub. Como nuevo colaborador, se espera que sigas las mejores prácticas para el manejo del código fuente utilizando Git. Que comandos de Git utilizaría para las siguientes tareas:*

1) Clonar el Repositorio:

**b) git clone**

2) Crear una Nueva Rama:

**a) git branch**

3) Cambiar entre Ramas:

**c) git checkout**

4) Añadir Cambios al Área de Preparación (Staging):

a) **git add**

5) Realizar un Commit:

**b) git commit**

6) Publicar la Rama en el Repositorio Remoto:

**b) git push**

7) Actualizar tu Rama Local con Cambios del Remoto:

**c) git pull**

8) Fusionar Cambios de otra Rama a tu Rama Actual:

**d) git merge**

9) Revertir Cambios Locales:

**a) git reset --hard**

10) Revisar el Historial de Commits:
    
**c) git log**


# *8º Eres parte de un equipo de desarrollo trabajando en un proyecto de software matemático. La estructura de ramas de tu proyecto en Git se ve de la siguiente manera:*

·         **main**: La rama principal donde el código es estable y listo para producción. (AA)

·         **develop**: Una rama de desarrollo donde se integran las nuevas características antes de pasar a main. 

·         **matemáticas**: Una rama donde tú y tu equipo están trabajando en resolver un problema.

·         **Diseño UX**: Una rama donde el equipo de diseño trabaja en desarrollar la vista de las integraciones por parte del equipo de matemáticas.

*Durante el desarrollo, tu equipo ha completado una serie de algoritmos importantes en la rama matemáticas y está listo para integrarlos en la rama develop. Simultáneamente, el equipo de diseño ha hecho cambios significativos en la rama diseño-UX, que también deben ser integrados en develop.*

Tu tarea es coordinar la integración de estas dos ramas en develop asegurándote de que se manejen adecuadamente los conflictos, se mantenga la calidad del código y se respete la funcionalidad tanto del lado matemático como del diseño UX.

Describe detalladamente los pasos y consideraciones que tomarías para lograr esta tarea, incluyendo cómo manejarías los posibles conflictos de fusión y cómo asegurarías que la integración final en develop sea estable y funcional. 


En primer lugar nos cambiaríamos de rama a la develop con <Git checkout develop> para realizar un merge de la rama matemáticas primero y a continuación, un merge de la rama diseños UX. En primer merge <git merge matemáticas>, podremos ver las diferencias y conflictos a resolver con **git diff matematicas develop**. Se abrirán de forma manual los ficheros a resolver con **nano <archivos>** y se borrarán los elementos que ocasionen los conflictos (control s para guardar y control x para salir del editor de texto). Una vez resultos se añadirán los cambios y realizará un commit como punto de guardado de la resolución de los conflictos de la rama matemáticas en la develop (**git commit -m "integración resuelta"**). Una vez ya integrada esta rama, procederemos a mergear la rama "Diseños UX" con **git merge "Diseños UX"**, y volveremos a resolver los conflictos con editores de texto (vi, nano, notas, etc.). Se volverán a commitear los cambios con **git commit -m "integrada la rama"**.
Con **git status -s**, podríamos ver en forma de columna el estado de los archivos y comprobar si están resultos o no los conflictos.





# *9º Pregunta práctica del módulo 3: Repositorios local y remoto*
Recientemente, has completado una práctica en la que creaste un repositorio tanto local como remoto para una calculadora web sencilla. La práctica implicaba varios pasos clave, incluyendo la creación del repositorio, la adición y el registro de cambios, y finalmente la subida del repositorio local al remoto en GitHub.
Considerando los pasos realizados durante la práctica, responde la siguiente pregunta:
¿Cuál de las siguientes afirmaciones describe mejor el proceso que seguiste para añadir el botón de "x^4" a tu calculadora web y subir los cambios al repositorio remoto? 

**C) Añadiste el botón "x^4" al archivo "index.html" en tu repositorio local, creaste un commit con los cambios y luego subiste el repositorio local al remoto en la rama principal (master).**

