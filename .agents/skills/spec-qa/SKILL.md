---
name: spec-qa
description: Revisa el plan terminado antes de las preguntas de decisión, la aprobación y la escritura de la spec; detecta ambigüedades, contradicciones, límites y riesgos.
compatibility: opencode
---

# QA previo del plan

## Momento y modelo
Actuar como QA técnico senior con el plan terminado en conversación, antes de presentar preguntas de decisión, pedir aprobación y crear o modificar archivos. No exigir una spec en disco ni crear un borrador para revisarlo.
Modelo preferido: `openai/gpt-6.1-sol#medium`; `/qa-plan` lo selecciona en la sesión actual. Esta skill no cambia el modelo. Si ya se usa Sol, no abrir otra sesión para repetir el contexto.

También puede revisar una spec existente indicada expresamente, antes de modificarla, sin asumir que está aprobada. No es una segunda revisión completa obligatoria después de escribir.

## Contexto mínimo
Rutas desde la raíz del proyecto, no desde el directorio de esta skill:
1. Plan y decisiones ya presentes en la conversación.
2. `AGENTS.md`, `docs/constitution.md` y `MEMORY.md` si existe, reutilizando lo ya leído mientras siga vigente.
3. Spec existente solo si la tarea se refiere a ella.
4. Archivos estrictamente necesarios para verificar afirmaciones. Distinguir evidencia comprobada, hipótesis y datos pendientes.

Si no hay plan suficiente, indicar lo que falta. No explorar todo el repositorio ni inventar requisitos.

## Revisión
1. **Ambigüedades:** interpretaciones posibles, impacto y pregunta concreta cuando requiera una decisión del desarrollador.
2. **Contradicciones:** señalar los requisitos, criterios, contratos o decisiones incompatibles y su evidencia.
3. **Casos límite relevantes:** entradas vacías/incorrectas, permisos, recursos inexistentes, fallos externos, concurrencia, duplicados, reintentos, estados parciales y recuperación, según aplique.
4. **Constitución:** citar la regla o ID en conflicto. No autorizar excepciones; proponer una resolución y pedir aprobación. Detectar normas particulares faltantes sin inventar políticas de negocio.
5. **Seguridad e impactos:** comprobar fronteras de confianza, secretos, autorización, datos, compatibilidad, dependencias, pruebas y capacidad de recuperación. Evaluar si los criterios de aceptación son observables.

## Salida concisa
- Estado: `LISTO PARA APROBACIÓN`, `REQUIERE DECISIONES` o `REQUIERE MODIFICACIÓN`. El primero no equivale a aprobación ni permite construir.
- Solo hallazgos relevantes, ordenados por severidad. Para cada uno: ID, categoría, severidad (crítica/alta/media/baja), evidencia, impacto y corrección o decisión necesaria.
- Preguntas accionables agrupadas y sin duplicados: opciones, recomendación y consecuencia de elegir cada alternativa cuando sea útil.
- Si no hay hallazgos, decirlo sin fabricar preguntas y declarar las limitaciones de la revisión.

## Costo, seguimiento y límites
- Preferir una revisión previa bien acotada a escribir y volver a reescribir la spec. No repetir el plan completo en el informe.
- Resolver con el repositorio y los documentos lo que no sea una decisión de negocio; no preguntar lo ya respondido.
- Tras las respuestas, actualizar el plan solo en conversación y revisar únicamente los puntos afectados si cambian requisitos o riesgos. Pedir aprobación final explícita.
- No editar código, spec, memoria ni otros archivos; no ejecutar operaciones con efectos persistentes.
- Tras implementar, ejecutar validaciones aplicables. Reservar una revisión dirigida adicional para autenticación/autorización, migraciones, pagos, borrados u otros cambios de alto riesgo; no sustituir pruebas por QA del plan.
