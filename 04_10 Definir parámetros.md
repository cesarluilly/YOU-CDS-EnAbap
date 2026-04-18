# 4/10 CDS en ABAP - Definir parámetros - April 09

[**VIEW RECORDING - 5 mins (No highlights)**](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN)

## Propósito de la reunión

[Agregar un parámetro a una vista CDS para el filtrado dinámico de datos.](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=67.0 "PLAY @1:07")

## Puntos clave

* [**Agregar parámetros:** Usa `with parameters` después del nombre de la vista para definir parámetros, cada uno con un tipo de dato (por ejemplo, `s_carr_id` desde la base de datos o un tipo incorporado como `abap.char(3)`).](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=84.0 "PLAY @1:24")
* [**Filtrar con parámetros:** Usa una cláusula `WHERE` con el prefijo `$parameters` (por ejemplo, `carrid = $parameters.PRlineCode`) para referenciar un parámetro. Este prefijo es obligatorio para diferenciar los parámetros de las columnas de datos.](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=170.0 "PLAY @2:50")
* [**Probar en ADT:** Activa la vista y presiona `F8` en ABAP Development Tools (ADT) para abrir una ventana de prueba, donde puedes ingresar valores de parámetros y ver los resultados filtrados.](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=245.0 "PLAY @4:05")

## Temas

### Definición de un parámetro

* [Se agregó un parámetro a la vista CDS existente `SPFly` para habilitar el filtrado dinámico.](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=67.0 "PLAY @1:07")
* [**Sintaxis:** `with parameters PRlineCode : s_carr_id`](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=84.0 "PLAY @1:24")
  * [`PRlineCode`: El nombre del parámetro.](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=84.0 "PLAY @1:24")
  * [`s_carr_id`: El tipo de dato, proveniente de la base de datos.](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=84.0 "PLAY @1:24")
* [**Ubicación:** El bloque `with parameters` debe colocarse después del nombre de la vista y antes de la sentencia `SELECT`.](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=84.0 "PLAY @1:24")
* [**Múltiples parámetros:** Separa los parámetros con comas; el último parámetro de la lista no lleva coma.](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=229.0 "PLAY @3:49")

### Uso del parámetro en un filtro

* [Se agregó la cláusula `WHERE` para filtrar los datos usando el nuevo parámetro.](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=170.0 "PLAY @2:50")
* [**Sintaxis:** `WHERE carrid = $parameters.PRlineCode`](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=170.0 "PLAY @2:50")
  * [**Operador `=`:** Usa el carácter estándar `=` para igualdad, no el operador `EQ` de OpenSQL.](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=170.0 "PLAY @2:50")
  * [**Prefijo `$parameters`:** Este prefijo es obligatorio. Sin él, el sistema trataría `PRlineCode` como una columna desconocida, causando un error.](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=190.0 "PLAY @3:10")

### Prueba de la vista parametrizada

* [La vista fue activada y el sistema emitió una advertencia indicando que el parámetro no se usó. Esto es esperado y no es un error, ya que un parámetro puede definirse para uso futuro sin implementarse inmediatamente en un filtro.](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=133.0 "PLAY @2:13")
* [**Proceso de prueba:**](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=245.0 "PLAY @4:05")
  1. Activa la vista CDS.
  2. Presiona `F8` en ADT para abrir la herramienta de prueba.
  3. Ingresa un valor para `PRlineCode` (por ejemplo, `LH` para Lufthansa).
  4. La herramienta muestra los resultados filtrados.
