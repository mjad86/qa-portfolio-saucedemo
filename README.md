# qa-portfolio-saucedemo
Testing case for QA portfolio


# Reportes de bugs: Sauce Demo (Shopify)

**Sitio probado:** https://sauce-demo.myshopify.com/
**Entorno:** Google Chrome 157.0.8103.40 (64 bits), Windows 10
**Convención de IDs:** `BUG-###` para reportes de bug, `TC-###` para casos de prueba.

---

## BUG-001: El campo "Nombre" acepta números en el registro

| Campo | Contenido |
|---|---|
| **Precondiciones** | Usuario en la página principal, sin sesión iniciada |
| **Pasos** | 1. Abrir https://sauce-demo.myshopify.com/ <br> 2. Ir a la opción de registro de usuario <br> 3. Escribir `121212` en el campo **Nombre** <br> 4. Completar los demás campos con datos válidos <br> 5. Hacer clic en el botón de crear cuenta |
| **Datos de prueba** | Nombre: `121212` |
| **Resultado esperado** | El sistema muestra un mensaje de validación y no permite crear la cuenta con un nombre numérico |
| **Resultado real** | La cuenta se crea con el nombre `121212` |
| **Severidad** | Media: se guardan datos de baja calidad, pero no se bloquea ninguna funcionalidad |
| **Reproducibilidad** 3 de 3 intentos
| **Evidencia** | `evidence/BUG-001.png` |

**Nota:** una validación correcta no debe ser "solo letras A-Z". Los nombres reales llevan acentos, ñ, apóstrofes y guiones (José, O'Connor, Ana-María). Ver casos de datos de prueba abajo.

---

## BUG-002: El campo "Apellido" acepta caracteres especiales en el registro

| Campo | Contenido |
|---|---|
| **Precondiciones** | Usuario en la página principal, sin sesión iniciada |
| **Pasos** | 1. Abrir https://sauce-demo.myshopify.com/ <br> 2. Ir a la opción de registro de usuario <br> 3. Escribir `@` en el campo **Apellido** <br> 4. Completar los demás campos con datos válidos <br> 5. Hacer clic en el botón de crear cuenta |
| **Datos de prueba** | Apellido: `@` |
| **Resultado esperado** | El sistema muestra un mensaje de validación y no permite crear la cuenta con un apellido de caracteres especiales |
| **Resultado real** | La cuenta se crea con el apellido `@` |
| **Severidad** | Media: se guardan datos de baja calidad, pero no se bloquea ninguna funcionalidad |
| **Reproducibilidad** ||
| **Evidencia** | `evidence/BUG-002.png` |

### Datos de prueba para validación de nombre y apellido

| Entrada | Tipo | Resultado esperado | Resultado real |
|---|---|---|---|
| `12345` | Inválida | Rechazada con mensaje ||
| `@#$%` | Inválida | Rechazada con mensaje ||
| `José` | Válida (acento) | Aceptada ||
| `O'Connor` | Válida (apóstrofe) | Aceptada ||
| `Ana-María` | Válida (guion) | Aceptada ||
| *(vacío)* | Inválida | Rechazada con mensaje ||
| 100+ caracteres | Límite | Rechazada o truncada con mensaje ||

---

## BUG-003: El carrito no se actualiza al volver con el botón de retroceso del navegador

| Campo | Contenido |
|---|---|
| **Precondiciones** | Usuario en la página de catálogo, carrito vacío |
| **Pasos** | 1. Abrir https://sauce-demo.myshopify.com/ <br> 2. Ir a la opción de catálogo <br> 3. Seleccionar un producto <br> 4. Agregarlo al carrito <br> 5. Hacer clic en la flecha de retroceso del navegador |
| **Datos de prueba** | N/A |
| **Resultado esperado** | El carrito muestra el producto agregado |
| **Resultado real** | El carrito se muestra desactualizado (sin el producto). Al navegar a Home, el carrito sí se actualiza con los datos correctos |
| **Severidad** | Media: el dato está bien guardado, pero la vista desactualizada puede confundir al usuario |
| **Reproducibilidad** ||
| **Evidencia** | `evidence/BUG-003.png` |

---

## BUG-004: El botón "Search" no devuelve resultados (Enter sí funciona)

| Campo | Contenido |
|---|---|
| **Precondiciones** | Usuario en la página principal, sin sesión iniciada |
| **Pasos** | 1. Abrir https://sauce-demo.myshopify.com/ <br> 2. Escribir "Jacket" en la barra de búsqueda <br> 3. Hacer clic en el botón "Search" del encabezado |
| **Datos de prueba** | Término: `Jacket` |
| **Resultado esperado** | Se muestra la lista de productos relacionados con "Jacket", igual que al presionar Enter |
| **Resultado real** | Se muestra el mensaje "No search results" (con cualquier término) |
| **Severidad** | Media: es un camino principal de búsqueda, aunque existe la alternativa de Enter |
| **Reproducibilidad** ||
| **Evidencia** | `evidence/BUG-004.png` |

---

## BUG-005: El botón "Refer a Friend" no responde

| Campo | Contenido |
|---|---|
| **Precondiciones** | Usuario en la página principal, sin sesión iniciada |
| **Pasos** | 1. Abrir https://sauce-demo.myshopify.com/ <br> 2. Hacer clic en "Refer a Friend" del menú principal (izquierda) |
| **Datos de prueba** | N/A |
| **Resultado esperado** | Navegación a otra página o apertura de un modal |
| **Resultado real** | No hay navegación, modal ni mensaje |
| **Verificaciones pendientes** | **[COMPLETAR]** ¿Aparece un error en la consola (F12 > Console) al hacer clic? <br> **[COMPLETAR]** ¿Funciona con la sesión iniciada? Si requiere login y no avisa, el reporte cambia a "no informa que se necesita iniciar sesión" |
| **Severidad** | Media: los referidos suelen traer clientes potenciales |
| **Reproducibilidad** ||
| **Evidencia** | `evidence/BUG-005.png` |

---

## BUG-006: Al navegar durante el proceso de "agregar al carrito", el producto no se agrega

| Campo | Contenido |
|---|---|
| **Precondiciones** | Usuario en la página de catálogo, carrito vacío |
| **Pasos** | 1. Abrir https://sauce-demo.myshopify.com/ <br> 2. Abrir las herramientas de desarrollo (F12) > pestaña **Network** y activar throttling **Slow 3G** (hace la petición lo bastante lenta para reproducirlo siempre) <br> 3. Agregar un producto al carrito <br> 4. Antes de que termine la animación, navegar a otra sección del sitio <br> 5. Revisar el carrito |
| **Datos de prueba** | N/A |
| **Resultado esperado** | El producto aparece en el carrito |
| **Resultado real** | El producto no se agrega al carrito |
| **Severidad** | Media-Baja: riesgo de pérdida involuntaria de una compra, pero requiere una acción rápida del usuario y el navegador suele cancelar peticiones al navegar |
| **Reproducibilidad** 4 de 5 intentos, con y sin throttling |
| **Evidencia** | `evidence/BUG-006.png` |
