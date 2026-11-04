# Prueba técnica: Automatización QA

Tres ejercicios de automatización que cubren pruebas de API, pruebas end-to-end de interfaz y pruebas de rendimiento.

## Ejercicios

| # | Ejercicio | Herramientas | Qué valida | Carpeta |
|---|---|---|---|---|
| 1 | API REST: gestión de usuarios (PetStore Swagger) | Karate DSL, JUnit 5, Gradle, patrón Screenplay | Crear, buscar, actualizar y eliminar un usuario, y verificar el 404 posterior (TC-001 a TC-006) | [ejercicio-API](ejercicio-API/) |
| 2 | E2E: flujo de compra como invitado (OpenCart) | Serenity BDD 4.2.1, Cucumber, Selenium, WebDriverManager, Java 21, Gradle | Búsqueda de productos, checkout como invitado y confirmación del pedido | [ejercicio-e2e](ejercicio-e2e/) |
| 3 | Performance: carga sobre el login (FakeStore API) | Apache JMeter 5.6.3 | 30 usuarios concurrentes y 20 TPS durante 120 s, con validación de tiempos de respuesta y tasa de error | [ejercicio-performance](ejercicio-performance/) |

Cada carpeta incluye sus instrucciones de ejecución (`readme`) y sus hallazgos (`conclusiones`).

## Qué no está incluido

Para mantener el repositorio ligero, no se incluyen las carpetas generadas por las herramientas (`build/`, `target/`), las configuraciones de IntelliJ (`.idea/`), la instalación de JMeter ni los conectores de MySQL. Para ejecutar el ejercicio 3, instala Apache JMeter 5.6.3.
