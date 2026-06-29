---LAB_START---
LAB_ID: 06-00-01
---MARKDOWN---
# Práctica 6 — Limpieza y Análisis de Bases de Datos Salariales mediante Copilot en Excel

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 90 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Aplicar |
| **Módulo** | Capítulo 6 — Manejo de Grandes Volúmenes de Datos de Compensaciones |
| **Herramienta principal** | Microsoft Excel con Copilot (Microsoft 365) |
| **Datos requeridos** | Dataset ficticio de compensaciones (200–500 registros) proporcionado por el instructor |
| **Cumplimiento normativo** | LFPDPPP — Únicamente datos ficticios o anonimizados |

---

## 2. Descripción General

Esta práctica aplica las capacidades de Microsoft Copilot en Excel para transformar un dataset de compensaciones intencionalmente "sucio" en una base de datos estructurada, confiable y lista para análisis estratégico. El participante ejecutará un ciclo completo de calidad de datos: diagnóstico automatizado, limpieza, normalización de catálogos y análisis de equidad salarial, culminando en un dashboard ejecutivo generado con apoyo de IA. El trabajo se organiza en dos bloques que corresponden a las Lecciones 6.2 y 6.3 del capítulo: **Estructuración de Big Data** y **Modelos Analíticos Masivos**, con Microsoft Copilot actuando como capa transversal de apoyo en cada etapa del proceso.

---

## 3. Objetivos de Aprendizaje

Al finalizar esta práctica, el participante será capaz de:

- [ ] **Aplicar** Copilot en Excel para diagnosticar y corregir problemas de calidad de datos en una base salarial (duplicados, nulos, formatos inconsistentes y errores tipográficos).
- [ ] **Estructurar** una base de compensaciones mediante la normalización de catálogos de puestos, departamentos y niveles salariales usando Copilot y Power Query.
- [ ] **Ejecutar** análisis de equidad salarial por género, antigüedad y área organizacional con Copilot, identificando empleados fuera de banda salarial.
- [ ] **Generar** visualizaciones y un dashboard ejecutivo de compensaciones utilizando tablas dinámicas y gráficas creadas con asistencia de Copilot.
- [ ] **Interpretar** los resultados de los modelos analíticos y formular al menos dos recomendaciones estratégicas sobre bandas salariales o beneficios.

---

## 4. Prerrequisitos

### 4.1 Conocimientos Previos

| Requisito | Nivel esperado |
|---|---|
| Navegación básica en Microsoft Excel (tablas, filtros, ordenamiento) | Básico |
| Comprensión de conceptos de compensaciones (bandas salariales, niveles, beneficios) | Intermedio |
| Haber completado las Prácticas 1 a 5 del curso | Obligatorio |
| Lectura de la Lección 6.1 (Objetivos del Capítulo 6) | Obligatorio |

### 4.2 Acceso y Licenciamiento

| Recurso | Estado requerido |
|---|---|
| Cuenta corporativa Microsoft 365 con licencia **Copilot activa** | ✅ Verificado antes del inicio |
| Microsoft Excel versión 2308 o superior con Copilot habilitado | ✅ Activo |
| OneDrive for Business con espacio disponible (mínimo 500 MB) | ✅ Activo |
| Archivos de práctica del instructor cargados en OneDrive/SharePoint | ✅ Disponibles |
| Acceso a internet estable (mínimo 10 Mbps) | ✅ Verificado |

> ⚠️ **Advertencia crítica:** Copilot en Excel **solo funciona cuando el archivo está guardado en OneDrive for Business o SharePoint Online**. Los archivos guardados localmente no activarán el panel de Copilot. Verifica esto antes de iniciar cualquier paso.

---

## 5. Entorno de Laboratorio

### 5.1 Hardware Mínimo Recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8ª gen / AMD Ryzen 5 | Intel Core i7 / AMD Ryzen 7 |
| RAM | 8 GB | 16 GB |
| Almacenamiento libre | 10 GB | 20 GB |
| Resolución de pantalla | 1366 × 768 | 1920 × 1080 |
| Conexión a internet | 10 Mbps | 25 Mbps |

### 5.2 Software Requerido

| Aplicación | Versión mínima | Verificación |
|---|---|---|
| Microsoft Excel | 2308 (Microsoft 365) | `Archivo > Cuenta > Acerca de Excel` |
| Microsoft Copilot en Excel | Habilitado por admin | Panel lateral visible al abrir Excel |
| Power Query (integrado en Excel) | Incluido en M365 | `Datos > Obtener y transformar datos` |
| Microsoft Edge o Chrome | Edge 120+ / Chrome 120+ | Actualización automática |
| OneDrive for Business | Sincronizado | Icono en bandeja del sistema |

### 5.3 Archivos de Práctica

El instructor debe haber distribuido los siguientes archivos en la carpeta del curso en SharePoint/OneDrive:

| Archivo | Descripción | Registros aprox. |
|---|---|---|
| `Lab06_Dataset_Compensaciones_Sucio.xlsx` | Base salarial con errores intencionales | 300–500 filas |
| `Lab06_Catalogo_Puestos.xlsx` | Catálogo oficial de nombres de puestos | 40–60 puestos |
| `Lab06_Catalogo_Departamentos.xlsx` | Catálogo oficial de departamentos | 15–20 departamentos |
| `Lab06_Bandas_Salariales.xlsx` | Tabla de bandas salariales por nivel y área | 8–10 niveles |
| `Lab06_Dashboard_Plantilla.xlsx` | Plantilla en blanco para el dashboard final | N/A |

### 5.4 Preparación del Entorno (Antes de Iniciar)

Ejecuta los siguientes pasos de configuración **antes** de comenzar el laboratorio:

**Paso A — Verificar Copilot en Excel:**
1. Abre Microsoft Excel desde Microsoft 365.
2. Crea un libro en blanco y guárdalo en OneDrive for Business.
3. Verifica que el botón **Copilot** aparezca en la pestaña **Inicio** de la cinta de opciones (ícono de constelación de puntos).
4. Si no aparece: ve a `Archivo > Opciones > Complementos` y confirma que Copilot no está deshabilitado. Contacta al administrador de TI si el botón sigue ausente.

**Paso B — Descargar archivos de práctica:**
```
1. Abre Microsoft Edge y navega a: https://[tenant].sharepoint.com/sites/CursoCopilotCompensaciones
2. Navega a la carpeta: Documentos > Módulo 6 > Archivos de Práctica
3. Selecciona todos los archivos Lab06_*.xlsx
4. Haz clic en "Descargar" o "Sincronizar con OneDrive"
5. Confirma que los archivos aparecen en tu carpeta OneDrive local
```

**Paso C — Abrir el dataset principal:**
1. Abre `Lab06_Dataset_Compensaciones_Sucio.xlsx` desde OneDrive (no desde la carpeta local descargada directamente).
2. Confirma que la barra de título muestra el ícono de nube de OneDrive junto al nombre del archivo.
3. Haz clic en **Copilot** en la cinta de opciones para abrir el panel lateral. Si aparece el panel de chat, el entorno está listo.

---

## 6. Desarrollo Paso a Paso

### BLOQUE A — Estructuración de Big Data para Compensaciones (Lección 6.2)
> **Tiempo estimado:** 45 minutos

---

### Paso 1: Diagnóstico Inicial de Calidad del Dataset

**Objetivo:** Utilizar Copilot en Excel para obtener un diagnóstico automático de los problemas de calidad presentes en el dataset de compensaciones antes de realizar cualquier corrección manual.

#### Instrucciones

1. Con el archivo `Lab06_Dataset_Compensaciones_Sucio.xlsx` abierto en Excel y guardado en OneDrive, haz clic en el botón **Copilot** en la pestaña **Inicio**.

2. Selecciona el rango completo de datos (incluyendo encabezados). Puedes usar `Ctrl + Shift + Fin` para seleccionar hasta la última celda con datos.

3. En el panel de Copilot, escribe el siguiente prompt:

   ```
   Analiza esta tabla de datos de compensaciones y genera un diagnóstico 
   completo de calidad de datos. Identifica: (1) columnas con valores nulos 
   o vacíos y el porcentaje que representan, (2) posibles registros duplicados 
   basados en ID de empleado, (3) columnas con formatos inconsistentes 
   (fechas, montos, texto), (4) valores atípicos en las columnas de salario 
   base y salario total. Presenta los resultados en una tabla resumen.
   ```

4. Espera la respuesta de Copilot (aproximadamente 15–30 segundos).

5. Lee el diagnóstico completo. Copilot generará una tabla con los hallazgos y posiblemente sugerirá insertar dicha tabla en una nueva hoja. Acepta la sugerencia haciendo clic en **Insertar en una hoja nueva**.

6. Renombra la nueva hoja como `Diagnóstico_Calidad`.

7. Vuelve a la hoja del dataset original y escribe un segundo prompt de seguimiento:

   ```
   ¿Cuántas columnas tiene esta tabla y cuáles son sus nombres exactos? 
   Lista también los tipos de datos detectados en cada columna.
   ```

8. Documenta mentalmente (o en un bloc de notas) los 3 problemas más críticos identificados por Copilot. Los usarás en los siguientes pasos.

#### Resultado Esperado

- Una hoja `Diagnóstico_Calidad` con una tabla que incluya al menos: nombre de columna, tipo de problema, número de registros afectados y porcentaje del total.
- Identificación de al menos 4–6 tipos de problemas distintos en el dataset (duplicados, nulos, formatos de fecha inconsistentes, errores tipográficos en nombres de puestos, valores de salario en formato texto, etc.).

#### Verificación

✅ La hoja `Diagnóstico_Calidad` existe y contiene una tabla con mínimo 5 filas de hallazgos.
✅ Copilot identificó al menos una columna con valores nulos y al menos un grupo de registros duplicados.
✅ El panel de Copilot sigue activo y muestra el historial del diagnóstico.

---

### Paso 2: Eliminación de Duplicados y Corrección de Valores Nulos

**Objetivo:** Aplicar las correcciones de duplicados y valores nulos identificados en el diagnóstico, usando Copilot para generar las fórmulas y pasos necesarios, y ejecutarlas directamente en el dataset.

#### Instrucciones

1. En el panel de Copilot, escribe:

   ```
   Basándote en el diagnóstico anterior, ayúdame a eliminar los registros 
   duplicados de esta tabla usando la columna "ID_Empleado" como identificador 
   único. Muéstrame los pasos exactos para hacerlo en Excel sin perder datos 
   válidos. Primero quiero ver cuáles son los duplicados antes de eliminarlos.
   ```

2. Copilot sugerirá resaltar duplicados con formato condicional o crear una columna auxiliar. Sigue las instrucciones que proporcione. El proceso típico será:
   - Copilot insertará una columna auxiliar `CONTAR.SI` para marcar duplicados.
   - Aplica el filtro para ver solo las filas marcadas como duplicadas.
   - Revisa visualmente 3–5 registros duplicados para confirmar que son verdaderos duplicados.

3. Una vez confirmados, escribe en Copilot:

   ```
   Confirmo que los duplicados identificados son válidos. ¿Cómo elimino 
   estas filas duplicadas de forma segura usando la herramienta nativa 
   de Excel "Quitar duplicados"? Guíame paso a paso.
   ```

