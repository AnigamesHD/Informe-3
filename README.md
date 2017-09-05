


---

####<strong>Plataforma phylogeny.fr y preparación de datos</strong>

####<strong>Responde:
####1. ¿Qué cosas ofrece este portal?
#####R.- El portal Phylogeny.fr, conecta varios programas de bioinformática para reconstruir árboles filogenéticos desde un conjunto de secuencias. Entre lo que ofrece la página, es posible realizar análisis filogenéticos de tres formas distintas (“One Click”, “Advanced” y “A la Carte”), donde cada modo tiene un orden de opciones de las cuales el investigador puede seleccionar. Además, es posible realizar un análisis con BLAST sobre una secuencia, para explorar secuencias homólogas que se encuentren en la base de datos. Por otra parte, el portal además entrega vínculos de acceso a programas online en la página principal, para alineamientos múltiples, filogenia,  visualización de árboles filogenéticos, entre otras herramientas útiles. 
####2. ¿Para qué tipo de usuario está diseñado?
#####R.- La idea central del portal Phylogeny.fr es asistir y proveer con las herramientas necesarias a biólogos sin experiencia en filogenia, para que sea posible analizar su información de un modo robusto, con fuentes de información comprensibles y flexibles.
####3. Menciona 5 tipos de análisis que se pueden realizar en el portal de acuerdo a la documentación.
#####R.- Análisis del alineamiento, por medio del programa MUSCLE; refinamiento del alineamiento, mediante Gblocks, donde el programa elimina posiciones alineadas de forma pobre y regiones divergentes; análisis de la filogenia, por medio del programa PhyML; y representación del árbol, a través del programa TreeDyn, donde se muestra la imagen final del árbol obtenido mediante las secuencias colocadas, que puede ser luego editado según el interés del usuario. Otro tipo de análisis es mediante BLAST, para explorar secuencias homólogas a la secuencia que se desee analizar, donde el sistema facilita la selección de estas mediante una representación filogenética y un estimador del largo del alineamiento.  

####<strong>-Inferencia de genomas.

####1.- Filogenia inferida con parámetros: ProbCons (Alineamiento), GBlocks (Alignment curation), MrBayes (Filogenia), y TreeDyn (representación del árbol):

![Texto Alternativo](http://i.imgur.com/J21RtSn.png)

####- En ausencia de la etapa de <em>Alingment Curation</em>:

![Texto Alternativo](http://i.imgur.com/FDMVFZO.png)

####2.- Filogenia inferida con parámetros: ClustalW (Alineamiento), Built-in Curer (Alignment curation), TNT (Filogenia), y TreeDyn (representación del árbol):

![Texto Alternativo](http://i.imgur.com/2aCJM3z.png)

####- En ausencia de la etapa de <em>Alingment Curation</em>:

![Texto Alternativo](http://i.imgur.com/1IRKADk.png)

####<strong>Responde:
####1. ¿A qué se refiere el paso de *Alignment curation* y para qué sirve?
#####R.- El programa Gblocks realiza el paso de “Alignment Curation”, el cual consta en que el programa elimina posiciones alineadas de forma pobre y además regiones divergentes, en otras palabras, remueve el “ruido” del alineamiento. Entonces, Gblocks identifica porciones del alineamiento para eliminar posiciones con gaps, incluyendo regiones que no están presentes en todas las secuencias. Si se encuentra un alineamiento ambiguo adyacente de forma inmediata al gap, esa posición también puede ser excluida del alineamiento final, ya que el evento indel puede ser el responsable de la ambigüedad observada. 
####2. ¿Cuál es la diferencia entre BioNJ y Neighbor? 
#####R.- Al dirigirse hacia la documentación del portal, BioNJ y Neighbor, ambos utilizan PHYLYP, el cual es un paquete de programas para inferir filogenias, pero se diferencian en la limitación en el número de taxas, que se refiere a un conjunto de organismos emparentados y agrupados de acuerdo a una clasificación, tomando en cuenta las variables entre especies cuando se realiza un alineamiento. Entonces, el programa BioNJ, puede soportar hasta <5000 taxas, mientras que Neighbor puede tolerar hasta <500 taxas; esto quiere decir la cantidad de taxas que el programa analizará antes de "confundirse", es decir, existe un límite que el programa puede soportar respecto a la cantidad de datos que se adjunten.
####3. Corre de nuevo las filogenias pero esta vez sin *Alignment curation*. ¿Cuál es el efecto en las filogenias?

####-Detalle de la filogenia inferida 1:

![Texto Alternativo](http://i.imgur.com/ojGubMR.png)

####-Detalle de la filogenia inferida 1, sin etapa de curado:

![Texto Alternativo](http://i.imgur.com/pSpQJqZ.png)

#####R.- Si se omite el paso de <em>Alignment curation</em>, que como se mencionó anteriormente es la etapa donde se remueven gaps y regiones ambiguas, puede observarse en la primera filogenia inferida, una pequeña diferencia en el largo de la rama de <em>Macaca mulatta</em>, incrementando el largo de forma leve. En cambio, en la segunda filogenia, no se observan cambios aparentes. Esto puede deberse al parámetro predeterminado del programa que realiza la etapa de filogenia para el largo de rama (cambios esperados por sitio), siendo 0,01 en MrBayes, y 0,5 en TNT, teniendo una resolución de la diferencia del largo en el árbol resultante de la primera inferencia, ya que en el segundo árbol al ser de 0,5, no es posible observar cambios. El incremento del largo de la rama al omitir el curado del alineamiento, se debe a que como no se remueven regiones ambiguas, esto genera más cambios entre las secuencias, pues el largo de la rama en un árbol filogenético indica cantidad de cambio, expresado en sustituciones por sitio. Esto puede comprobarse al dirigirse hacia la pestaña de Filogenia, donde la rama de <em>Macaca mulatta</em>, al omitir el curado del alineamiento, se extiende en el largo, agregando un espacio "-".
####4. Describe las diferencias entre las filogenias que has estimado: cantidad de grupos monofiléticos, relaciones que potencialmente cambiaron, etc.
#####R.- Si se comparan ambas filogenias generadas, en la primera, si se interpreta desde el punto de vista del nodo más reciente (ancestro) de las especies, entonces se puede hablar de monofiléticos, por lo que se observan dos grupos monofiléticos (ramificación a dos ancestros que luego dan lugar a las especies mostradas); en cambio, en el segundo árbol filogenético, se pueden considerar todas las especies como monofiléticos, al surgir del mismo ancestro, si se interpreta el árbol desde el origen. Ahora bien, la primera filogenia generada, puede decirse que los dos 2 grupos monofiléticos (especies que provienen de los nodos que se observan) podria hablarse además que son monofiléticos entre sí, si se interpreta desde el origen. En el segundo árbol, se pueden observan además 3 grupos monofiléticos, si se toman de cada nodo. La relación que cambia entre ambas filogenias, es entre <em>Chlorocebus sabaeus</em> y <em>Macaca mulatta</em>; ya que se interpretan como provenientes del mismo ancestro más reciente en el generado a través de MrBayes, en cambio, el generado por TNT, las especies se alejan evolutivamente respecto al ancestro de donde provinieron, colocando a <em>Chlorocebus sabaeus</em> como una ramificación aparte de <em>Macaca mulatta</em>.

---

#####*Detalle al margen: para observar cambios más evidentes, intenté agregar más taxas, basándome en algunos de los ortólogos del gen SRY, pero al parecer por la lejanía entre especies, el programa no logró terminar de inferir la filogenia, aún colocando especies que podrian estar más cercanas a los adjuntos.
