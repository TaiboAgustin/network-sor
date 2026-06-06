# TP Final Redes — Mundial FIFA 2026

Trabajo Práctico Final de Redes. Diseño e implementación en Cisco Packet Tracer de la red de comunicaciones para el Mundial FIFA México/EE.UU./Canadá 2026.

## Resumen

La red conecta 6 estadios sede del mundial, distribuidos en 3 regiones (Canadá, EE.UU., México), con 4 áreas funcionales por estadio (Servidores, Administración, Deportistas, Público). Vancouver además aloja los servidores centrales (Web/DNS y Datos).

## Diseño

- **Direccionamiento:** `10.0.0.0/8` (privado clase A).
  - LANs: máscara `/14` (uniforme, prioriza simplicidad).
  - WANs: máscara `/30` (punto a punto, óptimo).
- **Routers:** Cisco ISR 4321 con módulo NIM-ES2-4 (6 en total).
- **Switches:** Cisco 2960 (24 en total, 4 por estadio).
- **VLANs:** 10 Servidores / 20 Administración / 30 Deportistas / 40 Público.
- **Enrutamiento:** RIP v2 con `no auto-summary`.

## Topología

```
                 Toronto
                    ↑
                Vancouver ←—— servidores centrales
                    ↓
                New York ——————→ San Francisco
                    ↓
                Guadalajara ——————→ Monterrey
```

## Estado actual

- ✅ Guadalajara y Monterrey configurados al 100% (router + switches + PCs).
- ✅ Conectividad end-to-end verificada entre ambos.
- ⏳ Vancouver, Toronto, New York, San Francisco: pendientes.
- ⏳ Servidor Web/DNS en Vancouver: pendiente.

## Archivos

- `network-mundial-2026.pkt` — Implementación en Cisco Packet Tracer.
- `Tabla de direccionamiento.xlsx` — Subredes LAN con primer y último host.

## Software requerido

- Cisco Packet Tracer (versión de los labos para asegurar compatibilidad en el coloquio).
