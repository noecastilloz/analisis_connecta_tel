# analisis_connecta_tel

# 📊 Análisis de Clientes y Patrones de Uso en ConnectaTel

## 📌 Descripción del Proyecto

Este proyecto realiza un análisis exploratorio de datos (EDA) sobre la base de clientes de ConnectaTel, una empresa de telecomunicaciones. El objetivo es comprender los patrones de uso de los usuarios, segmentarlos según sus características y el nivel de consumo, identificar oportunidades comerciales y generar recomendaciones para optimizar la oferta de planes.

El análisis incluye procesos de limpieza de datos, variables, detección de outliers, segmentación de clientes y generación de insights de negocio.

---

# 🎯 Objetivos del Proyecto

* Limpiar y preparar los datos para garantizar su calidad.
* Detectar y corregir valores inconsistentes, faltantes y sentinela.
* Analizar el comportamiento de uso de los clientes.
* Construir métricas agregadas de consumo por usuario.
* Segmentar clientes por edad y nivel de uso.
* Detectar patrones de uso extremo (outliers).
* Comparar el comportamiento entre diferentes tipos de planes.
* Generar recomendaciones comerciales basadas en evidencia.

---

# 📂 Datasets Utilizados

## 1. users.csv

Contiene información contractual de los clientes.

### Variables

| Columna    | Descripción                      |
| ---------- | -------------------------------- |
| user_id    | Identificador único del usuario  |
| first_name | Nombre del cliente               |
| last_name  | Apellido del cliente             |
| age        | Edad del cliente                 |
| city       | Ciudad de residencia             |
| reg_date   | Fecha de registro                |
| plan       | Plan contratado                  |
| churn_date | Fecha de cancelación (si aplica) |

### Propósito

Permite analizar características de los clientes y relacionarlas con sus patrones de consumo.

---

## 2. usage.csv

Contiene el historial de uso de servicios de telecomunicaciones.

### Variables

| Columna  | Descripción                       |
| -------- | --------------------------------- |
| id       | Identificador único del registro  |
| user_id  | Identificador del usuario         |
| type     | Tipo de interacción (call o text) |
| duration | Duración de la llamada            |
| length   | Longitud del mensaje              |
| date     | Fecha de la interacción           |

### Propósito

Permite medir el comportamiento real de uso de los clientes.

A partir de este dataset se construyeron variables agregadas como:

* Cantidad de mensajes enviados.
* Cantidad de llamadas realizadas.
* Total de minutos consumidos.

---

## 3. plans.csv

Contiene las características y costos de los planes ofrecidos por ConnectaTel.

### Variables

| Columna           | Descripción                     |
| ----------------- | ------------------------------- |
| plan_name         | Nombre del plan                 |
| messages_included | Mensajes incluidos              |
| gb_per_month      | Datos móviles incluidos por mes |
| minutes_included  | Minutos incluidos               |
| usd_monthly_pay   | Pago mensual                    |
| usd_per_gb        | Costo por GB excedente          |
| usd_per_message   | Costo por mensaje excedente     |
| usd_per_minute    | Costo por minuto excedente      |

### Propósito

Permite comprender la estructura comercial de los planes y evaluar si el comportamiento de los clientes está alineado con los beneficios contratados.

---

# 🧹 Etapas del Análisis

## 1. Exploración Inicial

* Revisión de estructura de los datasets.
* Identificación de tipos de datos.
* Detección de valores faltantes.
* Identificación de inconsistencias.

## 2. Limpieza de Datos

* Conversión de fechas.
* Corrección de tipos de datos.
* Tratamiento de valores sentinela.
* Análisis de valores nulos.
* Validación de registros inconsistentes.

## 3. Variables

Se crearon variables agregadas por usuario:

* `cant_mensajes`
* `cant_llamadas`
* `cant_minutos_llamada`

Estas métricas permiten representar el comportamiento histórico de cada cliente.

## 4. Análisis Exploratorio (EDA)

Se realizaron:

* Estadísticas descriptivas.
* Histogramas.
* Boxplots.
* Distribuciones por tipo de plan.
* Comparaciones entre segmentos.

## 5. Detección de Outliers

Se utilizó el método IQR para detectar valores atípicos en:

* Cantidad de mensajes.
* Cantidad de llamadas.
* Minutos de llamada.

Los outliers encontrados fueron conservados debido a que representan usuarios reales con alto nivel de consumo.

## 6. Segmentación de Clientes

### Segmentación por Edad

| Grupo        | Condición     |
| ------------ | ------------- |
| Joven        | age < 30      |
| Adulto       | 30 ≤ age < 60 |
| Adulto Mayor | age ≥ 60      |

### Segmentación por Uso

| Grupo     | Condición                     |
| --------- | ----------------------------- |
| Bajo uso  | llamadas < 5 y mensajes < 5   |
| Uso medio | llamadas < 10 y mensajes < 10 |
| Alto uso  | resto de usuarios             |

## 7. Generación de Insights

Se analizaron:

* Diferencias entre planes.
* Segmentos de mayor valor.
* Comportamientos extremos.
* Oportunidades comerciales.

---

# 📈 Principales Hallazgos

## Comportamiento de los Usuarios

* La mayoría de los clientes pertenece al segmento de uso medio.
* No se observó una relación fuerte entre la edad y el tipo de plan contratado.
* Los usuarios Premium presentan una ligera tendencia a consumir más minutos de llamadas.

## Outliers

Se detectaron outliers en:

* Cantidad de mensajes.
* Cantidad de llamadas.
* Minutos de llamadas.

Sin embargo, estos valores representan usuarios con uso intensivo del servicio y no errores de captura.

## Oportunidades de Negocio

* Los usuarios de alto uso representan el segmento de mayor valor.
* Existe potencial para crear planes especializados para clientes con alto consumo.
* Los usuarios de uso medio constituyen una oportunidad para estrategias de upselling.

---

# 💡 Recomendaciones

1. Diseñar planes específicos para usuarios de alto consumo.
2. Implementar campañas de migración hacia planes superiores.
3. Desarrollar programas de fidelización para clientes de alto valor.
4. Monitorear periódicamente patrones de uso extremo.
5. Utilizar segmentación por comportamiento para personalizar ofertas.

---

# 🛠️ Tecnologías Utilizadas

* Python 3.x
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Seaborn

---

# ▶️ Ejecutar el Proyecto

## 

# 👤 Autor

* Noe Castillo Zacapala

Proyecto desarrollado como ejercicio de análisis exploratorio de datos enfocado en segmentación de clientes, comportamiento de uso y generación de insights para la toma de decisiones en el sector de telecomunicaciones.
