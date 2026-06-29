---LAB_START---
LAB_ID: 03-00-01
---MARKDOWN---
# Implementación de herramientas de auditoría con IA para confrontas de IMSS/Infonavit y REPSE. Validación de conceptos ante el SAT (timbrado) y detección de discrepancias en el timbrado.

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 90 minutos |
| **Complejidad** | Alta (Hard) |
| **Nivel Bloom** | Aplicar |
| **Módulo** | Capítulo 3 — Auditoría y Validación ante Autoridades con IA |
| **Práctica número** | 03-00-01 |
| **Modalidad** | Individual con acceso a Microsoft 365 Copilot |

---

## 2. Descripción General

Esta práctica integra las capacidades de Microsoft Copilot en Excel y Word para ejecutar un proceso completo de auditoría de nómina en tres frentes regulatorios críticos del marco mexicano: las confrontas con el **IMSS** e **Infonavit**, la validación de cumplimiento **REPSE** y la detección de discrepancias en el **timbrado de CFDI** ante el SAT. El participante utilizará datasets ficticios que simulan archivos reales exportados de los portales SUA/IDSE, SINCE y el SAT, cruzándolos con una base de nómina interna mediante Copilot para identificar diferencias, calcular importes en riesgo y generar un reporte ejecutivo de hallazgos. Al concluir, el participante habrá experimentado de primera mano cómo la IA reduce de días a horas el ciclo de auditoría de nómina, potenciando la capacidad analítica del especialista de compensaciones sin reemplazar su juicio profesional.

> ⚠️ **Aviso de cumplimiento:** Todos los datos utilizados en esta práctica son **estrictamente ficticios**. Está prohibido sustituirlos por datos reales de empleados en cumplimiento con la Ley Federal de Protección de Datos Personales en Posesión de los Particulares (LFPDPPP).

---

## 3. Objetivos de Aprendizaje

Al finalizar esta práctica, el participante será capaz de:

- [ ] **Implementar** un proceso de confronta asistido por Copilot en Excel entre registros internos de nómina y los determinados por el IMSS e Infonavit, identificando discrepancias en el Salario Base de Cotización (SBC) y aportaciones.
- [ ] **Aplicar** Copilot para validar el cumplimiento de obligaciones REPSE, cruzando información de contratos, trabajadores registrados y comprobantes de pago de cuotas.
- [ ] **Detectar** discrepancias en el timbrado de CFDI de nómina ante el SAT utilizando Copilot en Excel y Word para comparar nodos XML con registros internos de dispersión.
- [ ] **Generar** un reporte ejecutivo de auditoría con hallazgos, riesgos fiscales cuantificados y recomendaciones de corrección mediante Copilot en Word.

---

## 4. Prerrequisitos

### 4.1 Conocimientos Previos

| Área | Nivel requerido |
|---|---|
| Estructura del Salario Base de Cotización (SBC) y movimientos afiliatorios IMSS | Básico-Intermedio |
| Aportaciones patronales Infonavit (5% sobre SBC) y uso del sistema SINCE | Básico |
| Estructura de un CFDI de nómina versión 1.2 (nodos XML: percepciones, deducciones, totales) | Básico |
| Obligaciones del REPSE: informes cuatrimestrales y registro de proveedores | Básico |
| Uso de Microsoft Excel (tablas, Power Query, fórmulas básicas) | Intermedio |
| Uso de prompts en Microsoft Copilot (Prácticas 1 y 2 completadas) | Intermedio |

### 4.2 Acceso y Licencias

- Cuenta corporativa Microsoft 365 con licencia activa de **Microsoft 365 Copilot** (verificar con el administrador de TI mínimo 48 horas antes).
- Acceso a **Microsoft Excel** (versión 2308 o superior) con Copilot habilitado en la cinta de opciones.
- Acceso a **Microsoft Word** (versión 2308 o superior) con Copilot habilitado.
- Acceso a **SharePoint Online** del curso para descargar los archivos de práctica.
- Acceso a **Microsoft 365 Copilot Chat** (anteriormente Bing Chat Enterprise) en el navegador.

### 4.3 Archivos de Práctica Requeridos

Los siguientes archivos deben estar disponibles en la biblioteca de SharePoint del curso antes de iniciar. El instructor los habrá precargado en la carpeta **`Práctica 3 / Archivos de Entrada`**:

| Archivo | Descripción | Formato |
|---|---|---|
| `P3_Nomina_Interna_Julio2024.xlsx` | Base de nómina interna del mes de julio 2024 (150 registros ficticios) | Excel |
| `P3_Confronta_IMSS_SUA_Julio2024.xlsx` | Archivo de confronta exportado del sistema SUA del IMSS (simulado) | Excel |
| `P3_Confronta_Infonavit_SINCE_Julio2024.xlsx` | Archivo de confronta exportado del sistema SINCE de Infonavit (simulado) | Excel |
| `P3_REPSE_Proveedores_Registrados.xlsx` | Listado de proveedores con registro REPSE activo y trabajadores reportados | Excel |
| `P3_CFDI_Nomina_Muestra_XML.xlsx` | Datos clave extraídos de 30 archivos XML de CFDI de nómina (parseados a columnas) | Excel |
| `P3_Nomina_Dispersada_Julio2024.xlsx` | Registro de pagos dispersados (importes netos, percepciones y deducciones) | Excel |
| `P3_Plantilla_Reporte_Auditoria.docx` | Plantilla Word para el reporte ejecutivo de auditoría | Word |

---

## 5. Entorno de Laboratorio

### 5.1 Requisitos de Hardware

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8ª gen / AMD Ryzen 5 | Intel Core i7 10ª gen / AMD Ryzen 7 |
| Memoria RAM | 8 GB | 16 GB (Excel + Word + Copilot simultáneos) |
| Almacenamiento libre | 2 GB | 5 GB |
| Conexión a internet | 10 Mbps | 25 Mbps |
| Resolución de pantalla | 1366×768 | 1920×1080 |

### 5.2 Requisitos de Software

| Aplicación | Versión mínima | Verificación |
|---|---|---|
| Microsoft Excel | 2308 (Microsoft 365) | `Archivo > Cuenta > Acerca de Excel` |
| Microsoft Word | 2308 (Microsoft 365) | `Archivo > Cuenta > Acerca de Word` |
| Microsoft 365 Copilot | Licencia activa | Ícono Copilot visible en la cinta de Excel/Word |
| Microsoft Edge / Chrome | Edge 120+ / Chrome 120+ | Barra de dirección del navegador |
| SharePoint Online | Acceso vía tenant corporativo | Navegar a `https://[tenant].sharepoint.com` |

### 5.3 Configuración Inicial del Entorno

Antes de iniciar los pasos de la práctica, completa la siguiente verificación de entorno:

