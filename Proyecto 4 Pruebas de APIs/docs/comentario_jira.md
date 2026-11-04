Resumen de ejecución: Pruebas de APIs de Urban Grocers (Release) - UG-1, UG-2 y UG-3

- Casos ejecutados: 26 (UG-1: 9 | UG-2: 9 | UG-3: 8)
- Resultados: 19 aprobados, 7 fallidos, 0 omitidos
- Defectos confirmados (6):
  - UG-1-BUG-01 (Media): POST /grocery-bundles/{id}/products acepta un productId inexistente y responde 200 OK.
  - UG-1-BUG-02 (Media): POST /grocery-bundles/{id}/products con productsList que no es un arreglo responde 500.
  - UG-2-BUG-01 (Alta): POST /speedy/v1/calculate devuelve isItPossibleToDeliver = true con deliveryTime 6 y 22, fuera del horario de 07 a 21 hrs.
  - UG-2-BUG-02 (Alta): POST /speedy/v1/calculate responde 200 OK cuando falta deliveryTime.
  - UG-2-BUG-03 (Media): POST /speedy/v1/calculate responde 200 OK cuando deliveryTime es un string.
  - UG-2-BUG-04 (Media): POST /speedy/v1/calculate responde 200 OK cuando products no es un arreglo.
- Evidencia: registros del servidor en la columna "Evidencia" de la hoja de reportes de cada área.
- Recomendación: no liberar Delivery Services hasta corregir UG-2-BUG-01 y UG-2-BUG-02 (severidad Alta). Los defectos de validación de UG-1 y UG-2 deben corregirse antes del cierre del release.
