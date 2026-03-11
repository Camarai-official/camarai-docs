# Camarai Documentation Repository (Mintlify)

Este repositorio centraliza la **inteligencia estratégica** de Camarai. Documentamos el paso de un sistema basado en mocks a una arquitectura de producción reactiva.

---

## Estado de la Verdad Técnica

| Pilar | Estado | Documento de Referencia |
| :--- | :---: | :--- |
| **Vistas y UI** | ✅ Estructurado | Todos los `.mdx` tienen Tabs + Tablas |
| **Roles y Permisos** | ✅ Sincronizado | [`ingenieria/roles.mdx`](ingenieria/roles.mdx) |
| **Autenticación** | ✅ Documentado | [`ingenieria/autenticacion.mdx`](ingenieria/autenticacion.mdx) |
| **Base de Datos** | ✅ Especificación completa | [`ingenieria/bbdd.mdx`](ingenieria/bbdd.mdx) — 25 tablas, ~200 campos |
| **Alineación de Datos** | 🟡 Sincronizado con BBDD | [`ingenieria/alineacion.mdx`](ingenieria/alineacion.mdx) |
| **Backend Convex** | 🔴 Pendiente | Vista por crear en Ingeniería |
| **Capturas de Pantalla** | 🟡 10 faltantes | Ver sección "Auditoría Visual" |

> [!IMPORTANT]
> **Omni-Sincronización**: En Camarai, cualquier cambio en cualquier dispositivo (POS, PDA, KDS o Dashboard) se refleja instantáneamente en el resto del ecosistema. La documentación debe respetar este principio de "Verdad Única".

---

## Roadmap de la Documentación

### Fase 1: Auditoría Visual Completa *(En progreso)*
- [x] Estructura de Tabs y Tablas en todas las vistas.
- [x] Placeholders de imágenes con nombres estandarizados (`TODO-*.png`).
- [ ] Captura de pantallas de las 16 vistas/modals pendientes.

### Fase 2: Especificación de BBDD *(Completada)*
- [x] Especificación maestra con trazabilidad Tabla → Vista → Rol.
- [x] Plan de implementación en 5 fases con revisión en bucle.
- [x] Diagrama ER completo con campos dentro de cada tabla.
- [x] Modelo de monetización dual (suscripción + comisión por pedido).
- [x] Sincronización de nomenclatura entre `bbdd.mdx` y `alineacion.mdx`.
- [ ] Validación cruzada de cada tabla contra las vistas operativas.
- [ ] Glosario de Enums unificado en Inglés.

### Fase 3: Backend Convex *(Pendiente)*
- [ ] Crear vista dedicada en Ingeniería y Datos para el backend de Convex.
- [ ] Documentar el `convex/schema.ts` basado en la especificación de `bbdd.mdx`.
- [ ] Documentar mutations, queries y acciones de Convex.
- [ ] Mapear qué funciones Convex consume cada app (Dashboard, POS, Carta, PDA).
- [ ] Documentar la estrategia de autenticación server-side (validación de `role` en cada mutación).

### Fase 4: Flujos de Agentes e IA
- [x] Documentación de los 4 agentes (Cliente, Gerente, Camarero, TPV).
- [ ] Arquitectura n8n: Mapeo de flujos.
- [ ] Manual del Bot del Cliente: Lógica de recomendaciones.

---

## Auditoría Visual — Capturas Pendientes (10)

### Gestión de Catálogo y Stock (3)
- [ ] `TODO-productos-view-main.png` — Listado de productos con filtros.
- [ ] `TODO-categorias-view-main.png` — Listado de categorías.
- [ ] `TODO-ingredientes-view-main.png` — Listado de materia prima.

### Marketing y Clientes (5)
- [ ] `TODO-clientes-view-main.png` — Tabla CRM.
- [ ] `TODO-clientes-modal-ficha.png` — Ficha detalle de cliente.
- [ ] `TODO-marketing-promociones-main.png` — Lista de campañas WhatsApp.
- [ ] `TODO-marketing-promociones-modal.png` — Editor de campaña.
- [ ] `TODO-marketing-promociones-preview.png` — Vista previa del mensaje.

### Comunicación (2)
- [ ] `TODO-chat-view-main.png` — Vista principal del chat.
- [ ] `TODO-chat-agent-alerts.png` — Alerta de agente IA en el chat.

### Terminales Operativos (POS, PDA) (1)
- [ ] `TODO-pda-camarero-view.png` — Interfaz principal de la PWA del camarero.

### Imágenes Potencialmente Sobrantes
- `modal-carta-general.png` / `modal-carta-whatsapp.png` — Reemplazadas.
- `modal-categoria-general.png` / `apariencia.png` — Reemplazadas.
- `modal-empleado.png` — Redundante con `personal-modal-*`.
- `modal-ingrediente.png` — Redundante con `modal-inventario-ingrediente.png`.
- `personal-view.png` — La docu usa capturas por tab.

---

## Desarrollo Local

```bash
# Instalar Mintlify CLI
npm i -g mintlify

# Ejecutar documentación
mintlify dev
```

---

## Estructura del Repositorio

```
camarai-docs/
├── general/          # Índice, Roadmap, Nomenclatura
├── ingenieria/       # BBDD, Roles, Autenticación, Alineación, Componentes
├── operativa/        # Dashboard, Comandas, Plano Mesas, Chat, POS, PDA Camarero
├── gestion/          # Productos, Categorías, Ingredientes, Inventario, Reservas, Personal, Reportes, Cartas
├── marketing/        # Clientes, Promociones, Notificaciones
├── configuracion/    # Configuración General, Perfil, Impuestos
├── agentes/          # Agente Cliente, Gerente, Camarero, TPV
├── images/           # Capturas de pantalla (~93 archivos)
└── mint.json         # Navegación y branding
```
