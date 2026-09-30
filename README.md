#Resume Analyzer

Takes a resume (PDF) and produces a summary, a tone assessment, and a list of detected skills — using Hugging Face transformers pipelines and models.

Project that combines tokenization, model heads, and zero-shot classification into one working tool.

What it does:
Extracts text from an uploaded PDF resume (pdfplumber)
Summarizes the resume two ways, to compare the high-level pipeline against the underlying mechanism:
pipeline("summarization") — the convenient wrapper
AutoModelForSeq2SeqLM + manual tokenizer → generate() → decode() — what the pipeline does internally
Assesses tone — zero-shot classification against descriptive labels (confident, formal, humble, enthusiastic, casual)
Detects skills — zero-shot classification with multi_label=True, since a resume can demonstrate multiple skills at once rather than just one best match

Technologies Used
Python
Hugging Face Transformers
PyTorch
pdfplumber
BART (facebook/bart-large-cnn)
Natural Language Processing (NLP)
Zero-Shot Classification
