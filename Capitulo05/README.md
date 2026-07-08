# Auditoría y Encriptación de Reportes de Nómina con Copilot

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 90 minutos (Alta Densidad en Ciberseguridad, Gobierno de Datos y Cumplimiento Legal) |
| **Complejidad** | Intermedia |
| **Audiencia** | Gerentes de Compensaciones, Oficiales de Privacidad de Datos, Analistas de Nómina, Auditores de TI y Profesionales de Recursos Humanos |
| **Tecnologías** | Microsoft Copilot (M365), Microsoft Excel y Microsoft Word |
| **Enfoque** | Diseño e implementación de protocolos de encriptación lógica, técnicas de enmascaramiento y anonimización de salarios, matrices de control de accesos basados en roles (RBAC) y cumplimiento estricto de la normativa de protección de datos personales. |

---

## 2. Descripción Corta

Este laboratorio avanzado de 90 minutos entrena a los profesionales de compensaciones en la aplicación de técnicas de seguridad y gobierno de datos sobre reportes de nómina utilizando Microsoft Copilot. A través de un enfoque práctico de fases independientes, los participantes diseñarán matrices de control de acceso basados en roles en **Microsoft Excel**, implementarán técnicas de anonimización y enmascaramiento de datos salariales sensibles para compartir reportes de forma segura, y redactarán políticas corporativas de cifrado y respuesta ante incidentes en **Microsoft Word** para garantizar el cumplimiento normativo.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Estructurar matrices de control de acceso basado en roles (RBAC)** para segregar funciones dentro del sistema y los archivos de nómina.
* **Aplicar técnicas de enmascaramiento y anonimización de datos personales** (CURP, RFC, Salarios) en layouts de Excel asistidos por instrucciones de IA.
* **Diseñar políticas de cifrado y protección de archivos** estructuradas bajo estándares internacionales de seguridad de la información.
* **Redactar planes de respuesta ante incidentes de fuga de datos** de nómina listos para su incorporación en manuales de cumplimiento corporativo.
* **Generar diagramas visuales de arquitecturas de seguridad de datos** a través de la interfaz interactiva de Copilot.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Microsoft Copilot**.
* Aplicación de **Microsoft Excel** abierta con un libro en blanco guardado como `Seguridad_Y_Auditoria_Nomina.xlsx`.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Politicas_Seguridad_Compensaciones.docx`.

---

## 5. Procedimiento Paso a Paso

### Fase A: Matriz de Control de Accesos por Roles (RBAC) para el Sistema de Nómina en Excel

El objetivo de esta fase independiente es diseñar una matriz de seguridad que defina con precisión qué perfiles del departamento tienen permisos de lectura, escritura o modificación sobre los datos salariales, mitigando el riesgo de accesos no autorizados.

1. Abra el chat de **Microsoft Copilot**.
2. Introduzca el siguiente prompt para generar la matriz de privilegios de acceso:

```
Actúa como un Auditor de Seguridad de la Información y Consultor de Gobierno de Datos. Necesito estructurar una matriz de control de acceso basado en roles (RBAC) para segregar estrictamente las funciones dentro del módulo del sistema de nómina y los archivos compartidos de compensaciones.

Por favor, devuélveme únicamente una tabla en formato markdown limpia, lista para copiar y pegar en la celda A1 de Excel (en una hoja llamada "1. Control_Accesos") con los campos totalmente resueltos y las siguientes columnas exactas:
| ID Rol | Nombre del Puesto / Rol | Módulo / Tipo de Reporte | Permiso Lectura (Sí/No) | Permiso Escritura/Edición (Sí/No) | Permiso de Exportación / Descarga (Sí/No) | Nivel de Criticidad del Acceso (Crítico / Alto / Medio) | Justificación del Control de Seguridad |

