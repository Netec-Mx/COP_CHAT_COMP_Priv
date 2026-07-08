# Aplicación de IA en los Procesos de Cálculo de Nómina y Pagos a Seguridad Social. Uso de Excel con IA para Cargas Automáticas de Incidencias y Análisis de Gastos por Departamento

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 60 minutos |
| **Complejidad** | Intermedia |
| **Audiencia** | Gerentes de Compensaciones, Analistas de Nómina, Especialistas en Relaciones Laborales y Profesionales de Recursos Humanos |
| **Tecnologías** | Microsoft Copilot Chat (M365), Copilot Image Generator (DALL-E), Microsoft Excel y Microsoft Word |
| **Enfoque** | Optimización operativa del ciclo de nómina mediante la automatización de la carga de incidencias, layouts de seguridad social y análisis predictivo de gastos departamentales utilizando inteligencia artificial. |

---

## 2. Descripción Corta

Este laboratorio de 60 minutos capacita a los profesionales del área en el uso de Microsoft Copilot para acelerar los procesos de cálculo de nómina y mitigar errores operativos de captura. Cada fase de este laboratorio está diseñada para ser completamente independiente, entregando resultados listos para copiar y pegar directamente en las herramientas de trabajo cotidianas (Excel y Word), acompañados de una representación visual del ecosistema de automatización.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Generar matrices estructuradas de incidencias** mediante IA listas para su uso inmediato en hojas de cálculo.
* **Aplicar fórmulas lógicas de validación y control presupuestal** mediante bloques de datos precalculados por la IA.
* **Unificar directrices visuales y flujos de trabajo** empleando el generador de imágenes de Copilot para documentar procesos de nómina.
* **Estructurar políticas corporativas de control interno** en Word usando prompts de redacción ejecutiva avanzada.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Copilot Chat** y generación de imágenes habilitada.
* Aplicación de **Microsoft Excel** abierta con un libro en blanco guardado como `Automatizacion_Nomina_Incidencias.xlsx`.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Politica_Control_Incidencias.docx`.

---

## 5. Procedimiento Paso a Paso

### Fase A: Estructuración del Layout de Incidencias en Excel

El objetivo de esta fase es utilizar la IA para modelar y estructurar una matriz de incidencias del personal por departamento con datos realistas, lista para ser insertada directamente en la primera pestaña de la hoja de cálculo.

1. Abra el chat de **Microsoft Copilot**.
2. Introduzca el siguiente prompt para generar el conjunto de datos completo:

```
Actúa como un Especialista Senior en Procesamiento de Nóminas y Sistemas ERP en México. Necesito diseñar un layout estandarizado para la captura mensual de incidencias de personal.

Por favor, devuélveme una tabla markdown limpia para copiar y pegar directamente en la celda A1 de Excel con las siguientes columnas exactas:
| ID Empleado | Nombre Colaborador | Departamento | Centro de Costos | Tipo de Incidencia | Cantidad (Días/Horas) | Impacto en Pago | Fecha de Registro |

Incluye exactamente 5 registros realistas que muestren variaciones entre los departamentos de Operaciones, Ventas, Finanzas y TI utilizando incidencias comunes como "Faltas", "Horas Extra Dobles", "Horas Extra Triples" e "Incapacidad". Genera únicamente la tabla markdown con los datos completamente calculados y listos, sin agregar textos introductorios ni explicaciones.
```

3. Seleccione la tabla generada en el chat, cópiela (`Ctrl+C`) y péguela (`Ctrl+V`) en la celda `A1` de la hoja `1. Control_Incidencias` de su archivo de Excel.

---

### Fase B: Matriz Analítica de Fórmulas y Análisis de Gastos por Departamento

Esta fase es independiente y sirve para generar un reporte de auditoría presupuestal completamente resuelto. La IA procesará las incidencias, ejecutará los cálculos de horas acumuladas y estatus de alertas legales, entregando una matriz terminada para su pegado inmediato.

1. En el chat de Copilot, introduzca el siguiente prompt:

```
Actúa como un Auditor Senior de Compensaciones y Control de Gestión de Nóminas. Necesito un reporte consolidado y resuelto de auditoría analítica de gastos por incidencias y alertas de control legal para la Dirección.

