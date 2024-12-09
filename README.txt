
Proyecto-Base

Este es un proyecto web del Hospital Clinico Dr Victor Ramirez que utiliza Bootstrap, y SASS para crear un sitio responsivo con un sistema de navegaci�n. El proyecto incluye p�ginas como "Inicio", "Equipo M�dico" y "Contacto".

Tabla de Contenidos

Tecnolog�as Usadas
Estructura del Proyecto
Instalaci�n
Uso
Scripts
Contribuciones
Licencia

Tecnolog�as Usadas

Bootstrap: Para estilos responsivos y componentes predefinidos.
SASS: Para la escritura de estilos en CSS con caracter�sticas adicionales como variables y anidamiento.
JavaScript (ES6): Para la l�gica del cliente.

Estructura del Proyecto

Index2.html: Contiene la informacion generla del hospital, mision, vision y bienvenida
equipo2.thml:Contiene la informacion del listado de servicios y profesionales que conforman el hospital.
contacto2.html: Contiene la informacion de la ubicacion geografica de la institucion y un formulario de contacto para hacer llegar consultas.
/img: Contiene las im�genes utilizadas en el proyecto.
/js: Contiene los archivos JavaScript.
/lib: Contiene los archivos para los estilos de Boostrap.
/styles: Contiene los archivos para los estilos de la pagina definida por el desarrollador.

Instalaci�n

Clona este repositorio:

git clone https://github.com/FabianPena/proyecto-base.git
cd tu-repo


Instruciones para visualizacion:

Se debe dejar todos los archivos en una misma carpeta y luego abrir con su navegador el archivo llamado "Index2.html" que es la pagina principal del proyecto.


Actualizaciones README especificar Modulo 3 - Laboratorio Virtual 1

- Explicación de cómo se implementaron los objetos JSON y las operaciones
realizadas (clonación, merge, recorrido).

Implementación de Objetos JSON y Operaciones Realizadas
En este proyecto se utilizó JSON (JavaScript Object Notation) para representar y manipular la información de los doctores y sus servicios. JSON es un formato ligero y fácil de leer/escribir que se utiliza para el intercambio de datos.

Objetos JSON
Se implementaron objetos JSON para representar a los doctores del hospital con propiedades como nombre, especialidad, años de experiencia, disponibilidad (horarios) y contacto (teléfono y email). A continuación se muestra un ejemplo del objeto JSON para un doctor:

A continuacion un ejemplo del JSON de los doctores

{
  "nombre": "Dr. Victor Retamal",
  "especialidad": "Medicina General",
  "anos_experiencia": 6,
  "disponibilidad": {
    "lunes": "08:00 - 12:00",
    "martes": "08:00 - 12:00",
    "miercoles": "08:00 - 12:00",
    "jueves": "08:00 - 12:00",
    "viernes": "08:00 - 12:00"
  },
  "contacto": {
    "telefono": "555-1234",
    "email": "dr.victor@hospital.com"
  },
  "foto": "img/drvictor.png"
}

Operaciones con Objetos JSON

Realizamos las siguientes operaciones comunes con los objetos JSON:

1.- Clonación: Utilizamos una copia profunda (deep copy) con JSON.parse(JSON.stringify()) para Clonar el JSON de los doctores y poder modficar la copia sin que afecte al original.

2.- Merge (Fusión): Usamos el operador de propagación ... para fusionar el objeto de los doctores con otro objeto que contiene los servicios médicos disponibles. Esta operación permitió combinar dos conjuntos de datos distintos:

Ejemplo de la linea de codigo donde se hace el Merge: const doctoresYServicios = {...doctores, ...servicios};

3.- Recorrido y stringify: Se recorrió el objeto JSON utilizando un bucle forEach para mostrar la información de cada doctor en el navegador. Además, se utilizó JSON.stringify() para convertir los objetos en una cadena JSON legible.



- Explicación de las estructuras de datos implementadas (arreglos, pilas, colas) y
su utilidad en el proyecto.

El proyecto utiliza varias estructuras de datos que permiten gestionar eficazmente la información del hospital.

Arreglos

Se utilizaron arreglos para almacenar la lista de doctores y realizar operaciones de búsqueda, inserción y eliminación. Ejemplos de operaciones realizadas:

*Agregar un doctor a la lista de doctores.
*Eliminar un doctor de la lista.
*Buscar un doctor dentro del arreglo utilizando el método find().

Utilidad: Los arreglos son útiles cuando necesitamos mantener un conjunto de datos ordenado o realizar búsquedas de manera eficiente. En este caso, usamos los arreglos para manipular la lista de doctores.

Pilas

Una pila (LIFO - Last In First Out) fue implementada para gestionar las citas de los pacientes. Cada vez que se agendaba una cita, se añadía a la pila con el método push(). Para eliminar una cita o acceder a la más reciente, se utilizó el método pop().

Utilidad: Las pilas son útiles cuando necesitamos realizar un seguimiento de las citas en el orden en que fueron agendadas. La pila ayuda a procesar primero las citas más recientes, lo cual es útil en escenarios como emergencias o citas urgentes.

Colas

Se utilizó una cola (FIFO - First In First Out) para gestionar la llegada de pacientes. A medida que un paciente llegaba, se añadía al final de la cola con el método push(). Cuando se atendía a un paciente, se eliminaba de la cola usando shift().

Utilidad: Las colas son apropiadas para gestionar procesos en los que el primer elemento en llegar es el primero en ser procesado, como en el caso de la atención al paciente. Esto asegura que los pacientes sean atendidos en el orden en que llegaron.



- Descripción de los algoritmos implementados y su complejidad.

Algoritmos Implementados

Búsqueda en el Arreglo de Doctores

Se implementó un algoritmo de búsqueda lineal para encontrar un doctor específico dentro del arreglo de doctores. Este algoritmo recorre el arreglo y compara cada elemento con el doctor buscado:

Ejemplo de uso de algoritmo de busqueda lineal:

function buscarDoctor2(nombre) {
    for (let i = 0; i < doctoresArreglo2.length; i++) {
        if (doctoresArreglo2[i] === nombre) {
            return "Doctor encontrado: " + doctorBuscado;
        }
    }
    return "Doctor no encontrado: " + doctorBuscado;
}

Complejidad temporal (Big-O): O(n), donde n es el número de doctores en el arreglo. El algoritmo realiza una búsqueda secuencial, por lo que en el peor de los casos, se recorre todo el arreglo.


Ordenamiento de Doctores por Experiencia (Algoritmo de Burbuja)

Para ordenar la lista de doctores por años de experiencia, se implementó el algoritmo de ordenamiento por burbuja (Bubble Sort). Este algoritmo compara cada par de elementos adyacentes y los intercambia si están en el orden incorrecto. El proceso se repite hasta que el arreglo está completamente ordenado.

Ejmeplo de algoritmo de busqeda de Burbuja:

function ordenarDoctoresPorExperiencia(doctores) {
    let n = doctores.length;
    for (let i = 0; i < n; i++) {
        for (let j = 0; j < n - i - 1; j++) {
            if (doctores[j].experiencia > doctores[j + 1].experiencia) {
                let temp = doctores[j];
                doctores[j] = doctores[j + 1];
                doctores[j + 1] = temp;
            }
        }
    }
    return doctores;
}

Complejidad temporal (Big-O): O(n²), donde n es el número de doctores. En el peor de los casos, el algoritmo realiza múltiples comparaciones e intercambios, lo que lo hace menos eficiente en grandes volúmenes de datos.


Creditos:
Imagenes sacada de buscador Google.