**Paso A — Descargar archivos de práctica desde SharePoint:**

1. Abre Microsoft Edge y navega a la URL del sitio SharePoint del curso proporcionada por el instructor.
2. Navega a la biblioteca de documentos: **`Documentos > Práctica 3 > Archivos de Entrada`**.
3. Selecciona todos los archivos listados en la tabla 4.3, haz clic en **`Descargar`** y guárdalos en la carpeta local:
   ```
   C:\Curso_M365_Copilot\Practica3\
   ```
4. Verifica que los 7 archivos estén presentes en la carpeta local antes de continuar.

**Paso B — Verificar que Copilot está habilitado en Excel:**

1. Abre `P3_Nomina_Interna_Julio2024.xlsx` en Excel.
2. En la cinta de opciones, verifica que el botón **`Copilot`** (ícono de estrella azul) sea visible en la pestaña **`Inicio`**.
3. Si el botón no aparece, notifica al instructor antes de continuar. **No avances sin Copilot habilitado.**

**Paso C — Verificar que los datos están en formato de Tabla de Excel:**

En el archivo `P3_Nomina_Interna_Julio2024.xlsx`, confirma que los datos estén formateados como **Tabla de Excel** (borde azul, encabezados con flecha de filtro). Si no lo están, selecciona el rango de datos y presiona `Ctrl + T` para convertirlos. Repite para los demás archivos de entrada.

---

## 6. Procedimiento Paso a Paso

La práctica está dividida en dos secciones principales:

- **Sección 3.1** (Pasos 1–5): Confrontas IMSS, Infonavit y validación REPSE con Copilot en Excel.
- **Sección 3.2** (Pasos 6–9): Detección de discrepancias en CFDI y generación del reporte ejecutivo con Copilot en Word.

---

### SECCIÓN 3.1 — Confrontas IMSS, Infonavit y Validación REPSE

---

#### Paso 1: Exploración y Comprensión de los Datasets con Copilot

**Objetivo:** Familiarizarse con la estructura de los tres archivos de entrada (nómina interna, confronta IMSS y confronta Infonavit) usando Copilot para generar un resumen analítico inicial antes de ejecutar el cruce de datos.

**Instrucciones:**

1. Abre el archivo `P3_Nomina_Interna_Julio2024.xlsx`. Asegúrate de que los datos estén en formato de Tabla de Excel (ver Paso C de la configuración).

2. Haz clic en el botón **`Copilot`** en la cinta de opciones (pestaña `Inicio`). Se abrirá el panel de Copilot en el lado derecho de la pantalla.

3. Escribe el siguiente prompt en el campo de texto del panel de Copilot:

   ```
   Analiza esta tabla de nómina interna. Dime cuántos empleados hay en total,
   cuál es el rango de Salario Base de Cotización (columna SBC_Interno),
   cuántos empleados tienen registro de movimiento afiliatorio en el mes
   (columna Movimiento_Afiliatorio) y cuál es la suma total de cuotas
   patronales calculadas (columna Cuota_Patronal_Calculada).
   Presenta el resumen en formato de tabla.
   ```

4. Revisa la respuesta de Copilot y anota los valores clave en tu hoja de notas o en una celda aparte de la hoja `Resumen` (si existe).

5. Sin cerrar el panel de Copilot, abre el archivo `P3_Confronta_IMSS_SUA_Julio2024.xlsx` en una nueva ventana de Excel.

6. En el panel de Copilot de este segundo archivo, escribe:

   ```
   Describe la estructura de esta tabla de confronta IMSS. Identifica las
   columnas principales, el número de registros y señala si hay algún campo
   que indique diferencias entre el SBC reportado por la empresa y el
   determinado por el IMSS (busca columnas con nombres como "Diferencia",
   "SBC_IMSS", "SBC_Empresa" o similares).
   ```

7. Repite el paso 6 con el archivo `P3_Confronta_Infonavit_SINCE_Julio2024.xlsx`.

8. Con base en las respuestas de Copilot, completa la siguiente tabla de mapeo de columnas en tu cuaderno o en la hoja `Mapeo_Columnas` del archivo de nómina interna:

   | Campo lógico | Columna en Nómina Interna | Columna en Confronta IMSS | Columna en Confronta Infonavit |
   |---|---|---|---|
   | Clave de empleado / NSS | | | |
   | Salario Base de Cotización | | | |
   | Cuota patronal calculada | | | |
   | Diferencia detectada | N/A | | |

**Resultado esperado:** El panel de Copilot habrá generado tres resúmenes analíticos (uno por archivo) con estadísticas descriptivas y la identificación de columnas clave. El participante contará con un mapa de columnas para ejecutar el cruce en el paso siguiente.

**Verificación:** Confirma que Copilot identificó correctamente al menos 4 columnas en cada archivo. Si Copilot no reconoce la estructura, verifica que los datos estén en formato de Tabla de Excel y que los encabezados sean descriptivos (sin celdas combinadas ni filas en blanco).

---

#### Paso 2: Cruce de Datos IMSS con Power Query y Análisis de Discrepancias con Copilot

**Objetivo:** Consolidar en un solo libro los datos de nómina interna y la confronta IMSS mediante Power Query, y luego usar Copilot para identificar y cuantificar discrepancias en el SBC.

**Instrucciones:**

1. En el archivo `P3_Nomina_Interna_Julio2024.xlsx`, ve a la pestaña **`Datos`** en la cinta de opciones y haz clic en **`Obtener datos > De libro`**.

2. Selecciona el archivo `P3_Confronta_IMSS_SUA_Julio2024.xlsx` y haz clic en **`Importar`**. En el navegador de Power Query, selecciona la tabla principal del archivo y haz clic en **`Transformar datos`**.

3. En el editor de Power Query, realiza las siguientes transformaciones:
   - Renombra la consulta como `Confronta_IMSS`.
   - Verifica que la columna de NSS (Número de Seguridad Social) tenga el mismo tipo de dato en ambas tablas (texto, no número). Si es necesario, haz clic derecho sobre la columna y selecciona **`Cambiar tipo > Texto`**.
   - Haz clic en **`Cerrar y cargar en...`** y selecciona **`Solo crear conexión`**.

4. Repite los pasos 1–3 para importar `P3_Confronta_Infonavit_SINCE_Julio2024.xlsx`, renombrando la consulta como `Confronta_Infonavit`.

5. Ahora crea una consulta de combinación. Ve a **`Datos > Obtener datos > Combinar consultas > Combinar`**. Configura:
   - **Tabla izquierda:** `Nomina_Interna` (o el nombre de la tabla principal del archivo de nómina)
   - **Tabla derecha:** `Confronta_IMSS`
   - **Columna de combinación:** NSS (en ambas tablas)
   - **Tipo de combinación:** `Externa izquierda (todos los de la primera, los coincidentes de la segunda)`
   - Haz clic en **`Aceptar`**.

