Exactamente 👌

## ✅ Sí: todo lo que crees en **$TMP (Local Objects)** **nunca** te pedirá orden de transporte.

---

## 🧠 ¿Por qué?

El paquete **$TMP** significa:

> 🔹 Objeto local
>
> 🔹 No transportable
>
> 🔹 Solo existe en ese sistema (por ejemplo DEV)
>
> 🔹 No se puede mover a QA ni a PRD

Cuando creas un objeto y eliges  **$TMP** , SAP entiende:

> “Esto es solo para pruebas locales”

Por eso:

* ❌ No te pide orden de transporte
* ❌ No se mueve entre ambientes
* ❌ No forma parte del proyecto oficialmente

---

## 🏗 ¿Qué pasa si luego lo quiero mover a QA?

No se puede transportar directamente.

Tendrías que:

1. Crear un objeto nuevo en un paquete transportable (Z*)
2. Copiar el código manualmente
3. Eliminar el objeto en $TMP

---

## 🔥 En proyectos reales S/4

En proyectos serios en  **SAP S/4HANA** , normalmente:

* $TMP → solo para pruebas rápidas
* Paquetes Z* o Y* → desarrollo real
* Todo lo oficial → va en orden de transporte

---

## 📦 ¿Cuándo usar $TMP?

✔ Pruebas personales

✔ Debug temporal

✔ Experimentos

✔ Código que vas a borrar

---

## ⚠ Señal de alerta profesional

Si estás desarrollando algo que:

* Va a producción
* Es parte de un requerimiento
* Forma parte de una solución funcional

👉 NO debe estar en $TMP.

---

## 🧭 Tip de Senior

Si no sabes qué paquete usar:

1. Pregunta al líder técnico
2. Revisa convenciones del proyecto
3. Busca objetos similares y mira en qué paquete están

---

Si quieres, te explico ahora:

* 🧠 Cómo funcionan realmente las órdenes de transporte
* 🚚 Qué es una Workbench vs Customizing Request
* 🔥 Cómo se mueve un objeto DEV → QA → PRD en S/4
* 📦 Qué pasa si modificas un objeto estándar SAP

¿Cuál quieres entender a fondo?

me puedes recordar como usar el prefijo Z y Y

Perfecto 👌 esto es básico pero  **fundamental en ABAP profesional** .

En **SAP** los prefijos **Z** y **Y** están reservados para desarrollos del cliente.

---

# 🧠 ¿Por qué existen Z y Y?

SAP protege su estándar.

Todo lo que empieza con:

* `MARA`
* `VBAK`
* `CL_`
* `/SAP/`
* etc.

👉 Es estándar SAP.

Para evitar conflictos, SAP obliga que los desarrollos propios empiecen con:

> 🔹  **Z** *
>
> 🔹  **Y** *

---

# 📌 ¿Cuál usar? ¿Z o Y?

Técnicamente  **no hay diferencia funcional** .

Pero en proyectos se usan convenciones:

| Prefijo | Uso típico                                   |
| ------- | --------------------------------------------- |
| Z*      | Desarrollo oficial del proyecto               |
| Y*      | Pruebas, temporales o desarrollos secundarios |

⚠ Esto depende de la empresa.

Algunas solo usan Z.

Otras usan ambos para separar tipos de desarrollo.

---

# 🏗 Cómo usar correctamente el prefijo (Nivel Proyecto)

No es solo poner "Z" y ya.

Debe seguir una estructura clara.

---

## 📦 Clases

<pre class="overflow-visible! px-0!" data-start="967" data-end="1019"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>ZCL_MM_PURCHASE_ORDER</span><br/><span>ZCL_FI_INVOICE_SERVICE</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Formato recomendado:

<pre class="overflow-visible! px-0!" data-start="1042" data-end="1076"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>ZCL_<MODULO>_<DESCRIPCION></span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

## 📄 Programas

<pre class="overflow-visible! px-0!" data-start="1100" data-end="1124"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>ZMM_REPORT_STOCK</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

## 📊 CDS Views

<pre class="overflow-visible! px-0!" data-start="1148" data-end="1175"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>ZCDS_SALES_ANALYSIS</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

## 🗃 Tablas

<pre class="overflow-visible! px-0!" data-start="1196" data-end="1220"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>ZMM_ORDER_HEADER</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

## 🧱 Estructuras

<pre class="overflow-visible! px-0!" data-start="1246" data-end="1266"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>ZSTR_MM_DATA</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

## 🔌 Function Modules

<pre class="overflow-visible! px-0!" data-start="1297" data-end="1319"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>ZFM_SEND_EMAIL</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

# 🚨 Regla profesional importante

Nunca crees:

<pre class="overflow-visible! px-0!" data-start="1375" data-end="1396"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>Z_MARA</span><br/><span>Z_VBAK</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Eso es mala práctica.

Debe tener sentido funcional y pertenecer a un paquete correcto.

---

# 📦 Prefijo + Paquete

No basta con el nombre.

Debe estar en un paquete transportable, ejemplo:

<pre class="overflow-visible! px-0!" data-start="1591" data-end="1631"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>ZMM_CORE</span><br/><span>ZFI_INTERFACE</span><br/><span>ZDEV_TEST</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

No en `$TMP`.

---

# 🔥 Nivel Senior — Namespaces

En empresas grandes verás:

<pre class="overflow-visible! px-0!" data-start="1713" data-end="1758"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>/CU/CL_SALES_SERVICE</span><br/><span>/ABC/CDS_FINANCE</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Eso es un  **namespace registrado** .

Es más profesional que usar solo Z.

---

# 🎯 Resumen claro

✔ Todo desarrollo propio → empieza con Z o Y

✔ No modificar estándar SAP

✔ Seguir convención del proyecto

✔ Usar paquetes transportables

✔ Nombre debe indicar módulo y función

---

Si quieres, te explico ahora:

* 🚚 Qué pasa si modificas estándar SAP directamente
* 🧱 Diferencia entre Enhancement vs Modificación
* 📦 Cómo organizar naming convention por módulo (MM, SD, FI)
* 🔥 Cómo definir un estándar de nombres profesional para tu equipo
