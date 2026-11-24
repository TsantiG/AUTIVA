---
description: Revisa el plan con Sol antes de preguntar, aprobar y escribir
agent: plan
model: openai/gpt-6.1-sol#medium
subagent: false
---

Revisa el último plan completo de esta conversación. Contexto adicional del desarrollador: $ARGUMENTS

Carga la skill spec-qa y aplícala al plan en conversación, sin crear una spec provisional ni modificar archivos. Si no hay un plan suficiente, indícalo en lugar de inventarlo.
Devuelve hallazgos verificables, correcciones recomendadas y preguntas necesarias con opciones y recomendación. No repitas preguntas ya resueltas ni la documentación completa.
Después de las respuestas, ajusta solo lo afectado en el plan y solicita aprobación explícita de la versión final y el número NNN de la spec si falta. No vuelvas a Luna para repetir el plan ni ejecutes la implementación. Para escribir será necesario cambiar a Build con Sol.
