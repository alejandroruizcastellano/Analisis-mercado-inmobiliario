# Análisis del mercado inmobiliario turístico en Madrid

## Contexto del proyecto

Este proyecto forma parte de un ejercicio de analítica de datos aplicado al mercado de alquiler turístico (tipo Airbnb) en la ciudad de Madrid.

La empresa (ficticia) está evaluando invertir en inmuebles para obtener rentabilidad a través del alquiler de corta estancia. Antes de movilizar al equipo de valoraciones, la dirección solicita al equipo de Data Science un análisis exploratorio (Discovery) que ayude a:

- Entender mejor el comportamiento del mercado de alquiler turístico en Madrid.
- Identificar zonas y tipos de inmuebles con mayor potencial de rentabilidad.
- Priorizar líneas de trabajo para el equipo de valoración de oportunidades.

## Objetivos del análisis

Desde la perspectiva de un perfil junior de Data Analyst / Data Scientist, el proyecto se centra en:

- Analizar fuentes de datos públicas relacionadas con anuncios de alquiler turístico y precios de compraventa.
- Explorar patrones entre precio de alquiler, precio de compra y niveles de ocupación.
- Identificar barrios con mejor relación coste-ingresos para la inversión.
- Proponer recomendaciones accionables para el negocio basadas en los datos.

Los ejes principales del análisis son:

- **Precio del alquiler** (ingresos potenciales).
- **Niveles de ocupación** (utilización del inmueble y estabilidad de ingresos).
- **Precio de compra** (coste de entrada a la inversión).

## Conclusiones ejecutivas

A partir del análisis realizado, se obtienen las siguientes conclusiones clave:

- **14 barrios con alto potencial de inversión**: se identifican barrios que maximizan la relación coste-ingreso, combinando precios de compra relativamente contenidos con niveles de alquiler atractivos.
- **Foco en propiedades de 1 dormitorio**: los apartamentos de 1 habitación muestran las tasas de ocupación más altas, lo que indica una fuerte demanda por este tipo de inmueble (viajeros solos o parejas).
- **Más camas no implican más ocupación**: las propiedades con 1–2 camas tienen mejor ocupación que aquellas con 4 o más camas, donde la ocupación cae claramente por debajo de ~55 %.
- **Capacidad recomendada: 4 huéspedes**: las propiedades de un dormitorio con capacidad para 4 personas presentan un equilibrio interesante entre precio de alquiler y potencial de demanda.
- **Ventaja de las habitaciones privadas**: las habitaciones privadas destacan por su alta ocupación, ayudando a reducir el riesgo de vacantes frente a otros tipos de anuncio.
- **Ubicación dentro del barrio vs. cercanía a puntos de interés**: dentro de los barrios identificados, no es estrictamente necesario estar muy cerca de puntos de interés para mantener buenos niveles de ocupación y alquiler, lo que abre la puerta a comprar algo más alejado a menor precio.
- **El tamaño (m²) no es el driver principal**: no se observa una relación clara y directa entre los metros cuadrados del inmueble y la ocupación o el precio del alquiler.
- **La competencia no determina por sí sola los resultados**: tener muchos anuncios en un barrio no implica necesariamente peor ocupación ni menores precios de alquiler; otros factores (tipo de inmueble, calidad, estrategia de precios, etc.) también son determinantes.
- **Oportunidad de producto orientado a eventos (San Blas–Canillejas)**: el distrito de San Blas–Canillejas aparece como candidato para desarrollar formatos de alquiler asociados a eventos (conciertos, ferias, deporte), donde todavía hay margen de mejora en la explotación de ese potencial.

## Enfoque analítico y herramientas

Aunque el objetivo principal es de negocio, el proyecto también sirve como muestra de habilidades técnicas de análisis de datos:

- **Limpieza y preparación de datos**: uso de pandas para tratamiento de valores nulos, creación de variables derivadas y discretización de variables (habitaciones, camas, capacidad, etc.).
- **Análisis exploratorio (EDA)**: agrupaciones, minicubos (precio y ocupación por distintas dimensiones), métricas de tendencia central (medianas) y comparaciones entre barrios y distritos.
- **Visualización**:
  - Gráficos con matplotlib y seaborn (dispersión, líneas, barras, ejes dobles).
  - Mapas interactivos con folium para visualizar el comportamiento de los anuncios en el distrito de San Blas–Canillejas.
- **Almacenamiento**: uso de SQLite como base de datos intermedia para el dataset preparado.

Tecnologías principales:

- Python (pandas, numpy, matplotlib, seaborn, sqlalchemy, folium)
- SQLite
- Jupyter Notebooks

## Estructura del repositorio

- [0_Diseño del proyecto.ipynb](0_Diseño%20del%20proyecto.ipynb): planteamiento inicial, preguntas de negocio y diseño del flujo de trabajo.
- [1_Analisis de ficheros.ipynb](1_Analisis%20de%20ficheros.ipynb): exploración inicial de las fuentes de datos.
- [2_Calidad de datos y datamart analitico.ipynb](2_Calidad%20de%20datos%20y%20datamart%20analitico.ipynb): revisión de calidad de datos y construcción del datamart analítico.
- [3_Preparacion de datos.ipynb](3_Preparacion%20de%20datos.ipynb): transformación y enriquecimiento de variables para el análisis.
- [4_Analisis e insights.ipynb](4_Analisis%20e%20insights.ipynb): análisis exploratorio detallado y generación de insights.
- [5_Comunicacion resultados.ipynb](5_Comunicacion%20resultados.ipynb): resumen ejecutivo, visualizaciones clave y recomendaciones de negocio.
- Carpeta [Datos](Datos): ficheros de origen y derivados (csv, geojson, base de datos SQLite, etc.).

## Posibles extensiones futuras

Algunas ideas de evolución del proyecto, interesantes para un perfil junior que quiera seguir practicando:

- Construir un modelo sencillo de scoring de barrios o inmuebles (por ejemplo, combinando ocupación, rentabilidad estimada y riesgo).
- Simular distintos escenarios de inversión (precio de compra, niveles de ocupación, variación de precios de alquiler).
- Añadir un dashboard interactivo (Streamlit, Power BI, etc.) para que perfiles de negocio exploren los resultados sin necesidad de código.
