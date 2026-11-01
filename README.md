# Maleños VIP – Prototipos de la tesis

Aplicaciones web de las propuestas de mejora para la ruta Lima – Mala (R-01). Cada una es un solo archivo HTML que funciona en cualquier navegador, sin instalar nada.

| Aplicación | Archivo | Enlace con GitHub Pages |
|---|---|---|
| Monitoreo de neumáticos (PdM/CBM) | `index.html` | `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/` |
| Punto de reorden de repuestos | `punto_reorden.html` | `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/punto_reorden.html` |

## Monitoreo de neumáticos (PdM/CBM)

Muestra el estado de las cuatro llantas de cada uno de los 55 buses a partir de los sensores de presión y temperatura.

- **Flota:** una tarjeta por bus con sus cuatro neumáticos y el color del semáforo.
- **Alertas:** responsable y acción según el momento de la operación; registro de atención y cierre con su causa.
- **Mapa de ruta:** posición de cada bus en la ruta y estado de sus llantas.
- **Indicadores:** disponibilidad de datos, tiempo de aviso, amarillos atendidos a tiempo y falsas alarmas.
- **Configuración:** presión recomendada por eje, límites del semáforo y fuente de datos.

Semáforo, sobre la presión corregida a frío como porcentaje de la recomendada del eje:

| Estado | Condición |
|---|---|
| Verde | 90 % o más, sin caída anormal |
| Amarillo | 80 – 90 %, o caída de más de 5 % frente al arranque en frío de ayer (fuga lenta) |
| Rojo | Menos de 80 %, o pérdida rápida de presión |
| Sin datos | El sensor no transmite durante más de 5 min con el motor encendido |

Corrección a frío: `P_frío = (P_medida + 1,013) × (T_ref + 273,15) ÷ (T_medida + 273,15) − 1,013` [bar; °C].

Por defecto funciona en modo demostración, con lecturas simuladas. En **Configuración → Fuente de datos → Datos reales** se conecta a un servicio web o se carga un archivo JSON de lecturas.

## Punto de reorden de repuestos

Gestión del inventario de repuestos críticos: inventario, punto de reorden, lote económico (EOQ), clasificación ABC y Kraljic, kárdex y pedidos, indicadores y proceso RPA.

## Datos

Lo que se registra en cada aplicación (atenciones, cierres, movimientos) se guarda solo en el navegador de quien la usa; no se envía a GitHub ni a ningún servidor.
