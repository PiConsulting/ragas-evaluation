# 🧪 RAGAS Evaluation Notebook

Este notebook muestra cómo evaluar un pipeline de **Retrieval-Augmented Generation (RAG)** utilizando **RAGAS**, una herramienta que permite cuantificar la calidad de las respuestas generadas y la efectividad del sistema de recuperación de contexto.

Se utilizan métricas como:
- `context_recall` y `context_precision` para evaluar la **recuperación**.
- `faithfulness` y `answer_relevancy` para evaluar la **generación**.

## 📂 Datasets utilizados

### 📚 Base de conocimiento (chunked)
- **Fuente:** [`jamescalam/ai-arxiv2-chunks`](https://huggingface.co/datasets/jamescalam/ai-arxiv2-chunks)
- **Descripción:** Dataset con abstracts y artículos científicos relacionados a IA, preprocesados y divididos en _chunks_ listos para ser embebidos en una base vectorial.

### ✅ Datos con ground truth
- **Fuente:** [`aurelio-ai/ai-arxiv2-ragas-mixtral`](https://huggingface.co/datasets/aurelio-ai/ai-arxiv2-ragas-mixtral)
- **Descripción:** Dataset que incluye preguntas, respuestas correctas (_ground truth_) y documentos relevantes. Utilizado para evaluar el rendimiento de un pipeline RAG de forma supervisada.

## 🛠️ Requisitos

- Python 3.10+
- API key de OpenAI
- Hugging Face Datasets
- LangChain
- RAGAS
- ChromaDB

## 🔐 Variables de entorno

El archivo `.env` debe contener:

```env
OPENAI_API_KEY=tu_clave_de_openai
```

> ⚠️ Este archivo está ignorado en `.gitignore` por seguridad.

## ⚙️ Descripción del flujo

1. Se construye una base de conocimiento con embeddings OpenAI y ChromaDB.
2. Se configura un agente conversacional que recupera contexto desde la base vectorial.
3. Se responde una serie de preguntas reales.
4. Se evalúa automáticamente el desempeño usando las métricas de RAGAS.

---

📊 Ideal para probar pipelines RAG en entornos controlados y medir su calidad con métricas objetivas.