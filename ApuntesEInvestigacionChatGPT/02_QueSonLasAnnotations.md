## 📌 ¿Qué son las anotaciones en CDS?

Las **anotaciones en CDS (Core Data Services)** son **metadatos** que agregan comportamiento especial a una vista CDS.

No modifican el `SELECT` como tal, sino que:

> 🔹 Le dicen al sistema cómo debe comportarse esa vista
>
> 🔹 Agregan información semántica
>
> 🔹 Permiten integración con OData, Fiori, seguridad, rendimiento, etc.

Son clave cuando trabajas en **SAP S/4HANA** o desarrollos modernos en  **SAP** .

---

# 🧠 Concepto sencillo

Sin anotaciones → solo datos.

Con anotaciones → datos + significado + comportamiento.

---

# 🏗 Sintaxis

Las anotaciones siempre empiezan con `@`.

Ejemplo:

<pre class="overflow-visible! px-0!" data-start="682" data-end="847"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@AbapCatalog.sqlViewName: 'ZV_CLIENTE'</span><br/><span>@EndUserText.label: 'Vista de Clientes'</span><br/><span>define view Z_CDS_Cliente</span><br/><span>as select from kna1</span><br/><span>{</span><br/><span>    key kunnr,</span><br/><span>    name1</span><br/><span>}</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

# 🎯 ¿Para qué sirven?

Las anotaciones pueden:

* ✅ Generar automáticamente un servicio OData
* ✅ Definir etiquetas visibles en Fiori
* ✅ Controlar seguridad
* ✅ Definir comportamiento de UI
* ✅ Optimizar rendimiento
* ✅ Marcar campos obligatorios
* ✅ Definir campos calculados

---

# 🔥 Tipos principales de anotaciones

## 1️⃣ Anotaciones Técnicas (ABAP Catalog)

Controlan cómo se crea la vista en la base de datos.

Ejemplo:

<pre class="overflow-visible! px-0!" data-start="1300" data-end="1348"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@AbapCatalog.sqlViewName: 'ZV_SALES'</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Le da nombre técnico en la base.

---

## 2️⃣ Anotaciones de Texto

<pre class="overflow-visible! px-0!" data-start="1418" data-end="1468"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@EndUserText.label: 'Pedidos de Venta'</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Define descripción visible para usuarios.

---

## 3️⃣ Anotaciones OData

<pre class="overflow-visible! px-0!" data-start="1544" data-end="1576"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@OData.publish: true</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

👉 Genera automáticamente un servicio OData.

Muy usada en Fiori.

---

## 4️⃣ Anotaciones de Seguridad

<pre class="overflow-visible! px-0!" data-start="1683" data-end="1736"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@AccessControl.authorizationCheck: #CHECK</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Indica que la vista debe validar roles (DCL).

---

## 5️⃣ Anotaciones de UI

Estas hacen magia en Fiori 👇

<pre class="overflow-visible! px-0!" data-start="1847" data-end="1930"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@UI.lineItem: [{ position: 10 }]</span><br/><span>@UI.selectionField: [{ position: 20 }]</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Controlan:

* Qué campos aparecen en lista
* Qué campos son filtros
* Orden de columnas
* Campos obligatorios

---

## 6️⃣ Anotaciones de Analítica

<pre class="overflow-visible! px-0!" data-start="2081" data-end="2123"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@Analytics.dataCategory: #CUBE</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Usadas en modelos analíticos.

---

# 🧩 Ejemplo completo real

<pre class="overflow-visible! px-0!" data-start="2189" data-end="2546"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@AbapCatalog.sqlViewName: 'ZV_ORDERS'</span><br/><span>@EndUserText.label: 'Órdenes de Compra'</span><br/><span>@OData.publish: true</span><br/><span>@AccessControl.authorizationCheck: #CHECK</span><br/><br/><span>define view Z_CDS_Orders</span><br/><span>as select from ekko</span><br/><span>{</span><br/><span>    @UI.lineItem: [{ position: 10 }]</span><br/><span>    key ebeln,</span><br/><br/><span>    @UI.lineItem: [{ position: 20 }]</span><br/><span>    lifnr,</span><br/><br/><span>    @UI.selectionField: [{ position: 30 }]</span><br/><span>    bukrs</span><br/><span>}</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Esta vista:

* Tiene nombre técnico
* Tiene etiqueta
* Genera OData
* Valida autorizaciones
* Controla UI en Fiori

---

# 🧠 Diferencia importante

| Sin Anotaciones          | Con Anotaciones        |
| ------------------------ | ---------------------- |
| Solo datos               | Datos + comportamiento |
| No interactúa con Fiori | Se integra con Fiori   |
| No genera servicios      | Puede generar OData    |
| No aplica seguridad      | Puede validar roles    |

---

# 🎓 En resumen

Las anotaciones son:

> 🔹 Metadatos declarativos
>
> 🔹 El corazón de Fiori y RAP
>
> 🔹 La forma moderna de definir comportamiento en CDS
>
> 🔹 Lo que convierte una vista simple en una vista inteligente

---

Si quieres, te explico ahora:

* 🔎 Cómo funcionan las anotaciones DCL (seguridad real)
* 🚀 Qué hace exactamente `@OData.publish`
* 🧠 Todas las anotaciones más usadas que debes saber como ABAP Developer
* 📊 Diferencia entre anotaciones de UI y de Analytics
* 🔥 Cómo funcionan en RAP

Tú dime cuál quieres dominar ahora 😎
