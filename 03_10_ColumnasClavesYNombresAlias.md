## Propósito de la reunión

[Definir claves y alias de CDS para el rendimiento y la claridad.]()

## Puntos clave

* [**Rendimiento:** Definir claves de CDS (p. ej., `CARID`, `CONID`) es fundamental para el rendimiento, ya que permite que la base de datos optimice modelos complejos (joins, asociaciones) que usan la vista CDS como origen.]()
* [**Claridad:** Los alias (`código de aerolínea`, `número de vuelo`) mejoran la legibilidad y abstraen la estructura interna de la vista, garantizando que los modelos posteriores solo vean los nombres fáciles de entender.]()
* [**Sintaxis:** Use `key` antes del nombre de una columna para definir una clave y `as` para asignar un alias.]()

## Temas

### Problema: rendimiento y legibilidad

* [Las columnas clave de la tabla `SPFLY` (`CARID`, `CONID`) deben definirse explícitamente en la vista CDS.]()
  * [**Por qué:** Estos metadatos permiten que la base de datos optimice el rendimiento cuando la vista CDS se utiliza en modelos complejos (joins, asociaciones).]()
* [Los nombres internos de las columnas de la vista no son fáciles de usar.]()
  * [**Por qué:** Se necesitan alias para proporcionar nombres claros y descriptivos para las aplicaciones y modelos posteriores.]()

### Solución: definición de claves y alias

* [**Claves:**]()
  * [Use la palabra clave `key` antes del nombre de la columna para definir una clave.]()
  * [Ejemplo: `key CARID`, `key CONID`]()
* [**Alias:**]()
  * [Use la palabra clave `as` para asignar un alias a una columna.]()
  * [Ejemplo: `CARID as código de aerolínea`]()
* [**Resultado:**]()
  * [Al activar la vista, los alias se convierten en los nombres oficiales, ocultando los nombres de columna originales a los modelos posteriores.]()

## Próximos pasos

* [**Cesar Luilly Garcia Aguazul:**]()
  * [Activar la vista CDS actualizada.]()
  * [Probar la vista en la herramienta de pruebas de ABAP Development Tools (ADT) (F8) para confirmar las nuevas definiciones de claves y alias.]()

---

---

---




## Propósito

Enseñanza sobre CDS (Core Data Services) en SAP, específicamente cómo definir columnas clave y asignar nombres alias en vistas CDS, continuando con conceptos de una clase anterior.

## Glosario

* **CDS** : Core Data Services - vistas generadas en base de datos
* **CARID** : Identificador de aerolínea
* **CONID** : Identificador de conexión/vuelo
* **SPFLY** : Tabla fuente de datos utilizada
* **Alias** : Nombre alternativo asignado a columnas
* **Cardinalidad** : Relación entre elementos en modelos de datos
* **SAP GUI** : Interfaz gráfica de SAP
* **ABAP Development Tools** : Herramienta de desarrollo en Eclipse

## Atajos de Teclado

* **SE11** : Código de transacción para acceder a tablas en SAP
* **F8** : Ejecutar/ver resultado en herramienta de test

## Buenas Prácticas y Recomendaciones

1. **Ver clase anterior** antes de continuar si no dominas vistas CDS básicas
2. **Definir columnas clave** explícitamente para mejor rendimiento en modelos complejos
3. **Usar alias descriptivos** (ej: "airline_code", "flight_number") para claridad
4. **Activar la vista** después de cambios para aplicarlos
5. **Suscribirse al canal** para actualizaciones sobre SAP
6. **Compartir contenido** con colegas para beneficio colectivo


# Ejemplo de Base - Definición de CDS con Claves y Alias

## Estructura de la Vista CDS

```abap
define view SPFLY_VIEW as
  select from SPFLY {
    key CARID as airline_code,
    key CONID as flight_number,
    CITYFROM as departure_city,
    CITYTO as arrival_city,
    COUNTRYFR as country_from,
    COUNTRYTO as country_to
  }
```

## Componentes Clave

