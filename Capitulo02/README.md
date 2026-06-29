# Aplicación de IA en los Procesos de Cálculo de Nómina y Pagos a Seguridad Social. Uso de Excel con IA para Cargas Automáticas de Incidencias y Análisis de Gastos por Departamento

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 60 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Aplicar |
| **Módulo** | Capítulo 2 — Automatización de Procesos de Nómina |
| **Herramienta principal** | Microsoft Excel con Copilot integrado (Microsoft 365) |
| **Normativa aplicable** | LFT, IMSS, Infonavit, SAT (ejercicio fiscal vigente) |

---

## 2. Descripción General

En esta práctica aplicarás las capacidades de Microsoft Copilot integrado en Excel para automatizar dos procesos críticos del ciclo de nómina: la carga y validación de incidencias del período (Parte 2.1) y el análisis estratégico del gasto de nómina por departamento y centro de costos (Parte 2.2). Trabajarás con un dataset simulado de 75 empleados ficticios que incluye salarios, incidencias y tablas de cuotas vigentes de IMSS/ISR, utilizando prompts en lenguaje natural en español para instruir a Copilot sin necesidad de memorizar fórmulas complejas. Al finalizar, habrás generado un resumen de dispersión de pago, tablas dinámicas automáticas y visualizaciones que soportan la toma de decisiones del área de Compensaciones, todo ello conforme a los principios de validación humana que son no negociables en procesos de alta responsabilidad legal.

---

## 3. Objetivos de Aprendizaje

Al completar esta práctica, serás capaz de:

- [ ] **Aplicar** prompts de Copilot en Excel para limpiar, estructurar y validar una base de incidencias de nómina (faltas, horas extra, permisos e incapacidades), reduciendo el tiempo de procesamiento manual.
- [ ] **Calcular** automáticamente cuotas obrero-patronales del IMSS, aportaciones al Infonavit y retenciones de ISR mediante fórmulas asistidas por Copilot con las tablas del ejercicio fiscal vigente.
- [ ] **Generar** análisis de gasto de nómina segmentado por departamento, centro de costos y tipo de percepción, identificando desviaciones presupuestales con apoyo de Copilot.
- [ ] **Crear** visualizaciones automáticas (gráficas y tablas dinámicas) que soporten decisiones de optimización del gasto en el área de compensaciones.
- [ ] **Validar** los resultados generados por IA contra los marcos normativos mexicanos vigentes, aplicando el principio de supervisión humana en procesos de nómina.

---

## 4. Prerrequisitos

### 4.1 Conocimientos Previos

| Área | Nivel Requerido |
|---|---|
| Componentes de nómina mexicana (salario base, SDI, percepciones, deducciones) | Básico |
| Cuotas IMSS obrero-patronales y tabla de ISR (Art. 96 LISR) | Básico |
| Manejo de Excel (tablas, filtros, fórmulas básicas) | Intermedio |
| Conceptos de Copilot en Microsoft 365 (Capítulo 1 del curso) | Completado |

### 4.2 Acceso y Licenciamiento

| Requisito | Estado Requerido |
|---|---|
| Licencia activa de **Microsoft 365 Copilot** (no Copilot gratuito) | ✅ Activa y asignada |
| Microsoft Excel versión 2308 o superior (Microsoft 365) | ✅ Instalado |
| Copilot habilitado en Excel (icono visible en la cinta de opciones) | ✅ Verificado |
| Acceso a OneDrive for Business para guardar el archivo de trabajo | ✅ Disponible |
| Archivos de práctica descargados desde SharePoint del curso | ✅ Descargados |

> ⚠️ **AVISO CRÍTICO DE DATOS:** Todos los datasets utilizados en esta práctica contienen exclusivamente datos ficticios y anonimizados, conforme a la Ley Federal de Protección de Datos Personales en Posesión de los Particulares (LFPDPPP). **Está estrictamente prohibido sustituir estos datos con información real de empleados.**

---

## 5. Entorno del Laboratorio

### 5.1 Requisitos de Hardware

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8ª gen / AMD Ryzen 5 | Intel Core i7 / AMD Ryzen 7 |
| Memoria RAM | 8 GB | 16 GB |
| Almacenamiento disponible | 500 MB para archivos de práctica | 2 GB |
| Resolución de pantalla | 1366 × 768 | 1920 × 1080 |
| Conexión a internet | 10 Mbps | 25 Mbps |

### 5.2 Requisitos de Software

| Aplicación | Versión | Notas |
|---|---|---|
| Microsoft Excel | Microsoft 365 (≥ 2308) | Con Copilot habilitado en la cinta |
| Microsoft 365 Copilot | Versión actual del tenant | Licencia asignada al usuario |
| OneDrive for Business | Versión actual | Sincronizado con la cuenta corporativa |
| Navegador web | Edge 120+ o Chrome 120+ | Para acceso a SharePoint del curso |

### 5.3 Archivos de Práctica Necesarios

Descarga los siguientes archivos desde el sitio de SharePoint del curso antes de comenzar:

| Archivo | Descripción | Ubicación en SharePoint |
|---|---|---|
| `Lab02_Dataset_Nomina_Ficticios.xlsx` | Dataset de 75 empleados con salarios e incidencias del período | `Módulo 2 > Archivos de Práctica` |
| `Lab02_Tablas_IMSS_ISR_2024.xlsx` | Tablas de cuotas IMSS y tabla de ISR Art. 96 LISR vigente | `Módulo 2 > Archivos de Práctica` |
| `Lab02_Plantilla_Dispersion.xlsx` | Plantilla de resumen de dispersión de pago | `Módulo 2 > Archivos de Práctica` |

### 5.4 Configuración Inicial del Entorno

Realiza los siguientes pasos de configuración **antes** de comenzar las actividades:

1. Abre **OneDrive for Business** en el Explorador de archivos y navega a tu carpeta personal.
2. Crea una carpeta nueva llamada `Práctica_Lab02_Nómina`.
3. Copia los tres archivos de práctica descargados a esta carpeta.
4. Abre `Lab02_Dataset_Nomina_Ficticios.xlsx` desde OneDrive (no desde el escritorio local) para garantizar que Copilot tenga acceso completo al archivo en la nube.
5. Verifica que el ícono de **Copilot** (estrella de colores) aparece en la cinta de opciones de Excel, en la pestaña **Inicio**. Si no aparece, notifica al instructor antes de continuar.

```
Verificación rápida de Copilot en Excel:
Cinta de opciones → Inicio → [Ícono Copilot con estrella]
Si el ícono no aparece: Archivo → Opciones → Complementos → verificar que Copilot esté habilitado
```

---

## 6. Instrucciones Paso a Paso

---

### PARTE 2.1 — Carga Automática y Validación de Incidencias de Nómina

**Tiempo estimado:** 30 minutos

---

### Paso 1: Exploración y Diagnóstico Inicial del Dataset con Copilot

**Objetivo:** Familiarizarse con la estructura del dataset de nómina y usar Copilot para obtener un diagnóstico rápido de la calidad de los datos antes de procesar incidencias.

**Instrucciones:**

1. Con `Lab02_Dataset_Nomina_Ficticios.xlsx` abierto en Excel, ubica las siguientes hojas de trabajo:
   - **`Empleados_Base`** — Datos maestros: ID, nombre ficticio, departamento, puesto, salario mensual, SDI diario.
   - **`Incidencias_Período`** — Registro de incidencias: faltas injustificadas, horas extra, permisos con/sin goce, incapacidades IMSS.
   - **`Tablas_Cuotas`** — Porcentajes de cuotas IMSS obrero-patronales y tabla de ISR mensual.

2. Haz clic en la hoja **`Incidencias_Período`** y selecciona cualquier celda dentro de los datos (por ejemplo, celda `A2`).

3. Abre el panel de Copilot haciendo clic en el ícono de Copilot en la cinta de opciones **Inicio**.

4. En el panel de Copilot, escribe el siguiente prompt:

```
Analiza los datos de esta hoja y dime: ¿cuántos registros hay en total?, 
¿existen celdas vacías o valores faltantes en las columnas clave (ID_Empleado, 
Tipo_Incidencia, Días_Afectados, Fecha_Inicio)?, ¿hay valores duplicados 
en la columna ID_Registro? Presenta el diagnóstico en formato de tabla resumen.
```

5. Revisa la respuesta de Copilot y anota en papel o en una celda de la hoja **`Notas_Trabajo`** (si existe) los hallazgos principales.

6. Si Copilot detectó valores faltantes, escribe el siguiente prompt de seguimiento:

```
Resalta con color amarillo todas las filas que tengan celdas vacías 
en las columnas ID_Empleado, Tipo_Incidencia o Días_Afectados.
```

**Resultado Esperado:**

- El panel de Copilot muestra una tabla con el conteo total de registros (esperado: entre 150 y 200 incidencias para 75 empleados), el número de celdas vacías por columna y el conteo de duplicados.
- Las filas con datos incompletos quedan resaltadas en amarillo en la hoja, facilitando su revisión manual.

**Verificación:**

- [ ] El panel de Copilot muestra una respuesta estructurada con el diagnóstico.
- [ ] Al menos una columna del dataset muestra el conteo de valores vacíos (puede ser 0 si el dataset está limpio).
- [ ] Las filas problemáticas (si existen) están visualmente resaltadas.

---

### Paso 2: Limpieza y Estandarización de la Base de Incidencias

**Objetivo:** Usar Copilot para estandarizar los valores de la columna `Tipo_Incidencia` y asegurarse de que los datos estén en el formato correcto para el cálculo posterior.

**Instrucciones:**

1. En la hoja **`Incidencias_Período`**, identifica la columna `Tipo_Incidencia`. Observa que puede contener variaciones de escritura como: `"falta"`, `"Falta"`, `"FALTA"`, `"hrs extra"`, `"Horas Extra"`, `"HORAS EXTRA"`, `"incapacidad"`, `"Incapacidad IMSS"`.

2. En el panel de Copilot, escribe:

```
En la columna Tipo_Incidencia, estandariza todos los valores a las siguientes 
categorías exactas usando mayúsculas y sin acentos:
- FALTA_INJUSTIFICADA
- HORAS_EXTRA
- PERMISO_CON_GOCE
- PERMISO_SIN_GOCE
- INCAPACIDAD_IMSS

Aplica los cambios directamente en la columna y muéstrame cuántos registros 
pertenecen a cada categoría.
```