6. En el editor de Power Query resultante, expande la columna de `Confronta_IMSS` y selecciona únicamente las columnas: `SBC_IMSS`, `Cuota_IMSS_Determinada` y `Diferencia_SBC` (o los nombres equivalentes según el mapeo del Paso 1). Desmarca `Usar nombre de columna original como prefijo` si lo prefieres. Haz clic en **`Aceptar`**.

7. Haz clic en **`Cerrar y cargar en...`** y selecciona **`Tabla`** en una **nueva hoja**. Nombra la hoja `Cruce_IMSS`.

8. Una vez cargada la tabla en la hoja `Cruce_IMSS`, abre el panel de Copilot y escribe el siguiente prompt:

   ```
   En esta tabla de cruce IMSS, identifica todos los empleados donde existe
   una diferencia entre el SBC interno y el SBC determinado por el IMSS
   (columnas SBC_Interno y SBC_IMSS). Para cada diferencia, clasifícala como:
   - "A favor empresa" si SBC_Interno > SBC_IMSS
   - "A favor IMSS" si SBC_IMSS > SBC_Interno
   - "Sin diferencia" si son iguales
   Calcula el importe de diferencia en cuota patronal para cada caso
   (usa la tasa del 17.15% sobre el SBC mensual como aproximación).
   Muestra los resultados ordenados de mayor a menor diferencia monetaria.
   Agrega estas columnas a la tabla.
   ```

9. Copilot generará una propuesta de fórmulas o columnas calculadas. Haz clic en **`Insertar columnas`** para aplicar los cambios a la tabla.

10. Solicita a Copilot un resumen ejecutivo de los hallazgos:

    ```
    Genera un resumen de los hallazgos de la confronta IMSS. Incluye:
    1. Número total de empleados con discrepancia
    2. Importe total de diferencias a favor de la empresa
    3. Importe total de diferencias a favor del IMSS (riesgo de pago)
    4. Los 5 empleados con mayor diferencia monetaria
    5. Recomendación de acción correctiva
    ```

**Resultado esperado:** La hoja `Cruce_IMSS` contiene la tabla consolidada con columnas adicionales de clasificación y cálculo de diferencias. El panel de Copilot muestra un resumen con los hallazgos cuantificados.

**Verificación:** La tabla en `Cruce_IMSS` debe tener el mismo número de filas que la tabla de nómina interna (150 registros). Si hay menos filas, revisar el tipo de combinación en Power Query (debe ser externa izquierda). Confirma que las columnas `Clasificacion_Diferencia` e `Importe_Diferencia_Cuota` fueron creadas correctamente.

---

#### Paso 3: Confronta Infonavit y Detección de Diferencias en Aportaciones

**Objetivo:** Ejecutar el cruce entre la nómina interna y el archivo SINCE de Infonavit para detectar diferencias en el cálculo del 5% de aportación patronal y movimientos de baja no reportados.

**Instrucciones:**

1. En el archivo `P3_Nomina_Interna_Julio2024.xlsx`, crea una nueva hoja llamada `Cruce_Infonavit`.

2. Siguiendo el mismo procedimiento del Paso 2 (pasos 5–7), crea una consulta de combinación entre `Nomina_Interna` y `Confronta_Infonavit`, cargando el resultado en la hoja `Cruce_Infonavit`.

3. Abre el panel de Copilot en la hoja `Cruce_Infonavit` y escribe:

   ```
   Analiza esta tabla de cruce Infonavit. Realiza las siguientes tareas:
   1. Calcula la diferencia entre la aportación Infonavit interna
      (columna Aportacion_Infonavit_Interna) y la aportación determinada
      por Infonavit (columna Aportacion_Infonavit_SINCE).
   2. Identifica empleados con estatus "Baja" en la columna
      Movimiento_Afiliatorio de la nómina interna que aún aparezcan como
      activos en el archivo SINCE (columna Estatus_SINCE = "Activo").
      Estos son casos de baja no reportada.
   3. Marca con "ALERTA: Baja no reportada" los registros del punto 2.
   4. Calcula el importe acumulado de aportaciones en riesgo por bajas
      no reportadas.
   Agrega columnas para cada resultado.
   ```

4. Aplica las columnas sugeridas por Copilot haciendo clic en **`Insertar columnas`**.

5. Para identificar trabajadores con diferencias superiores al 2% (umbral de tolerancia estándar en auditoría), escribe el siguiente prompt:

   ```
   Filtra y resalta los empleados donde la diferencia porcentual entre
   la aportación interna y la de Infonavit sea mayor al 2%.
   Calcula el porcentaje de diferencia como:
   ABS(Aportacion_Infonavit_Interna - Aportacion_Infonavit_SINCE)
   / Aportacion_Infonavit_SINCE * 100
   Ordena los resultados de mayor a menor diferencia porcentual.
   ```

6. Solicita a Copilot que genere un resumen de hallazgos Infonavit:

   ```
   Genera un resumen ejecutivo de los hallazgos de la confronta Infonavit.
   Incluye: número de empleados con diferencia, importe total en riesgo,
   número de bajas no reportadas y su impacto económico estimado.
   ```

7. Copia el texto del resumen generado por Copilot en la hoja `Resumen_Hallazgos` del libro (créala si no existe). Etiqueta la sección como **"Hallazgos Infonavit"**.

**Resultado esperado:** La hoja `Cruce_Infonavit` contiene la tabla con columnas de diferencia calculada, alertas de bajas no reportadas y clasificación por umbral de tolerancia. La hoja `Resumen_Hallazgos` contiene el primer bloque de hallazgos documentados.

**Verificación:** Verifica que la columna `Alerta_Baja_No_Reportada` identifica correctamente los registros donde `Movimiento_Afiliatorio = "Baja"` y `Estatus_SINCE = "Activo"`. Debe haber al menos 3–5 casos en el dataset de práctica (el instructor habrá incluido estos casos intencionalmente).

---

#### Paso 4: Validación de Cumplimiento REPSE con Copilot

**Objetivo:** Usar Copilot para cruzar el listado de proveedores con registro REPSE activo contra los trabajadores en nómina de subcontratistas, detectando incumplimientos en la entrega de información cuatrimestral y trabajadores no reportados.

**Instrucciones:**

1. Abre el archivo `P3_REPSE_Proveedores_Registrados.xlsx`. Este archivo contiene dos hojas:
   - `Proveedores_REPSE`: Listado de proveedores con su número de registro REPSE, fecha de vencimiento y estatus.
   - `Trabajadores_REPSE_Reportados`: Trabajadores reportados por cada proveedor al cliente (empresa auditada).

