# 📚 Camarai Documentation Repository (Mintlify)

Este repositorio centraliza la **inteligencia estratégica** de Camarai. Documentamos el paso de un sistema basado en mocks a una arquitectura de producción reactiva.

## 🧠 Estado de la Verdad Técnica

Tras la última auditoría, hemos establecido los pilares para la integración con el Backend:

1.  **Prioridad de Vistas Huérfanas**: Hemos detectado que completar las vistas sin lógica es el paso previo e indispensable para diseñar una BBDD (Convex) robusta. No se construye el esquema sin entender el flujo de datos total del Dashboard.
2.  **Rol de n8n**: Definido exclusivamente para el **Agente IA** y **Comunicaciones Externas**. La lógica operativa interna reside en Convex. 
3.  **Estandarización de Datos**: Sustitución de "veneno" (strings en cálculos matemáticos) por tipos numéricos puros y enums en inglés.
4.  **Hardware en Radar**: La integración con periféricos (impresoras/TPV) queda en fase de definición, evaluando la mejor vía de comunicación.

---

## 🗺️ Roadmap de la Documentación (Objetivos de la Doc)

Este es el plan para que la "Doc" alcance su madurez, permitiendo el acceso rápido a cada rincón del sistema.

### 🏁 Fase 1: Auditoría Visual Completa (Galería)
- [ ] **Captura de Pantallas**: Documentación visual de TODAS las vistas actuales (POS, Dash y Carta).
- [ ] **Galería Histórica**: Estructurar Mintlify para que todas las capturas sean accesibles sin necesidad de eliminar versiones anteriores.
- [ ] **Detección de Vacíos**: Listado visual de partes del Dashboard que carecen de backend.

### 🏁 Fase 2: Diseño de BBDD y Contratos
- [ ] **Esquema Convex**: Documentar el `schema.ts` unificado una vez saneadas las vistas huérfanas.
- [ ] **Glosario de Enums**: Definir todos los estados (Libre, Ocupado, Sucio) en inglés técnico para la base de datos.

### 🏁 Fase 3: Flujos de Agentes e IA
- [ ] **Arquitectura n8n**: Mapeo de flujos para el Agente Cliente y notificaciones de Gerencia.
- [ ] **Manual del Bot del Cliente**: Lógica de recomendaciones y links de sesión.

---

## 🛠️ Desarrollo Local

```bash
# Instalar Mintlify CLI
npm i -g mintlify

# Ejecutar documentación
mintlify dev
```

> [!IMPORTANT]
> **Omni-Sincronización**: En Camarai, cualquier cambio en cualquier dispositivo (POS, PDA, KDS o Dashboard) se refleja instantáneamente en el resto del ecosistema. La documentación debe respetar este principio de "Verdad Única".
