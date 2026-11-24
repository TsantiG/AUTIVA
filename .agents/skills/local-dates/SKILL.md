---
name: local-dates
description: Ejemplo opcional para proyectos JavaScript con fechas civiles locales; no aplicar a instantes UTC ni a cualquier proyecto por defecto.
metadata:
  opencode/autoinvoke: false
---
# Ejemplo opcional — Fechas civiles locales en JavaScript

Muestra desactivada para descubrimiento automático. Cargar explícitamente con `@local-dates` solo cuando el proyecto haya elegido fechas civiles locales. Para activarla de forma habitual, adaptar sus reglas y quitar `opencode/autoinvoke: false` con aprobación.
No aplica a marcas de tiempo: esos instantes normalmente necesitan UTC y una zona de presentación explícita. No asumir que el servidor comparte la zona horaria del usuario.

## Reglas
- Las fechas se guardan como texto "AAAA-MM-DD" en la zona horaria local del usuario.
- Para obtener el día de hoy, construye el texto con getFullYear(), getMonth() + 1 y
getDate(), rellenando con ceros.
- Para convertir "AAAA-MM-DD" en fecha, usa new Date(año, mes - 1, día). Nunca new
Date("AAAA-MM-DD"): se interpreta en UTC.
- Nunca uses toISOString() para obtener el día: devuelve la fecha en UTC.
- Para sumar o restar días, usa setDate(getDate() ± n), nunca milisegundos (24 h no
siempre es un día por los cambios de hora).
- Reutiliza las funciones de fechas existentes; valida fechas inexistentes antes de aceptar la normalización del constructor de JavaScript.
## Checklist de revisión
- [ ] ¿Algún toISOString() o new Date("AAAA-MM-DD")?
- [ ] ¿Algún cálculo con 86400000 milisegundos?
- [ ] ¿Qué pasa con una sesión registrada a las 00:30?
- [ ] ¿Qué pasa el día del cambio de hora (último domingo de marzo y de octubre)?
- [ ] ¿La política sobre fechas futuras está definida por el proyecto?
## Al terminar
Indica qué puntos del checklist has comprobado y cómo.

Estas son reglas de ejemplo, no decisiones de negocio para otros proyectos.
