# Práctica 8 — Simulación de un Agente Interconectado para Auditorías de Pago

## Metadatos

| Campo | Detalle |
|---|---|
| **Duración estimada** | 90 minutos |
| **Complejidad** | Alta |
| **Nivel Bloom** | Crear |
| **Módulo** | Capítulo 8 — Colaboración e Interconexión de Agentes |
| **Práctica número** | 8 de 8 |
| **Última actualización** | 2025 |

---

## Descripción General

Esta práctica final integra todas las competencias desarrolladas a lo largo del curso en la construcción de un **ecosistema de agentes de IA interconectados** para compensaciones. El participante partirá del agente de nómina creado en la Práctica 7 y construirá un segundo agente especializado en auditorías de pago en Microsoft Copilot Studio, configurando la comunicación bidireccional entre ambos mediante mecanismos de redirección de tópicos y flujos de Power Automate compartidos. La práctica culmina con la demostración completa del ecosistema funcionando en Microsoft Teams, donde el agente de auditoría detecta discrepancias, escala alertas y genera un reporte ejecutivo automatizado que se distribuye por Outlook a la dirección.

> ⚠️ **Aviso de cumplimiento:** Todos los datos utilizados en esta práctica son **estrictamente ficticios**. Está prohibido usar datos reales de empleados conforme a la Ley Federal de Protección de Datos Personales en Posesión de los Particulares (LFPDPPP).

---

## Objetivos de Aprendizaje

Al finalizar esta práctica, el participante será capaz de:

- [ ] **Diseñar e implementar** un agente de auditoría de pagos en Copilot Studio que se interconecte con el agente de nómina de la Práctica 7, utilizando el mecanismo de *Redirect to another topic* y flujos de Power Automate compartidos.
- [ ] **Configurar flujos de sincronización** de datos multi-área (Compensaciones, Finanzas, Contabilidad, Dirección General) en Power Automate para garantizar información actualizada en tiempo real.
- [ ] **Simular un escenario de auditoría end-to-end** donde el agente detecta discrepancias automáticamente, genera alertas, escala al responsable correcto y documenta el hallazgo en SharePoint.
- [ ] **Construir un flujo de reporte ejecutivo automatizado** que consolide KPIs de nómina mediante Power Automate y Word con Copilot, distribuyéndolo automáticamente por Outlook.
- [ ] **Demostrar el ecosistema de agentes** funcionando de forma integrada en Microsoft Teams ante el grupo.

---

## Prerrequisitos

### Conocimientos Previos

| Área | Nivel Requerido |
|---|---|
| Microsoft Copilot Studio (creación de agentes, tópicos, entidades) | Intermedio — completado en Práctica 7 |
| Microsoft Power Automate (flujos de múltiples pasos) | Intermedio — completado en Prácticas 4 y 7 |
| Microsoft SharePoint Online (listas y bibliotecas de documentos) | Básico — completado en Prácticas 3 y 5 |
| Microsoft Excel (tablas y rangos nombrados) | Básico — completado en Prácticas 1 y 2 |
| Microsoft Word con Copilot (generación de documentos) | Básico — completado en Práctica 6 |
| Conceptos de interconexión de agentes (Capítulo 8, Lección 8.1) | Requerido — lección previa |

### Accesos y Recursos Necesarios

| Recurso | Estado Requerido |
|---|---|
| Licencia activa de Microsoft 365 Copilot (Apps for Enterprise) | ✅ Activa y verificada |
| Acceso a Copilot Studio (`copilotstudio.microsoft.com`) | ✅ Habilitado por el administrador del tenant |
| Rol de **Maker** en el entorno de Power Platform del curso | ✅ Asignado por el administrador |
| Agente de nómina funcional de la Práctica 7 | ✅ Publicado y probado |
| Acceso al sitio de SharePoint del curso con permisos de contribuidor | ✅ Configurado por el instructor |
| Archivos de práctica distribuidos por el instructor | ✅ Descargados en equipo local |

### Archivos de Práctica Requeridos

El instructor debe haber distribuido los siguientes archivos antes de iniciar:

| Archivo | Descripción |
|---|---|
| `P8_Dataset_Auditoria_Pagos.xlsx` | Dataset con 50 registros ficticios de nómina con discrepancias simuladas |
| `P8_Presupuesto_Nomina_Departamentos.xlsx` | Datos de presupuesto aprobado vs. ejercido por departamento (ficticios) |
| `P8_Plantilla_Reporte_Ejecutivo.docx` | Plantilla Word con secciones predefinidas para el reporte ejecutivo |
| `P8_Datos_Contabilidad_Provisiones.xlsx` | Provisiones contables de nómina ficticias por quincena |

---

## Entorno de Laboratorio

### Requisitos de Hardware

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8ª gen / AMD Ryzen 5 | Intel Core i7 10ª gen o superior |
| RAM | 8 GB | 16 GB (múltiples aplicaciones simultáneas) |
| Almacenamiento disponible | 10 GB | 20 GB |
| Resolución de pantalla | 1366×768 | 1920×1080 |
| Conexión a internet | 10 Mbps | 25 Mbps |

### Requisitos de Software

| Aplicación | Versión Mínima | URL de Acceso |
|---|---|---|
| Microsoft Copilot Studio | Versión actual | `https://copilotstudio.microsoft.com` |
| Microsoft Power Automate | Versión actual | `https://make.powerautomate.com` |
| Microsoft Excel (M365) | 2308 o superior | Aplicación de escritorio o web |
| Microsoft Word (M365) | 2308 o superior | Aplicación de escritorio o web |
| Microsoft Teams | Versión actual | Aplicación de escritorio |
| Microsoft SharePoint Online | Versión actual | URL del sitio del curso |
| Microsoft Outlook (M365) | Versión actual | Aplicación de escritorio o web |
| Navegador web | Edge 120+ / Chrome 120+ | — |

### Configuración Previa al Inicio

Antes de comenzar los pasos del laboratorio, ejecuta las siguientes verificaciones:

**1. Verificar acceso a Copilot Studio y el agente de la Práctica 7:**
```
1. Navega a https://copilotstudio.microsoft.com
2. Selecciona el entorno del curso (esquina superior derecha)
3. Confirma que el agente "Agente Nómina MX - [TuNombre]" aparece en la lista
4. Verifica que su estado sea "Publicado"
```

**2. Verificar acceso al sitio de SharePoint del curso:**
```
1. Navega al sitio SharePoint proporcionado por el instructor
2. Confirma que puedes ver la biblioteca "Práctica 8 - Auditoría"
3. Verifica que tienes permisos de contribuidor (botón "Nuevo" visible)
```

