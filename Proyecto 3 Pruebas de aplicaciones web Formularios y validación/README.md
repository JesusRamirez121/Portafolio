# Proyecto 3: Pruebas de formulario de pago (Urban Routes)

Diseño y ejecución de pruebas sobre el formulario **Agregar tarjeta** (método de pago) de Urban Routes, a partir del criterio de aceptación 3 del ticket de Jira TMTS-S-4. Se aplicaron partición en clases de equivalencia y análisis de valores límite, y se reportaron los defectos encontrados.

## Reglas de validación (CA-3)

- **Número de tarjeta:** formato `nnnn nnnn nnnn`, solo números, 12 dígitos. Cada bloque va de 0000 a 9999. Los espacios se agregan automáticamente. Con menos de 12 dígitos, el botón "Agregar tarjeta" permanece inactivo.
- **Código:** formato `nn`, solo números, 2 dígitos. El rango va de 01 a 99. Con menos de 2 dígitos, el botón permanece inactivo.

## Escenarios de validación

Se diseñaron 9 escenarios que combinan clases de equivalencia (válidas e inválidas) con valores límite para ambos campos. Cada escenario se marcó como positivo o negativo, y se eliminaron los valores de entrada repetidos.

## Casos de prueba

Se escribieron 18 casos de prueba con precondiciones, pasos y resultados esperados.

| Estado | Casos |
|---|---|
| Aprobado | 9 |
| Fallido | 6 |
| Bloqueado | 3 |

## Defectos reportados

| ID | Título | Prioridad | Casos afectados | Evidencia |
|---|---|---|---|---|
| SP3-B1 | El campo "Número de tarjeta" permite más de 12 dígitos | Media | 3.1, 3.2 | [Evidencia](https://drive.google.com/file/d/1nYQeOJCYIar8HRC5-EM6cHhucjTzSe8l/view?usp=sharing) |
| SP3-B2 | El campo "Número de tarjeta" acepta cualquier carácter | Alta | 4.1 | [Evidencia](https://drive.google.com/file/d/1gZ5HebViTyQZd13PeZE1qRss9-hnQywE/view?usp=drive_link) |
| SP3-B3 | El botón "Agregar tarjeta" se activa con 11 dígitos | Alta | 2.3 | [Evidencia](https://drive.google.com/file/d/1d2qSkL2E_7KN3pBKzlylq-Wii_310dzz/view?usp=drive_link) |
| SP3-B4 | El botón "Agregar tarjeta" se activa con un código de 1 dígito | Alta | 6.2 | [Evidencia](https://drive.google.com/file/d/1ADZ_kUcudgWbUkVe8tNKMLiF4k3YUbBq/view?usp=drive_link) |
| SP3-B5 | El campo "Código" permite más de 2 dígitos | Alta | 7.1 | [Evidencia](https://drive.google.com/file/d/1pt9CgJdDjmVuUjAr7_N_RY_i-x-up5wS/view?usp=drive_link) |

## Estructura

```
Proyecto 3 Pruebas de aplicaciones web Formularios y validación/
├── README.md
└── docs/
    └── Proyecto 3 Pruebas de aplicaciones web Formularios y validación.xlsx
```

Hojas del Excel: "1. Escenarios de validación", "2. Casos de prueba" y "3. Reporte de errores".

## Herramientas

- Google Chrome (Urban Routes)
- Microsoft Excel (escenarios, casos y reporte de errores)
