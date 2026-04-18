# 🧠 1️⃣ Anotaciones Técnicas (Base obligatoria)

## 🔹 `@AbapCatalog.sqlViewName`

Define el nombre técnico en la base de datos.

<pre class="overflow-visible! px-0!" data-start="372" data-end="420"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@AbapCatalog.sqlViewName: 'ZV_SALES'</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

👉 Obligatoria en CDS clásicas (no en View Entity modernas).

---

## 🔹 `@AbapCatalog.compiler.compareFilter: true`

Optimiza filtros en joins complejos.

---

## 🔹 `@AbapCatalog.preserveKey: true`

Mantiene claves originales.

---

# 🔐 2️⃣ Seguridad (CRÍTICO en proyectos reales)

## 🔹 `@AccessControl.authorizationCheck`

Controla si aplica reglas DCL.

<pre class="overflow-visible! px-0!" data-start="782" data-end="835"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@AccessControl.authorizationCheck: #CHECK</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Valores:

* `#CHECK` → Valida roles (lo normal)
* `#NOT_REQUIRED` → No valida
* `#NOT_ALLOWED` → Prohíbe acceso

👉 En productivo siempre se usa `#CHECK`.

---

# 🌍 3️⃣ OData (Para Fiori)

## 🔹 `@OData.publish: true`

Genera automáticamente servicio OData.

<pre class="overflow-visible! px-0!" data-start="1096" data-end="1128"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@OData.publish: true</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Después debes activarlo en `/IWFND/MAINT_SERVICE`.

---

# 🎨 4️⃣ UI (Muy usadas en Fiori)

Estas controlan cómo se ve la app sin tocar UI5.

---

## 🔹 `@UI.lineItem`

Define columnas en lista.

<pre class="overflow-visible! px-0!" data-start="1326" data-end="1370"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@UI.lineItem: [{ position: 10 }]</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

## 🔹 `@UI.selectionField`

Campo aparece como filtro.

<pre class="overflow-visible! px-0!" data-start="1433" data-end="1483"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@UI.selectionField: [{ position: 20 }]</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

## 🔹 `@UI.identification`

Campo visible en detalle.

---

## 🔹 `@UI.headerInfo`

Define título principal de la app.

<pre class="overflow-visible! px-0!" data-start="1610" data-end="1693"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@UI.headerInfo: {</span><br/><span>   typeName: 'Pedido',</span><br/><span>   typeNamePlural: 'Pedidos'</span><br/><span>}</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

# 📊 5️⃣ Analítica (Muy importante en S/4)

---

## 🔹 `@Analytics.dataCategory`

Define tipo de modelo analítico.

<pre class="overflow-visible! px-0!" data-start="1816" data-end="1858"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@Analytics.dataCategory: #CUBE</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Valores comunes:

* `#CUBE`
* `#DIMENSION`
* `#FACT`

---

## 🔹 `@Analytics.query: true`

Convierte CDS en consulta analítica.

---

# 🏷 6️⃣ Etiquetas y Textos

---

## 🔹 `@EndUserText.label`

Etiqueta descriptiva.

<pre class="overflow-visible! px-0!" data-start="2078" data-end="2129"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@EndUserText.label: 'Pedidos de Compra'</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

## 🔹 `@ObjectModel.text.association`

Asocia campo a su texto.

<pre class="overflow-visible! px-0!" data-start="2201" data-end="2251"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@ObjectModel.text.association: '_Text'</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

# 🔄 7️⃣ Asociaciones

---

## 🔹 `@ObjectModel.association.type`

Define tipo de asociación.

Muy usada en RAP.

---

# 📦 8️⃣ RAP (Modelo moderno)

Si trabajas con RAP necesitas:

---

## 🔹 `@ObjectModel.transactionalProcessingEnabled: true`

Permite manejo transaccional.

---

## 🔹 `@ObjectModel.compositionRoot: true`

Define raíz de composición.

---

# ⚡ 9️⃣ Rendimiento

---

## 🔹 `@Consumption.filter`

