# 📊 Análisis Exploratorio de Clientes y Patrones de Uso - ConnectaTel

## Descripción del proyecto

Este proyecto tiene como objetivo realizar un análisis exploratorio de datos (EDA) sobre la base de clientes de ConnectaTel, una empresa de telecomunicaciones. El análisis busca identificar patrones de comportamiento, segmentar usuarios según su nivel de uso y edad, detectar problemas de calidad de datos y generar recomendaciones comerciales basadas en la información obtenida.

A partir de los datos de usuarios y registros de uso (llamadas y mensajes), se desarrolló un proceso completo de limpieza, transformación, agregación y visualización para obtener información útil para la toma de decisiones de negocio.

---

## Objetivos

* Evaluar la calidad de los datos y corregir inconsistencias.
* Analizar el comportamiento de los usuarios según llamadas y mensajes.
* Identificar segmentos de clientes según edad y nivel de uso.
* Detectar valores atípicos (outliers) y evaluar su impacto.
* Generar recomendaciones para optimizar la oferta de planes de ConnectaTel.

---

## Datasets utilizados

### users.csv

Contiene información demográfica y de suscripción de los clientes.

Columnas principales:

* `user_id`: identificador único del usuario.
* `first_name`: nombre.
* `last_name`: apellido.
* `age`: edad.
* `city`: ciudad de residencia.
* `reg_date`: fecha de registro.
* `plan`: tipo de plan contratado.
* `churn_date`: fecha de cancelación del servicio.

---

### usage.csv

Contiene los registros de actividad de los usuarios.

Columnas principales:

* `id`: identificador del evento.
* `user_id`: identificador del usuario.
* `type`: tipo de actividad (`call` o `text`).
* `date`: fecha del evento.
* `duration`: duración de la llamada.
* `length`: longitud del mensaje.

---

## Etapas del análisis

### 1. Exploración inicial de los datos

* Revisión de dimensiones y tipos de datos.
* Identificación de valores nulos.
* Detección de valores inválidos o sentinels.
* Revisión de variables numéricas y categóricas.

---

### 2. Limpieza y preparación de datos

Se realizaron las siguientes acciones:

* Reemplazo del valor sentinel `-999` en la columna `age` por la mediana.
* Reemplazo del valor `"?"` en la columna `city` por valores nulos.
* Conversión de columnas de fecha al tipo datetime.
* Identificación y corrección de fechas fuera de rango.
* Verificación de valores faltantes en `duration` y `length`.

---

### 3. Verificación de valores faltantes

Se comprobó que:

* Los nulos de `duration` corresponden a registros de tipo `text`.
* Los nulos de `length` corresponden a registros de tipo `call`.

Estos valores faltantes se mantuvieron debido a que representan campos no aplicables y no errores de calidad de datos.

---

### 4. Agregación de información por usuario

Se construyó una tabla agregada por usuario que incluye:

* Cantidad total de mensajes.
* Cantidad total de llamadas.
* Total de minutos de llamadas.

Posteriormente se integró esta información al perfil de cada usuario.

---

### 5. Análisis exploratorio

Se analizaron:

* Distribución de edades.
* Distribución de mensajes enviados.
* Distribución de llamadas realizadas.
* Distribución de minutos totales de llamadas.
* Distribución de usuarios por plan.

Se utilizaron histogramas y gráficos de barras para visualizar los resultados.

---

### 6. Detección de outliers

Se aplicó el método del rango intercuartílico (IQR) para identificar valores atípicos en:

* Edad.
* Cantidad de mensajes.
* Cantidad de llamadas.
* Minutos totales de llamadas.

Los outliers encontrados se conservaron porque representan comportamientos reales de usuarios de alto consumo.

---

### 7. Segmentación de usuarios

Se crearon nuevos grupos para clasificar a los clientes:

#### Grupo de uso

* Bajo uso
* Uso medio
* Alto uso

#### Grupo de edad

* Joven
* Adulto
* Adulto Mayor

Posteriormente se analizaron sus distribuciones para identificar oportunidades comerciales.

---

### 8. Conclusiones y recomendaciones

Se identificaron segmentos de clientes con diferentes patrones de consumo y se formularon recomendaciones relacionadas con:

* Nuevos planes para usuarios de alto consumo.
* Estrategias de migración hacia planes Premium.
* Ofertas diferenciadas según nivel de uso y edad.

---

## Herramientas utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Google Colab

---

## Cómo ejecutar el proyecto

### Opción 1: Google Colab

1. Abrir Google Colab.
2. Crear un nuevo notebook.
3. Cargar los archivos:

   * `users.csv`
   * `usage.csv`
4. Copiar el contenido del notebook del proyecto.
5. Ejecutar las celdas en orden.

---

### Opción 2: Jupyter Notebook

Instalar dependencias:

```bash
pip install pandas numpy matplotlib seaborn
```

Abrir el notebook:

```bash
jupyter notebook
```

Ejecutar todas las celdas secuencialmente.

---

## Guía de reproducción

1. Cargar los datasets.
2. Revisar estructura y tipos de datos.
3. Limpiar valores inválidos y fechas inconsistentes.
4. Analizar valores faltantes.
5. Agregar métricas de uso por usuario.
6. Unir la información de uso con los perfiles de clientes.
7. Generar estadísticas descriptivas.
8. Crear visualizaciones.
9. Detectar outliers.
10. Segmentar usuarios por edad y uso.
11. Interpretar resultados y generar recomendaciones de negocio.

---

## Autor

Proyecto desarrollado como parte de un ejercicio de análisis exploratorio de datos y segmentación de clientes utilizando Python y técnicas de Data Analytics.