2. Abre el panel de Copilot en la hoja `Proveedores_REPSE` y escribe:

   ```
   Analiza esta tabla de proveedores REPSE. Identifica:
   1. Proveedores con registro REPSE vencido (fecha de vencimiento anterior
      a la fecha actual: julio 2024).
   2. Proveedores con estatus distinto a "Activo" o "Vigente".
   3. Proveedores sin fecha de último informe cuatrimestral registrada
      (columna Fecha_Ultimo_Informe vacía o nula).
   Marca cada caso con la categoría de riesgo: "ALTO", "MEDIO" o "BAJO"
   según la gravedad del incumplimiento. Agrega la columna "Riesgo_REPSE".
   ```

3. Aplica las columnas sugeridas y luego cambia a la hoja `Trabajadores_REPSE_Reportados`.

4. Ahora abre simultáneamente (en ventanas separadas) el archivo `P3_Nomina_Interna_Julio2024.xlsx` para comparar. En el panel de Copilot de `P3_REPSE_Proveedores_Registrados.xlsx`, escribe:

   ```
   Tengo una tabla de trabajadores reportados por proveedores REPSE.
   Necesito identificar posibles inconsistencias. Por favor:
   1. Agrupa los trabajadores por proveedor (columna RFC_Proveedor)
      y muestra el conteo de trabajadores reportados por cada uno.
   2. Identifica si hay trabajadores con el mismo NSS reportados por
      más de un proveedor en el mismo período (duplicados de NSS).
   3. Señala proveedores que reportaron 0 trabajadores en el período
      pero tienen contratos activos según la columna Contrato_Vigente.
   ```

5. Con los hallazgos de Copilot, crea una nueva hoja llamada `Hallazgos_REPSE` en el archivo `P3_REPSE_Proveedores_Registrados.xlsx` y pide a Copilot:

   ```
   Genera una tabla resumen de hallazgos REPSE con las siguientes columnas:
   RFC_Proveedor, Nombre_Proveedor, Tipo_Incumplimiento, Descripcion,
   Nivel_Riesgo, Accion_Recomendada.
   Incluye todos los incumplimientos identificados en los análisis anteriores.
   ```

6. Copia la tabla generada a la hoja `Resumen_Hallazgos` del libro de nómina interna. Etiqueta la sección como **"Hallazgos REPSE"**.

**Resultado esperado:** El archivo REPSE contiene la hoja `Hallazgos_REPSE` con una tabla estructurada de incumplimientos clasificados por nivel de riesgo. La hoja `Resumen_Hallazgos` del libro principal acumula los hallazgos IMSS, Infonavit y REPSE.

**Verificación:** Confirma que Copilot identificó al menos un proveedor con registro vencido y al menos un caso de trabajador con NSS duplicado (el instructor habrá incluido estos casos en el dataset). Si no aparecen, revisa que la columna de fechas esté formateada como `Fecha` en Excel (no como texto).

---

#### Paso 5: Consolidación de Hallazgos de Seguridad Social en Dashboard Resumen

**Objetivo:** Usar Copilot para crear un dashboard visual en Excel que consolide todos los hallazgos de IMSS, Infonavit y REPSE, cuantificando el riesgo económico total de la auditoría.

**Instrucciones:**

1. En el archivo `P3_Nomina_Interna_Julio2024.xlsx`, ve a la hoja `Resumen_Hallazgos`.

2. Abre el panel de Copilot y escribe:

   ```
   Basándote en los datos de esta hoja que contiene hallazgos de IMSS,
   Infonavit y REPSE, crea una tabla de resumen ejecutivo con las siguientes
   métricas por organismo:
   - Número de empleados/proveedores con incumplimiento
   - Importe total en riesgo (en pesos MXN)
   - Nivel de riesgo predominante (Alto/Medio/Bajo)
   - Prioridad de atención (1=urgente, 2=importante, 3=rutinario)
   Incluye una fila de TOTAL GENERAL al final.
   ```

3. Solicita a Copilot que genere una visualización:

   ```
   Crea un gráfico de barras agrupadas que muestre el importe en riesgo
   por organismo (IMSS, Infonavit, REPSE) y el número de incumplimientos
   detectados. Usa colores: rojo para riesgo alto, amarillo para medio
   y verde para bajo.
   ```

4. Inserta el gráfico en la hoja `Resumen_Hallazgos` y ajusta el tamaño para que sea visible sin hacer scroll.

5. Finalmente, solicita a Copilot:

   ```
   Redacta un párrafo ejecutivo de 5-7 líneas que resuma los hallazgos
   totales de la auditoría de seguridad social (IMSS, Infonavit, REPSE)
   para el período julio 2024. Incluye el importe total en riesgo,
   los principales tipos de incumplimiento detectados y la recomendación
   de acción inmediata más urgente. Usa lenguaje formal y directo.
   ```

6. Copia el párrafo generado en una celda de la hoja `Resumen_Hallazgos` (puedes usar una celda con ajuste de texto o un cuadro de texto).

7. **Guarda el archivo** con `Ctrl + S` antes de continuar con la Sección 3.2.

**Resultado esperado:** La hoja `Resumen_Hallazgos` contiene una tabla consolidada con métricas por organismo, un gráfico de barras con los importes en riesgo y un párrafo ejecutivo de síntesis. El archivo está guardado.

**Verificación:** El gráfico debe mostrar datos para los tres organismos (IMSS, Infonavit, REPSE). Si alguno no aparece, verifica que la tabla de resumen tenga filas para los tres. El párrafo ejecutivo debe mencionar explícitamente los tres organismos y un importe total en pesos MXN.

---

### SECCIÓN 3.2 — Detección de Discrepancias en CFDI y Reporte Ejecutivo

---

#### Paso 6: Análisis de CFDI de Nómina con Copilot en Excel

**Objetivo:** Cargar y analizar los datos extraídos de los archivos XML de CFDI de nómina para identificar discrepancias entre los conceptos timbrados ante el SAT y los registros internos de dispersión de pago.

**Instrucciones:**

1. Abre el archivo `P3_CFDI_Nomina_Muestra_XML.xlsx`. Este archivo contiene los datos clave extraídos de 30 archivos XML de CFDI de nómina, organizados en columnas que representan los nodos principales del XML:

   | Columna | Nodo XML equivalente |
   |---|---|
   | UUID_CFDI | `//cfdi:Comprobante/@UUID` |
   | RFC_Emisor | `//cfdi:Emisor/@Rfc` |
   | NSS_Empleado | `//nomina12:Receptor/@NumSeguridadSocial` |
   | Total_Percepciones_CFDI | `//nomina12:Percepciones/@TotalGravado` + `@TotalExento` |
   | Total_Deducciones_CFDI | `//nomina12:Deducciones/@TotalOtrasDeducciones` |
   | ISR_Retenido_CFDI | `//nomina12:Deducciones/nomina12:Deduccion[@TipoDeduccion='002']` |
   | Neto_CFDI | `//cfdi:Comprobante/@Total` |
   | Estatus_SAT | Campo simulado: "Vigente", "Cancelado", "En proceso cancelación" |

