# Práctica 5 — Auditoría y Encriptación de Reportes de Nómina con Copilot

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 90 minutos |
| **Complejidad** | Alta |
| **Nivel Bloom** | Aplicar |
| **Módulo** | Capítulo 5 — Seguridad en Datos de Compensaciones |
| **Práctica número** | 5 |
| **Última actualización** | 2024 |

---

## 2. Descripción General

Esta práctica aborda la dimensión crítica de **seguridad y privacidad** en el uso de inteligencia artificial para la gestión de compensaciones. Utilizarás Microsoft 365 Copilot para auditar archivos de nómina simulados, identificar datos sensibles expuestos (RFC, CURP, salarios, cuentas bancarias) y evaluar el nivel de riesgo de confidencialidad. Posteriormente, implementarás controles técnicos de protección —etiquetas de sensibilidad de Microsoft Purview, cifrado de archivos Excel y permisos granulares en SharePoint— y redactarás, con asistencia de Copilot, una política de uso responsable de IA para el área de compensaciones conforme a la **LFPDPPP** y la **NOM-035-STPS-2018**.

> ⚠️ **Aviso de cumplimiento:** Todos los archivos de práctica contienen exclusivamente **datos ficticios**. Está estrictamente prohibido sustituirlos por datos reales de empleados, conforme a la Ley Federal de Protección de Datos Personales en Posesión de los Particulares (LFPDPPP).

---

## 3. Objetivos de Aprendizaje

Al finalizar esta práctica serás capaz de:

- [ ] **Aplicar** técnicas de auditoría de seguridad en reportes de nómina usando Copilot para identificar datos sensibles expuestos y evaluar el nivel de riesgo de confidencialidad.
- [ ] **Implementar** controles de encriptación y protección de archivos de nómina en Excel y SharePoint mediante etiquetas de sensibilidad, contraseñas de documento y permisos de acceso granulares.
- [ ] **Analizar** la legislación mexicana de privacidad aplicable a datos de nómina (LFPDPPP, NOM-035) usando Copilot para generar lineamientos de manejo de información.
- [ ] **Diseñar** una política de uso responsable de IA en el área de compensaciones que establezca qué datos pueden procesarse con Copilot y cuáles requieren anonimización previa.

---

## 4. Prerrequisitos

### Conocimientos Previos

| Conocimiento requerido | Nivel mínimo |
|---|---|
| Uso básico de Microsoft Excel (hojas, rangos, formato) | Intermedio |
| Navegación en SharePoint Online | Básico |
| Conceptos generales de la LFPDPPP | Básico |
| Haber completado las Prácticas 1 a 4 del curso | Obligatorio |
| Comprensión del filtro de tres preguntas de seguridad (Lección 5.1) | Obligatorio |

### Accesos y Licencias Requeridos

| Recurso | Requerimiento |
|---|---|
| Cuenta Microsoft 365 corporativa | Licencia activa **Microsoft 365 Copilot** (no Copilot gratuito) |
| Microsoft Excel (M365) | Versión 2308 o superior |
| Microsoft Purview | Acceso a etiquetas de sensibilidad habilitado por el administrador |
| SharePoint Online | Permisos de **Propietario** en el sitio del curso |
| Microsoft Word (M365) | Versión actual con Copilot habilitado |
| Archivos de práctica | Dataset `P5_Nomina_Simulada.xlsx` y `P5_Bandas_Salariales.xlsx` (proporcionados por el instructor en SharePoint) |

> 📋 **Nota para el administrador:** Verificar que Microsoft Purview Information Protection esté habilitado en el tenant y que las etiquetas de sensibilidad "Confidencial" y "Altamente Confidencial" estén publicadas para los usuarios del curso antes de la sesión.

---

## 5. Entorno de Laboratorio

### Hardware Recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8ª gen / AMD Ryzen 5 | Intel Core i7 / AMD Ryzen 7 |
| RAM | 8 GB | 16 GB |
| Almacenamiento libre | 10 GB | 20 GB |
| Conexión a internet | 10 Mbps | 25 Mbps |
| Resolución de pantalla | 1366×768 | 1920×1080 |

### Software Necesario

| Aplicación | Versión | Propósito en esta práctica |
|---|---|---|
| Microsoft Excel (M365) | 2308+ | Auditoría y protección de archivos de nómina |
| Microsoft Word (M365) | Actual | Redacción de política con Copilot |
| Microsoft Purview | Actual | Etiquetas de sensibilidad |
| SharePoint Online | Actual | Configuración de permisos granulares |
| Microsoft Edge / Chrome | 120+ | Acceso a portales web |
| Microsoft 365 Copilot | Activo | Auditoría, análisis normativo y redacción |

### Configuración Inicial del Entorno

Antes de iniciar los pasos de la práctica, realiza la siguiente verificación:

**Paso A — Verificar acceso a los archivos de práctica:**
1. Abre tu navegador y navega al sitio de SharePoint del curso.
2. Ve a la carpeta **Módulo 5 → Archivos de Práctica**.
3. Confirma que existen los siguientes archivos:
   - `P5_Nomina_Simulada.xlsx`
   - `P5_Bandas_Salariales.xlsx`
   - `P5_Plantilla_Politica_IA.docx`
