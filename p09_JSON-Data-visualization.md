# Práctica 9. JSON Data visualization
### Factor de ponderación: 8

### Objetivos
Los objetivos de esta tarea son poner en práctica:
* Gestión de ficheros remotos en formato JSON.
* Manipulación, gestión, análisis y representación de datos.
* Conceptos básicos de Programación Gráfica en TypeScript usando la API Canvas.
* Metodologías y conceptos de diseño y Programación Orientada a Objetos en TypeScript.
* Principios y Buenas prácticas de programación Orientada a Objetos.

### Rúbrica de evaluacion del ejercicio
Se señalan a continuación los aspectos más relevantes (la lista no es exhaustiva)
que se tendrán en cuenta a la hora de evaluar esta práctica:
* Se valorará la realización de las diferentes tareas que se proponen
* El comportamiento del programa debe ajustarse a lo descrito en este documento
* Capacidad de la programadora de introducir cambios en el programa desarrollado
* Se acredita conocimiento y puesta en práctica de principios y buenas prácticas de programación orientada a objetos
* Saber corregir bugs en sus programas utilizando el depurador de Visual Studio Code
* Deben usarse estructuras de datos adecuadas para representar los diferentes elementos que intervienen en el problema
* Ser capaz de desarrollar programas simples en TypeScript en el entorno Linux de la VM de la asignatura usando
  `ts-node`
* Ser capaz de generar documentación para sus programas TS utilizando
  [TypeDoc](https://typedoc.org/)
  y de visualizar dicha documentación en un servidor web
* El alumnado debe ser capaz de resolver problemas tanto en JS como en TS en la plataforma Exercism subiendo sus soluciones a la misma
* Ser capaz de desarrollar tests unitarios para sus programas utilizando
  [Jest](https://jestjs.io/)
* Acreditar su capacidad para configurar y utilizar 
  [ESLint](https://eslint.org/)
y que es capaz de trabajar con la misma en Visual Studio Code
* Acreditar que conoce las etiquetas de 
  [JSDoc](https://jsdoc.app/)
* Acreditar que es capaz de generar documentación para sus programas utilizando
  [TypeDoc](https://typedoc.org/)
y que es capaz de generar documentación para sus programas utilizando la herramienta
* El alumnado ha de acreditar que es capaz de desarrollar programas de la plataforma Jutge
* Se comprobará que el código que el alumnado escribe se adhiere a las reglas de las Guías de Estilo de Google
  para Javascript y/o TypeScript
* Todas las prácticas realizadas hasta la fecha, incluída la que se presenta para su evaluación, se encuentran alojadas en repositorios privados de GitHub.
* Acreditar que es capaz de editar ficheros de forma remota en su VM usando Visual Studio Code

### Indicaciones de caracter general

El programa que desarrolle ha de ser orientados a objetos.
Ponga en práctica los principios de abstracción y encapsulamiento característicos 
de la OOP así como las buenas prácticas, principios y patrones que han sido expuestos en las clases de la asignatura.

Previo a la implementación de cada clase, diseñe y desarrolle un conjunto de tests para probar el correcto
funcionamiento de todos los métodos que desarrolle.

Configure para esta práctica una página web que sirva de índice para mostrar la documentación generada por
TypeDoc para el ejercicio que se propone.

Configure adecuadamente ficheros `package.json` y `tsconfig.json` en el directorio raíz de su ejercicio, 
de modo que ejecutando `npm install` queden instaladas todas las dependencias del proyecto.

En el desarrollo de esta práctica, utilice el depurador integrado en el navegador para confirmar que el flujo
de ejecución de su programa es el correcto.


### Lectura de datos en formato JSON desde un servidor remoto

En el directorio `read-JSON-app` de esta práctica puede hallar un ejemplo de aplicación que lee datos de un
fichero en formato JSON alojado en un servidor remoto.

Comience por ejecutar 

`npm install`

para instalar los paquetes necesarios para la aplicación.

A continuación, ejecute `tsc` en el directorio `www` para compilar la aplicación `read-json.ts` de ese
directorio. 
La compilación generará el fichero `read-json.js` que se enlaza en la página `index.html` que se encuentra en
ese mismo directorio.

Ejecute `npm start` para arrancar la aplicación.
Un mensaje le indicará la URL en la que puede visualizar en un navegador la aplicación.
En la página que se abre (`index.html`) verá solamente una página con un texto explicativo.
Si abre (*Herramientas para desarrolladores*) la consola de esa página verá que en consola se está imprimiendo
un vector de datos de 1736 componentes.

Estudie los comentarios que figuran en la cabecera de los ficheros `read-json.ts` (directorio `www` de la
aplicación) y `app.js` (directorio `web-server`).

El programa `app.js`, similar al que se utilizó en la práctica 1 de la asignatura, configura un servidor de
ficheros basado en Express, mientras que `read-json.ts` es el programa principal que consume los datos desde
el servidor local.
Tal como se explica en la documentación de estos programas, consumiendo los datos desde un mismo servidor en
el que se ejecutan ambos programas, obviamos ciertas restricciones de seguridad que imponen los navegadores a
la hora de consumir datos desde un servidor externo (política CORS).

Ambos programas utilizan la API 
* [Fetch](https://javascript.info/fetch)
En el caso del servidor local, para leer un fichero JSON con datos de población de Tenerife desde una URL
externa, y en el caso de la aplicación cliente para leer el fichero JSON desde el *endpoint* `data` que
configura el servidor local.

El programa `read-json-ts` define la interfaz *PopulationData* (podría haberse utilizado una definición de
tipo en lugar de una interfaz) para caracterizar el tipo de datos presentes en el fichero JSON que se va a
leer.
Ha de tenerse en cuenta (a) que esta definición se introduce para disponer de un control de tipos de datos más
exhaustivo (b) que esa aplicación depende directamente del tipo de datos que se pretende leer y que habría que
conocer a priori.

No es un objetivo de esta práctica (ni de esta asignatura) el estudio de los protocolos de comunicación ni las
restricciones y características que intervienen en estas comunicaciones.

El objeto de estos fragmentos de código es ofrecer al alumnado un esqueleto simple que pueden tomar como punto
de partida para sus propios diseños, siendo el objetivo de esta práctica leer datos (de diverso tipo)
procedentes de una URL remota y representarlos gráficamente en un lienzo (canvas) de HTML5.




## Referencias
* [Fetch](https://javascript.info/fetch)
* [TypeDoc](https://typedoc.org/)
* [Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html)
* [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)
* [ESLint](https://eslint.org/)
* [JSDoc](https://jsdoc.app/)
