# 🛒 Análisis de Precios en Hermosillo – PROFECO “Quién es Quién en los Precios”

Este proyecto realiza un **Análisis Exploratorio de Datos (EDA)** del programa **“Quién es Quién en los Precios” (QQP)** publicado por la **PROFECO**, enfocado específicamente en los **supermercados y tiendas de Hermosillo, Sonora**.  

El objetivo es **identificar variaciones, tendencias y patrones** en los precios de productos básicos, con el fin de entender el comportamiento del mercado local y la competencia entre establecimientos.

---

## 📂 Datos utilizados  

Los datos provienen del portal oficial de datos abiertos de PROFECO:  
🔗 [https://datos.profeco.gob.mx/datos_abiertos/qqp.php](https://datos.profeco.gob.mx/datos_abiertos/qqp.php)

El script descarga automáticamente los archivos `.rar` correspondientes a cada año, los descomprime y filtra la información para conservar solo los registros de **Hermosillo, Sonora**.

---

## ⚙️ Proceso de análisis  

1. **Extracción de enlaces de datos**  
   - Se obtiene el *hash* de descarga de cada año directamente desde el sitio de PROFECO.  

2. **Descarga y descomposición automática**  
   - Los archivos `.rar` se descargan con barra de progreso usando `tqdm` y se extraen en formato `.csv`.  

3. **Filtrado de información**  
   - Se seleccionan solo los registros con `ESTADO = SONORA` y `MUNICIPIO = HERMOSILLO`.  
   - Se filtran las **categorías de la canasta básica** (como leche, arroz, huevo, carne, etc.).  

4. **Análisis estadístico y visualización**  
   - Se calculan **promedios y variaciones porcentuales por año y categoría**.  
   - Se muestran las **categorías con mayor variación de precios** en los últimos años.  
   - Se generan:
     - Gráficas de tendencia de precios.  
     - Mapa georreferenciado con precios promedio por sucursal (usando `GeoPandas` y `shapefiles` de Hermosillo).  
     - Boxplots de dispersión de precios por categoría.  

---

## 🧠 Tecnologías y librerías

| Tipo | Librerías |
|------|------------|
| Procesamiento y análisis | `pandas`, `tqdm` |
| Web scraping y descargas | `requests`, `BeautifulSoup4`, `rarfile` |
| Visualización | `matplotlib`, `seaborn`, `adjustText` |
| Geoespacial | `geopandas`, `geopy`, `shapely` |
| Utilidades | `datetime`, `os`, `glob` |

---

## 🌎 Visualizaciones principales  

- 📈 **Variación porcentual de precios** por categoría a lo largo del tiempo.  
- 🗺️ **Mapa de calor** de precios promedio por supermercado en Hermosillo.  
- 📊 **Distribución de precios** (boxplots) para identificar dispersiones y anomalías.

---

## 📊 Resultados  

Este análisis permite:  
- Observar qué categorías de productos han aumentado más su precio con el tiempo.  
- Comparar visualmente la distribución espacial de precios entre supermercados.  
- Identificar zonas o tiendas con precios consistentemente más altos o bajos.

---

## 🧾 Autor  

👤 **Francisco Ortega**  
📍 Hermosillo, Sonora, México  
🎓 Ingeniero Químico / Estudiante de Maestría en Ciencia de Datos  
💡 Interesado en aplicar ciencia de datos al análisis económico y de consumo  

---