2. Abre también el archivo `P3_Nomina_Dispersada_Julio2024.xlsx` en una segunda ventana de Excel.

3. En el archivo `P3_CFDI_Nomina_Muestra_XML.xlsx`, abre el panel de Copilot y escribe:

   ```
   Analiza esta tabla de CFDI de nómina. Dime:
   1. Cuántos CFDIs tienen estatus "Cancelado" o "En proceso cancelación"
      (columna Estatus_SAT).
   2. Cuántos CFDIs tienen un valor de Total_Percepciones_CFDI igual a cero
      o negativo (posible error de timbrado).
   3. Cuántos CFDIs tienen ISR_Retenido_CFDI igual a cero cuando el
      Total_Percepciones_CFDI es mayor a 10,000 pesos (posible omisión
      de retención).
   4. Presenta los hallazgos en una tabla resumen con el UUID_CFDI
      y el tipo de anomalía detectada.
   ```

4. Aplica las columnas de clasificación de anomalías sugeridas por Copilot.

5. Ahora crea el cruce con la nómina dispersada. Usando Power Query (igual que en el Paso 2), importa la tabla principal de `P3_Nomina_Dispersada_Julio2024.xlsx` como conexión y combínala con la tabla de CFDI usando el NSS como llave de cruce. Carga el resultado en una nueva hoja llamada `Cruce_CFDI_vs_Dispersion`.

6. En la hoja `Cruce_CFDI_vs_Dispersion`, abre el panel de Copilot y escribe:

   ```
   En esta tabla de cruce entre CFDIs timbrados y nómina dispersada,
   identifica las siguientes discrepancias:
   1. Empleados donde el Neto_CFDI difiere del Neto_Dispersado en más
      de 1 peso (diferencias de centavos pueden ignorarse).
   2. Empleados donde el ISR_Retenido_CFDI difiere del ISR_Retenido_Nomina.
   3. Empleados donde el Total_Percepciones_CFDI difiere del
      Total_Percepciones_Nomina en más del 0.5%.
   Para cada discrepancia, calcula el importe de la diferencia y clasifica
   el riesgo como "CRÍTICO" (diferencia > 500 pesos), "MODERADO"
   (100-500 pesos) o "MENOR" (< 100 pesos).
   Agrega columnas: Tipo_Discrepancia, Importe_Diferencia, Nivel_Riesgo_CFDI.
   ```

7. Aplica las columnas sugeridas.

**Resultado esperado:** La hoja `Cruce_CFDI_vs_Dispersion` contiene la tabla consolidada con las discrepancias identificadas, clasificadas por tipo y nivel de riesgo. Los CFDIs con anomalías (cancelados, valores en cero, diferencias de ISR) están marcados.

**Verificación:** La tabla debe mostrar al menos 5 discrepancias (el instructor habrá incluido errores intencionalmente en el dataset). Verifica que la columna `Nivel_Riesgo_CFDI` tenga valores en las tres categorías (CRÍTICO, MODERADO, MENOR). Si todos los registros muestran "Sin discrepancia", verifica que las columnas de neto y percepciones estén correctamente mapeadas en el cruce de Power Query.

---

#### Paso 7: Profundización en Discrepancias Críticas con Copilot Chat

**Objetivo:** Usar Microsoft 365 Copilot Chat para analizar la normativa SAT aplicable a las discrepancias encontradas y obtener orientación sobre los procedimientos de corrección (cancelación y retimbrado de CFDI).

**Instrucciones:**

1. Abre Microsoft Edge y navega a `https://microsoft365.com/copilot` (o accede desde el ícono de Copilot en la barra de Microsoft 365). Asegúrate de estar autenticado con tu cuenta corporativa.

2. En el campo de chat de Copilot, escribe el siguiente prompt contextual:

   ```
   Soy especialista de compensaciones en México. Durante una auditoría de
   CFDI de nómina encontré las siguientes discrepancias:
   1. 3 CFDIs donde el neto timbrado difiere del neto dispersado en más
      de 500 pesos.
   2. 2 CFDIs con ISR retenido igual a cero para empleados con percepciones
      superiores a 15,000 pesos mensuales.
   3. 1 CFDI con estatus "En proceso de cancelación" que ya fue dispersado.

   Basándote en la normativa SAT vigente (Resolución Miscelánea Fiscal 2024
   y complemento de nómina versión 1.2), explícame:
   a) ¿Cuál es el procedimiento correcto para corregir cada tipo de
      discrepancia?
   b) ¿Cuáles son los plazos para cancelar y retimbrar un CFDI de nómina
      sin incurrir en multas?
   c) ¿Qué riesgos fiscales específicos implica cada tipo de error si no
      se corrige?
   ```

3. Lee y analiza la respuesta de Copilot. Copia los puntos más relevantes en un documento de Word temporal o en el bloc de notas.

4. Realiza una pregunta de seguimiento para profundizar en el caso más crítico:

   ```
   Para el caso de los 2 CFDIs con ISR retenido en cero para empleados
   con percepciones altas, ¿esto podría considerarse una práctica de
   evasión fiscal desde la perspectiva del SAT? ¿Qué artículos del
   Código Fiscal de la Federación (CFF) serían aplicables en caso de
   una revisión? ¿Cuál sería la multa estimada?
   ```

5. Vuelve al archivo de Excel `P3_CFDI_Nomina_Muestra_XML.xlsx`. En el panel de Copilot de Excel, en la hoja `Cruce_CFDI_vs_Dispersion`, escribe:

   ```
   Genera una lista de los 10 CFDIs con mayor riesgo fiscal basándote
   en las columnas Nivel_Riesgo_CFDI e Importe_Diferencia. Para cada uno,
   incluye el UUID_CFDI, el NSS del empleado, el tipo de discrepancia,
   el importe de diferencia y una recomendación de acción inmediata
   (Cancelar y retimbrar / Aclaración con el empleado / Revisión contable).
   Presenta el resultado en una tabla ordenada por nivel de riesgo.
   ```

6. Copia la tabla de los 10 CFDIs de mayor riesgo en la hoja `Resumen_Hallazgos` del libro de nómina interna. Etiqueta la sección como **"Hallazgos CFDI / SAT"**.

