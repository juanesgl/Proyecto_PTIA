# Plantilla informes PTIA
![licencia](https://img.shields.io/github/license/diegocostares/latex-templates)
![usa](https://img.shields.io/badge/Utiliza-XeLaTeX-brightgreen)

## Explicación de la plantilla

Esta plantilla fue creada con el objetivo de hacer algo minimalista, ordenado y documentado para informes del proyecto de curso de Principios y Tecnologías de Inteligencia Artificial (PTIA). La estructura sigue una lógica académica tipo APA, por lo que sirve para entregas universitarias donde haya que presentar portada, declaración, índice, introducción, trabajos relacionados, selección del problema, marco PEAS, alcance, objetivos, metodología y referencias.

La propuesta final del documento se centra en el problema de un **Planificador Inteligente de Ruta de Estudio**, modelado como un problema de búsqueda y optimización sobre un Grafo Dirigido Acíclico (DAG). El contexto del sistema está pensado para estudiantes de pregrado en una universidad colombiana, con mallas curriculares en español y restricciones institucionales de créditos, prerrequisitos y oferta por periodo.

Es importante cambiar el compilador a XeLaTeX o LuaLaTeX para que el documento funcione correctamente. Para agregar nuevas secciones, basta con crear archivos `.tex` dentro de la carpeta `content` y usarlos en el archivo principal con `\input{content/tu_archivo_creado.tex}`.

Este proyecto no tiene ninguna afiliación oficial con la Escuela Colombiana de Ingeniería Julio Garavito.

## Uso

Para usar la plantilla, debes modificar los archivos base del proyecto y organizar el contenido por secciones.

```text
├── README.md             // Este documento
├── main.tex              // Documento principal
├── style.cls             // Documento de estilos
├── img/                  // Carpeta para imágenes
│   ├── logo-escuela.png  // Logo institucional
│   ├── matriz.png        // Imagen de la matriz de decisión
│   ├── peas.png          // Diagrama del agente
│   └── prototipo.png     // Captura del prototipo
├── content/
│   ├── portada.tex       // Portada
│   ├── declaracion.tex   // Declaración firmada
│   ├── introduccion.tex  // Introducción
│   ├── relacionados.tex  // Trabajos relacionados
│   ├── seleccion.tex     // Criterios y matriz de decisión
│   ├── peas.tex          // Definición del agente PEAS
│   ├── problema.tex      // Problemática general
│   ├── alcance.tex       // Alcance y objetivos
│   ├── metodologia.tex   // Diseño metodológico
│   └── bibliografia.tex  // Referencias
```

## Comandos personalizados

Los comandos personalizados de la plantilla son los siguientes:

- `\fig`: permite agregar imágenes de forma rápida. Si se desea personalizar, revisar la definición dentro de `style.cls`.

```latex
\fig[referencia1]{Título de la imagen 1}{width = 0.2\textwidth}{img/cuadradoejemplo.png}
```

- `\figposition`: permite incluir una imagen a la izquierda o derecha de un párrafo.

```latex
\figposition[label]{Título}{tamaño}{ruta_imagen}{posicion_r/l}
```

- `\tableimage`: permite incluir imágenes con formato de tabla.

```latex
\tableimage[referencia1]{Título de la tabla 1}{width = 0.2\textwidth}{img/tablaejemplo.png}
```

## Encabezado

La plantilla tiene encabezados a la izquierda y un espacio vacío a la derecha, que se puede reemplazar por una imagen siguiendo el comentario que aparece en `main.tex`. Si se quiere quitar, toca editar varias partes del estilo.

Los pasos serían:

1. Quitar las líneas del encabezado en `main.tex`.
2. Quitar la parte correspondiente al encabezado en `style.cls`.
3. Eliminar la carga de `fancyhdr` en `style.cls` si ya no se va a usar.

## Cosas por mejorar

- Falta hacer una portada más bonita.
- Falta una configuración que permita cambiar entre portada completa y mini portada sin índices.
- Se puede mejorar la integración visual de figuras y tablas.
- También sería útil migrar la bibliografía a `BibTeX` o `biblatex`.

[^1]: Al menos para los laboratorios de Dinámica, Termodinámica y Electro, si lo permiten.

## Nota sobre el proyecto

El documento está orientado al avance de PTIA y mantiene el foco en el modelo de IA: representación del currículo como DAG, optimización de rutas, criterios ponderados de selección y definición del agente bajo PEAS. La interfaz es importante, pero debe salir después de que la lógica del sistema esté bien armada.