
Propósito de la reunión

[Explicar la evolución de ABAP para HANA y el papel de Core Data Services (CDS).]()

## Puntos clave

* [**ABAP 7.4 SP5 introdujo el enfoque "de arriba hacia abajo",** permitiendo a los desarrolladores ABAP aprovechar la potencia de HANA directamente desde su entorno familiar, resolviendo la complejidad del método anterior &#34;de abajo hacia arriba&#34;.]()
* [**Core Data Services (CDS) es la capa central de modelado de datos** para el enfoque de arriba hacia abajo, definiendo modelos semánticos ricos (entidades, relaciones, anotaciones) que sirven como la única fuente de la verdad para todas las aplicaciones.]()
* [**Los modelos CDS son altamente flexibles,** admitiendo vistas en capas (básicas → potentes) y funciones avanzadas de SQL como `UNION` que no están disponibles en el Diccionario ABAP tradicional.]()
* [**Existen dos variantes de CDS:** HANA CDS (solo HANA, desarrollo nativo) y ABAP CDS (multibase de datos, basado en NetWeaver), ambas con el objetivo compartido de una definición unificada de datos.]()

## Temas

### El desafío: ABAP para HANA "de abajo hacia arriba"

* [ABAP 7.4 introdujo el &#34;Code Pushdown&#34; para trasladar los cálculos a la base de datos HANA, reemplazando el ineficiente modelo &#34;Datos al código&#34; (obtener todos los datos → procesar en ABAP).]()
* [El enfoque inicial &#34;de abajo hacia arriba&#34; (ABAP 7.4 SP2) tenía desventajas importantes:]()
  * [**Desarrollo en dos mundos:** Requería trabajar tanto en HANA como en ABAP.]()
  * [**Configuración compleja:** Necesitaba un usuario de base de datos HANA por separado, a menudo difícil de obtener.]()
  * [**Sincronización manual:** Exigía que los desarrolladores sincronizaran manualmente los objetos de HANA y ABAP.]()

### La solución: ABAP para HANA "de arriba hacia abajo"

* [ABAP 7.4 SP5 introdujo el enfoque &#34;de arriba hacia abajo&#34; para resolver estos problemas.]()
* [**Beneficio clave:** Los desarrolladores trabajan completamente dentro del entorno ABAP mientras acceden a las capacidades de HANA.]()
* [**Nuevas funcionalidades:**]()
  * [Escribir SQLScript directamente en ABAP.]()
  * [Crear vistas de base de datos con combinaciones (joins) y agregaciones avanzadas.]()
* [**Nota:** El enfoque &#34;de abajo hacia arriba&#34; sigue siendo necesario para escenarios específicos y complejos.]()

### La base: Core Data Services (CDS)

* [CDS es la capa de modelado de datos que potencia el enfoque de arriba hacia abajo.]()
* [**Propósito:** Definir modelos de datos semánticos ricos como vistas CDS.]()
* [**Estructura:**]()
  * [**Entidades:** Representan objetos de negocio (p. ej., pedidos, productos).]()
  * [**Relaciones:** Definen vínculos semánticos entre entidades (como claves externas).]()
  * [**DDL (Data Definition Language):** Un lenguaje estándar basado en SQL para definir CDS.]()
  * [**Asociaciones:** Definen relaciones entre vistas CDS.]()
  * [**Anotaciones:** Dirigen el uso específico de dominio de los artefactos CDS.]()
  * [**Expresiones:** Permiten cálculos dentro de la vista (p. ej., agregación de medidas).]()
* [**Ventajas frente al Diccionario ABAP:**]()
  * [**Fuente unificada:** Sirve a todas las aplicaciones (transaccionales, analíticas).]()
  * [**Vistas en capas:** Construye vistas complejas apilando vistas básicas.]()
  * [**SQL avanzado:** Admite operadores como `UNION`.]()

### Variantes de CDS: HANA vs. ABAP

* [**HANA CDS:**]()
  * [**Plataforma:** Solo SAP HANA.]()
  * [**Contexto:** Parte de SAP HANA Extended Application Services (XS).]()
  * [**Repositorio:** Repositorio de desarrollo nativo de HANA.]()
* [**ABAP CDS:**]()
  * [**Plataforma:** La mayoría de las principales plataformas de bases de datos, incluida HANA.]()
  * [**Contexto:** Totalmente implementado en el servidor NetWeaver (ABAP 7.4 SP5).]()
  * [**Repositorio:** Repositorio de desarrollo ABAP.]()
* [**Objetivo común:** Ambas variantes buscan proporcionar una definición común y central para los modelos de datos.]()

## Próximos pasos

* [**Cesar Luilly Garcia Aguazul:**]()
  * [Seguir explorando las capacidades de CDS, con foco en las vistas en capas y las funcionalidades avanzadas de SQL.]()
  * [Investigar casos de uso prácticos del enfoque &#34;de abajo hacia arriba&#34; para comprender su relevancia restante.]()

---

---

---


# Resumen de la Reunión

## Propósito de la Reunión

Cesar presentó las nuevas capacidades de ABAP para SAP HANA en Fathom Server 7.4 Service Pack 5, enfocándose en el enfoque "Code Pushdown" y Core Data Services (CDS) para optimizar el rendimiento mediante cálculos en la capa de base de datos.

## Glosario

| Término                                      | Definición                                                                          |
| --------------------------------------------- | ------------------------------------------------------------------------------------ |
| **Code Pushdown**                       | Paradigma que traslada cálculos a la capa de persistencia (BD) para aprovechar HANA |
| **Data to Code**                        | Enfoque antiguo: SELECT todos los datos, luego procesar en servidor de aplicaciones  |
| **Code to Data**                        | Enfoque nuevo: procesar cálculos en BD, enviar resultados a aplicación             |
| **CDS (Core Data Services)**            | Capa para definir modelos de datos semánticamente ricos como vistas                 |
| **DDL (Data Definition Language)**      | Lenguaje SQL estándar en que se basan los CDS                                       |
| **Asociaciones**                        | Relaciones entre vistas CDS (equivalente a claves foráneas)                         |
| **Anotaciones**                         | Directivas que especifican uso de artefactos CDS                                     |
| **XAS (Extended Application Services)** | Servidor de aplicaciones nativo para SAP HANA                                        |

## Atajos de Teclado

*No se mencionaron en la reunión.*

## Buenas Prácticas, Recomendaciones y Consejos

* **Selectividad en Code Pushdown** : No trasladar *todos* los cálculos a BD, solo los que tengan sentido (ej: SUM de posiciones de factura)
* **Modelos CDS centralizados** : Usar CDS como definiciones centrales reutilizables en múltiples aplicaciones (transaccionales y analíticas)
* **Enfoque estratificado** : Construir vistas básicas primero, luego agregar vistas potentes que las transforman
* **Mantener sincronización** : Sincronizar objetos HANA y ABAP, gestionar ciclo de vida
* **Flexibilidad de plataforma** : CDS en ABAP opera en múltiples BD (no solo HANA), ofreciendo mayor portabilidad


# Ejemplo de Base Mencionado

**Cálculo del importe total de posiciones de una factura**

## Enfoque Antiguo (Data to Code)

```markup
SELECT todas las posiciones de la factura
LOOP para cada posición
  Sumar el importe
FIN LOOP
```

❌ Ineficiente: trae todos los datos a la aplicación y procesa en bucle

## Enfoque Nuevo (Code to Data)

```markup
SELECT SUM(importe) FROM posiciones_factura
```

✅ Eficiente: la agregación se realiza en la base de datos HANA, retorna solo el resultado

 **Ventaja** : Aprovecha las capacidades de alto rendimiento de HANA en memoria, reduciendo transferencia de datos y procesamiento en el servidor de aplicaciones.


Investigación de Ejemplos por Punto Importante

## 1. Code Pushdown vs Data to Code

### Data to Code (Antiguo - Ineficiente)

```abap
* Traer TODOS los datos a la aplicación
SELECT * FROM vbap INTO TABLE lt_items
  WHERE vbeln = '0000100001'.

* Procesar en el servidor de aplicaciones
DATA lv_total TYPE p DECIMALS 2.
LOOP AT lt_items INTO ls_item.
  lv_total = lv_total + ls_item-netwr.
ENDLOOP.
```

 **Problema** : Si hay 10,000 líneas, trae todas a memoria y suma en bucle.

### Code to Data (Nuevo - Eficiente)

```abap
* Cálculo en la base de datos
SELECT SUM( netwr ) INTO lv_total
  FROM vbap
  WHERE vbeln = '0000100001'.
```

 **Ventaja** : HANA suma en memoria de BD, retorna solo 1 valor.

---

## 2. CDS (Core Data Services) - Definición Centralizada

### Ejemplo: Vista CDS de Pedidos

```sql
@AccessControl.authorizationCheck: #CHECK
define view ZC_ORDERS as select from vbak
  association [0..1] to ZC_CUSTOMERS as _customer
    on vbak.kunnr = _customer.kunnr
{
  key vbak.vbeln as order_id,
  vbak.erdat as order_date,
  vbak.kunnr as customer_id,
  vbak.netwr as total_amount,
  _customer
}
```

 **Ventajas** :

* Definición centralizada reutilizable
* Relaciones semánticas claras (asociaciones)
* Puede usarse en reportes, apps transaccionales y analíticas

---

## 3. Enfoque Estratificado de CDS

### Nivel 1: Vista Básica (Datos Crudos)

```sql
define view ZI_SALES_BASIC as select from vbap {
  key vbeln as order_id,
  key posnr as line_item,
  matnr as product_id,
  netwr as line_amount
}
```

### Nivel 2: Vista Intermedia (Transformación)

```sql
define view ZI_SALES_CALC as select from ZI_SALES_BASIC {
  order_id,
  product_id,
  line_amount,
  line_amount * 1.19 as amount_with_tax
}
```

### Nivel 3: Vista Analítica (Agregación)

```sql
define view ZC_SALES_SUMMARY as select from ZI_SALES_CALC {
  order_id,
  sum(amount_with_tax) as total_with_tax
} group by order_id
```

 **Beneficio** : Cada capa reutiliza la anterior, manteniendo lógica modular.

---

## 4. Asociaciones en CDS

### Ejemplo: Relación Pedido-Cliente-Dirección

```sql
define view ZC_ORDER_DETAILS as select from vbak
  association [0..1] to ZC_CUSTOMERS as _customer
    on vbak.kunnr = _customer.kunnr
  association [0..1] to ZC_ADDRESSES as _address
    on _customer.kunnr = _address.kunnr
{
  key vbak.vbeln as order_id,
  vbak.erdat as order_date,
  _customer.name as customer_name,
  _address.city as delivery_city,
  _customer,
  _address
}
```

 **Ventaja** : Define relaciones sin necesidad de JOINs explícitos en consultas posteriores.

---

## 5. Anotaciones en CDS

### Ejemplo: Anotaciones para UI y Seguridad

```sql
@AccessControl.authorizationCheck: #CHECK
@UI.headerInfo: { typeName: 'Pedido', typeNamePlural: 'Pedidos' }
@UI.presentationVariant: [{ sortOrder: [{ by: 'order_date', direction: #DESC }] }]
define view ZC_ORDERS as select from vbak {
  @UI.hidden: true
  key vbak.vbeln as order_id,
  
  @UI.lineItem: { position: 10 }
  @UI.selectionField: [{ position: 10 }]
  vbak.erdat as order_date,
  
  @UI.lineItem: { position: 20 }
  vbak.netwr as total_amount
}
```

 **Uso** : Controla visualización, seguridad y comportamiento sin código adicional.

---

## 6. Operador UNION en CDS

### Ejemplo: Combinar Ventas y Devoluciones

```sql
define view ZC_ALL_TRANSACTIONS as
  select from vbak {
    vbeln as transaction_id,
    erdat as transaction_date,
    netwr as amount,
    'SALE' as transaction_type
  }
  union all
  select from vbfa {
    vbeln as transaction_id,
    erdat as transaction_date,
    netwr as amount,
    'RETURN' as transaction_type
  }
```

 **Beneficio** : Un único resultado con ambos tipos de transacciones.

---

## 7. Diferencia: CDS en HANA vs CDS en ABAP

| Aspecto                 | CDS HANA                    | CDS ABAP                       |
| ----------------------- | --------------------------- | ------------------------------ |
| **Plataforma BD** | Solo SAP HANA               | HANA, Oracle, SQL Server, etc. |
| **Introducido**   | Support Package 06 HANA XAS | NetWeaver 7.4 SP05             |
| **Repositorio**   | HANA Repository             | ABAP Repository                |
| **Ejemplo**       | Cálculos nativos HANA      | Portabilidad multi-BD          |

### Ejemplo CDS ABAP (Portátil)

```abap
@AbapCatalog.sqlViewName: 'ZV_ORDERS'
define view ZC_ORDERS_ABAP as select from vbak {
  key vbak.vbeln as order_id,
  vbak.netwr as total_amount
}
```

Funciona en cualquier BD soportada por ABAP.

---

## 8. Sincronización HANA-ABAP

### Desafío

```markup
Cambio en HANA → Debe reflejarse en ABAP
Cambio en ABAP → Debe reflejarse en HANA
```

### Solución con SP5

* **Enfoque Top-Down** : Definir en ABAP, desplegar automáticamente en HANA
* **Ciclo de vida unificado** : Un solo repositorio (ABAP)
* **Menos duplicación** : No mantener objetos en ambos lados

---

## Resumen Comparativo

| Concepto      | Antiguo                    | Nuevo (SP5)               |
| ------------- | -------------------------- | ------------------------- |
| Cálculos     | Servidor aplicaciones      | Base de datos (HANA)      |
| Modelos datos | ABAP Dictionary (limitado) | CDS (rico, estratificado) |
| Desarrollo    | Dos mundos (HANA + ABAP)   | Un mundo (ABAP top-down)  |
| Portabilidad  | Solo HANA                  | Multi-plataforma          |
| Mantenimiento | Sincronización manual     | Automático               |
