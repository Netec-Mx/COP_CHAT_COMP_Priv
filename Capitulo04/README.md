# Configuración de herramientas de IA para la distribución de correos masivos personalizados y gestión de tareas del área. Creación de plantillas inteligentes para cartas y soporte al empleado.

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 90 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Crear |
| **Módulo** | Capítulo 4 — Comunicación Corporativa y Gestión Automatizada con IA |
| **Práctica número** | 4 |

---

## 2. Descripción General

Esta práctica integra las capacidades de Microsoft Copilot en Outlook, Word, Teams y Power Automate para transformar dos procesos críticos del área de compensaciones: la comunicación masiva personalizada y la creación de documentos corporativos estandarizados. El participante construirá un flujo automatizado que genera y distribuye correos de nómina personalizados a partir de un archivo Excel de empleados ficticios, gestionará tareas del área mediante Copilot en Teams y edificará una biblioteca de plantillas inteligentes en SharePoint. Al finalizar, contará con un ecosistema funcional que reduce de horas a minutos la operación de comunicación interna del departamento de compensaciones, manteniendo consistencia legal y personalización por destinatario.

---

## 3. Objetivos de Aprendizaje

Al completar esta práctica, el participante será capaz de:

- [ ] **Configurar** un flujo en Power Automate que detecte cambios en un archivo Excel de nómina y dispare el envío automatizado de correos personalizados en Outlook, usando variables dinámicas (nombre, puesto, salario, departamento).
- [ ] **Utilizar** Copilot en Outlook para redactar comunicados corporativos segmentados por nivel jerárquico con tono y contenido adaptados a cada grupo de destinatarios.
- [ ] **Crear** al menos tres plantillas inteligentes en Word con Copilot (carta de oferta, constancia de empleo y salario, aviso de ajuste salarial) y publicarlas en una biblioteca de SharePoint accesible para el equipo.
- [ ] **Implementar** una lista de tareas del área de compensaciones en Microsoft Teams usando Copilot para asignar responsables, establecer fechas límite y generar recordatorios automáticos.
- [ ] **Diseñar** un flujo de soporte básico al empleado que integre plantillas de Word y Outlook para responder las consultas más frecuentes de forma semi-automatizada.

---

## 4. Prerrequisitos

### Conocimientos Previos

| Área | Nivel requerido |
|---|---|
| Microsoft Outlook (redacción y reglas básicas) | Básico |
| Microsoft Word (estilos y formato) | Básico |
| Microsoft Teams (canales y tareas) | Básico |
| Power Automate (creación de flujos simples con disparadores) | Básico |
| Conceptos de compensaciones y nómina (México) | Intermedio |

### Accesos y Permisos Requeridos

| Recurso | Estado requerido |
|---|---|
| Licencia activa de Microsoft 365 Copilot | ✅ Habilitada y verificada |
| Acceso a Microsoft Outlook (M365) | ✅ Cuenta corporativa activa |
| Acceso a Microsoft Word (M365) | ✅ Versión 2308 o superior |
| Acceso a Microsoft Teams | ✅ Con Copilot habilitado |
| Acceso a Power Automate (`make.powerautomate.com`) | ✅ Con conectores premium disponibles |
| Acceso a SharePoint Online (sitio del curso) | ✅ Permisos de colaborador o superior |
| Archivos de práctica del instructor | ✅ Descargados en equipo local |

> ⚠️ **Aviso de cumplimiento:** Todos los datos de empleados utilizados en esta práctica son **estrictamente ficticios**. Está prohibido usar datos reales de empleados en cumplimiento con la Ley Federal de Protección de Datos Personales en Posesión de los Particulares (LFPDPPP).

---

## 5. Entorno de Laboratorio

### Requisitos de Hardware

| Componente | Mínimo | Recomendado |
|---|---|---|
| RAM | 8 GB | 16 GB |
| Procesador | Intel Core i5 8ª gen / AMD Ryzen 5 | Intel Core i7 / AMD Ryzen 7 |
| Almacenamiento libre | 10 GB | 20 GB |
| Conexión a internet | 10 Mbps | 25 Mbps |
| Resolución de pantalla | 1366×768 | 1920×1080 |

### Software Requerido

| Aplicación | Versión mínima | URL de acceso |
|---|---|---|
| Microsoft Outlook | M365 (versión actual) | Escritorio o `outlook.office.com` |
| Microsoft Word | M365 versión 2308+ | Escritorio o `office.com` |
| Microsoft Teams | M365 (versión actual) | Escritorio o `teams.microsoft.com` |
| Power Automate | Versión actual | `make.powerautomate.com` |
| SharePoint Online | M365 (versión actual) | URL del sitio del curso |
| Microsoft Excel | M365 versión 2308+ | Escritorio o `office.com` |
| Navegador web | Edge 120+ o Chrome 120+ | — |

### Archivos de Práctica

El instructor habrá cargado los siguientes archivos en la carpeta **`/Practica-04/`** del sitio de SharePoint del curso:

```
/Practica-04/
├── empleados_ficticios.xlsx        ← Lista de 15 empleados con datos de nómina
├── plantilla_base_carta_oferta.docx
├── plantilla_base_constancia.docx
├── plantilla_base_ajuste_salarial.docx
└── comunicado_vales_despensa_base.txt
```

### Configuración Inicial — Descarga de Archivos

Antes de comenzar, descarga los archivos de práctica desde SharePoint:

1. Abre tu navegador y navega al sitio de SharePoint del curso.
2. Dirígete a **Documentos > Practica-04**.
3. Selecciona todos los archivos (Ctrl+A) y haz clic en **Descargar**.
4. Extrae el contenido en la siguiente ruta local:

```
C:\LabM365\Practica-04\
```

5. Verifica que los cinco archivos estén presentes antes de continuar.

---

## 6. Procedimiento Paso a Paso

La práctica se divide en dos bloques temáticos:

| Bloque | Tema | Tiempo estimado |
|---|---|---|
| **Bloque 4.1** | Comunicación Corporativa Automatizada | 45 minutos |
| **Bloque 4.2** | Plantillas Inteligentes y Biblioteca en SharePoint | 45 minutos |

---

### BLOQUE 4.1 — Comunicación Corporativa Automatizada

---

### Paso 1: Revisión del Archivo de Empleados Ficticios en Excel

**Objetivo:** Familiarizarse con la estructura de datos que alimentará los correos personalizados y verificar que el archivo contiene todos los campos necesarios para la automatización.

#### Instrucciones

1. Abre el archivo `empleados_ficticios.xlsx` desde `C:\LabM365\Practica-04\`.

2. Verifica que el archivo contiene las siguientes columnas en la **Hoja1** (renombrada como `Empleados`):

   | Columna | Descripción | Ejemplo |
   |---|---|---|
   | `A — ID_Empleado` | Clave interna | EMP-001 |
   | `B — Nombre_Completo` | Nombre ficticio | Ana García López |
   | `C — Puesto` | Título del puesto | Analista de Nómina |
   | `D — Departamento` | Área organizacional | Compensaciones |
   | `E — Salario_Mensual` | Salario bruto MXN | $18,500.00 |
   | `F — RFC` | RFC ficticio | GALA850312AB3 |
   | `G — Correo_Electronico` | Correo de prueba | ana.garcia@empresa-prueba.com |
   | `H — Nivel_Jerarquico` | Operativo / Supervisión / Gerencia | Operativo |
   | `I — Fecha_Ingreso` | Fecha de ingreso | 15/03/2019 |
   | `J — Estatus_Envio` | Campo de control | (vacío — se llenará automáticamente) |

3. Confirma que hay exactamente **15 registros** de empleados ficticios.

4. En la columna `G — Correo_Electronico`, reemplaza los correos de ejemplo con **correos reales de los participantes del curso** (máximo 10–15 cuentas) para que los envíos de prueba lleguen a buzones verificables. Esto evita activar filtros anti-spam del tenant.

   > ⚠️ **Límite de envío:** El tenant de Microsoft 365 permite máximo 500 destinatarios por mensaje y 10,000 por día. Para esta práctica, usa únicamente las cuentas de los participantes presentes en el aula.

5. Guarda el archivo con **Ctrl+S** y ciérralo. Lo volverás a necesitar en el Paso 3.

#### Resultado Esperado

El archivo Excel está abierto, revisado y guardado con correos de prueba válidos en la columna G. Las 15 filas de empleados ficticios están completas y sin valores nulos en las columnas B, C, D, E, G y H.

#### Verificación

- Aplica un filtro en la columna G y confirma que no hay celdas vacías.
- Revisa que la columna J (`Estatus_Envio`) esté completamente vacía — Power Automate la actualizará automáticamente en el Paso 3.

---

### Paso 2: Redacción de Correo Personalizado con Copilot en Outlook

**Objetivo:** Usar Copilot en Outlook para redactar una plantilla de correo de aviso de nómina que incluya marcadores de posición para variables dinámicas, con tono corporativo apropiado para cada nivel jerárquico.

#### Instrucciones

1. Abre **Microsoft Outlook** en tu equipo.

2. Haz clic en **Nuevo correo** (o presiona **Ctrl+N**).

3. En el panel lateral derecho, localiza el ícono de **Copilot** (estrella de cuatro puntas) y haz clic en él para abrir el panel de Copilot.

4. En el campo de prompt de Copilot, escribe el siguiente prompt para el nivel **Operativo**:

   ```
   Redacta un correo corporativo formal en español mexicano para notificar 
   a un empleado del nivel operativo sobre el depósito de su nómina quincenal. 
   El correo debe incluir los siguientes marcadores de posición entre corchetes:
   [NOMBRE_EMPLEADO], [PERIODO_NOMINA], [MONTO_NETO], [FECHA_DEPOSITO], 
   [BANCO_DESTINO]. 
   El tono debe ser profesional pero cercano. Incluye una sección de 
   "¿Tienes dudas?" con instrucciones para contactar al área de compensaciones. 
   Máximo 200 palabras. Firma como "Equipo de Compensaciones y Nómina — 
   Recursos Humanos".
   ```

5. Haz clic en **Generar** y revisa el borrador producido por Copilot.

6. Si el resultado es satisfactorio, haz clic en **Conservar**. Si deseas ajustarlo, usa el botón **Regenerar** o escribe instrucciones adicionales como:

   ```
   Hazlo más conciso. Elimina saludos informales. 
   Añade el número de folio de nómina como marcador: [FOLIO_NOMINA].
   ```

7. Una vez que tengas el correo base aprobado, **copia el cuerpo del mensaje** y pégalo en un nuevo archivo de texto llamado `plantilla_correo_operativo.txt` en `C:\LabM365\Practica-04\`.

8. Repite los pasos 4–7 para el nivel **Gerencia**, modificando el prompt así:

   ```
   Redacta un correo corporativo en español mexicano para notificar a un 
   gerente sobre el depósito de su nómina quincenal. El tono debe ser 
   ejecutivo y conciso. Incluye los marcadores: [NOMBRE_EMPLEADO], 
   [PERIODO_NOMINA], [MONTO_NETO], [FECHA_DEPOSITO], [BANCO_DESTINO], 
   [FOLIO_NOMINA]. Incluye referencia al portal de autoservicio de RH 
   para consultar el recibo digital. Máximo 150 palabras.
   ```

9. Guarda este segundo borrador como `plantilla_correo_gerencia.txt`.

#### Resultado Esperado

Dos archivos de texto con plantillas de correo diferenciadas por nivel jerárquico, con marcadores de posición claramente identificados entre corchetes, listos para ser usados como cuerpo de mensaje en el flujo de Power Automate.

#### Verificación

- Abre cada archivo `.txt` y confirma que contiene al menos 5 marcadores de posición entre corchetes.
- Verifica que el tono difiere entre el correo operativo (más cercano) y el gerencial (más ejecutivo).
- Confirma que ambos archivos están guardados en `C:\LabM365\Practica-04\`.

---

### Paso 3: Creación del Flujo Automatizado en Power Automate

**Objetivo:** Construir un flujo en Power Automate que detecte cuando se agrega o modifica un registro en el Excel de empleados y dispare automáticamente el envío de un correo personalizado en Outlook con los datos del empleado correspondiente.

#### Instrucciones

1. Abre tu navegador y navega a `https://make.powerautomate.com`.