4. Descarga los tres archivos a una carpeta local: `C:\CursoM365\Practica5\` (Windows) o `~/CursoM365/Practica5/` (Mac).

**Paso B — Verificar que Copilot esté activo en Excel:**
1. Abre `P5_Nomina_Simulada.xlsx` en Excel.
2. En la cinta de opciones, verifica que aparezca el botón **Copilot** (ícono de constelación) en la pestaña **Inicio**.
3. Si no aparece, notifica al instructor antes de continuar.

**Paso C — Verificar acceso a etiquetas de sensibilidad:**
1. En Excel, ve a **Inicio → Sensibilidad** (botón de Microsoft Purview).
2. Confirma que aparecen al menos las etiquetas: **General**, **Confidencial** y **Altamente Confidencial**.
3. Si el botón no aparece, ve a **Archivo → Opciones → Centro de confianza → Configuración del Centro de confianza → Complementos de Office** y verifica que el complemento de Microsoft Purview esté habilitado.

---

## 6. Procedimiento Paso a Paso

---

### Sección 5.1 — Ciberseguridad en Bandas Salariales

---

### Paso 1: Auditoría Inicial del Archivo de Nómina con Copilot

**Objetivo:** Usar Copilot en Excel para identificar automáticamente qué tipos de datos sensibles contiene el archivo de nómina simulado y generar un reporte de riesgo inicial.

#### Instrucciones

1. Asegúrate de que `P5_Nomina_Simulada.xlsx` está abierto en Excel. El archivo contiene las siguientes columnas en la Hoja "Nómina_Junio":

   | Columna | Ejemplo de dato |
   |---|---|
   | ID_Empleado | EMP-001 |
   | Nombre_Completo | Juan Pérez García (ficticio) |
   | RFC | PEGJ850312AB1 (ficticio) |
   | CURP | PEGJ850312HDFRRN01 (ficticio) |
   | NSS | 12345678901 (ficticio) |
   | Salario_Mensual_Bruto | $25,000.00 |
   | Cuenta_Bancaria | 002180012345678901 (ficticia) |
   | CLABE | 002180012345678901 (ficticia) |
   | Banco | BBVA |
   | Deduccion_IMSS | $1,312.50 |
   | Deduccion_ISR | $3,200.00 |
   | Salario_Neto | $20,487.50 |
   | Departamento | Finanzas |
   | Nivel_Puesto | Senior |

2. Haz clic en el botón **Copilot** en la cinta de opciones de Excel para abrir el panel lateral de Copilot.

3. En el campo de chat de Copilot, escribe el siguiente prompt:

   ```
   Analiza todas las columnas de esta hoja de cálculo e identifica cuáles contienen 
   datos personales sensibles según la Ley Federal de Protección de Datos Personales 
   en Posesión de los Particulares (LFPDPPP) de México. Para cada columna sensible, 
   indica: (1) el tipo de dato, (2) el nivel de sensibilidad (Alto/Medio/Bajo), 
   (3) el riesgo potencial si este dato se expone sin autorización, y (4) si este 
   dato puede compartirse con herramientas de IA sin anonimización previa. 
   Presenta los resultados en una tabla ordenada por nivel de sensibilidad descendente.
   ```

4. Espera la respuesta de Copilot y **lee cuidadosamente** el análisis generado.

5. En la misma conversación de Copilot, escribe el siguiente prompt de seguimiento:

   ```
   Basándote en el análisis anterior, genera un resumen ejecutivo de 3 párrafos 
   sobre el nivel de riesgo de confidencialidad de este archivo. Incluye: 
   (1) cuántas columnas representan riesgo alto, (2) qué consecuencias legales 
   podría tener una filtración de estos datos según la LFPDPPP (menciona artículos 
   específicos si es posible), y (3) tres recomendaciones inmediatas de seguridad.
   ```

6. Selecciona todo el texto del resumen ejecutivo generado por Copilot, cópialo (Ctrl+C) y pégalo en una **nueva hoja** del mismo archivo llamada `Auditoria_Riesgo`. Para crear la hoja: clic derecho en la pestaña de hoja → **Insertar** → **Hoja de cálculo**.

#### Resultado Esperado

El panel de Copilot debe mostrar una tabla similar a la siguiente (el contenido exacto puede variar):

| Columna | Tipo de Dato | Sensibilidad | Riesgo de Exposición | ¿Requiere Anonimización para IA? |
|---|---|---|---|---|
| RFC | Identificador fiscal | **Alto** | Fraude fiscal, suplantación de identidad | **Sí — obligatorio** |
| CURP | Identificador único | **Alto** | Suplantación de identidad | **Sí — obligatorio** |
| Cuenta_Bancaria / CLABE | Dato financiero | **Alto** | Fraude bancario, robo | **Sí — obligatorio** |
| NSS | Seguridad social | **Alto** | Fraude ante IMSS | **Sí — obligatorio** |
| Salario_Mensual_Bruto | Dato laboral | **Medio** | Conflictos laborales, discriminación | **Sí — recomendado** |
| Nombre_Completo | Dato personal | **Medio** | Vinculación con otros datos | **Sí — recomendado** |
| Deducciones | Dato financiero | **Medio** | Inferencia de situación económica | **Sí — recomendado** |
| Departamento / Nivel | Dato organizacional | **Bajo** | Limitado en aislamiento | No necesariamente |

#### Verificación

- [ ] La hoja `Auditoria_Riesgo` existe en el archivo y contiene el resumen ejecutivo de Copilot.
- [ ] Copilot identificó al menos 4 columnas de sensibilidad **Alta**.
- [ ] El resumen menciona consecuencias legales vinculadas a la LFPDPPP.

---

### Paso 2: Aplicación de Etiquetas de Sensibilidad con Microsoft Purview

**Objetivo:** Clasificar el archivo de nómina con la etiqueta de sensibilidad adecuada usando Microsoft Purview para activar controles automáticos de protección.

#### Instrucciones

1. Con `P5_Nomina_Simulada.xlsx` aún abierto, ve a la pestaña **Inicio** en la cinta de opciones.

2. Localiza el botón **Sensibilidad** (puede aparecer como un escudo o candado con el texto "Sensibilidad"). Haz clic en él.

3. En el menú desplegable de etiquetas, selecciona **Altamente Confidencial → Todos los empleados** (o la etiqueta equivalente configurada en tu tenant: busca la que indique el mayor nivel de restricción disponible).

   > 💡 **Nota:** Si tu organización tiene etiquetas personalizadas, selecciona la que corresponda a "información de nómina" o "datos de empleados". Consulta con el instructor si tienes dudas.

4. Aparecerá un cuadro de diálogo solicitando confirmación o justificación. Escribe:

   ```
   Archivo de nómina con datos personales sensibles (RFC, CURP, cuentas bancarias). 
   Acceso restringido al equipo de Compensaciones y RRHH.
   ```

5. Haz clic en **Aplicar** o **Aceptar**.

6. Observa que en la barra de título del archivo ahora aparece una barra de color (generalmente roja o naranja) con el texto de la etiqueta aplicada. Esto confirma que la etiqueta está activa.

7. Guarda el archivo (Ctrl+S).

8. Ahora abre `P5_Bandas_Salariales.xlsx`. Este archivo contiene rangos salariales por nivel de puesto pero **sin datos individuales de empleados**.

9. Aplica la etiqueta **Confidencial → Departamento de RRHH** (o equivalente de nivel medio en tu tenant).

10. Guarda el archivo.

11. Abre Copilot en Excel (con `P5_Bandas_Salariales.xlsx` activo) y escribe:

    ```
    ¿Qué diferencia práctica existe entre clasificar un archivo como "Confidencial" 
    versus "Altamente Confidencial" en Microsoft Purview? ¿Qué controles técnicos 
    activa cada nivel automáticamente en Microsoft 365?
    ```

12. Copia la respuesta de Copilot en la hoja `Auditoria_Riesgo` del archivo de nómina (puedes abrir ambos archivos simultáneamente), bajo el título **"Diferencias de Clasificación Purview"**.

#### Resultado Esperado

- El archivo `P5_Nomina_Simulada.xlsx` muestra la barra de clasificación **Altamente Confidencial** en la parte superior.
- El archivo `P5_Bandas_Salariales.xlsx` muestra la barra de clasificación **Confidencial**.
- La explicación de Copilot describe controles como: cifrado automático, restricción de reenvío de correo, marcas de agua en impresión, y auditoría de acceso.

#### Verificación

- [ ] Ambos archivos muestran visualmente la etiqueta de sensibilidad aplicada.
- [ ] La justificación de clasificación fue documentada en el paso 4.
- [ ] La explicación de Copilot fue guardada en la hoja `Auditoria_Riesgo`.

---

### Paso 3: Protección de Hojas y Cifrado del Archivo Excel

**Objetivo:** Implementar protección por contraseña en hojas específicas de Excel y cifrado del archivo completo para prevenir acceso no autorizado.

#### Instrucciones

**Parte A — Proteger hojas individuales:**

1. En `P5_Nomina_Simulada.xlsx`, navega a la hoja **Nómina_Junio**.

2. Haz clic derecho en la pestaña de la hoja → **Proteger hoja**.

3. En el cuadro de diálogo "Proteger hoja":
   - Contraseña: `Nomina@2024Segura` (úsala solo para esta práctica; en producción usa contraseñas generadas aleatoriamente)
   - Deja marcadas únicamente las opciones: **Seleccionar celdas bloqueadas** y **Seleccionar celdas desbloqueadas**
   - Desmarca todas las demás opciones para máxima restricción
   - Haz clic en **Aceptar**
   - Confirma la contraseña: `Nomina@2024Segura`

4. Repite el proceso para la hoja **Auditoria_Riesgo** usando la misma contraseña.

5. Verifica que las hojas están protegidas intentando editar una celda: debe aparecer el mensaje *"La celda o el gráfico está protegido y es de solo lectura"*.

**Parte B — Cifrar el archivo completo:**

1. Ve a **Archivo → Información → Proteger libro → Cifrar con contraseña**.

2. En el campo de contraseña, escribe: `Cifrado#Nomina2024`

   > ⚠️ **Importante:** En un entorno real, usa contraseñas distintas para la protección de hojas y el cifrado del archivo. Documenta ambas contraseñas en un gestor de contraseñas corporativo (ej. Azure Key Vault), **nunca** en el mismo archivo.

