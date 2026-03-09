# 📚 Camarai Documentation Repository (Mintlify)

Este repositorio contiene la **documentación técnica y estratégica** del ecosistema Camarai. No es el software en sí, sino el cerebro informativo que guía el desarrollo del Dashboard, POS, Carta y Agentes IA.

## 🚀 Logros Recientes (Auditoría Técnica)

Hemos transformado una documentación estática en un activo vivo alineado con el código real:

1.  **Auditoría de "Veneno" de Datos**: Mapeo exhaustivo de toda la deuda técnica (strings en cálculos, naming inconsistente, mocks hardcodeados).
2.  **Regla de Oro Nº1**: Establecimiento del Dashboard como el cerebro único de gestión y autoridad de datos.
3.  **Constitución de Nomenclatura**: Definición estricta de estándares (English-only, CamelCase, Tipos Numéricos puros).
4.  **Omni-Sincronización**: Definición del principio de reactividad total entre dispositivos vía Convex.
5.  **Inventario Verificado**: ~65 pantallas, ~146 componentes y 33 contratos de tipos (types) validados contra el código fuente.

---

## 🗺️ Roadmap de la Documentación (Próximos Pasos)

El objetivo es alcanzar el **100% de cobertura informativa** antes de la integración total con el Backend.

### 🏁 Fase 1: Infraestructura de Datos (Cierre Inmediato)
- [ ] **Documentar BBDD (Convex Schema)**: Finalizar `ingenieria/bbdd.mdx` una vez el esquema esté limpio de strings.
- [ ] **Documentar 7 Vistas Huérfanas**: Crear las páginas de tipos y lógica para Clientes, Chat, Notificaciones, Inventario, Reservas y Dashboard.
- [ ] **Contratos de API**: Documentar los webhooks actuales de n8n y su transición a mutaciones de Convex.

### 🏁 Fase 2: Completado de Vistas Operativas
- [ ] **Documentación del POS (Operativa)**: Detallar los flujos de `Caja`, `Mesas`, `KDS` y `Recibos` una vez salgan de placeholders.
- [ ] **Flujo de la Carta**: Documentar la arquitectura de sesiones de WhatsApp y su vínculo con la identificación de mesas.
- [ ] **Documentar Hardware**: Guía técnica de conexión de impresoras y terminales táctiles gestionados desde el Dashboard.

### 🏁 Fase 3: Guía de Agentes IA
- [ ] **Entrenamiento del Agente Cliente**: Documentar los prompts base y la lógica de recomendación (upselling).
- [ ] **Lógica de Voz (V2)**: Especificar el contrato de datos para el Agente Camarero (Voice-to-Order).

---

## 🛠️ Tecnologías del Proyecto
- **Generador**: [Mintlify](https://mintlify.com)
- **Formato**: MDX (Markdown + React Components)
- **Estructura**: Basada en productos (Dash, POS, Carta) y capas (Ingeniería, Operativa).

---

## 💻 Desarrollo Local

```bash
# Instalar Mintlify CLI
npm i -g mintlify

# Ejecutar documentación
mintlify dev
```

> [!TIP]
> **Alineación Crítica**: Antes de sugerir una mejora en la UI o en el Schema de datos, consulta siempre los documentos de `Alineación` y `Nomenclatura` en la sección de Ingeniería.