**3. Cargar los archivos de práctica a SharePoint:**
```
1. En la biblioteca "Práctica 8 - Auditoría" de SharePoint
2. Sube los cuatro archivos de práctica (.xlsx y .docx)
3. Confirma que los archivos son visibles y accesibles
```

---

## Pasos del Laboratorio

---

### Sección 8.1: Creación del Agente de Auditoría de Pagos

---

#### Paso 1: Crear el Nuevo Agente de Auditoría en Copilot Studio

**Objetivo:** Crear la estructura base del agente especializado en auditorías de pago, configurando su identidad, instrucciones y fuente de conocimiento inicial.

**Instrucciones:**

1. Navega a `https://copilotstudio.microsoft.com` e inicia sesión con tu cuenta corporativa.

2. Asegúrate de que el **entorno del curso** esté seleccionado en el selector de entornos (esquina superior derecha). Si ves "Predeterminado (org)", cambia al entorno creado por el administrador para el curso.

3. En el panel izquierdo, haz clic en **Crear** y selecciona **Nuevo agente**.

4. En la pantalla de creación, selecciona **Omitir para configurar** (para configuración manual detallada).

5. En el campo **Nombre**, escribe exactamente:
   ```
   Agente Auditoría Pagos MX - [TuNombre]
   ```
   *(Reemplaza `[TuNombre]` con tus iniciales o nombre para identificación en el entorno compartido)*

6. En el campo **Descripción**, escribe:
   ```
   Agente especializado en auditoría de pagos de nómina para empresas mexicanas.
   Detecta discrepancias, genera alertas y documenta hallazgos conforme a la LFT,
   IMSS e Infonavit. Se interconecta con el Agente de Nómina para consultas cruzadas.
   ```

7. En el campo **Instrucciones** (sección de configuración del agente), escribe las siguientes instrucciones del sistema:
   ```
   Eres un agente especializado en auditoría de pagos de nómina en México.
   Tu función principal es:
   1. Detectar discrepancias entre los pagos calculados y los pagos realizados.
   2. Identificar inconsistencias con las obligaciones del IMSS, Infonavit y SAT.
   3. Generar alertas cuando una variación supera el umbral permitido (5% por defecto).
   4. Escalar hallazgos críticos al responsable de Compensaciones.
   5. Documentar cada hallazgo con: fecha, empleado (ID ficticio), tipo de discrepancia,
      monto, severidad (Alta/Media/Baja) y acción recomendada.
   Siempre solicita el número de quincena o período antes de iniciar una auditoría.
   Responde siempre en español formal. Nunca reveles datos personales reales.
   ```

8. En la sección **Conocimiento**, haz clic en **Agregar conocimiento** y selecciona **Archivos**.

9. Carga el archivo `P8_Dataset_Auditoria_Pagos.xlsx` desde tu equipo local. Espera a que el procesamiento concluya (indicador verde ✅).

10. Haz clic en **Crear** para finalizar la creación del agente.

**Resultado Esperado:**
El agente "Agente Auditoría Pagos MX - [TuNombre]" aparece en el panel principal de Copilot Studio con estado "Listo para pruebas". El ícono del agente muestra un escudo o ícono de auditoría.

**Verificación:**
- [ ] El agente aparece en la lista con el nombre correcto.
- [ ] La descripción e instrucciones son visibles en la pestaña **Configuración > Detalles**.
- [ ] El archivo de dataset aparece en la sección **Conocimiento** con estado procesado.

---

#### Paso 2: Crear el Tópico Principal de Auditoría de Pagos

**Objetivo:** Diseñar el flujo conversacional principal del agente para iniciar y ejecutar una auditoría de pagos por período.

**Instrucciones:**

1. Dentro del agente "Agente Auditoría Pagos MX", navega a la pestaña **Tópicos** en el panel izquierdo.

2. Haz clic en **Agregar tópico** → **Desde cero**.

3. Configura el tópico con los siguientes datos:
   - **Nombre del tópico:** `Iniciar Auditoría de Pagos`
   - **Frases de activación (Trigger phrases):** Agrega las siguientes cinco frases, una por una:
     ```
     iniciar auditoría
     auditar pagos
     revisar nómina del período
     detectar discrepancias
     verificar pagos quincenales
     ```

4. En el lienzo del tópico, el primer nodo debe ser el de **Mensaje**. Edita el mensaje de bienvenida:
   ```
   Hola, soy el Agente de Auditoría de Pagos. Estoy aquí para ayudarte a verificar
   la integridad de los pagos de nómina y detectar posibles discrepancias.
   
   Para comenzar la auditoría, necesito algunos datos.
   ```

5. Agrega un nodo de **Pregunta** después del mensaje de bienvenida:
   - **Texto de la pregunta:**
     ```
     ¿Qué período deseas auditar? Por favor indica el número de quincena
     y el año (ejemplo: Q1-2025, Q2-2025).
     ```
   - **Identificar como:** Selecciona **Respuesta completa del usuario**
   - **Guardar respuesta en variable:** Nombra la variable `varPeriodoAuditoria`

6. Agrega un segundo nodo de **Pregunta**:
   - **Texto:**
     ```
     ¿Deseas auditar un departamento específico o toda la organización?
     ```
   - **Tipo de respuesta:** Selecciona **Opciones múltiples** y agrega:
     - `Departamento específico`
     - `Toda la organización`
   - **Guardar en variable:** `varAlcanceAuditoria`

7. Agrega un nodo de **Condición** para bifurcar el flujo:
   - **Condición 1:** `varAlcanceAuditoria` es igual a `Departamento específico`
     - Agrega un nodo de **Pregunta** adicional:
       ```
       Indica el nombre o código del departamento a auditar:
       ```
       - Guardar en variable: `varDepartamento`
   - **Condición 2 (Else):** Asigna `varDepartamento` = `TODOS`

8. Después de ambas ramas de la condición, agrega un nodo de **Mensaje**:
   ```
   Perfecto. Iniciando auditoría del período {varPeriodoAuditoria} 
   para: {varDepartamento}.
   
   Consultando el dataset de pagos... Por favor espera un momento.
   ```

9. Agrega un nodo de **Llamar a una acción** → **Crear un flujo de Power Automate**. Esto abrirá Power Automate en una nueva pestaña — **no cierres esta pestaña de Copilot Studio**.

   > 📝 **Nota:** El flujo de Power Automate se construirá en el Paso 3. Por ahora, solo deja este nodo como marcador de posición y continúa con el mensaje de cierre temporal.

