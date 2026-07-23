# Implementación de herramientas de auditoría con IA para confrontas de IMSS/Infonavit y REPSE. Validación de conceptos ante el SAT (timbrado) y detección de discrepancias en el timbrado.

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 90 minutos (Alta Densidad de Auditoría, Control Fiscal y Seguridad Social) |
| **Complejidad** | Intermedia |
| **Audiencia** | Gerentes de Compensaciones, Analistas de Nómina, Auditores Internos, Especialistas en Relaciones Laborales y Profesionales de Recursos Humanos |
| **Tecnologías** | Microsoft Copilot Chat (M365), Microsoft Excel y Microsoft Word |
| **Enfoque** | Detección preventiva de discrepancias en el timbrado CFDI de nómina, confrontas de emisión IMSS contra SUA, auditoría de prestadores de servicios especializados (REPSE) y blindaje fiscal trilateral. |

---

## 2. Descripción Corta

Este laboratorio avanzado de 90 minutos entrena a los profesionales de compensaciones en la utilización estratégica de Microsoft Copilot como un auditor automatizado e inteligente. A través de un enfoque de fases independientes de alta resolución, los participantes implementarán conciliaciones precalculadas de cuotas IMSS (EMA/EBA vs. SUA) en **Microsoft Excel**, auditarán expedientes de contratistas en el padrón del REPSE, analizarán inconsistencias de timbrado de CFDI ante el SAT y consolidarán un informe de auditoría ejecutiva en **Microsoft Word** para mitigar multas y capitalizar la deducibilidad de la nómina.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Ejecutar confrontas de cuotas de seguridad social** IMSS (EMA/EBA) contra sistemas de nómina y SUA de forma masiva en Excel con apoyo analítico de IA.
* **Auditar expedientes y contratos de proveedores especializados (REPSE)** asegurando la deducibilidad del IVA y la acreditación de ISR mediante listas de validación inteligente.
* **Detectar discrepancias en el timbrado de CFDI de nómina** (versión 4.0) cruzando montos retenidos de ISR contra la plataforma de declaraciones del SAT.
* **Producir informes ejecutivos de auditoría laboral y fiscal** en Word listos para su presentación formal ante comités de finanzas.
* **Diseñar diagramas conceptuales de procesos de control interno** a través de la generación interactiva de imágenes con Copilot.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Copilot Chat** y generación de imágenes habilitada.
* Aplicación de **Microsoft Excel** abierta con un libro en blanco guardado como `Auditoria_Confrontas_SAT_IMSS.xlsx`.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Informe_Auditoria_Compensaciones.docx`.

---

## 5. Procedimiento Paso a Paso

### Fase A: Confronta Automatizada IMSS (EMA/EBA) contra SUA en Excel

El objetivo de esta fase independiente es procesar una matriz de confronta de cuotas IMSS que compare la emisión mensual patronal enviada por el instituto (EMA) contra los cálculos ejecutados localmente en el Sistema Único de Autodeterminación (SUA), entregando resultados y diferencias calculadas listos para copiar.

1. Abra el chat de **Microsoft Copilot**.
2. Introduzca el siguiente prompt para generar el reporte de confronta:

```
Actúa como un Especialista en Auditoría de Seguridad Social e IMSS en México. Necesito de manera urgente estructurar una matriz de confronta mensual para conciliar los datos emitidos en la propuesta del IMSS (EMA - Emisión Mensual Anticipada) contra el SUA.

Por favor, devuélveme únicamente una tabla markdown limpia para copiar y pegar en la celda A1 de Excel (en una hoja llamada "1. Confronta_IMSS") con los siguientes campos exactos y datos totalmente resueltos sin necesidad de que yo realice cálculos:
| ID Empleado | Nombre del Trabajador | SBC Reportado IMSS ($ MXN) | SBC Registrado SUA ($ MXN) | Cuota Patronal EMA ($ MXN) | Cuota Patronal SUA ($ MXN) | Diferencia Detectada ($ MXN) | Estatus de Conciliación (Muestra: "Conciliado" si la diferencia es 0, o "REVISAR INTEGRACIÓN" si hay variación) |

Incluye exactamente 4 registros realistas que simulen:
1. Dos empleados conciliados a la perfección (diferencia de $0.00).
2. Un empleado con diferencia debido a una omisión en la fecha de baja en el SUA.
3. Un empleado con diferencia debido a la aplicación incorrecta de un cambio de salario variable.

