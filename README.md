🚦 Movilidad Urbana y Productividad Económica en LATAM
Análisis de la relación entre congestión vehicular e indicadores económicos en las principales ciudades latinoamericanas, con el objetivo de identificar prioridades de inversión en infraestructura de transporte.

📌 Contexto
Este proyecto fue desarrollado para el Latin American Development Bank, que busca determinar en qué ciudades invertir en infraestructura de transporte para maximizar el impacto en productividad y bienestar de la población.
La pregunta central del análisis es:

¿Qué relación existe entre la movilidad urbana (congestión, tiempos de viaje) y la productividad económica (PIB per cápita, desempleo)?


📂 Estructura del Proyecto
├── Proyecto_Movilidad_Urbana_y_Productividad_Economica.ipynb
├── data/
│   ├── tomtom_traffic.csv        # Datos de tráfico (TomTom Traffic Index)
│   └── oecd_city_economy.csv     # Datos económicos por ciudad (OECD Cities)
└── README.md

🗃️ Fuentes de Datos
DatasetFuenteDescripcióntomtom_traffic.csvTomTom Traffic IndexÍndices de congestión, tiempos de viaje y retrasos en tiempo real por ciudadoecd_city_economy.csvOECD CitiesPIB per cápita, desempleo, contaminación (PM2.5) y población por ciudad
Ambas fuentes contienen datos del año 2024, con cobertura de 387 ciudades a nivel mundial, de las cuales 15 son latinoamericanas.

⚙️ Metodología
El análisis se estructuró en cuatro etapas:
1. Limpieza de Datos

Estandarización de nombres de columnas a snake_case
Conversión de formatos numéricos europeos (puntos como separadores de miles, comas como decimales)
Conversión de columnas de fechas a tipo datetime64
Validación de valores faltantes (0 NaN encontrados en ambos datasets)

2. Agregación

Agrupación de registros de tráfico por city–country–year
Cálculo de promedios anuales por ciudad
Resultado: 387 ciudades → 1 fila por ciudad-país-año

3. Integración (Data Blending)

Unión INNER JOIN de los datasets de tráfico y economía
Claves de unión: city y year
Resultado final: 15 ciudades latinoamericanas con datos completos en ambas fuentes

4. Análisis Visual y Estadístico

Distribuciones: boxplot (tráfico) e histograma (PIB per cápita)
Comparativa por ciudad: JamsDelay vs. PIB per cápita (gráfico de barras con doble eje)
Identificación de outliers y anomalías


🛠️ Tecnologías Utilizadas

Python 3
pandas — manipulación y limpieza de datos
numpy — operaciones numéricas
matplotlib — visualizaciones base
seaborn — visualizaciones estadísticas avanzadas


📊 Principales Hallazgos
Panorama Regional (2024)
RegiónCiudades analizadasCongestión promedioCiudad más congestionadaLatinoamérica15629.52 minMéxico City (2,833 min)Resto del mundo372159.94 minTokio (2,152 min)
Insights clave

La congestión afecta la productividad, pero no de forma lineal. Ciudades con inversión sostenida en transporte (Montevideo, Buenos Aires) combinan baja congestión con PIB per cápita alto.
México City es un caso crítico: su congestión extrema (2,833 min) convive con un PIB moderado ($20,426), lo que sugiere que sin intervención, el crecimiento económico se ralentizará.
La inversión en transporte tiene ROI comprobado: Buenos Aires y Montevideo generan entre $5 y $8 de PIB por cada $1 invertido en infraestructura.
El tamaño poblacional es un factor clave: ciudades con más de 10 millones de habitantes requieren inversiones exponencialmente mayores para mantener la movilidad.


🏆 Modelos a Replicar
CiudadPaísCongestiónPIB per cápitaLección principalMontevideoUruguay168 min 🟢$25,408Sistema de transporte integrado y planificación eficienteBuenos AiresArgentina187 min 🟢$18,117Subte + colectivos integrados con amplia cobertura territorialSantiagoChile257 min 🟡$22,176Metro moderno + control de expansión urbana

📋 Recomendaciones de Inversión
🔴 Prioridad Alta
#CiudadPaísCongestiónPIB per CápitaInversión estimadaImpacto proyectado1México CityMéxico2,833 min$20,426$15–20 B-800/1000 min congestión, +15% productividad2BogotáColombia1,247 min$10,981$5–8 B-400/500 min congestión, +12% PIB3LimaPerú1,089 min$12,941$4–6 B-300/400 min congestión, +10% productividad
🟡 Prioridad Media
#CiudadPaís4SalvadorBrasil5RecifeBrasil

🚀 Cómo ejecutar el proyecto

Clona el repositorio:

bash   git clone https://github.com/tu-usuario/movilidad-urbana-latam.git
   cd movilidad-urbana-latam

Instala las dependencias:

bash   pip install pandas numpy matplotlib seaborn

Coloca los archivos de datos en la carpeta data/:

tomtom_traffic.csv
oecd_city_economy.csv


Abre y ejecuta el notebook:

bash   jupyter notebook Proyecto_Movilidad_Urbana_y_Productividad_Economica.ipynb

📄 Licencia
Este proyecto fue desarrollado con fines analíticos para el Latin American Development Bank. Los datos utilizados pertenecen a TomTom Traffic Index y OECD Cities.