4. Sigue los pasos indicados:
   - Ve a `Datos > Herramientas de datos > Quitar duplicados`.
   - En el cuadro de diálogo, selecciona únicamente la columna `ID_Empleado`.
   - Haz clic en **Aceptar** y anota el número de duplicados eliminados.

5. Para los valores nulos, escribe en Copilot:

   ```
   La columna "Departamento" tiene valores vacíos. Genera una fórmula 
   para identificar todas las filas donde Departamento esté vacío y 
   sugiéreme cómo rellenarlos usando el valor "SIN_ASIGNAR" como 
   valor provisional, para no perder los registros durante el análisis.
   ```

6. Aplica la corrección sugerida. Si Copilot propone usar `Buscar y reemplazar` o una fórmula `SI(ESBLANCO(...))`, ejecútala.

7. Repite el proceso para cualquier otra columna crítica con nulos (típicamente: `Nivel_Salarial`, `Fecha_Ingreso`, `Género`).

#### Resultado Esperado

- El dataset no contiene registros con `ID_Empleado` duplicado.
- Las columnas críticas (`Departamento`, `Nivel_Salarial`, `Género`) no tienen celdas vacías; los nulos fueron reemplazados por valores provisionales documentados.
- Una nota en la hoja `Diagnóstico_Calidad` registra cuántos duplicados se eliminaron y qué columnas recibieron valores provisionales.

#### Verificación

✅ `Datos > Quitar duplicados` en `ID_Empleado` reporta 0 duplicados al ejecutarse por segunda vez.
✅ Un filtro en la columna `Departamento` no muestra celdas en blanco.
✅ El conteo de filas del dataset es menor al original (se eliminaron duplicados).

---

### Paso 3: Estandarización de Formatos — Fechas, Montos y Texto

**Objetivo:** Corregir inconsistencias de formato en columnas de fecha, salario y texto libre usando Copilot para generar las transformaciones necesarias y Power Query para aplicarlas de forma masiva.

#### Instrucciones

**Sección 3A — Corrección de formatos de fecha:**

1. En Copilot, escribe:

   ```
   La columna "Fecha_Ingreso" tiene fechas en múltiples formatos: 
   algunos registros usan DD/MM/YYYY, otros MM-DD-YYYY y algunos 
   tienen el año en dos dígitos. Genera una fórmula de Excel que 
   estandarice todos los valores al formato DD/MM/YYYY y los convierta 
   en valores de fecha reales (no texto).
   ```

2. Copilot generará una fórmula combinando `TEXTO`, `FECHANUMERO` o `SI` con funciones de texto. Copia la fórmula sugerida en una columna auxiliar `Fecha_Ingreso_Limpia`.

3. Una vez verificada la fórmula en 10 filas de muestra, selecciona la columna auxiliar, cópiala y pégala como **Valores** sobre la columna original `Fecha_Ingreso`.

4. Elimina la columna auxiliar.

**Sección 3B — Corrección de montos salariales:**

5. Escribe en Copilot:

   ```
   La columna "Salario_Base_MXN" tiene inconsistencias: algunos valores 
   incluyen el símbolo "$" y comas como separadores de miles (ej. $15,000.00), 
   otros son números puros y algunos están en formato texto. Genera una 
   fórmula para limpiar esta columna y convertir todos los valores a 
   números enteros sin símbolo de moneda ni separadores de texto.
   ```

6. Aplica la fórmula en una columna auxiliar `Salario_Base_Limpio`, verifica con 10 filas y reemplaza la columna original.

**Sección 3C — Normalización de texto en nombres de empleados:**

7. Escribe en Copilot:

   ```
   La columna "Nombre_Completo" tiene empleados con nombres en mayúsculas, 
   minúsculas y combinaciones mixtas. Genera una fórmula para estandarizar 
   todos los nombres en formato "Nombre Propio" (primera letra de cada 
   palabra en mayúscula, resto en minúscula). También identifica si hay 
   espacios extra al inicio o al final de los nombres.
   ```

8. Aplica la función `NOMPROPIO(ESPACIOS(celda))` sugerida por Copilot en la columna auxiliar y reemplaza los valores originales.

**Sección 3D — Uso de Power Query para transformaciones masivas:**

9. Ve a `Datos > Obtener y transformar datos > Desde tabla o rango`.

10. En el Editor de Power Query, escribe en el cuadro de búsqueda o usa la interfaz para:
    - Seleccionar la columna `RFC_Empleado` → clic derecho → **Transformar** → **MAYÚSCULAS** (los RFC deben estar en mayúsculas).
    - Seleccionar la columna `CURP_Empleado` → **Transformar** → **MAYÚSCULAS**.
    - Seleccionar columnas de salario → **Transformar** → **Tipo de datos: Número decimal**.

11. Haz clic en **Cerrar y cargar** para aplicar las transformaciones al dataset.

#### Resultado Esperado

- Columna `Fecha_Ingreso` con todas las fechas en formato `DD/MM/YYYY` reconocido como fecha por Excel.
- Columna `Salario_Base_MXN` con valores numéricos puros (sin texto, sin símbolos).
- Columna `Nombre_Completo` con formato de nombre propio consistente.
- Columnas `RFC_Empleado` y `CURP_Empleado` en mayúsculas uniformes.

#### Verificación

✅ Al aplicar `=TIPO(A2)` en una celda junto a `Fecha_Ingreso`, el resultado es `1` (número/fecha), no `2` (texto).
✅ `=SUMA(Salario_Base_MXN)` produce un resultado numérico sin errores `#VALOR!`.
✅ Un filtro en `Nombre_Completo` no muestra variaciones del mismo nombre con distintas mayúsculas.

---

### Paso 4: Normalización de Catálogos — Puestos y Departamentos