3. Revisa los cambios aplicados por Copilot en la columna. Si algún valor no fue clasificado correctamente, corrige manualmente esa celda.

4. Ahora verifica que la columna `Días_Afectados` solo contenga valores numéricos positivos. Escribe en Copilot:

```
Verifica que todos los valores en la columna Días_Afectados sean números 
enteros positivos mayores que 0 y menores o iguales a 30. 
Señala cualquier valor que esté fuera de este rango.
```

5. Corrige manualmente cualquier valor anómalo señalado por Copilot (por ejemplo, un valor negativo o mayor a 30 días en un mes).

**Resultado Esperado:**

- La columna `Tipo_Incidencia` muestra únicamente las cinco categorías estandarizadas.
- Copilot presenta un conteo por categoría (ejemplo: `FALTA_INJUSTIFICADA: 28`, `HORAS_EXTRA: 45`, etc.).
- La columna `Días_Afectados` no contiene valores fuera del rango válido.

**Verificación:**

- [ ] Ninguna celda en `Tipo_Incidencia` contiene variaciones de escritura no estandarizadas.
- [ ] El conteo por categoría es visible en el panel de Copilot.
- [ ] La columna `Días_Afectados` pasa la validación de rango.

---

### Paso 3: Cálculo de Percepciones y Deducciones con Fórmulas Asistidas por Copilot

**Objetivo:** Utilizar Copilot para generar las fórmulas de cálculo de percepciones (salario ordinario, prima por horas extra) y deducciones (descuento por faltas, cuota IMSS obrera, retención ISR) en la hoja de liquidación.

**Instrucciones:**

1. Navega a la hoja **`Liquidacion_Período`** del archivo. Esta hoja ya contiene los encabezados de columna pero las filas de cálculo están vacías. Los encabezados son:

   | Columna | Descripción |
   |---|---|
   | A | ID_Empleado |
   | B | Nombre_Ficticio |
   | C | Departamento |
   | D | Salario_Mensual |
   | E | SDI_Diario |
   | F | Días_Trabajados |
   | G | Salario_Ordinario |
   | H | Importe_Horas_Extra |
   | I | Descuento_Faltas |
   | J | Total_Percepciones |
   | K | Cuota_IMSS_Obrera |
   | L | Retencion_ISR |
   | M | Total_Deducciones |
   | N | Neto_a_Pagar |

2. Haz clic en la celda `G2` y abre el panel de Copilot. Escribe:

```
En la celda G2 necesito una fórmula para calcular el Salario_Ordinario. 
El salario ordinario se calcula como: Salario_Mensual (columna D) dividido 
entre 30 días, multiplicado por los Días_Trabajados (columna F). 
La columna Días_Trabajados se obtiene restando de 30 los días de faltas 
injustificadas del empleado en la hoja Incidencias_Período. 
Genera la fórmula completa con BUSCARV o SUMAR.SI.CONJUNTO según corresponda.
```

3. Copilot sugerirá una fórmula. Revísala y, si es correcta, aplícala en `G2`. Extiende la fórmula hasta el último empleado (fila 76).

4. Para calcular el importe de horas extra (columna H), escribe en Copilot:

```
En la columna H necesito calcular el importe de horas extra. 
Según la LFT mexicana, las primeras 9 horas extra semanales se pagan 
al doble del valor hora ordinaria; las horas que excedan ese límite 
se pagan al triple. El valor hora ordinaria es: Salario_Mensual / 30 / 8. 
Las horas extra del período están en la hoja Incidencias_Período. 
Genera la fórmula para H2 usando SUMAR.SI.CONJUNTO para obtener 
las horas extra del empleado y aplica la lógica del pago doble/triple.
```

5. Revisa la fórmula sugerida. **Importante:** Valida manualmente con al menos 3 empleados del dataset que el cálculo sea correcto antes de aceptarla. Aplica la fórmula en toda la columna H.

6. Para la cuota IMSS obrera (columna K), escribe en Copilot:

```
En la columna K necesito calcular la cuota obrera del IMSS. 
Usando la hoja Tablas_Cuotas donde están los porcentajes vigentes por rama 
(Enfermedad y Maternidad, Invalidez y Vida, Cesantía y Vejez, Guarderías), 
calcula la suma total de las cuotas obreras aplicadas sobre el SDI_Diario 
(columna E) multiplicado por 30 días. Genera la fórmula para K2.
```

7. Para la retención de ISR (columna L), escribe en Copilot:

```
En la columna L necesito calcular la retención mensual de ISR conforme 
al artículo 96 de la LISR. En la hoja Tablas_Cuotas existe la tabla de 
ISR mensual con columnas: Límite_Inferior, Límite_Superior, Cuota_Fija, 
Porcentaje_Excedente. La base gravable es el Total_Percepciones (columna J) 
menos el subsidio al empleo si aplica. Genera una fórmula con BUSCARV 
que ubique el rango de la base gravable y calcule el ISR correctamente.
```