10. Agrega un nodo de **Mensaje** final temporal:
    ```
    El análisis ha sido completado. Los resultados se mostrarán una vez que 
    el flujo de auditoría esté conectado en el siguiente paso.
    ```

11. Haz clic en **Guardar** (ícono de disco o Ctrl+S).

**Resultado Esperado:**
El tópico "Iniciar Auditoría de Pagos" muestra un flujo conversacional completo con nodos de pregunta, condición y mensaje. El lienzo visual muestra el árbol de decisión correctamente conectado.

**Verificación:**
- [ ] Las 5 frases de activación están configuradas.
- [ ] Las variables `varPeriodoAuditoria`, `varAlcanceAuditoria` y `varDepartamento` aparecen en el panel de variables del tópico.
- [ ] El flujo no muestra errores de validación (sin íconos rojos ⚠️).

---

#### Paso 3: Construir el Flujo de Auditoría en Power Automate

**Objetivo:** Crear el flujo de Power Automate que procesa el dataset de auditoría, detecta discrepancias y registra hallazgos en SharePoint.

**Instrucciones:**

1. Navega a `https://make.powerautomate.com` en una nueva pestaña del navegador.

2. Selecciona el mismo **entorno del curso** en el selector de entornos.

3. En el panel izquierdo, haz clic en **Crear** → **Flujo de nube instantáneo**.

4. Configura el flujo:
   - **Nombre:** `PA_P8_Auditoria_Discrepancias`
   - **Desencadenador:** Selecciona **Cuando Copilot Studio llama a un flujo** (PowerApps V2 o el conector de Copilot Studio disponible en tu entorno)

5. Configura las **entradas del desencadenador** (parámetros que recibirá desde el agente):
   - Agrega entrada de tipo **Texto**, nombre: `PeriodoAuditoria`
   - Agrega entrada de tipo **Texto**, nombre: `Departamento`

6. Agrega la acción **Excel Online (Business) — Obtener una tabla**:
   - **Ubicación:** SharePoint
   - **Biblioteca de documentos:** Selecciona la biblioteca "Práctica 8 - Auditoría"
   - **Archivo:** `P8_Dataset_Auditoria_Pagos.xlsx`
   - **Tabla:** `TablaAuditoria` *(el instructor habrá preconfigurado esta tabla nombrada en el archivo)*

7. Agrega la acción **Excel Online (Business) — Enumerar filas presentes en una tabla**:
   - Usa la misma configuración de archivo y tabla del paso anterior.
   - En **Filtrar consulta**, escribe:
     ```
     Periodo eq '@{triggerBody()?['text']}'
     ```
     > 📝 Haz clic en el campo y usa la expresión dinámica para referenciar la entrada `PeriodoAuditoria`.

8. Agrega una acción **Aplicar a cada uno** sobre el resultado de la enumeración de filas:

   Dentro del bucle **Aplicar a cada uno**, agrega una **Condición** para detectar discrepancias:
   - **Condición:** `Columna: VariacionPorcentual` es **mayor que** `5`
   
   **Rama SÍ (discrepancia detectada):**
   
   a. Agrega la acción **SharePoint — Crear elemento** para registrar el hallazgo:
      - **Dirección del sitio:** URL del sitio SharePoint del curso
      - **Nombre de lista:** `Hallazgos de Auditoría` *(el instructor habrá creado esta lista)*
      - Mapea los campos:
        ```
        Title          → "Discrepancia - " + ID_Empleado (dinámico)
        Periodo        → PeriodoAuditoria (entrada del flujo)
        ID_Empleado    → Columna ID_Empleado (dinámico del bucle)
        Departamento   → Columna Departamento (dinámico)
        TipoDiscrepancia → Columna TipoDiscrepancia (dinámico)
        MontoDiscrepancia → Columna VariacionMonto (dinámico)
        Severidad      → Columna Severidad (dinámico)
        FechaDeteccion → utcNow() [expresión]
        Estado         → "Nuevo"
        ```
   
   b. Agrega la acción **Office 365 Outlook — Enviar un correo electrónico (V2)**:
      - **Para:** Correo del responsable de Compensaciones (usa el correo del instructor o un correo de prueba)
      - **Asunto:**
        ```
        ⚠️ ALERTA DE AUDITORÍA: Discrepancia detectada en @{items('Aplicar_a_cada_uno')?['ID_Empleado']} - @{triggerBody()?['text_1']}
        ```
      - **Cuerpo:**
        ```html
        <p>Se ha detectado una discrepancia en la auditoría de nómina.</p>
        <table border="1">
          <tr><td><b>Período:</b></td><td>@{triggerBody()?['text_1']}</td></tr>
          <tr><td><b>ID Empleado:</b></td><td>@{items('Aplicar_a_cada_uno')?['ID_Empleado']}</td></tr>
          <tr><td><b>Departamento:</b></td><td>@{items('Aplicar_a_cada_uno')?['Departamento']}</td></tr>
          <tr><td><b>Tipo:</b></td><td>@{items('Aplicar_a_cada_uno')?['TipoDiscrepancia']}</td></tr>
          <tr><td><b>Monto Variación:</b></td><td>$@{items('Aplicar_a_cada_uno')?['VariacionMonto']}</td></tr>
          <tr><td><b>Severidad:</b></td><td>@{items('Aplicar_a_cada_uno')?['Severidad']}</td></tr>
        </table>
        <p>Por favor revisa el hallazgo en SharePoint y toma la acción correspondiente.</p>
        ```

9. **Fuera del bucle**, agrega la acción **Inicializar variable** (antes del bucle, al inicio del flujo después del desencadenador):
   - **Nombre:** `ConteoDiscrepancias`
   - **Tipo:** Entero
   - **Valor:** `0`
   
   Dentro del bucle, en la **Rama SÍ**, agrega también la acción **Incrementar variable**:
   - **Nombre:** `ConteoDiscrepancias`
   - **Valor:** `1`

10. Al final del flujo (fuera del bucle), agrega la acción **Responder a Copilot Studio** (o **Devolver valor(es) a Power Virtual Agents**):
    - Agrega una salida de tipo **Texto**, nombre: `ResumenAuditoria`
    - **Valor:**
      ```
      Auditoría del período @{triggerBody()?['text_1']} completada. 
      Se detectaron @{variables('ConteoDiscrepancias')} discrepancias. 
      Los hallazgos han sido registrados en SharePoint y se han enviado alertas al responsable.
      ```

11. Haz clic en **Guardar** y espera confirmación. Luego haz clic en **Publicar**.

12. Regresa a la pestaña de Copilot Studio.

**Resultado Esperado:**
El flujo `PA_P8_Auditoria_Discrepancias` aparece como publicado en Power Automate. El flujo tiene un desencadenador de Copilot Studio, procesa filas de Excel, crea elementos en SharePoint y envía correos de alerta.