2. Inicia sesión con tu cuenta corporativa de Microsoft 365.

3. En el panel izquierdo, haz clic en **+ Crear** y selecciona **Flujo automatizado en la nube**.

4. En el cuadro de diálogo, asigna el nombre:
   ```
   Flujo_Nomina_Correos_Personalizados
   ```

5. En el campo de búsqueda de disparadores, escribe:
   ```
   Excel Online Business
   ```
   Selecciona el disparador: **Cuando se agrega una fila en una tabla (Excel Online Business)**.

6. Haz clic en **Crear**.

7. Configura el disparador con los siguientes parámetros:

   | Campo | Valor |
   |---|---|
   | **Ubicación** | SharePoint |
   | **Biblioteca de documentos** | Documentos (o la biblioteca donde guardaste el archivo) |
   | **Archivo** | `empleados_ficticios.xlsx` |
   | **Tabla** | `Empleados` |

   > 📝 **Nota:** Si el archivo está en tu OneDrive de trabajo, selecciona **OneDrive for Business** como ubicación en lugar de SharePoint.

8. Haz clic en **+ Nuevo paso** y busca la acción:
   ```
   Enviar un correo electrónico (V2) — Office 365 Outlook
   ```

9. Configura la acción de correo con los siguientes valores. Para insertar contenido dinámico, haz clic en el campo correspondiente y selecciona el ícono de **relámpago** (contenido dinámico):

   | Campo | Configuración |
   |---|---|
   | **Para** | `[Contenido dinámico: Correo_Electronico]` |
   | **Asunto** | `Notificación de Nómina — [Contenido dinámico: Periodo_Nomina] — [Contenido dinámico: Nombre_Completo]` |
   | **Cuerpo** | Pega el contenido de `plantilla_correo_operativo.txt` y reemplaza cada marcador `[NOMBRE_EMPLEADO]` por `[Contenido dinámico: Nombre_Completo]`, `[MONTO_NETO]` por `[Contenido dinámico: Salario_Mensual]`, etc. |
   | **Es HTML** | Sí (activa el interruptor) |

   > 💡 **Consejo:** Para diferenciar el correo por nivel jerárquico, añade un paso de **Condición** antes del envío: si `Nivel_Jerarquico` es igual a `Gerencia`, usa la plantilla gerencial; de lo contrario, usa la operativa.

10. Para añadir la condición de nivel jerárquico:
    - Haz clic en **+ Nuevo paso** > **Condición**.
    - En el campo izquierdo, inserta `[Contenido dinámico: Nivel_Jerarquico]`.
    - Operador: **es igual a**.
    - Valor: `Gerencia`.
    - En la rama **Sí**: configura el correo con la plantilla gerencial.
    - En la rama **No**: configura el correo con la plantilla operativa.

11. Agrega un paso final para actualizar la columna `Estatus_Envio` en Excel:
    - Haz clic en **+ Nuevo paso** (dentro de cada rama de la condición).
    - Busca: **Actualizar una fila — Excel Online Business**.
    - Configura los mismos parámetros de ubicación/archivo/tabla del disparador.
    - En **Identificador de fila**, usa `[Contenido dinámico: ID_Empleado]`.
    - En **Estatus_Envio**, escribe:
      ```
      Enviado — [utcNow()]
      ```

12. Haz clic en **Guardar** (esquina superior derecha).

13. Para probar el flujo, haz clic en **Probar** > **Manualmente** > **Ejecutar flujo**.
    - Abre el archivo Excel, agrega una fila de empleado ficticio de prueba con un correo válido de un participante y guarda el archivo.
    - Regresa a Power Automate y observa la ejecución del flujo en tiempo real.

#### Resultado Esperado

El flujo se ejecuta sin errores. El participante de prueba recibe un correo en su bandeja de entrada con su nombre, nivel jerárquico y datos de nómina personalizados. La columna `Estatus_Envio` del Excel se actualiza con la marca de tiempo del envío.

#### Verificación

- En Power Automate, navega a **Historial de ejecuciones** del flujo y confirma que el estado es **Correcto** (ícono verde ✅).
- Abre el correo recibido en el buzón de prueba y verifica que el nombre del empleado ficticio aparece correctamente (no como marcador de posición).
- Abre el Excel y confirma que la columna J contiene la marca de tiempo del envío.

---

### Paso 4: Gestión de Tareas del Área con Copilot en Teams

**Objetivo:** Usar Copilot en Microsoft Teams para crear una lista de tareas del área de compensaciones, asignar responsables y configurar recordatorios automáticos para el seguimiento de solicitudes de empleados.

#### Instrucciones

1. Abre **Microsoft Teams** en tu equipo.

2. Navega al canal del equipo de práctica (el instructor habrá creado un canal llamado **`Practica-04-Compensaciones`** o similar).

3. En la barra de composición del canal, haz clic en el ícono de **Copilot** (o usa el atajo **Alt+Shift+C** en Windows).

