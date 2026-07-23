# Limpieza y Análisis de Bases de Datos Salariales mediante Copilot en Excel

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 90 minutos (Densidad de Datos Avanzada, Optimización y Análisis Masivo) |
| **Complejidad** | Intermedia |
| **Audiencia** | Gerentes de Compensaciones, Analistas de Nómina, Administradores de Sistemas de RRHH y Especialistas en Analytics |
| **Tecnologías** | Microsoft Copilot (M365), Microsoft Excel y Microsoft Word |
| **Enfoque** | Limpieza de datos salariales a gran escala, normalización de textos corruptos, eliminación de registros duplicados invisibles, diseño de diccionarios de datos estructurados y preparación de layouts maestros para sistemas ERP/HRMS. |

---

## 2. Descripción Corta

Este laboratorio de 90 minutos entrena a los profesionales de compensaciones en el uso analítico de Microsoft Copilot para depurar, limpiar y estructurar archivos de nómina o encuestas salariales que contienen miles de registros e inconsistencias de formato. A través de fases independientes de alta resolución, los participantes generarán layouts de datos crudos corruptos en **Microsoft Excel** para resolver problemas de espacios vacíos y formatos numéricos rotos, y estructurarán un diccionario de datos técnico y reglas de gobierno de calidad de información en **Microsoft Word**.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Identificar y depurar anomalías en bases de datos masivas** (espacios en blanco, caracteres extraños, duplicados lógicos) utilizando comandos de asistencia de IA.
* **Estandarizar registros de texto y formatos numéricos** de salarios para asegurar la compatibilidad con herramientas de Inteligencia de Negocio (BI).
* **Diseñar diccionarios de datos maestros (Data Dictionaries)** estructurados para bases de datos de compensaciones.
* **Establecer reglas de gobierno para la calidad del dato (Data Quality Rules)** que prevengan la corrupción de archivos históricos.
* **Generar visualizaciones conceptuales de Dashboards Analíticos** masivos mediante instrucciones complejas en Copilot.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Microsoft Copilot**.
* Aplicación de **Microsoft Excel** abierta con un libro en blanco guardado como `Limpieza_Grandes_Volumenes_Nomina.xlsx`.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Diccionario_Y_Gobierno_Datos.docx`.

---

## 5. Procedimiento Paso a Paso

### Fase A: Simulación y Depuración de Datos Salariales Corruptos en Excel

El objetivo de esta fase independiente es generar una base de datos masiva de prueba con errores comunes de captura (nombres en mayúsculas/minúsculas desordenadas, espacios extra, formatos numéricos inconsistentes) para aplicar técnicas automatizadas de limpieza en Excel con la guía analítica de la IA.

1. Abra el chat de **Microsoft Copilot**.
2. Introduzca el siguiente prompt para generar el set de datos con inconsistencias controladas:

```
Actúa como un Ingeniero de Datos de Recursos Humanos. Necesito un set de pruebas en formato de tabla markdown para simular una base de datos salarial masiva extraída de un sistema antiguo que contiene severos problemas de calidad.

Por favor, devuélveme una tabla markdown limpia, lista para copiar y pegar en la celda A1 de Excel (en una hoja llamada "1. Datos_Crudos") que contenga exactamente 5 registros realistas con las siguientes columnas, simulando los errores que te detallo a continuación:
| ID_Empleado | Nombre_Completo | Departamento | Puesto | Salario_Mensual_Texto | Fecha_Ingreso_Inconsistente |

Simula estos errores específicos en las filas:
- Fila 1 y 2: Nombres duplicados pero con sutiles variaciones de espacios en blanco al inicio o al final.
- Fila 3: El campo Salario_Mensual_Texto debe venir como texto mezclado con letras (Ejemplo: "MXN 45,000" o "35000 fijos") rompiendo la capacidad de Excel de sumarlo.
- Fila 4: Nombres escritos en un desorden caótico de mayúsculas y minúsculas (Ejemplo: "jUaN pÉrEz mArTíNeZ").
- Fila 5: Departamentos con nombres inconsistentes (Ejemplo: "RH", "Rec. Humanos", "Human Resources" para referirse al mismo área).