**Verificación:**
- [ ] El flujo no muestra errores en el panel de validación de Power Automate.
- [ ] El flujo aparece en la lista de flujos con estado "Activado".
- [ ] La acción de respuesta a Copilot Studio está configurada con la salida `ResumenAuditoria`.

---

#### Paso 4: Conectar el Flujo al Agente de Auditoría

**Objetivo:** Vincular el flujo de Power Automate al tópico del agente y mostrar el resumen de auditoría al usuario.

**Instrucciones:**

1. Regresa a la pestaña de Copilot Studio con el agente "Agente Auditoría Pagos MX".

2. Abre el tópico **Iniciar Auditoría de Pagos**.

3. Localiza el nodo de **Llamar a una acción** que dejaste como marcador de posición en el Paso 2.

4. Haz clic en ese nodo y selecciona **Seleccionar acción existente**. En la lista de flujos disponibles, selecciona `PA_P8_Auditoria_Discrepancias`.

5. Mapea las entradas del flujo con las variables del agente:
   - **PeriodoAuditoria** → Variable: `varPeriodoAuditoria`
   - **Departamento** → Variable: `varDepartamento`

6. El flujo devolverá la variable de salida `ResumenAuditoria`. Asegúrate de que esté mapeada a una variable del agente: `varResumenAuditoria`.

7. Elimina el nodo de **Mensaje** temporal que creaste al final del Paso 2 (el que decía "El análisis ha sido completado...").

8. Agrega un nuevo nodo de **Mensaje** después de la llamada al flujo:
   ```
   ✅ Auditoría completada.
   
   {varResumenAuditoria}
   
   ¿Deseas que escale esta información al Agente de Nómina para verificar 
   los cálculos originales de las discrepancias detectadas?
   ```

9. Agrega un nodo de **Pregunta** con opciones:
   - **Texto:** `¿Escalamos al Agente de Nómina?`
   - **Opciones:**
     - `Sí, escalar al Agente de Nómina`
     - `No, finalizar aquí`
   - **Guardar en:** `varEscalar`

10. Agrega un nodo de **Condición**:
    - **Si** `varEscalar` es igual a `Sí, escalar al Agente de Nómina`:
      - Agrega un nodo de **Redirigir a otro tópico** → selecciona **Ir a otro agente** (si está disponible en tu versión) o configura un mensaje de transferencia:
        ```
        Transfiriendo tu consulta al Agente de Nómina para verificación detallada.
        Por favor espera...
        ```
        > 📝 **Nota técnica:** La función "Ir a otro agente" requiere que ambos agentes estén en el mismo entorno y publicados. Si esta opción no está disponible en tu versión de Copilot Studio, usa el mensaje de transferencia y continúa con el Paso 5 donde se configurará la interconexión alternativa.
    - **Else:** Agrega un nodo de **Mensaje**:
      ```
      Entendido. La auditoría ha concluido. Los hallazgos están documentados 
      en SharePoint. ¿Hay algo más en lo que pueda ayudarte?
      ```

11. Haz clic en **Guardar**.

**Resultado Esperado:**
El tópico "Iniciar Auditoría de Pagos" ahora muestra el flujo completo: captura de datos → llamada a Power Automate → presentación de resultados → opción de escalamiento. El nodo de llamada al flujo muestra el nombre `PA_P8_Auditoria_Discrepancias` correctamente vinculado.

**Verificación:**
- [ ] El nodo de llamada al flujo muestra las entradas y salidas mapeadas correctamente.
- [ ] No hay íconos de error ⚠️ en el lienzo del tópico.
- [ ] La variable `varResumenAuditoria` aparece en el panel de variables.

---

### Sección 8.2: Interconexión con el Agente de Nómina (Práctica 7)

---

#### Paso 5: Configurar la Interconexión entre Agentes

**Objetivo:** Establecer el mecanismo de comunicación entre el Agente de Auditoría y el Agente de Nómina de la Práctica 7, permitiendo que consultas complejas sean atendidas por el agente más especializado.

**Instrucciones:**

1. Abre el agente **"Agente Nómina MX - [TuNombre]"** creado en la Práctica 7 en Copilot Studio.

2. Navega a la pestaña **Tópicos** y haz clic en **Agregar tópico** → **Desde cero**.

3. Nombra el nuevo tópico: `Recibir Escalamiento de Auditoría`

4. Agrega las siguientes **frases de activación**:
   ```
   verificar cálculo de discrepancia
   escalamiento de auditoría
   revisar nómina por discrepancia
   validar pago cuestionado
   ```

5. Agrega un nodo de **Mensaje**:
   ```
   He recibido el escalamiento del Agente de Auditoría. 
   Procederé a verificar los cálculos originales de nómina para las 
   discrepancias identificadas.
   ```

6. Agrega un nodo de **Pregunta**:
   - **Texto:**
     ```
     ¿Cuál es el ID del empleado cuyo pago deseas verificar?
     (Este dato proviene del reporte de auditoría)
     ```
   - **Guardar en:** `varIDEmpleadoVerificar`

7. Agrega un nodo de **Llamar a una acción** → Selecciona el flujo de nómina creado en la Práctica 7 (si existe) o crea un nodo de **Respuesta generativa** con el siguiente prompt:
   ```
   Usando el conocimiento disponible del dataset de nómina, proporciona 
   el detalle del cálculo de pago para el empleado con ID {varIDEmpleadoVerificar}, 
   incluyendo: salario base, deducciones IMSS, Infonavit, ISR, percepciones 
   adicionales y neto a pagar. Indica si el cálculo es conforme a la LFT vigente.
   ```

8. Agrega un nodo de **Mensaje** final:
   ```
   Verificación completada. El detalle del cálculo ha sido generado.
   
   ¿Deseas que registre este resultado de verificación en el expediente 
   de auditoría en SharePoint?
   ```

9. Agrega un nodo de **Pregunta** con opciones Sí/No y guarda en `varRegistrarVerificacion`.

10. Para la rama **Sí**, agrega una acción de **Llamar a un flujo** — crea un flujo simple en Power Automate llamado `PA_P8_Registrar_Verificacion` que:
    - Reciba como entrada: `IDEmpleado` (texto), `ResultadoVerificacion` (texto)
    - Actualice el elemento correspondiente en la lista de SharePoint "Hallazgos de Auditoría" cambiando el campo `Estado` de "Nuevo" a "Verificado por Agente Nómina"
    - Responda con confirmación de texto: `"Registro actualizado correctamente"`

    > 📝 **Instrucciones del flujo simplificadas:**
    > En Power Automate, crea el flujo con desencadenador de Copilot Studio, agrega la acción **SharePoint — Obtener elementos** filtrando por `ID_Empleado eq '@{triggerBody()...}'`, luego **SharePoint — Actualizar elemento** con `Estado = "Verificado por Agente Nómina"`, y finalmente la acción de respuesta.

