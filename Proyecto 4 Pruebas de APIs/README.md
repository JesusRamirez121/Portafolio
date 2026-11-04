# Proyecto 4: Pruebas de APIs (Urban Grocers)

Pruebas de API sobre tres áreas de Urban Grocers, verificando las actualizaciones del lanzamiento en Grocery Bundles, Delivery Services y Shopping Cart. Los casos se diseñaron a partir de la documentación Swagger y se ejecutaron en Postman contra el servidor del proyecto. Se aplicaron partición de equivalencia, análisis de valores límite y casos de autenticación según cada área.

**Servidor:** https://urban-grocers-es.up.railway.app
**Swagger:** https://urban-grocers-es.up.railway.app/api/swagger/#/

## Resultados

| Área | Casos | Aprobados | Fallidos | Defectos |
|---|---|---|---|---|
| UG-1: Grocery Bundles | 9 | 7 | 2 | 2 |
| UG-2: Delivery Services | 9 | 4 | 5 | 4 |
| UG-3: Shopping Cart (opcional) | 8 | 8 | 0 | 0 |
| **Total** | **26** | **19** | **7** | **6** |

## Defectos reportados

| ID | Título | Severidad | Caso |
|---|---|---|---|
| UG-1-BUG-01 | `POST /api/v1/grocery-bundles/{id}/products` acepta un `productId` que no existe y responde 200 OK | Media | UG-1-TC-06 |
| UG-1-BUG-02 | `POST /api/v1/grocery-bundles/{id}/products` con `productsList` que no es un arreglo responde 500 | Media | UG-1-TC-08 |
| UG-2-BUG-01 | `POST /speedy/v1/calculate` devuelve `isItPossibleToDeliver = true` con `deliveryTime` de 6 y 22 (fuera del horario 07 a 21) | Alta | UG-2-TC-03, UG-2-TC-05 |
| UG-2-BUG-02 | `POST /speedy/v1/calculate` responde 200 OK cuando falta `deliveryTime` | Alta | UG-2-TC-06 |
| UG-2-BUG-03 | `POST /speedy/v1/calculate` responde 200 OK cuando `deliveryTime` es un string | Media | UG-2-TC-07 |
| UG-2-BUG-04 | `POST /speedy/v1/calculate` responde 200 OK cuando `products` no es un arreglo | Media | UG-2-TC-08 |

Cada reporte incluye pasos para reproducir, resultado esperado, resultado actual y evidencia. La evidencia son registros del servidor (logs de la petición y la respuesta), que están en la columna "Evidencia" de la hoja de reportes.

## Hallazgos principales

- **Validación de entrada:** en Delivery Services, el servicio acepta solicitudes sin `deliveryTime`, con tipo incorrecto o con `products` mal formado, y responde 200 OK. Los errores de validación deberían responder 400 Bad Request.
- **Horario de servicio:** Speedy atiende de 07 a 21 hrs, pero el servicio marca como entregables horarios fuera de ese rango.
- **Paquetes de productos:** el servicio no valida que el producto exista y, con una estructura inválida, responde con error 500.

## Estructura

```
Proyecto 4 Pruebas de APIs/
├── README.md
└── docs/
    └── Proyecto 4 Pruebas de APIs.xlsx
```

Hojas del Excel: "Guía del proyecto", "UG-1 Casos de prueba", "UG-1 Reportes de errores", "UG-2 Casos de prueba", "UG-2 Reportes de errores", "UG-3 Casos de prueba", "UG-3 Reportes de errores" y "Listas".

## Herramientas

- Postman (ejecución de las solicitudes)
- Swagger (documentación de la API)
- Excel (casos de prueba y reportes de errores)