Genera únicamente la tabla markdown sin textos introductorios ni instrucciones de fórmulas todavía.
```

3. Seleccione la tabla generada en el chat, cópiela (`Ctrl+C`) y péguela (`Ctrl+V`) en la celda `A1` de la hoja `1. Datos_Crudos` de su archivo de Excel.

---

### Fase B: Generación de Guía Técnica de Fórmulas y Scripts de Limpieza en Excel

Esta fase independiente permite al usuario obtener de la IA las funciones exactas de Excel en español (como ESPACIOS, NOMPROPIO, SUSTITUIR, VALOR) o scripts necesarios para corregir de forma masiva los errores inyectados en la Fase A, normalizando el archivo para su uso analítico.

1. En el chat de Copilot, introduzca el siguiente prompt para extraer las instrucciones de depuración:

```
Actúa como un Experto Avanzado en Microsoft Excel y Analista de Compensaciones. Necesito que me proporciones las fórmulas exactas en español y los pasos lógicos que debo aplicar en columnas adicionales de mi hoja "1. Datos_Crudos" para limpiar la información corrupta generada previamente.

Por favor, devuélveme una tabla markdown limpia para copiar en Excel (en una hoja llamada "2. Guía_Limpieza") con las siguientes columnas exactas:
| Problema Detectado | Columna Afectada | Fórmula de Excel Recomendada (En Español) | Explicación del Comportamiento de la Fórmula | Resultado Esperado Esperable |

Asegúrate de cubrir de forma matemática y lógica:
1. Cómo eliminar los espacios invisibles adicionales alrededor del texto.
2. Cómo estandarizar los nombres desordenados a formato de nombre propio.
3. El truco con fórmulas para extraer solo el valor numérico de una celda que contiene texto y convertirlo en un número operable.

Proporciona únicamente la tabla markdown limpia sin introducciones informales.
```

2. Copie la tabla markdown del chat y péguela en la pestaña `2. Guía_Limpieza` de su archivo de Excel, ubicándose en la celda `A1`.

---

### Fase C: Interacción Práctica – Diseño Visual de un Dashboard de Analítica de Big Data

Para romper los flujos tradicionales, diseñaremos una interfaz visual avanzada que simule un panel de control ejecutivo de analítica masiva (Big Data) enfocado en la dispersión salarial y el análisis de equidad de género de toda la corporación.

1. En el chat de Copilot, introduzca el siguiente prompt para activar la generación gráfica del panel de control:

```
Crea una vista conceptual en perspectiva de una pantalla de computadora que muestra un "Executive Dashboard de Analítica Masiva de Compensaciones y Big Data".

La interfaz debe lucir moderna e interactiva, mostrando un diseño oscuro compuesto por tres secciones de gráficos analíticos avanzados:
1. **Gráfico Central:** Un mapa de calor denso (Heatmap) con degradados de color púrpura y azul eléctrico que muestra la concentración de salarios por regiones geográficas.
2. **Gráfico Derecho:** Un diagrama de dispersión de puntos densos (Scatter Plot) con una línea de tendencia que analiza la equidad salarial por género.
3. **Métricas Clave (KPIs):** Paneles digitales en la parte superior mostrando números macro y porcentajes globales de rotación e incremento presupuestal.

El estilo visual debe ser de tecnología financiera de punta, minimalista, limpio, ordenado y completamente libre de textos legibles, palabras distorsionadas o caracteres de relleno para resaltar la estética de los datos.
```

2. Una vez generado el gráfico por la IA, descárguelo en su computadora con el nombre `Dashboard_Analitica_Compensaciones.png`.

---

### Fase D: Estructuración del Diccionario de Datos Maestro en Word

El objetivo de esta fase independiente es generar la documentación técnica en Word que define la estructura oficial, tipos de datos, longitudes y restricciones que debe cumplir cualquier reporte salarial antes de ser cargado en las plataformas analíticas de la empresa.

1. Abra su archivo de **Word** (`Diccionario_Y_Gobierno_Datos.docx`) e introduzca el título: `# Documento Técnico de Gobierno de Datos: Diccionario de Compensaciones`.
2. Utilice el siguiente prompt en el chat de Copilot para redactar el diccionario maestro de datos:

```
Actúa como un Arquitecto de Datos y Administrador de Sistemas de Información de Recursos Humanos (HRIS). Necesito redactar el Diccionario de Datos Maestro de la base de datos de compensaciones de la compañía para asegurar que futuros archivos mantengan la integridad estructural.

Por favor, genera únicamente una tabla en formato markdown limpia, lista para pegar en Word, con las siguientes columnas exactas:
| Nombre del Campo Técnico | Descripción del Campo | Tipo de Dato (Alfanumérico / Numérico / Fecha) | Longitud Máxima (Caracteres) | Restricciones / Reglas de Validación de Negocio | Ejemplo de Entrada Válida |

Incluye exactamente 5 campos críticos del sistema: ID_Colaborador, RFC_Completo, Codigo_Puesto_ERP, Salario_Diario_Integrado, y Clave_Estructura_Costos. Asegúrate de que las reglas de negocio detallen formatos específicos (como máscaras de caracteres para el RFC o valores permitidos). No agregues texto introductorio.
```

3. Copie la tabla generada en el chat y péguela en su documento de Word debajo del título principal.

---

### Fase E: Matriz de Reglas de Calidad del Dato (Data Quality Rules) en Word

Esta fase independiente establece las políticas y umbrales de aceptación para la carga de archivos masivos, definiendo qué porcentaje de errores es tolerable y qué acciones automáticas se ejecutan si un archivo de nómina no cumple con los estándares mínimos de calidad.

1. En el chat de Copilot, elija el siguiente prompt para generar las reglas de validación operacional:

```
Actúa como un Director de Gobierno de Datos y Compensaciones. Necesito redactar la sección de "Reglas de Calidad del Dato e Integridad Operativa" para el manual de control interno.

Por favor, genera el contenido estructurado exactamente en los siguientes 3 apartados ejecutivos en prosa:
1. **Dimensión de Completitud y Precisión**: Explica detalladamente las penalizaciones de proceso que se aplican si un reporte de nómina masivo llega con celdas vacías en campos clave como el salario o departamento, detallando el impacto en el cálculo presupuestal.
2. **Umbrales de Aceptación de Carga (SLA de Datos)**: Define los porcentajes máximos de variación permitidos en los layouts salariales antes de rechazar un archivo completo proveniente de una unidad de negocio (por ejemplo, rechazo automático si más del 1% de los registros fallan en el formato de datos).
3. **Protocolo de Saneamiento y Re-procesamiento**: Detalla la directriz operativa obligatoria para el equipo de analistas cuando una base de datos es rechazada, especificando los tiempos de respuesta y los métodos aprobados para su corrección.

Devuelve únicamente el texto formal estructurado en las tres secciones indicadas, con un estilo técnico e imperativo impecable, listo para pegar en Word.
```

2. Copie el texto normativo e insértelo en su documento de Word bajo la sección `# 2. Reglas Corporativas de Calidad del Dato (Data Quality)`.

---

### Fase F: Reto de Aplicación Autónoma – Layout Maestro de Carga para un Sistema ERP/HRMS

**Instrucciones para el estudiante:** La compañía migrará a un nuevo sistema ERP global (como SAP SuccessFactors, Oracle HCM o Workday) el próximo mes. El sistema requiere de manera mandatoria un layout de carga masiva perfectamente formateado, limpio y libre de duplicados lógicos para migrar los salarios y prestaciones de los colaboradores sin generar caídas en los servidores del proveedor.

#### El Desafío:
Utiliza la inteligencia artificial de forma totalmente autónoma para resolver el diseño estructural del layout de migración:

1. **Diseño de Layout Estricto ERP (Excel):** Diseña un prompt avanzado en Copilot para obtener una tabla markdown limpia con los datos completamente formateados de 3 empleados muestra que puedas pegar en una hoja nueva de Excel llamada `3. Layout_Carga_ERP`.
   * *Columnas obligatorias:* `| SYS_ID_USER | BASE_SALARY_AMOUNT | CURRENCY_CODE | FREQUENCY_PAYMENT | EFFECTIVE_START_DATE | EXEMPT_TAX_STATUS (Y/N) | COST_CENTER_CODE |`
   * *Regla técnica:* Asegúrate de que las fechas tengan formato ISO estricto (`AAAA-MM-DD`) y los salarios vengan redondeados a dos decimales sin comas separadoras de miles (Ejemplo: `52450.50`).
2. **Justificación de la Migración Segura (Word):** Pídele a la IA que redacte un párrafo de cierre ejecutivo que explique los riesgos económicos y operativos que implica subir datos con formatos numéricos rotos o fechas inválidas a los sistemas de producción de la empresa.

#### Pistas de Ingeniería de Prompts para el Éxito:
* **Asignación del Rol:** Modela con precisión el comportamiento del asistente: "Actúa como un Consultor Senior de Implementación ERP y Sistemas de Compensaciones. Genera la tabla markdown del layout técnico de migración masiva cumpliendo con las siguientes reglas de formato..."
* **Filtro de Ruido:** Estipula claramente en tu instrucción que no se incluyan explicaciones de relleno ni saludos conversacionales del chat para una copia fluida de los datos.

#### Cierre del Laboratorio:
1. Copie la tabla del layout de carga generada en el reto autónomo.
2. Péguela en la pestaña `3. Layout_Carga_ERP` en la celda `A1` de su archivo de Excel.
3. Copie la justificación técnica de la migración e insértela en la parte final de su documento de Word.
4. Inserte la imagen `Dashboard_Analitica_Compensaciones.png` (descargada en la Fase C) directamente al inicio de la sección de reglas de calidad del dato para dar soporte visual al análisis masivo del manual.
5. Guarde ambos archivos (`Limpieza_Grandes_Volumenes_Nomina.xlsx` y `Diccionario_Y_Gobierno_Datos.docx`). Su arquitectura corporativa para el gobierno, limpieza y manejo de grandes volúmenes de datos salariales ha quedado completamente unificada.

---

## 6. Conceptos Clave para Recordar

* **Diccionario de Datos:** Documento centralizado que describe la estructura, significado, tipo, formato y restricciones de los campos de una base de datos para asegurar el entendimiento común entre las áreas de TI y el negocio.
* **Layout de Carga Masiva:** Archivo con una estructura y formato técnico rígidamente predefinidos que los sistemas de software (como ERPs) exigen para importar grandes volúmenes de registros de una sola vez de forma segura.
* **Gobierno de Datos (Data Governance):** Conjunto de principios, políticas y prácticas que aseguran que los datos de una organización sean precisos, confiables, seguros y estén disponibles para la correcta toma de decisiones estratégicas.

---

## 7. Resultado Esperado

Al finalizar los 90 minutos del laboratorio, el estudiante consolidará los siguientes entregables unificados en su equipo:

1. **Archivo `Limpieza_Grandes_Volumenes_Nomina.xlsx` (Excel):**
   * **Hoja 1 (`1. Datos_Crudos`):** Matriz base con registros salariales que simulan errores intencionales de mayúsculas, espacios y tipos de datos de texto rotos.
   * **Hoja 2 (`2. Guía_Limpieza`):** Guía de referencia técnica cruzada con las fórmulas exactas en español sugeridas por la IA para depurar el archivo.
   * **Hoja 3 (`3. Layout_Carga_ERP`):** Estructura técnica resuelta del layout limpio de migración con formatos de fecha ISO y salarios sin caracteres especiales.
2. **Archivo `Diccionario_Y_Gobierno_Datos.docx` (Word):**
   * Manual normativo técnico de gobierno corporativo que contiene el diccionario detallado de campos del área de compensaciones, las políticas e indicadores (SLA) de calidad de información para procesos de carga, la justificación de riesgos de migración de sistemas y el soporte gráfico del panel de control de Big Data `Dashboard_Analitica_Compensaciones.png`.