11. Guarda el tópico en el Agente de Nómina.

12. **Regresa al Agente de Auditoría** y actualiza el nodo de transferencia del Paso 4:
    - En el mensaje de transferencia, agrega instrucciones claras para que el usuario copie el ID del empleado y lo use en el Agente de Nómina.
    - Agrega un hipervínculo o instrucción para abrir el Agente de Nómina en Teams:
      ```
      Para continuar la verificación, abre el chat con "Agente Nómina MX" 
      en Teams y escribe: "verificar cálculo de discrepancia" seguido del 
      ID del empleado que aparece en el reporte.
      ```

13. Guarda todos los cambios en ambos agentes.

**Resultado Esperado:**
El Agente de Nómina tiene un nuevo tópico "Recibir Escalamiento de Auditoría" que puede recibir consultas provenientes del flujo de auditoría. Ambos agentes están configurados para trabajar en coordinación, con el flujo `PA_P8_Registrar_Verificacion` actualizando el estado de los hallazgos en SharePoint.

**Verificación:**
- [ ] El tópico "Recibir Escalamiento de Auditoría" aparece en el Agente de Nómina sin errores.
- [ ] El flujo `PA_P8_Registrar_Verificacion` está publicado y activo en Power Automate.
- [ ] La lista "Hallazgos de Auditoría" en SharePoint tiene el campo `Estado` disponible.

---

### Sección 8.3: Reporte Ejecutivo Automatizado

---

#### Paso 6: Construir el Flujo de Reporte Ejecutivo Quincena

**Objetivo:** Crear el flujo de Power Automate que consolida los KPIs de nómina y genera automáticamente un reporte ejecutivo en Word con Copilot, distribuyéndolo por Outlook.

**Instrucciones:**

1. En Power Automate (`make.powerautomate.com`), crea un nuevo flujo:
   - **Nombre:** `PA_P8_Reporte_Ejecutivo_Quincena`
   - **Desencadenador:** **Periodicidad** (Recurrence)
     - **Intervalo:** `1`
     - **Frecuencia:** `Semana`
     - **En estos días:** Selecciona el día que simula la quincena (para la práctica, usa el día actual)
     - **A las:** `08:00` (hora de México, UTC-6)

2. Agrega la acción **Excel Online (Business) — Ejecutar script** (o **Obtener una tabla** si no tienes acceso a scripts):
   - **Ubicación:** SharePoint
   - **Archivo:** `P8_Dataset_Auditoria_Pagos.xlsx`
   - **Tabla:** `TablaAuditoria`
   
   > Si usas **Enumerar filas**, deberás calcular los KPIs en pasos posteriores. Para simplificar, usa las siguientes variables inicializadas manualmente con valores del dataset:

3. Agrega las siguientes acciones **Inicializar variable** (una por una) para los KPIs del reporte:
   ```
   Variable: KPI_CostoTotal       | Tipo: Float  | Valor: 0
   Variable: KPI_Variacion        | Tipo: Float  | Valor: 0  
   Variable: KPI_NumDiscrepancias | Tipo: Entero | Valor: 0
   Variable: KPI_AlertasCriticas  | Tipo: Entero | Valor: 0
   Variable: KPI_Periodo          | Tipo: Texto  | Valor: [expresión formatDateTime(utcNow(),'Q-yyyy')]
   ```

4. Agrega la acción **Excel Online (Business) — Enumerar filas** para leer el archivo de presupuesto:
   - **Archivo:** `P8_Presupuesto_Nomina_Departamentos.xlsx`
   - **Tabla:** `TablPresupuesto`

5. Agrega un bloque **Aplicar a cada uno** sobre las filas del presupuesto:
   - Dentro del bucle, usa **Incrementar variable** para `KPI_CostoTotal` sumando el campo `CostoRealQuincena` de cada fila.

6. Agrega la acción **SharePoint — Obtener elementos** para leer los hallazgos de auditoría:
   - **Lista:** `Hallazgos de Auditoría`
   - **Filtro:** `Estado eq 'Nuevo'`

7. Agrega la acción **Establecer variable** para `KPI_NumDiscrepancias`:
   - **Valor:** `@{length(body('Obtener_elementos')?['value'])}`

8. Agrega la acción **Establecer variable** para `KPI_AlertasCriticas` filtrando por severidad Alta:
   - Usa una expresión:
     ```
     @{length(filter(body('Obtener_elementos')?['value'], item()?['Severidad'] == 'Alta'))}
     ```

9. Ahora genera el reporte en Word. Agrega la acción **SharePoint — Obtener contenido de archivo** para la plantilla:
   - **Archivo:** `P8_Plantilla_Reporte_Ejecutivo.docx`

10. Agrega la acción **Word Online (Business) — Convertir a PDF** o usa la acción **Crear archivo** para generar una copia de trabajo:
    - **Ubicación:** SharePoint, biblioteca "Práctica 8 - Auditoría"
    - **Nombre de archivo:**
      ```
      Reporte_Ejecutivo_Nomina_@{variables('KPI_Periodo')}.docx
      ```
    - **Contenido:** Contenido del archivo de plantilla

11. Agrega la acción **Word Online (Business) — Rellenar y firmar** (o usa la acción de **Actualizar un documento de Word**) para insertar los KPIs en los marcadores de posición de la plantilla:
    > 📝 La plantilla `P8_Plantilla_Reporte_Ejecutivo.docx` tiene marcadores predefinidos: `{{PERIODO}}`, `{{COSTO_TOTAL}}`, `{{VARIACION}}`, `{{NUM_DISCREPANCIAS}}`, `{{ALERTAS_CRITICAS}}`. Reemplaza cada uno con el valor de la variable correspondiente.

    Si tu entorno no tiene la acción de Word con marcadores, usa la siguiente alternativa con **Copilot en Power Automate (Preview)**:
    - Agrega la acción **Copilot — Resumir texto** o **Generar contenido con Copilot**:
      ```
      Genera un reporte ejecutivo de nómina con los siguientes datos:
      - Período: @{variables('KPI_Periodo')}
      - Costo Total de Nómina: $@{variables('KPI_CostoTotal')} MXN
      - Variación vs. Presupuesto: @{variables('KPI_Variacion')}%
      - Discrepancias Detectadas: @{variables('KPI_NumDiscrepancias')}
      - Alertas Críticas: @{variables('KPI_AlertasCriticas')}
      
      Formato ejecutivo, lenguaje formal, máximo 3 párrafos.
      Incluye recomendaciones de acción para la dirección.
      ```

