# Resume Analyzer

Takes a resume (PDF) and produces a summary, a tone assessment, and a list of detected skills using Hugging Face Transformers pipelines and models.

This project combines tokenization, model heads, and zero-shot classification into one working tool.

## What It Does

* Extracts text from an uploaded PDF resume using `pdfplumber`.
* Summarizes the resume in two ways to compare the high-level pipeline against the underlying mechanism:

  * `pipeline("summarization")` — the convenient wrapper.
  * `AutoModelForSeq2SeqLM` + manual tokenizer → `generate()` → `decode()` — demonstrates what the pipeline does internally.
* Assesses tone using zero-shot classification against descriptive labels: confident, formal, humble, enthusiastic, and casual.
* Detects skills using zero-shot classification with `multi_label=True`, since a resume can demonstrate multiple skills at once rather than just one best match.

## Technologies Used

* Python
* Hugging Face Transformers
* PyTorch
* pdfplumber
* BART (`facebook/bart-large-cnn`)
* Natural Language Processing (NLP)
* Zero-Shot Classification
