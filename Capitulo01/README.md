# Uso de IA para la interpretación de leyes, reglamentos y reformas laborales (IMSS, Infonavit, LFT). Creación de agentes de consulta para soporte legal y análisis de impacto en nóminas.

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 60 minutos (Alta Densidad de Análisis de Cumplimiento y Costeo) |
| **Complejidad** | Intermedia |
| **Audiencia** | Gerentes de Compensaciones, Analistas de Nómina, Especialistas en Relaciones Laborales y Profesionales de Recursos Humanos |
| **Tecnologías** | Microsoft Copilot Chat (M365), Copilot Image Generator (DALL-E), Microsoft Excel y Microsoft Word |
| **Enfoque** | Aplicación dual de IA para la interpretación precisa de reformas laborales en México (LFT, IMSS, Infonavit, SAT), automatización de matrices de costo patronal e integración de un plan de blindaje fiscal. |

---

## 2. Descripción Corta

Este laboratorio de 60 minutos capacita a los profesionales de compensaciones en el uso de Microsoft Copilot como un copiloto legal y fiscal de alta velocidad. Los participantes aprenderán a interrogar de forma avanzada a la IA para interpretar reformas críticas (como el incremento gradual de las cuotas patronales de Cesantía y Vejez, o cambios en la integración del Salario Base de Cotización - SBC), modelarán los impactos financieros en el costo de la nómina patronal utilizando **Microsoft Excel**, redactarán un memorándum oficial de cumplimiento en **Microsoft Word** para la dirección general y generarán una infografía conceptual sobre el flujo de auditoría regulatoria utilizando el motor gráfico de Copilot.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Construir prompts de consulta normativa avanzada** para interpretar reglamentos, reformas y artículos específicos de la LFT, Ley del Seguro Social (LSS) e Infonavit con precisión jurídica.
* **Mapear y evaluar el impacto financiero** del aumento de costos de seguridad social o prestaciones sobre el factor de integración de la nómina en Excel.
* **Estructurar un memorándum ejecutivo de cumplimiento** in Word, traduciendo cambios regulatorios complejos en acciones operativas claras para el equipo de nóminas.
* **Diseñar diagramas de flujo de validación legal** utilizando herramientas visuales de IA para estandarizar procesos de auditoría internos.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Copilot Chat** y generación de imágenes habilitada.
* Aplicación de **Microsoft Excel** abierta con un libro en blanco guardado como `Matriz_Impacto_Reformas.xlsx`.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Memo_Cumplimiento_Legal.docx`.

---

## 5. Procedimiento Paso a Paso

### Fase A: Ingeniería de Prompts para Consulta de Reformas y LFT (Copilot)

El primer paso es utilizar la IA para actuar como un abogado laboralista y fiscal corporativo en México, ayudándonos a interpretar la reforma al artículo 168 de la Ley del Seguro Social (incremento gradual de las cuotas de Cesantía en Edad Avanzada y Vejez del patrón).

1. Abra el chat de **Microsoft Copilot**.
2. Introduzca el siguiente prompt avanzado para estructurar la consulta normativa:

```
Actúa como un Abogado Laboral y Consultor Fiscal Corporativo en México, especialista en la Ley del Seguro Social (LSS) y la Ley Federal del Trabajo (LFT).

Necesito interpretar el impacto del incremento progresivo de las cuotas patronales de la rama de Cesantía en Edad Avanzada y Vejez (CEAV) según la reforma del artículo 168 de la LSS. 

Por favor, proporcióname un resumen ejecutivo sumamente estructurado que responda a lo siguiente:
1. ¿Cuál es el rango de porcentajes de aportación patronal vigentes para el año fiscal en curso, indexados según el salario del trabajador expresado en UMA?
2. ¿Cómo afecta directamente este incremento gradual al costo del Factor de Integración de la nómina en empresas con alta densidad de personal operativo?
3. Entrega una tabla de cumplimiento normativo de 3 columnas que me sirva para copiar a Word:
   | Concepto de Reforma | Impacto Directo en Nómina | Acción de Validación Requerida por el Analista |

Asegúrate de citar los fundamentos legales aplicables y usar un lenguaje técnico corporativo de nivel C-Suite. Devuelve solo la información solicitada sin saludos aclaratorios.
```

3. Lea el análisis generado y mantenga la ventana de Copilot abierta para los siguientes pasos.

---

### Fase B: Matriz de Costeo e Impacto Financiero en Excel

Con la base legal interpretada por la IA, el equipo de compensaciones debe calcular el impacto financiero real en la nómina de la empresa. Utilizaremos Copilot para estructurar un simulador de costo patronal.

1. En su libro de Excel, renombre la primera hoja como `1. Impacto_CEAV`.
2. Introduzca el siguiente prompt en el chat de Copilot para generar la matriz analítica de costos:

```
Actúa como un Gerente de Compensaciones y Estructura Analítica de Costos de Nómina. Necesito diseñar una matriz en Excel para modelar el impacto del incremento de las aportaciones patronales de Cesantía en Edad Avanzada y Vejez (CEAV) sobre cuatro perfiles de puestos operativos y administrativos representativos en México.