12. Agrega la acción **Office 365 Outlook — Enviar un correo electrónico (V2)**:
    - **Para:** Lista de correos de prueba (máximo 10-15 cuentas de participantes del curso — **no usar listas reales de distribución**)
    - **Asunto:**
      ```
      📊 Reporte Ejecutivo de Nómina — @{variables('KPI_Periodo')} | [EMPRESA FICTICIA S.A. DE C.V.]
      ```
    - **Cuerpo:**
      ```html
      <h2>Reporte Ejecutivo de Nómina — @{variables('KPI_Periodo')}</h2>
      <p>Estimada Dirección General,</p>
      <p>A continuación se presenta el resumen consolidado de los indicadores de nómina 
      correspondientes al período <b>@{variables('KPI_Periodo')}</b>:</p>
      <table border="1" style="border-collapse:collapse; width:100%">
        <tr style="background-color:#0078d4; color:white">
          <th>Indicador</th><th>Valor</th><th>Estatus</th>
        </tr>
        <tr>
          <td>Costo Total de Nómina</td>
          <td>$@{variables('KPI_CostoTotal')} MXN</td>
          <td>✅ Calculado</td>
        </tr>
        <tr>
          <td>Variación vs. Presupuesto</td>
          <td>@{variables('KPI_Variacion')}%</td>
          <td>⚠️ Revisar</td>
        </tr>
        <tr>
          <td>Discrepancias Detectadas</td>
          <td>@{variables('KPI_NumDiscrepancias')}</td>
          <td>🔍 En revisión</td>
        </tr>
        <tr>
          <td>Alertas Críticas</td>
          <td>@{variables('KPI_AlertasCriticas')}</td>
          <td>🚨 Atención requerida</td>
        </tr>
      </table>
      <p>Este reporte fue generado automáticamente por el Sistema de Agentes de IA 
      de Compensaciones. Para mayor detalle, consulte el documento adjunto en SharePoint.</p>
      <p><i>Datos ficticios generados para práctica de formación.</i></p>
      ```
    - **Importancia:** Alta
    - **Adjuntos:** Agrega el contenido del reporte Word generado

13. Haz clic en **Guardar** y luego en **Probar** → **Manualmente** para ejecutar una prueba inmediata.

**Resultado Esperado:**
El flujo `PA_P8_Reporte_Ejecutivo_Quincena` se ejecuta sin errores. Se genera un archivo Word en SharePoint con los KPIs del período. Los participantes del curso reciben un correo con el reporte ejecutivo en formato HTML con tabla de indicadores.

**Verificación:**
- [ ] El flujo muestra estado "Correcto" en el historial de ejecuciones.
- [ ] El archivo `Reporte_Ejecutivo_Nomina_[Periodo].docx` aparece en la biblioteca de SharePoint.
- [ ] Los participantes reciben el correo con el asunto correcto y la tabla de KPIs.

---

#### Paso 7: Publicar los Agentes y Configurar el Canal de Teams

**Objetivo:** Publicar el Agente de Auditoría en Microsoft Teams y verificar que el ecosistema completo de agentes funciona en el entorno de simulación.

**Instrucciones:**

1. Regresa a Copilot Studio y abre el agente **"Agente Auditoría Pagos MX - [TuNombre]"**.

2. En la barra superior, haz clic en **Publicar**. Confirma la publicación en el diálogo que aparece. Espera el mensaje de confirmación ✅.

3. Una vez publicado, navega a la pestaña **Canales** (en el panel izquierdo o en la configuración del agente).

4. Selecciona el canal **Microsoft Teams**.

5. Haz clic en **Agregar a Teams** y sigue el asistente:
   - Confirma los permisos solicitados.
   - Selecciona **Abrir en Teams** cuando el proceso concluya.

6. En Microsoft Teams, el agente debe aparecer como un nuevo bot en la sección de aplicaciones. Si no aparece automáticamente:
   - Ve a **Aplicaciones** en Teams (barra lateral izquierda).
   - Busca el nombre de tu agente.
   - Haz clic en **Agregar** para añadirlo a tu espacio de trabajo.

7. Abre un chat directo con el agente "Agente Auditoría Pagos MX" en Teams.

8. Escribe el mensaje de activación: `iniciar auditoría`

9. Sigue el flujo conversacional:
   - Período: `Q1-2025`
   - Alcance: `Toda la organización`
   - Observa cómo el agente llama al flujo de Power Automate.

10. Verifica en SharePoint que los hallazgos simulados aparecen en la lista "Hallazgos de Auditoría".

11. Verifica en Outlook que las alertas de discrepancia fueron enviadas.

12. Repite la prueba con el **Agente de Nómina**: escribe `verificar cálculo de discrepancia` y proporciona un ID de empleado del dataset.

**Resultado Esperado:**
Ambos agentes responden correctamente en Teams. La lista de SharePoint muestra nuevos elementos con los hallazgos de auditoría. Los correos de alerta llegan a las cuentas de prueba. El ecosistema de agentes funciona de forma coordinada.

**Verificación:**
- [ ] El Agente de Auditoría responde en Teams con el flujo conversacional completo.
- [ ] La lista "Hallazgos de Auditoría" en SharePoint muestra registros nuevos con fecha actual.
- [ ] Los correos de alerta fueron recibidos en las cuentas de prueba.
- [ ] El Agente de Nómina responde al tópico de "Recibir Escalamiento de Auditoría".

---

### Sección 8.4: Demostración del Ecosistema Completo

---

#### Paso 8: Ejecutar la Demostración End-to-End

**Objetivo:** Presentar el ecosistema completo de agentes interconectados simulando un escenario de auditoría real ante el grupo, demostrando el valor estratégico de la interconexión de agentes.

**Instrucciones:**

1. Prepara el escenario de demostración. Abre simultáneamente las siguientes ventanas/pestañas:
   - **Ventana 1:** Microsoft Teams — Chat con "Agente Auditoría Pagos MX"
   - **Ventana 2:** Microsoft Teams — Chat con "Agente Nómina MX"
   - **Ventana 3:** SharePoint — Lista "Hallazgos de Auditoría" (vista en tiempo real)
   - **Ventana 4:** Power Automate — Historial de ejecuciones del flujo de auditoría
   - **Ventana 5:** Outlook — Bandeja de entrada para ver alertas en tiempo real