Genera únicamente la tabla markdown con los cálculos de cuotas y diferencias ya ejecutados y los estatus asignados, sin explicaciones introductorias.
```

3. Seleccione la tabla consolidada en el chat, cópiela (`Ctrl+C`) y péguela (`Ctrl+V`) en la celda `A1` de la hoja `1. Confronta_IMSS` de su archivo de Excel.

---

### Fase B: Matriz de Control de Cumplimiento de Contratistas (REPSE) en Excel

Esta fase independiente audita la deducibilidad de los servicios especializados contratados por la empresa, validando que los prestadores cumplan con las obligaciones del REPSE (registro vigente, opinión positiva del SAT, pagos de aportaciones IMSS e INFONAVIT).

1. En el chat de Copilot, introduzca el siguiente prompt para generar la matriz de cumplimiento:

```
Actúa como un Abogado Laboral and Auditor Interno en México. Necesito estructurar una matriz de control de cumplimiento técnico-legal para validar que nuestros proveedores de servicios especializados en la planta estén alineados con las regulaciones de la LFT y el REPSE.

Por favor, devuélveme una tabla markdown limpia para copiar y pegar directamente en la celda A1 de Excel (en una hoja llamada "2. Auditoría_REPSE") con los siguientes campos exactos y completamente calculados:
| Razón Social Proveedor | Servicio Especializado Contratado | Folio Registro REPSE | Estatus de Registro (Vigente / Vencido) | Opinión de Cumplimiento SAT (Positiva / Negativa) | Comprobante IMSS/INFONAVIT (Entregado / Omiso) | Estatus de Deducibilidad Contrato (Muestra: "APROBADO PARA PAGO" si todo cumple, o "RETENER PAGO - EXPEDIENTE INCOMPLETO" si falta algún requisito) |

Incluye exactamente 4 registros de proveedores ficticios (como servicios de comedor industrial, seguridad privada, mantenimiento de subestaciones y limpieza técnica) mostrando escenarios donde al menos un proveedor tenga el expediente incompleto. Devuelve únicamente la tabla markdown sin textos adicionales.
```

2. Copie la tabla generada en el chat y péguela en la pestaña `2. Auditoría_REPSE` de su archivo de Excel, ubicándose en la celda `A1`.

---

### Fase C: Interacción Práctica – Diseño de Infografía del Proceso de Blindaje Corporativo

Para documentar visualmente el proceso de validación trilateral de compensaciones ante el área de cuentas por pagar y tesorería, utilizaremos la IA para diseñar una infografía del flujo de blindaje preventivo.

1. En el chat de Copilot, introduzca el siguiente prompt para activar el motor de imágenes:

```
Crea una ilustración conceptual o diagrama de flujo con estilo de diseño corporativo limpio e industrial que represente el "Proceso de Blindaje y Auditoría Preventiva de Nómina y REPSE".

El diseño debe mostrar de forma lineal, de izquierda a derecha, tres etapas de control:
1. **Etapa 1: Auditoría de Entrada (REPSE/IMSS):** El icono de un portafolios corporativo cerrado con un escudo de verificación que representa la inspección de contratos de proveedores.
2. **Etapa 2: Conciliación Analítica (Excel/SUA):** Un panel digital moderno de hojas de cálculo de color verde que muestra una lupa analizando filas de datos de seguridad social.
3. **Etapa 3: Timbrado sin Errores (SAT):** Un icono de una marca de verificación verde y brillante que representa el cumplimiento tributario al 100%.

Utiliza tonos profesionales como gris acero, azul corporativo oscuro y verde oliva. Mantén el diseño minimalista, ordenado y completamente libre de textos complejos, confusos o distorsionados para optimizar su legibilidad técnica.
```

2. Descargue la imagen generada por la IA en su computadora con el nombre `Blindaje_Auditoria_Navegacion.png`.

---

### Fase D: Validación de Conceptos ante el SAT y Discrepancias de Timbrado

Esta fase independiente permite analizar y validar los catálogos de conceptos de pago asignados a los colaboradores frente al SAT, detectando errores comunes en la clasificación de importes gravados y exentos para efectos del cálculo de retenciones de ISR.

1. En el chat de Copilot, introduzca el siguiente prompt para generar el reporte de discrepancias en timbrado de CFDI 4.0:

```
Actúa como un Auditor Fiscal y Consultor experto en Nómina Digital (CFDI 4.0) ante el SAT en México. Necesito una matriz detallada que audite la consistencia del timbrado de los recibos de nómina frente a lo reportado en la declaración mensual de retenciones por salarios.