**Objetivo:** Estandarizar los valores de las columnas `Puesto` y `Departamento` del dataset contra los catálogos oficiales proporcionados, utilizando Copilot para identificar discrepancias y Power Query para aplicar la normalización masiva.

#### Instrucciones

1. Abre el archivo `Lab06_Catalogo_Puestos.xlsx` en una ventana separada de Excel. Observa la estructura: columna `ID_Puesto` y columna `Nombre_Puesto_Oficial`.

2. Regresa al dataset principal. En Copilot, escribe:

   ```
   Tengo una columna "Puesto" en mi dataset que puede contener 
   variaciones no estandarizadas de los nombres de puestos (abreviaciones, 
   errores tipográficos, nombres anteriores). Necesito compararla contra 
   un catálogo oficial. ¿Cuál es la mejor estrategia en Excel para 
   identificar los valores de "Puesto" que NO coinciden exactamente 
   con el catálogo? Sugiere una fórmula usando BUSCARV o COINCIDIR.
   ```

3. Copilot sugerirá una fórmula similar a:
   ```excel
   =SI(ESNOD(COINCIDIR(B2,Catalogo_Puestos!$B$2:$B$60,0)),"NO ENCONTRADO","OK")
   ```
   Aplica esta fórmula en una columna auxiliar `Validación_Puesto`.

4. Filtra la columna `Validación_Puesto` por el valor `"NO ENCONTRADO"`. Copia la lista de puestos no encontrados.

5. En Copilot, pega la lista de puestos no encontrados y escribe:

   ```
   Estos son los valores de puesto que no coinciden con el catálogo oficial: 
   [pega aquí la lista]. El catálogo oficial incluye estos puestos: 
   [pega los nombres del catálogo]. ¿Puedes hacer una correspondencia 
   probable entre los valores del dataset y el catálogo oficial, 
   considerando similitud fonética y abreviaciones comunes en RH mexicano?
   ```

6. Copilot generará una tabla de correspondencias sugeridas (ej. `"Aux. Contab."` → `"Auxiliar de Contabilidad"`). Revisa cada sugerencia y confirma o corrige manualmente.

7. Con la tabla de correspondencias validada, ve a `Datos > Power Query > Desde tabla` en el dataset.

8. En Power Query, usa `Transformar > Reemplazar valores` para aplicar cada correspondencia de la tabla validada.

9. Repite el proceso completo para la columna `Departamento` usando `Lab06_Catalogo_Departamentos.xlsx`.

10. Al finalizar, escribe en Copilot:

    ```
    Después de normalizar las columnas "Puesto" y "Departamento", 
    ¿cuántos valores únicos quedan en cada columna? Genera un conteo 
    de frecuencia para ambas columnas y muéstralo en una tabla.
    ```

#### Resultado Esperado

- La columna `Puesto` contiene únicamente valores que coinciden exactamente con el catálogo oficial.
- La columna `Departamento` está completamente normalizada contra el catálogo.
- Una tabla de frecuencia muestra la distribución de empleados por puesto y por departamento.
- La columna auxiliar `Validación_Puesto` muestra `"OK"` en el 100% de los registros.

#### Verificación

✅ Filtrar `Validación_Puesto` por `"NO ENCONTRADO"` devuelve 0 resultados.
✅ Un recuento de valores únicos en `Puesto` coincide con el número de puestos en el catálogo oficial (o menos).
✅ No hay variaciones ortográficas del mismo departamento en la columna `Departamento`.

---

### BLOQUE B — Modelos Analíticos Masivos para Optimización de Compensaciones (Lección 6.3)
> **Tiempo estimado:** 40 minutos

---

### Paso 5: Análisis de Equidad Salarial por Género y Área

**Objetivo:** Usar Copilot en Excel para ejecutar un análisis de equidad salarial que identifique brechas de compensación por género dentro de los mismos niveles y áreas organizacionales.

#### Instrucciones

1. Asegúrate de estar trabajando en el dataset ya limpio (resultado del Bloque A). Si guardaste una copia limpia, ábrela ahora.

2. En el panel de Copilot, escribe:

   ```
   Analiza la distribución salarial de esta tabla comparando el 
   "Salario_Base_MXN" entre empleados por género (columna "Género") 
   dentro de cada combinación de "Nivel_Salarial" y "Departamento". 
   Calcula: (1) salario promedio por género en cada nivel, 
   (2) brecha salarial de género en porcentaje, (3) número de 
   empleados en cada grupo. Presenta los resultados como tabla 
   y destaca los grupos donde la brecha supera el 5%.
   ```

3. Copilot generará la tabla de análisis. Acepta la opción de **Insertar tabla dinámica** si la ofrece, o copia los resultados a una nueva hoja llamada `Análisis_Equidad`.

4. Escribe un segundo prompt para profundizar:

   ```
   De los grupos donde detectaste brecha salarial superior al 5%, 
   ¿cuáles son los tres casos más críticos? Para cada uno, indica 
   el departamento, nivel salarial, género con salario menor, 
   diferencia en pesos mexicanos y el número de empleados afectados.
   ```

5. Copilot presentará los casos más críticos. Documenta estos hallazgos en la hoja `Análisis_Equidad`.

6. Solicita a Copilot que cree una visualización:

   ```
   Crea una gráfica de barras agrupadas que compare el salario 
   promedio por género en cada nivel salarial. Usa colores 
   diferenciados para cada género y agrega etiquetas con los 
   valores promedio en cada barra.
   ```

7. Inserta la gráfica generada en la hoja `Análisis_Equidad`.

#### Resultado Esperado

- Hoja `Análisis_Equidad` con tabla de brechas salariales por género, nivel y departamento.
- Identificación de al menos 2–3 grupos con brecha superior al 5%.
- Gráfica de barras agrupadas comparando salarios promedio por género en cada nivel.

