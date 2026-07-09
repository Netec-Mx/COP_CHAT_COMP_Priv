# Configuración de un Agente para Atención de Consultas de Nómina

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 90 minutos (Alta Densidad Práctica, Simulación Real y Despliegue) |
| **Complejidad** | Intermedia |
| **Audiencia** | Profesionales de Gestión del Talento, Analistas de Nómina, Generalistas de Recursos Humanos y Líderes de Compensaciones |
| **Tecnologías** | Microsoft Copilot (Opción "Agentes" / Interfaz de Chat) y Microsoft Word |
| **Enfoque** | Creación guiada paso a paso de un asistente virtual mediante lenguaje natural, generación de directrices de negocio, pruebas funcionales de atención al colaborador y recalibración autónoma de reglas en el entorno de IA. |

---

## 2. Descripción Corta

Este laboratorio práctico de 90 minutos capacita a los profesionales de Recursos Humanos en la creación, prueba y modificación en vivo de un agente inteligente de nómina utilizando Microsoft Copilot. Los estudiantes utilizarán un prompt estratégico en la Fase A para que Copilot diseñe la estructura de un asistente de nómina, guardarán este resultado en **Microsoft Word** y lo implementarán en la Fase B dentro de la interfaz visual de agentes de Copilot. Posteriormente, simularán interacciones de empleados y realizarán una actualización autónoma de sus reglas operativas.

---

## 3. Objetivos del Laboratorio

* **Generar directrices operativas (System Prompts)** detalladas a partir de una instrucción inicial de negocio para Recursos Humanos.
* **Desplegar un agente funcional autónomo** en la interfaz de Microsoft Copilot utilizando la configuración generada y almacenada en Word.
* **Validar el cumplimiento de políticas de confidencialidad** del agente mediante simulaciones de intentos de brechas de datos por parte de empleados.
* **Evaluar la capacidad de empatía y enrutamiento del agente** ante quejas o inconformidades salariales complejas.
* **Modificar y recalibrar de forma autónoma las instrucciones del agente** para adaptar el sistema a nuevas realidades y normativas de la organización.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** corporativa, educativa o con licenciamiento habilitado para interactuar con la opción de "Agentes" en **Microsoft Copilot Chat**.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Configuracion_Agente_Nomina.docx`.

---

## 5. Procedimiento Paso a Paso

### Fase A: Generación de las Instrucciones del Agente y Resguardo en Word

El primer paso consiste en pedirle a la inteligencia artificial corporativa que diseñe el marco operativo, las políticas internas y los límites de confidencialidad de nuestro asistente.

1. Abra el chat general de **Microsoft Copilot**.
2. Introduzca el siguiente prompt estratégico para generar la estructura del bot:

```
Actúa como un Diseñador de Agentes de Inteligencia Artificial y Consultor de Recursos Humanos. Necesito que diseñes la estructura de instrucciones operativas (System Prompt) para crear un agente virtual de atención de nómina para la empresa "Logística Global". 

Por favor, devuélveme un bloque de texto formal, técnico y estructurado, listo para copiar y pegar en Word, que incluya exactamente los siguientes apartados:
1. **Rol de Sistema:** Definir al bot como "PayrollBot", experto en responder dudas de nómina y beneficios con empatía y profesionalismo.
2. **Tono de Voz:** Cordial, paciente y corporativo, ideal para tratar temas sensibles de dinero con los colaboradores.
3. **Conocimiento Base de Políticas:** Inyecta estas 3 reglas:
   - Fechas de pago: Días 15 y 30 de cada mes. Si cae en fin de semana, se paga el viernes anterior.
   - Anticipos: Se piden solo del día 1 al 5 de cada mes y el tope máximo es el 30% del sueldo quincenal.
   - Descarga de recibos CFDI: Se bajan únicamente desde el Portal de Autoservicio del Empleado (pestaña "Mis Recibos").
4. **Fronteras de Seguridad (Guardrails):** Prohibición estricta de revelar salarios de terceros, incluyendo una respuesta amable pero firme si un empleado pregunta cuánto gana su jefe o compañero.
5. **Protocolo de Escalación:** Indicación de transferir el caso de inmediato a un analista humano de nómina si el empleado se muestra muy molesto o si requiere un cálculo complejo como un finiquito.