2. **Escenario de demostración:** *"La Directora de Compensaciones de Empresa Ficticia S.A. de C.V. solicita una auditoría urgente del período Q2-2025 para el departamento de Operaciones, tras detectar una variación inusual en el presupuesto."*

3. En el chat con el Agente de Auditoría (Ventana 1), escribe:
   ```
   Necesito auditar pagos urgentemente
   ```

4. Sigue el flujo conversacional respondiendo:
   - Período: `Q2-2025`
   - Alcance: `Departamento específico`
   - Departamento: `Operaciones`

5. Mientras el agente procesa (llama al flujo de Power Automate), cambia a la **Ventana 4** (Power Automate) y muestra al grupo cómo el flujo se está ejecutando en tiempo real.

6. Cuando el agente responda con el resumen de auditoría, cambia a la **Ventana 3** (SharePoint) y muestra los nuevos hallazgos registrados automáticamente.

7. Cambia a la **Ventana 5** (Outlook) y muestra las alertas de discrepancia recibidas.

8. En el chat del Agente de Auditoría, responde `Sí, escalar al Agente de Nómina`.

9. Cambia a la **Ventana 2** (Chat con Agente de Nómina) y escribe:
   ```
   verificar cálculo de discrepancia
   ```
   Proporciona el ID de empleado que aparece en el reporte de auditoría.

10. Muestra cómo el Agente de Nómina verifica el cálculo y actualiza el estado en SharePoint.

11. Finalmente, ejecuta manualmente el flujo `PA_P8_Reporte_Ejecutivo_Quincena` desde Power Automate:
    - Ve a Power Automate → Mis flujos → `PA_P8_Reporte_Ejecutivo_Quincena`
    - Haz clic en **Ejecutar** → **Ejecutar flujo**
    - Muestra el correo ejecutivo recibido en Outlook.

12. Comparte tu pantalla con el grupo (o con el instructor) y explica cada componente del ecosistema:
    - Qué hace cada agente.
    - Cómo se comunican entre sí.
    - Qué valor aporta a la organización.
    - Cómo cumple con los requisitos de la LFT, IMSS e Infonavit al documentar hallazgos.

**Resultado Esperado:**
La demostración muestra el ecosistema completo funcionando: el Agente de Auditoría detecta discrepancias → registra en SharePoint → alerta por Outlook → escala al Agente de Nómina → el Agente de Nómina verifica y actualiza → el flujo ejecutivo genera y distribuye el reporte. El tiempo total del escenario end-to-end es menor a 5 minutos (vs. días en un proceso manual).

**Verificación:**
- [ ] Todos los componentes del ecosistema respondieron correctamente durante la demostración.
- [ ] El reporte ejecutivo fue recibido por los participantes en Outlook.
- [ ] Los hallazgos en SharePoint muestran el ciclo completo: Nuevo → Verificado por Agente Nómina.
- [ ] El instructor o compañeros confirmaron la demostración como exitosa.

---

## Validación y Pruebas

### Lista de Verificación Final del Ecosistema

Antes de considerar la práctica completada, verifica cada componente del ecosistema:

| Componente | Criterio de Éxito | Estado |
|---|---|---|
| Agente de Auditoría en Copilot Studio | Publicado, con tópico "Iniciar Auditoría de Pagos" funcional | ☐ |
| Flujo `PA_P8_Auditoria_Discrepancias` | Activo, ejecuta sin errores, registra en SharePoint | ☐ |
| Lista "Hallazgos de Auditoría" en SharePoint | Contiene registros generados por el flujo | ☐ |
| Alertas de Outlook | Correos de discrepancia recibidos en cuentas de prueba | ☐ |
| Tópico "Recibir Escalamiento" en Agente Nómina | Funcional, actualiza estado en SharePoint | ☐ |
| Flujo `PA_P8_Reporte_Ejecutivo_Quincena` | Ejecuta, genera documento Word, envía correo ejecutivo | ☐ |
| Agente de Auditoría en Teams | Responde correctamente al canal configurado | ☐ |
| Demostración end-to-end | Completada ante instructor/grupo | ☐ |

### Prueba de Regresión: Escenario Alternativo

Para validar la robustez del ecosistema, ejecuta este escenario adicional (5 minutos):

1. En el Agente de Auditoría en Teams, escribe: `auditar pagos`
2. Proporciona un período inexistente en el dataset (ej. `Q5-2030`).
3. Verifica que el agente maneja el escenario de "sin resultados" de forma elegante (mensaje informativo, no error).
4. Escribe: `detectar discrepancias` y selecciona `Toda la organización`.
5. Verifica que el conteo de discrepancias es mayor a 0 (el dataset tiene discrepancias simuladas).

---

## Solución de Problemas

### Problema 1: El flujo de Power Automate no aparece disponible en el nodo de acción de Copilot Studio

**Síntoma:** Al intentar seleccionar `PA_P8_Auditoria_Discrepancias` en el nodo "Llamar a una acción" dentro del tópico de Copilot Studio, el flujo no aparece en la lista o aparece con un ícono de error.

**Causa:** El flujo no fue creado con el desencadenador correcto de Copilot Studio (debe usar el conector "Cuando Copilot Studio llama a un flujo" / PowerApps V2), o el flujo fue creado en un entorno de Power Platform diferente al que está usando Copilot Studio. También puede ocurrir si el flujo no ha sido guardado y publicado antes de intentar vincularlo.

**Solución:**
```
1. En Power Automate, abre el flujo PA_P8_Auditoria_Discrepancias.
2. Verifica que el desencadenador sea "Cuando Copilot Studio llama a un flujo"
   (no "Cuando se activa un flujo manualmente" ni otro desencadenador).
3. Si el desencadenador es incorrecto, crea un nuevo flujo desde Copilot Studio:
   - En el nodo de acción, selecciona "Crear un flujo de Power Automate"
   - Esto abrirá Power Automate con el desencadenador correcto preconfigurado
   - Reconstruye los pasos del flujo en esta nueva plantilla
4. Asegúrate de que el entorno seleccionado en Power Automate (esquina superior derecha)
   coincide exactamente con el entorno seleccionado en Copilot Studio.
5. Guarda y publica el flujo, luego regresa a Copilot Studio y actualiza la página
   antes de intentar seleccionar el flujo nuevamente.
```

---

### Problema 2: El Agente de Auditoría no aparece en Microsoft Teams después de la publicación

**Síntoma:** El agente fue publicado exitosamente en Copilot Studio y se configuró el canal de Teams, pero al buscar el agente en la barra de aplicaciones de Teams no aparece, o aparece pero responde con el mensaje "Este bot no está disponible actualmente".