8. Completa las columnas J (Total_Percepciones = G + H - I), M (Total_Deducciones = K + L) y N (Neto_a_Pagar = J - M) usando los prompts correspondientes o escribiendo las fórmulas directamente.

**Resultado Esperado:**

- La hoja `Liquidacion_Período` tiene todas las columnas calculadas para los 75 empleados.
- Los valores de `Neto_a_Pagar` son positivos y razonables para los rangos salariales del dataset.
- Las fórmulas de IMSS e ISR referencian correctamente la hoja `Tablas_Cuotas`.

**Verificación:**

- [ ] La columna G (Salario_Ordinario) muestra valores coherentes con los salarios mensuales del dataset.
- [ ] La columna K (Cuota_IMSS_Obrera) refleja los porcentajes de la tabla de cuotas vigente.
- [ ] La columna L (Retención_ISR) muestra variación entre empleados de distintos rangos salariales.
- [ ] La columna N (Neto_a_Pagar) no contiene valores negativos ni errores `#N/A` o `#¡VALOR!`.

> 💡 **Nota de validación obligatoria:** Selecciona manualmente 5 empleados del dataset y verifica sus cálculos con una calculadora o con los valores de referencia proporcionados por el instructor en el archivo `Lab02_Claves_Respuesta.pdf`. La IA asiste, pero **la responsabilidad del cálculo final es del especialista en nómina**.

---

### Paso 4: Generación del Resumen de Dispersión de Pago

**Objetivo:** Usar Copilot para consolidar los resultados de liquidación en un resumen ejecutivo de dispersión de pago, listo para enviar al área de Tesorería.

**Instrucciones:**

1. Abre la plantilla `Lab02_Plantilla_Dispersion.xlsx` (ya descargada en tu carpeta `Práctica_Lab02_Nómina`).

2. Regresa al archivo `Lab02_Dataset_Nomina_Ficticios.xlsx` y navega a la hoja `Liquidacion_Período`.

3. En el panel de Copilot, escribe:

```
Crea un resumen de dispersión de pago con los siguientes datos agrupados 
por Departamento (columna C):
- Número de empleados en el departamento
- Suma total de Neto_a_Pagar por departamento
- Suma total de Cuota_IMSS_Obrera por departamento
- Suma total de Retención_ISR por departamento
- Neto_a_Pagar mínimo, máximo y promedio por departamento

Presenta el resumen como una nueva tabla en una hoja llamada 
"Resumen_Dispersión" y agrega una fila de TOTALES al final.
```

4. Copilot creará la hoja y la tabla. Verifica que la hoja `Resumen_Dispersión` fue creada correctamente.

5. Escribe un prompt adicional para agregar el cálculo de cuotas patronales del IMSS:

```
En la hoja Resumen_Dispersión, agrega una columna llamada 
"Cuota_IMSS_Patronal" que calcule el total de cuotas patronales 
por departamento. Usa los porcentajes patronales de la hoja Tablas_Cuotas 
(Enfermedad y Maternidad, Invalidez y Vida, Retiro, Cesantía y Vejez, 
Guarderías e INFONAVIT). El cálculo base es SDI_Diario × 30 días 
× porcentaje patronal total por empleado, sumado por departamento.
```

6. Agrega una columna final `Costo_Total_Empresa` = Neto_a_Pagar + Cuota_IMSS_Patronal.

**Resultado Esperado:**

- La hoja `Resumen_Dispersión` contiene una tabla limpia con todos los departamentos del dataset.
- La fila de TOTALES muestra el monto total de nómina a dispersar.
- La columna `Costo_Total_Empresa` refleja el costo real del empleado para la organización (salario + cuotas patronales).

**Verificación:**

- [ ] La hoja `Resumen_Dispersión` existe en el libro de Excel.
- [ ] El total de `Neto_a_Pagar` en la fila TOTALES coincide con la suma de la columna N en `Liquidacion_Período` (tolerancia: ±$1 por redondeo).
- [ ] Todos los departamentos del dataset están representados en el resumen.

---

### PARTE 2.2 — Análisis de Gasto de Nómina por Departamento con Copilot

**Tiempo estimado:** 30 minutos

---

### Paso 5: Creación de Tabla Dinámica Automática con Copilot

**Objetivo:** Generar una tabla dinámica que segmente el gasto de nómina por departamento, tipo de percepción y centro de costos, usando Copilot para su configuración automática.

**Instrucciones:**

1. En el archivo `Lab02_Dataset_Nomina_Ficticios.xlsx`, navega a la hoja `Liquidacion_Período` y haz clic en cualquier celda dentro de los datos.

2. En el panel de Copilot, escribe:

```
Crea una tabla dinámica en una nueva hoja llamada "Análisis_Gasto" 
con la siguiente estructura:
- Filas: Departamento
- Columnas: Tipo de percepción (Salario_Ordinario, Importe_Horas_Extra)
- Valores: Suma de cada tipo de percepción
- Filtro: Centro_de_Costos (si existe la columna) o Puesto

Incluye también el total de Neto_a_Pagar y el Costo_Total_Empresa 
por departamento. Ordena los departamentos de mayor a menor 
costo total para la empresa.
```

3. Revisa la tabla dinámica creada por Copilot. Si algún campo no fue incluido correctamente, ajústalo manualmente en el panel de Campos de tabla dinámica.

