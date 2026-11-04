Resumen de ejecución: Pruebas de regresión - Flujo de solicitud de viaje - Release 1.4

- Casos ejecutados: 11 (Aprobados: 9 | Fallidos: 2 | Omitidos: 0)
- Defectos confirmados:
  - BUG-01 (Mayor): error 503 Service Unavailable en /api/v1/tariffs/price para la tarifa "shine" al calcular la ruta. Evidencia: https://drive.google.com/file/d/1z55gV8qJtmR65SIiIryQ-4ToLeXh_DyF/view?usp=sharing
  - BUG-02 (Mayor): la pantalla de espera del vehículo no se puede cerrar ni cancelar tras solicitar el viaje. Evidencia: https://drive.google.com/file/d/1uuWf3_GHn5ryLsnL0SpUryuB9RBSCk3J/view?usp=sharing
- Hoja de ejecución: [enlace al documento de Google Sheets]
- Recomendación: no liberar la Release 1.4 hasta corregir BUG-01 y BUG-02, ya que ambos afectan el flujo core de solicitud de viaje.