**Resultado esperado:** Se cuenta con orientación normativa de Copilot Chat sobre los procedimientos de corrección de CFDI y los riesgos fiscales asociados. La hoja `Resumen_Hallazgos` ahora incluye los hallazgos de los tres frentes (IMSS/Infonavit/REPSE y CFDI/SAT).

**Verificación:** La respuesta de Copilot Chat debe mencionar específicamente el complemento de nómina versión 1.2, los plazos de cancelación y al menos un artículo del CFF o de la RMF. Si la respuesta es genérica o no menciona normativa mexicana específica, reformula el prompt añadiendo: *"Responde exclusivamente en el contexto de la legislación fiscal mexicana vigente en 2024"*.

---

#### Paso 8: Generación del Reporte Ejecutivo de Auditoría con Copilot en Word

**Objetivo:** Utilizar Copilot en Word para generar un reporte ejecutivo de auditoría completo, integrando todos los hallazgos de las secciones 3.1 y 3.2, con estructura profesional lista para presentación a la dirección.

**Instrucciones:**

1. Abre el archivo `P3_Plantilla_Reporte_Auditoria.docx` en Microsoft Word. Este archivo contiene la estructura básica del reporte con marcadores de posición (placeholders) para cada sección.

2. Haz clic en el botón **`Copilot`** en la cinta de opciones de Word (pestaña `Inicio` o `Revisar`). Se abrirá el panel de Copilot en Word.

3. Para generar la sección de **Resumen Ejecutivo**, escribe:

   ```
   Redacta el Resumen Ejecutivo de este reporte de auditoría de nómina.
   El contexto es el siguiente:
   - Empresa auditada: Corporativo Ficticios S.A. de C.V. (datos de prueba)
   - Período auditado: Julio 2024
   - Empleados en nómina: 150
   - Hallazgos IMSS: [X] empleados con diferencias en SBC, importe en
     riesgo: $[Y] MXN
   - Hallazgos Infonavit: [X] empleados con diferencias en aportaciones,
     [X] bajas no reportadas, importe en riesgo: $[Y] MXN
   - Hallazgos REPSE: [X] proveedores con incumplimientos, [X] con
     registro vencido
   - Hallazgos CFDI/SAT: [X] CFDIs con discrepancias, [X] con ISR en
     cero, importe en riesgo: $[Y] MXN

   [Sustituye los valores [X] e [Y] con los números reales que obtuviste
   en los pasos anteriores de la práctica]

   El resumen debe ser de 3-4 párrafos, en tono ejecutivo y formal,
   destacando el riesgo total cuantificado y la urgencia de las acciones
   correctivas. Incluye una tabla de "Semáforo de Riesgos" al final del
   resumen con los cuatro organismos y su nivel de riesgo (Rojo/Amarillo/Verde).
   ```

4. Copilot generará el texto. Haz clic en **`Insertar`** para colocarlo en el documento en la sección correspondiente.

5. Para generar la sección de **Hallazgos Detallados por Organismo**, escribe:

   ```
   Redacta la sección "Hallazgos Detallados" del reporte. Para cada uno
   de los cuatro organismos (IMSS, Infonavit, REPSE, SAT/CFDI), incluye:
   a) Metodología de revisión utilizada (confronta de archivos, cruce
      de datos con IA)
   b) Principales hallazgos con datos cuantitativos
   c) Riesgo fiscal o legal asociado
   d) Recomendación específica de corrección con plazo sugerido

   Usa el formato de la plantilla: encabezados de nivel 2 por organismo,
   texto en párrafo y una tabla de hallazgos al final de cada sección.
   Mantén un tono técnico-legal apropiado para presentación a dirección
   y al área jurídica.
   ```

6. Inserta el texto generado en la sección correspondiente del documento.

7. Para generar el **Plan de Acción Correctiva**, escribe:

   ```
   Genera la sección "Plan de Acción Correctiva" del reporte. Crea una
   tabla con las siguientes columnas:
   - Acción correctiva
   - Organismo / Área afectada
   - Responsable sugerido (Rol, no nombre: ej. "Coordinador de Nómina")
   - Plazo de implementación
   - Prioridad (Inmediata / 30 días / 60 días)
   - Indicador de cumplimiento

   Incluye mínimo 8 acciones correctivas basadas en los hallazgos
   identificados en esta auditoría. Ordena por prioridad de mayor a menor.
   ```

8. Inserta la tabla generada en la sección del Plan de Acción.

9. Para el **Cierre del Reporte**, escribe:

   ```
   Redacta el párrafo de conclusiones y las firmas del reporte. Las
   conclusiones deben:
   - Reiterar el importe total en riesgo identificado
   - Destacar que el uso de herramientas de IA (Microsoft Copilot)
     permitió completar la auditoría en un tiempo significativamente
     menor al proceso manual tradicional
   - Recomendar la implementación de un proceso de auditoría continua
     mensual con las mismas herramientas
   - Incluir una declaración de que los datos analizados son ficticios
     y utilizados exclusivamente para fines de capacitación

   Agrega un bloque de firmas para: Auditor de Nómina, Director de RH
   y Dirección General.
   ```

10. Revisa el documento completo. Usa la función **`Copilot > Revisar este documento`** para solicitar mejoras de redacción:

    ```
    Revisa este documento completo y sugiere mejoras en:
    1. Consistencia de tono y estilo (formal, ejecutivo)
    2. Claridad de las recomendaciones
    3. Cualquier inconsistencia numérica que detectes entre secciones
    Muestra las sugerencias como comentarios en el documento.
    ```

11. Acepta o rechaza las sugerencias de Copilot según tu criterio profesional.