#### Verificación

✅ La tabla de análisis incluye columnas: Departamento, Nivel, Género, Salario Promedio, Brecha %, N° Empleados.
✅ La gráfica está insertada en la hoja `Análisis_Equidad` y es legible.
✅ Los cálculos de brecha porcentual son matemáticamente correctos (verifica manualmente 2 filas).

---

### Paso 6: Análisis de Dispersión de Bandas Salariales e Identificación de Empleados Fuera de Banda

**Objetivo:** Cruzar los salarios del dataset con las bandas salariales de referencia para identificar empleados cuyo salario está por debajo del mínimo o por encima del máximo de su banda, usando Copilot para automatizar el análisis.

#### Instrucciones

1. Abre `Lab06_Bandas_Salariales.xlsx` y observa su estructura: columnas `Nivel_Salarial`, `Salario_Minimo_MXN`, `Salario_Medio_MXN`, `Salario_Maximo_MXN`.

2. En el dataset principal, agrega las columnas de bandas mediante BUSCARV. En Copilot, escribe:

   ```
   Necesito agregar tres columnas a mi dataset: "Banda_Min", 
   "Banda_Max" y "Banda_Medio", trayendo los valores correspondientes 
   desde una tabla de bandas salariales usando la columna 
   "Nivel_Salarial" como clave de búsqueda. Genera las fórmulas 
   BUSCARV necesarias para las tres columnas.
   ```

3. Copilot generará tres fórmulas BUSCARV. Aplícalas en columnas nuevas al final del dataset.

4. Agrega una columna `Estatus_Banda` con el siguiente prompt a Copilot:

   ```
   Crea una fórmula para la columna "Estatus_Banda" que clasifique 
   cada empleado en una de estas tres categorías basándose en su 
   "Salario_Base_MXN" comparado con "Banda_Min" y "Banda_Max": 
   "BAJO BANDA" si el salario es menor al mínimo, 
   "SOBRE BANDA" si supera el máximo, 
   "EN BANDA" si está dentro del rango.
   ```

5. Aplica la fórmula `SI` anidada generada por Copilot en la columna `Estatus_Banda`.

6. Escribe en Copilot:

   ```
   Analiza la columna "Estatus_Banda" y genera un resumen que muestre: 
   (1) cuántos empleados están en cada categoría (BAJO BANDA, EN BANDA, 
   SOBRE BANDA) y qué porcentaje representan del total, 
   (2) el costo mensual adicional para llevar a todos los empleados 
   "BAJO BANDA" al salario mínimo de su banda, 
   (3) los tres departamentos con mayor número de empleados fuera de banda.
   ```

7. Inserta los resultados en una nueva hoja `Análisis_Bandas`.

8. Solicita una visualización adicional:

   ```
   Genera un gráfico de dispersión (scatter plot) donde el eje X 
   sea el nivel salarial (numérico del 1 al 10), el eje Y sea el 
   salario base en MXN, y se muestren líneas horizontales de 
   referencia para el mínimo, medio y máximo de cada banda. 
   Colorea los puntos según su "Estatus_Banda".
   ```

#### Resultado Esperado

- Columnas `Banda_Min`, `Banda_Max`, `Banda_Medio` y `Estatus_Banda` correctamente calculadas en el dataset.
- Hoja `Análisis_Bandas` con resumen de distribución por estatus y costo estimado de corrección.
- Gráfico de dispersión que visualiza la posición de cada empleado respecto a su banda salarial.

#### Verificación

✅ La suma de empleados en las tres categorías (`BAJO BANDA + EN BANDA + SOBRE BANDA`) es igual al total de registros del dataset.
✅ El costo calculado para llevar empleados al mínimo de banda es positivo y razonable (no hay errores `#N/A` ni `#VALOR!`).
✅ El gráfico de dispersión muestra claramente tres grupos de puntos diferenciados por color.

---

### Paso 7: Modelado de Escenarios de Incremento Salarial

**Objetivo:** Usar Copilot en Excel para modelar al menos tres escenarios de incremento salarial (inflación, meritocracia, nivelación de banda) y calcular su impacto presupuestal total.

#### Instrucciones

1. Crea una nueva hoja llamada `Escenarios_Incremento`.

2. En Copilot, escribe:

   ```
   Necesito modelar tres escenarios de incremento salarial para 
   el próximo ejercicio fiscal. Crea una tabla en esta hoja con 
   los siguientes escenarios para cada empleado del dataset:
   
   Escenario 1 - Inflación General: 
   Incremento del 6.5% a todos los empleados "EN BANDA" y 4% 
   a los "SOBRE BANDA". Los "BAJO BANDA" reciben incremento 
   hasta el mínimo de su banda.
   
   Escenario 2 - Meritocracia: 
   Los empleados con "Calificación_Desempeño" >= 4 reciben 8%, 
   calificación 3 reciben 5%, calificación <= 2 reciben 3%.
   
   Escenario 3 - Combinado: 
   Promedio ponderado de los Escenarios 1 y 2 (60% peso 
   Escenario 1, 40% peso Escenario 2).
   
   Para cada escenario, calcula el nuevo salario y el incremento 
   en pesos. Al final, muestra el costo total mensual adicional 
   de nómina para cada escenario.
   ```

3. Copilot generará las fórmulas para cada escenario. Aplícalas en columnas separadas: `Salario_Esc1`, `Salario_Esc2`, `Salario_Esc3`, `Incremento_Esc1_MXN`, `Incremento_Esc2_MXN`, `Incremento_Esc3_MXN`.

4. Agrega una fila de totales al final de la tabla con `SUMA` de cada columna de incremento.

