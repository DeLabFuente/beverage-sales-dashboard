🇬🇧 [English version](README.md) | 🇪🇸 Versión en español

# 🍺 Dashboard de Ventas de Bebidas — Power BI

## Descripción
Dashboard interactivo en Power BI que analiza el 
rendimiento de ventas de una distribuidora de bebidas 
en Alemania. Desarrollado como parte de mi portafolio 
de análisis de datos, orientado a roles de Business 
Intelligence en el sector de gran consumo (FMCG).

## Objetivo
Demostrar capacidades de análisis de datos de extremo 
a extremo — desde la limpieza y transformación de datos 
hasta el modelado y la visualización interactiva — 
utilizando un dataset real del sector bebidas.

## Dataset
- **Fuente:** Kaggle — Beverage Sales Dataset 
  (sebastianwillmann/beverage-sales)
- **Licencia:** MIT
- **Tamaño:** +3.000.000 filas × 11 columnas
- **Periodo:** Enero 2021 — Diciembre 2023

## Herramientas y Tecnologías
- **Power BI Desktop** — desarrollo del dashboard
- **Power Query (lenguaje M)** — limpieza y 
  transformación de datos
- **DAX** — medidas calculadas y KPIs
- **Excel** — exploración inicial de datos

## Limpieza y Transformación de Datos
- Detección y corrección de errores de cálculo en 
  la columna Total_Price original
- Creación de columna Discount_Rate (Discount / 100)
- Creación de columna Price_After_Discount 
  (Unit_Price × (1 - Discount_Rate))
- Recálculo de Total_Price 
  (Price_After_Discount × Quantity)
- Extracción de dimensiones temporales: Year, Quarter,
  Month_Num, Month_Name desde Order_Date
- Traducción de categorías de producto al español
- Construcción de tabla Calendario con DAX 
  para inteligencia de tiempo
- Relación establecida: 
  Ventas_Bebidas[Order_Date] → Calendario[Date]

## Medidas DAX
- Total_Ventas = SUM(Total_Price)
- Total_Unidades = SUM(Quantity)
- Ticket_Medio = DIVIDE(Total_Ventas, 
  DISTINCTCOUNT(Order_ID))
- Descuento_Medio = AVERAGE(Discount)
- Top10_Ventas = filtro TOP 10 con RANKX

## Estructura del Dashboard
### Página 1 — Resumen Ejecutivo
- 4 KPI Cards: Total Ventas, Total Unidades, 
  Ticket Medio, Descuento Medio
- Gráfico de área: Evolución de ventas 2021→2023
- Barras horizontales: Ventas por categoría
- Gráfico circular: B2B (76,48%) vs B2C (23,52%)

### Página 2 — Canal y Región
- Mapa de burbujas: Total ventas por región alemana
- Barras apiladas: Ventas por región y tipo de cliente

### Página 3 — Top Productos
- Top 10 productos por ventas (medida DAX con RANKX)
- Barras apiladas: Ventas por categoría y 
  tipo de cliente
- Tabla resumen: Producto, Total Ventas, 
  Total Unidades, Descuento Medio

## Filtros Interactivos (Slicers)
Sincronizados en las 3 páginas:
- Año (2021 / 2022 / 2023)
- Tipo de Cliente (B2B / B2C)
- Categoría (Agua / Bebidas Alcohólicas / 
  Refrescos / Zumos)

## Insights Clave
- 📈 Las ventas crecieron de forma consistente 
  de 2021 a 2023
- 🍾 Veuve Clicquot lidera las ventas — el canal 
  B2B premium es el motor del negocio
- 🏢 B2B representa el 76,48% de los ingresos 
  totales en TODAS las categorías
- 🍺 Bebidas Alcohólicas acapara la mayor parte 
  de las ventas totales

## Autor
**Daniel Díaz De La Fuente**  
Analista de Datos en formación | 
Power BI · SQL · Python · R  
Certificado Google Data Analytics (media 94,85%) · 
Business Analytics with Excel — Johns Hopkins  
📍 Sevilla, España 
 
[LinkedIn](https://www.linkedin.com/in/daniel-diaz-de-la-fuente-3b0835296/) | [GitHub](https://github.com/DeLabFuente/beverage-sales-dashboard)

> 📥 Archivo del dashboard (.pbix) disponible 
> bajo petición a través de LinkedIn