4. Escribe un segundo prompt para agregar un análisis de horas extra:

```
En la misma hoja Análisis_Gasto, debajo de la tabla dinámica principal, 
crea una segunda tabla dinámica que muestre:
- Por departamento: total de horas extra del período, costo total 
  de horas extra, promedio de horas extra por empleado en el departamento
- Resalta los departamentos donde el costo de horas extra supere 
  el 15% del total de percepciones del departamento (posible anomalía)
```

**Resultado Esperado:**

- La hoja `Análisis_Gasto` contiene dos tablas dinámicas bien estructuradas.
- Los departamentos están ordenados de mayor a menor costo total.
- Los departamentos con horas extra anómalas (>15% de percepciones) están resaltados visualmente.

**Verificación:**

- [ ] La hoja `Análisis_Gasto` fue creada por Copilot.
- [ ] La primera tabla dinámica muestra todos los departamentos con sus percepciones desglosadas.
- [ ] La segunda tabla dinámica identifica al menos un departamento con posible anomalía en horas extra.

---

### Paso 6: Identificación de Anomalías y Desviaciones Presupuestales

**Objetivo:** Usar Copilot para detectar automáticamente empleados o departamentos con comportamientos atípicos en el gasto de nómina que requieran revisión del área de Compensaciones.

**Instrucciones:**

1. En el panel de Copilot (con la hoja `Liquidacion_Período` activa), escribe:

```
Analiza los datos de nómina e identifica las siguientes anomalías:

1. Empleados cuyo Neto_a_Pagar sea más de 2 desviaciones estándar 
   por encima del promedio de su departamento (posibles errores de captura).
2. Empleados con más de 40 horas extra en el período (posible violación 
   al artículo 68 de la LFT que limita a 9 horas semanales de tiempo extra).
3. Departamentos donde la suma de Descuento_Faltas supere el 10% 
   del total de percepciones del departamento (alto ausentismo).

Presenta los resultados en una tabla con columnas: 
Tipo_Anomalía, ID_Empleado o Departamento, Valor_Detectado, 
Umbral_Referencia, Acción_Sugerida.
```

2. Copia los resultados de anomalías a una nueva hoja llamada `Alertas_Nómina`.

3. Para el análisis de desviación presupuestal, escribe:

```
Asumiendo que el presupuesto mensual de nómina por departamento 
está en la columna "Presupuesto_Mensual" de la hoja Empleados_Base, 
calcula la desviación porcentual entre el Costo_Total_Empresa real 
(de la hoja Resumen_Dispersión) y el presupuesto asignado por departamento. 
Identifica qué departamentos están por encima del presupuesto y en qué porcentaje.
```

> 📌 **Nota:** Si la columna `Presupuesto_Mensual` no existe en el dataset, solicita al instructor el archivo complementario o utiliza como presupuesto de referencia el promedio de los últimos 3 meses multiplicado por 1.05 (incremento del 5%).

4. Guarda los resultados de desviación presupuestal en la hoja `Alertas_Nómina` junto con las anomalías del paso anterior.

**Resultado Esperado:**

- La hoja `Alertas_Nómina` contiene una tabla consolidada de anomalías detectadas.
- Al menos 2-3 anomalías son identificadas en el dataset (diseñadas intencionalmente por el instructor).
- La desviación presupuestal por departamento está calculada y muestra qué áreas excedieron su presupuesto.

**Verificación:**

- [ ] La hoja `Alertas_Nómina` existe y contiene datos.
- [ ] Las anomalías de horas extra se contrastan con el límite de la LFT (Art. 68).
- [ ] La columna `Acción_Sugerida` contiene texto descriptivo generado por Copilot.

---

### Paso 7: Generación de Visualizaciones Automáticas con Copilot

**Objetivo:** Crear gráficas automáticas con Copilot que presenten el análisis de gasto de nómina de manera visual y ejecutiva, listas para incluir en un reporte de Compensaciones.

**Instrucciones:**

1. Navega a la hoja `Análisis_Gasto` y haz clic en la tabla dinámica principal.

2. En el panel de Copilot, escribe:

```
Crea las siguientes visualizaciones basadas en los datos de nómina 
y colócalas en una nueva hoja llamada "Dashboard_Nómina":

1. Gráfica de barras apiladas: Costo total por departamento, 
   desglosado en Salario_Ordinario, Horas_Extra y Cuota_IMSS_Patronal.
   Título: "Composición del Costo de Nómina por Departamento"

2. Gráfica de pastel (pie chart): Distribución porcentual del 
   Costo_Total_Empresa por departamento.
   Título: "Participación de cada Departamento en el Gasto Total de Nómina"

3. Gráfica de líneas o barras: Top 10 empleados con mayor 
   Costo_Total_Empresa, mostrando su departamento.
   Título: "Top 10 Empleados por Costo Total para la Empresa"

Asegúrate de que todas las gráficas tengan etiquetas de datos visibles 
y leyendas claras.
```

3. Revisa las gráficas generadas en la hoja `Dashboard_Nómina`. Ajusta manualmente el tamaño y posición si es necesario para que queden organizadas.