5. Escribe en Copilot:

   ```
   Compara los tres escenarios de incremento. ¿Cuál tiene mayor 
   impacto presupuestal? ¿Cuál atiende mejor el problema de 
   empleados "BAJO BANDA"? ¿Cuál genera mayor equidad salarial 
   por género basándote en el análisis previo? Presenta tu 
   análisis como un resumen ejecutivo de 5 puntos.
   ```

6. Copia el resumen ejecutivo generado por Copilot en la hoja `Escenarios_Incremento`, debajo de la tabla de datos.

#### Resultado Esperado

- Hoja `Escenarios_Incremento` con tres columnas de nuevos salarios y tres columnas de incrementos en pesos.
- Fila de totales que muestra el costo mensual adicional de cada escenario.
- Resumen ejecutivo de 5 puntos generado por Copilot comparando los tres escenarios.

#### Verificación

✅ Los valores de `Salario_Esc1` son mayores o iguales a los de `Salario_Base_MXN` en todos los registros.
✅ El costo total del Escenario 2 (meritocracia) es diferente al del Escenario 1 (no son iguales, lo que confirma que las fórmulas son distintas).
✅ El resumen ejecutivo menciona explícitamente los tres escenarios y hace una recomendación.

---

### Paso 8: Generación del Dashboard Ejecutivo de Compensaciones

**Objetivo:** Consolidar todos los análisis previos en un dashboard ejecutivo visual y navegable, usando Copilot para automatizar la creación de las visualizaciones clave y estructurar la presentación para la dirección.

#### Instrucciones

1. Abre el archivo `Lab06_Dashboard_Plantilla.xlsx` desde OneDrive.

2. En Copilot, escribe:

   ```
   Voy a crear un dashboard ejecutivo de compensaciones. 
   Necesito las siguientes secciones en hojas separadas o 
   en una sola hoja con paneles visuales:
   
   Panel 1 - Resumen General: 
   Total de empleados, masa salarial mensual total, 
   salario promedio general, distribución por género (%).
   
   Panel 2 - Distribución por Bandas: 
   Gráfico de dona o barras con % de empleados en cada 
   estatus de banda (BAJO/EN/SOBRE), costo de nivelación.
   
   Panel 3 - Equidad Salarial: 
   Gráfico de barras comparando salario promedio por género 
   en los 5 niveles salariales más poblados.
   
   Panel 4 - Escenarios de Incremento: 
   Tabla comparativa de los 3 escenarios con costo total 
   y número de empleados beneficiados por cada uno.
   
   ¿Qué tipo de gráficas recomiendas para cada panel y 
   cómo debo estructurar los datos fuente para cada una?
   ```

3. Sigue las recomendaciones de Copilot para estructurar los datos fuente. Típicamente te pedirá crear tablas de resumen en hojas intermedias que alimenten los gráficos.

4. Crea cada gráfico siguiendo las instrucciones de Copilot. Para cada uno:
   - Selecciona los datos fuente indicados.
   - Inserta el tipo de gráfico recomendado (`Insertar > Gráficos`).
   - Aplica el estilo y colores sugeridos.
   - Agrega título descriptivo y etiquetas de datos.

5. En la hoja principal del dashboard, organiza los cuatro paneles en una cuadrícula 2×2.

6. Escribe en Copilot para generar el texto de conclusiones:

   ```
   Basándote en todos los análisis realizados en esta sesión 
   (diagnóstico de calidad, equidad salarial, análisis de bandas 
   y escenarios de incremento), redacta un párrafo ejecutivo de 
   máximo 150 palabras que resuma los 3 hallazgos más importantes 
   y las 2 recomendaciones prioritarias para la dirección de 
   Recursos Humanos. Usa lenguaje ejecutivo formal.
   ```

7. Inserta el párrafo generado en el dashboard como un cuadro de texto en la parte superior.

8. Guarda el dashboard en OneDrive con el nombre:
   ```
   Dashboard_Compensaciones_[TuNombre]_[Fecha].xlsx
   ```

#### Resultado Esperado

- Dashboard con 4 paneles visuales claramente identificados.
- Cada panel contiene al menos un gráfico y una tabla de datos de soporte.
- Párrafo ejecutivo de conclusiones y recomendaciones en la parte superior del dashboard.
- Archivo guardado en OneDrive con el nombre correcto.

#### Verificación

✅ El dashboard es navegable sin necesidad de ir a otras hojas para entender los hallazgos.
✅ Todos los gráficos tienen títulos descriptivos y etiquetas de datos visibles.
✅ El párrafo ejecutivo menciona hallazgos específicos del dataset (no texto genérico).
✅ El archivo aparece en OneDrive con el nombre correcto y la fecha actual.

---

## 7. Validación y Pruebas Finales

Al completar todos los pasos, realiza las siguientes verificaciones de cierre para confirmar que el laboratorio fue completado exitosamente:

### Lista de Verificación Final

| # | Verificación | Método | Estado |
|---|---|---|---|
| 1 | El dataset limpio no tiene duplicados en `ID_Empleado` | `Datos > Quitar duplicados` → resultado: 0 duplicados | ☐ |
| 2 | Todas las columnas críticas tienen el tipo de dato correcto | `=TIPO()` en celdas de muestra | ☐ |
| 3 | Las columnas `Puesto` y `Departamento` están 100% normalizadas | Filtro de `Validación_Puesto` → 0 "NO ENCONTRADO" | ☐ |
| 4 | La columna `Estatus_Banda` clasifica correctamente a todos los empleados | Suma de tres categorías = total de registros | ☐ |
| 5 | Los tres escenarios de incremento producen costos distintos | Comparar totales de `Incremento_Esc1`, `Esc2`, `Esc3` | ☐ |
| 6 | El dashboard contiene los 4 paneles con gráficos y datos | Revisión visual del archivo de dashboard | ☐ |
| 7 | El archivo de dashboard está guardado en OneDrive | Verificar ícono de nube en barra de título | ☐ |
| 8 | El historial de Copilot muestra al menos 10 prompts ejecutados | Desplazarse por el panel de Copilot | ☐ |