Por favor, devuélveme una tabla markdown limpia para copiar y pegar directamente en la celda A1 de Excel con las siguientes columnas exactas:
| ID Empleado | Puesto | Salario Diario ($ MXN) | SBC/SDI Integrado ($ MXN) | Cuota CEAV Patronal Anterior (Fórmula conceptual: SBC * 3.150%) | Nueva Cuota CEAV Patronal Reforma (Fórmula conceptual: SBC * Tarifa Progresiva según rango UMA de la reforma, asume un promedio de 4.5% para este ejercicio) | Incremento Mensual en Costo Patronal por Empleado ($ MXN, asume 30 días) | % de Incremento de Costo Directo |

Incluye exactamente 4 puestos realistas:
1. Operario de Línea (Salario Diario Integrado cercano al mínimo).
2. Supervisor de Turno (SBC medio de 3 UMA).
3. Coordinador de Mantenimiento (SBC de 5 UMA).
4. Gerente de Planta (SBC topado a 25 UMA).

Genera únicamente la tabla markdown, calculando valores realistas y representativos del mercado de compensaciones actual en México, sin agregar párrafos de introducción o conclusión.
```

3. Seleccione la tabla generada por Copilot, cópiela (`Ctrl+C`) y péguela (`Ctrl+V`) en la celda `A1` de la hoja `1. Impacto_CEAV` en Excel.

---

### Fase C: Interacción Práctica – Diagrama de Auditoría y Validación de Nómina (Copilot)

Para garantizar que el analista de nómina ejecute las conciliaciones correspondientes de manera visual antes del timbrado de los recibos, generaremos un diagrama del "Flujo de Validación y Blindaje SAT-IMSS-LFT".

1. En el chat de Copilot, introduzca el siguiente prompt para activar el motor de imágenes:

```
Crea un diagrama de flujo de estilo infografía técnica corporativa que represente el "Proceso de Validación y Conciliación Trilateral de Nóminas en México (SAT - IMSS - LFT)".

El gráfico debe mostrar un flujo limpio de izquierda a derecha con tres nodos o etapas clave:
1. **Etapa 1: Entrada Legal (LFT):** La silueta de una balanza de justicia y un libro de leyes que representa la configuración inicial de prestaciones y factor de integración.
2. **Etapa 2: Auditoría de Seguridad Social (IMSS):** El icono de un escudo de protección médica y un panel digital que muestra un indicador analizando el Salario Base de Cotización (SBC).
3. **Etapa 3: Timbrado Exitoso (SAT):** Una gran marca de verificación verde y una flecha limpia que apunta a una nube con el símbolo del SAT (Servicio de Administración Tributaria), simbolizando cero discrepancias y cumplimiento al 100%.

Usa un estilo visual corporativo, limpio, moderno, con colores azul oscuro, gris acero y verde de aprobación. Evita el desorden o textos caóticos dentro del diseño, optimizándolo para uso en una presentación corporativa de compensaciones.
```

2. Cuando la imagen esté lista, haga clic en ella, seleccione **Descargar** y guárdela en su computadora con el nombre `Flujo_Auditoria_Trilateral.png`.

---

### Fase D: Redacción del Memorándum Ejecutivo de Impacto Regulatorio (Word)

Consolidaremos la interpretación legal de la Fase A y los números de costeo de la Fase B en un documento formal de Word dirigido al Comité de Finanzas.

1. Abra su archivo de **Word** (`Memo_Cumplimiento_Legal.docx`) e introduzca el título inicial: `# Memorándum Ejecutivo: Impacto Financiero y Plan de Cumplimiento ante Reformas del Seguro Social (CEAV)`.
2. Use el siguiente prompt en Copilot para redactar el cuerpo del memorándum técnico corporativo:

```
Actúa como un Director de Compensaciones y Relaciones Laborales de una gran corporación. Necesito redactar un memorándum ejecutivo dirigido al Comité de Finanzas y Recursos Humanos para mi documento de Word. El objetivo es alertar y justificar el presupuesto adicional necesario para el incremento gradual de cuotas patronales de Cesantía y Vejez (CEAV) del ejercicio fiscal actual.

Por favor, genera el texto formal estructurado exactamente en estas 3 secciones:
1. **Análisis de Impacto Financiero en Costo Social**: Un párrafo técnico de alta densidad que explique la correlación directa entre el incremento progresivo de la cuota patronal de CEAV establecida en la reforma al artículo 168 de la LSS y la elevación del Costo Social Total de la Nómina (Costo Patronal Integrado).
2. **Plan de Acción para Mitigación de Riesgos de Auditoría (SAT-IMSS)**: Describe de manera imperativa las actividades críticas de control interno que el área de nóminas debe ejecutar, tales como la conciliación mensual de confronta IMSS contra sistema de nómina (SUA vs Software ERP) y la verificación de la correcta integración del SBC.
3. **Recomendación de Presupuestación Anual**: Redacta una directriz para la planeación financiera, recomendando incorporar el incremento del factor del costo patronal directo en los presupuestos del próximo año para evitar desviaciones en el flujo de efectivo operativo.
```