3. Haz clic en **Aceptar** y confirma la contraseña.

4. Observa que en la sección **Información** aparece el ícono de candado con el texto *"Se requiere una contraseña para abrir este libro"*.

5. Guarda el archivo (Ctrl+S) y **ciérralo**.

6. Vuelve a abrirlo para verificar que solicita la contraseña de cifrado. Ingresa `Cifrado#Nomina2024` para continuar.

**Parte C — Consultar mejores prácticas con Copilot:**

7. Una vez abierto el archivo, abre el panel de Copilot y escribe:

   ```
   Soy profesional de Recursos Humanos en México. Necesito una checklist de 
   seguridad para archivos Excel que contienen datos de nómina (RFC, CURP, 
   salarios, cuentas bancarias). La checklist debe incluir controles técnicos 
   en Excel, controles en SharePoint y controles organizacionales. Organízala 
   en tres secciones con máximo 5 puntos cada una. Indica cuáles son obligatorios 
   por la LFPDPPP y cuáles son buenas prácticas adicionales.
   ```

8. Copia la checklist generada en la hoja `Auditoria_Riesgo` bajo el título **"Checklist de Seguridad para Archivos de Nómina"**.

#### Resultado Esperado

- Las hojas `Nómina_Junio` y `Auditoria_Riesgo` están protegidas con contraseña (aparece el ícono de candado en las pestañas).
- Al abrir el archivo desde cero, Excel solicita la contraseña de cifrado.
- La checklist de Copilot distingue claramente entre requisitos de la LFPDPPP y buenas prácticas adicionales.

#### Verificación

- [ ] Al intentar editar la hoja `Nómina_Junio` aparece el mensaje de protección.
- [ ] Al cerrar y reabrir el archivo, Excel solicita contraseña antes de mostrar el contenido.
- [ ] La checklist fue guardada en la hoja `Auditoria_Riesgo`.

---

### Paso 4: Configuración de Permisos Granulares en SharePoint

**Objetivo:** Configurar permisos de acceso restringidos en SharePoint Online para la carpeta de archivos de nómina, asegurando que solo el personal autorizado pueda acceder a los reportes de compensaciones.

#### Instrucciones

1. Abre tu navegador (Edge o Chrome) y navega al sitio de SharePoint del curso.

2. Ve a la biblioteca de documentos **Módulo 5 → Archivos de Práctica**.

