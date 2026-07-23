# Configuración de herramientas de IA para la distribución de correos masivos personalizados y gestión de tareas del área. Creación de plantillas inteligentes para cartas y soporte al empleado.

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 90 minutos (Alta Densidad Operativa y Automatización Documental) |
| **Complejidad** | Intermedia |
| **Audiencia** | Gerentes de Compensaciones, Analistas de Nómina, Especialistas en Clima Laboral y Profesionales de Recursos Humanos |
| **Tecnologías** | Microsoft Copilot (M365), Microsoft Word y Microsoft Outlook |
| **Enfoque** | Estructuración masiva de flujos de trabajo de nómina, diseño de plantillas inteligentes parametrizadas para soporte laboral, matrices de resolución de dudas frecuentes (FAQ) y automatización de campañas de comunicación masiva sin macros. |

---

## 2. Descripción Corta

Este laboratorio de alta resolución de 90 minutos entrena a los profesionales de Recursos Humanos en el uso estratégico de Microsoft Copilot para resolver cuellos de botella críticos en la atención al empleado y la distribución de tareas departamentales. Los estudiantes generarán de forma independiente estructuras de comunicados masivos listos para producción en **Microsoft Outlook**, diseñarán plantillas corporativas de soporte en **Microsoft Word**, desarrollarán guías de preguntas frecuentes (FAQ) de autoajuste y programarán la distribución de cargas de trabajo de la pre-nómina sin necesidad de configurar bases de datos o fórmulas adicionales.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Estructurar planes operativos de asignación de tareas** mediante IA, definiendo tiempos, responsables y entregables críticos para el equipo de nómina.
* **Diseñar plantillas inteligentes de atención al empleado** parametrizadas mediante corchetes, listas para rellenar directamente en Word.
* **Desarrollar guías de Preguntas Frecuentes (FAQ) de Soporte Técnico** estructuradas en matrices analíticas para agilizar la atención a dudas sobre nómina.
* **Crear comunicados masivos personalizados** optimizados para el motor de combinación de correspondencia de Outlook.
* **Diseñar diagramas visuales del flujo de atención** mediante instrucciones de diseño integradas en Copilot.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Microsoft Copilot**.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Plantillas_Y_Tareas_Compensaciones.docx`.
* Aplicación de **Microsoft Outlook** abierta (o en su defecto, una sección dedicada en el documento de Word anterior para almacenar los borradores de correo).

---

## 5. Procedimiento Paso a Paso

### Fase A: Planificación Operativa y Gestión de Tareas de la Pre-nómina

El objetivo de esta fase independiente es utilizar la IA como un gestor de proyectos para estructurar la distribución de actividades, fechas límite y responsables dentro del equipo de nómina, eliminando la necesidad de planificadores externos.

1. Abra el chat de **Microsoft Copilot**.
2. Introduzca el siguiente prompt para generar la matriz de tareas ejecutivas:

```
Actúa como un Líder de PMO y Gerente de Compensaciones. Necesito estructurar un plan de trabajo operativo semanal para coordinar las actividades críticas del cierre de la pre-nómina dentro de mi equipo.

Por favor, devuélveme únicamente una tabla en formato markdown limpia, lista para copiar y pegar directamente en Word, con los campos totalmente resueltos y las siguientes columnas exactas:
| ID Tarea | Actividad Crítica de Nómina | Responsable (Rol) | Día Límite de Ejecución | Entregable Esperado | Impacto Operativo (Alto/Medio/Bajo) | Estatus Inicial |

Incluye exactamente 5 tareas clave que cubran: la recolección de incidencias, el cruce de cuotas IMSS, la validación de alertas legales de horas extra, el timbrado de prueba ante el SAT y la liberación del archivo de dispersión bancaria. Genera solo la tabla sin textos introductorios.
```

3. Seleccione la tabla markdown generada en el chat, cópiela (`Ctrl+C`) y péguela (`Ctrl+V`) al inicio de su documento de Word bajo el título `# 1. Plan Operativo de Cierre de Nómina`.

---

### Fase B: Creación de Plantilla Inteligente de Soporte al Empleado (Carta de Aclaración)

Esta fase autónoma genera una plantilla formal en Word parametrizada con campos dinámicos listos para rellenar, la cual sirve para responder de manera estandarizada y clara a las dudas de los colaboradores sobre variaciones en sus depósitos.

1. En el chat de Copilot, introduzca el siguiente prompt para modelar la plantilla de atención:

```
Actúa como un Especialista Senior de Relaciones Laborales y Atención al Empleado. Necesito redactar una plantilla formal de carta de respuesta para aclaraciones de nómina (cuando un colaborador reporta una diferencia en su pago de horas extra o un descuento no reconocido).

Por favor, genera el texto completo de la carta en prosa ejecutiva utilizando corchetes claros como [Insertar_Nombre] para delimitar los campos variables que el usuario de Recursos Humanos deba llenar manualmente después. La estructura de la carta debe incluir:
1. Membrete e introducción formal institucional.
2. Cuerpo explicativo que desglose de manera pacífica y técnica si la incidencia procedió o se ajustará en el siguiente periodo.
3. Cierre formal con firma del departamento de beneficios.

Devuelve únicamente el cuerpo de la plantilla formal listo para usar en Word, sin saludos iniciales ni comentarios del asistente.
```

2. Copie la plantilla de texto generada por la IA y péguela en su archivo de Word bajo la sección `# 2. Plantilla Estandarizada de Aclaraciones`.

---

### Fase C: Interacción Práctica – Diagramación Visual de Canales de Atención

Esta fase independiente se enfoca en el diseño de un soporte visual corporativo que ilustre a los colaboradores la ruta correcta que sigue un ticket de soporte de nómina desde que se recibe hasta que se soluciona.

1. En el chat de Copilot, introduzca el siguiente prompt para activar la generación visual:

```
Crea una ilustración conceptual con estilo de diseño corporativo moderno y limpio que represente los "Canales Digitales de Atención y Resolución al Empleado".

El diseño debe mostrar un camino lineal con tres estaciones clave:
1. **Estación 1:** El icono de un teléfono inteligente o computadora mostrando un sobre de correo electrónico abierto, que simboliza la recepción de la duda del empleado.
2. **Estación 2:** El icono de un engranaje y un documento de texto protegido por un sello de validación, que representa la revisión interna del analista de nómina.
3. **Estación 3:** El icono de una mano entregando un recibo impreso con un símbolo de verificación verde, que representa la resolución exitosa de la aclaración.

Utiliza una paleta de colores profesionales basada en azul marino, gris corporativo y detalles en verde menta para denotar efectividad. Mantén la composición minimalista y completamente libre de textos legibles o etiquetas complejas para evitar distorsiones.
```

2. Una vez que la imagen se haya procesado, haga clic en ella, elija **Descargar** y guárdela con el nombre `Flujo_Atencion_Soporte.png`.

---

### Fase D: Matriz de Preguntas Frecuentes (FAQ) de Soporte de Nómina

El objetivo de esta fase de alta densidad es equipar al equipo de soporte de primera línea con una guía estructurada en formato de tabla para responder de manera inmediata a las dudas de nómina más recurrentes del personal durante el fin de año o periodos de reparto de utilidades.

1. En el chat de Copilot, introduzca el siguiente prompt para estructurar la matriz de FAQ:

```
Actúa como un Especialista en Comunicación Interna y Atención de Nómina en México. Necesito estructurar una guía rápida en formato de tabla para el personal de soporte que atiende las dudas más comunes de los colaboradores sobre sus recibos de pago.

Por favor, devuélveme únicamente una tabla markdown limpia para copiar y pegar directamente en Word con los siguientes campos exactos:
| Categoría de la Duda | Pregunta Típica del Empleado | Explicación Técnica (Fundamento Breve LFT/LISR) | Guía de Respuesta Verbal (Tono Amable y Claro) | Acción Requerida en Sistema |

Incluye exactamente 4 escenarios críticos:
1. Retención de ISR en el aguinaldo.
2. Descuento por pensión alimenticia.
3. El cálculo del pago de un día festivo laborado.
4. Saldo negativo por faltas injustificadas.

Asegúrate de que las respuestas verbales estén listas para ser usadas por el analista y que la tabla no incluya introducciones ni explicaciones adicionales fuera de las filas markdown.
```

2. Copie la tabla markdown generada por la IA y péguela en su archivo de Word bajo la sección `# 3. Guía de Preguntas Frecuentes (FAQ) para Soporte`.

---

### Fase E: Configuración de Comunicado Masivo Personalizado para Outlook

Esta fase autónoma genera la estructura del cuerpo de un correo electrónico masivo diseñado específicamente para ser utilizado con la función de Combinar Correspondencia de Microsoft Outlook, notificando de manera personalizada a los líderes de departamento el inicio del periodo de captura.

1. En el chat de Copilot, introduzca el siguiente prompt para redactar la campaña de comunicación masiva:

```
Actúa como un Gerente de Comunicación Interna y Compensaciones. Necesito redactar el cuerpo de un correo electrónico masivo parametrizado que se enviará a todos los directores y jefes de área de la empresa a través de Outlook para recordarles la fecha límite de entrega de incidencias de su personal.

Por favor, genera el texto estructurado con las siguientes pautas:
- **Asunto del Correo:** Claro, institucional y con carácter de urgente.
- **Cuerpo del Mensaje:** Utiliza el campo parametrizado [Nombre_Líder] en el saludo. Debe redactarse en un tono profesional e imperativo, recordándoles que el portal de captura cerrará de forma automatizada y que cualquier retraso afectará la dispersión de sus equipos de trabajo.
- **Bloque Técnico:** Incluye viñetas limpias donde se listen los 3 documentos obligatorios que deben adjuntar (Reporte de asistencias, layout de horas extra validado y justificantes médicos de incapacidades).

Devuelve únicamente el texto final del correo electrónico listo para copiar y usar como plantilla de envío masivo en Outlook.
```

