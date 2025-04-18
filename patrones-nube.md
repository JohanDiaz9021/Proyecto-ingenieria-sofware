# Patrones de Diseño de Nube 15%

## Objetivo

Aplicar patrones arquitectonicos modernos que mejoran escalabilidad, trazabilidad y mantenibilidad en entornos distribuidos como microservicios

---

## 1. Sidecar Pattern – Logging y Trazabilidad

**Aplicado en:** `log-message-processor/main.py`

**Descripcion tecnica:**  
Este microservicio en Python escucha mensajes desde Redis enviados por los demas servicios y los reenvia a Zipkin para trazabilidad. Se ejecuta como un componente independiente, sin afectar el codigo del negocio, cumpliendo el rol de **Sidecar**.

**Ventajas:**
- Separa responsabilidades (negocio vs monitoreo)
- Escalable y reutilizable
- Centraliza el logging distribuido

---

## 2. Gateway Routing Pattern – Redireccion de peticiones

**Aplicado en:** `frontend/config/index.js`

**Descripcion tecnica:**  
Se configuro el proxy de Webpack (`proxyTable`) para que el frontend redirija automaticamente las rutas:

- `/login` → `auth-api`
- `/todos` → `todos-api`

Esto unifica el acceso y evita exponer directamente las IPs o puertos de los microservicios, comportandose como un **gateway de rutas**.

**Ventajas:**
- Abstraccion entre frontend y backend
- Facilidad para cambiar rutas sin modificar la UI
- Mejora la seguridad y organizacion de llamadas

---

## Resultado

El proyecto implementa correctamente **dos patrones de arquitectura en la nube**:

- `Sidecar Pattern` con `log-message-processor`
- `Gateway Routing Pattern` con `frontend`

Esto mejora significativamente la estructura y mantenibilidad del sistema