3. Sube el archivo `P5_Nomina_Simulada.xlsx` (ya protegido y cifrado del paso anterior) a esta biblioteca:
   - Haz clic en **Cargar → Archivos**
   - Selecciona el archivo desde `C:\CursoM365\Practica5\`
   - Espera a que termine la carga

4. Una vez cargado, haz clic en los **tres puntos (...)** junto al archivo → **Detalles**.

5. En el panel de detalles, haz clic en **Administrar acceso**.

6. En la ventana de administración de acceso, haz clic en **Dejar de heredar permisos** (o "Stop inheriting permissions"). Confirma la acción en el cuadro de diálogo.

   > 💡 **Concepto clave:** Al "romper la herencia de permisos", este archivo ya no heredará automáticamente los permisos de la biblioteca padre. Esto permite configurar acceso específico solo para este documento.

7. Ahora configura los permisos específicos:
   - **Elimina** todos los grupos actuales excepto el de administradores del sitio
   - Haz clic en **Invitar personas** o **Compartir**
   - En el campo de destinatarios, escribe el correo de **tu propio usuario** (para verificar acceso)
   - Selecciona el nivel de permisos: **Solo lectura** (no "Editar")
   - Desmarca la opción de "Permitir que el destinatario comparta"
   - Haz clic en **Aplicar** o **Guardar**

8. Cierra el panel de permisos.

9. Para verificar la configuración, abre una ventana de **navegación privada/incógnito** en tu navegador, inicia sesión con una cuenta de prueba diferente (usa la cuenta de un compañero del curso con su autorización) e intenta acceder al archivo. Debe mostrar un mensaje de acceso denegado.

10. Regresa a tu sesión principal. Abre Copilot en el navegador (copilot.microsoft.com) o en Teams, y escribe el siguiente prompt:

    ```
    Explícame las diferencias entre los niveles de permisos en SharePoint Online: 
    Lectura, Colaboración, Diseño y Control total. ¿Cuál es el nivel recomendado 
    para un archivo de nómina que debe ser consultado (pero no modificado) por los 
    gerentes de área? ¿Y para el equipo de Compensaciones que debe actualizar los 
    datos mensualmente? Incluye las implicaciones de seguridad de cada decisión.
    ```

11. Documenta la respuesta de Copilot en un documento Word nuevo llamado `P5_Registro_Auditoria.docx`. Crea una sección titulada **"Configuración de Permisos SharePoint"** y pega la respuesta.

#### Resultado Esperado

- El archivo `P5_Nomina_Simulada.xlsx` en SharePoint tiene permisos independientes (herencia rota).
- Solo los usuarios explícitamente autorizados pueden acceder al archivo.
- El documento `P5_Registro_Auditoria.docx` existe con la sección de permisos documentada.

#### Verificación

- [ ] La columna "Acceso" del archivo en SharePoint muestra "Restringido" o un ícono de candado.
- [ ] La prueba con cuenta alternativa resultó en "Acceso denegado".
- [ ] El documento `P5_Registro_Auditoria.docx` fue creado con la documentación correspondiente.

---

### Sección 5.2 — Privacidad e Inteligencia Artificial

---

### Paso 5: Análisis de la LFPDPPP con Copilot para Datos de Nómina

**Objetivo:** Usar Copilot para analizar los artículos clave de la LFPDPPP aplicables al tratamiento de datos de empleados en sistemas de IA, y generar lineamientos prácticos para el área de compensaciones.

#### Instrucciones

1. Abre Microsoft Word y crea un nuevo documento en blanco. Guárdalo como `P5_Analisis_Legal_LFPDPPP.docx` en `C:\CursoM365\Practica5\`.

2. Activa Copilot en Word haciendo clic en el botón **Copilot** en la cinta de opciones (pestaña **Inicio** o **Insertar → Copilot**).

3. En el panel de Copilot, escribe el siguiente prompt de análisis legal:

   ```
   Actúa como experto en derecho laboral y protección de datos en México. 
   Analiza los siguientes aspectos de la Ley Federal de Protección de Datos 
   Personales en Posesión de los Particulares (LFPDPPP) aplicados específicamente 
   al contexto de datos de nómina y compensaciones en una empresa:
   
   1. ¿Cuáles son los principios del Artículo 6 (licitud, consentimiento, 
      información, calidad, finalidad, lealtad, proporcionalidad, responsabilidad) 
      que aplican al uso de datos de nómina en herramientas de IA como Copilot?
   
   2. ¿Qué obligaciones establece el Artículo 16 sobre el aviso de privacidad 
      cuando los datos de empleados se procesan con IA?
   
   3. ¿Qué dice la ley sobre la transferencia de datos personales a terceros 
      (incluidos proveedores de tecnología como Microsoft) según los Artículos 
      36 y 37?
   
   4. ¿Cuáles son las sanciones del Artículo 64 por incumplimiento en el manejo 
      de datos sensibles de empleados?
   
   Presenta la respuesta en formato de tabla con columnas: Artículo, 
   Obligación/Restricción, Aplicación Práctica en Nómina con IA.
   ```

4. Inserta la tabla generada por Copilot en el documento Word.

5. Escribe un segundo prompt para profundizar en la NOM-035:

   ```
   Ahora analiza la NOM-035-STPS-2018 (Factores de riesgo psicosocial en el 
   trabajo). ¿Qué datos recopilados en el contexto de esta norma (datos de 
   bienestar, encuestas de clima laboral, niveles de estrés) podrían considerarse 
   datos sensibles bajo la LFPDPPP? ¿Qué precauciones adicionales debe tomar el 
   área de Compensaciones al usar Copilot para analizar estos datos?
   ```

6. Inserta la respuesta como una segunda sección en el documento Word, titulada **"NOM-035 y Datos de Bienestar Laboral"**.

7. Escribe un tercer prompt orientado a la acción práctica:

   ```
   Basándote en el análisis anterior de la LFPDPPP y NOM-035, genera 5 lineamientos 
   concretos y accionables que el área de Compensaciones de una empresa mexicana 
   debe seguir antes de usar Microsoft Copilot para procesar datos de nómina. 
   Cada lineamiento debe incluir: (a) la acción específica, (b) el fundamento 
   legal, y (c) cómo verificar el cumplimiento. Usa formato numerado.
   ```

8. Inserta los lineamientos como una tercera sección titulada **"Lineamientos de Uso de IA para Compensaciones — Fundamento LFPDPPP"**.

9. Guarda el documento (Ctrl+S).

#### Resultado Esperado

El documento `P5_Analisis_Legal_LFPDPPP.docx` debe contener tres secciones bien estructuradas:
- Tabla de análisis LFPDPPP con artículos, obligaciones y aplicación práctica
- Análisis de NOM-035 con datos de bienestar identificados como sensibles
- 5 lineamientos accionables con fundamento legal y mecanismo de verificación

#### Verificación

- [ ] El documento tiene al menos 3 páginas de contenido sustantivo.
- [ ] La tabla de LFPDPPP incluye referencias a artículos específicos (6, 16, 36, 37, 64).
- [ ] Los 5 lineamientos incluyen acción, fundamento legal y verificación.
- [ ] El documento está guardado en la carpeta de práctica.

---

### Paso 6: Creación de la Matriz de Clasificación de Datos de Nómina

**Objetivo:** Construir una matriz de clasificación de todos los tipos de datos de nómina según su nivel de sensibilidad, indicando qué datos pueden usarse directamente con Copilot y cuáles requieren anonimización previa.

#### Instrucciones

1. Abre `P5_Nomina_Simulada.xlsx` (ingresa la contraseña `Cifrado#Nomina2024` cuando se solicite).