Incluye exactamente 5 roles operativos reales del área: Auxiliar de Nómina, Gerente de Compensaciones, Auditor Externo, Administrador del Sistema de TI y Director de Finanzas. Genera solo la tabla sin textos introductorios ni explicaciones anexas.
```

3. Seleccione la tabla markdown generada en el chat, cópiela (`Ctrl+C`) y péguela (`Ctrl+V`) en la celda `A1` de la hoja `1. Control_Accesos` de su archivo de Excel.

---

### Fase B: Simulación de Reporte Anonimizado y Enmascaramiento de Datos en Excel

Esta fase independiente resuelve la necesidad de compartir reportes estadísticos de nómina con analistas externos sin revelar datos personales sensibles, utilizando técnicas de enmascaramiento de cadenas de texto y tokens numéricos simulados.

1. En el chat de Copilot, introduzca el siguiente prompt para modelar el layout seguro:

```
Actúa como un Oficial de Privacidad de Datos y Analista de Compensaciones. Necesito generar un layout de nómina modificado para un análisis de equidad salarial que proteja la identidad de los colaboradores de acuerdo con las leyes de protección de datos personales.

Por favor, proporcióname únicamente una tabla en formato markdown limpia, lista para copiar y pegar directamente en la celda A1 de Excel (en una hoja llamada "2. Reporte_Anonimizado"), que simule datos con técnicas de enmascaramiento aplicadas y cuente con los siguientes campos exactos:
| ID Empleado Tokenizado | RFC Enmascarado | Género | Departamento | Antigüedad (Años) | Salario Mensual Bruto ($ MXN) | Estatus del Dato (Muestra: "ENMASCARADO" o "ANONIMIZADO") |

Incluye exactamente 4 registros realistas donde:
- El ID esté tokenizado (Ejemplo: EMP-OXX-982).
- El RFC muestre solo los primeros 4 dígitos y el resto oculto con asteriscos (Ejemplo: VAME******).
- Los salarios y departamentos sean legibles pero desvinculados de cualquier nombre propio.

Devuelve exclusivamente la tabla con los datos resueltos para transferir directamente a Excel.
```

2. Copie la tabla generada por la IA y péguela en la pestaña `2. Reporte_Anonimizado` de su archivo de Excel, ubicándose en la celda `A1`.

---

### Fase C: Interacción Práctica – Arquitectura Visual del Flujo de Datos Cifrados

Para documentar y capacitar al equipo en el flujo seguro que siguen los archivos de nómina desde que se extraen del sistema hasta que se envían al banco dispersor, utilizaremos la IA para diseñar un diagrama conceptual de la infraestructura de seguridad.

1. En el chat de Copilot, introduzca el siguiente prompt para activar la generación visual:

```
Crea una ilustración conceptual con estilo de diseño corporativo técnico y limpio que represente el "Flujo de Cifrado y Protección de Datos de Nómina".

El diseño debe mostrar un recorrido lineal de tres pasos seguros de izquierda a derecha:
1. **Paso 1: Extracción Segura:** El icono de una base de datos o servidor de red conectado a un candado cerrado de color plata.
2. **Paso 2: Encriptación en Tránsito:** El icono de un archivo de hoja de cálculo flotando dentro de un escudo de energía digital azul brillante con líneas de código binario de fondo.
3. **Paso 3: Destino Protegido:** El icono de una caja fuerte o bóveda bancaria digital con una marca de verificación verde, simbolizando la recepción segura del archivo de dispersión.

Utiliza una paleta de colores de alta seguridad como azul oscuro, gris pizarra y acentos en verde brillante. Mantén la composición minimalista, ordenada y completamente libre de textos escritos, letras o etiquetas deformadas.
```

2. Una vez procesada la imagen por la IA, descárguela en su equipo local con el nombre `Arquitectura_Seguridad_Nomina.png`.

---

### Fase D: Redacción de la Política Departamental de Cifrado y Manejo de Archivos en Word

Esta fase independiente genera la documentación normativa interna obligatoria que regula el uso de contraseñas, almacenamiento local y canales de transmisión permitidos para cualquier archivo que contenga información de sueldos y salarios.

1. Abra su archivo de **Word** (`Politicas_Seguridad_Compensaciones.docx`) e introduzca el título: `# Manual de Gobierno de Datos: Política de Cifrado y Privacidad en Compensaciones`.
2. Utilice el siguiente prompt en el chat de Copilot para redactar el cuerpo de la política:

```
Actúa como un Director de Cumplimiento Normativo (Compliance) y Seguridad de la Información. Necesito redactar la sección formal de la política de confidencialidad y directrices de cifrado de reportes de nómina para el manual de control interno.

Por favor, genera un texto estructurado detallando los siguientes 3 apartados técnicos:
1. **Clasificación de la Información de Sueldos**: Define los criterios institucionales para catalogar a la nómina como "Información Confidencial y Altamente Sensible", explicando los riesgos legales y reputacionales de su exposición.
2. **Estándar Obligatorio de Cifrado y Almacenamiento**: Redacta las reglas operativas estrictas para los analistas (uso obligatorio de contraseñas complejas en archivos Excel, prohibición de almacenamiento en discos locales o nubes personales, y uso exclusivo de repositorios protegidos en SharePoint).
3. **Mecanismos de Transmisión Segura**: Detalla el protocolo aprobado para el intercambio de información con terceros (bancos, auditores, autoridades), prohibiendo el envío de layouts abiertos por canales no oficiales o aplicaciones de mensajería instantánea.

Devuelve únicamente el texto normativo formal, redactado con un estilo legal, imperativo y corporativo, listo para incorporarse a Word.
```

3. Copie el texto generado por la IA y péguelo en su documento de Word debajo del título principal.

---

### Fase E: Plan de Respuesta ante Incidentes de Seguridad (Fuga de Información de Nómina)

Esta fase independiente establece el protocolo de acción inmediata (contención, erradicación y notificación) que el equipo de compensaciones debe ejecutar de forma conjunta con el área de TI en caso de sospechar o confirmar una brecha de seguridad en los datos de pago.

1. En el chat de Copilot, introduzca el siguiente prompt para estructurar la matriz de respuesta ante incidentes:

```
Actúa como un Especialista en Gestión de Crisis y Ciberseguridad Corporativa. Necesito diseñar un plan de acción rápida para el equipo de Recursos Humanos y Compensaciones en caso de detectar una vulnerabilidad o fuga de datos en los layouts de nómina.

Por favor, devuélveme únicamente una tabla en formato markdown limpia para copiar directamente en Word, organizada cronológicamente con las siguientes columnas exactas:
| Fase del Incidente | Acciones Inmediatas de Contención | Responsable Principal | Ventana de Tiempo (Máxima) | Entregable o Evidencia Necesaria |

Incluye exactamente 4 fases críticas: Identificación/Alerta, Aislamiento del Archivo/Acceso, Evaluación del Alcance del Daño y Notificación Legal/Cierre del Incidente. No agregues preámbulos, saludos ni textos explicativos secundarios fuera de la estructura markdown.
```

2. Copie la tabla generada por la IA y péguela en su documento de Word bajo la sección `# 2. Protocolo de Reacción ante Brechas de Seguridad`.

---

### Fase F: Reto de Aplicación Autónoma – Auditoría de Registro de Cambios en Salarios (Audit Trail)

**Instrucciones para el estudiante:** La dirección de auditoría interna ha solicitado evidenciar los mecanismos de control sobre las modificaciones manuales de sueldos en el sistema. Se requiere estructurar un formato técnico que registre de manera inalterable la bitácora de auditoría (Audit Trail) para rastrear quién, cuándo y por qué alteró un registro salarial.

#### El Desafío:
Utiliza la inteligencia artificial de forma totalmente autónoma para resolver el diseño técnico de la bitácora de auditoría:

1. **Diseño de Tabla de Bitácora (Excel):** Diseña un prompt estratégico en Copilot para obtener una tabla markdown lista para pegar en una hoja nueva de Excel llamada `3. Bitácora_Auditoría`.
   * *Columnas obligatorias:* `| Folio Evento | Fecha y Hora Exacta | ID Usuario (Analista) | ID Empleado Afectado | Tipo de Modificación (Sueldo Base / Bono / Deducción) | Monto Anterior ($ MXN) | Monto Nuevo ($ MXN) | Código de Autorización de Dirección |`
   * Genera 3 registros simulados realistas que reflejen un ajuste autorizado y una fila sospechosa sin código de validación correcto.
2. **Justificación Técnica del Registro (Word):** Pídele a la IA que redacte un párrafo técnico ejecutivo que explique cómo mantener un rastro de auditoría inalterable previene fraudes internos, colusiones y errores operativos en el cierre fiscal del ejercicio.

#### Pistas de Ingeniería de Prompts para el Éxito:
* **Foco en el Rol:** Inicia tu comando delimitando la experiencia: "Actúa como un Auditor Forense Digital y Especialista en Control Interno de Nóminas. Genera una tabla markdown limpia con los campos de bitácora..."
* **Restricción de Ruido:** Estipula claramente que el resultado final debe omitir introducciones comerciales o saludos casuales de la IA para agilizar la integración en los archivos de trabajo.

#### Cierre del Laboratorio:
1. Copie la tabla de la bitácora del reto e insértela en la hoja `3. Bitácora_Auditoría` en la celda `A1` de su archivo de Excel.
2. Copie la justificación del rastro de auditoría y péguela en la sección final de su documento de Word.
3. Inserte la imagen `Arquitectura_Seguridad_Nomina.png` (descargada en la Fase C) directamente entre la sección de políticas de cifrado y el plan de respuesta ante incidentes para amarrar visualmente los conceptos técnicos del manual.
4. Guarde ambos archivos (`Seguridad_Y_Auditoria_Nomina.xlsx` y `Politicas_Seguridad_Compensaciones.docx`). Su framework avanzado de ciberseguridad, gobierno de datos y cumplimiento operativo para el área de compensaciones ha concluido con éxito.

---

## 6. Conceptos Clave para Recordar

* **RBAC (Role-Based Access Control):** Método de regulación de accesos que restringe los privilegios del sistema únicamente a los usuarios autorizados de acuerdo con su rol específico en la organización.
* **Anonimización / Enmascaramiento:** Proceso técnico mediante el cual un dato sensible es modificado o sustituido de forma que sea imposible asociarlo de manera directa con su titular, protegiendo su identidad legal.
* **Audit Trail (Pista de Auditoría):** Registro cronológico y secuencial de alteraciones informáticas que proporciona evidencia documental detallada de la secuencia de actividades que han afectado una transacción o registro de datos.

---

## 7. Resultado Esperado

Al finalizar los 90 minutos del laboratorio, el estudiante consolidará los siguientes entregables unificados en su espacio de trabajo:

1. **Archivo `Seguridad_Y_Auditoria_Nomina.xlsx` (Excel):**
   * **Hoja 1 (`1. Control_Accesos`):** Matriz avanzada de permisos RBAC segmentando accesos de lectura, edición y exportación en el área.
   * **Hoja 2 (`2. Reporte_Anonimizado`):** Tabla de nómina modificada con datos enmascarados y tokenizados lista para análisis externos seguros.
   * **Hoja 3 (`3. Bitácora_Auditoría`):** Reporte técnico de rastreabilidad e historial de modificaciones de salarios ligada al reto autónomo.
2. **Archivo `Politicas_Seguridad_Compensaciones.docx` (Word):**
   * Manual normativo que incorpora la política departamental de cifrado de archivos, las directrices de almacenamiento seguro, el plan integral de respuesta cronológica ante fugas de información, la justificación forense de la bitácora de auditoría y el diagrama de infraestructura visual `Arquitectura_Seguridad_Nomina.png`.
