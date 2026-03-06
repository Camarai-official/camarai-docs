# 🔎 Audit Report: Camarai TPV
**De:** CTO Google  
**Para:** Product Owner & Equipo de Desarrollo  

He analizado la documentación técnica y la propuesta de base de datos actual. Aunque funcional para un MVP, presenta **riesgos sistémicos** que impedirán la escalabilidad a 100+ locales y la integridad financiera. A continuación, el diagnóstico y plan de acción inmediato.

---

## 1. Deficiencias Detectadadas (Gap Analysis)

### A. Integridad Financiera e Históricos
- **Precio Volátil**: El sistema actual referencia el precio directamente desde `products` en las comandas. Si el precio de un plato cambia mañana, todos los reportes históricos de facturación se corromperán.
- **Detección**: Falta el campo `unit_price_at_sale` en `order_items`.

### B. Normalización y Escalabilidad (Multi-Tenancy)
- **Aislamiento de Datos**: La tabla `tables` referencia a `environments`, pero no todas las entidades tienen un `establishment_id` explícito. En una arquitectura de nube, esto es una brecha de seguridad crítica.
- **Naming Inconsistente**: Mezclar `users` (EN) con `cartas` (ES) aumenta la fricción cognitiva del desarrollador y dificulta la automatización de la API.

### C. Lógica de Negocio en Almacén
- **Recetas Embebidas**: Guardar la receta como un array JSON en `products` impide generar reportes de "Necesidad de Compra" eficientes.
- **Solución**: Necesitamos una relación N:M formal para escandallos.

### D. Seguridad de Terminales
- **PIN Handling**: Guardar el PIN en texto plano o manejar sesiones sin un `terminal_id` único expone al restaurante a fraudes internos.

---

## 2. Plan de Mejoras Inmediato

### [Fase 1] Re-Estructuración de Datos (Convex)
Migraremos a una arquitectura **Snapshot-Based**. Cada vez que ocurre una transacción (venta, fichaje, ajuste de stock), se debe guardar una copia inmutable de las variables aplicables (IVA, Precio, Coste).

### [Fase 2] Normalización Estándar
Adoptaremos **English-Only Naming** para la base de datos y la API, manteniendo el Español solo para la UI. Esto es no negociable para integraciones futuras (Stripe, Meta, etc.).

### [Fase 3] Triggers & Real-time Sinc
Implementaremos `mutation` wrappers en Convex que aseguren que al cerrar una `order`, se disparen los movimientos de stock automáticos basados en la receta.

---

## 3. Próximos Pasos Técnicos
Procederé a re-diseñar el **Diccionario de Datos** en formato profesional de tablas (GRID) para que el equipo de BBDD no tenga dudas sobre tipos, nulos y FKs.