2. Crea una nueva hoja llamada `Matriz_Clasificacion`. Para crear la hoja: clic derecho en cualquier pestaña → **Insertar** → **Hoja de cálculo** → renombrar.

3. Abre el panel de Copilot en Excel y escribe:

   ```
   Necesito crear una Matriz de Clasificación de Datos de Nómina completa. 
   Genera una tabla con los siguientes tipos de datos que típicamente aparecen 
   en sistemas de nómina mexicanos: RFC, CURP, NSS, Nombre completo, 
   Fecha de nacimiento, Domicilio, Teléfono personal, Correo electrónico personal, 
   Salario bruto, Salario neto, Deducciones IMSS, Deducciones ISR, 
   Crédito Infonavit, Cuenta bancaria, CLABE interbancaria, Nivel de puesto, 
   Departamento, Fecha de ingreso, Historial de aumentos salariales, 
   Bonos y comisiones, Datos de incapacidades, Faltas y retardos.
   
   Para cada tipo de dato, incluye las siguientes columnas:
   - Tipo de Dato
   - Categoría LFPDPPP (Dato Personal / Dato Personal Sensible / Dato Financiero)
   - Nivel de Sensibilidad (Alto / Medio / Bajo)
   - ¿Puede usarse directamente con Copilot? (Sí / No / Solo anonimizado)
   - Método de Anonimización Recomendado
   - Fundamento Legal
   - Tiempo Máximo de Retención Recomendado
   ```

4. Copilot generará la tabla. Haz clic en **"Insertar en hoja"** o copia y pega el resultado en la hoja `Matriz_Clasificacion`.

5. Formatea la tabla aplicando los siguientes colores de fondo según el nivel de sensibilidad:
   - **Alto** → Rojo claro (`#FFB3B3`)
   - **Medio** → Amarillo claro (`#FFFACD`)
   - **Bajo** → Verde claro (`#B3FFB3`)

   Para aplicar el formato: selecciona las celdas de cada nivel → **Inicio → Color de relleno → Más colores → Personalizado** → ingresa el código hexadecimal.

6. Agrega una fila de encabezado con fondo gris oscuro y texto blanco en negrita.

7. En el panel de Copilot, escribe un prompt adicional:

   ```
   ¿Cuál es la diferencia legal entre "dato personal" y "dato personal sensible" 
   según la LFPDPPP? ¿Por qué los datos financieros como salarios y cuentas 
   bancarias merecen un tratamiento especialmente cuidadoso incluso si técnicamente 
   no son "datos sensibles" bajo la ley? Responde en máximo 150 palabras.
   ```

8. Agrega esta explicación como una nota al pie de la hoja `Matriz_Clasificacion` (en las filas debajo de la tabla, con fondo gris claro y texto en cursiva).

9. Guarda el archivo.

#### Resultado Esperado

La hoja `Matriz_Clasificacion` debe mostrar:
- Una tabla con al menos 20 tipos de datos de nómina clasificados
- Código de colores aplicado consistentemente (rojo/amarillo/verde)
- La nota explicativa sobre datos personales vs. datos personales sensibles
- Al menos 8 tipos de datos marcados como "No" o "Solo anonimizado" para uso con Copilot

#### Verificación

- [ ] La hoja `Matriz_Clasificacion` existe y contiene la tabla completa.
- [ ] El código de colores está aplicado correctamente.
- [ ] La columna "¿Puede usarse directamente con Copilot?" tiene valores diferenciados.
- [ ] La nota explicativa está presente al pie de la tabla.

---

### Paso 7: Diseño del Protocolo de Anonimización con Copilot

**Objetivo:** Usar Copilot para diseñar un protocolo práctico de anonimización de datos de nómina que permita usar la IA de manera segura sin comprometer la privacidad de los empleados.

#### Instrucciones

1. Abre `P5_Nomina_Simulada.xlsx` y navega a la hoja `Nómina_Junio`.

2. Crea una copia de la hoja: clic derecho en la pestaña → **Mover o copiar** → marca "Crear una copia" → ubícala al final → renómbrala `Nomina_Anonimizada`.

3. En la hoja `Nomina_Anonimizada`, aplica las siguientes técnicas de anonimización manualmente en las primeras 5 filas de datos (como ejercicio demostrativo):

   **Técnicas a aplicar:**
   - **RFC y CURP:** Reemplaza con `RFC-ANON-001`, `RFC-ANON-002`, etc. (seudonimización)
   - **Nombre_Completo:** Reemplaza con `Empleado_001`, `Empleado_002`, etc.
   - **NSS:** Reemplaza con `NSS-***-***` (enmascaramiento)
   - **Cuenta_Bancaria y CLABE:** Reemplaza con `XXXX-XXXX-XXXX-[últimos 4 dígitos ficticios]`
   - **Salario_Mensual_Bruto:** Redondea al múltiplo de $5,000 más cercano (generalización)
   - **Departamento y Nivel_Puesto:** Mantén sin cambios (no son datos sensibles individuales)