2. Copie el texto generado por la IA y péguelo en su documento de Word bajo la sección `# 4. Estructura de Campaña de Comunicación Masiva`. Puedes usar este borrador para pegarlo directamente en un nuevo mensaje de Outlook al ejecutar una combinación de correspondencia.

---

### Fase F: Reto de Aplicación Autónoma – Creación de la Plantilla de Notificación de Modificación Salarial

**Instrucciones para el estudiante:** La Dirección General ha aprobado un ajuste salarial extraordinario por desempeño para un grupo selecto de colaboradores de la planta operativa. Se requiere generar de manera inmediata una plantilla formal de notificación individual que sea institucional y transparente respecto al incremento de su Salario Diario Integrado (SDI).

#### El Desafío:
Utiliza la inteligencia artificial de forma totalmente autónoma para resolver la documentación del aviso corporativo:

1. **Redacción de la Notificación de Incremento (Word):** Diseña un prompt estratégico en Copilot para obtener el cuerpo de una carta institucional de modificación de salario lista para producción.
   * *Campos dinámicos obligatorios que debe incluir la IA usando corchetes:* `[Nombre_Colaborador]`, `[Puesto_Actual]`, `[Departamento]`, `[Sueldo_Anterior_MXN]`, `[Sueldo_Nuevo_MXN]` y `[Fecha_Aplicacion]`.
2. **Justificación del Liderazgo en Compensaciones (Word):** Pídele a la IA que redacte un párrafo ejecutivo corto de cierre que explique la importancia de comunicar las mejoras salariales de manera oportuna para fomentar la retención del talento clave y el compromiso organizacional.

#### Pistas de Ingeniería de Prompts para el Éxito:
* **Foco en el Rol:** Asigna con precisión el perfil al asistente: "Actúa como un Director de Desarrollo Organizacional y Compensaciones. Redacta una carta de felicitación y notificación de incremento salarial estructurada con corchetes para los datos variables..."
* **Salida Limpia:** Asegúrate de estipular en tu comando que el resultado no contenga preámbulos informales ni introducciones conversacionales por parte de la IA para facilitar la transferencia directa del texto.

#### Cierre del Laboratorio:
1. Copie la plantilla de notificación generada en el reto autónomo.
2. Péguela en la sección final de su archivo de Word bajo el título `# 5. Reto Autónomo: Plantilla de Modificación Salarial`.
3. Inserte la imagen `Flujo_Atencion_Soporte.png` (descargada en la Fase C) justo debajo del título de la sección de FAQ para completar la estética técnica del documento.
4. Guarde el archivo `Plantillas_Y_Tareas_Compensaciones.docx`. Su manual operativo de gestión de comunicaciones masivas y tareas automatizadas ha quedado concluido con éxito.

---

## 6. Conceptos Clave para Recordar

* **Campos Parametrizados:** Marcadores de posición o variables envueltas en corchetes que permiten a los sistemas de automatización (como combinar correspondencia de Office) inyectar datos masivos de manera personalizada en un documento estándar.
* **Combinar Correspondencia:** Herramienta nativa de Microsoft Office que vincula un documento maestro de Word o un correo de Outlook con una lista de contactos para emitir comunicaciones masivas personalizadas de forma simultánea.
* **Flujo Operativo de Nómina:** Secuencia lógica y cronológica de tareas administrativas e inspecciones de control que el equipo de compensaciones debe completar rigurosamente para garantizar la dispersión correcta del capital humano.

---

## 7. Resultado Esperado

Al finalizar los 90 minutos del laboratorio, el estudiante consolidará el siguiente entregable unificado en su equipo:

1. **Archivo `Plantillas_Y_Tareas_Compensaciones.docx` (Word):**
   * **Sección 1:** Matriz markdown completa con el plan semanal y cronograma de actividades críticas del cierre de nómina de la empresa.
   * **Sección 2:** Cuerpo técnico e institucional parametrizado para la atención y resolución de aclaraciones de pago del personal.
   * **Sección 3:** Matriz analítica de preguntas frecuentes (FAQ) orientada a blindar las dudas tributarias y operativas de los colaboradores.
   * **Sección 4:** Borrador maestro de comunicación masiva urgente para Outlook optimizado para interactuar con los líderes de área.
   * **Sección 5:** Estructura formal resuelta de la notificación de incrementos salariales ligada al reto autónomo, complementada visualmente por la infografía de atención al usuario `Flujo_Atencion_Soporte.png`.
