# Tablero de cartera de autos + cotizador

Tablero en Streamlit para analizar una cartera de seguros de auto y cotizar primas. Proyecto de la
Tarea 1 del Módulo 5 del Diplomado Machine Learning en Seguros (FC UNAM).

**App publicada:** https://tablero-seguros-mfajardo.streamlit.app/

## Qué hace

- **Filtros** en la barra lateral: cobertura, sexo, uso, combustible y edad.
- **KPIs** de la selección: exposición, nº de siniestros, frecuencia, severidad y prima pura,
  además de loss ratio y combined ratio.
- **Gráficas**: frecuencia por factor y combined ratio por factor.
- **Detalle**: tabla de KPIs por segmento, descargable en CSV.
- **Cotizador**: para un perfil de asegurado calcula, en orden,
  1. la prima pura **empírica** del segmento,
  2. la prima pura del **GLM** (frecuencia Poisson × severidad Gamma),
  3. la **prima de tarifa** (con recargos de gastos y margen),

  y explica con una gráfica qué factores suben o bajan la prima.

## Cómo correrlo local

```bash
pip install -r requirements.txt
streamlit run app_streamlit.py
```

Se abre en http://localhost:8501. La primera vez la app crea `cartera.db` (SQLite) a partir de
`datos/datos.parquet` y ajusta los GLM, así que tarda unos segundos más.

## Estructura

```
app_streamlit.py      # la app
requirements.txt      # librerías que instala el servidor
datos/datos.parquet   # datos de la cartera
.gitignore            # excluye cartera.db (se reconstruye sola)
```