4. Una vez aplicadas las técnicas, abre el panel de Copilot y escribe:

   ```
   Observa la hoja "Nomina_Anonimizada" de este archivo. He aplicado técnicas 
   básicas de anonimización a los datos de nómina. Por favor:
   
   1. Evalúa si la anonimización aplicada es suficiente para usar estos datos 
      con herramientas de IA como Microsoft Copilot sin violar la LFPDPPP.
   
   2. Identifica si aún existen riesgos de re-identificación de los empleados 
      con los datos que permanecen visibles.
   
   3. Sugiere técnicas adicionales de anonimización que podrían aplicarse 
      (tokenización, perturbación de datos, k-anonimato, etc.) y explica 
      brevemente cada una.
   
   4. Diseña un procedimiento paso a paso de 6 etapas para que el equipo de 
      Compensaciones anonimice datos de nómina antes de cada sesión de trabajo 
      con Copilot.
   ```

5. Copia la respuesta de Copilot (específicamente el procedimiento de 6 etapas) en el documento `P5_Registro_Auditoria.docx`, en una nueva sección titulada **"Protocolo de Anonimización Pre-Copilot"**.

6. Guarda tanto el archivo Excel como el documento Word.

#### Resultado Esperado

- La hoja `Nomina_Anonimizada` contiene datos modificados con las 5 técnicas de anonimización aplicadas.
- Copilot identificó riesgos residuales de re-identificación (por ejemplo, la combinación de departamento + nivel + salario puede ser suficiente para identificar a una persona en organizaciones pequeñas).
- El protocolo de 6 etapas está documentado en `P5_Registro_Auditoria.docx`.

#### Verificación

- [ ] La hoja `Nomina_Anonimizada` no contiene ningún RFC, CURP, NSS ni cuenta bancaria en formato original.
- [ ] Copilot identificó al menos 1 riesgo residual de re-identificación.
- [ ] El protocolo de 6 etapas está en el documento de registro.

---

### Paso 8: Redacción de la Política de Uso Responsable de IA con Copilot en Word

**Objetivo:** Crear con asistencia de Copilot un documento formal de política que establezca las reglas de uso de IA en el área de compensaciones, incluyendo qué datos pueden procesarse y bajo qué condiciones.

#### Instrucciones

1. Abre la plantilla `P5_Plantilla_Politica_IA.docx` descargada al inicio de la práctica.

2. Activa Copilot en Word y escribe el siguiente prompt para generar el cuerpo principal de la política:

   ```
   Redacta una Política de Uso Responsable de Inteligencia Artificial para el 
   Área de Compensaciones y Nómina de una empresa mexicana mediana (500-1000 
   empleados). La política debe:
   
   ESTRUCTURA REQUERIDA:
   1. Objetivo y Alcance
   2. Marco Legal Aplicable (LFPDPPP, NOM-035, LFT, lineamientos IMSS/Infonavit)
   3. Clasificación de Datos por Nivel de Riesgo para uso con IA
      - Datos que PUEDEN usarse directamente con Copilot (con ejemplos)
      - Datos que REQUIEREN anonimización previa (con ejemplos y método)
      - Datos que NUNCA deben procesarse con herramientas de IA externas (con ejemplos)
   4. Procedimientos Obligatorios antes de usar Copilot con datos de nómina
   5. Responsabilidades (Gerente de RRHH, Analista de Nómina, Área de TI, DPO)
   6. Sanciones por incumplimiento (alineadas con la LFPDPPP)
   7. Vigencia y proceso de revisión anual
   
   TONO: Formal, claro y directo. Debe ser comprensible para profesionales de 
   RRHH sin formación legal especializada.
   EXTENSIÓN: Aproximadamente 800-1000 palabras.
   FECHA: Usar el año actual.
   ```

3. Revisa el borrador generado por Copilot. Identifica al menos **3 secciones que requieran ajuste** basándote en el contexto específico de tu organización o en la información analizada en los pasos anteriores.

4. Para cada sección que necesite ajuste, usa Copilot con prompts de refinamiento. Por ejemplo:

   ```
   Reescribe la sección "Sanciones por incumplimiento" siendo más específica 
   sobre los montos de multa que establece el Artículo 64 de la LFPDPPP 
   (entre 100 y 320,000 días de salario mínimo general vigente en la CDMX) 
   y añade que el incumplimiento también puede generar responsabilidad penal 
   según el Artículo 67 de la misma ley.
   ```

5. Una vez satisfecho con el contenido, aplica el siguiente formato al documento:
   - **Título:** Arial 18pt, negrita, centrado, color azul oscuro
   - **Encabezados de sección:** Arial 14pt, negrita, color gris oscuro
   - **Cuerpo de texto:** Calibri 11pt, justificado
   - **Pie de página:** Número de página, nombre del documento y "CONFIDENCIAL — Uso Interno"

6. Aplica la etiqueta de sensibilidad **Confidencial** al documento Word (Inicio → Sensibilidad).

7. Guarda el documento como `P5_Politica_Uso_IA_Compensaciones_v1.0.docx`.

8. Sube el documento a la carpeta de SharePoint **Módulo 5 → Políticas** y configura permisos de **Solo lectura** para todos los miembros del equipo (repite el procedimiento del Paso 4 para este archivo).

#### Resultado Esperado

El documento `P5_Politica_Uso_IA_Compensaciones_v1.0.docx` debe:
- Tener las 7 secciones requeridas, cada una con contenido sustantivo
- Mencionar explícitamente la LFPDPPP, NOM-035 y LFT
- Incluir la clasificación de tres categorías de datos (pueden usarse / requieren anonimización / nunca con IA externa)
- Estar formateado profesionalmente con la etiqueta de sensibilidad aplicada
- Estar disponible en SharePoint con permisos de solo lectura

#### Verificación

- [ ] El documento tiene las 7 secciones completas.
- [ ] La sección de sanciones menciona montos específicos de la LFPDPPP.
- [ ] La etiqueta de sensibilidad "Confidencial" es visible en el documento.
- [ ] El archivo está en SharePoint con permisos correctamente configurados.

---

## 7. Validación y Pruebas

Al concluir todos los pasos, realiza la siguiente validación integral:

### Lista de Verificación Final

