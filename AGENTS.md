# AGENTS.md — AUTIVA

AUTIVA es una aplicación Android de productividad y organización personal en desarrollo. Busca reunir proyectos, estudio, tareas y hábitos para facilitar la planificación y el seguimiento del progreso. Estas áreas son objetivos del producto, no una certificación de funciones implementadas.

## Contexto del proyecto
- Público propuesto: personas con metas que desean mejorar su organización, incluidos estudiantes y profesionales; segmentación final pendiente.
- Contexto de producto: `AUTIVA.txt` distingue hechos, propuestas y consejos; `README.md` es la presentación pública. Ninguno sustituye la spec aprobada ni prueba implementación.
- Proyecto Android: `AUTIVA/`; módulo configurado `:app` en `AUTIVA/settings.gradle.kts`. Configuración del módulo en `AUTIVA/app/build.gradle.kts` y catálogo en `AUTIVA/gradle/libs.versions.toml`.
- Stack declarado: Kotlin, Jetpack Compose y Material 3. Al adaptar esta base se observaron AGP 9.5.2, plugin Compose Kotlin 2.2.10, BOM Compose 2026.02.01 y Gradle Wrapper 9.6.0. Revalidar antes de usarlos como requisitos; no se comprobó compilación ni disponibilidad de herramientas.
- Compatibilidad pendiente: el objetivo previo es Android 6.0/API 23, pero Gradle configura `minSdk = 24` (Android 7.0), `targetSdk = 37` y `compileSdk = 37`. No prometer soporte API 23 ni cambiar SDK hasta resolverlo con el desarrollador. Documentar la discrepancia no autoriza resolverla.
- Rutas reales de fuentes/pruebas y convenciones internas: pendientes de inspección autorizada. No asumir arquitectura, librerías de persistencia, navegación, inyección, backend ni sincronización.
- Comandos exactos de compilación, pruebas y análisis: pendientes de verificación; no inventarlos. Existe `AUTIVA/gradlew.bat`, pero no se ejecutó en esta tarea. No confundir compatibilidad Java declarada en Gradle con el JDK que necesitan Gradle y AGP.

## Contexto obligatorio
- Leer `docs/constitution.md` y `MEMORY.md` al comenzar; después, solo los archivos necesarios para la tarea.
- La constitución contiene las reglas permanentes. Este archivo define el procedimiento; la spec aprobada define el alcance de una tarea. Ante un conflicto entre documentos, detenerse y pedir una resolución, sin ignorar la constitución.
- Al adaptar la plantilla, comprobar qué normas específicas faltan (datos, permisos, despliegue, normativa, stack). Proponer adiciones concretas a la constitución con su motivo y pedir aprobación antes de aplicarlas; no preguntar por reglas ya resueltas.
- Antes de buscar recursivamente en una zona nueva, comprobar si hay instrucciones `AGENTS.md` anidadas aplicables. Acotar el descubrimiento y respetar las autorizaciones de acceso.

## Flujo de cambios
1. **Planificar sin escribir:** analizar el contexto pertinente y preparar en la conversación un plan con alcance y exclusiones, archivos y cambios, riesgos/dependencias, criterios de aceptación y validaciones. Solo preguntar antes si falta un dato indispensable para poder planear.
2. **QA previo con Sol:** con el plan terminado, cargar `spec-qa` antes de presentar las preguntas de decisión y antes de crear o modificar archivos. Si se planificó con Luna, ejecutar `/qa-plan` en la misma sesión para revisar con Sol. El plan en conversación basta: no crear una spec provisional.
3. **Resolver y aprobar:** presentar hallazgos y preguntas necesarias, incorporar las decisiones al plan en conversación y pedir aprobación explícita de la versión final. Si las decisiones cambian requisitos relevantes, revisar solo esa parte, no repetir todo el QA.
4. **Documentar una vez:** con aprobación y permisos de escritura, crear `specs/NNN/spec.md` con el número indicado por el desarrollador. Si falta, preguntarlo; no elegir uno automáticamente. Usar la estructura de `specs/001/spec.md`. No sobrescribir una spec real ni asumir que la de mayor número está activa. La aprobación del plan autoriza los archivos y dependencias que enumera, sin pedir permiso por cada archivo de nuevo.
5. **Checkpoint:** antes de tocar código, solicitar confirmación de que el estado anterior está guardado en Git. No ejecutar commits, inicializar repositorios ni publicar cambios automáticamente. Si no hay Git, pedir una alternativa o excepción explícita; una tarea solo documental no requiere checkpoint salvo indicación del desarrollador.
6. **Construir con Sol:** leer la spec activa indicada y comprobar brevemente que refleja el plan aprobado. Implementar dentro de su alcance. Un plan aprobado no elimina las restricciones del agente Plan: cambiar a Build para escribir.
7. **Validar y cerrar:** ejecutar las pruebas y comprobaciones aplicables; informar resultados reales, limitaciones y riesgos pendientes. No hacer otro QA completo por defecto: repetirlo solo en las partes con cambios de alcance o riesgos nuevos; en cambios de alto riesgo incluir una revisión dirigida del resultado.

