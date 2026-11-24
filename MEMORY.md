# MEMORY.md — AUTIVA
Máximo aproximado de 50 líneas; sin secretos. Estado documental: 24 de noviembre de 2026.

## Estado actual
- AUTIVA es una app Android de productividad: proyectos, estudio, tareas y hábitos son áreas previstas, no funcionalidades auditadas.
- Proyecto Gradle en `AUTIVA/`, módulo `:app`; no se leyó código de la app ni se modificó ningún archivo dentro de esa carpeta.
- Spec 002 aprobada: adaptación documental de agentes y README; no autoriza desarrollo funcional posterior.
- `specs/001/spec.md` sigue siendo plantilla, no spec activa.
- Reglas permanentes en `docs/constitution.md`; procedimiento en `AGENTS.md`; contexto y consejos en `AUTIVA.txt`.
- README público básico creado, sin instalación, licencia ni funciones implementadas inventadas.

## Decisiones y motivos
- Acceso vigente: configuración Android pertinente; pedir permiso antes de leer código/recursos de implementación o ampliar análisis.
- Mantener el flujo plan -> QA previo -> decisiones/aprobación -> spec numerada -> Build -> validación.
- QA con Sol en la misma sesión si ya está seleccionado; no requiere lanzar `/qa-plan` de nuevo ni otro agente.
- Mantener modelos configurados: Luna #medium en Plan; Sol #medium en Build y QA. No activar MCP ni plugins.
- Normas Android AND-01 a AND-05 aprobadas: compatibilidad, permisos mínimos, privacidad/firma, persistencia y validación.
- Actualizar consejos al cerrar cambios autorizados; completados solo con evidencia, no durante análisis.
- No se inicializó Git ni se publicaron cambios; el entorno informó que la raíz no es un repositorio Git.
- Antes de cambiar código: pedir checkpoint Git o alternativa/excepción explícita; no aplica a la tarea documental 002.

## Datos técnicos observados, no probados
- `minSdk = 24` (Android 7.0), `targetSdk = 37`, `compileSdk = 37`; Compose habilitado, Material 3 declarado.
- Catálogo: AGP 9.5.2, plugin Compose Kotlin 2.2.10, BOM Compose 2026.02.01; Wrapper Gradle 9.6.0.
- Compatibilidad fuente/destino Java 11 no determina el JDK necesario para ejecutar Gradle/AGP.
- Objetivo previo Android 6.0/API 23 contradice el mínimo actual: pendiente de decisión, sin cambios de SDK autorizados.

## Validación y límites
- Se contrastaron configuración y agentes de OpenCode con documentación oficial V2; opencode.jsonc se conserva sin cambios.
- No se ejecutó Gradle, no se probó la app ni se verificaron modelos/conexiones en una sesión nueva.
- Spec 002 completada: comprobaciones documentales satisfactorias (referencias heredadas, 6 enlaces README, reglas Android, memoria y plantilla 001); JSONC analizable con modelos conservados e integraciones locales inactivas. Sin validación completa de esquema.

## Próximos pasos
- Resolver mínimo Android y definir un MVP antes de implementar funcionalidades.
- Verificar rutas de fuentes/pruebas con permiso; después comprobar entorno, comandos y compatibilidad real.
- Acordar persistencia/privacidad, identidad visual, distribución y licencia cuando corresponda; no asumir nube ni cuentas.
