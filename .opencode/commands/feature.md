---
description: Prepara un plan con Luna sin escribir archivos
agent: plan
model: openai/gpt-6-luna#medium
subagent: false
---

Planifica esta solicitud: $ARGUMENTS

Lee desde la raíz del proyecto AGENTS.md, docs/constitution.md y MEMORY.md, y solo el contexto adicional necesario.
Prepara en esta conversación un plan conciso con alcance/exclusiones, archivos y cambios, riesgos, criterios de aceptación y validación. Propón reglas constitucionales adicionales solo si hacen falta.
No crees ni modifiques archivos, tampoco una spec o la memoria. No inventes datos del proyecto ni presentes decisiones de negocio como resueltas.
Antes de las preguntas de decisión, indica ejecutar /qa-plan en esta misma sesión: revisará el plan con Sol usando spec-qa. Si falta un dato indispensable para poder planear, puedes pedirlo primero.