4. Escribe el siguiente prompt en el chat de Copilot:

   ```
   Crea una lista de tareas pendientes para el área de compensaciones 
   correspondiente al cierre de nómina de la quincena actual. 
   Incluye las siguientes tareas con sus responsables sugeridos y 
   fechas límite (considera que hoy es el día 10 del mes):
   1. Validar incidencias de nómina reportadas por supervisores
   2. Procesar altas y bajas ante el IMSS
   3. Enviar recibos de nómina digitales a todos los empleados
   4. Conciliar pagos de Infonavit del periodo
   5. Generar reporte de variaciones salariales para Dirección
   Formato: tabla con columnas Tarea, Responsable, Fecha Límite, Prioridad, Estatus.
   ```

5. Copilot generará una tabla de tareas. Copia el resultado y pégalo en una nueva publicación del canal con el título: **"📋 Tareas de Cierre de Nómina — [Fecha actual]"**.

6. Ahora, abre la aplicación **Tareas de Planner y To Do** dentro de Teams (búscala en la barra lateral izquierda o en la pestaña superior del canal).

7. Crea un nuevo **Plan** llamado:
   ```
   Compensaciones — Cierre Quincena [Número de quincena]
   ```

8. Añade manualmente las 5 tareas generadas por Copilot. Para cada tarea:
   - Haz clic en **+ Agregar tarea**.
   - Ingresa el nombre de la tarea.
   - Asigna una fecha de vencimiento (según la tabla de Copilot).
   - Asigna la tarea a un participante del curso como responsable.
   - Establece la prioridad (Alta / Media / Baja).

9. Regresa al chat de Copilot en Teams y escribe el siguiente prompt para generar un recordatorio automático:

   ```
   Redacta un mensaje de recordatorio para el canal de Teams que se enviará 
   automáticamente 24 horas antes de la fecha límite de cada tarea de cierre 
   de nómina. El mensaje debe mencionar la tarea específica, el responsable 
   asignado y la fecha límite. Tono: profesional y directo. 
   Incluye un emoji relevante para cada tipo de tarea.
   ```

10. Usa el mensaje generado como plantilla para configurar un recordatorio manual en Teams: haz clic en los tres puntos (**...**) de la publicación de tareas > **Recordarme** > selecciona la fecha/hora deseada.

#### Resultado Esperado

Un plan de Planner activo con 5 tareas asignadas, con fechas límite, responsables y prioridades definidas. Una publicación en el canal del equipo con el resumen de tareas generado por Copilot. Un recordatorio configurado para al menos una tarea.

#### Verificación

- En Planner, confirma que las 5 tareas aparecen en la vista de **Tablero** con sus respectivos responsables.
- Verifica que la publicación del canal contiene la tabla de tareas con todas las columnas solicitadas.
- Confirma que el recordatorio aparece en tu calendario de Outlook como evento futuro.

---

### BLOQUE 4.2 — Plantillas Inteligentes y Biblioteca en SharePoint

---

### Paso 5: Creación de Plantilla de Carta de Oferta con Copilot en Word

**Objetivo:** Usar Copilot en Word para crear una plantilla corporativa de carta de oferta laboral que incluya campos variables, cumpla con los requisitos de la Ley Federal del Trabajo (LFT) y sea reutilizable para distintos perfiles de puesto.

#### Instrucciones

