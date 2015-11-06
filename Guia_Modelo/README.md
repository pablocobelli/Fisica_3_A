Como componer una guia con este modelo
--------------------------------------

En primer lugar es necesario hacer una copia local de los archivos de formato
especificos. El archivo `tex` de la guia debe componerse siguiendo los 
lineamientos generales descriptos a continuacion.

Declaraciones iniciales
-----------------------

El documento `tex` esta encabezado por la eleccion de la clase asociada.
Para generar una guia de problemas, la opcion es 

    \documentclass[problemas]{guia}

Definiendo el titulo y numero de la guia
----------------------------------------

El numero de la guia practica se especifica haciendo

    \def \practnum {5}

si se desea especificar que se trata de la guia numero 5. 

El titulo completo de la guia se especifica mediante el comando

    \def \practica {Frecuencia de resonancia de un circuito RLC}

La clase provee la posibilidad de declarar un titulo alternativo mas corto,
que sera utilizado automaticamente si, al procesar el documento, el compilador
de LaTeX detecta que el titulo completo es demasiado largo para el encabezado
(header) de pagina. Para suministrar la version 'corta' del titulo, basta 
con declarar 

    \def \practcur {Circuito RLC}

Estas definiciones se realizan **antes** de introducir el 
`\begin{document}`. 

Acerca de la inclusion de figuras
---------------------------------
En el caso de las guias de trabajos de laboratorio, la inclusion de figuras
se realiza en la forma usual, via el codigo

    \begin{figure}
        \includegraphics{archivo_figura}
        \caption{Epigrafe de la figura.}
        \label{fig:label_de_la_figura}
    \end{figure}

Por otro lado, las figuras asociadas a los problemas de las guias de 
ejercicios, se incluyen mas facilmente a traves de la propia definicion
del problema (ver seccion aparte para mas detalle):

    \begin{problema}[archivo_figura]
        Si un auto viaja a 100 km/h, que distancia recorre en 30 minutos?
    \end{problema}

En ambos casos, se recomienda poner los archivos de figura en un subdirectorio
cuyo nombre es el mismo que el archivo fuente `LaTeX` que da nombre a la guia.
No hace falta definir el `path` de figura (via `\graphicspath{...}`) ya que
esto **lo hace automaticamente** el archivo `estilo.tex`. 


Definiendo el objetivo y las tematicas  de la guia
--------------------------------------------------

**Luego** del `\begin{document}` y **antes** del `\maketitle` de rigor, 
la definicion del objetivo de la guia y de las tematicas en ella abordadas se
realiza mediante:

    \objetivo{Medir la frecuencia de resonancia de un circuito RLC. 
              \tematicas{Resonancia, circuito RLC} }

Observense dos cosas:
- `\tematicas` queda definido **dentro** de `\objetivo`. 
- El argumento de tematicas no requiere de punto final.

Habiendo definido el objetivo y las tematicas, puede pedirse la construccion
del titulo mediante el comando usual `\maketitle`.

Acerca del cuerpo de la guia
----------------------------

A continuacion el cuerpo de la guia se define en la forma usual, y se dispone
de todos los comandos de LaTeX habituales: `\begin{section}`, etc.  

Incorporar la bibliografia sugerida o de referencia
---------------------------------------------------

La bibliografia sugerida o de referencia puede incorporarse al final del 
cuerpo de la guia, aun cuando dichas referencias no hayan sido citas 
explicitamente en el cuerpo. Esto se logra haciendo

    \nocite{Alonso1998, Crawford1994, Purcell1988}

Ya sea que se utilice esta forma o la usual `\cite{Alonso1988}` en el texto,
la inclusion de la bibliografia se hace en la forma usual mediante

    \bibliographystyle{babunsrt}
    \bibliography{Referencias}

La primera linea emplea el estilo bibliografico `babunsrt`, asociado al 
paquete `babelbib`, que permite customizar el texto de la bibliografia a
cualquier idioma (en este caso, el español). El estilo `babunsrt` es el 
equivalente del `unsrt` estandar. 

Finalmente, la segunda linea apunta al archivo `Referencias.bib` que lista
y nuclea **todas** las referencias asociadas a la totalidad de las guias.

Entornos adicionales provistos por la clase
-------------------------------------------

Hasta el momento la clase provee los siguientes entornos adicionales, 
- `problema`
- `sabermas`

sabermas
--------
La idea es emplear este entorno para motivar al estudiante a leer conceptos
mas avanzados asociados a esta guia. Para hacer uso del entorno, se emplea la
construccion habitual

    \begin{sabermas}
    ...
    \end{sabermas}

problema
--------
Este entorno sirve para las guias de problemas, definiendo en forma completa
un ejercicio o problema. Admite ademas un campo
**opcional** mediante el cual se especifica el nombre de fichero de la figura
asociada al ejercicio en cuestion (si tiene una; de lo contrario, al dejarlo
vacio o no especificarlo, no se incorpora figura alguna).

    \begin{problema}[nombre_del_archivo_de_figura.extension]
        Un auto se mueve a 10 km/h. Calcule la distancia que habra recorrido
        en 1 hora. 
    \end{problema}

Las figuras asociadas a cada problema se ubican automaticamente de la siguiente
forma:
- Las figuras se escalan de forma tal de caber en un area de ancho 5 cm.
- Se les agrega  un epigrafe que las vincula al problema.
- Si se trata de la figura de un problema cuyo numero es impar, la figura va
  al lado del texto del problema, la derecha de la pagina.
- Si es la figura de un problema par, la figura va a la izquierda. 





