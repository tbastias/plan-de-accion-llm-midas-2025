# Plan de acción

**Objetivo general:** Evaluar la viabilidad técnica, operativa y económica de implementar un modelo local (on‑premise).

## Fases del plan

### Fase 0 — Preparación

**Modelos propuestos**

Llama 3.1 (8B, 70B)
- Open source de Meta, licencia permisiva comercial
- Gran comunidad y soporte
- 8B: corre en GPUs consumer (24GB VRAM)
- 70B: calidad cercana a GPT-4 en muchas tareas

Mistral (7B, Mixtral 8x7B)
- Excelente ratio calidad/tamaño
- Mixtral usa arquitectura MoE (solo activa parte del modelo por token = más rápido)
- Buen desempeño en español y código

Qwen 2.5 (7B, 14B, 32B)
- Muy buenos en tareas técnicas y razonamiento
- Soporte multilingüe robusto
- 32B competitivo con modelos más grandes

Gemma 2 (9B, 27B)
- De Google, optimizado para eficiencia
- Buena calidad con menos recursos
- Licencia abierta

**Coste real de implementación:**

Tiempo:
- Setup inicial: 1-2 semanas (infraestructura + pruebas básicas)
- Optimización: 2-4 semanas adicionales
- Mantenimiento: 4-8 horas/mes

Dinero (hardware on-premise):

| Modelo | GPU necesaria | Coste aprox | Alternativa cloud |
| ------ | ------------- | ----------- | ----------------- |
| 7-9B | RTX 4090 (24GB) | $1,500-2,000 | ~$0.50-1/hora |
| GPU13-14B | A100 40GB | $10,000-15,000 | ~$2-3/hora | 
| 30-32B | A100 80GB x2 | $30,000-40,000 | ~$6-8/hora |
| 70B | H100 x2-4 | $80,000-120,000 | ~$15-25/hora |

**Método elegido para realizar las pruebas**

Comparación A/B
- Misma pregunta utilizando varios modelos
- Usuarios eligen mejor respuesta (blind test)
- Métricas: % preferencia, tiempo de respuesta

**Herramienta elegida para validar pruebas de concurrencia**

Locust
- Herramienta de código abierto para pruebas de carga y rendimiento que permite simular usuarios concurrentes en un sistema, definiendo el comportamiento de esos usuarios directamente en código Python

### Fase 1 — Pruebas exploratorias

### Fase 2 — Selección de modelos candidatos y pruebas de rendimiento

### Fase 3 — Pruebas de evaluación de utilidad para Midas

### Fase 4 — Pruebas de fine‑tuning (si hay tiempo)

### Fase 5 — Consolidación y recomendación
