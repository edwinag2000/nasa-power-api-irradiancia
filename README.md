# nasa-power-api-irradiancia
Análisis horario de irradiancia solar para Mérida, Yucatán usando la API de NASA POWER. Cálculo de HSP promedio y visualización con Python (pandas, matplotlib).

# 🛰️ Cálculo de Irradiancia Solar y Horas Pico Solar (HSP) usando NASA POWER

Este repositorio contiene un análisis completo de irradiancia solar horaria para una ubicación geográfica definida (por defecto: latitud 21°, longitud -89°, México), utilizando la **API de NASA POWER**.

El objetivo es calcular:

- La **irradiancia promedio horaria**
- La **irradiancia diaria promedio**
- Las **Horas Pico Solar (HSP)**
- Y generar gráficos en alta calidad (PNG) exportables para informes técnicos.

---

## 📁 Contenido

| Archivo                         | Descripción                                                                 |
|--------------------------------|-----------------------------------------------------------------------------|
| `irradiancia_bdd.csv`          | Base de datos descargada desde la API (irradiancia horaria en W/m²)       |
| `irradiancia_promedio_solar.png`   | Gráfica temporal completa de irradiancia                                  |
| `irradiancia_promedio_diaria.png` | Irradiancia promedio horaria (curva de 24 h)                              |
| `HSP.png`                      | Representación visual de HSP mediante rectángulo de 1000 W/m²              |
| `irrprom_1.ipynb`         | Script principal con todo el proceso (descarga, análisis, gráficos)       |

---

## 🧪 Herramientas utilizadas

- Python 3
- `pandas`
- `matplotlib`
- `requests`
- NASA POWER API ([https://power.larc.nasa.gov](https://power.larc.nasa.gov))

---

## 🧮 Metodología

1. Se solicita a la NASA POWER API los datos horarios de irradiancia (`ALLSKY_SFC_SW_DWN`) en formato JSON.
2. Se convierte en un `DataFrame` con `pandas` y se exporta a `.csv`.
3. Se calculan:
   - Irradiancia promedio horaria (`hourly_mean`)
   - Irradiancia diaria promedio (`daily_mean`)
   - Horas Pico Solar (HSP):

4. Se generan tres gráficos en alta resolución:
   - Curva completa de irradiancia en el tiempo
   - Promedio diario (perfil de 24 horas)
   - Visualización de HSP como área bajo la curva de 1000 W/m²

---

## 📍 Parámetros configurables

Puedes cambiar fácilmente en el script los siguientes valores:

```python
latitude = 21        # Latitud deseada
longitude = -89      # Longitud deseada
start_date = "20200101"
end_date   = "20250101"