12. **Guarda el documento** como `P3_Reporte_Auditoria_Julio2024_[TuNombre].docx` en la carpeta local `C:\Curso_M365_Copilot\Practica3\Entregables\`.

**Resultado esperado:** El documento Word contiene un reporte ejecutivo completo con: Resumen Ejecutivo con semáforo de riesgos, Hallazgos Detallados por los cuatro organismos, Plan de Acción Correctiva con tabla de 8+ acciones y sección de Conclusiones y Firmas. El documento está guardado con el nombre correcto.

**Verificación:** El reporte debe tener mínimo 4 páginas. Verifica que la tabla de semáforo de riesgos esté presente en el Resumen Ejecutivo y que la tabla del Plan de Acción tenga al menos 8 filas. Si Copilot generó texto con marcadores como "[insertar dato]" o "[X]", reemplázalos manualmente con los valores reales de tu análisis.

---

#### Paso 9: Publicación de Evidencias en SharePoint

**Objetivo:** Subir los archivos de entregables al repositorio de SharePoint del curso como evidencia de cumplimiento de la práctica, simulando el flujo real de gestión documental de auditoría.

**Instrucciones:**

1. Abre Microsoft Edge y navega al sitio SharePoint del curso.

2. Ve a la biblioteca: **`Documentos > Práctica 3 > Entregables > [Tu Nombre o Grupo]`**.

3. Si la carpeta con tu nombre no existe, créala: haz clic en **`+ Nuevo > Carpeta`** y nómbrala con tu nombre completo o número de participante.

4. Sube los siguientes archivos a tu carpeta de entregables:

   | Archivo a subir | Descripción |
   |---|---|
   | `P3_Nomina_Interna_Julio2024.xlsx` (versión modificada) | Archivo con hojas Cruce_IMSS, Cruce_Infonavit, Cruce_CFDI_vs_Dispersion y Resumen_Hallazgos |
   | `P3_REPSE_Proveedores_Registrados.xlsx` (versión modificada) | Archivo con hoja Hallazgos_REPSE |
   | `P3_CFDI_Nomina_Muestra_XML.xlsx` (versión modificada) | Archivo con columnas de anomalías y cruce |
   | `P3_Reporte_Auditoria_Julio2024_[TuNombre].docx` | Reporte ejecutivo final |

5. Para cada archivo subido, agrega metadatos en SharePoint:
   - Haz clic en los tres puntos `...` junto al archivo > **`Detalles`**.
   - En el campo **`Descripción`**, escribe: `Entregable Práctica 3 - Auditoría IMSS/Infonavit/REPSE/SAT - [Fecha]`.

6. Verifica que los 4 archivos estén visibles en tu carpeta de entregables en SharePoint.

**Resultado esperado:** Los cuatro archivos de entregables están disponibles en la carpeta de SharePoint del participante con los metadatos correspondientes.

**Verificación:** Abre cada archivo directamente desde SharePoint para confirmar que se cargaron correctamente y que las hojas/secciones de análisis son visibles. Si algún archivo muestra error al abrir, descárgalo y vuelve a subirlo.

---

## 7. Validación y Pruebas

Una vez completados todos los pasos, realiza la siguiente verificación integral de los entregables:

### Lista de Verificación Final

| # | Criterio de validación | Estado |
|---|---|---|
| 1 | El archivo Excel de nómina interna contiene las hojas: `Cruce_IMSS`, `Cruce_Infonavit`, `Cruce_CFDI_vs_Dispersion` y `Resumen_Hallazgos` | ☐ |
| 2 | La hoja `Cruce_IMSS` tiene columnas `Clasificacion_Diferencia` e `Importe_Diferencia_Cuota` con valores calculados | ☐ |
| 3 | La hoja `Cruce_Infonavit` tiene columna `Alerta_Baja_No_Reportada` con al menos 1 alerta activa | ☐ |
| 4 | El archivo REPSE contiene la hoja `Hallazgos_REPSE` con columna `Riesgo_REPSE` (Alto/Medio/Bajo) | ☐ |
| 5 | La hoja `Cruce_CFDI_vs_Dispersion` contiene columnas `Tipo_Discrepancia`, `Importe_Diferencia` y `Nivel_Riesgo_CFDI` | ☐ |
| 6 | La hoja `Resumen_Hallazgos` contiene hallazgos de los 4 organismos (IMSS, Infonavit, REPSE, SAT) | ☐ |
| 7 | El reporte Word tiene mínimo 4 páginas con las 4 secciones principales (Resumen, Hallazgos, Plan de Acción, Conclusiones) | ☐ |
| 8 | El reporte Word incluye tabla de semáforo de riesgos y tabla de Plan de Acción con 8+ filas | ☐ |
| 9 | Los 4 archivos de entregables están subidos a SharePoint en la carpeta del participante | ☐ |
| 10 | Ningún archivo contiene datos reales de empleados (todos son datos ficticios del dataset de práctica) | ☐ |

### Prueba de Calidad del Análisis de Copilot

Para validar que los prompts generaron análisis de calidad (no respuestas genéricas), verifica:

1. **Especificidad numérica:** Los hallazgos en el reporte Word deben incluir importes en pesos MXN específicos, no rangos genéricos.
2. **Referencias normativas:** El reporte debe mencionar al menos una referencia normativa específica (ej. "Ley del Seguro Social, Artículo 27", "Complemento de Nómina versión 1.2", "RMF 2024").
3. **Acciones concretas:** El Plan de Acción debe tener plazos específicos (días calendario), no solo "a la brevedad" o "próximamente".

---

## 8. Solución de Problemas

### Problema 1: Copilot no genera columnas calculadas en Excel y solo muestra texto explicativo

**Síntomas:** Al pedir a Copilot que "agregue columnas" o "calcule diferencias", el panel solo muestra una explicación de cómo hacerlo manualmente, sin insertar nada en la hoja de cálculo. El botón `Insertar columnas` no aparece en la respuesta.

**Causa:** Copilot en Excel solo puede insertar columnas calculadas cuando los datos están formateados como **Tabla de Excel** (no como rango simple). Si los datos son un rango sin formato de tabla, Copilot opera en modo "solo lectura" y no puede modificar la hoja. También puede ocurrir si la tabla tiene celdas combinadas, filas en blanco intermedias o encabezados con caracteres especiales.

**Solución:**
1. Selecciona cualquier celda dentro del rango de datos.
2. Presiona `Ctrl + T`. En el cuadro de diálogo, verifica que el rango sea correcto y que "La tabla tiene encabezados" esté marcado. Haz clic en `Aceptar`.
3. Verifica que la tabla tenga un nombre descriptivo: haz clic en la tabla, ve a `Diseño de tabla` en la cinta y cambia el nombre genérico (ej. "Tabla1") por uno descriptivo (ej. "Nomina_Interna").
4. Cierra y vuelve a abrir el panel de Copilot (`X` en el panel, luego clic en el botón `Copilot`).
5. Repite el prompt original. Ahora debería aparecer el botón `Insertar columnas`.
6. Si el problema persiste, verifica que no haya filas en blanco dentro del rango de datos y que ninguna celda esté combinada.

---

### Problema 2: El cruce de Power Query no produce coincidencias (la tabla combinada muestra valores nulos en todas las columnas de la segunda tabla)

**Síntomas:** Después de ejecutar la combinación de consultas en Power Query entre la nómina interna y el archivo de confronta (IMSS, Infonavit o CFDI), la tabla resultante tiene datos en las columnas de la primera tabla pero todas las columnas de la segunda tabla muestran `null`. El número de coincidencias es 0.

**Causa:** La causa más común es una incompatibilidad de tipos de dato en la columna llave (NSS). Si en una tabla el NSS está almacenado como **número** (sin ceros iniciales) y en la otra como **texto** (con ceros iniciales, ej. "08123456789"), Power Query no los reconoce como iguales aunque visualmente parezcan similares. También puede deberse a espacios en blanco antes o después del valor en una de las tablas.

**Solución:**
1. En el Editor de Power Query, abre cada consulta por separado.
2. Para la columna NSS en cada tabla: haz clic derecho sobre el encabezado de la columna > `Cambiar tipo` > `Texto`. Esto garantiza que ambas columnas sean del mismo tipo.
3. Para eliminar espacios en blanco: con la columna NSS seleccionada, ve a `Transformar` en la cinta del Editor de Power Query > `Formato` > `Recortar`. Esto elimina espacios iniciales y finales.
4. Si el NSS tiene longitud variable (algunos con 10 dígitos, otros con 11), aplica también: `Transformar > Formato > Agregar prefijo` y ajusta la longitud con una columna calculada usando `Text.PadStart([NSS], 11, "0")` para normalizar a 11 caracteres.
5. Cierra el Editor de Power Query guardando los cambios y vuelve a ejecutar la combinación. Ahora debería haber coincidencias.
6. Verifica el resultado: si la tabla combinada sigue mostrando `null`, abre una muestra de 5 registros de cada tabla y compara visualmente los valores NSS para detectar cualquier diferencia de formato no evidente.

---

## 9. Limpieza del Entorno

Al finalizar la práctica, realiza las siguientes acciones para mantener el entorno ordenado y proteger la confidencialidad de los datos ficticios utilizados:

1. **Cierra todos los archivos de Excel y Word** abiertos durante la práctica. Asegúrate de haber guardado todos los cambios antes de cerrar.

2. **Verifica que los entregables estén en SharePoint** (Paso 9 completado) antes de eliminar cualquier archivo local.

3. **Elimina los archivos de trabajo temporales** de la carpeta local:
   ```
   C:\Curso_M365_Copilot\Practica3\
   ```
   Conserva únicamente la subcarpeta `Entregables\` con los archivos finales, en caso de que el instructor solicite revisión adicional.

4. **Cierra el panel de Copilot Chat** en el navegador y cierra las pestañas abiertas de SharePoint.

5. **No compartas** los archivos de práctica (ni los datasets ficticios) fuera del entorno del curso. Aunque los datos son ficticios, la estructura de los archivos y los prompts desarrollados son materiales del curso sujetos a derechos de autor.

6. **Opcional — Borrar historial de Copilot Chat:** Si utilizaste Copilot Chat en el navegador y deseas limpiar el historial de la sesión, haz clic en el ícono de configuración de Copilot y selecciona `Borrar historial de conversación`.

---

## 10. Resumen y Próximos Pasos

### Resumen de la Práctica

En esta práctica de 90 minutos implementaste un flujo completo de auditoría de nómina asistida por IA, cubriendo los cuatro principales frentes regulatorios del marco mexicano:

| Sección | Actividad realizada | Herramienta principal |
|---|---|---|
| **3.1 — IMSS** | Cruce de nómina interna vs. SUA/IDSE; clasificación y cuantificación de diferencias en SBC | Excel + Copilot + Power Query |
| **3.1 — Infonavit** | Confronta de aportaciones patronales; detección de bajas no reportadas en SINCE | Excel + Copilot + Power Query |
| **3.1 — REPSE** | Validación de registros activos, cumplimiento de informes cuatrimestrales y consistencia de trabajadores | Excel + Copilot |
| **3.2 — SAT/CFDI** | Análisis de anomalías en CFDI timbrados; cruce con nómina dispersada; orientación normativa | Excel + Copilot + Copilot Chat |
| **3.2 — Reporte** | Generación de reporte ejecutivo con hallazgos, semáforo de riesgos y plan de acción | Word + Copilot |

### Competencias Desarrolladas

Al completar esta práctica demostraste la capacidad de:

- **Diseñar y ejecutar** cruces de datos multi-fuente usando Power Query y Copilot, reduciendo el tiempo de confronta de días a minutos.
- **Formular prompts especializados** en el dominio de seguridad social y fiscalidad mexicana para obtener análisis precisos y accionables de Copilot.
- **Cuantificar el riesgo fiscal** de las discrepancias encontradas, traduciendo hallazgos técnicos en impacto económico comprensible para la dirección.
- **Generar documentación ejecutiva** de calidad profesional con Copilot en Word, lista para presentación a stakeholders internos y autoridades.

### Reflexión sobre el Impacto de la IA en Auditoría de Nómina

El proceso que realizaste en 90 minutos con Copilot representa típicamente entre 3 y 5 días hábiles de trabajo manual para un equipo de dos especialistas de compensaciones. Esta reducción de tiempo no solo incrementa la eficiencia operativa, sino que permite realizar auditorías con mayor frecuencia (mensual en lugar de trimestral), detectar discrepancias de manera más temprana y reducir significativamente el riesgo de multas y recargos por incumplimientos no detectados a tiempo.

### Próximos Pasos

Con las habilidades de esta práctica como base, en la **Práctica 4** del curso aplicarás Power Automate para automatizar el flujo completo de auditoría, de modo que el proceso de confronta y generación de reportes se ejecute de forma programada sin intervención manual, enviando alertas automáticas por correo cuando se detecten discrepancias que superen los umbrales de riesgo definidos.

### Recursos de Referencia

| Recurso | URL |
|---|---|
| Portal IMSS — Sistema SUA y obligaciones patronales | https://www.imss.gob.mx/patrones/sua |
| Infonavit — Guía SIPARE y aportaciones | https://patronos.infonavit.org.mx/sipare |
| SAT — Complemento de Nómina versión 1.2 | https://www.sat.gob.mx/consultas/01008/conoce-los-esquemas-del-comprobante-de-nomina |
| STPS — Portal REPSE | https://repse.stps.gob.mx |
| Microsoft — Copilot en Excel (documentación oficial) | https://learn.microsoft.com/es-es/copilot/microsoft-365/use-copilot-in-excel |
| Microsoft — Copilot en Word (documentación oficial) | https://learn.microsoft.com/es-es/copilot/microsoft-365/use-copilot-in-word |
| Resolución Miscelánea Fiscal 2024 — DOF | https://www.dof.gob.mx/nota_detalle.php?codigo=5714853&fecha=29/12/2023 |

---

> 📌 **Nota del Instructor:** Antes de la sesión, verifique que el dataset `P3_Confronta_IMSS_SUA_Julio2024.xlsx` incluya intencionalmente al menos 8 registros con diferencias en SBC, 3–5 casos de bajas no reportadas en Infonavit, 2 proveedores REPSE con registro vencido y 5 CFDIs con discrepancias (incluyendo 2 con ISR en cero). Esto garantiza que los participantes encuentren hallazgos reales durante la práctica y no trabajen con datos "perfectos" que no generan aprendizaje práctico.

---
LAB_END---
