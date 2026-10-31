# Sentimiento en noticias financieras y movimiento de precios

Trabajo Práctico Integrador de Procesamiento de Lenguaje Natural, Universidad de Palermo.

Grupo 10. Gastón Eduardo Echegoyen, Joaquín Rodriguez, Simón Martín Rubiño Montilla y Juan Pablo García Guerrero.

Clasificamos titulares de noticias financieras sobre 8 acciones como positivos, negativos o neutros y
analizamos si esa señal de texto se relaciona con el movimiento del precio en la ventana siguiente. El
precio se usa solo como referencia para evaluar y no entra en ningún modelo. Comparamos un baseline de
TF-IDF con clasificadores lineales contra embeddings de oraciones, FinBERT y un LLM sin ajuste (Gemini
en zero-shot y few-shot).

No hay etiquetado manual. Los modelos se entrenan y se evalúan con dos datasets públicos que ya vienen
etiquetados (Financial PhraseBank y Twitter Financial News Sentiment), y las noticias reales se evalúan
contra el precio.

## Contenido

| Archivo o carpeta | Qué tiene |
|---|---|
| `TP_Integrador_Grupo10.ipynb` | El trabajo completo, ejecutado, con código, resultados y lectura de cada resultado |
| `Informe_TP_Integrador_Grupo10.pdf` | El informe técnico |
| `Informe_TP_Integrador_Grupo10.docx` | El mismo informe en Word, para editar |
| `requirements.txt` | Dependencias (Colab ya trae casi todas) |
| `data/cache/` | Datasets, titulares y precios descargados |
| `resultados/` | Tablas, figuras y bitácora de las consultas al LLM |

## Cómo correrlo

1. Subir esta carpeta a *Mi unidad* de Google Drive con el nombre `TP-Integrador-PLN`.
2. Abrir la notebook con Colab y elegir un entorno con GPU T4.
3. En *Secrets* (el ícono de la llave) cargar `GEMINI_API_KEY` y darle acceso a la notebook.
4. Ejecutar todas las celdas. La primera vez tarda entre 30 y 45 minutos.

Si `data/cache/` y `resultados/` ya tienen los archivos de la corrida, una nueva ejecución reproduce los
mismos números sin volver a descargar nada ni consultar al LLM.

## Datos y licencias

- Financial PhraseBank. Malo, P. et al. (2014), *JASIST* 65(4). Licencia CC BY-NC-SA 3.0.
- Twitter Financial News Sentiment (`zeroshot` en Hugging Face). Licencia MIT.
- FinBERT. Araci, D. (2019), modelo `ProsusAI/finbert`.
- Titulares públicos de Google News (RSS) y precios de Yahoo Finance (`yfinance`), usados con fines académicos.
