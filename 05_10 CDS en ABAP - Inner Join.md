## Propósito de la reunión

[Demostrar la creación de una vista CDS con un `INNER JOIN`.]()

## Puntos clave

* [Se creó `ZVCDS02_InnerJoin` uniendo una vista CDS existente (`ZVCDS01`) con la tabla `SCARR` para enriquecer los datos de vuelos con los nombres de las aerolíneas.]()
* [Se utilizó una plantilla para acelerar el desarrollo, que completa automáticamente la lista de orígenes y la condición de la unión.]()
* [La cláusula `ON` debe usar los alias proyectados del CDS del lado izquierdo, no sus campos fuente originales, porque la unión opera sobre la salida de la vista.]()
* [Se requirió una corrección rápida (cambiar `CARID` a `CARRNAME`) para proyectar el nombre correcto de la aerolínea, validando la recuperación de datos de la unión.]()

## Temas

### Creación de la vista CDS

* [Se creó `ZVCDS02_InnerJoin` desde el asistente &#34;New Data Definition&#34;.]()
* [Se seleccionó la plantilla para una vista CDS con una unión para armar el esqueleto del código.]()
* [Nota: Se comentaron temporalmente el parámetro y el filtro del CDS origen (`ZVCDS01`) para simplificar este ejemplo; se volverán a habilitar más adelante.]()

### Definición del `INNER JOIN`

* [Se reemplazó el `LEFT OUTER JOIN` de la plantilla por `INNER JOIN`.]()
* [Orígenes:]()
  * [`ZVCDS01` (con alias `Flights`)]()
  * [tabla `SCARR` (con alias `Airline`)]()
* [Condición de unión (`ON`):]()
  * [`Flights.AirLineCode = Airline.CARRID`]()
  * [Rationale: La cláusula `ON` debe hacer referencia a los alias proyectados de `ZVCDS01` (`AirLineCode`), no a su campo fuente original, porque la unión opera sobre la salida de la vista.]()

### Proyección de campos y validación

* [Se proyectaron todos los campos de `Flights` usando `insert all elements`.]()
* [Se añadió `CARRNAME` de `Airline` a la lista de proyección.]()
  * [Alias: `AS AirlineName`]()
* [Validación:]()
  * [La prueba inicial mostró solo el código de la aerolínea.]()
  * [Corrección: Se cambió el campo proyectado de `CARRID` a `CARRNAME` en la definición de la CDS.]()
  * [Resultado: Se actualizó la vista de prueba para confirmar que se mostraban los nombres correctos de las aerolíneas, validando la unión.]()

## Próximos pasos

* [Cesar: Volver a habilitar el parámetro y el filtro en `ZVCDS01` para una lección futura sobre pasar valores a modelos de datos de nivel superior.]()

---

---

---



# Resumen de la Reunión

## Propósito

Tutorial educativo sobre cómo crear un **CDS (Core Data Services) con InnerJoin** en SAP, combinando múltiples fuentes de datos (CDS y tablas de base de datos) para realizar intersecciones de datos.

---

## Glosario

* **CDS** : Core Data Services (Servicios de Datos Principales)
* **InnerJoin** : Intersección que retorna solo registros coincidentes entre dos fuentes
* **Left Outer Join** : Intersección que retorna todos los registros de la tabla izquierda
* **Alias** : Nombre alternativo asignado a elementos/columnas
* **ON** : Condición de intersección (equivalente a OpenSQL)
* **Data Definition** : Carpeta para crear nuevas definiciones CDS
* **SCARR/CARRID** : Tabla de compañías aéreas
* **Flights** : CDS de vuelos

---

## Atajos de Teclado

| Atajo                    | Función                      |
| ------------------------ | ----------------------------- |
| **Ctrl + V**       | Copiar/pegar fuentes de datos |
| **Ctrl + Espacio** | Autocompletado de columnas    |
| **Shift + F1**     | Formatear código             |
| **F8**             | Visualizar resultado/test     |

---

## Buenas Prácticas & Recomendaciones

✓ Ver videos previos antes de esta clase (requisitos previos)
✓ Mantener modelos CDS sencillos inicialmente (2 fuentes máximo)
✓ Usar nombres alias descriptivos para claridad
✓ Proyectar solo columnas necesarias (no todas)
✓ Activar y testear después de cambios
✓ Suscribirse al canal logallygroup.com para más cursos ABAP/HANA


Ejemplo Base del Tutorial

## Estructura del CDS con InnerJoin

```abap
DEFINE VIEW ZVCDS02_InnerJoin AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS airline
      ON f.airlinecode = airline.carrid
  {
    f.flightid,
    f.airlinecode,
    airline.carrid,
    airline.carrname AS airlinename
  }
```

---

## Componentes Clave

| Elemento                 | Descripción                     | Ejemplo                            |
| ------------------------ | -------------------------------- | ---------------------------------- |
| **Primera Fuente** | CDS o tabla principal            | `flights AS f`                   |
| **Segunda Fuente** | Tabla a intersectar              | `scarr AS airline`               |
| **Tipo de Join**   | Intersección (Inner/Left Outer) | `INNER JOIN`                     |
| **Condición ON**  | Campo de coincidencia            | `f.airlinecode = airline.carrid` |
| **Alias**          | Nombre corto para fuente         | `AS f`, `AS airline`           |
| **Proyección**    | Columnas a mostrar               | `carrname AS airlinename`        |

---

## Resultado

Una vista que combina datos de **vuelos** con  **nombres de compañías aéreas** , mostrando en cada fila el código de aerolínea y su nombre correspondiente obtenido de la segunda fuente.


# Investigación Detallada de Puntos Importantes

## 1. TIPOS DE JOIN EN CDS

### InnerJoin

```abap
DEFINE VIEW ZV_INNER_JOIN AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS airline
      ON f.airlinecode = airline.carrid
  {
    f.flightid,
    f.airlinecode,
    airline.carrname
  }
```

 **Resultado** : Solo vuelos con aerolínea válida (coincidencia obligatoria)

---

### Left Outer Join

```abap
DEFINE VIEW ZV_LEFT_OUTER_JOIN AS
  SELECT FROM flights AS f
    LEFT OUTER JOIN scarr AS airline
      ON f.airlinecode = airline.carrid
  {
    f.flightid,
    f.airlinecode,
    airline.carrname
  }
```

 **Resultado** : Todos los vuelos, aunque no tengan aerolínea (NULL si no coincide)

---

### Right Outer Join

```abap
DEFINE VIEW ZV_RIGHT_OUTER_JOIN AS
  SELECT FROM scarr AS airline
    RIGHT OUTER JOIN flights AS f
      ON airline.carrid = f.airlinecode
  {
    airline.carrid,
    airline.carrname,
    f.flightid
  }
```

 **Resultado** : Todas las aerolíneas, aunque no tengan vuelos

---

### Full Outer Join

```abap
DEFINE VIEW ZV_FULL_OUTER_JOIN AS
  SELECT FROM flights AS f
    FULL OUTER JOIN scarr AS airline
      ON f.airlinecode = airline.carrid
  {
    f.flightid,
    airline.carrid,
    airline.carrname
  }
```

 **Resultado** : Todos los registros de ambas tablas (con NULLs donde no coincida)

---

## 2. ALIAS - NOMBRES ALTERNATIVOS

### Alias para Tablas/CDS

```abap
DEFINE VIEW ZV_ALIAS_EXAMPLE AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  {
    f.flightid,
    f.airlinecode,
    s.carrname
  }
```

 **Ventaja** : Código más legible y evita conflictos de nombres

---

### Alias para Columnas

```abap
DEFINE VIEW ZV_COLUMN_ALIAS AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  {
    f.flightid AS flight_id,
    f.airlinecode AS airline_code,
    s.carrname AS airline_name,
    f.price AS flight_price
  }
```

 **Ventaja** : Nombres descriptivos en la salida

---

### Alias Anidados

```abap
DEFINE VIEW ZV_NESTED_ALIAS AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  {
    f.flightid,
    s.carrid AS code,
    s.carrname AS name,
    CAST(f.price AS DECIMAL(10,2)) AS final_price
  }
```

---

## 3. CONDICIÓN ON - INTERSECCIÓN

### ON Simple (1 Campo)

```abap
DEFINE VIEW ZV_ON_SIMPLE AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  {
    f.flightid,
    s.carrname
  }
```

---

### ON Múltiple (Varios Campos)

```abap
DEFINE VIEW ZV_ON_MULTIPLE AS
  SELECT FROM flights AS f
    INNER JOIN spfli AS route
      ON f.airlinecode = route.carrid
      AND f.flightid = route.flightid
  {
    f.flightid,
    route.cityfrom,
    route.cityto
  }
```

 **Uso** : Cuando se necesita más de una condición de coincidencia

---

### ON con Constantes

```abap
DEFINE VIEW ZV_ON_CONSTANT AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
      AND s.currcode = 'USD'
  {
    f.flightid,
    s.carrname
  }
```

 **Uso** : Filtrar por valores específicos en la segunda tabla

---

## 4. PROYECCIÓN DE COLUMNAS

### Proyectar Todas las Columnas

```abap
DEFINE VIEW ZV_PROJECT_ALL AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  {
    *
  }
```

 **Resultado** : Todas las columnas de ambas tablas

---

### Proyectar Columnas Específicas

```abap
DEFINE VIEW ZV_PROJECT_SPECIFIC AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  {
    f.flightid,
    f.airlinecode,
    s.carrname,
    f.price
  }
```

 **Ventaja** : Optimización de rendimiento (menos datos)

---

### Proyectar con Cálculos

```abap
DEFINE VIEW ZV_PROJECT_CALC AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  {
    f.flightid,
    s.carrname,
    f.price,
    f.price * 1.1 AS price_with_tax,
    CASE WHEN f.price > 1000 THEN 'Premium' ELSE 'Standard' END AS category
  }
```

---

### Proyectar con Funciones de Agregación

```abap
DEFINE VIEW ZV_PROJECT_AGGREGATE AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  {
    s.carrname,
    COUNT(*) AS total_flights,
    AVG(f.price) AS avg_price,
    MAX(f.price) AS max_price
  }
  GROUP BY s.carrname
```

---

## 5. MÚLTIPLES JOINS

### Dos InnerJoins

```abap
DEFINE VIEW ZV_DOUBLE_JOIN AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
    INNER JOIN spfli AS route
      ON f.airlinecode = route.carrid
      AND f.flightid = route.flightid
  {
    f.flightid,
    s.carrname,
    route.cityfrom,
    route.cityto
  }
```

---

### Combinación de Joins (Inner + Left Outer)

```abap
DEFINE VIEW ZV_MIXED_JOINS AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
    LEFT OUTER JOIN sbook AS booking
      ON f.flightid = booking.flightid
  {
    f.flightid,
    s.carrname,
    booking.bookid,
    booking.customid
  }
```

 **Uso** : Datos obligatorios de una tabla, opcionales de otra

---

### Tres o Más Joins

```abap
DEFINE VIEW ZV_TRIPLE_JOIN AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
    INNER JOIN spfli AS route
      ON f.airlinecode = route.carrid
      AND f.flightid = route.flightid
    LEFT OUTER JOIN sbook AS booking
      ON f.flightid = booking.flightid
  {
    f.flightid,
    s.carrname,
    route.cityfrom,
    route.cityto,
    booking.bookid
  }
```

---

## 6. PARÁMETROS EN CDS CON JOIN

### Parámetro Simple

```abap
DEFINE VIEW ZV_PARAM_JOIN AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  WHERE f.airlinecode = $P{airline_code}
  {
    f.flightid,
    s.carrname,
    f.price
  }
```

---

### Parámetro con Filtro

```abap
DEFINE VIEW ZV_PARAM_FILTER AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  WHERE f.airlinecode = $P{airline_code}
    AND f.price > $P{min_price}
  {
    f.flightid,
    s.carrname,
    f.price
  }
```

---

## 7. BUENAS PRÁCTICAS

### ✓ Estructura Limpia

```abap
DEFINE VIEW ZV_CLEAN_STRUCTURE AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  {
    f.flightid,
    f.airlinecode,
    s.carrname,
    f.price
  }
```

---

### ✓ Nombres Descriptivos

```abap
DEFINE VIEW ZV_DESCRIPTIVE_NAMES AS
  SELECT FROM flights AS flight
    INNER JOIN scarr AS airline
      ON flight.airlinecode = airline.carrid
  {
    flight.flightid AS flight_identifier,
    airline.carrname AS airline_name,
    flight.price AS flight_price
  }
```

---

### ✓ Evitar Proyectar Todo

```abap
-- ❌ MAL: Proyecta columnas innecesarias
DEFINE VIEW ZV_BAD_PRACTICE AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  { * }

-- ✓ BIEN: Solo columnas necesarias
DEFINE VIEW ZV_GOOD_PRACTICE AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  {
    f.flightid,
    s.carrname
  }
```

---

### ✓ Documentación

```abap
@EndUserText.label: 'Vuelos con Información de Aerolínea'
@ObjectModel.usageType.serviceType: #OData
@ObjectModel.usageType.dataClass: #TRANSACTIONAL
DEFINE VIEW ZV_DOCUMENTED_JOIN AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  {
    f.flightid,
    s.carrname,
    f.price
  }
```

---

## 8. CASOS DE USO REALES

### Caso 1: Reporte de Vuelos por Aerolínea

```abap
DEFINE VIEW ZV_FLIGHTS_BY_AIRLINE AS
  SELECT FROM flights AS f
    INNER JOIN scarr AS s
      ON f.airlinecode = s.carrid
  {
    s.carrid,
    s.carrname,
    COUNT(*) AS total_flights,
    AVG(f.price) AS avg_price
  }
  GROUP BY s.carrid, s.carrname
```

---

### Caso 2: Búsqueda de Rutas Disponibles

```abap
DEFINE VIEW ZV_AVAILABLE_ROUTES AS
  SELECT FROM spfli AS route
    INNER JOIN scarr AS airline
      ON route.carrid = airline.carrid
    LEFT OUTER JOIN sbook AS booking
      ON route.flightid = booking.flightid
  WHERE booking.bookid IS NULL
  {
    route.carrid,
    airline.carrname,
    route.cityfrom,
    route.cityto,
    route.flightid
  }
```

---

### Caso 3: Dashboard de Reservas

```abap
DEFINE VIEW ZV_BOOKING_DASHBOARD AS
  SELECT FROM sbook AS booking
    INNER JOIN flights AS flight
      ON booking.flightid = flight.flightid
    INNER JOIN scarr AS airline
      ON flight.airlinecode = airline.carrid
    INNER JOIN spfli AS route
      ON flight.airlinecode = route.carrid
      AND flight.flightid = route.flightid
  {
    booking.bookid,
    booking.customid,
    airline.carrname,
    route.cityfrom,
    route.cityto,
    booking.bookdate
  }
```

---

## Resumen Comparativo de Joins

| Tipo                  | Resultado                 | Uso                            |
| --------------------- | ------------------------- | ------------------------------ |
| **INNER**       | Solo coincidencias        | Datos obligatorios             |
| **LEFT OUTER**  | Izquierda + coincidencias | Datos principales + opcionales |
| **RIGHT OUTER** | Derecha + coincidencias   | Menos común                   |
| **FULL OUTER**  | Todos los registros       | Análisis completo             |


# Puntos Importantes de la Clase - Ejemplos

## 1. **InnerJoin en CDS**

Cesar mostró cómo unir dos fuentes de datos (tabla FLIGHTS + tabla SCARR) usando InnerJoin para obtener solo registros coincidentes en ambas tablas.

## 2. **Sintaxis ON**

```markup
INNER JOIN SCARR AS Airline
ON Flights.AirlineCode = Airline.CarID
```

Define la condición de intersección entre las dos fuentes.

## 3. **Nombres Alias (AS)**

* `AsFlights` para la primera fuente
* `Airline` para la segunda fuente Permiten referenciar columnas sin ambigüedad.

## 4. **Proyección de Columnas**

Seleccionar qué columnas mostrar:

* Todas las de FLIGHTS
* Solo CARNAME de SCARR (renombrada como AirlineName)

## 5. **Auto-completado con Control+Espacio**

Herramienta que sugiere columnas disponibles según el alias usado.

## 6. **Extensibilidad**

El modelo permite agregar más JOINs (LEFT OUTER JOIN, múltiples INNER JOINs) para complejidad mayor.

## 7. **Activación y Testing**

* Activar el objeto CDS
* Usar F8 para visualizar resultados
* Refresh para actualizar datos

¿Necesitas profundizar en algún punto específico?