4. Agrega un cuadro de texto o forma en la hoja `Dashboard_Nómina` con las siguientes observaciones clave (puedes pedirle a Copilot que las genere):

```
Basándote en los datos de nómina analizados, redacta 3 observaciones 
ejecutivas clave para el área de Compensaciones, en formato de viñetas, 
de máximo 2 líneas cada una. Incluye: el departamento con mayor costo, 
el departamento con mayor anomalía en horas extra, y la desviación 
presupuestal más significativa detectada.
```

5. Guarda el archivo completo en OneDrive con el nombre: `Lab02_Resultado_[TuNombreUsuario]_Nómina.xlsx`.

```
Atajo de teclado para guardar: Ctrl + S
Verificar que el archivo se guarda en OneDrive (no localmente):
Barra de título → debe mostrar el ícono de nube ☁ junto al nombre del archivo
```

**Resultado Esperado:**

- La hoja `Dashboard_Nómina` contiene tres gráficas bien etiquetadas.
- Las observaciones ejecutivas están redactadas de forma concisa y basadas en los datos reales del análisis.
- El archivo está guardado en OneDrive for Business con el nombre correcto.

**Verificación:**

- [ ] La hoja `Dashboard_Nómina` existe y contiene las tres gráficas solicitadas.
- [ ] Cada gráfica tiene título, etiquetas de datos y leyenda.
- [ ] Las observaciones ejecutivas son coherentes con los datos del dataset.
- [ ] El archivo aparece guardado en OneDrive (ícono de nube en la barra de título).

---

### Paso 8: Proyección del Impacto Presupuestal de Incrementos Salariales

**Objetivo:** Usar Copilot para simular el impacto en el gasto de nómina ante diferentes escenarios de incremento salarial, generando información estratégica para la toma de decisiones.

**Instrucciones:**

1. Navega a la hoja `Resumen_Dispersión` del archivo de trabajo.

2. En el panel de Copilot, escribe:

```
Crea una tabla de simulación de impacto presupuestal en una nueva hoja 
llamada "Simulación_Incrementos" con los siguientes escenarios de 
incremento salarial aplicados a todos los empleados:

- Escenario A: Incremento del 5% (mínimo referencial IMSS)
- Escenario B: Incremento del 8% (inflación proyectada)
- Escenario C: Incremento del 12% (propuesta sindical)
- Escenario D: Incremento diferenciado: 15% para puestos operativos 
  y 7% para puestos gerenciales

Para cada escenario calcula:
- Nuevo Costo_Total_Empresa mensual
- Incremento absoluto vs. nómina actual
- Incremento porcentual vs. nómina actual
- Impacto anual (× 12 meses) + aguinaldo (15 días) + prima vacacional

Presenta los resultados por departamento y en total general.
```

3. Revisa la tabla de simulación generada. Verifica que los cálculos del Escenario D apliquen correctamente el porcentaje diferenciado según el tipo de puesto.

4. Pide a Copilot que agregue una gráfica de barras agrupadas en la misma hoja que compare el costo total actual vs. cada escenario de incremento:

```
Agrega una gráfica de barras agrupadas en la hoja Simulación_Incrementos 
que compare el Costo_Total_Empresa actual contra los 4 escenarios de 
incremento. Usa colores distintos para cada escenario y agrega una 
línea de referencia en el presupuesto anual aprobado si está disponible.
Título: "Impacto Presupuestal por Escenario de Incremento Salarial"
```

**Resultado Esperado:**

- La hoja `Simulación_Incrementos` contiene la tabla de 4 escenarios con todos los cálculos solicitados.
- El Escenario D muestra valores diferentes para puestos operativos vs. gerenciales.
- La gráfica comparativa permite visualizar rápidamente la diferencia de costo entre escenarios.

**Verificación:**

- [ ] La hoja `Simulación_Incrementos` existe con los 4 escenarios.
- [ ] Los cálculos incluyen el impacto anual con aguinaldo y prima vacacional.
- [ ] La gráfica comparativa está presente y diferencia los escenarios por color.

---

## 7. Validación y Pruebas Finales

Al finalizar todos los pasos, realiza la siguiente lista de comprobación integral antes de dar por concluida la práctica:

### Lista de Comprobación Final

| # | Elemento a Verificar | Criterio de Éxito | ✅ |
|---|---|---|---|
| 1 | Dataset de incidencias estandarizado | Columna `Tipo_Incidencia` solo contiene las 5 categorías definidas | ☐ |
| 2 | Fórmulas de liquidación completas | Todas las celdas de `Liquidacion_Período` están calculadas sin errores | ☐ |
| 3 | Cálculo de IMSS correcto | Cuota obrera refleja porcentajes de la tabla de cuotas vigente | ☐ |
| 4 | Cálculo de ISR correcto | Retención varía según el rango de la tabla del Art. 96 LISR | ☐ |
| 5 | Resumen de dispersión completo | Hoja `Resumen_Dispersión` con todos los departamentos y fila TOTALES | ☐ |
| 6 | Tablas dinámicas creadas | Hoja `Análisis_Gasto` con 2 tablas dinámicas funcionales | ☐ |
| 7 | Anomalías identificadas | Hoja `Alertas_Nómina` con al menos 2 alertas documentadas | ☐ |
| 8 | Dashboard visual completo | Hoja `Dashboard_Nómina` con 3 gráficas etiquetadas | ☐ |
| 9 | Simulación de incrementos | Hoja `Simulación_Incrementos` con 4 escenarios y gráfica | ☐ |
| 10 | Archivo guardado en OneDrive | Nombre correcto, ícono de nube visible en barra de título | ☐ |