### Prueba de Integridad de Datos

Ejecuta esta prueba rápida para confirmar la integridad del dataset final:

```excel
// En una celda vacía del dataset limpio, escribe:
=CONTARA(ID_Empleado) - SUMA(CONTAR.SI(ID_Empleado,ID_Empleado)/CONTAR.SI(ID_Empleado,ID_Empleado))

// El resultado debe ser 0 (cero duplicados)
// Si el resultado es mayor a 0, regresa al Paso 2
```

```excel
// Verifica que la masa salarial sea coherente:
=SUMA(Salario_Base_MXN)

// El resultado debe ser un número positivo entre 
// $3,000,000 y $25,000,000 MXN para un dataset de 300-500 empleados
// Si es menor a $1,000,000 o mayor a $50,000,000, hay errores de formato
```

---

## 8. Solución de Problemas

### Problema 1: El botón de Copilot no aparece en la cinta de opciones de Excel

**Síntoma:** Al abrir Excel, la pestaña **Inicio** no muestra el ícono de Copilot (constelación de puntos). El panel lateral de Copilot no se activa al hacer clic en ninguna opción del menú.

**Causa probable:** El archivo de Excel está guardado localmente (no en OneDrive/SharePoint), la licencia de Microsoft 365 Copilot no está asignada al usuario, o la versión de Excel es anterior a la 2308.

**Solución paso a paso:**
1. Verifica primero la ubicación del archivo: la barra de título debe mostrar el ícono de nube ☁️ de OneDrive. Si no aparece, ve a `Archivo > Guardar como > OneDrive - [Nombre de tu organización]` y guarda el archivo ahí.
2. Cierra y vuelve a abrir el archivo desde OneDrive (no desde la carpeta local).
3. Si el botón sigue sin aparecer, verifica la versión de Excel: `Archivo > Cuenta > Acerca de Excel`. Si la versión es anterior a 2308, haz clic en `Actualizar ahora`.
4. Si la versión es correcta y el archivo está en OneDrive, el problema es de licencia. Ve a `https://portal.office.com`, inicia sesión y verifica que tu cuenta muestre "Microsoft 365 Copilot" en la lista de aplicaciones. Si no aparece, contacta al administrador de TI para que asigne la licencia desde el Centro de Administración de Microsoft 365 (`admin.microsoft.com > Usuarios > Licencias`).
5. Después de que el administrador asigne la licencia, espera 15–30 minutos, cierra Excel completamente y vuelve a abrirlo.

---

### Problema 2: Copilot genera fórmulas con errores `#N/A` o `#VALOR!` al aplicar BUSCARV para las bandas salariales

**Síntoma:** Al aplicar las fórmulas BUSCARV generadas por Copilot en el Paso 6 para traer los valores de bandas salariales, varias celdas muestran el error `#N/A`. El error aparece incluso en registros donde el `Nivel_Salarial` parece correcto visualmente.

**Causa probable:** Los valores de `Nivel_Salarial` en el dataset y en el catálogo de bandas tienen tipos de datos distintos (uno es texto y el otro es número), o hay espacios invisibles al inicio/final de los valores de nivel que impiden la coincidencia exacta. También puede ocurrir si el rango de búsqueda del BUSCARV no está fijo con referencias absolutas.

**Solución paso a paso:**
1. Verifica el tipo de dato de `Nivel_Salarial` en el dataset: selecciona una celda de esa columna y observa si el valor está alineado a la izquierda (texto) o a la derecha (número). Haz lo mismo en el catálogo de bandas.
2. Si los tipos son distintos, estandariza ambos: en Copilot, escribe: `"La columna Nivel_Salarial en mi dataset tiene valores como texto (ej. '3') pero el catálogo usa números. Genera una fórmula para convertir la columna a número usando VALOR() y otra para el catálogo."` Aplica las conversiones antes de ejecutar el BUSCARV.
3. Para eliminar espacios invisibles, aplica `=ESPACIOS(celda)` en una columna auxiliar de `Nivel_Salarial` tanto en el dataset como en el catálogo, y usa esas columnas limpias como base del BUSCARV.
4. Verifica que las referencias del rango de búsqueda en el BUSCARV usen `$` para fijar las filas y columnas (ej. `$A$2:$C$15` en lugar de `A2:C15`). En Copilot, pide: `"Revisa la fórmula BUSCARV que generaste y confirma que las referencias al rango de la tabla de bandas estén fijas con signos de dólar."` 
5. Si después de estos pasos aún hay errores `#N/A`, usa `BUSCARX` en lugar de `BUSCARV` (disponible en Excel 365): en Copilot escribe: `"Convierte las fórmulas BUSCARV a BUSCARX para mayor robustez ante errores."` BUSCARX maneja mejor las discrepancias de tipo de dato.

---

## 9. Limpieza del Entorno

Al finalizar el laboratorio, realiza los siguientes pasos para mantener el entorno ordenado y cumplir con las políticas de manejo de datos del curso:

### 9.1 Organización de Archivos en OneDrive

```
1. En OneDrive, navega a tu carpeta de trabajo del curso
2. Crea una subcarpeta: "Lab06_Completado_[TuNombre]"
3. Mueve los siguientes archivos a esa carpeta:
   - Lab06_Dataset_Compensaciones_Limpio.xlsx (dataset final limpio)
   - Dashboard_Compensaciones_[TuNombre]_[Fecha].xlsx
4. Conserva los archivos originales del instructor en su ubicación 
   original en SharePoint (NO los muevas ni elimines)
```