Por favor, devuélveme únicamente una tabla en formato markdown limpia, lista para copiar y pegar directamente en la celda A1 de Excel, con los cálculos ya ejecutados y los siguientes campos exactos:
| Departamento | Total Horas Extra Dobles Acumuladas | Alerta Límite Legal (Muestra: "OK" si es menor o igual a 9 hrs, o "REVISIÓN COMPENSACIONES" si excede) | Gasto Mensual Calculado por Incidencias ($ MXN) | Nivel de Riesgo Presupuestal (Bajo/Medio/Alto) | Acción Mitigante Obligatoria |

Incluye exactamente 4 registros correspondientes a los departamentos de Operaciones (asume 14 horas extra acumuladas), Ventas (asume 6 horas), Finanzas (asume 0 horas) y TI (asume 11 horas). Asegúrate de que las alertas y los gastos mensuales muestren los resultados lógicos ya resueltos. No incluyas explicaciones matemáticas ni textos fuera de la tabla markdown.
```

2. Copie la tabla markdown generada por la IA y péguela en una pestaña nueva de Excel llamada `2. Analisis_Gastos` en la celda `A1`. El reporte queda integrado de manera automática con sus métricas calculadas.

---

### Fase C: Interacción Práctica – Diseño Visual del Ciclo de Sincronización (Copilot)

Esta fase se enfoca de manera autónoma en la creación de una infografía técnica que sirva de apoyo visual para capacitar a los supervisores sobre las etapas correctas en el flujo de la información de nómina.

1. En el chat de Copilot, introduzca el siguiente prompt para activar el motor gráfico:

```
Crea un diagrama de flujo con estilo de diseño corporativo limpio y moderno que ilustre el "Ecosistema Automatizado de Carga de Incidencias y Nómina".

El flujo debe conectar de forma lineal tres conceptos clave:
1. **Paso 1: Captura Departamental:** Icono de un usuario ingresando novedades de personal en una interfaz digital azul claro.
2. **Paso 2: Procesamiento Centralizado (IA/Excel):** Un engranaje moderno junto a un archivo de hoja de cálculo digital que procesa las incidencias y calcula las variaciones.
3. **Paso 3: Dispersión Bancaria y Seguridad Social:** Un icono de una transferencia digital exitosa junto a un escudo institucional, representando el pago exacto y puntual.

Usa tonos profesionales de gris acero, azul corporativo y detalles en naranja suave. Mantén el diseño minimalista, ordenado y libre de textos confusos para asegurar su legibilidad técnica.
```

2. Cuando la imagen esté lista, haga clic en ella, seleccione **Descargar** y guárdela localmente con el nombre `Ciclo_Automatizacion_Nomina.png`.

---

### Fase D: Redacción de la Política de Control Interno en Word

Esta fase independiente genera la documentación normativa en prosa técnica ejecutiva que formaliza los tiempos de entrega y responsabilidades de los líderes de área respecto al reporte de incidencias.

1. Abra su archivo de **Word** (`Politica_Control_Incidencias.docx`) e introduzca el título inicial: `# Política de Control Interno: Reporte y Automatización de Incidencias de Nómina`.
2. Utilice el siguiente prompt en el chat de Copilot para estructurar el contenido formal del documento:

```
Actúa como un Gerente de Recursos Humanos y Auditoría Interna. Necesito redactar el cuerpo formal para una política corporativa que controle el proceso de envío de novedades de nómina de los líderes de departamento hacia el área de compensaciones.

Por favor, genera el texto formal estructurado exactamente en estas 3 secciones:
1. **Objetivo y Alcance del Control de Incidencias**: Explica la importancia de estandarizar la entrega de novedades mediante formatos unificados para evitar retrasos en el cálculo de la nómina y garantizar que los impactos de seguridad social se determinen sobre datos reales.
2. **Calendario y Responsabilidades de los Líderes de Área**: Redacta las directrices imperativas que obligan a los jefes de departamento a revisar y validar los reportes de tiempos (horas extra, faltas, turnos) antes del cierre de la pre-nómina.
3. **Consecuencias Operativas del Reporte Extemporáneo**: Detalla los riesgos financieros y de clima laboral si las incidencias no se reportan a tiempo, afectando retroactivamente el cálculo del salario integrado y las aportaciones obligatorias.

Devuelve únicamente el texto formal estructurado en las tres secciones indicadas, listo para copiar y pegar en Word.
```