* [**Pruebas dinámicas:** El botón &#34;PARAMETER&#34; en la herramienta de prueba permite cambiar el valor del parámetro (por ejemplo, a `AA` para American Airlines) para ver diferentes salidas filtradas sin volver a ejecutar la activación.](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=284.0 "PLAY @4:44")

## Próximos pasos

* [**Cesar Luilly Garcia Aguazul:**](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=309.0 "PLAY @5:09")
  * [Continuar con la serie de tutoriales de CDS, basándose en esta vista parametrizada.](https://fathom.video/share/6tsckt68sRFxGishtuEV2odjPdK4NrbN?tab=summary&timestamp=309.0 "PLAY @5:09")

---

---

---



## Propósito

Tutorial educativo sobre  **Core Data Services (CDS) en ABAP** : cómo crear vistas CDS con parámetros para filtrar datos en la base de datos HANA, utilizando ABAP Development Tools (ADT) en Eclipse.

## Glosario

* **CDS** : Core Data Services - vistas creadas en perspectiva ABAP
* **ADT** : ABAP Development Tools
* **HANA** : Base de datos en memoria
* **SPFly** : Tabla fuente de datos utilizada en el ejemplo
* **$parameters** : Sintaxis para referenciar parámetros en CDS
* **WHERE** : Cláusula de filtrado en CDS

## Atajos de Teclado

* **F8** : Ejecutar test/prueba sobre la vista CDS

## Buenas Prácticas y Recomendaciones

1. **Sintaxis de parámetros** : Usar `WITH PARAMETERS` después de `DEFINE VIEW` y antes de `SELECT`
2. **Referencia de parámetros** : Utilizar `$parameters.nombreParametro` para acceder a parámetros (no usar el nombre directo)
3. **Separación de parámetros** : Separar múltiples parámetros con comas; sin coma antes de `SELECT`
4. **Operadores** : En CDS usar `=` en lugar de `EQ` (diferente a OpenSQL)
5. **Punto y coma** : Opcional al cerrar definición CDS (`.`)
6. **Testing** : Usar F8 para probar vistas con diferentes valores de parámetros


# Ejemplo Base de CDS con Parámetros

## Estructura

```abap
DEFINE VIEW nombre_vista
WITH PARAMETERS
  PRlineCode : abap.char(2)
AS SELECT FROM SPFly
{
  columna1,
  columna2,
  key columna_clave
}
WHERE
  carry = $parameters.PRlineCode;
```

## Desglose

| Elemento                                 | Descripción                             |
| ---------------------------------------- | ---------------------------------------- |
| `DEFINE VIEW`                          | Inicia definición de vista CDS          |
| `WITH PARAMETERS`                      | Declara parámetros de filtrado          |
| `PRlineCode : abap.char(2)`            | Parámetro de tipo carácter, longitud 2 |
| `AS SELECT FROM SPFly`                 | Fuente de datos (tabla SPFly)            |
| `WHERE carry = $parameters.PRlineCode` | Filtro usando el parámetro              |
| `;`                                    | Cierre opcional                          |

## Prueba (F8)

El sistema solicita valor para `PRlineCode`:

* Ejemplo: `LH` (Lufthansa) → devuelve registros filtrados
* Ejemplo: `AA` (American Airlines) → devuelve otros registros

 **Nota** : El parámetro es **obligatorio** cada vez que se consume la vista.


# Ejemplos Detallados de Puntos Importantes

## 1. Sintaxis de Parámetros: WITH PARAMETERS

### ✅ Correcto

```abap
DEFINE VIEW cv_flights
WITH PARAMETERS
  p_airline : abap.char(3)
AS SELECT FROM SPFly
{
  carrid,
  connid,
  fldate
}
WHERE
  carrid = $parameters.p_airline;
```

### ❌ Incorrecto

```abap
DEFINE VIEW cv_flights
AS SELECT FROM SPFly
WITH PARAMETERS p_airline : abap.char(3)
{
  carrid
}
```

 **Error** : WITH PARAMETERS debe ir ANTES de AS SELECT

---

## 2. Referencia de Parámetros: $parameters

### ✅ Correcto

```abap
WHERE
  carrid = $parameters.p_airline
  AND connid = $parameters.p_connection;
```

### ❌ Incorrecto

```abap
WHERE
  carrid = p_airline  -- Sistema no reconoce la columna
  AND connid = connection;
```

 **Error** : "Columna desconocida" sin `$parameters.`

---

## 3. Separación de Múltiples Parámetros

### ✅ Correcto

```abap
DEFINE VIEW cv_flight_filter
WITH PARAMETERS
  p_airline : abap.char(3),
  p_date : abap.dats,
  p_destination : abap.char(3)
AS SELECT FROM SPFly
{
  carrid,
  fldate,
  deptime
}
WHERE
  carrid = $parameters.p_airline
  AND fldate = $parameters.p_date
  AND destin = $parameters.p_destination;
```

### ❌ Incorrecto

```abap
WITH PARAMETERS
  p_airline : abap.char(3),
  p_date : abap.dats,
  p_destination : abap.char(3),  -- Coma antes de AS SELECT
AS SELECT FROM SPFly
```

 **Error** : Coma innecesaria antes de AS SELECT

---

## 4. Operadores: = en lugar de EQ

### ✅ Correcto (CDS)

```abap
WHERE
  carrid = $parameters.p_airline
  AND status = 'A'
  AND price > 500;
```

### ❌ Incorrecto (OpenSQL en CDS)

```abap
WHERE
  carrid EQ $parameters.p_airline  -- EQ no funciona en CDS
  AND status = 'A'
  AND price GT 500;  -- GT no funciona en CDS
```

### Comparación: OpenSQL vs CDS

| Operación    | OpenSQL | CDS             |
| ------------- | ------- | --------------- |
| Igual         | `EQ`  | `=`           |
| No igual      | `NE`  | `!=` o `<>` |
| Mayor que     | `GT`  | `>`           |
| Menor que     | `LT`  | `<`           |
| Mayor o igual | `GE`  | `>=`          |
| Menor o igual | `LE`  | `<=`          |

---

## 5. Punto y Coma: Opcional

### ✅ Con punto y coma

```abap
DEFINE VIEW cv_flights
WITH PARAMETERS
  p_airline : abap.char(3)
AS SELECT FROM SPFly
{
  carrid,
  connid
}
WHERE
  carrid = $parameters.p_airline;
```

### ✅ Sin punto y coma (también válido)

```abap
DEFINE VIEW cv_flights
WITH PARAMETERS
  p_airline : abap.char(3)
AS SELECT FROM SPFly
{
  carrid,
  connid
}
WHERE
  carrid = $parameters.p_airline
```

 **Nota** : Ambas formas son válidas. Es cuestión de estilo.

---

## 6. Testing con F8: Diferentes Valores

### Ejemplo Completo

```abap
DEFINE VIEW cv_airline_filter
WITH PARAMETERS
  p_airline : abap.char(3)
AS SELECT FROM SPFly
{
  carrid,
  carrname,
  connid,
  fldate
}
WHERE
  carrid = $parameters.p_airline;
```

### Pruebas (F8)

 **Test 1** : Lufthansa

```markup
Parámetro: p_airline = "LH"
Resultado: Todos los vuelos de Lufthansa
```

 **Test 2** : American Airlines

```markup
Parámetro: p_airline = "AA"
Resultado: Todos los vuelos de American Airlines
```

 **Test 3** : Sin valor (error)

```markup
Parámetro: p_airline = (vacío)
Resultado: Error - parámetro obligatorio
```

---

## 7. Tipos de Datos en Parámetros

### Ejemplos de Tipos

```abap
WITH PARAMETERS
  p_airline : abap.char(3),           -- Carácter fijo
  p_code : abap.char(2),              -- Código de 2 caracteres
  p_date : abap.dats,                 -- Fecha (YYYYMMDD)
  p_time : abap.tims,                 -- Hora (HHMMSS)
  p_amount : abap.dec(15,2),          -- Decimal con 2 decimales
  p_quantity : abap.int4,             -- Entero
  p_description : abap.string,        -- Texto variable
  p_flag : abap.boolean               -- Booleano (X o espacio)
```

---

## 8. Filtros Complejos con Parámetros

### Ejemplo: Múltiples Condiciones

```abap
DEFINE VIEW cv_complex_filter
WITH PARAMETERS
  p_airline : abap.char(3),
  p_min_price : abap.dec(10,2),
  p_max_price : abap.dec(10,2)
AS SELECT FROM SPFly
{
  carrid,
  connid,
  price,
  currency
}
WHERE
  carrid = $parameters.p_airline
  AND price >= $parameters.p_min_price
  AND price <= $parameters.p_max_price;
```

 **Prueba** :

* Airline: "LH"
* Min Price: 100.00
* Max Price: 500.00
* Resultado: Vuelos de Lufthansa entre 100 y 500

---

## 9. Parámetro No Utilizado (Advertencia)

### ✅ Válido (con advertencia)

```abap
DEFINE VIEW cv_flights
WITH PARAMETERS
  p_unused : abap.char(3)  -- Parámetro declarado pero no usado
AS SELECT FROM SPFly
{
  carrid,
  connid
}
WHERE
  carrid = 'LH';  -- No usa p_unused
```

 **Sistema** : Muestra advertencia pero permite activar

### ✅ Mejor Práctica

```abap
DEFINE VIEW cv_flights
WITH PARAMETERS
  p_airline : abap.char(3)
AS SELECT FROM SPFly
{
  carrid,
  connid
}
WHERE
  carrid = $parameters.p_airline;  -- Parámetro utilizado
```

---

## 10. Consumo de Vista CDS con Parámetros

### En ABAP

```abap
SELECT * FROM cv_airline_filter( p_airline = 'LH' )
  INTO TABLE @lt_flights.
```

### En Reporting

```abap
DATA(lt_result) = SELECT * FROM cv_airline_filter( p_airline = 'AA' ).
```

---

## Resumen Rápido

| Punto                  | Regla                                                           |
| ---------------------- | --------------------------------------------------------------- |
| **Ubicación**   | WITH PARAMETERS antes de AS SELECT                              |
| **Referencia**   | Usar `$parameters.nombre`                                     |
| **Múltiples**   | Separar con comas, sin coma antes de AS SELECT                  |
| **Operadores**   | `=`, `!=`, `>`, `<`, `>=`, `<=` (no EQ, NE, GT, LT) |
| **Punto y coma** | Opcional al final                                               |
| **Testing**      | F8 para probar con valores                                      |
| **Obligatorio**  | Parámetro requerido al consumir vista                          |
