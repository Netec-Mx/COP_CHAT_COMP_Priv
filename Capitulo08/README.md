# Simulación de un Agente Interconectado para Auditorías de Pago

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 90 minutos (Enfoque en Ecosistemas de IA, Auditoría Funcional y Procesos Cruzados) |
| **Complejidad** | Intermedia |
| **Audiencia** | Profesionales de Gestión del Talento, Especialistas en Compensaciones, Auditores de Nómina y Líderes de Operaciones de RRHH |
| **Tecnologías** | Microsoft Copilot (Opción "Agentes" / Interfaz de Chat) y Microsoft Word |
| **Enfoque** | Diseño y simulación de un ecosistema de agentes interconectados (Agente de Servicio + Agente Auditor Financiero) para la detección de errores de pago, conciliación automatizada de incidencias y gobernanza de auditorías salariales. |

---

## 2. Descripción Corta

Este laboratorio práctico de 90 minutos capacita a los profesionales de Recursos Humanos en el diseño lógico y la simulación de agentes de IA interconectados que colaboran entre sí para resolver auditorías de pago complejas. Los estudiantes utilizarán un prompt estratégico en la Fase A para que Copilot diseñe las instrucciones de un "Agente Auditor de Nómina", guardarán el resultado en **Microsoft Word** y lo configurarán en la Fase B dentro de la plataforma de Copilot para que trabaje en equipo con el asistente de servicio. Posteriormente, simularán conciliaciones de nómina y actualizarán de forma autónoma los criterios de auditoría.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Estructurar instrucciones lógicas para agentes especializados** orientados a la revisión y cumplimiento analítico de pagos.
* **Configurar un entorno colaborativo de IA** donde un agente de servicio de RRHH interactúa con un agente supervisor de auditoría.
* **Simular conciliaciones automatizadas de incidencias** (como horas extra no pagadas o bonos caídos) mediante diálogos de control.
* **Auditar la veracidad de las respuestas del ecosistema de IA** frente a políticas internas de compensaciones.
* **Modificar y actualizar de forma autónoma los umbrales de tolerancia de auditoría** en el agente para responder a nuevas normativas de control financiero.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** corporativa, educativa o con licenciamiento habilitado para interactuar con la opción de "Agentes" en **Microsoft Copilot Chat**.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Configuracion_Agente_Auditor.docx`.

---

## 5. Procedimiento Paso a Paso

### Fase A: Generación de las Instrucciones del Agente Auditor y Resguardo en Word

El primer paso consiste en pedirle a la inteligencia artificial corporativa que diseñe el marco operativo, las reglas de control y los criterios de revisión de un agente especializado en auditorías de compensaciones que apoyará al bot de servicio al empleado.

1. Abra el chat general de **Microsoft Copilot**.
2. Introduzca el siguiente prompt estratégico para generar la estructura del bot auditor:

```
Actúa como un Diseñador de Soluciones de Inteligencia Artificial y Consultor de Auditoría de Recursos Humanos. Necesito que diseñes la estructura de instrucciones operativas (System Prompt) para crear un agente virtual especializado llamado "PayrollAuditor". Este agente no hablará directamente con el empleado, sino que será consultado por nuestro agente de servicio ("PayrollBot") para validar discrepancias en los pagos.

Por favor, devuélveme un bloque de texto formal, técnico y estructurado, listo para copiar y pegar en Word, que incluya exactamente los siguientes apartados:
1. **Rol de Sistema:** Definir al bot como "PayrollAuditor", un supervisor virtual analítico encargado de cruzar reportes de incidencias contra las bases de pago cargadas para detectar errores.
2. **Tono de Voz:** Estrictamente analítico, objetivo, preciso y basado en datos numéricos.
3. **Conocimiento Base de Criterios de Auditoría:** Inyecta estas 3 reglas de negocio:
   - Validación de Horas Extra: El límite máximo permitido para pago automático sin firma gerencial es de 9 horas semanales. Cualquier registro superior debe marcarse como "Requiere Aprobación Humana".
   - Conciliación de Bonos: Los bonos de productividad comercial deben cruzarse con el cumplimiento de la meta (100%). Si la meta registra 99% o menos, el bono debe aparecer como "0% asignado".
   - Margen de Tolerancia de Discrepancia: Si la diferencia reportada por un empleado en su quincena es menor a 50 pesos, el agente puede autorizar un ajuste automático en la siguiente nómina. Si es mayor, debe emitir un folio de auditoría formal.
