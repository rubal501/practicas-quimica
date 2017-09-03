# practicas-quimica

Este repositorio es para poder trabajar de manera colaborativa en las practicas de
queimica, usando Github para poder controlar los cambios de los archivos Tex.

### Recomendaciones previas
Antes que nada recomiendo que le eches un vistazo a la documentacion de [ShareLatex][f4ff5bf4] y en caso de
tener una duda demasiado compleja uses [StackExchange][69bec2cd].

Para editar los archivos de Latex estoy usando [TexMaker][73e2c5e2] el cual es un editor que facilita demansiado el trabajo(Si encuentras otro que te acomode mejor usalo).

La complejidad de Github depende si los usas con un sistema grafico o en la terminal. Personalmente recomiendo la ultima, ya que a pesar de lo intimidante que parece al principio, solo es necesario algo de practica y aprenderte minimo 5 comando. En caso de que decidas irte por la ocpion grafica te recomiendo [GitKraken][6a601149].

### Formato
```
\documentclass[letter]{article}
\usepackage[utf8]{inputenc}
\usepackage[spanish]{babel}```
importante ponerlo para tener español

```
\usepackage{tikz}
\usetikzlibrary{shapes.geometric, arrows}```
permite hacer diagramas de flujo

```
\graphicspath{ {images/} }
\usepackage{natbib}
\usepackage{graphicx}
\usepackage{wrapfig}
```


\graphicspath es para seleccionar la carpeta donde estan las imagenes

```
\title{Practica1}
\author{
Muñoz Carpio Erick David
\and
Rubalcava Cortés Javier Roberto
}
\date{\today}
```
Datos basicos(No moverle)

```
\tikzstyle{startstop} = [rectangle, rounded corners, minimum width=3cm, minimum height=1cm,text centered, draw=black, fill=red!30]

%%\tikzstyle{io} = [trapezium, trapezium left angle=70, trapezium right angle=110, minimum width=3cm, minimum height=1cm, text centered, draw=black, fill=blue!30]
%%la comento por que de momento no la estamos usando
\tikzstyle{process} = [rectangle, minimum width=3cm, minimum height=1cm, text centered, draw=black, fill=orange!30]

\tikzstyle{arrow} = [thick,->,>=stealth]
```
Configuracioon de los elementos del diagrama
```
\begin{document}
\maketitle
\begin{center}
	\textbf{Grupo:602}
\end{center}

\newpage


\tableofcontents{}
\newpage

```
Estos comandos hacen la portada y la tabla de contenidos en automatico

```
\section{Objetivos.}

\begin{itemize}
	\item Efectuaras alguna recciones quimicas.
	\item Escribirás las ecuaciones completas de las reacciones que efectuaras y las
\end{itemize}
```
Los objetivos se van a enlistar con el comando [itemize][dc66d3cc]

```
\section{Investigación previa.}
```
los conceptos investigados antes de la pracica

### Citas
Para poder realizar citas de manera automatizada es necesario primero declararlas en el archivo .bib siguiendo estos [formatos][ffd2140f]


una cita dentro del .tex se realiza asi:
```\cite{nombre cita}```

```
\section{Desarrollo experimental.}
\subsection{Diagrama de flujo.}\par
\begin{center}
	\begin{tikzpicture}{node distance=2}

		\node (start) [startstop] {Inicio};
		\node (pro1) [process, below of=start, yshift=-1cm] {Lorem ipsum};
		```
    Cada proceso se formatea asi: ```\node (nombre del proceso) [process, below of=proceso anterior, yshift=-1cm] {Texto proceso};```

    ```
		%% las flechas van despues de los componentes del diagrama de flujo
		\draw [arrow] (start) -- (pro1);
		\draw [arrow] (pro1) -- (pro2);
		\draw [arrow] (pro2) -- (pro3);    
    \end{tikzpicture}
    \end{center}
  ```
  las flechas se declaran asi: ```\draw [arrow] (proceso del que empieza) -- (proceso al que va); ```
  para mas informacion checa [estto][260b56d4]

```
  \section{Precentación de resultados}
  \paragraph{resultado de paso 1}
  El hierro tiene un color café y de asemeja al café en polvo y no tiene olor(aparente), el Azufre tiene un color verde limón sin olor(aparente).
  \paragraph{resultado del paso 2}
  Los elementos mantienen sus propiedades por lo que se le considera mezcla(entre ella el color) como se puede ver en la figura \ref{fig:obs1}
  ....

```
  [260b56d4]: https://es.sharelatex.com/blog/2013/08/29/tikz-series-pt3.html "aiuuda"

\paragraph{resultado del paso5}

**partir de aqui empiezan las imagenes de lo que se observo en la practica, para agregar una imagen se sigue este formato**
```
  \begin{figure}
	 \centering
	 \includegraphics[width=0.5\textwidth]{nombre de figura}
	 \caption{descripcion de figura .}
	 \label{referencia}
  \end{figure}
```

```\section{Analisis de resultados.}```

AQUI VA EL ANALISIS DE LOS resultados
```
  \bibliographystyle{apalike}
  \bibliography{references}
  \end{document}
```
Bibliografia y fin de documento
  [ffd2140f]: https://es.sharelatex.com/learn/Bibliography_management_in_LaTeX "aiuda formatos"
  [dc66d3cc]: https://es.sharelatex.com/learn/Lists "aiuda"
  [73e2c5e2]: http://www.xm1math.net/texmaker/index.html "editor"
  [6a601149]: https://www.gitkraken.com/ "Gui de Git"
  [f4ff5bf4]: https://es.sharelatex.com/learn "documentacion"
  [69bec2cd]: https://tex.stackexchange.com/ "sitio de preguntas"