| # | Entregable | Ubicación | Criterio de Éxito |
|---|---|---|---|
| 1 | `P5_Nomina_Simulada.xlsx` | `C:\CursoM365\Practica5\` + SharePoint | Tiene 4 hojas, etiqueta "Altamente Confidencial", hojas protegidas, cifrado activo |
| 2 | `P5_Bandas_Salariales.xlsx` | `C:\CursoM365\Practica5\` | Etiqueta "Confidencial" aplicada |
| 3 | `P5_Analisis_Legal_LFPDPPP.docx` | `C:\CursoM365\Practica5\` | 3 secciones: tabla LFPDPPP, NOM-035, 5 lineamientos |
| 4 | `P5_Registro_Auditoria.docx` | `C:\CursoM365\Practica5\` | Secciones: permisos SharePoint + protocolo anonimización |
| 5 | `P5_Politica_Uso_IA_Compensaciones_v1.0.docx` | SharePoint → Módulo 5 → Políticas | 7 secciones, formato profesional, etiqueta de sensibilidad, permisos correctos |

### Prueba de Escenario de Seguridad

Realiza esta prueba final para validar que los controles implementados funcionan correctamente:

1. **Prueba de acceso no autorizado a SharePoint:** Pide a un compañero de curso que intente acceder al archivo `P5_Nomina_Simulada.xlsx` en SharePoint desde su cuenta. Debe recibir un mensaje de acceso denegado. ✅

2. **Prueba de cifrado de archivo:** Cierra y vuelve a abrir `P5_Nomina_Simulada.xlsx`. Debe solicitar la contraseña de cifrado antes de mostrar el contenido. ✅

3. **Prueba de protección de hoja:** Con el archivo abierto, intenta escribir en cualquier celda de la hoja `Nómina_Junio`. Debe mostrar el mensaje de protección. ✅

4. **Prueba de etiqueta de sensibilidad:** Intenta enviar el archivo `P5_Nomina_Simulada.xlsx` por correo electrónico a una dirección externa (fuera del dominio corporativo). Si las políticas de Purview están correctamente configuradas, el sistema debe bloquear o advertir sobre el envío. ✅

---

## 8. Solución de Problemas

### Problema 1: La etiqueta de sensibilidad no aparece en Excel o Word

**Síntomas:**
- El botón "Sensibilidad" no está visible en la cinta de opciones de Excel o Word.
- Al buscar la opción, no aparece ningún resultado relacionado con clasificación o etiquetas.
- El mensaje de error puede indicar: *"No se puede conectar al servicio de protección de información"*.

**Causa probable:**
El complemento de Microsoft Purview Information Protection no está instalado o habilitado en la aplicación de Office, o la licencia del usuario no incluye Azure Information Protection (AIP). También puede deberse a que el administrador del tenant no ha publicado las etiquetas de sensibilidad para el grupo de usuarios del curso.

**Solución:**
1. Verifica la licencia: en el portal de Microsoft 365 Admin Center, confirma que el usuario tiene asignada una licencia que incluya **Azure Information Protection Plan 1** o superior (incluida en Microsoft 365 E3/E5 y Business Premium).
2. Instala manualmente el complemento: ve a **Archivo → Opciones → Complementos → Complementos COM → Ir** y verifica que **Microsoft Azure Information Protection** esté marcado. Si no aparece, descarga el cliente de AIP desde [https://www.microsoft.com/download/details.aspx?id=53018](https://www.microsoft.com/download/details.aspx?id=53018).
3. Si el complemento está instalado pero las etiquetas no aparecen, el administrador debe verificar en el **Portal de Cumplimiento de Microsoft Purview** (compliance.microsoft.com) que las etiquetas están publicadas en una política que incluya al usuario afectado. El tiempo de propagación puede ser de hasta 24 horas.
4. Como solución temporal para continuar la práctica: usa la protección de contraseña de archivo (Paso 3) y documenta que la etiqueta de sensibilidad requiere configuración adicional del administrador.

---

### Problema 2: Copilot en Excel no analiza los datos correctamente o muestra respuestas genéricas

**Síntomas:**
- Copilot responde con información genérica sobre la LFPDPPP sin hacer referencia a las columnas específicas del archivo.
- El panel de Copilot muestra el mensaje: *"No puedo acceder a los datos de esta hoja"* o *"Necesito que el rango sea una tabla de Excel"*.
- Las respuestas no incluyen los nombres de columnas del archivo (`RFC`, `CURP`, `Salario_Mensual_Bruto`, etc.).

**Causa probable:**
Copilot en Excel requiere que los datos estén formateados como una **Tabla de Excel** (no solo como un rango de celdas) para poder analizarlos. Si los datos están en un rango sin formato de tabla, Copilot no puede "leer" las columnas y sus valores, y responde de manera genérica. Adicionalmente, si la hoja está protegida (como en el Paso 3), Copilot puede tener restricciones para leer los datos.

**Solución:**
1. Selecciona cualquier celda dentro del rango de datos en la hoja `Nómina_Junio`.
2. Ve a **Insertar → Tabla** (o presiona `Ctrl+T`).
3. Verifica que el rango sea correcto y que la opción **"La tabla tiene encabezados"** esté marcada.
4. Haz clic en **Aceptar**. Los datos ahora están formateados como Tabla de Excel.
5. Si la hoja está protegida, deberás desprotegerla temporalmente para el análisis con Copilot: clic derecho en la pestaña → **Desproteger hoja** → ingresa la contraseña `Nomina@2024Segura`. Realiza el análisis con Copilot y vuelve a proteger la hoja al terminar.
6. Si el problema persiste, verifica que el archivo no esté abierto en **Vista protegida** (puede ocurrir si fue descargado de SharePoint). Haz clic en **Habilitar edición** en la barra amarilla de advertencia.
7. Como alternativa, copia los datos a un archivo temporal sin protección, realiza el análisis con Copilot, documenta los resultados y luego elimina el archivo temporal.

---

## 9. Limpieza del Entorno

Al finalizar la práctica, realiza las siguientes acciones de limpieza para mantener el entorno ordenado y seguro:

### Archivos Locales

1. Verifica que todos los archivos de práctica están guardados en `C:\CursoM365\Practica5\` con sus versiones finales.
2. **No elimines** los archivos locales; serán necesarios para las Prácticas 6 y 7.
3. Si trabajaste en una computadora compartida o de laboratorio, mueve los archivos a tu **OneDrive corporativo** antes de cerrar sesión:
   - Abre el Explorador de archivos → navega a `C:\CursoM365\Practica5\`
   - Selecciona todos los archivos → clic derecho → **Copiar**
   - Navega a tu carpeta de OneDrive → crea una carpeta `CursoM365\Practica5\` → pega los archivos

### SharePoint

4. Verifica que los siguientes archivos están correctamente cargados en SharePoint con los permisos configurados:
   - `P5_Nomina_Simulada.xlsx` → Módulo 5 → Archivos de Práctica (permisos restringidos)
   - `P5_Politica_Uso_IA_Compensaciones_v1.0.docx` → Módulo 5 → Políticas (solo lectura)

5. **No elimines** los archivos de SharePoint; el instructor los revisará como parte de la evaluación.

### Cierre de Sesiones

6. Cierra todos los archivos de Excel y Word abiertos.
7. Cierra las pestañas del navegador relacionadas con SharePoint y el Portal de Cumplimiento de Microsoft Purview.
8. Si iniciaste sesiones en modo incógnito para pruebas de acceso, cierra esas ventanas y verifica que no quedaron sesiones activas de cuentas de prueba.

> 🔒 **Recordatorio de seguridad:** Las contraseñas utilizadas en esta práctica (`Nomina@2024Segura` y `Cifrado#Nomina2024`) son exclusivas para fines de aprendizaje. En un entorno de producción, **nunca** uses contraseñas predecibles, las compartas en documentos o las reutilices entre archivos.