4. **Fronteras de Seguridad (Guardrails):** Prohibición estricta de procesar ajustes manuales de salarios directos. Solo puede auditar, validar y sugerir correcciones de incidencias temporales.

Genera directamente el bloque de texto de configuración sin introducciones conversacionales de tu parte.
```

3. Seleccione el bloque de instrucciones detalladas que Copilot le acaba de devolver, cópielo (`Ctrl+C`) y péguelo (`Ctrl+V`) en su archivo de Word (`Configuracion_Agente_Auditor.docx`).
4. Guarde el archivo de Word.

---

### Fase B: Creación y Configuración del Agente Auditor en Copilot Chat

En esta fase independiente, el estudiante transferirá las instrucciones del archivo de Word a la interfaz de Copilot para dar de alta el segundo nodo del ecosistema (el agente auditor).

1. En la plataforma de **Microsoft Copilot Chat**, busque en el panel izquierdo o menú superior el módulo **"Agentes"** (o "Crear un Agente" / "Copilot Studio", según su interfaz).
2. Haga clic en el comando **"Nuevo Agente"** (o icono **"+"**).
3. Localice el cuadro de configuración técnica llamado **"Instrucciones"** o **"¿Cómo debe comportarse el agente?"**.
4. Abra su archivo de Word (`Configuracion_Agente_Auditor.docx`), copie todo el texto de configuración que generó en la Fase A, y péguelo directamente en ese cuadro de instrucciones de la plataforma del agente.
5. Asigne los parámetros visuales del asistente:
   * **Nombre oficial del agente:** `Auditor de Nómina y Pagos`
   * **Descripción para el usuario:** `Agente analítico interconectado para la conciliación automatizada de incidencias, horas extra y bonos corporativos.`
6. Haga clic en **Guardar** y posteriormente en el botón **"Publicar"** o **"Probar Agente"** para activar la ventana de chat interactiva.

---

### Fase C: Prueba de Ejecución – Consulta Interconectada de Horas Extra

Esta fase independiente permite al estudiante simular el flujo donde se le pide al agente que audite un registro de horas extra para validar si cumple con la política de control financiero de la empresa.

1. En la ventana de pruebas del agente de auditoría creado en la Fase B, introduzca el siguiente comando de simulación (simulando la consulta cruzada que haría el bot principal de atención):

```
Solicitud del sistema: El colaborador ID #4520 reporta en su portal de atención que esta quincena laboró 12 horas extra, pero en su recibo de pago solo aparecen reflejadas y pagadas 9 horas. Ejecuta la auditoría cruzada con la política base e indícame el diagnóstico del caso.
```

2. Verifique la respuesta del agente. Basándose en la política de la Fase A, el bot debe emitir un diagnóstico que indique que 9 horas fueron pagadas correctamente de forma automática, pero las 3 horas restantes superan el límite y su estado actual es "Requiere Aprobación Humana" por parte de su gerencia.

---

### Fase D: Prueba de Ejecución – Auditoría Cruzada de Bonos de Productividad

Esta fase valida la capacidad del agente para aplicar lógica condicional estricta al auditar el cumplimiento de métricas comerciales antes de autorizar el desembolso de bonos salariales.

1. En la misma interfaz de chat con su agente auditor, introduzca el siguiente comando de prueba:

```
Solicitud del sistema: El analista comercial de la sucursal Norte reclama que no se le pagó su bono de productividad mensual. Al revisar el sistema de métricas, el colaborador cerró el mes con un cumplimiento global del 99.4%. Genera la resolución de la auditoría.
```

2. Analice detenidamente la respuesta emitida por el agente virtual.
3. **Criterio de Aceptación:** El agente debe aplicar estrictamente la regla de negocio configurada. Debe dictaminar que al ser el cumplimiento menor al 100% (99.4%), la resolución automática de la auditoría establece "0% asignado" para el bono, explicando el criterio de forma neutral y clara.

---

### Fase E: Prueba de Ejecución – Aplicación del Margen de Tolerancia Financiera

Esta fase evalúa la capacidad del asistente para discernir de forma inteligente el impacto económico de una discrepancia salarial, resolviendo casos menores en segundos u ordenando una auditoría formal si el monto es elevado.

1. En la ventana de chat del agente, introduzca el siguiente comando de simulación de monto:

```
Solicitud del sistema: Una colaboradora del área operativa indica que le hicieron un descuento indebido por concepto de comedor de 350 pesos. Verifica el monto contra el margen de tolerancia operativa y determina la acción que debe tomar el bot de servicio.
```

2. Evalúe el comportamiento del asistente virtual.
3. **Criterio de Aceptación:** El agente debe identificar que 350 pesos excede el margen de tolerancia configurado de 50 pesos. Por lo tanto, no debe autorizar un ajuste automático, sino que debe emitir la orden de generar un "Folio de Auditoría Formal" para que el caso sea turnado al equipo de nómina físico.

---

### Fase F: Reto de Aplicación Autónoma – Modificación de Criterios por Actualización de Políticas de Control

**Instrucciones para el estudiante:** La Dirección de Finanzas y el departamento de Contraloría de "Logística Global" han modificado las políticas de gobernanza de pagos debido a una reestructuración de presupuestos. Tu labor como líder de Recursos Humanos es actualizar las reglas de control en el cerebro de tu agente auditor de forma inmediata.

#### El Desafío:
Modifica de forma autónoma las instrucciones internas del agente auditor directamente en el software y valida su correcto funcionamiento:

1. **Acceso a la Edición:** Regrese a la pantalla principal de administración de agentes en Copilot y abra el panel de edición de su **Auditor de Nómina y Pagos**.
2. **Actualización de la Instrucción Raíz:** Diríjase al apartado de **Conocimiento Base de Criterios de Auditoría** dentro de sus instrucciones y reemplace las directrices anteriores por las nuevas aprobadas por contraloría:
   - *Actualización 1 (Horas Extra):* El límite máximo permitido para pago automático de horas extra se reduce a **6 horas semanales** (reemplazando el límite anterior de 9 horas). Cualquier excedente pasará a validación.
   - *Actualización 2 (Margen de Tolerancia):* El margen para autorizar ajustes automáticos en la siguiente nómina debido a discrepancias menores sube a **120 pesos** (reemplazando el límite anterior de 50 pesos).
3. **Compilación y Publicación:** Guarde los cambios y actualice el agente en producción.
4. **Prueba de Verificación Autónoma:** Abra el chat de pruebas modificado de su agente auditor e introduzca el siguiente comando para auditar la actualización del ecosistema:

```
Solicitud del sistema: Un colaborador reclama que le descontaron por error 85 pesos de un estacionamiento institucional. Ejecuta la auditoría de este monto con las nuevas políticas de control financiero vigentes y define la acción.
```

5. **Resultado Esperado:** El agente auditor modificado debe analizar sus nuevas instrucciones, identificar que la discrepancia de 85 pesos ahora está por debajo del nuevo umbral de tolerancia (120 pesos) y dictaminar la autorización de un "Ajuste Automático" para la siguiente nómina del colaborador, demostrando que asimiló las nuevas directrices de manera autónoma.

---

## 6. Conceptos Clave para Recordar

* **Ecosistema de Agentes Interconectados:** Entorno de IA donde múltiples agentes especializados colaboran entre sí en segundo plano (un bot de atención al usuario y un bot experto en reglas de control) para resolver flujos de trabajo corporativos complejos sin intervención humana inicial.
* **Margen de Tolerancia Operativa:** Umbral financiero predefinido en las reglas de negocio que faculta a un sistema automatizado a resolver y compensar discrepancias menores de forma inmediata para agilizar la operación y reducir la carga administrativa.
* **Auditoría de Nómina Automatizada:** Proceso mediante el cual un agente inteligente cruza de forma sistemática reportes de incidencias contra políticas internas para emitir un diagnóstico preciso sobre la validez de un pago o descuento.

---

## 7. Resultado Esperado del Estudiante

Para validar la correcta conclusión del laboratorio de 90 minutos, el estudiante consolidará los siguientes componentes en su estación de trabajo:

1. **Archivo `Configuracion_Agente_Auditor.docx` (Word):**
   * Documento maestro que preserva la estructura completa de las instrucciones de control financiero generadas en la Fase A para el alta y control operativo de "PayrollAuditor".
2. **Evidencia de Despliegue en Plataforma:**
   * Un agente de auditoría publicado funcionalmente dentro del entorno corporativo de Microsoft Copilot que procesa consultas cruzadas de horas extra, dictamina la asignación de bonos comerciales por métricas y procesa con éxito la resolución de ajustes automáticos basada en el nuevo umbral de 120 pesos evaluado en el Reto de la Fase F.