No escribir archivos durante el análisis o el QA. No implementar antes de la autorización. Si aparece una decisión que amplía o contradice el plan aprobado, detener la parte afectada y pedir autorización. El desarrollador puede exceptuar explícitamente el procedimiento para una tarea concreta, sin desactivar las reglas de seguridad.

## Modelos y consumo
- Planificación: `openai/gpt-6-luna#medium` mediante `/feature`.
- QA previo: `openai/gpt-6.1-sol#medium` mediante `/qa-plan`.
- Implementación: `openai/gpt-6.1-sol#medium` en Build, consistente con `opencode.jsonc`; aumentar razonamiento solo si la complejidad o el riesgo lo justifican.
- Si ya se usa Sol, revisar el plan en la misma sesión, sin abrir otro agente solo para repetir contexto. Las skills no cambian el modelo por sí solas. Si el modelo requerido no está disponible, indicarlo y pedir una alternativa, sin afirmar un cambio no realizado.
- Mantener planes y QA concisos; compartir solo el contexto necesario y reutilizar decisiones documentadas. No prometer un ahorro fijo: el costo depende del modelo, tokens, caché y proveedor.
- La selección de agente no garantiza cambiar el modelo guardado en una sesión. Verificar la selección visible; no afirmar cambios de modelo no realizados. No delegar sin petición explícita o instrucciones aplicables que lo requieran.
- Al modificar configuración o instrucciones de OpenCode, cargar la skill `opencode` y contrastar el tema con su documentación oficial V2. No activar MCP, plugins o skills externas sin evaluación y autorización.

## Memoria
- `MEMORY.md` registra estado, decisiones con su motivo y próximos pasos; máximo aproximado de 50 líneas, sin secretos.
- Actualizarla al finalizar tareas con cambios persistentes o decisiones relevantes, cuando haya autorización de escritura. En análisis o consultas sin cambios, proponer la actualización si hace falta, sin escribirla automáticamente.
- Al copiar la plantilla a otro proyecto, reiniciar la memoria; no trasladar el historial de esta base ni los datos del ejemplo.
- Al cerrar cambios autorizados, revisar los consejos de `AUTIVA.txt`: mantener pendientes relevantes y marcar completados solo con evidencia. Durante análisis no modificar memoria ni consejos automáticamente.

## Acceso y límites Android
- Autorización vigente: consultar documentación y configuración Android estrictamente necesaria. Antes de leer código de la app, recursos de implementación o ampliar el análisis, pedir permiso. El desarrollador puede conceder acceso más amplio para una tarea; no inferir acceso libre de la aprobación de este documento.
- Excluir de búsquedas rutinarias `**/.gradle/**`, `**/.kotlin/**`, `**/.idea/**`, `**/build/**`, `**/captures/**` y `**/.cxx/**`. No inspeccionar binarios generados (`.apk`, `.aab`, `.dex`, `.class`) ni cachés salvo necesidad y autorización. Los filtros no son controles de acceso ni permiso para leer secretos.
- No excluir por extensión fuentes, pruebas, recursos, manifiestos, catálogos TOML, scripts Gradle o configuración del Wrapper cuando sean pertinentes y estén autorizados. No modificar archivos generados para corregir su fuente.
- No leer `local.properties`, archivos de entorno, propiedades globales de Gradle ni almacenes de claves (`.jks`, `.keystore`) sin necesidad y autorización específica. No publicar rutas locales, tokens ni credenciales de firma.
- Cambiar manifiestos, permisos, SDK, Gradle, catálogo de dependencias, reglas de optimización, firma, identificadores de aplicación o configuración de distribución solo si el plan aprobado los incluye. No subir versiones ni añadir servicios automáticamente.

## Desarrollo y validación Android
- Tras obtener permiso de lectura de código, seguir la estructura y patrones existentes. No imponer una arquitectura nueva ni crear módulos/dependencias fuera de alcance.
- En Compose, considerar estado y recomposición, ciclo de vida, rotación/recreación y recuperación de estado según el cambio. Evitar trabajo bloqueante en el hilo principal y efectos repetidos por recomposición; gestionar cancelación de tareas cuando corresponda.
- Usar recursos de texto para contenido visible y revisar accesibilidad (etiquetas, tamaños de texto, contraste y objetivos táctiles) y temas claro/oscuro cuando afecte a UI; no asumir que ya existen.
- Usar el Gradle Wrapper del proyecto desde `AUTIVA/`, previa comprobación de sus tareas y requisitos. Advertir si la ejecución requiere descargas o instalaciones no autorizadas; nunca usar la instalación global de Gradle por conveniencia.
- Elegir validaciones según el cambio: pruebas locales para lógica, instrumentadas/Compose para interacción, análisis estático y comprobaciones manuales de permisos, estado y compatibilidad cuando apliquen. Registrar comandos, directorio, resultado y limitaciones; no dar por probado un dispositivo sin haberlo usado.
- Antes de cambios de código, cumplir el checkpoint aunque no exista Git en la raíz. No inicializar repositorios, ejecutar commits, publicar en GitHub ni distribuir builds automáticamente.