**Causa:** La propagación del canal de Teams puede tardar entre 5 y 30 minutos después de la publicación. También puede deberse a que la política de aplicaciones del tenant de Microsoft 365 no permite la instalación de aplicaciones personalizadas por parte de los usuarios, requiriendo aprobación del administrador de Teams. Una causa adicional es que el agente fue publicado pero el canal de Teams no fue configurado completamente (falta el paso de "Agregar a Teams").

**Solución:**
```
1. Espera mínimo 15 minutos después de la publicación antes de buscar el agente en Teams.

2. Si después de 15 minutos no aparece, verifica la configuración del canal:
   - En Copilot Studio → tu agente → Canales → Microsoft Teams
   - Confirma que el estado del canal muestra "Configurado" o "Activo"
   - Si muestra "No configurado", repite el proceso de "Agregar a Teams"

3. Si el canal está configurado pero el agente no aparece en Teams:
   - En Teams, ve a Aplicaciones (barra lateral) → busca el nombre exacto del agente
   - Si no aparece, solicita al administrador de Teams que verifique las políticas
     de aplicaciones personalizadas en el Centro de Administración de Teams:
     Teams Admin Center → Aplicaciones de Teams → Directivas de configuración de aplicaciones
   - El administrador debe permitir "Aplicaciones personalizadas" para los participantes

4. Alternativa inmediata para continuar la práctica:
   - Prueba el agente directamente en Copilot Studio usando el panel "Probar agente"
   - Esto no requiere publicación en Teams y permite completar la demostración
   - El panel de pruebas simula exactamente el comportamiento del agente en Teams
```

---

## Limpieza del Entorno

Una vez completada la práctica y aprobada por el instructor, realiza las siguientes acciones de limpieza para mantener el entorno ordenado:

> ⚠️ **Importante:** No elimines los agentes ni los flujos hasta que el instructor confirme que la evaluación ha sido registrada.

### Limpieza Opcional (según instrucción del instructor)

```
COPILOT STUDIO — Desactivar agentes (no eliminar):
1. Abre cada agente en Copilot Studio
2. Ve a Configuración → Canales → Microsoft Teams
3. Haz clic en "Quitar de Teams" para desconectar el canal
   (el agente permanece en Copilot Studio para revisión del instructor)

POWER AUTOMATE — Desactivar flujos programados:
1. Navega a make.powerautomate.com
2. Localiza el flujo PA_P8_Reporte_Ejecutivo_Quincena
3. Haz clic en los tres puntos (...) → Desactivar
   (evita que el flujo se ejecute automáticamente en fechas futuras)
   NOTA: No elimines los flujos; el instructor los revisará.

SHAREPOINT — Archivar datos de práctica:
1. En la biblioteca "Práctica 8 - Auditoría"
2. Crea una carpeta "Archivo_[TuNombre]_[Fecha]"
3. Mueve todos los archivos generados durante la práctica a esa carpeta
   (mantiene el sitio organizado para las siguientes sesiones)

OUTLOOK — Limpiar correos de prueba:
1. En tu bandeja de entrada, busca correos con asunto "ALERTA DE AUDITORÍA"
   y "Reporte Ejecutivo de Nómina"
2. Muévelos a una carpeta "Práctica 8 - Evidencias" para referencia futura
3. No elimines estos correos; son evidencia de la práctica completada
```

---

## Resumen

### Logros de la Práctica

En esta práctica final has construido un **ecosistema de agentes de IA interconectados** que representa la culminación de todas las competencias desarrolladas a lo largo del curso. Específicamente, has:

1. **Creado un Agente de Auditoría especializado** en Copilot Studio, con instrucciones del sistema orientadas al cumplimiento de la LFT, IMSS e Infonavit, y con conocimiento del dataset de auditoría de pagos ficticios.

2. **Construido un flujo de detección automática de discrepancias** en Power Automate que procesa el dataset de nómina, identifica variaciones superiores al umbral permitido, registra hallazgos en SharePoint y envía alertas automáticas al responsable.

3. **Configurado la interconexión entre agentes**, permitiendo que el Agente de Auditoría escale consultas complejas al Agente de Nómina, y que este último actualice el estado de los hallazgos en SharePoint, cerrando el ciclo de auditoría de forma automatizada.

4. **Implementado un flujo de reporte ejecutivo automatizado** que consolida KPIs de nómina (costo total, variaciones, discrepancias, alertas críticas) y genera un reporte en Word que se distribuye automáticamente por Outlook a la dirección.

5. **Demostrado el ecosistema completo en Teams**, simulando un escenario end-to-end de auditoría que reduce el tiempo de respuesta de días a minutos.

### Conexión con los Conceptos del Capítulo 8

Esta práctica materializó los conceptos teóricos de la Lección 8.1:
- La **interconexión de agentes** como ventaja competitiva organizacional quedó demostrada en la comunicación bidireccional entre el Agente de Auditoría y el Agente de Nómina.
- La **sincronización de datos para decisiones ejecutivas** se implementó mediante el flujo de reporte quincena que alimenta automáticamente a la dirección con información confiable y oportuna.
- El escenario de la empresa manufacturera con 1,200 empleados (reducción de 15 días a 4 horas) fue replicado en tu ecosistema, donde el tiempo de detección y escalamiento se redujo a menos de 5 minutos.

### Recursos Adicionales

| Recurso | Descripción | URL |
|---|---|---|
| Documentación de Copilot Studio | Integración entre agentes y canales | `https://learn.microsoft.com/es-es/microsoft-copilot-studio/` |
| Power Automate — Conectores de SharePoint | Referencia de acciones disponibles | `https://learn.microsoft.com/es-es/connectors/sharepointonline/` |
| Power Automate — Conector de Copilot Studio | Desencadenadores y acciones | `https://learn.microsoft.com/es-es/power-automate/copilot-overview` |
| Microsoft Teams — Despliegue de bots | Guía de administración | `https://learn.microsoft.com/es-es/microsoftteams/platform/bots/how-to/deploy-bots-overview` |
| LFT — Ley Federal del Trabajo (texto vigente) | Referencia normativa | `https://www.diputados.gob.mx/LeyesBiblio/pdf/LFT.pdf` |
| IMSS — Guía de obligaciones patronales | Cumplimiento de cuotas | `https://www.imss.gob.mx/patrones` |

---

*Este laboratorio forma parte del curso **Copilot en Compensaciones** y debe ejecutarse con datos estrictamente ficticios conforme a la LFPDPPP. Cualquier uso de datos reales de empleados está prohibido y puede constituir una violación a la legislación mexicana de protección de datos personales.*
