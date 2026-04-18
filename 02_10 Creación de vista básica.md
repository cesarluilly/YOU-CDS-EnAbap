2/10 CDS en ABAP - Creación de vista básica - April 09

[**VIEW RECORDING - 12 mins (No highlights)**](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf)

## Propósito de la reunión

[Demostrar la creación de una vista básica de Core Data Services (CDS) en ABAP.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=11.0 "PLAY @0:11")

## Puntos clave

* [**Creación de vistas CDS:** Las vistas CDS se crean en SAP HANA Studio/Eclipse ADT, no en el Workbench de SAP GUI, utilizando la plantilla `Define View`.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=36.0 "PLAY @0:36")
* [**Generación dual de objetos:** Al activar una vista CDS se crean dos objetos: la Definición de Datos CDS (`.ddls`) y una vista SQL correspondiente en el Diccionario ABAP (`SE11`).](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=506.0 "PLAY @8:26")
* [**Vista previa de datos:** La herramienta `Data Preview` (F8) es un potente entorno de pruebas integrado para validar los datos de la vista, aplicar filtros e inspeccionar el SQL generado.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=540.0 "PLAY @9:00")
* [**Objetos de BD impulsados desde ABAP:** CDS permite a los desarrolladores ABAP crear objetos nativos de HANA sin necesitar credenciales separadas de usuario de base de datos, simplificando el desarrollo.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=600.0 "PLAY @10:00")

## Temas

### Creación y activación de una vista CDS

* [**Herramientas:** Requiere SAP HANA Studio o Eclipse con ADT, ya que el Workbench de SAP GUI no puede crear vistas CDS.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=36.0 "PLAY @0:36")
* [**Proceso (usando la tabla `SPFLI`):**](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=326.0 "PLAY @5:26")
  1. [**Nuevo objeto:** Clic derecho en el paquete → `New` → `Other ABAP Repository Object` → `Core Data Services` → `Data Definition`.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=59.0 "PLAY @0:59")
  2. [**Nombrado:** `ZVCDS01` (Nombre), `Basic View` (Descripción).](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=87.0 "PLAY @1:27")
  3. [**Transporte:** Asignar a una orden de transporte existente.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=120.0 "PLAY @2:00")
  4. [**Plantilla:** Seleccionar `Define View` para una vista simple con una sola fuente de datos.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=142.0 "PLAY @2:22")
  5. **Código:**
     * [**Nombre de la vista SQL:** La anotación `@ABAPCatalog.sqlViewName` define el nombre de la vista del diccionario creada en `SE11`. Este nombre debe seguir las reglas de nomenclatura de `SE11` (p. ej., longitud máxima).](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=239.0 "PLAY @3:59")
     * [**Fuente de datos:** Sustituir el marcador de posición por la tabla fuente, `SPFLI`.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=326.0 "PLAY @5:26")
     * [**Proyección:** Enumerar los campos a incluir, separados por comas.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=372.0 "PLAY @6:12")
       * [`CarID`, `ConID`, `CountryFrom`, `CityFrom`, `CountryTo`, `CityTo`](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=372.0 "PLAY @6:12")
       * [La vista `Outline` se actualiza en tiempo real, mostrando los elementos proyectados.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=372.0 "PLAY @6:12")
  6. [**Activar:** `Ctrl+F3`. Esto genera tanto la definición CDS como la vista del diccionario.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=506.0 "PLAY @8:26")

### Vista previa de datos y pruebas

* [**Acceso:** Clic derecho en la vista CDS → `Open With` → `Data Preview`, o presionar `F8` desde el editor.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=540.0 "PLAY @9:00")
* [**Funcionalidad:**](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=540.0 "PLAY @9:00")
  * [**Consola SQL:** Muestra la sentencia `SELECT` generada que se ejecuta contra la base de datos.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=615.0 "PLAY @10:15")
  * [**Filtrado:** Aplicar filtros a columnas específicas (p. ej., `CarID = 'LH'`).](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=646.0 "PLAY @10:46")
  * [**Selección de columnas:** Elegir qué columnas mostrar.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=624.0 "PLAY @10:24")
  * [**Exportar:** Guardar datos en varios formatos de archivo.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=646.0 "PLAY @10:46")