3. Copie el texto generado por Copilot y péguelo directamente en su documento de Word.
4. Inserte la imagen `Flujo_Auditoria_Trilateral.png` descargada en la Fase C justo debajo de la segunda sección para ilustrar visualmente las acciones requeridas por el área.
5. Pegue la tabla de cumplimiento obtenida en la Fase A en la sección correspondiente.

---

### Fase E: Reto de Aplicación Autónoma – Integración de Aguinaldo y Prima Vacacional en el SBC

**Instrucciones para el estudiante:** La empresa ha tomado la decisión estratégica de elevar la prestación contractual de **Aguinaldo de 15 a 30 días** y la **Prima Vacacional del 25% al 50%** para retener talento crítico administrativo. Esta decisión tiene un impacto inmediato en el Factor de Integración que se utiliza para calcular el Salario Base de Cotización (SBC), lo que a su vez incrementará todas las aportaciones de IMSS e Infonavit.

#### El Desafío:
Usa tu lógica de compensaciones y la ingeniería de prompts de forma autónoma con Copilot para resolver la contingencia técnica y presupuestal:
1. **Matriz de Factor de Integración (Excel):** Diseña un prompt para que Copilot te entregue una tabla estructurada para Excel (en una hoja nueva llamada `2. Reto_Factor_Integracion`) que calcule automáticamente el Factor de Integración Diario antes y después de la modificación de prestaciones. 
   * *Fórmula de ayuda:*
   $$\text{Factor de Integración} = 1 + \frac{\text{Días de Aguinaldo} + (\text{Días de Vacaciones} \times \text{Prima Vacacional})}{365}$$
   Usa los días de vacaciones legales correspondientes al año 1 de antigüedad según la LFT actual (12 días).
2. **Justificación de Incremento en Costo Anualizado (Word):** Pídele a la IA que redacte un argumento formal para Recursos Humanos que explique de cuánto es el incremento porcentual neto que sufrirá la nómina diaria integrada de un empleado que gana $\$1,000$ MXN de salario base nominal, tras el aumento de aguinaldo y prima vacacional.

#### Pistas de Ingeniería de Prompts para el Éxito:
* **Para la Tabla en Excel:** Pide explícitamente las columnas: `| Antigüedad (Año 1) | Días de Vacaciones LFT | Días Aguinaldo Anterior | Prima Vacacional Anterior | Factor Integración Anterior | Días Aguinaldo Nuevo | Prima Vacacional Nueva | Factor Integración Nuevo | % de Variación en Factor |`
* **Para el Prompt de Copilot:** Puedes usar un comando asertivo: `"Actúa como un Ingeniero de compensaciones y nóminas en México. Genera una tabla markdown que muestre la fórmula detallada paso a paso para el cálculo del Factor de Integración..."`

#### Cierre del Laboratorio:
1. Copie la tabla del reto e insértela en la hoja `2. Reto_Factor_Integracion` en la celda `A1` de su archivo de Excel.
2. Guarde ambos archivos (`Matriz_Impacto_Reformas.xlsx` y `Memo_Cumplimiento_Legal.docx`). Su ecosistema para la auditoría, simulación de costos y consulta de reformas en el departamento de compensaciones está completamente operativo.

---

## 6. Conceptos Clave para Recordar

* **Salario Base de Cotización (SBC):** Es la base de cálculo sobre la cual se determinan las cuotas obrero-patronales del IMSS (Art. 27 LSS). Se integra con prestaciones fijas y variables entregadas al trabajador por su labor.
* **Factor de Integración:** Factor numérico que se multiplica por el Salario Diario Nominal del trabajador para obtener el SBC. Cualquier alteración a las prestaciones básicas altera este factor de inmediato.
* **Aportaciones de CEAV Graduales:** Reforma que escalona progresivamente la cuota patronal según el rango de salario del trabajador medido en UMA, incrementando significativamente el costo operativo anual del patrón.

---

## 7. Resultado Esperado

Al finalizar los 60 minutos del laboratorio, el estudiante consolidará los siguientes entregables integrados:

1. **Archivo `Matriz_Impacto_Reformas.xlsx` (Excel):**
   * **Hoja 1 (`1. Impacto_CEAV`):** Tabla de simulación del impacto financiero de la reforma al Art. 168 de la LSS para 4 perfiles salariales.
   * **Hoja 2 (`2. Reto_Factor_Integracion`):** Cálculo dinámico comparativo del Factor de Integración tras elevar las prestaciones contractuales (Aguinaldo y Prima Vacacional).
2. **Archivo `Memo_Cumplimiento_Legal.docx` (Word):**
   * Memorándum ejecutivo de cumplimiento y justificación presupuestal, incorporando el flujo trilateral de validación visual e integrando la infografía explicativa `Flujo_Auditoria_Trilateral.png`.