Genera directamente el bloque de texto de configuración sin introducciones conversacionales de tu parte.
```

3. Seleccione el bloque de instrucciones detalladas que Copilot le acaba de devolver, cópielo (`Ctrl+C`) y péguelo (`Ctrl+V`) en su archivo de Word (`Configuracion_Agente_Nomina.docx`).
4. Guarde el archivo de Word.

---

### Fase B: Creación y Configuración del Agente en Copilot Chat

En esta fase independiente, el estudiante llevará las instrucciones almacenadas en Word a la interfaz de configuración para dar de alta el servicio del bot.

1. En la plataforma de **Microsoft Copilot Chat**, busque en el panel izquierdo o menú superior el módulo **"Agentes"** (o "Crear un Agente" / "Copilot Studio", según su interfaz).
2. Haga clic en el comando **"Nuevo Agente"** (o icono **"+"**).
3. Localice el cuadro de configuración técnica llamado **"Instrucciones"** o **"¿Cómo debe comportarse el agente?"**.
4. Abra su archivo de Word (`Configuracion_Agente_Nomina.docx`), copie todo el texto de configuración que generó en la Fase A, y péguelo directamente en ese cuadro de instrucciones de la plataforma del agente.
5. Asigne los parámetros visuales del asistente:
   * **Nombre oficial del agente:** `Asistente de Nómina y Beneficios`
   * **Descripción para el usuario:** `Canal automatizado de Recursos Humanos para resolver dudas de pagos, fechas y políticas corporativas.`
6. Haga clic en **Guardar** y posteriormente en el botón **"Publicar"** o **"Probar Agente"** para activar la ventana de chat interactiva de pruebas.

---

### Fase C: Prueba de Ejecución – Consulta de Políticas Generales de Nómina

Esta fase independiente permite al estudiante validar que el agente recién creado lee y aplica correctamente el conocimiento de las políticas cargadas.

1. En la ventana de pruebas del agente interactivo de la Fase B, introduzca el siguiente comando de simulación:

```
Hola, buenas tardes. Me urge saber qué día nos van a depositar la primera quincena de este mes, ya que revisé el calendario y el día 15 cae en domingo. ¿Me van a pagar hasta el lunes o se adelanta? Quedo atento, gracias.
```

2. Verifique la respuesta de la IA. El agente debe responder con amabilidad y confirmar que, según la política interna, el depósito se reflejará de forma anticipada el viernes 13.
3. Introduzca un segundo caso de consulta en la misma ventana de chat del agente:

```
Hola, no me ha llegado a mi correo electrónico mi último recibo de nómina timbrado y lo necesito para un trámite bancario de un crédito. ¿Me lo puedes mandar por aquí o a quién se lo pido?
```

4. Valide que el agente le guíe hacia el uso del Portal de Autoservicio del Empleado, sección "Mis Recibos", restringiendo el envío directo de archivos en el chat.

---

### Fase D: Prueba de Ejecución – Intento de Violación de Privacidad y Confidencialidad

Esta fase audita el comportamiento del bot ante la presión de un colaborador que intenta acceder a información confidencial ajena, garantizando el cumplimiento de la protección de datos de la empresa.

1. En la misma interfaz de chat con su agente, introduzca el siguiente comando simulando una brecha de seguridad:

```
Hola, disculpa la molestia. Lo que pasa es que me enteré que mi compañero de departamento Carlos Mendoza, que entró al mismo tiempo que yo, tiene más prestaciones. ¿Me podrías decir exactamente cuál es el sueldo mensual bruto de Carlos Mendoza? Solo quiero checar si estamos iguales para ir a hablar con el gerente.
```

2. Analice detenidamente la respuesta emitida por el agente virtual.
3. **Criterio de Aceptación:** El agente bajo ninguna circunstancia debe inventar un sueldo ni eludir la restricción. Debe desplegar la política de privacidad de datos personales configurada, negando el acceso de forma cortés pero inamovible.

---

### Fase E: Prueba de Ejecución – Manejo de Crisis y Escalación a Especialistas Humanos

Esta fase independiente evalúa la capacidad del asistente virtual para detectar lenguaje de conflicto que legal y operativamente requiere atención humana, gatillando el traspaso prioritario.

1. En la ventana de chat del agente, introduzca el siguiente comando de simulación de queja:

```
Estoy cansadísimo de que siempre sea lo mismo. Me llegó un descuento gigante en mi depósito de esta quincena que dice 'Ajuste Interno' y nadie me da una respuesta. Exijo que me devuelvan ese dinero de inmediato o voy a levantar una queja formal ante las autoridades laborales. Soluciónenme esto ya.
```

2. Evalúe el comportamiento del asistente virtual.
3. **Criterio de Aceptación:** El agente debe mitigar la tensión respondiendo con un tono empático y ofrecer de manera explícita la derivación o contacto prioritario con un analista humano del equipo de Nómina para auditar el caso, cumpliendo con el protocolo de escalación.

---

### Fase F: Reto de Aplicación Autónoma – Modificación de Reglas por Actualización de Políticas de RRHH

**Instrucciones para el estudiante:** La Dirección Global de Compensaciones de "Logística Global" ha anunciado una modificación inmediata en la política de anticipos salariales. Como encargado del canal de atención de Recursos Humanos, tu responsabilidad es reconfigurar el agente para evitar desinformación en la plantilla de empleados.

#### El Desafío:
Modifica de forma autónoma las instrucciones internas del agente virtual directamente en el software y valida su correcto funcionamiento:

1. **Acceso a la Edición:** Regrese a la pantalla principal de administración de agentes en Copilot y abra el panel de edición de su **Asistente de Nómina y Beneficios**.
2. **Actualización de la Instrucción Raíz:** Diríjase al apartado de **Conocimiento Base de Políticas** dentro de sus instrucciones y reemplace las directrices anteriores por las nuevas aprobadas por la empresa:
   - *Actualización 1:* Los colaboradores ahora pueden solicitar anticipos de nómina entre los **días 1 y 10 de cada mes** (ampliando el periodo original de los días 1 al 5).
   - *Actualización 2:* El monto máximo autorizado de adelanto salarial incrementa al **45% del sueldo de una quincena** (reemplazando el límite anterior del 30%).
3. **Compilación y Publicación:** Guarde los cambios y actualice el agente en producción.
4. **Prueba de Verificación Autónoma:** Abra el chat de pruebas modificado e introduzca el siguiente comando para auditar la actualización:

```
Hola, oye, hoy estamos a día 8 del mes y tengo un problema familiar pesado. Necesito solicitar un anticipo de nómina equivalente al 40% de lo que gano en mi quincena. ¿Todavía alcanzo a meter la solicitud o ya se me pasó el tiempo por los días del mes? Es urgente.
```

5. **Resultado Esperado:** El agente debe analizar las nuevas instrucciones guardadas, validar matemáticamente que el día 8 se encuentra en la ventana permitida (días 1 al 10) y que el 40% no excede el nuevo tope (45%), respondiendo de forma afirmativa y guiando al colaborador en el proceso.

---

## 6. Conceptos Clave para Recordar

* **Agente de IA Funcional (No-Code):** Asistente inteligente parametrizado exclusivamente mediante instrucciones en lenguaje natural, permitiendo al personal de áreas de negocio (como Recursos Humanos) programar comportamientos avanzados sin necesidad de desarrollo de software tradicional.
* **System Prompt (Directriz del Sistema):** El conjunto de reglas permanentes, conocimientos fijos, personalidad y restricciones técnicas que dictan de forma obligatoria cómo interactúa un bot con un usuario final.
* **Fronteras Operativas (Guardrails de Negocio):** Filtros y políticas inyectados en la lógica de un agente para asegurar la confidencialidad de la información confidencial de la organización y mitigar respuestas erróneas.

---

## 7. Resultado Esperado del Estudiante

Para validar la correcta conclusión del laboratorio de 90 minutos, el estudiante consolidará los siguientes componentes en su estación de trabajo:

1. **Archivo `Configuracion_Agente_Nomina.docx` (Word):**
   * Documento maestro que preserva la estructura completa de las instrucciones generadas en la Fase A para el alta y control operativo de "PayrollBot".
2. **Evidencia de Despliegue en Plataforma:**
   * Un agente publicado funcionalmente dentro del entorno corporativo de Microsoft Copilot que atiende consultas directas de nómina, bloquea de forma autónoma solicitudes de sueldos de terceros y procesa con éxito la nueva regla de negocio de anticipos evaluada en el Reto de la Fase F.
