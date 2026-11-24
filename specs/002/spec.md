# Spec 002 — Adaptación de agentes y documentación de AUTIVA

Estado: COMPLETADA; alcance documental validado, sin pruebas de la app.
Número: 002, indicado por el desarrollador en esta conversación.

## Objetivo y alcance
- Adecuar las instrucciones de agentes al desarrollo Android de AUTIVA y publicar un README básico y verificable.
- Incluido: documentación de agentes y producto, reglas Android, consulta limitada de configuración y comprobaciones documentales.
- Excluido: lectura de código de la app sin nuevo permiso, modificación de cualquier archivo dentro de `AUTIVA/`, compilaciones, instalaciones, migraciones, publicación y activación de integraciones.

## Requisitos y decisiones
- Reemplazar instrucciones específicas de .NET por límites Android; mantener el flujo de planificación, QA, aprobación y checkpoint para código.
- Autorizar consulta de configuración Android estrictamente necesaria. Pedir permiso antes de leer código o ampliar la revisión; un acceso más amplio solo existe si el desarrollador lo concede expresamente.
- Organizar `AUTIVA.txt` como contexto de producto con hechos, propuestas y consejos pendientes/completados con evidencia.
- Crear `README.md` sin presentar objetivos como funciones implementadas ni inventar licencia, instalación o pruebas exitosas.
- Conservar los modelos configurados y no activar MCP, plugins ni dependencias. `opencode.jsonc` solo se corregirá si la documentación oficial V2 demuestra una necesidad dentro del alcance.
- Incorporar reglas constitucionales de compatibilidad, permisos, privacidad/firma, datos persistentes y validación Android, aprobadas junto al plan final.
- Conservar `specs/001/spec.md` como plantilla; esta spec no activa futuras tareas de desarrollo.
- Reglas aplicables: SEC-01 a SEC-05, ERR-01, ERR-02 y QUA-01; nuevas AND-01 a AND-05.

## Cambios previstos
| Archivo | Acción | Cambio y motivo |
| --- | --- | --- |
| `specs/002/spec.md` | crear | Documentar una sola vez el plan aprobado y sus resultados. |
| `README.md` | crear | Presentación pública del producto y estado técnico verificado. |
| `AGENTS.md` | modificar | Contexto y procedimiento de trabajo para Android. |
| `docs/constitution.md` | modificar | Añadir normas Android concretas, conservando las reglas generales. |
| `AUTIVA.txt` | modificar | Ordenar contexto, decisiones pendientes y consejos generales. |
| `MEMORY.md` | modificar | Sustituir memoria de plantilla por estado y decisiones reales. |
| `consejo.txt` | modificar | Guía operativa coherente, sin tarifas obsoletas ni comandos no verificados. |
| `opencode.jsonc` | condicional | Corregir solo si resulta necesario tras contraste oficial V2; sin cambiar modelos ni activar integraciones. |

## Riesgos y casos límite
- Android 6.0/API 23 es el objetivo declarado previo, pero `AUTIVA/app/build.gradle.kts` configura `minSdk = 24` (Android 7.0). Documentar ambos y no resolver la discrepancia ni cambiar Gradle sin decisión del desarrollador.
- Las versiones declaradas en configuración no prueban que la app compile ni que las herramientas estén disponibles.
- No leer `local.properties`, claves de firma, credenciales o código de la app; los filtros de búsqueda no son controles de acceso.
- No elegir arquitectura, almacenamiento, servicios, licencia ni funcionalidades adicionales por iniciativa del agente.

## Criterios de aceptación y validación
- No quedan instrucciones específicas de .NET en las guías operativas actualizadas.
- README y contexto distinguen configuración comprobada, objetivos e ideas pendientes.
- Las rutas enlazadas de la documentación existen; los comandos de compilación/prueba no se dan por comprobados sin ejecución autorizada.
- Se mantienen intactos los modelos de OpenCode, las integraciones inactivas y la plantilla 001.
- La memoria no supera aproximadamente 50 líneas y conserva pendientes relevantes.
- Validación mediante revisión y comprobaciones de texto/configuración, sin ejecutar Gradle ni cargar código de la app.

## Aprobación y ejecución
- QA previo: realizado con Sol en la misma conversación; QA-01 a QA-04 corregidos en el plan. Estado: LISTO PARA APROBACIÓN.
- Aprobación: el desarrollador respondió «si» a la aprobación explícita de la versión final y sus reglas constitucionales, después de indicar el número 002.
- Checkpoint: no aplica; tarea documental, sin cambios de código ni configuración de la aplicación.
- Validaciones ejecutadas: comprobación PowerShell con resultado satisfactorio de ausencia de instrucciones heredadas en las seis guías actualizadas; seis enlaces locales del README existentes; memoria de 36 líneas; reglas AND-01 a AND-05 presentes; estado de plantilla 001 conservado; discrepancia API 23/API 24 documentada en los seis documentos principales.
- Configuración: JSONC analizado tras retirar líneas de comentarios; modelos y agente predeterminado conservados, sin MCP ni plugins activos en ese archivo. Contraste con https://opencode.ai/v2/docs/config y https://opencode.ai/v2/docs/agents; no fue necesario modificar `opencode.jsonc`.
- Limitaciones: validación documental, no validación completa contra esquema ni prueba en una sesión nueva. No se ejecutó Gradle, no se leyó código de la app, no se comprobaron conexiones/modelos ni se modificaron archivos dentro de `AUTIVA/`. No se inicializó Git ni se publicó en GitHub.
- Pendiente ajeno al alcance: el desarrollador debe decidir entre el objetivo Android 6.0/API 23 y el mínimo actual API 24 antes de cambiar o anunciar compatibilidad.
