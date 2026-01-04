# cosine similarity

Extract symptoms, diseases, and body parts from clinical notes using **two complementary approaches**.

---

## 1️⃣ Embedding + Rule-based Matching
- **Method**:
  - Use **DistilBERT** to generate embeddings for text and a predefined vocabulary (symptoms, diseases, body parts)
  - Match text with vocabulary using **cosine similarity**
  - Adjustable threshold for matching (e.g., `0.7`)
- **Pros**:
  - Works well on small datasets
  - Captures semantic similarity (e.g., "tooth pain" ≈ "pain in tooth")
  - Quick to deploy without extensive labeled data
- **Cons**:
  - Limited context understanding
  - Negations like "no pain" are not automatically handled
- **Example**:
```python
info = extract_medical_info("Patient presents with tooth pain.")
print(info)
# {'text': 'Patient presents with tooth pain.',
#  'symptoms': ['tooth pain'],
#  'diseases': ['dental caries'],
#  'body_parts': []}
