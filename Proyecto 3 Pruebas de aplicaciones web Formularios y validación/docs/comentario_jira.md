Resumen de ejecución: Pruebas del formulario de pago (CA-3) - TMTS-S-4

- Casos ejecutados: 18 (Aprobados: 9 | Fallidos: 6 | Bloqueados: 3)
- Defectos confirmados:
  - SP3-B1 (Media): el campo "Número de tarjeta" permite más de 12 dígitos. Evidencia: https://drive.google.com/file/d/1nYQeOJCYIar8HRC5-EM6cHhucjTzSe8l/view?usp=sharing
  - SP3-B2 (Alta): el campo "Número de tarjeta" acepta cualquier carácter. Evidencia: https://drive.google.com/file/d/1gZ5HebViTyQZd13PeZE1qRss9-hnQywE/view?usp=drive_link
  - SP3-B3 (Alta): el botón "Agregar tarjeta" se activa con 11 dígitos. Evidencia: https://drive.google.com/file/d/1d2qSkL2E_7KN3pBKzlylq-Wii_310dzz/view?usp=drive_link
  - SP3-B4 (Alta): el botón "Agregar tarjeta" se activa con un código de 1 dígito. Evidencia: https://drive.google.com/file/d/1ADZ_kUcudgWbUkVe8tNKMLiF4k3YUbBq/view?usp=drive_link
  - SP3-B5 (Alta): el campo "Código" permite más de 2 dígitos. Evidencia: https://drive.google.com/file/d/1pt9CgJdDjmVuUjAr7_N_RY_i-x-up5wS/view?usp=drive_link
- Pendiente: 3 casos marcados como Bloqueados (7.2, 8.1 y 9.1) muestran comportamientos que parecen defectos adicionales; aún no tienen reporte.
- Recomendación: no liberar el formulario de método de pago hasta corregir SP3-B1 a SP3-B5 y revisar los casos bloqueados.
