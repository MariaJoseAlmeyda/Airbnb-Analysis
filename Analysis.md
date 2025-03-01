# Análisis de Airbnb en la Ciudad de México

Este documento detalla los análisis realizados sobre los listados de Airbnb en la Ciudad de México, incluyendo la metodología utilizada, las variables analizadas y las conclusiones obtenidas.

## 1. Objetivo del Análisis
Este proyecto tiene como propósito responder diferentes preguntas analíticas relacionadas con el precio, la disponibilidad y el número de reseñas, considerando variables clave como la zona (neighbourhood) y el tipo de habitación (room_type). A través de este análisis, se busca identificar las mejores zonas y tipos de alojamiento para realizar inversiones rentables en Airbnb.

## 2. Variables Analizadas
- Zona (neighbourhood): Área o colonia donde se encuentra el alojamiento, clave para identificar zonas con alta demanda.
- Tipo de habitación (room_type): Categoría de alojamiento (Entire home/apt, Private room, Shared room, Hotel room), lo que influye en la experiencia y costo.
- Precio (price): Costo por noche del listado, fundamental para evaluar la rentabilidad.
- Noches mínimas (minimum_nights): Cantidad mínima de noches que se debe reservar, relevante para estimar el flujo de ingresos.
- Número de reseñas (number_of_reviews): Refleja la popularidad y frecuencia de uso del alojamiento.
- Disponibilidad (availability_365): Número de días al año en que el alojamiento está disponible para reservaciones.

## 3. Analisis Descriptivo General
- **Resumen Estadistico General**
![Resumen General](img/df_cleaned_summary_filtered.png)
En la columna **price**, el precio promedio de los listados es de 1,280.37 pesos mexicanos, con un precio mínimo de 116 pesos y un máximo de 4,954 pesos. El 50% de los precios están por debajo de 1,050 pesos, lo que indica que la mayoría de los listados son accesibles, pero también existen algunas propiedades significativamente más caras.

En la columna **number_of_reviews**, los listados tienen en promedio 36 reseñas, con un mínimo de 0 reseñas y un máximo de 206 reseñas. El 75% de los listados tienen 53 reseñas o menos, lo que sugiere que la mayoría recibe un número moderado de evaluaciones.

Para **minimum_nights**, el número mínimo de noches requeridas es 1 noche, con un máximo sorprendente de 365 noches (aproximadamente 1 año), lo cual es poco común para Airbnb. El 50% de los listados exigen 2 noches o menos, y solo el 25% requiere más de 5 noches, lo que indica que las estancias cortas son las más comunes.

La columna **availability_365** muestra que los listados tienen una disponibilidad promedio de 219.73 días al año, con un mínimo de 0 días (posiblemente listados inactivos o no disponibles temporalmente) y un máximo de 365 días, indicando propiedades disponibles todo el año. El 50% de los listados están disponibles al menos 263 días al año, lo que sugiere una alta disponibilidad general en la mayoría de las propiedades.

Además, la columna **calculated_host_listings_count** revela que, en promedio, un anfitrión maneja alrededor de 16 listados, pero algunos tienen hasta 238 listados, lo que podría indicar la presencia de grandes anfitriones comerciales en la plataforma.

- **Histograma de Precios y Numero de Reseñas**
![Histograma de Precios y Numero de Reseñas](img/histograma_price_reviews.png)

En estos histogramas podemos obserbar la distribucion de precios y de reseñas:
La mayoría de los listados tienen precios por debajo de $2000, lo que hace que las inversiones en este mercado sean accesibles para un rango amplio de inversores.
A medida que el precio aumenta, la cantidad de listados disminuye significativamente, pero aún existen listados premium con precios cercanos a los 5,000 pesos, aunque son poco frecuentes.

La distribución es muy sesgada hacia la izquierda, indicando que pocos listados acumulan muchas reseñas. Esto resalta la importancia de destacar el alojamiento para generar más comentarios y atraer clientes.

## Preguntas a responder con el analisis de variables: 

- ¿Qué zonas tienen más listados en Airbnb?
![Mapa de listados por zona](img/mapa_de_listados_por_zona.png)

En el gráfico se observa la distribución geográfica de los listados de Airbnb en la Ciudad de México. La mayoría de los listados se concentran en el centro de la ciudad, especialmente en zonas como Cuauhtémoc, conocido por sus zonas turísticas como la colonia Roma y Condesa, y Miguel Hidalgo, que incluye áreas exclusivas como Polanco. Estas zonas son clave para invertir debido a su alta demanda turística.

