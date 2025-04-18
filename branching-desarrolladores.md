# Estrategia de Branching para Desarrolladores 25%

## Objetivo

Aplicar una estrategia de ramas que permita a los desarrolladores trabajar de forma paralela, ordenada y colaborativa, siguiendo una metodologia agil, en una arquitectura en microservicios

---

## Estructura de ramas utilizada

| Rama            | Proposito                                                                |
|-----------------|-------------------------------------------------------------------------|
| `main`          | Rama principal. Contiene el codigo estable, listo para ser desplegado  |
| `develop`       | Rama base de desarrollo. Aqui se integran todas las funcionalidades     |
| `feature/*`     | Ramas para nuevas funcionalidades. Se crean desde `develop`            |

---

## Ramas implementadas

Se implementaron las siguientes ramas como parte del flujo agil:

- `develop`: rama base de integracion
- `feature/auth-api`: funcionalidad del microservicio de autenticacion
- `main`: version estable del proyecto

---

## Flujo de trabajo seguido

1. Se creo la rama `develop` desde `main`
2. Se creo la rama `feature/auth-api` desde `develop`
3. Se realizo un commit con el codigo del microservicio `auth-api`
4. Se hizo push de `feature/auth-api` al repositorio remoto
5. Se hizo merge de `feature/auth-api` en `develop`
6. Se actualizo `develop` en el repositorio remoto (`push`)

---

## Observaciones

- Se simulo una entrega agil tal como se haria en un equipo profesional
- Esta implementacion demuestra como aplicar una estrategia de branching real en un entorno controlado
- El resto de microservicios (`frontend`, `users-api`, `todos-api`, etc.) pueden seguir este mismo flujo, creando ramas `feature/*` individuales por cada uno

---

## Resultado final

```bash
* main
* develop
* feature/auth-api