1. Abre el archivo `plantilla_base_carta_oferta.docx` desde `C:\LabM365\Practica-04\`.

2. En Word, haz clic en la pestaña **Inicio** y luego en el ícono de **Copilot** en la barra de herramientas (o usa **Alt+I** para abrir el panel de Copilot).

3. En el panel de Copilot, escribe el siguiente prompt:

   ```
   Basándote en el documento actual, genera una carta de oferta laboral 
   completa y profesional para una empresa mexicana. La carta debe cumplir 
   con los requisitos de la Ley Federal del Trabajo (LFT) e incluir:
   - Encabezado corporativo con campos variables: [NOMBRE_EMPRESA], [LOGO]
   - Datos del candidato: [NOMBRE_CANDIDATO], [PUESTO_OFERTADO], [DEPARTAMENTO]
   - Condiciones laborales: [SALARIO_MENSUAL_BRUTO], [TIPO_CONTRATO], 
     [FECHA_INICIO], [HORARIO_TRABAJO], [LUGAR_TRABAJO]
   - Prestaciones de ley: vacaciones, aguinaldo, prima vacacional conforme a LFT
   - Prestaciones adicionales: [PRESTACIONES_ADICIONALES]
   - Cláusula de confidencialidad básica
   - Espacio para firma del candidato y del representante de RH
   - Pie de página con datos de contacto: [CONTACTO_RH]
   Usa formato formal con tipografía clara. Todos los campos variables 
   deben estar en mayúsculas entre corchetes para facilitar su identificación.
   ```

4. Haz clic en **Generar** y espera a que Copilot produzca el contenido.

5. Revisa el documento generado. Si necesitas ajustes, usa prompts de refinamiento como:

   ```
   Añade una sección de "Periodo de Prueba" conforme al Artículo 47 de la LFT. 
   Máximo 30 días para empleados en general.
   ```

   O bien:

   ```
   Ajusta el lenguaje de la cláusula de confidencialidad para que sea 
   más específica sobre el manejo de información salarial y de nómina.
   ```

6. Una vez satisfecho con el resultado, aplica los estilos corporativos del documento base (si el archivo base tiene estilos predefinidos, Copilot los respetará automáticamente).

7. Guarda el archivo como:
   ```
   PLANTILLA_Carta_Oferta_v1.docx
   ```
   en `C:\LabM365\Practica-04\Plantillas\`

   > 📝 Crea la carpeta `Plantillas` si no existe.

#### Resultado Esperado

Un documento Word de 2–3 páginas con la carta de oferta completa, con al menos 12 campos variables entre corchetes, referencias explícitas a la LFT y formato corporativo consistente.

#### Verificación

- Usa **Ctrl+F** para buscar `[` en el documento y confirma que aparecen al menos 12 instancias de campos variables.
- Verifica que el documento menciona explícitamente: vacaciones (Art. 76 LFT), aguinaldo (Art. 87 LFT) y prima vacacional (Art. 80 LFT).
- Confirma que el archivo está guardado en la carpeta `Plantillas`.

---

### Paso 6: Creación de Plantilla de Constancia de Empleo y Salario

**Objetivo:** Generar con Copilot en Word una plantilla de constancia de empleo y salario que pueda completarse en menos de 2 minutos por el área de compensaciones, con validez legal para trámites ante instituciones financieras, IMSS e Infonavit.

#### Instrucciones

1. Abre el archivo `plantilla_base_constancia.docx` desde `C:\LabM365\Practica-04\`.

2. Abre el panel de Copilot en Word y escribe:

   ```
   Crea una constancia de empleo y salario para uso en México que incluya:
   - Membrete corporativo con: [NOMBRE_EMPRESA], [RFC_EMPRESA], 
     [DOMICILIO_FISCAL], [TELEFONO_EMPRESA]
   - Número de constancia: [NUM_CONSTANCIA]
   - Fecha de emisión: [FECHA_EMISION]
   - Datos del empleado: [NOMBRE_EMPLEADO], [RFC_EMPLEADO], [PUESTO], 
     [DEPARTAMENTO], [FECHA_INGRESO], [TIPO_CONTRATO]
   - Información salarial: [SALARIO_DIARIO_INTEGRADO], [SALARIO_MENSUAL_BRUTO], 
     [SALARIO_MENSUAL_NETO], [PERIODICIDAD_PAGO]
   - Registro IMSS: [NSS_EMPLEADO]
   - Propósito de la constancia: [PROPOSITO] (ej. trámite bancario, crédito Infonavit)
   - Declaración de vigencia de la relación laboral a la fecha de emisión
   - Firma del representante legal o apoderado de RH con datos: 
     [NOMBRE_FIRMANTE], [PUESTO_FIRMANTE], [FIRMA_DIGITAL]
   El documento debe caber en una sola página. Usa lenguaje formal y preciso.
   ```

3. Genera el documento y revisa que todos los campos estén presentes.

4. Añade un prompt de mejora específico para validez institucional:

   ```
   Añade al pie del documento una nota legal que indique que esta constancia 
   fue emitida para los fines indicados y no implica ningún compromiso adicional 
   por parte de la empresa. Incluye también el número de registro patronal 
   ante el IMSS: [REG_PATRONAL_IMSS].
   ```

5. Aplica el estilo "Título 1" al encabezado **CONSTANCIA DE EMPLEO Y SALARIO** para facilitar la navegación.

6. Guarda como `PLANTILLA_Constancia_Empleo_Salario_v1.docx` en `C:\LabM365\Practica-04\Plantillas\`.

#### Resultado Esperado

Documento de una sola página con constancia de empleo y salario, con todos los campos de datos requeridos para trámites ante IMSS, Infonavit e instituciones financieras, y nota legal al pie.

#### Verificación

- Confirma que el documento tiene exactamente 1 página (verifica en la barra de estado de Word: "1 de 1").
- Busca con **Ctrl+F** el término `IMSS` — debe aparecer al menos 2 veces (NSS y registro patronal).
- Verifica que el archivo está guardado en la carpeta `Plantillas`.

---

### Paso 7: Creación de Plantilla de Aviso de Ajuste Salarial

**Objetivo:** Diseñar con Copilot en Word una plantilla de aviso de ajuste salarial que documente correctamente el cambio, incluya el cálculo del incremento porcentual y cumpla con los requisitos de notificación de la LFT.

#### Instrucciones

1. Abre el archivo `plantilla_base_ajuste_salarial.docx` desde `C:\LabM365\Practica-04\`.

2. En el panel de Copilot, escribe:

   ```
   Crea un aviso formal de ajuste salarial para una empresa mexicana. 
   El documento debe incluir:
   - Encabezado: [NOMBRE_EMPRESA], [FECHA_DOCUMENTO], [FOLIO_AVISO]
   - Datos del empleado: [NOMBRE_EMPLEADO], [PUESTO], [DEPARTAMENTO], 
     [FECHA_INGRESO], [RFC_EMPLEADO]
   - Detalle del ajuste:
     * Salario anterior: [SALARIO_ANTERIOR_MENSUAL]
     * Nuevo salario: [SALARIO_NUEVO_MENSUAL]
     * Incremento en pesos: [INCREMENTO_PESOS]
     * Incremento porcentual: [INCREMENTO_PORCENTAJE]%
     * Fecha efectiva del ajuste: [FECHA_EFECTIVA]
     * Motivo del ajuste: [MOTIVO_AJUSTE] (ej. revisión anual, promoción, 
       ajuste por inflación)
   - Impacto en prestaciones: cómo cambia el cálculo de IMSS, Infonavit, 
     ISR y PTU con el nuevo salario
   - Sección de acuse de recibo con firma del empleado y fecha
   - Firma del Gerente de RH y del Director del área
   El tono debe ser formal y respetuoso. El documento debe caber en una página.
   ```

3. Genera y revisa el documento.

4. Añade un prompt adicional para la sección de impacto en prestaciones:

   ```
   En la sección de impacto en prestaciones, añade una tabla con tres columnas: 
   "Concepto", "Cálculo con salario anterior", "Cálculo con nuevo salario". 
   Incluye filas para: Cuota IMSS empleado, Aportación Infonavit, 
   ISR estimado mensual, Base de cálculo PTU.
   Los valores deben ser marcadores de posición entre corchetes.
   ```

5. Guarda como `PLANTILLA_Aviso_Ajuste_Salarial_v1.docx` en `C:\LabM365\Practica-04\Plantillas\`.

#### Resultado Esperado

Documento de aviso de ajuste salarial de 1 página con tabla comparativa de impacto en prestaciones, sección de acuse de recibo y firmas de autorización. Todos los valores numéricos son marcadores de posición.

#### Verificación

- Confirma que la tabla de impacto en prestaciones tiene exactamente 4 filas de conceptos (IMSS, Infonavit, ISR, PTU).
- Verifica que hay dos líneas de firma al final: empleado y Gerente de RH.
- Confirma que el archivo está guardado en la carpeta `Plantillas`.

---

### Paso 8: Publicación de la Biblioteca de Plantillas en SharePoint

**Objetivo:** Subir las tres plantillas creadas a una biblioteca de documentos en SharePoint, configurar metadatos para facilitar la búsqueda y establecer permisos de acceso para el equipo de compensaciones.

#### Instrucciones

1. Abre tu navegador y navega al sitio de SharePoint del curso.

2. En el menú lateral izquierdo, haz clic en **Documentos**.

3. Crea una nueva carpeta llamada:
   ```
   Biblioteca_Plantillas_Compensaciones
   ```
   Para ello, haz clic en **+ Nuevo** > **Carpeta**.

4. Dentro de la nueva carpeta, crea las siguientes subcarpetas:
   ```
   ├── 01_Cartas_de_Oferta
   ├── 02_Constancias
   └── 03_Avisos_Salariales
   ```

5. Sube las plantillas a sus carpetas correspondientes:
   - Arrastra `PLANTILLA_Carta_Oferta_v1.docx` a `01_Cartas_de_Oferta`.
   - Arrastra `PLANTILLA_Constancia_Empleo_Salario_v1.docx` a `02_Constancias`.
   - Arrastra `PLANTILLA_Aviso_Ajuste_Salarial_v1.docx` a `03_Avisos_Salariales`.

6. Para cada archivo, configura los **metadatos de columna**:
   - Haz clic en los tres puntos (**...**) junto al archivo > **Propiedades**.
   - Completa los campos (si el sitio tiene columnas configuradas):
     | Campo | Valor |
     |---|---|
     | Tipo de documento | Plantilla |
     | Área | Compensaciones |
     | Versión | 1.0 |
     | Estado | Activo |
     | Última revisión | [Fecha de hoy] |

7. Configura los permisos de la carpeta `Biblioteca_Plantillas_Compensaciones`:
   - Haz clic en los tres puntos (**...**) de la carpeta > **Administrar acceso**.
   - Verifica que el grupo de **Miembros del sitio** tiene permisos de **Editar**.
   - Si hay participantes externos al sitio, agrega sus correos con permisos de **Lectura**.

8. Obtén el enlace compartido de la carpeta:
   - Haz clic en los tres puntos > **Copiar vínculo**.
   - Selecciona **Personas de la organización con el vínculo pueden ver**.
   - Copia el enlace y guárdalo en un bloc de notas — lo usarás en el siguiente paso.

9. Regresa a Teams y publica el enlace en el canal **`Practica-04-Compensaciones`** con el siguiente mensaje (puedes usar Copilot en Teams para redactarlo):

   ```
   Redacta un mensaje para el canal de Teams anunciando la nueva 
   Biblioteca de Plantillas de Compensaciones en SharePoint. 
   El mensaje debe incluir: propósito de la biblioteca, las tres 
   plantillas disponibles, instrucciones breves de uso y el enlace 
   de acceso. Tono: profesional y entusiasta. Máximo 100 palabras.
   Incluye el enlace: [PEGAR_ENLACE_SHAREPOINT]
   ```

#### Resultado Esperado

Tres plantillas organizadas en subcarpetas dentro de SharePoint, con metadatos configurados y permisos adecuados. Un mensaje publicado en el canal de Teams con el anuncio de la biblioteca y el enlace de acceso.

#### Verificación

- En SharePoint, navega a la carpeta `Biblioteca_Plantillas_Compensaciones` y confirma que las tres subcarpetas contienen sus respectivos archivos.
- Haz clic en cada archivo para abrirlo en Word Online y verifica que se abre correctamente.
- Confirma que el mensaje en Teams contiene el enlace de SharePoint y es visible para todos los miembros del canal.

---

### Paso 9: Diseño del Flujo de Soporte Básico al Empleado

**Objetivo:** Configurar un flujo semi-automatizado en Power Automate que, al recibir un correo de solicitud de constancia en Outlook, genere automáticamente un borrador de respuesta usando la plantilla de Word correspondiente y notifique al responsable del área para su revisión y envío final.

#### Instrucciones

1. Regresa a `https://make.powerautomate.com`.

2. Crea un nuevo **Flujo automatizado en la nube** con el nombre:
   ```
   Flujo_Soporte_Solicitud_Constancias
   ```

3. Selecciona el disparador:
   ```
   Cuando llega un nuevo correo electrónico (V3) — Office 365 Outlook
   ```

4. Configura el disparador con los siguientes filtros:

   | Campo | Valor |
   |---|---|
   | **Carpeta** | Bandeja de entrada |
   | **Asunto contiene** | `Solicitud de Constancia` |
   | **Solo con datos adjuntos** | No |
   | **Importancia** | Cualquiera |

5. Añade un paso de **Obtener correo electrónico (V2)** para extraer el cuerpo del mensaje y el remitente.

6. Añade un paso de **Crear archivo — SharePoint** para generar una copia de la plantilla de constancia:
   - Ubica el archivo `PLANTILLA_Constancia_Empleo_Salario_v1.docx` en SharePoint.
   - Configura la acción para crear una copia con el nombre:
     ```
     Constancia_[Contenido dinámico: De (remitente)]_[utcNow()].docx
     ```

7. Añade un paso de **Enviar un correo electrónico (V2)** para notificar al responsable del área:

   | Campo | Valor |
   |---|---|
   | **Para** | Correo del responsable de compensaciones (usa tu correo de práctica) |
   | **Asunto** | `⚠️ Nueva solicitud de constancia — Acción requerida` |
   | **Cuerpo** | `Se recibió una solicitud de constancia de: [Contenido dinámico: De]. Se generó un borrador en SharePoint. Por favor, completa los datos y envía al solicitante. Enlace: [URL de SharePoint]` |

8. Añade un paso de **Enviar respuesta automática al solicitante**:
   - Usa otra acción de **Enviar un correo electrónico (V2)**.
   - **Para:** `[Contenido dinámico: De (remitente)]`
   - **Asunto:** `Re: Solicitud de Constancia — Recibida`
   - **Cuerpo:** Usa Copilot para generar el texto:

     ```
     Redacta una respuesta automática de acuse de recibo para una solicitud 
     de constancia de empleo. El correo debe confirmar que la solicitud fue 
     recibida, indicar un tiempo de respuesta de 24-48 horas hábiles, 
     proporcionar un número de folio automático y dar datos de contacto 
     del área de compensaciones. Tono: profesional y empático. Máximo 80 palabras.
     ```

9. Guarda el flujo y pruébalo enviando un correo a tu propio buzón con el asunto:
   ```
   Solicitud de Constancia — Empleado de Prueba
   ```

#### Resultado Esperado

Al recibir un correo con el asunto correcto, el flujo: (1) genera una copia de la plantilla de constancia en SharePoint, (2) notifica al responsable del área con el enlace al borrador, y (3) envía una respuesta automática de acuse al solicitante.

#### Verificación

- En Power Automate, revisa el **Historial de ejecuciones** y confirma que el flujo se ejecutó correctamente (estado: ✅ Correcto).
- Verifica en SharePoint que se creó el archivo de constancia con el nombre dinámico.
- Confirma que recibiste dos correos: el de notificación al responsable y el acuse de recibo al solicitante.

---

## 7. Validación y Pruebas Integrales

Al finalizar todos los pasos, realiza las siguientes verificaciones de integración para confirmar que el ecosistema completo funciona correctamente:

### Lista de Verificación Final

| # | Elemento a verificar | Herramienta | Estado |
|---|---|---|---|
| 1 | Flujo de nómina ejecutado sin errores en Power Automate | Power Automate | ☐ |
| 2 | Correo personalizado recibido con nombre y datos correctos | Outlook | ☐ |
| 3 | Columna `Estatus_Envio` actualizada en Excel | Excel | ☐ |
| 4 | Plan de Planner con 5 tareas asignadas y con fechas | Teams / Planner | ☐ |
| 5 | Tres plantillas publicadas en SharePoint con metadatos | SharePoint | ☐ |
| 6 | Flujo de soporte ejecutado al recibir solicitud de constancia | Power Automate | ☐ |
| 7 | Acuse de recibo automático enviado al solicitante | Outlook | ☐ |
| 8 | Enlace de biblioteca de plantillas publicado en Teams | Teams | ☐ |

### Prueba de Extremo a Extremo

Simula el siguiente escenario completo en **10 minutos**:

1. Un empleado ficticio envía un correo con el asunto `Solicitud de Constancia — Juan Pérez García`.
2. El flujo de soporte se activa, genera la constancia en SharePoint y notifica al responsable.
3. El responsable abre la constancia en SharePoint, completa los campos variables `[NOMBRE_EMPLEADO]`, `[PUESTO]`, `[SALARIO_MENSUAL_BRUTO]` y `[FECHA_EMISION]` manualmente.
4. El responsable envía la constancia completada al solicitante desde Outlook.
5. Registra la tarea "Constancia enviada a Juan Pérez" como **Completada** en el plan de Planner.

Si completaste los 5 pasos del escenario en menos de 10 minutos, el ecosistema está funcionando correctamente.

---

## 8. Resolución de Problemas

### Problema 1: El flujo de Power Automate falla con error "No se encontró la tabla en el archivo Excel"

**Síntoma:** Al ejecutar el flujo `Flujo_Nomina_Correos_Personalizados`, el historial de ejecuciones muestra un error en el disparador o en el paso de actualización de fila con el mensaje: *"The table 'Empleados' was not found"* o *"Resource not found"*.

**Causa:** El archivo Excel fue guardado sin una tabla formalmente definida (rango de datos sin convertir a tabla de Excel), o el nombre de la tabla no coincide exactamente con el configurado en Power Automate. También puede ocurrir si el archivo fue movido de ubicación después de configurar el flujo.

**Solución:**
1. Abre `empleados_ficticios.xlsx` en Excel.
2. Selecciona el rango de datos (A1:J16).
3. Ve a **Insertar** > **Tabla** > confirma que "La tabla tiene encabezados" está marcado > **Aceptar**.
4. Haz clic en la tabla creada > pestaña **Diseño de tabla** > cambia el nombre en el campo **Nombre de tabla** a exactamente:
   ```
   Empleados
   ```
   (sin espacios, sin acentos, sin mayúsculas adicionales)
5. Guarda el archivo en la **misma ubicación** de SharePoint u OneDrive donde el flujo lo busca.
6. En Power Automate, edita el flujo, elimina y vuelve a seleccionar el archivo y la tabla en el disparador.
7. Guarda y vuelve a probar.

---

### Problema 2: Copilot en Word no genera contenido o muestra el mensaje "Copilot no está disponible en este documento"

**Síntoma:** Al abrir el panel de Copilot en Word y escribir un prompt, el botón **Generar** no responde, o aparece el mensaje *"Copilot no está disponible"* / *"Tu organización no ha habilitado esta función"*. Esto puede ocurrir en los Pasos 5, 6 y 7.

**Causa:** Existen tres causas frecuentes: (a) la licencia de Microsoft 365 Copilot no está asignada correctamente al usuario, (b) el documento fue abierto desde una ubicación local (disco duro) en lugar de OneDrive o SharePoint — Copilot en Word requiere que el archivo esté guardado en la nube, o (c) el administrador del tenant no ha habilitado Copilot para la aplicación Word en las políticas de Microsoft 365.

**Solución:**
1. **Verificar ubicación del archivo:** Guarda el documento en **OneDrive for Business** antes de intentar usar Copilot:
   - Ve a **Archivo** > **Guardar una copia** > **OneDrive — [Nombre de tu organización]**.
   - Cierra y vuelve a abrir el documento desde OneDrive.
2. **Verificar licencia:** Ve a `https://portal.office.com` > haz clic en tu avatar > **Ver cuenta** > **Suscripciones**. Confirma que aparece **Microsoft 365 Copilot** en la lista de licencias activas.
3. **Si la licencia no aparece:** Contacta al administrador de TI para que asigne la licencia de Microsoft 365 Copilot a tu cuenta. Este proceso puede tardar hasta 24 horas en propagarse.
4. **Alternativa temporal:** Si Copilot no está disponible durante la práctica, usa `https://copilot.microsoft.com` con tu cuenta corporativa para generar el contenido de las plantillas y cópialo manualmente al documento de Word.

---

## 9. Limpieza del Entorno

Una vez completada y validada la práctica, realiza las siguientes acciones de limpieza para mantener el entorno ordenado y evitar envíos accidentales o ejecuciones no deseadas de los flujos:

### Desactivar los Flujos de Power Automate

1. Ve a `https://make.powerautomate.com`.
2. En **Mis flujos**, localiza `Flujo_Nomina_Correos_Personalizados`.
3. Haz clic en los tres puntos (**...**) > **Desactivar**.
4. Repite para `Flujo_Soporte_Solicitud_Constancias`.

> ⚠️ **Importante:** No elimines los flujos — solo desactívalos. El instructor puede necesitar revisarlos para la evaluación de la práctica.

### Limpiar la Columna de Estatus en Excel

1. Abre `empleados_ficticios.xlsx`.
2. Selecciona toda la columna J (`Estatus_Envio`).
3. Presiona **Suprimir** para limpiar los valores de prueba.
4. Guarda el archivo.

### Archivar Archivos Locales

1. En tu equipo local, comprime la carpeta `C:\LabM365\Practica-04\` en un archivo ZIP:
   - Clic derecho > **Comprimir en archivo ZIP**.
   - Nombra el archivo: `Practica-04_[TuNombre]_[Fecha].zip`.
2. Sube el archivo ZIP a la carpeta de entrega del curso en SharePoint (la que indique el instructor).

### Verificar Permisos de SharePoint

1. En SharePoint, confirma que la carpeta `Biblioteca_Plantillas_Compensaciones` tiene los permisos correctos (no acceso público externo).
2. Si durante la práctica otorgaste permisos temporales a cuentas externas, revócalos desde **Administrar acceso**.

---

## 10. Resumen y Recursos Adicionales

### Resumen de la Práctica

En esta práctica de 90 minutos construiste un ecosistema funcional de comunicación y gestión automatizada para el área de compensaciones, abarcando las dos capas tecnológicas del Capítulo 4:

**Bloque 4.1 — Comunicación Corporativa Automatizada:**
- Estructuraste un archivo Excel de empleados ficticios como fuente de datos para automatización masiva.
- Usaste **Copilot en Outlook** para redactar plantillas de correo personalizadas diferenciadas por nivel jerárquico (operativo y gerencial), con marcadores de posición para variables dinámicas.
- Construiste un **flujo en Power Automate** que detecta nuevas filas en el Excel y dispara automáticamente correos personalizados, actualizando el estatus de envío en la fuente de datos.
- Implementaste una **lista de tareas de cierre de nómina** en Planner usando Copilot en Teams para generarla y asignar responsables.

**Bloque 4.2 — Plantillas Inteligentes y Biblioteca en SharePoint:**
- Creaste tres plantillas corporativas con **Copilot en Word**: carta de oferta (con referencias a LFT), constancia de empleo y salario (válida para IMSS e Infonavit) y aviso de ajuste salarial (con tabla comparativa de impacto en prestaciones).
- Organizaste las plantillas en una **biblioteca de SharePoint** con metadatos, subcarpetas por tipo y permisos controlados.
- Diseñaste un **flujo de soporte al empleado** que responde automáticamente solicitudes de constancias, genera borradores en SharePoint y notifica al responsable del área.

### Conceptos Clave Reforzados

| Concepto | Herramienta aplicada |
|---|---|
| Personalización masiva con variables dinámicas | Power Automate + Excel + Outlook |
| Prompts efectivos para documentos legales en RH | Copilot en Word |
| Gestión de tareas automatizada | Copilot en Teams + Planner |
| Biblioteca de plantillas corporativas | SharePoint Online |
| Flujo de soporte semi-automatizado | Power Automate + Outlook + SharePoint |

### Recursos Adicionales

- 📚 [Documentación oficial: Copilot en Outlook — Redacción de correos](https://support.microsoft.com/es-es/topic/usar-copilot-en-outlook)
- 📚 [Documentación oficial: Copilot en Word — Generar y transformar contenido](https://support.microsoft.com/es-es/topic/usar-copilot-en-word)
- 📚 [Referencia de conectores de Power Automate: Excel Online Business](https://learn.microsoft.com/es-es/connectors/excelonlinebusiness/)
- 📚 [Referencia de conectores de Power Automate: Office 365 Outlook](https://learn.microsoft.com/es-es/connectors/office365/)
- 📚 [Guía de administración de SharePoint: Bibliotecas de documentos y metadatos](https://learn.microsoft.com/es-es/sharepoint/dev/solution-guidance/modern-experience-customizations-provisioning-sites)
- 📚 [Ley Federal del Trabajo — Texto vigente (DOF)](https://www.diputados.gob.mx/LeyesBiblio/pdf/LFT.pdf)
- 📚 [Límites de envío de correo en Microsoft 365](https://learn.microsoft.com/es-es/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)

> 🚀 **Próxima práctica:** En la Práctica 5 explorarás la construcción de agentes conversacionales en Microsoft Copilot Studio capaces de responder consultas de nómina de forma completamente autónoma, integrando los flujos y plantillas creados en esta práctica como base de conocimiento del agente.

---