A medida que nos alejamos del centro, la densidad de listados disminuye notablemente, destacando zonas con menos presencia como Tláhuac y Milpa Alta, ubicados en las periferias de la ciudad, donde la oferta de alojamientos es significativamente menor.

- ¿Qué tipos de habitaciones son más populares y donde se encuentran?
- 
![tipos de Habitaciones mas Populares](img/promedio_disponibilidad_por_tipo_de_habitacion.png)
Las gráficas muestran que, según el promedio de disponibilidad anual, las habitaciones compartidas (Shared room) son las que permanecen más tiempo disponibles, seguidas de las habitaciones privadas (Private room) y los apartamentos completos (Entire home/apt). Las habitaciones de hotel (Hotel room) presentan un promedio ligeramente menor de días disponibles. Esta tendencia sugiere que las habitaciones compartidas podrían tener menor demanda, manteniéndose más tiempo vacías, mientras que las habitaciones privadas y apartamentos completos, a pesar de su menor disponibilidad, podrían ser más rentables debido a una mayor ocupación y preferencia de los huéspedes por la privacidad.

![Cantidad de listados de Hotel Room por zona](img/cantidad_de_listados_Hotel.png)

Las zonas con más listados de habitaciones de Hotel es Cuauhtémoc, Miguel Hidalgo y Alvaro Obregon, lo que refleja una alta competencia, pero también una alta demanda. Por otro lado, Coyoacán se posiciona como la zona con la menor cantidad de este tipo de alojamientos, reflejando su ubicación periférica y menor actividad turística en comparación con otras zonas de la ciudad.

- ¿Qué tan disponibles están los listados durante el año en cada zona?
![disponibilidad Promedio por zona](img/disponibilidad_promedio_por_Zona.png)

La gráfica revela que los zonas periféricos de la Ciudad de México presentan una mayor disponibilidad de listados durante el año, encabezados por Milpa Alta, cuya disponibilidad destaca notablemente frente a otras zonas. Este fenómeno podría atribuirse a una menor demanda turística, permitiendo que los listados permanezcan disponibles por más tiempo. Tláhuac e Iztapalapa siguen la misma tendencia, lo que sugiere que, aunque ofrecen precios accesibles, no son las zonas más buscadas por los visitantes.

En contraste, zonas céntricos y populares como Miguel Hidalgo, Cuauhtémoc y Benito Juárez muestran una disponibilidad significativamente menor, probablemente debido a la alta rotación y demanda constante de turistas, lo que hace que las propiedades se ocupen rápidamente y con frecuencia.

- ¿Cual es el rango de precios en los zonas?
![Rango de Precios por zona](img/rango_de_precios_por_Zona.png)

En este Boxplot podemos observar que distribución del rango de precios en cada zona de la Ciudad de México. Se observa que Cuauhtémoc y Miguel Hidalgo tienen una amplia dispersión de precios, desde opciones accesibles hasta alojamientos de lujo, lo que refuerza su popularidad y variedad de oferta.

Por otro lado, Milpa Alta, aunque presenta precios elevados en su mayoría, también muestra una menor dispersión, indicando que los precios son más consistentes y menos variados.

Las zonas con mayor rango de precios son Miguel Hidalgo y La Magdalena Contreras, lo que podría ofrecer oportunidades tanto en el segmento de lujo como en opciones más económicas.

- ¿Qué zonas y tipo de habitaciones reciben más reseñas al mes?
![zonas de acuerdo al numero de reseñas](img/Zonas_con_mas_reseñas.png)

Las zonas más populares según las reseñas son Venustiano Carranza, Azcapotzalco, e Iztacalco, lo que indica alta rotación y potencial de ingresos recurrentes.

Venustiano Carranza lidera en el promedio de reseñas mensuales, destacándose notablemente a pesar de no figurar entre los zonas más caros ni con mayor disponibilidad, lo que sugiere que su popularidad podría estar relacionada con factores como accesibilidad o relación calidad-precio. 
Por otro lado, Tlahuac, con precios más bajos y mayor disponibilidad, muestra un menor número de reseñas mensuales, lo que podría indicar una menor atracción turística o preferencia por otras zonas.

![Tipo de habitacion con mas reseñas](img/habitaciones_can_mas_reseñas.png)