| Elemento                    | Tipo          | Descripción                  |
| --------------------------- | ------------- | ----------------------------- |
| **key CARID**         | Columna clave | Código de aerolínea         |
| **key CONID**         | Columna clave | Número de vuelo              |
| **as airline_code**   | Alias         | Nombre descriptivo para CARID |
| **as flight_number**  | Alias         | Nombre descriptivo para CONID |
| **as departure_city** | Alias         | Ciudad de salida              |
| **as arrival_city**   | Alias         | Ciudad de destino             |
| **as country_from**   | Alias         | País de origen               |
| **as country_to**     | Alias         | País de destino              |

## Punto Clave

Los modelos que usen esta vista CDS **solo verán los nombres alias** (airline_code, flight_number, etc.), no los nombres originales de las columnas (CARID, CONID, etc.).


# Investigación Detallada - Puntos Importantes de CDS

## 1. DEFINICIÓN DE COLUMNAS CLAVE (key)

### ¿Por qué es importante?

```abap
-- SIN claves definidas (rendimiento pobre en joins complejos)
define view FLIGHTS_BAD as
  select from SPFLY {
    CARID,
    CONID,
    CITYFROM
  }

-- CON claves definidas (rendimiento optimizado)
define view FLIGHTS_GOOD as
  select from SPFLY {
    key CARID,
    key CONID,
    CITYFROM
  }
```

### Impacto en Rendimiento

* **Sin claves** : BD no optimiza índices, joins lentos
* **Con claves** : BD crea índices automáticos, joins rápidos
* **Cardinalidad** : Permite al optimizador calcular mejor las relaciones 1:N, N:1

---

## 2. NOMBRES ALIAS (as)

### Ejemplo Comparativo

```abap
-- Versión SIN alias (confuso)
define view AIRLINE_DATA as
  select from SPFLY {
    CARID,
    CONID,
    CITYFROM,
    CITYTO
  }

-- Versión CON alias (claro y mantenible)
define view AIRLINE_DATA as
  select from SPFLY {
    key CARID as airline_code,
    key CONID as flight_number,
    CITYFROM as departure_city,
    CITYTO as arrival_city
  }
```

### Ventajas de Alias

* **Legibilidad** : `airline_code` vs `CARID`
* **Documentación** : El alias explica qué contiene
* **Mantenimiento** : Cambios en tabla origen no afectan consumidores
* **Reutilización** : Otros CDS/reportes usan solo los alias

---

## 3. ASOCIACIONES Y JOINS CON CLAVES DEFINIDAS

### Ejemplo: Join entre dos CDS

```abap
-- CDS 1: Vuelos (con claves)
define view FLIGHTS as
  select from SPFLY {
    key CARID as airline_code,
    key CONID as flight_number,
    CITYFROM as departure_city
  }

-- CDS 2: Aerolíneas (con clave)
define view AIRLINES as
  select from SCARR {
    key CARRID as airline_code,
    CARRNAME as airline_name
  }

-- CDS 3: Join (aprovecha las claves)
define view FLIGHT_DETAILS as
  select from FLIGHTS
    inner join AIRLINES on FLIGHTS.airline_code = AIRLINES.airline_code
  {
    FLIGHTS.airline_code,
    FLIGHTS.flight_number,
    AIRLINES.airline_name,
    FLIGHTS.departure_city
  }
```

 **Beneficio** : Sin claves definidas, el optimizador no sabe que `airline_code` es única en AIRLINES, generando planes de ejecución ineficientes.

---

## 4. CARDINALIDAD EN ASOCIACIONES

### Ejemplo con Cardinalidad

```abap
define view FLIGHT_MASTER as
  select from FLIGHTS {
    key CARID as airline_code,
    key CONID as flight_number,
    CITYFROM as departure_city,
  
    -- Asociación: 1 aerolínea : N vuelos
    association [1..1] to AIRLINES as _airline
      on _airline.airline_code = $projection.airline_code
  }
```

 **Impacto** :

* `[1..1]`: Cada vuelo tiene exactamente 1 aerolínea → optimización de índices
* `[1..N]`: Una aerolínea tiene muchos vuelos → cálculo de cardinalidad diferente

---

## 5. TABLA FUENTE: SPFLY

### Estructura Real