3. Copie el texto generado por la IA y péguelo en su documento de Word debajo del título principal. 
4. Inserte la imagen `Ciclo_Automatizacion_Nomina.png` (descargada previamente en la Fase C) directamente abajo de la sección de "Calendario y Responsabilidades" para ilustrar gráficamente el proceso normativo.

---

### Fase E: Reto de Aplicación Autónoma – Análisis Automatizado de Ausentismo por Centro de Costos

**Instrucciones para el estudiante:** El Director de Finanzas solicita un reporte inmediato sobre el impacto financiero que genera el ausentismo no justificado en la organización para tomar medidas drásticas de control presupuestal, sin requerir cálculos adicionales del usuario.

#### El Desafío:
Utiliza la inteligencia artificial de forma independiente para generar el entregable analítico solicitado:

1. **Estructura Analítica de Ausentismo (Excel):** Diseña un prompt específico en Copilot para obtener una tabla markdown con los datos completamente calculados de 3 departamentos que puedas pegar de forma limpia en una hoja nueva llamada `3. Analisis_Ausentismo`.
   * *Columnas requeridas:* `| Centro de Costos | Departamento | Total de Colaboradores | Días de Ausencia Registrados | Tasa de Ausentismo Mensual (%) | Costo Financiero Estimado por Reemplazos ($ MXN) |`
2. **Estrategia de Mitigación de Pérdidas (Word):** Pídele a la IA que redacte una propuesta ejecutiva corta de un párrafo dirigida a la Dirección de Recursos Humanos, recomendando el uso de modelos analíticos en hojas de cálculo automatizadas para identificar patrones de ausentismo por turnos y optimizar la planeación de la fuerza laboral.

#### Pistas de Ingeniería de Prompts para el Éxito:
* **Foco en el Rol:** Define con precisión el perfil del copiloto: `"Actúa como un Analista de Control de Gestión de Fuerza Laboral. Proporciona una tabla markdown con datos coherentes para 3 departamentos, donde la Tasa de Ausentismo se calcule de forma lógica..."`
* **Salida Limpia:** Exige que la respuesta contenga únicamente la tabla y los párrafos en bloques de código utilizables, evitando explicaciones introductorias fuera del formato deseado.

#### Cierre del Laboratorio:
1. Copie la tabla integrada obtenida en el reto e insértela en la hoja `3. Analisis_Ausentismo` en la celda `A1` de su archivo de Excel.
2. Copie la justificación teórica al final de su documento de Word.
3. Guarde ambos archivos (`Automatizacion_Nomina_Incidencias.xlsx` y `Politica_Control_Incidencias.docx`) para finalizar la práctica.

---

## 6. Conceptos Clave para Recordar

* **Pre-nómina:** Proceso de consolidación, validación y control de todas las novedades, incidencias, percepciones y deducciones aplicables a los trabajadores en un periodo específico antes de ejecutar el cálculo definitivo y dispersión de fondos.
* **Centro de Costos:** Unidad contable interna de la empresa que agrupa los gastos relacionados con un proyecto, departamento o área específica, permitiendo un análisis detallado de la eficiencia del capital humano.
* **Layout de Carga:** Estructura de datos técnica y estandarizada (generalmente en formato CSV o Excel) configurada con precisión para permitir la importación masiva de información entre diferentes plataformas informáticas sin requerir intervención manual.

---

## 7. Resultado Esperado

Al finalizar los 60 minutos del laboratorio, el estudiante consolidará los siguientes entregables unificados:

1. **Archivo `Automatizacion_Nomina_Incidencias.xlsx` (Excel):**
   * **Hoja 1 (`1. Control_Incidencias`):** Tabla de incidencias mensuales por departamento parametrizada para compatibilidad con sistemas de nómina.
   * **Hoja 2 (`2. Analisis_Gastos`):** Matriz presupuestal por incidencias con las directrices de las fórmulas lógicas de auditoría.
   * **Hoja 3 (`3. Analisis_Ausentismo`):** Reporte financiero y porcentual consolidado sobre la tasa de ausentismo y sus costos de cobertura por centro de costos.
2. **Archivo `Politica_Control_Incidencias.docx` (Word):**
   * Estructura formal de política corporativa para el reporte de novedades, integrando de manera ordenada la infografía de sincronización de procesos de datos `Ciclo_Automatizacion_Nomina.png` y la justificación analítica del reto autónomo.