### 9.2 Cierre de Archivos Temporales

1. Cierra todos los archivos de Excel abiertos durante la práctica.
2. Elimina cualquier archivo temporal descargado localmente que ya esté respaldado en OneDrive.
3. Cierra el panel de Copilot.

### 9.3 Verificación de Datos Ficticios

> ⚠️ **Recordatorio de cumplimiento LFPDPPP:** Confirma que ninguno de los archivos que trabajaste durante esta práctica contiene datos reales de empleados. Todos los registros deben ser ficticios. Si por error utilizaste o guardaste datos reales, notifica inmediatamente al instructor y al responsable de privacidad de tu organización.

### 9.4 Compartir el Dashboard con el Instructor

```
1. Abre el archivo Dashboard_Compensaciones_[TuNombre]_[Fecha].xlsx en OneDrive
2. Haz clic en "Compartir" (ícono de persona con +)
3. Ingresa el correo del instructor: [correo proporcionado por el instructor]
4. Selecciona permiso: "Puede ver"
5. Agrega el mensaje: "Lab06 completado - [Tu nombre] - [Fecha]"
6. Haz clic en "Enviar"
```

---

## 10. Resumen y Recursos Adicionales

### Resumen del Laboratorio

En esta práctica de 90 minutos completaste un ciclo completo de gestión de datos de compensaciones con apoyo de Microsoft Copilot en Excel, abarcando los dos ejes del Capítulo 6:

**Bloque A — Estructuración de Big Data (Lección 6.2):**
- Ejecutaste un **diagnóstico automatizado** de calidad de datos usando prompts de Copilot, identificando duplicados, nulos, inconsistencias de formato y errores tipográficos en un dataset de 300–500 registros.
- Aplicaste **correcciones sistemáticas**: eliminación de duplicados, relleno de nulos con valores provisionales, estandarización de fechas, montos y nombres usando fórmulas generadas por Copilot.
- Normalizaste los catálogos de **puestos y departamentos** contra fuentes oficiales, usando la capacidad de Copilot para identificar correspondencias entre variantes tipográficas y nombres estándar.

**Bloque B — Modelos Analíticos Masivos (Lección 6.3):**
- Realizaste un **análisis de equidad salarial por género** que identificó brechas específicas por nivel y departamento, con visualizaciones comparativas.
- Implementaste un **análisis de dispersión de bandas salariales** que clasificó a cada empleado en su estatus de banda y calculó el costo de nivelación.
- Modelaste **tres escenarios de incremento salarial** (inflación, meritocracia y combinado) con análisis de impacto presupuestal comparativo.
- Consolidaste todos los hallazgos en un **dashboard ejecutivo** con cuatro paneles visuales y un párrafo de conclusiones generado por Copilot.

### Conceptos Clave Aplicados

| Concepto | Aplicación en el Lab |
|---|---|
| **Diagnóstico de calidad de datos** | Prompt estructurado a Copilot para análisis automático del dataset |
| **Normalización de catálogos** | Correspondencia entre variantes tipográficas y nombres oficiales |
| **Análisis de equidad salarial** | Comparación de promedios por género dentro del mismo nivel y área |
| **Bandas salariales** | Clasificación BAJO/EN/SOBRE banda con BUSCARV y fórmulas SI |
| **Modelado de escenarios** | Tres hipótesis de incremento con cálculo de impacto presupuestal |
| **Dashboard ejecutivo** | Consolidación visual de múltiples análisis para toma de decisiones |

### Conexión con el Siguiente Módulo

Los datos limpios y el dashboard generados en esta práctica servirán como insumo directo para las Prácticas 7 y 8 del curso, donde construirás un agente de IA en Copilot Studio capaz de responder consultas sobre compensaciones en tiempo real, utilizando precisamente la estructura de datos que preparaste hoy.

### Recursos Adicionales

| Recurso | Descripción | URL |
|---|---|---|
| Documentación oficial de Copilot en Excel | Guía completa de funcionalidades y prompts | [learn.microsoft.com/es-es/copilot/microsoft-365/excel](https://learn.microsoft.com/es-es/copilot/microsoft-365/excel) |
| Power Query — Documentación oficial | Referencia de transformaciones y conectores | [learn.microsoft.com/es-es/power-query](https://learn.microsoft.com/es-es/power-query/) |
| Análisis de equidad salarial — IMSS | Marco normativo mexicano para brechas salariales | [imss.gob.mx](https://www.imss.gob.mx) |
| Guía de Big Data en RH — Microsoft Learn | Arquitectura de datos para analítica de personas | [learn.microsoft.com/es-es/azure/architecture/data-guide/big-data](https://learn.microsoft.com/es-es/azure/architecture/data-guide/big-data/) |
| Tendencias en People Analytics — SHRM | Mejores prácticas en análisis de datos de RH | [shrm.org/topics-tools/topics/technology/people-analytics](https://www.shrm.org/topics-tools/topics/technology/people-analytics) |
| Ley Federal del Trabajo — DOF | Texto vigente de la LFT para contexto normativo | [dof.gob.mx](https://www.dof.gob.mx) |

---

> **Nota del instructor:** Este laboratorio requiere el dataset ficticio `Lab06_Dataset_Compensaciones_Sucio.xlsx` con errores intencionales distribuidos en al menos 8 columnas distintas. Se recomienda incluir: 15–25 registros duplicados, 30–50 valores nulos en columnas críticas, 40–60 inconsistencias de formato de fecha, 20–30 variantes tipográficas de nombres de puestos y 10–15 valores de salario en formato texto. El nivel de "suciedad" debe ser suficiente para que los análisis de Copilot sean ilustrativos, pero no tan extremo que impida completar el laboratorio en 90 minutos.

---
LAB_END---