## Próximos pasos

* [**Cesar Luilly Garcia Aguazul:** Continuar la serie de tutoriales de CDS, cubriendo anotaciones más avanzadas y tipos de vistas.](https://fathom.video/share/z_NZf56pH-QHCDshPsadAPoxw7wQvCrf?tab=summary&timestamp=672.0 "PLAY @11:12")

---

---

---



## Propósito

Introducción a la creación de vistas CDS (Core Data Services) en ABAP, cubriendo desde la configuración inicial hasta la ejecución y prueba de datos.

## Glosario

* **CDS (Core Data Services)** : Vistas generadas en la base de datos HANA desde perspectiva ABAP
* **Data Definition** : Objeto del repositorio ABAP para definir un CDS
* **ADT (ABAP Development Tools)** : Herramienta necesaria para crear CDS (en Eclipse)
* **Annotations** : Conjunto de elementos que generan funcionalidades sin crear objetos relacionados
* **ABAP Catalog SQL View Name** : Anotación obligatoria que define el nombre de la vista en el diccionario de datos
* **Outline** : Panel que muestra fuentes de datos y elementos proyectados
* **Data Preview** : Herramienta para visualizar datos devueltos por la vista

## Atajos de Teclado

* **Ctrl + Espacio** : Autocompletado y sugerencias de elementos
* **Ctrl + C** : Copiar
* **Shift + F1** : Formatear código
* **Ctrl + F3** : Activar/compilar objeto
* **F8** : Abrir Data Preview desde el editor

## Buenas Prácticas y Recomendaciones

* Usar **SAP HANA Studio o Eclipse con ADT** (no Workbench ni SAP Logon)
* Separar elementos con **comas** en la proyección
* Nombrar vistas SQL con prefijo **ZV** (ej: ZVCDS01) respetando límite de caracteres
* Usar **Outline** para navegar en objetos con muchas líneas de código
* Aplicar **filtros en Data Preview** para validar datos específicos
* Formatear código regularmente con **Shift + F1** para legibilidad


# Ejemplo Base de Creación de CDS

## Estructura del Código

```abap
@AbapCatalog.sqlViewName: 'ZVCDS01'
define view ZVCDS_01_BasicView as
  select from spfly
  {
    carrid,
    connid,
    countryfr,
    cityfrom,
    countryto,
    cityto
  };
```

## Desglose del Ejemplo

| Componente                      | Descripción                               | Valor en Ejemplo                                           |
| ------------------------------- | ------------------------------------------ | ---------------------------------------------------------- |
| **Anotación**            | Nombre de la vista en diccionario de datos | `@AbapCatalog.sqlViewName: 'ZVCDS01'`                    |
| **Nombre CDS**            | Identificador del objeto ABAP              | `ZVCDS_01_BasicView`                                     |
| **Fuente de Datos**       | Tabla o vista origen                       | `spfly` (tabla de vuelos)                                |
| **Elementos Proyectados** | Columnas seleccionadas                     | `carrid, connid, countryfr, cityfrom, countryto, cityto` |

## Pasos Clave Ejecutados

1. **Crear objeto** : New → Other ABAP Repository Object → Core Data Services → Data Definition
2. **Asignar transporte** : Seleccionar orden existente
3. **Usar plantilla** : "Define View" (vista simple con una fuente)
4. **Reemplazar fuente** : `spfly` en lugar del placeholder
5. **Proyectar elementos** : Listar columnas separadas por comas
6. **Formatear** : Shift + F1
7. **Activar** : Ctrl + F3
8. **Probar** : F8 para Data Preview

 **Resultado** : Se generan 2 objetos en el paquete ZABAP-CDS (Data Definition + Dictionary View)



# Investigación Detallada de Puntos Importantes

## 1. ANOTACIONES EN CDS

### @AbapCatalog.sqlViewName

```abap
@AbapCatalog.sqlViewName: 'ZVCDS01'
define view ZVCDS_01_BasicView as
  select from spfly { ... };
```

 **Propósito** : Define el nombre de la vista SQL en el diccionario de datos (transacción SE11)  **Restricción** : Máximo 16 caracteres (límite de vistas en diccionario)  **Convención** : Prefijo ZV + nombre descriptivo

### Otras Anotaciones Comunes

```abap
@AbapCatalog.sqlViewName: 'ZVCDS01'
@AbapCatalog.compiler.compareFilter: true
@AccessControl.authorizationCheck: #CHECK
@EndUserText.label: 'Vista de Vuelos'
define view ZVCDS_01_BasicView as
  select from spfly { ... };
```

---

## 2. FUENTES DE DATOS (SELECT FROM)

### Tabla Base de Datos

```abap
define view ZVCDS_01_BasicView as
  select from spfly {
    carrid,
    connid
  };
```

### Otro CDS como Fuente

```abap
define view ZVCDS_02_ExtendedView as
  select from ZVCDS_01_BasicView {
    carrid,
    connid,
    countryfr
  };
```

### Vista del Diccionario

```abap
define view ZVCDS_03_DictView as
  select from v_flights {
    carrid,
    connid
  };
```

### Múltiples Fuentes (JOIN)

```abap
define view ZVCDS_04_JoinView as
  select from spfly
  inner join scarr on spfly.carrid = scarr.carrid {
    spfly.carrid,
    spfly.connid,
    scarr.carrname
  };
```

---

## 3. PROYECCIÓN DE ELEMENTOS

### Selección Específica

```abap
define view ZVCDS_01_BasicView as
  select from spfly {
    carrid,           // Código aerolínea
    connid,           // Número conexión
    countryfr,        // País origen
    cityfrom,         // Ciudad origen
    countryto,        // País destino
    cityto            // Ciudad destino
  };
```

### Con Alias

```abap
define view ZVCDS_05_AliasView as
  select from spfly {
    carrid as airline_code,
    connid as flight_number,
    countryfr as origin_country,
    cityfrom as origin_city
  };
```

### Seleccionar Todo (*)

```abap
define view ZVCDS_06_AllFields as
  select from spfly {
    *
  };
```

### Con Expresiones

```abap
define view ZVCDS_07_ExprView as
  select from spfly {
    carrid,
    connid,
    concat(cityfrom, ' - ', cityto) as route,
    cast(connid as abap.int4) as flight_id
  };
```

---

## 4. FILTROS Y CONDICIONES

### WHERE Clause

```abap
define view ZVCDS_08_FilterView as
  select from spfly
  where carrid = 'LH' {
    carrid,
    connid,
    cityfrom,
    cityto
  };
```

### Múltiples Condiciones

```abap
define view ZVCDS_09_MultiFilter as
  select from spfly
  where carrid = 'LH'
    and countryfr = 'DE'
    and countryto = 'US' {
    carrid,
    connid,
    cityfrom,
    cityto
  };
```

---

## 5. JOINS (Combinaciones)

### INNER JOIN

```abap
define view ZVCDS_10_InnerJoin as
  select from spfly
  inner join scarr on spfly.carrid = scarr.carrid {
    spfly.carrid,
    spfly.connid,
    scarr.carrname as airline_name,
    spfly.cityfrom,
    spfly.cityto
  };
```

### LEFT OUTER JOIN

```abap
define view ZVCDS_11_LeftJoin as
  select from spfly
  left outer join scarr on spfly.carrid = scarr.carrid {
    spfly.carrid,
    spfly.connid,
    scarr.carrname,
    spfly.cityfrom
  };
```

### Múltiples JOINs

```abap
define view ZVCDS_12_MultiJoin as
  select from spfly
  inner join scarr on spfly.carrid = scarr.carrid
  inner join sairport as origin on spfly.countryfr = origin.country
                                and spfly.cityfrom = origin.city {
    spfly.carrid,
    scarr.carrname,
    origin.airport as origin_airport,
    spfly.cityto
  };
```

---

## 6. AGRUPACIÓN Y AGREGACIÓN

### GROUP BY

```abap
define view ZVCDS_13_GroupView as
  select from spfly {
    carrid,
    countryfr,
    count(*) as flight_count,
    count(distinct connid) as unique_connections
  }
  group by carrid, countryfr;
```

### Funciones de Agregación

```abap
define view ZVCDS_14_AggregateView as
  select from spfly {
    carrid,
    count(*) as total_flights,
    max(connid) as max_connection,
    min(connid) as min_connection
  }
  group by carrid;
```

---

## 7. ORDENAMIENTO

### ORDER BY

```abap
define view ZVCDS_15_OrderView as
  select from spfly {
    carrid,
    connid,
    cityfrom,
    cityto
  }
  order by carrid asc, connid desc;
```

---

## 8. PARÁMETROS Y VARIABLES

### Con Parámetros

```abap
define view ZVCDS_16_ParamView
  (p_carrid : abap.char(3))
as
  select from spfly
  where carrid = $parameters.p_carrid {
    carrid,
    connid,
    cityfrom,
    cityto
  };
```

---

## 9. ASOCIACIONES (Relationships)

### Definir Asociación

```abap
define view ZVCDS_17_AssocView as
  select from spfly {
    carrid,
    connid,
    cityfrom,
    cityto,
    association [0..1] to scarr as _airline
      on spfly.carrid = _airline.carrid
  };
```

### Usar Asociación

```abap
define view ZVCDS_18_UseAssoc as
  select from ZVCDS_17_AssocView {
    carrid,
    connid,
    cityfrom,
    _airline.carrname as airline_name
  };
```

---

## 10. HERRAMIENTAS DE PRUEBA

### Data Preview (F8)

```markup
Resultado: 26 entradas
Columnas: carrid, connid, countryfr, cityfrom, countryto, cityto

Filtro aplicado: carrid = 'LH'
Resultado: Solo vuelos Lufthansa
```

### SQL Console

```sql
SELECT carrid, connid, countryfr, cityfrom, countryto, cityto
FROM ZVCDS01
WHERE carrid = 'LH'
```

---

## 11. BUENAS PRÁCTICAS APLICADAS

### Estructura Recomendada

```abap
@AbapCatalog.sqlViewName: 'ZVCDS01'
@AbapCatalog.compiler.compareFilter: true
@AccessControl.authorizationCheck: #CHECK
@EndUserText.label: 'Vista de Vuelos Básica'
@EndUserText.quickInfo: 'Información de vuelos por aerolínea'
define view ZVCDS_01_BasicView as
  select from spfly
  where carrid = 'LH' {
    carrid as airline_code,
    connid as flight_number,
    countryfr as origin_country,
    cityfrom as origin_city,
    countryto as destination_country,
    cityto as destination_city
  }
  order by carrid, connid;
```

### Convenciones de Nombres

* **CDS** : `ZVCDS_[##]_[Descripción]`
* **SQL View** : `ZV[Descripción]` (máx 16 caracteres)
* **Alias** : `snake_case` en inglés
* **Asociaciones** : Prefijo `_` (ej: `_airline`)


# Anotaciones Comunes en CDS - Guía Completa

## 1. @AbapCatalog.sqlViewName

### Definición

```abap
@AbapCatalog.sqlViewName: 'ZVCDS01'
```

### Propósito

Define el nombre técnico de la vista SQL que se genera en la base de datos HANA y se registra en el diccionario de datos (SE11).

### Características

* **Obligatoria** : Sí, siempre requerida
* **Longitud máxima** : 16 caracteres
* **Formato** : Mayúsculas, sin espacios
* **Convención** : Prefijo ZV + descripción

### Cuándo Usarlo

✅ **Siempre** - Es obligatoria en todo CDS

```abap
@AbapCatalog.sqlViewName: 'ZVCDS01'
define view ZVCDS_01_BasicView as
  select from spfly { carrid, connid };
```

### Ejemplo Incorrecto

```abap
@AbapCatalog.sqlViewName: 'ZVCDS_01_BasicViewWithLongName'  // ❌ Excede 16 caracteres
@AbapCatalog.sqlViewName: 'zvcds01'  // ❌ Debe ser mayúsculas
```

---

## 2. @AbapCatalog.compiler.compareFilter

### Definición

```abap
@AbapCatalog.compiler.compareFilter: true
```

### Propósito

Habilita la comparación de filtros en tiempo de compilación. Permite que el compilador valide y optimice las condiciones WHERE.

### Características

* **Valores** : `true` o `false`
* **Defecto** : `false`
* **Impacto** : Mejora rendimiento y validación

### Cuándo Usarlo

✅ Cuando tienes **filtros complejos** o **condiciones WHERE**

```abap
@AbapCatalog.sqlViewName: 'ZVCDS02'
@AbapCatalog.compiler.compareFilter: true
define view ZVCDS_02_FilteredView as
  select from spfly
  where carrid = 'LH'
    and countryfr = 'DE'
    and countryto = 'US' {
    carrid,
    connid,
    cityfrom,
    cityto
  };
```

❌ **No necesario** en vistas simples sin filtros

```abap
@AbapCatalog.sqlViewName: 'ZVCDS03'
define view ZVCDS_03_SimpleView as
  select from spfly {
    carrid,
    connid
  };
```

---

## 3. @AccessControl.authorizationCheck

### Definición

```abap
@AccessControl.authorizationCheck: #CHECK
```

### Propósito

Define si se deben aplicar controles de autorización (permisos) al acceder a los datos de la vista.

### Valores Posibles

| Valor             | Significado                 | Uso             |
| ----------------- | --------------------------- | --------------- |
| `#CHECK`        | Valida permisos del usuario | Datos sensibles |
| `#NOT_REQUIRED` | Sin validación de permisos | Datos públicos |
| `#NOT_ALLOWED`  | Rechaza acceso directo      | Vistas internas |

### Cuándo Usarlo

✅ **#CHECK** - Datos sensibles o confidenciales

```abap
@AbapCatalog.sqlViewName: 'ZVCDS04'
@AccessControl.authorizationCheck: #CHECK
define view ZVCDS_04_SensitiveData as
  select from spfly {
    carrid,
    connid,
    price  // Información sensible
  };
```

✅ **#NOT_REQUIRED** - Datos públicos o de referencia

```abap
@AbapCatalog.sqlViewName: 'ZVCDS05'
@AccessControl.authorizationCheck: #NOT_REQUIRED
define view ZVCDS_05_PublicData as
  select from scarr {
    carrid,
    carrname,
    currency
  };
```

✅ **#NOT_ALLOWED** - Vistas auxiliares internas

```abap
@AbapCatalog.sqlViewName: 'ZVCDS06'
@AccessControl.authorizationCheck: #NOT_ALLOWED
define view ZVCDS_06_InternalHelper as
  select from spfly {
    carrid,
    connid
  };
```

---

## 4. @EndUserText.label

### Definición

```abap
@EndUserText.label: 'Vista de Vuelos'
```

### Propósito

Define la descripción corta (etiqueta) visible para usuarios finales en herramientas UI y reportes.

### Características

* **Longitud máxima** : 60 caracteres
* **Idioma** : Soporta múltiples idiomas
* **Visibilidad** : Aparece en SAP Fiori, reportes, etc.

### Cuándo Usarlo

✅ **Siempre** - Mejora usabilidad y documentación

```abap
@AbapCatalog.sqlViewName: 'ZVCDS07'
@EndUserText.label: 'Información de Vuelos'
define view ZVCDS_07_FlightInfo as
  select from spfly {
    carrid,
    connid,
    cityfrom,
    cityto
  };
```

### Ejemplo Multiidioma

```abap
@AbapCatalog.sqlViewName: 'ZVCDS08'
@EndUserText.label: 'Flight Information'
@EndUserText.label#es: 'Información de Vuelos'
@EndUserText.label#de: 'Flugginformationen'
define view ZVCDS_08_MultiLang as
  select from spfly { carrid, connid };
```

---

## 5. @EndUserText.quickInfo

### Definición

```abap
@EndUserText.quickInfo: 'Detalles de vuelos por aerolínea'
```

### Propósito

Proporciona una descripción más detallada (tooltip) que aparece al pasar el cursor sobre el objeto.

### Características

* **Longitud máxima** : 255 caracteres
* **Uso** : Ayuda contextual en UI
* **Opcional** : Sí

### Cuándo Usarlo

✅ Cuando necesitas **explicación adicional**

```abap
@AbapCatalog.sqlViewName: 'ZVCDS09'
@EndUserText.label: 'Vuelos'
@EndUserText.quickInfo: 'Vista que contiene información detallada de vuelos incluyendo origen, destino y aerolínea'
define view ZVCDS_09_FlightDetails as
  select from spfly {
    carrid,
    connid,
    cityfrom,
    cityto
  };
```

---

## 6. @Metadata.ignoredElements

### Definición

```abap
@Metadata.ignoredElements: ['campo_interno']
```

### Propósito

Excluye campos específicos de la exposición en metadatos (OData, APIs, etc.).

### Características

* **Formato** : Array de nombres de campos
* **Uso** : Ocultar campos técnicos
* **Impacto** : No afecta la funcionalidad, solo la visibilidad

### Cuándo Usarlo

✅ Cuando tienes **campos técnicos internos**

```abap
@AbapCatalog.sqlViewName: 'ZVCDS10'
@Metadata.ignoredElements: ['created_by', 'created_date']
define view ZVCDS_10_PublicView as
  select from spfly {
    carrid,
    connid,
    cityfrom,
    created_by,      // Campo técnico
    created_date     // Campo técnico
  };
```

---

## 7. @ObjectModel.usageType

### Definición

```abap
@ObjectModel.usageType.dataClass: #TRANSACTIONAL
@ObjectModel.usageType.serviceType: #OData
```

### Propósito

Define el tipo de uso y clasificación del CDS para optimización y exposición de servicios.

### Valores Comunes

| Parámetro      | Valores                                    | Significado      |
| --------------- | ------------------------------------------ | ---------------- |
| `dataClass`   | `#TRANSACTIONAL`, `#MASTER`, `#FACT` | Tipo de datos    |
| `serviceType` | `#OData`, `#ANALYTICS`                 | Tipo de servicio |

### Cuándo Usarlo

✅ Para **servicios OData** o **análisis**

```abap
@AbapCatalog.sqlViewName: 'ZVCDS11'
@ObjectModel.usageType.dataClass: #TRANSACTIONAL
@ObjectModel.usageType.serviceType: #OData
define view ZVCDS_11_ODataView as
  select from spfly {
    carrid,
    connid,
    cityfrom,
    cityto
  };
```

---

## 8. @Analytics.query

### Definición

```abap
@Analytics.query: true
```

### Propósito

Marca el CDS como una vista analítica para consultas OLAP y reportes.

### Características

* **Valores** : `true` o `false`
* **Defecto** : `false`
* **Uso** : Optimización para análisis

### Cuándo Usarlo

✅ Para **vistas de análisis y reportes**

```abap
@AbapCatalog.sqlViewName: 'ZVCDS12'
@Analytics.query: true
define view ZVCDS_12_AnalyticsView as
  select from spfly {
    carrid,
    countryfr,
    count(*) as flight_count,
    count(distinct connid) as connections
  }
  group by carrid, countryfr;
```

❌ **No usar** en vistas transaccionales simples

---

## 9. @VDM.viewType

### Definición

```abap
@VDM.viewType: #BASIC
```

### Propósito

Define el tipo de vista en la arquitectura VDM (Virtual Data Model) de SAP.

### Valores

| Valor            | Significado               | Uso                |
| ---------------- | ------------------------- | ------------------ |
| `#BASIC`       | Vista básica sobre tabla | Datos crudos       |
| `#COMPOSITE`   | Combina múltiples vistas | Lógica de negocio |
| `#CONSUMPTION` | Para consumo final        | UI, reportes       |

### Cuándo Usarlo

✅ En **arquitecturas VDM estructuradas**

```abap
@AbapCatalog.sqlViewName: 'ZVCDS13'
@VDM.viewType: #BASIC
define view ZVCDS_13_BasicVDM as
  select from spfly {
    carrid,
    connid,
    cityfrom,
    cityto
  };
```

---

## 10. @Search.searchable

### Definición

```abap
@Search.searchable: true
```

### Propósito

Habilita búsqueda de texto completo en la vista.

### Características

* **Valores** : `true` o `false`
* **Impacto** : Rendimiento de búsqueda
* **Uso** : Interfaces de búsqueda

### Cuándo Usarlo

✅ Para **vistas con búsqueda de usuario**

```abap
@AbapCatalog.sqlViewName: 'ZVCDS14'
@Search.searchable: true
define view ZVCDS_14_SearchableView as
  select from scarr {
    carrid,
    carrname,
    currency
  };
```

---

## Resumen Comparativo

| Anotación                              | Obligatoria | Frecuencia    | Impacto |
| --------------------------------------- | ----------- | ------------- | ------- |
| `@AbapCatalog.sqlViewName`            | ✅ Sí      | Siempre       | Alto    |
| `@AccessControl.authorizationCheck`   | ❌ No       | Frecuente     | Alto    |
| `@EndUserText.label`                  | ❌ No       | Muy Frecuente | Medio   |
| `@EndUserText.quickInfo`              | ❌ No       | Frecuente     | Bajo    |
| `@AbapCatalog.compiler.compareFilter` | ❌ No       | Ocasional     | Medio   |
| `@Metadata.ignoredElements`           | ❌ No       | Ocasional     | Bajo    |
| `@ObjectModel.usageType`              | ❌ No       | Ocasional     | Medio   |
| `@Analytics.query`                    | ❌ No       | Ocasional     | Alto    |
| `@VDM.viewType`                       | ❌ No       | Ocasional     | Medio   |
| `@Search.searchable`                  | ❌ No       | Raro          | Bajo    |

---

## Ejemplo Completo Recomendado

```abap
@AbapCatalog.sqlViewName: 'ZVCDS15'
@AbapCatalog.compiler.compareFilter: true
@AccessControl.authorizationCheck: #CHECK
@EndUserText.label: 'Información de Vuelos'
@EndUserText.quickInfo: 'Vista con detalles de vuelos, origen y destino'
@ObjectModel.usageType.dataClass: #TRANSACTIONAL
@ObjectModel.usageType.serviceType: #OData
@Metadata.ignoredElements: ['created_by', 'created_date']
define view ZVCDS_15_CompleteExample as
  select from spfly
  where carrid = 'LH' {
    carrid as airline_code,
    connid as flight_number,
    countryfr as origin_country,
    cityfrom as origin_city,
    countryto as destination_country,
    cityto as destination_city,
    created_by,
    created_date
  }
  order by carrid, connid;
```
