<img width="921" height="269" alt="image" src="https://github.com/user-attachments/assets/38e789a9-e7b1-43f6-89c5-bf452d374b52" />

# Análisis de Datos de Taxis en Chicago – Tendencias del Mercado e Impacto del Clima

## Problema
Entender la dinámica del transporte en taxi en Chicago es esencial para optimizar la asignación de flotas y mejorar la precisión de las estimaciones de tiempo.  
El objetivo de este proyecto es analizar la concentración del mercado de taxis, identificar los principales puntos de destino en la ciudad y evaluar estadísticamente si las condiciones climáticas adversas alteran significativamente la duración de los viajes desde *The Loop* hacia el *Aeropuerto Internacional O'Hare* los sábados.

---

## Datos
El análisis se realizó sobre tres conjuntos de datos:

- **Empresas de taxis:** volumen de viajes por compañía (`moved_project_sql_result_01.csv`)  
- **Geografía de la demanda:** promedio de viajes finalizados por barrio de destino (`moved_project_sql_result_04.csv`)  
- **Ruta crítica y clima:** registros de viajes los sábados entre The Loop y O'Hare con variables meteorológicas y duración en segundos (`moved_project_sql_result_07.csv`)  

---

## Enfoque
El proyecto siguió una metodología estructurada de análisis de datos y estadística inferencial:

- Limpieza de datos y verificación de tipos  
- Análisis exploratorio de datos (EDA) para evaluar concentración de mercado y hotspots  
- Formulación de hipótesis nula y alternativa  
- Evaluación inferencial mediante **prueba $t$ de Welch** (`equal_var=False`)  
- Inspección gráfica mediante diagramas de caja (Boxplot) y curvas de densidad (KDE)  

---

## Resultados
La prueba $t$ de Welch confirmó que el mal clima impacta de forma estadísticamente significativa la duración del trayecto hacia el aeropuerto:

- **Estadístico t:** 7.1860  
- **p-value:** $6.74 \times 10^{-12}$ (rechazo de $H_0$ con $\alpha = 0.05$)  

### Otros resultados clave:
- **Impacto cuantificado:** La lluvia incrementa la duración promedio del viaje de 33.3 minutos (1,999.7 s) a 40.5 minutos (2,427.2 s), añadiendo un retraso medio de **7.1 minutos (+21.4%)**.  
- **Estructura del mercado:** *Flash Cab* domina el sector con cerca de 20,000 viajes, seguido por un comportamiento de cola larga entre 64 empresas competidoras.  
- **Concentración geográfica:** *The Loop* es el nodo neurálgico de destino (>10,000 viajes promedio), seguido por *River North*, *Streeterville* y *West Loop*.  

El análisis gráfico KDE evidenció que el mal clima no solo aumenta el tiempo promedio, sino que incrementa la variabilidad y dispersión en las horas de llegada.

---

## Conclusión
La prueba estadística y la visualización de distribuciones confirmaron que las condiciones climáticas adversas retrasan sistemáticamente el tránsito en la ruta Loop $\rightarrow$ O'Hare. 

Estos hallazgos justifican la implementación de algoritmos de estimación de tiempo de llegada (ETA) dinámicos (+15% a +20% en días lluviosos) y la emisión de alertas preventivas para usuarios que se dirigen al aeropuerto.

---

## Herramientas y Tecnologías
- Python  
- Pandas  
- NumPy  
- SciPy (`scipy.stats`)  
- Matplotlib  
- Seaborn  

---

## Conclusión Clave
Este proyecto demuestra la aplicación de análisis exploratorio de datos y estadística inferencial para resolver un problema operativo real, sustentando decisiones estratégicas de producto y estimación de tiempos.

---
---

# Chicago Taxi Data Analysis – Market Trends & Weather Impact

## Problem
Understanding Chicago's taxi transportation dynamics is critical for optimizing fleet allocation and improving arrival time accuracy.  
The goal of this project is to analyze market concentration among taxi companies, identify key destination hotspots across the city, and statistically evaluate whether adverse weather conditions significantly affect trip durations from *The Loop* to *O'Hare International Airport* on Saturdays.

---

## Data
The analysis was conducted across three datasets:

- **Taxi companies:** trip volume by company (`moved_project_sql_result_01.csv`)  
- **Demand geography:** average drop-offs by destination neighborhood (`moved_project_sql_result_04.csv`)  
- **Critical route & weather:** Saturday trips from The Loop to O'Hare with weather condition labels and duration in seconds (`moved_project_sql_result_07.csv`)  

---

## Approach
The project followed a structured data analysis and inferential statistics workflow:

- Data cleaning and type validation  
- Exploratory Data Analysis (EDA) to evaluate market share and geographic clusters  
- Null and alternative hypothesis formulation  
- Inferential testing using **Welch's $t$-test** (`equal_var=False`)  
- Visual diagnostic using Boxplots and Kernel Density Estimation (KDE) curves  

---

## Results
Welch's $t$-test confirmed that bad weather significantly increases travel time to the airport:

- **t-statistic:** 7.1860  
- **p-value:** $6.74 \times 10^{-12}$ ($H_0$ rejected at $\alpha = 0.05$)  

### Other key results:
- **Quantified impact:** Rain increases average trip duration from 33.3 minutes (1,999.7 s) to 40.5 minutes (2,427.2 s), adding an average delay of **7.1 minutes (+21.4%)**.  
- **Market structure:** *Flash Cab* leads the industry with nearly 20,000 trips, followed by a long-tail distribution across 64 competing operators.  
- **Geographic demand:** *The Loop* is the primary destination hub (>10,000 average trips), followed by *River North*, *Streeterville*, and *West Loop*.  

KDE density plots demonstrated that bad weather not only increases mean duration but also spreads out the probability distribution, leading to higher arrival time uncertainty.

---

## Conclusion
Statistical testing and distribution analysis confirmed that adverse weather conditions systematically slow down transit on the Loop $\rightarrow$ O'Hare corridor. 

These findings support implementing dynamic ETA algorithms (+15% to +20% buffer during rain) and sending proactive notification alerts to airport-bound passengers.

---

## Tools and Technologies
- Python  
- Pandas  
- NumPy  
- SciPy (`scipy.stats`)  
- Matplotlib  
- Seaborn  

---

## Key Takeaway
This project demonstrates the application of exploratory data analysis and inferential statistics to solve a real-world operational problem, supporting data-driven product decisions and ETA calibration.