Define comportamiento de filtros.

---

## 🔹 `@Semantics.amount.currencyCode`

Define relación moneda-importe.

<pre class="overflow-visible! px-0!" data-start="2786" data-end="2837"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@Semantics.amount.currencyCode: 'WAERS'</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Muy importante para cálculos correctos.

---

# 🧩 Ejemplo Profesional Completo

<pre class="overflow-visible! px-0!" data-start="2920" data-end="3364"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@EndUserText.label: 'Pedidos de Venta'</span><br/><span>@AccessControl.authorizationCheck: #CHECK</span><br/><span>@OData.publish: true</span><br/><span>@Analytics.dataCategory: #CUBE</span><br/><br/><span>define view entity Z_CDS_Sales</span><br/><span>as select from vbak</span><br/><span>association [0..1] to kna1 as _Customer</span><br/><span>    on _Customer.kunnr = vbak.kunnr</span><br/><span>{</span><br/><span>    @UI.lineItem: [{ position: 10 }]</span><br/><span>    key vbeln,</span><br/><br/><span>    @UI.lineItem: [{ position: 20 }]</span><br/><span>    kunnr,</span><br/><br/><span>    @Semantics.amount.currencyCode: 'waerk'</span><br/><span>    netwr,</span><br/><br/><span>    waerk</span><br/><span>}</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Esta vista:

* Tiene seguridad
* Genera OData
* Es analítica
* Tiene UI lista
* Maneja moneda correctamente

---

# 🎓 Lo que debes dominar como ABAP Developer moderno

Si quieres subir a nivel senior en CDS debes saber:

✔ Seguridad (DCL + authorizationCheck)

✔ UI annotations

✔ Analítica

✔ Semantics (currency, quantity)

✔ Asociaciones

✔ View Entity vs View clásica

✔ RAP annotations

---

Si quieres, te armo ahora:

* 🧠 Un mapa conceptual jerárquico de todas las anotaciones
* 📚 Un checklist para entrevistas SAP ABAP modernas
* 🔥 Las 15 anotaciones que siempre preguntan en proyectos S/4
* 🚀 Un mini proyecto práctico para que las uses todas

¿Cuál quieres?

Las 15 anotaciones que siempre preguntan en proyectos S/4

Perfecto 😎

Aquí tienes **las 15 anotaciones CDS que más preguntan en proyectos reales de S/4HANA** (entrevistas y proyectos productivos).

Trabajando en **SAP S/4HANA** dentro del ecosistema de  **SAP** , estas son las que debes dominar sí o sí 👇

---

# 🏆 🔥 TOP 15 Anotaciones CDS en S/4

---

## 🥇 1️⃣ `@AccessControl.authorizationCheck`

👉 Controla si la CDS valida reglas DCL.

<pre class="overflow-visible! px-0!" data-start="422" data-end="475"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@AccessControl.authorizationCheck: #CHECK</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

🔹 Siempre preguntan esto

🔹 Es obligatorio en productivo

🔹 Sin esto no hay seguridad real

---

## 🥈 2️⃣ `@EndUserText.label`

Define descripción amigable.

<pre class="overflow-visible! px-0!" data-start="643" data-end="693"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@EndUserText.label: 'Pedidos de Venta'</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

## 🥉 3️⃣ `@OData.publish: true`

Genera servicio OData automático.

<pre class="overflow-visible! px-0!" data-start="769" data-end="801"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@OData.publish: true</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

⚠ Luego se activa en `/IWFND/MAINT_SERVICE`.

---

## 4️⃣ `@UI.lineItem`

Define columnas en lista Fiori.

<pre class="overflow-visible! px-0!" data-start="910" data-end="954"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@UI.lineItem: [{ position: 10 }]</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

## 5️⃣ `@UI.selectionField`

Define filtros visibles.

<pre class="overflow-visible! px-0!" data-start="1016" data-end="1066"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@UI.selectionField: [{ position: 20 }]</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

## 6️⃣ `@UI.identification`

