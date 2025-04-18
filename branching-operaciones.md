# Estrategia de Branching para Operaciones (2.5%)

## Objetivo

Separar los cambios de infraestructura, despliegue y configuracion del codigo de negocio, para mantener entornos controlados, organizados y seguros en el trabajo colaborativo de un equipo agil

---

## Ramas creadas para operaciones

| Rama              | Proposito                                                                 |
|-------------------|--------------------------------------------------------------------------|
| `infra/main`      | Configuracion estable para entornos de produccion (docker-compose, env) |
| `infra/develop`   | Pruebas de nuevas configuraciones e infraestructura                     |
| `infra/env-local` | Variables de entorno y ajustes especificos para el entorno local        |
| `infra/ci-cd`     | Scripts y configuracion de integracion y despliegue continuo            |

---

## Flujo aplicado

1. Se parte de la rama `infra/main`
2. Se crean ramas `infra/develop`, `infra/env-local`, `infra/ci-cd` para trabajar aspectos separados de la infraestructura
3. Una vez validadas, estas ramas pueden integrarse nuevamente a `infra/main`
4. Esto evita que operaciones afecte accidentalmente la logica de negocio y permite mantener ambientes limpios y bien versionados

---

## Relacion con el proyecto actual

El proyecto contiene multiples microservicios (`auth-api`, `users-api`, `frontend`, etc.), que requieren:

- `docker-compose.yml` para orquestacion
- `.env` para variables sensibles
- Redis y Zipkin como infraestructura comun
- Scripts posibles de automatizacion o despliegue

Estas ramas permiten gestionar cada parte de esa infraestructura de forma modular y trazable

---

## Resultado final en el repositorio

```bash
infra/main         # Infraestructura estable
infra/develop      # Config de pruebas
infra/env-local    # Variables y pruebas locales
infra/ci-cd        # Automatización y despliegue
