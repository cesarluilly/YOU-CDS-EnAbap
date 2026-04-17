# YOU-CDS-EnAbap

https://www.youtube.com/watch?v=hihQzSlE2ds&list=PLBBoc2l3GGf3fvyWsMzg_Aft-Rd2qOIVG&index=1

📌 ¿Qué son las CDS en SAP?

Las CDS (Core Data Services) son una tecnología de modelado de datos en SAP que permite definir vistas y modelos de datos directamente en la base de datos, pero con lógica semántica más avanzada que un simple SELECT.

En pocas palabras:

🔹 Son una forma moderna de crear vistas de base de datos con lógica, relaciones y anotaciones integradas.
🔹 Se usan mucho en SAP S/4HANA y en desarrollos ABAP modernos.

🧠 Concepto sencillo

Imagina que antes en ABAP hacías esto:

SELECT * FROM mara INTO TABLE lt_mara.

Eso solo trae datos.

Con CDS, tú defines una vista más inteligente que:

Une tablas

Define relaciones (asociaciones)

Agrega campos calculados

Aplica filtros

Añade anotaciones para UI, OData, seguridad, etc.

Y luego simplemente la consumes desde ABAP.

🏗 Estructura básica de una CDS View

Ejemplo simple:

@AbapCatalog.sqlViewName: 'ZV_MATERIAL'
@EndUserText.label: 'Vista de Materiales'
define view Z_CDS_Material
as select from mara
{
    key matnr,
    mtart,
    meins
}
🎯 ¿Para qué sirven?

Las CDS se usan para:

✅ Modelar datos de forma limpia

✅ Exponer servicios OData

✅ Crear aplicaciones Fiori

✅ Mejorar rendimiento (la lógica corre en HANA)

✅ Definir seguridad a nivel de datos

✅ Crear capas semánticas

🔥 Diferencia con una vista SQL tradicional
Vista SQL	CDS
Solo SELECT	SELECT + asociaciones
Sin anotaciones	Tiene anotaciones
Sin semántica	Modelo semántico
Lógica limitada	Lógica avanzada
No integrada a UI	Integrada con Fiori
🧩 Componentes importantes en CDS
1️⃣ Asociaciones

Permiten relacionar tablas sin hacer JOIN explícito.

association [0..1] to mara as _Material
    on _Material.matnr = vbap.matnr
2️⃣ Anotaciones

Son metadatos que agregan comportamiento.

Ejemplo:

@OData.publish: true

Esto genera automáticamente un servicio OData.

3️⃣ Tipos de CDS
🔹 CDS View (clásica)

Usada en sistemas tradicionales ABAP.

🔹 CDS View Entity

Versión moderna recomendada en SAP S/4HANA.

🔹 CDS con comportamiento (RAP)

Usadas en el modelo RAP (RESTful ABAP Programming Model).

🏎 ¿Por qué son importantes en S/4HANA?

Porque SAP HANA trabaja mejor cuando la lógica está en la base de datos.

Con CDS:

La agregación ocurre en HANA

El filtro ocurre en HANA

El join ocurre en HANA

👉 No cargas datos innecesarios a ABAP.

🧱 Arquitectura simplificada
Base de Datos (HANA)
       ↑
    CDS View
       ↑
  ABAP / OData
       ↑
   SAP Fiori
🎓 En resumen

Las CDS son:

🔹 El estándar moderno para modelar datos en SAP
🔹 La base de Fiori
🔹 Parte fundamental de S/4HANA
🔹 Clave para desarrolladores ABAP modernos





