Campos visibles en pantalla de detalle.

---

## 7️⃣ `@UI.headerInfo`

Define título principal en Fiori.

<pre class="overflow-visible! px-0!" data-start="1208" data-end="1291"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@UI.headerInfo: {</span><br/><span>   typeName: 'Pedido',</span><br/><span>   typeNamePlural: 'Pedidos'</span><br/><span>}</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

## 8️⃣ `@Semantics.amount.currencyCode`

Relaciona importe con moneda.

<pre class="overflow-visible! px-0!" data-start="1370" data-end="1421"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@Semantics.amount.currencyCode: 'WAERS'</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

💥 Muy preguntada en entrevistas.

---

## 9️⃣ `@Semantics.quantity.unitOfMeasure`

Relaciona cantidad con unidad.

<pre class="overflow-visible! px-0!" data-start="1539" data-end="1593"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@Semantics.quantity.unitOfMeasure: 'MEINS'</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

## 🔟 `@Analytics.dataCategory`

Define modelo analítico.

<pre class="overflow-visible! px-0!" data-start="1659" data-end="1701"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@Analytics.dataCategory: #CUBE</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

Valores importantes:

* `#CUBE`
* `#DIMENSION`
* `#FACT`

---

## 1️⃣1️⃣ `@Analytics.query: true`

Convierte la CDS en query analítica.

---

## 1️⃣2️⃣ `@ObjectModel.text.association`

Asocia campo a su texto descriptivo.

<pre class="overflow-visible! px-0!" data-start="1925" data-end="1975"><div class="w-full my-4"><div class=""><div class="min-h-0 flex-1 relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border corner-superellipse/1.1 border-token-border-light bg-token-bg-elevated-secondary rounded-3xl"><div class="absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class="absolute inset-x-px top-0 bottom-96"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-bg-elevated-secondary"></div></div></div><div class="corner-superellipse/1.1 rounded-3xl bg-token-bg-elevated-secondary"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼ5 ͼj"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>@ObjectModel.text.association: '_Text'</span></div></div></div></div></div></div></div></div><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"></div></div></div></div></div></pre>

---

## 1️⃣3️⃣ `@Consumption.filter`

Define comportamiento de filtros en Fiori.

---

## 1️⃣4️⃣ `@ObjectModel.compositionRoot: true`

Usada en RAP para definir raíz.

---

## 1️⃣5️⃣ `@ObjectModel.transactionalProcessingEnabled: true`

Permite manejo transaccional en RAP.

---

# 🧠 BONUS (las que demuestran nivel senior)

Si quieres destacar en entrevista:

* `@AbapCatalog.compiler.compareFilter`
* `@ObjectModel.foreignKey.association`
* `@Search.searchable`
* `@Search.defaultSearchElement`

---

# 🎯 Las 5 que SIEMPRE debes saber explicar sin titubear

1. `@AccessControl.authorizationCheck`
2. `@OData.publish`
3. `@UI.lineItem`
4. `@Semantics.amount.currencyCode`
5. `@Analytics.dataCategory`

Si sabes explicar estas con ejemplos reales → ya estás arriba del 80% de los ABAP developers tradicionales.

---

# 🚀 Nivel entrevista técnica

Si te preguntan:

> “¿Cómo aseguras una CDS?”
>
> → DCL + `authorizationCheck`

> “¿Cómo haces una Fiori sin tocar UI5?”
>
> → UI annotations + OData

> “¿Cómo manejas moneda correctamente?”
>
> → `@Semantics.amount.currencyCode`

> “¿Cómo modelas analítica en S/4?”
>
> → `@Analytics.dataCategory`

---

Si quieres, ahora puedo:

* 🧩 Armarte una CDS real que use las 15 juntas
* 📊 Hacer un mapa conceptual jerárquico (como te gusta estructurado)
* 🧠 Simularte una entrevista técnica con preguntas reales
* 🔥 Explicarte las diferencias entre proyecto ECC vs S/4

Tú dime cómo quieres subir de nivel 😎
