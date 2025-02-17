# Análisis de Airbnb: Mejores Zonas para Invertir

Este proyecto analiza los listados de Airbnb para identificar las mejores zonas y tipos de habitación para invertir en la Ciudad de México, considerando factores clave como número de reseñas, rango de precios y disponibilidad.

---

## Estructura del Proyecto
- **README.md**: Introducción y resumen del proyecto.
- **analysis.md**: Explicación detallada de las gráficas generadas.
- **img/**: Carpeta que contiene las capturas de los gráficos generados.
- **scripts/**: Carpeta con los archivos principales de código:
  - `data_cleaning.ipynb`: Proceso de limpieza y preparación de datos.  
  - `analysis.ipynb`: Análisis exploratorio, visualizaciones y generación de gráficas.
- **listings_data/**: Carpeta con los datasets utilizados para el análisis.
- **requirements.txt**: Archivo que especifica las librerías necesarias para reproducir el proyecto.

---

## Requisitos
- **Python 3.10+**

### Librerías utilizadas:
- `pandas`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `statsmodels`

---

## Cómo Ejecutarlo

### **Instalar las dependencias**:
```bash
pip install -r requirements.txt
```

### **Ejecutar la limpieza de datos**:
```bash
jupyter notebook scripts/data_cleaning.ipynb
```

### **Ejecutar el análisis y generar gráficas**:
```bash
jupyter notebook scripts/analysis.ipynb
```

## Conclusiones
- Mejores zonas para invertir: Cuauhtémoc, Coyoacán, La Magdalena Contreras, Miguel Hidalgo y Tlalpan.
- Tipos de alojamiento recomendados: Habitaciones privadas (Private room), por su balance entre rentabilidad y popularidad.