---

## 10. Resumen y Recursos Adicionales

### Resumen de lo Aprendido

En esta práctica de 90 minutos aplicaste un proceso completo de auditoría y protección de datos de nómina usando Microsoft 365 Copilot y las herramientas de seguridad del ecosistema Microsoft 365:

| Sección | Actividad Realizada | Herramienta Principal |
|---|---|---|
| **5.1 — Auditoría** | Identificación de datos sensibles y evaluación de riesgo | Copilot en Excel |
| **5.1 — Clasificación** | Aplicación de etiquetas de sensibilidad (Purview) | Microsoft Purview |
| **5.1 — Protección** | Cifrado de archivos y protección de hojas Excel | Excel + Purview |
| **5.1 — Acceso** | Configuración de permisos granulares en SharePoint | SharePoint Online |
| **5.2 — Marco legal** | Análisis de LFPDPPP y NOM-035 con Copilot | Copilot en Word |
| **5.2 — Matriz** | Clasificación de datos por nivel de sensibilidad | Copilot en Excel |
| **5.2 — Anonimización** | Protocolo de anonimización pre-Copilot | Copilot en Excel |
| **5.2 — Política** | Redacción de política de uso responsable de IA | Copilot en Word |

### Conceptos Clave Reforzados

- El **filtro de tres preguntas** (¿Qué datos comparto? ¿Tengo autorización? ¿El resultado es seguro?) es la base de cualquier uso responsable de IA en compensaciones.
- La **LFPDPPP** establece obligaciones concretas sobre consentimiento, finalidad y transferencia de datos que aplican directamente al uso de herramientas de IA como Copilot.
- Las **etiquetas de sensibilidad de Microsoft Purview** activan controles técnicos automáticos (cifrado, restricción de compartición, auditoría) que van más allá de una simple clasificación visual.
- La **anonimización no es binaria**: existen diferentes técnicas (seudonimización, enmascaramiento, generalización, tokenización) con distintos niveles de protección y utilidad analítica.
- Una **política de uso de IA** es un documento vivo que debe revisarse al menos anualmente y actualizarse conforme evoluciona la tecnología y el marco regulatorio.

### Recursos Adicionales

| Recurso | URL | Relevancia |
|---|---|---|
| LFPDPPP — Texto completo | [diputados.gob.mx/LeyesBiblio/pdf/LFPDPPP.pdf](https://www.diputados.gob.mx/LeyesBiblio/pdf/LFPDPPP.pdf) | Marco legal principal de la práctica |
| Microsoft Purview — Etiquetas de sensibilidad (documentación) | [learn.microsoft.com/es-es/purview/sensitivity-labels](https://learn.microsoft.com/es-es/purview/sensitivity-labels) | Referencia técnica para configuración avanzada |
| Microsoft Copilot — Privacidad y seguridad de datos | [learn.microsoft.com/es-es/copilot/microsoft-365/microsoft-365-copilot-privacy](https://learn.microsoft.com/es-es/copilot/microsoft-365/microsoft-365-copilot-privacy) | Comprensión de cómo Copilot maneja los datos |
| INAI — Guía de datos personales en el ámbito laboral | [inai.org.mx](https://www.inai.org.mx/vut-web/faces/view/consultaPublica.xhtml) | Orientación regulatoria para RH |
| ISO/IEC 27001 — Gestión de seguridad de la información | [iso.org/isoiec-27001-information-security.html](https://www.iso.org/isoiec-27001-information-security.html) | Estándar internacional complementario |
| NOM-035-STPS-2018 — Texto oficial | [dof.gob.mx](https://www.dof.gob.mx/nota_detalle.php?codigo=5541828&fecha=23/10/2018) | Marco normativo de bienestar laboral |

### Conexión con la Siguiente Práctica

Los archivos y políticas creados en esta práctica serán utilizados en la **Práctica 6**, donde diseñarás flujos de trabajo automatizados en Power Automate que integren los controles de seguridad implementados hoy con los procesos de aprobación de nómina. Asegúrate de tener todos los archivos disponibles en OneDrive o SharePoint antes de la siguiente sesión.

---

> 📝 **Nota final del instructor:** Al revisar los entregables de los participantes, verifique especialmente que: (1) ningún archivo contiene datos reales de empleados, (2) las etiquetas de sensibilidad están correctamente aplicadas (no solo visualmente sino con protección activa), y (3) las políticas redactadas con Copilot fueron revisadas y ajustadas por el participante (no copiadas directamente sin revisión crítica). La capacidad de evaluar y refinar el output de Copilot es una competencia central de este curso.