Por favor, proporcióname únicamente una tabla en formato markdown limpia, lista para copiar y pegar directamente en la celda A1 de Excel (en una hoja llamada "3. Auditoría_SAT"), con los cálculos ya resueltos y los siguientes campos exactos:
| Concepto de Nómina (SAT) | Clave Agrupadora SAT | Total Timbrado CFDI ($ MXN) | Total Declarado en Portal SAT ($ MXN) | Diferencia Identificada ($ MXN) | Diagnóstico del Error / Hallazgo Fiscal | Acción Correctiva de Nómina |

Incluye exactamente 3 conceptos típicos donde se generan fricciones fiscales en México:
1. Sueldos y Salarios (Clave 001).
2. Tiempo Extra (Clave 019).
3. Vales de Despensa (Clave 029 - asume un error de timbrado como gravado indebidamente).

Asegúrate de que la columna "Diferencia Identificada" muestre el resultado numérico directo restando el timbrado de lo declarado y que las acciones correctivas sean precisas y profesionales. No incluyas párrafos introductorios ni conclusiones.
```

2. Copie la tabla markdown generada por la IA y péguela en la pestaña `3. Auditoría_SAT` de su archivo de Excel, ubicándose en la celda `A1`.

---

### Fase E: Redacción del Informe Técnico de Auditoría de Compensaciones en Word

Esta fase independiente genera la documentación de soporte formal que el departamento de compensaciones presenta ante los Comités de Dirección o Auditoría para sustentar el estatus de cumplimiento legal y tributario de la nómina de la empresa.

1. Abra su archivo de **Word** (`Informe_Auditoria_Compensaciones.docx`) e introduzca el título principal: `# Informe de Auditoría y Validación Operativa: Blindaje Social, Fiscal y REPSE`.
2. Utilice el siguiente prompt en el chat de Copilot para redactar el informe técnico:

```
Actúa como un Director de Compensaciones y Auditoría Fiscal de Nóminas. Necesito redactar un informe ejecutivo formal dirigido a la Vicepresidencia de Finanzas y Recursos Humanos para mi archivo de Word. El objetivo es reportar los hallazgos identificados en los ciclos de control preventivo de la nómina, seguridad social y subcontratación.

Por favor, genera el texto estructurado exactamente en estas 3 secciones:
1. **Resultados de la Confronta de Seguridad Social (IMSS vs SUA)**: Describe con enfoque de auditoría de procesos por qué la conciliación periódica de la EMA contra el SUA mitiga riesgos de capital de trabajo y multas por discrepancias de afiliación.
2. **Estatus de Cumplimiento de Contratistas REPSE**: Redacta una justificación de control de riesgos que explique cómo la retención preventiva de pagos a proveedores de servicios especializados omisos en el expediente digital protege la deducibilidad de impuestos de la organización.
3. **Control Interno para el Timbrado de CFDI de Nómina (SAT 4.0)**: Detalla la directriz operativa obligatoria para auditar que el catálogo de conceptos del sistema de nóminas esté perfectamente alineado con los criterios fiscales de exenciones de ISR del SAT antes de cada timbrado.

Devuelve únicamente el texto formal estructurado en las tres secciones indicadas, listo para copiar y pegar en Word, con un estilo académico y técnico impecable.
```

3. Copie el texto generado por la IA y péguelo en su documento de Word debajo del título principal.
4. Inserte la imagen `Blindaje_Auditoria_Navegacion.png` (descargada en la Fase C) directamente debajo de la sección "Estatus de Cumplimiento de Contratistas REPSE" para ilustrar visualmente las capas de control corporativo que se ejecutan en la organización.

---

### Fase F: Reto de Aplicación Autónoma – Auditoría de Retenciones de Infonavit y Descuentos de Amortización

**Instrucciones para el estudiante:** El INFONAVIT ha notificado a la empresa que existen diferencias acumuladas en las amortizaciones de crédito de vivienda de tres colaboradores, lo que puede derivar en un requerimiento de pago patronal con recargos y multas si no se detecta la causa raíz de la discrepancia de manera inmediata.

