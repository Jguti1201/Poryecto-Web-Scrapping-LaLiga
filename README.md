# 🏟 Proyecto de Web Scraping de LaLiga 2025-26

## Índice
1. [Descripción del proyecto](#descripción-del-proyecto)  
2. [Objetivos](#objetivos)  
3. [Estructura del proyecto](#estructura-del-proyecto)  
4. [🛠 Tecnologías y librerías](#-tecnologías-y-librerías)  
5. [Flujo de trabajo](#flujo-de-trabajo)  
   - [Scraping inicial de resultados por jornada](#scraping-inicial-de-resultados-por-jornada)  
   - [Scraping completo de todas las jornadas](#scraping-completo-de-todas-las-jornadas)  
   - [Scraping de estadísticas dinámicas](#scraping-de-estadísticas-dinámicas)  
6. [Ejecutar el proyecto](#ejecutar-el-proyecto)  
7. [Aprendizajes y mejoras](#aprendizajes-y-mejoras)  
8. [Conclusión](#conclusión)  

---

## Descripción del proyecto
Este proyecto tiene como objetivo realizar **web scraping de LaLiga 2025-26**, extrayendo información de partidos, jugadores y estadísticas de diversas páginas dentro del sitio oficial de LaLiga.  

Se desarrolló un scraper escalable que permite automatizar la navegación, recorrer todas las jornadas de la temporada y recopilar estadísticas completas de jugadores y equipos.

El proyecto se dividió en tres fases:  

1. Prueba inicial: extracción básica de resultados de partidos.  
2. Scraping completo de todas las jornadas.  
3. Scraping de estadísticas dinámicas de jugadores y equipos (goleadores, asistencias, tarjetas, etc.).  

---

## Objetivos
- Extraer información de **partidos**: fecha, hora, equipos y goles.  
- Recorrer automáticamente todas las jornadas de la temporada.  
- Extraer estadísticas de jugadores y equipos de forma automática, incluyendo goleadores, asistencias, tarjetas y más.  
- Guardar todos los datos en **archivos JSON y CSV** para análisis posteriores.  
- Implementar un scraper robusto, escalable y amigable con el servidor web.  


---

## 🛠 Tecnologías y librerías

- **Python**:
  - `selenium` + `webdriver-manager` → automatización de navegación y scraping de sitios dinámicos.  
  - `beautifulsoup4` → parseo de HTML y extracción de información de tablas.  
  - `pandas` + `numpy` → limpieza y procesamiento de datos (opcional para análisis).  
  - `json` + `csv` → almacenamiento estructurado de resultados.  
  - `time` + `random` → delays entre requests para simular navegación humana y evitar bloqueos.  

---

## Flujo de trabajo

### Scraping inicial de resultados por jornada
- Abrir la página de resultados de LaLiga en **modo headless**.  
- Esperar dinámicamente a que cargue la tabla de partidos (máximo 20 segundos).  
- Extraer de cada partido:
  - Fecha y hora  
  - Equipos (local y visitante)  
  - Resultado (goles de cada equipo)  
- Almacenar la información en una lista de diccionarios (`partidos`).  
- Esta fase permitió familiarizarse con **Selenium + BeautifulSoup** y preparar la base para un scraper más robusto.  

---

### Scraping completo de todas las jornadas
- Recorrer automáticamente todas las jornadas de la temporada 2025-26.  
- Verificar si la jornada existe y si contiene partidos.  
- Extraer:
  - Fecha y hora  
  - Equipos locales y visitantes  
  - Resultado del partido  
  - Número de jornada y temporada  
- Guardar todos los datos en un **archivo JSON** (`resultados_laliga_2025_26.json`).  
- Implementación de **delays de 1 segundo** entre jornadas para respetar la política del servidor.  

---

### Scraping de estadísticas dinámicas
- Extraer estadísticas de jugadores y equipos:
  - Goleadores  
  - Asistencias  
  - Tarjetas amarillas  
  - Tarjetas rojas  
  - Pases  
  - Paradas  
- Automatización completa de **URLs y paginación**, recorriendo todas las páginas disponibles para cada estadística.  
- Uso de delays aleatorios entre páginas y estadísticas para simular navegación humana.  
- Guardado de los datos en archivos **CSV** con encabezados, listos para análisis posterior.  

---


