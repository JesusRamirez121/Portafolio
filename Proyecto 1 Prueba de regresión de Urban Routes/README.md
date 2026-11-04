# Urban Routes: Pruebas de regresión

Pruebas de regresión manuales sobre la aplicación web **Urban Routes**, un servicio de solicitud de taxi. Se cubrieron la definición de la ruta, la selección de tarifa, el flujo de reserva y la pantalla de espera del vehículo.

## Alcance

- Ingreso de direcciones en los campos "Desde" y "Hasta"
- Cálculo de ruta y respuestas del endpoint `/api/v1/tariffs/price`
- Modos de transporte: Óptimo, Flash y Personal
- Flujo de reserva con verificación por código SMS
- Campo "Mensaje para el conductor"
- Pantalla de espera del vehículo
- Validación de direcciones inválidas y revisión de errores en consola

## Resultados

| Métrica | Valor |
|---|---|
| Casos de prueba ejecutados | 11 |
| Aprobados | 9 |
| Fallidos | 2 |
| Errores reportados | 2 (ambos con severidad Mayor) |

## Contexto del ticket

Ticket de Jira TMTS-S-4, *Pruebas de regresión - Flujo de solicitud de viaje - Release 1.4*. Antes del lanzamiento había que confirmar que el flujo core de solicitud de viaje no se vio afectado por cambios recientes.

**Criterios de aceptación cubiertos:**
- Los campos Desde y Hasta aceptan direcciones válidas.
- Las direcciones ingresadas se muestran correctamente en el mapa.
- Cada modo de transporte (Óptimo, Flash y Personal) muestra tiempo y costo.
- Al completar ambos campos, la aplicación muestra los modos disponibles.
- La solicitud de cálculo de ruta devuelve HTTP 200 OK desde el servidor.
- Al seleccionar un tipo de transporte y solicitar el viaje, la aplicación avanza al siguiente paso.
- La pantalla de espera del vehículo puede cerrarse sin bloquear la interfaz.

**Definition of Done:**
- [x] Todos los casos asignados se ejecutaron (11 de 11).
- [x] Resultados registrados en la hoja de ejecución.
- [x] Evidencia adjunta para cada defecto confirmado.
- [ ] Resumen final agregado como comentario en Jira (borrador en `docs/comentario_jira.md`).

## Errores encontrados

| ID | Título | Caso | Severidad |
|---|---|---|---|
| BUG-01 | Error 503 Service Unavailable en `/api/v1/tariffs/price` para la tarifa "shine" | CASO-3 | Mayor |
| BUG-02 | La pantalla de espera del vehículo no se puede cerrar ni cancelar | CASO-10 | Mayor |

**BUG-01:** al ingresar las direcciones, la solicitud de la tarifa "shine" responde 503, aunque se esperaba 200 OK. Evidencia: [captura de DevTools](https://drive.google.com/file/d/1z55gV8qJtmR65SIiIryQ-4ToLeXh_DyF/view?usp=sharing).

**BUG-02:** después de solicitar el taxi y escribir un mensaje al conductor, el botón de cerrar o cancelar la espera no responde. Evidencia: [video](https://drive.google.com/file/d/1uuWf3_GHn5ryLsnL0SpUryuB9RBSCk3J/view?usp=sharing).

## Estructura

```
urban-routes-regresion/
├── README.md
└── docs/
    └── casos_y_errores_urban_routes.xlsx   # Hojas: "Casos de prueba" e "Informes de errores"
```

## Herramientas

- Microsoft Excel (casos de prueba e informes de errores)
- Navegador Chrome con DevTools (pestañas Network y Console)
