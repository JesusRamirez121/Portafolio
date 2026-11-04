# Proyecto 2: Checklist de interfaz (Compartir automóvil)

Validación de extremo a extremo de la funcionalidad **Compartir un automóvil** de Urban Routes, a partir del ticket de Jira *Desarrollar la interfaz para la funcionalidad de compartir un automóvil* (TMTS-S-4). Este proyecto cubre los **criterios de aceptación 1 y 2**. El criterio 3 (método de pago) se trabajará en el sprint 3.

## Alcance

- Visibilidad del botón "Reservar" y del formulario del pedido en el modo Personal
- Formulario del pedido: tarifa, licencia de conducir, método de pago y requisitos del pedido
- Información de cada tarjeta: nombre del modo, ícono, precio y duración
- Descripción de cada tarifa (Casual, Camping y De lujo) y símbolo de peatón
- Comparación contra los diseños de Figma

**Entornos:** Google Chrome 800×600 y Firefox 1920×1080.

## Resultados del checklist

Se ejecutaron 13 verificaciones en ambos entornos.

| Entorno | Aprobados | Fallidos |
|---|---|---|
| Chrome 800×600 | 9 | 4 |
| Firefox 1920×1080 | 9 | 4 |

Los 4 ítems fallidos son los mismos en ambos entornos, así que el comportamiento no depende del tamaño de pantalla ni del navegador.

## Defectos reportados

| ID | Título | Ítem del checklist | Prioridad | Evidencia |
|---|---|---|---|---|
| B01-SP2 | Ausencia del texto de precio para "Compartir un automóvil" en el modo Flash | 3 | Media | [Carpeta de evidencias](https://drive.google.com/drive/folders/1lMJvcO00h1Q7zy76yoKRYE_m3FCiXv5L?usp=sharing) |
| B02-SP2 | Ausencia del texto de duración para "Compartir un automóvil" en el modo Flash | 4 | Media | [Carpeta de evidencias](https://drive.google.com/drive/folders/1lMJvcO00h1Q7zy76yoKRYE_m3FCiXv5L?usp=sharing) |
| B03-SP2 | Texto incorrecto en la descripción de la tarifa "De lujo" (Porsche 911) | 12 | Baja | [Carpeta de evidencias](https://drive.google.com/drive/folders/1TDY6P523xMNsE3ePDMyDIdXadgOLsawE?usp=sharing) |
| B04-SP2 | Texto incorrecto en la descripción de la tarifa "Camping" (Audi A3 Sedan) | 12 | Baja | [Carpeta de evidencias](https://drive.google.com/drive/folders/1TDY6P523xMNsE3ePDMyDIdXadgOLsawE?usp=sharing) |
| B05-SP2 | Ausencia del símbolo de peatón en la información de las tarifas | 13 | Baja | [Evidencia (archivo)](https://drive.google.com/file/d/1_nvL6-e_AkagAi0o6sInfJ9x1XIJ7owj/view?usp=drive_link) |

**Causa observable de B01 y B02:** en el modo Flash, la aplicación solo habilita el transporte "Taxi", así que la opción "Compartir un automóvil" no aparece. El diseño de Figma sí la muestra con precio y duración.

## Estructura

```
Proyecto 2 checklist de interfaz/
├── README.md
└── docs/
    └── Proyecto 2 checklist de interfaz.xlsx   # Hojas: "1. Checklist de la interfaz" y "2. Reporte de errores"
```

## Herramientas

- Google Chrome y Firefox (verificación en dos resoluciones)
- Figma (diseños de referencia)
- Microsoft Excel (checklist y reporte de errores)