### Prueba de Integridad de Cálculos

Ejecuta esta verificación cruzada para confirmar la integridad de los cálculos:

1. Selecciona al azar 5 IDs de empleados del dataset.
2. Para cada empleado, verifica manualmente:
   - `Neto_a_Pagar` = `Total_Percepciones` - `Total_Deducciones`
   - `Total_Percepciones` = `Salario_Ordinario` + `Importe_Horas_Extra` - `Descuento_Faltas`
   - `Total_Deducciones` = `Cuota_IMSS_Obrera` + `Retención_ISR`
3. La tolerancia aceptable por redondeo es de ±$1.00 MXN por empleado.

```
Fórmula de verificación rápida en celda vacía:
=SUMA(N2:N76) - SUMA(J2:J76) + SUMA(M2:M76)
Resultado esperado: 0 (o muy cercano a 0 por redondeo)
```

---

## 8. Solución de Problemas

### Problema 1: El ícono de Copilot no aparece en la cinta de opciones de Excel

**Síntoma:** Al abrir Excel y navegar a la pestaña **Inicio**, el ícono de Copilot (estrella de colores) no está visible. El botón puede aparecer en gris o directamente ausente.

**Causa:** Este problema tiene tres causas principales: (a) la licencia de Microsoft 365 Copilot no está asignada correctamente a la cuenta del usuario, (b) el archivo de Excel está guardado localmente (en el escritorio o en `C:\`) en lugar de en OneDrive o SharePoint —Copilot en Excel **requiere** que el archivo esté en la nube—, o (c) la versión de Excel instalada es anterior a la 2308.

**Solución:**

```
Paso 1: Verificar ubicación del archivo
→ Barra de título del archivo → debe mostrar "OneDrive" o nombre del sitio SharePoint
→ Si muestra una ruta local (C:\Users\...), guarda el archivo en OneDrive:
   Archivo → Guardar una copia → OneDrive - [Nombre de la organización]

Paso 2: Verificar versión de Excel
→ Archivo → Cuenta → Información del producto
→ Verificar que la versión sea 2308 o superior
→ Si no lo es: Archivo → Cuenta → Opciones de actualización → Actualizar ahora

Paso 3: Verificar licencia (requiere acceso de administrador o soporte TI)
→ Navegar a: https://admin.microsoft.com
→ Usuarios → Usuarios activos → [Nombre del usuario] → Licencias
→ Verificar que "Microsoft 365 Copilot" aparece como licencia activa
→ Si no aparece, contactar al administrador de TI para asignación de licencia
```

---

### Problema 2: Las fórmulas generadas por Copilot devuelven errores `#N/A` o `#¡VALOR!` en las columnas de IMSS e ISR

**Síntoma:** Después de aplicar las fórmulas sugeridas por Copilot para calcular la cuota IMSS obrera (columna K) o la retención ISR (columna L), varias celdas muestran el error `#N/A` o `#¡VALOR!` en lugar de valores numéricos.

**Causa:** Los errores `#N/A` en fórmulas `BUSCARV` generalmente indican que el valor buscado (por ejemplo, el SDI del empleado o la base gravable de ISR) no se encuentra dentro del rango de la tabla de referencia en la hoja `Tablas_Cuotas`. Esto puede ocurrir porque: (a) los valores de la tabla de cuotas tienen formato de texto en lugar de número, (b) hay espacios en blanco ocultos en las celdas de referencia, o (c) la fórmula `BUSCARV` usa el argumento de búsqueda exacta (`0` o `FALSO`) cuando debería usar búsqueda aproximada (`1` o `VERDADERO`) para tablas de rangos como la de ISR.

**Solución:**

```
Paso 1: Verificar formato de las tablas de referencia
→ Seleccionar el rango de la tabla Tablas_Cuotas (ej. columna Límite_Inferior de ISR)
→ Inicio → Número → verificar que el formato sea "Número" o "General", no "Texto"
→ Si es texto: seleccionar el rango → Datos → Texto en columnas → Finalizar
   (esto fuerza la conversión a número)

Paso 2: Eliminar espacios ocultos en celdas de referencia
→ En una celda vacía de Tablas_Cuotas, usar: =LARGO(A2) 
→ Si el resultado es mayor al número de caracteres visibles, hay espacios ocultos
→ Aplicar: =RECORTAR(A2) para limpiar espacios

Paso 3: Corregir el argumento de búsqueda en BUSCARV para tablas de rangos ISR
→ La fórmula correcta para ISR por rangos debe usar VERDADERO (búsqueda aproximada):
   =BUSCARV(base_gravable, rango_tabla_ISR, columna_cuota_fija, VERDADERO)
→ Pedir a Copilot: "Corrige la fórmula de ISR en la columna L para usar 
   búsqueda aproximada (VERDADERO) ya que la tabla de ISR es de rangos, 
   no de valores exactos"

Paso 4: Verificar que la tabla de ISR esté ordenada de menor a mayor
→ BUSCARV con VERDADERO requiere que la primera columna esté ordenada ascendentemente
→ Seleccionar la tabla de ISR → Datos → Ordenar → por Límite_Inferior → Ascendente
```

---

## 9. Limpieza del Entorno

Al finalizar la práctica, realiza los siguientes pasos para mantener el entorno ordenado:

1. **Guardar el archivo final** en OneDrive con el nombre correcto: `Lab02_Resultado_[TuNombreUsuario]_Nómina.xlsx`.

2. **Cerrar archivos de referencia** que ya no sean necesarios (`Lab02_Tablas_IMSS_ISR_2024.xlsx` y `Lab02_Plantilla_Dispersion.xlsx`), guardando cualquier cambio si el instructor lo indicó.

3. **Compartir el archivo** con el instructor para revisión: En Excel → Compartir (esquina superior derecha) → ingresar el correo del instructor → permiso de "Solo lectura".

4. **Verificar el historial de versiones** en OneDrive para confirmar que el archivo quedó guardado correctamente:

```
Archivo → Información → Historial de versiones
→ Debe aparecer al menos una versión guardada con la fecha y hora de hoy
→ Si no aparece, guardar nuevamente con Ctrl + S
```

5. **No eliminar** los archivos de práctica de OneDrive, ya que podrán ser referenciados en prácticas posteriores del curso (especialmente en la Práctica 4 con Power Automate).

6. **Cerrar el panel de Copilot** haciendo clic en la X del panel lateral para liberar recursos del sistema.

---

## 10. Resumen y Recursos Adicionales

### Resumen de la Práctica

En esta práctica aplicaste Microsoft Copilot integrado en Excel para automatizar dos procesos críticos del ciclo de nómina en una empresa mexicana:

**Parte 2.1 — Automatización de Incidencias:**
- Diagnosticaste y limpiaste una base de incidencias de nómina usando prompts en lenguaje natural.
- Generaste fórmulas complejas de cálculo (Salario Ordinario, Horas Extra conforme a LFT, Cuota IMSS, ISR por rangos) con asistencia de Copilot.
- Construiste un resumen de dispersión de pago consolidado por departamento, incluyendo cuotas patronales.

**Parte 2.2 — Análisis Estratégico del Gasto:**
- Creaste tablas dinámicas automáticas segmentadas por departamento y tipo de percepción.
- Detectaste anomalías en horas extra y ausentismo usando umbrales normativos (LFT Art. 68).
- Generaste un dashboard visual ejecutivo con tres gráficas y observaciones estratégicas.
- Simulaste el impacto presupuestal de cuatro escenarios de incremento salarial, incluyendo prestaciones anuales.

### Principio Reforzado

> **La IA asiste, el especialista decide.** Copilot acelera el procesamiento y reduce errores mecánicos, pero la validación de los cálculos de nómina, la interpretación de las anomalías detectadas y la toma de decisiones sobre el gasto son responsabilidad exclusiva del profesional de Compensaciones. Este principio es especialmente crítico en contextos de alta responsabilidad legal como la nómina en México.

### Conexión con las Siguientes Prácticas

| Práctica | Cómo se relaciona con lo aprendido hoy |
|---|---|
| Práctica 3 (Word + Copilot) | Los reportes de anomalías de nómina generados en esta práctica se convertirán en documentos formales de auditoría |
| Práctica 4 (Power Automate) | El resumen de dispersión de pago se automatizará para enviarse por correo al área de Tesorería |
| Práctica 7 (Copilot Studio) | El agente de IA utilizará los datos de gasto por departamento para responder consultas ejecutivas en tiempo real |

### Recursos Adicionales

| Recurso | Descripción | URL |
|---|---|---|
| Documentación de Copilot en Excel | Guía oficial de Microsoft sobre prompts y capacidades | [learn.microsoft.com/es-es/copilot/microsoft-365/excel](https://learn.microsoft.com/es-es/copilot/microsoft-365/excel) |
| Tablas de cuotas IMSS vigentes | Portal oficial del IMSS para patrones | [imss.gob.mx/patrones/obligaciones](https://www.imss.gob.mx/patrones/obligaciones) |
| Tabla ISR Art. 96 LISR | SAT — Retención mensual de ISR para trabajadores | [sat.gob.mx](https://www.sat.gob.mx/consultas/23972/comprobantes-de-nomina) |
| Límites de tiempo extra (LFT) | Art. 66-68 de la Ley Federal del Trabajo | [trabajo.gob.mx/LFT](https://www.gob.mx/cms/uploads/attachment/file/156203/1044_Ley_Federal_del_Trabajo.pdf) |
| Galería de prompts para Excel | Prompts de ejemplo para análisis de datos con Copilot | [adoption.microsoft.com/copilot-scenario-library](https://adoption.microsoft.com/en-us/copilot-scenario-library/) |

---

*Práctica completada. Asegúrate de que tu archivo esté guardado en OneDrive y compartido con el instructor antes de avanzar a la siguiente actividad del curso.*