En cuanto al tipo de habitación, Entire home/apt no solo es la opción con más listados, sino también la que recibe más reseñas.. Un dato interesante es que las habitaciones compartidas (Shared room) reciben más reseñas que las habitaciones privadas (Private room) y las habitaciones de hotel (Hotel room), lo que podría reflejar una mayor interacción social en este tipo de alojamientos o un menor costo que motiva a los viajeros a compartir sus experiencias con mayor frecuencia.

- ¿Cuáles son las mejores zonas para invertir en un Airbnb?
![Mejores zonas para invertir](img/mejores_zonas_para_invertir.png)

Las mejores zonas para invertir son:
- Cuauhtémoc: Alta demanda, muchas reseñas y buen rango de precios.
- Coyoacán: Popular entre turistas, con precios competitivos.
- La Magdalena Contreras: Alta rentabilidad debido a su variabilidad de precios.
- Miguel Hidalgo: Zona premium con alto potencial de ingresos.
- Tlalpan: Buena disponibilidad y rentabilidad equilibrada.
  
Esta clasificación se obtiene mediante un análisis que pondera el número de reseñas, el rango de precios y la disponibilidad, dando más peso a aquellas zonas con alto movimiento de reseñas y una mayor variedad de precios. Por otro lado, las zonas menos recomendadas para invertir son Iztacalco, Venustiano Carranza, Iztapalapa, Azcapotzalco y Tláhuac, debido a su menor atractivo según los mismos criterios.

Este modelo prioriza zonas con alta actividad de usuarios (reseñas), una amplia variabilidad en precios (posibilidades de rentabilidad diversa) y menor disponibilidad, ya que una alta ocupación suele reflejar mayor demanda y competitividad en la zona.

- ¿Cual es el mejor tipo de habitacion para invertir?
![Mejores tipos de habitacion para invertir en Airbnb](img/mejores_habitaciones_para_invertir.png)


Podemos observar que "Private room" y "Entire home/apt" presentan puntuaciones muy similares, lo que sugiere que ambos son excelentes opciones para invertir. Esto refleja una preferencia de los huéspedes por alojamientos que ofrezcan privacidad y comodidad, factores clave en la elección de hospedaje. "Hotel room" también muestra una puntuación competitiva, lo que lo convierte en una opción atractiva; sin embargo, es importante considerar que este tipo de inversión suele requerir un mayor capital inicial y costos de mantenimiento. Por otro lado, "Shared room" obtiene la puntuación más baja, lo que indica que es la opción menos recomendable para invertir, probablemente porque los clientes valoran más la privacidad y la independencia, lo que hace que las habitaciones compartidas tengan menor demanda y rentabilidad.

## 4. Conclusiones

Las mejores zonas para invertir, como Cuauhtémoc, Coyoacán, La Magdalena Contreras, Miguel Hidalgo y Tlalpan, destacan por su alta actividad de usuarios (evidenciada en el número de reseñas) y una amplia variabilidad en precios, lo que sugiere que son áreas populares y rentables. Por otro lado, las zonas menos recomendadas (Iztacalco, Venustiano Carranza, Iztapalapa, Azcapotzalco y Tláhuac) muestran menor movimiento y competitividad, lo que sugiere una demanda más baja o menor atractivo para los visitantes. Además, es recomendable evaluar zonas emergentes como Venustiano Carranza e Iztacalco, donde la rotación de huéspedes es alta.

En cuanto a el mejor tipo de habitacion para invertir los huéspedes tienden a preferir alojamientos que ofrezcan mayor privacidad, como habitaciones privadas (Private room) y apartamentos completos (Entire home/apt). Esto se refleja en las altas puntuaciones obtenidas por estos tipos de alojamiento, lo que indica una mayor demanda y potencial de rentabilidad. Las habitaciones compartidas (Shared room) son la opción menos rentable debido a la menor demanda, lo que confirma que la privacidad es un factor decisivo para los huéspedes.

En conclusión, se recomienda enfocar las inversiones en zonas con alta actividad y amplia variedad de precios, así como en tipos de alojamiento que prioricen la privacidad, como habitaciones privadas y apartamentos completos. Además, es aconsejable realizar un análisis más detallado sobre la relación costo-beneficio entre las inversiones en hoteles y aquellas en habitaciones privadas o apartamentos completos, considerando factores como rentabilidad, costos operativos y mantenimiento. Por último, se sugiere profundizar en el estudio de las preferencias de los clientes para comprender mejor qué aspectos influyen en su elección entre diferentes tipos de alojamiento, como ubicación, comodidades, precio y políticas de hospedaje.