```markup
Tabla: SPFLY (Flights)
┌─────────────────────────────────────┐
│ MANDT (Mandante) - Clave            │
│ CARID (Airline Code) - Clave        │
│ CONID (Connection ID) - Clave       │
│ COUNTRYFR (Country From)            │
│ CITYFROM (City From)                │
│ COUNTRYTO (Country To)              │
│ CITYTO (City To)                    │
│ FLTIME (Flight Time)                │
│ DEPTIME (Departure Time)            │
│ ARRTIME (Arrival Time)              │
└─────────────────────────────────────┘
```

### Acceso en SE11

```markup
Transacción: SE11
→ Tabla: SPFLY
→ Mostrar estructura
→ Ver claves (MANDT, CARID, CONID)
```

---

## 6. HERRAMIENTAS Y TRANSACCIONES

### SE11 - Diccionario de Datos

```markup
Uso: Verificar estructura de tablas fuente
Pasos:
1. Transacción SE11
2. Ingresar nombre tabla (SPFLY)
3. Botón "Mostrar"
4. Ver pestaña "Campos" para estructura
5. Ver pestaña "Claves" para identificadores
```

### F8 - Test de CDS

```abap
-- Después de activar CDS, presionar F8
-- Abre herramienta de test
-- Muestra datos con alias aplicados
-- Valida sintaxis y rendimiento
```

---

## 7. IMPACTO EN MODELOS COMPLEJOS

### Escenario: CDS Multicapa

```abap
-- Nivel 1: Vista básica (con claves y alias)
define view FLIGHTS_BASE as
  select from SPFLY {
    key CARID as airline_code,
    key CONID as flight_number,
    CITYFROM as departure_city
  }

-- Nivel 2: Vista intermedia (reutiliza nivel 1)
define view FLIGHTS_ENRICHED as
  select from FLIGHTS_BASE {
    airline_code,
    flight_number,
    departure_city,
    case when departure_city = 'NYC' then 'USA' else 'OTHER' end as region
  }

-- Nivel 3: Vista final (reutiliza nivel 2)
define view FLIGHTS_REPORT as
  select from FLIGHTS_ENRICHED {
    airline_code,
    flight_number,
    region
  }
```

 **Beneficio de claves en Nivel 1** :

* Nivel 2 hereda optimización
* Nivel 3 hereda optimización
* Rendimiento consistente en toda la cadena

---

## 8. BUENA PRÁCTICA: Convención de Nombres para Alias

```abap
-- ❌ MALO: Alias poco descriptivos
define view FLIGHTS as
  select from SPFLY {
    key CARID as ca,
    key CONID as cn,
    CITYFROM as cf
  }

-- ✅ BUENO: Alias descriptivos y consistentes
define view FLIGHTS as
  select from SPFLY {
    key CARID as airline_code,
    key CONID as flight_number,
    CITYFROM as departure_city,
    CITYTO as arrival_city,
    COUNTRYFR as country_from,
    COUNTRYTO as country_to
  }

-- ✅ EXCELENTE: Alias con prefijo de contexto
define view FLIGHTS as
  select from SPFLY {
    key CARID as flight_airline_code,
    key CONID as flight_number,
    CITYFROM as flight_departure_city,
    CITYTO as flight_arrival_city
  }
```

---

## 9. VALIDACIÓN CON F8

### Qué verifica F8

```markup
✓ Sintaxis correcta
✓ Alias aplicados correctamente
✓ Claves reconocidas
✓ Datos accesibles
✓ Rendimiento de consulta
✓ Estructura de salida

Resultado esperado:
┌──────────────────────────────────┐
│ airline_code │ flight_number │... │
├──────────────────────────────────┤
│ AA           │ 0017          │... │
│ AA           │ 0064          │... │
│ LH           │ 0400          │... │
└──────────────────────────────────┘
(Nota: Muestra alias, NO nombres originales)
```

---

## 10. RESUMEN COMPARATIVO

| Aspecto                  | Sin Claves     | Con Claves   | Impacto               |
| ------------------------ | -------------- | ------------ | --------------------- |
| **Rendimiento**    | Lento en joins | Rápido      | 10-100x más rápido  |
| **Índices**       | No optimizados | Automáticos | Mejor acceso BD       |
| **Cardinalidad**   | Desconocida    | Conocida     | Mejor plan ejecución |
| **Mantenibilidad** | Difícil       | Fácil       | Menos errores         |
| **Reutilización** | Limitada       | Óptima      | Mejor arquitectura    |