#### El Desafío:
Utiliza la inteligencia artificial de forma autónoma e independiente para resolver y documentar la auditoría de descuentos de amortización:

1. **Estructura de Auditoría Infonavit (Excel):** Diseña un prompt avanzado en Copilot para obtener una tabla markdown con los datos completamente calculados de 3 empleados que puedas pegar de forma limpia en una hoja nueva de Excel llamada `4. Reto_Infonavit`.
   * *Columnas obligatorias:* `| ID Empleado | Tipo de Crédito (VSM / Cuota Fija / Porcentaje) | Valor del Descuento Bimestral INFONAVIT ($ MXN) | Descuento Aplicado en Nómina ($ MXN) | Diferencia Detectada ($ MXN) | Causa Raíz de la Desviación | Acción Correctiva de Nómina |`
2. **Justificación del Riesgo de Amortizaciones (Word):** Pídele a la IA que redacte una propuesta de control de un párrafo dirigida a Recursos Humanos, recomendando el uso de asistentes de IA para analizar mensualmente las emisiones del portal "Mis Cuentas" del Infonavit contra la nómina activa para erradicar requerimientos de pago extraordinarios.

#### Pistas de Ingeniería de Prompts para el Éxito:
* **Asignación de Rol:** Configura con exactitud el perfil de la IA: "Actúa como un Auditor Experto en Créditos INFONAVIT y Nómina en México. Genera una tabla markdown con los cálculos resueltos para 3 colaboradores donde se visualicen discrepancias por falta de aviso de retención..."
* **Limpieza de Salida:** Asegúrate de especificar en tu comando que no se agreguen saludos ni comentarios explicativos complementarios para agilizar el traslado de datos.

#### Cierre del Laboratorio:
1. Copie la tabla de auditoría del reto e insértela en la hoja `4. Reto_Infonavit` en la celda `A1` de su archivo de Excel.
2. Copie la justificación teórica y péguela en la sección final de su documento de Word.
3. Guarde ambos archivos (`Auditoria_Confrontas_SAT_IMSS.xlsx` y `Informe_Auditoria_Compensaciones.docx`). Su ecosistema avanzado para el control, validación y auditoría ante autoridades en el departamento de compensaciones se encuentra completado con éxito.

---

## 6. Conceptos Clave para Recordar

* **EMA / EBA (IMSS):** Emisión Mensual Anticipada y Emisión Bimestral Anticipada. Son los documentos que envía el IMSS al patrón mensualmente con los cálculos de cuotas que el instituto espera recibir con base en sus registros afiliatorios históricos.
* **REPSE:** Registro de Prestadores de Servicios Especializados u Obras Especializadas. Es el padrón público obligatorio en México que regula la subcontratación, cuya omisión o incumplimiento anula la deducibilidad fiscal del servicio contratado.
* **Diferencias de Timbrado:** Ocurren cuando los catálogos internos del sistema de nómina asignan incorrectamente gravámenes o exenciones a conceptos de pago, provocando discrepancias que el SAT detecta mediante sus algoritmos de fiscalización automatizados.

---

## 7. Resultado Esperado

Al finalizar los 90 minutos del laboratorio, el estudiante consolidará los siguientes entregables unificados en su espacio de trabajo:

1. **Archivo `Auditoria_Confrontas_SAT_IMSS.xlsx` (Excel):**
   * **Hoja 1 (`1. Confronta_IMSS`):** Tabla conciliada de cuotas IMSS vs. SUA con estatus de validación y cálculo de diferencias ejecutado al 100%.
   * **Hoja 2 (`2. Auditoría_REPSE`):** Matriz de evaluación de proveedores de servicios especializados con su respectivo estatus de deducibilidad contractual.
   * **Hoja 3 (`3. Auditoría_SAT`):** Matriz de control y consistencia de timbrado CFDI 4.0 frente al portal de retenciones del SAT.
   * **Hoja 4 (`4. Reto_Infonavit`):** Reporte de discrepancias de descuentos de amortización por créditos de vivienda totalmente resuelto.
2. **Archivo `Informe_Auditoria_Compensaciones.docx` (Word):**
   * Documento corporativo de auditoría de nómina que incluye el informe ejecutivo de blindaje social, la justificación de control presupuestal de subcontratación, el cual incorpora la infografía analítica `Blindaje_Auditoria_Navegacion.png` y la justificación teórica de amortizaciones del reto autónomo.
