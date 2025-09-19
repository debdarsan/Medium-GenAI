## 1. Explain-It-Like-I’m-Five (Music or Cooking Metaphors)

**Answer (Cooking):**
A language model is like a cook who has tasted every dish in the world. When you give it the start of a recipe (your prompt), it guesses the next ingredient or step one by one. Sometimes a word takes one spoon of spice, sometimes a whole handful. Prompts are like telling the chef *“make it Italian and short”*. Parameters (temperature, max tokens) decide if the chef sticks to the recipe or experiments wildly.

---

## 2. Prompt Critic

**Vague Prompt:**
“Summarize this article.”

**Precise Prompt:**
“You are a concise research assistant. Summarize the article in **three bullet points**, each less than 15 words. Use only the terms appearing in the text. Output JSON with keys: `summary`.”

**Why Better:**
The precise one sets role, task, constraints, and output format—reducing rambling and enforcing clarity.

---

## 3. Hallucination Spotter

**Question:** “What features does the product *Zorblax-9000* offer?” (a fake product)

**Prompt Design:**
“You are a fact-checking assistant. If the answer is unknown, reply ONLY with:

```json
{ 'answer': 'I don’t know' }  
```

Otherwise, provide a short factual list.”

**Expected Result:** Forces a structured fallback instead of invention.

---

## 4. Guardrail Sketch

**Refusal Conditions:**

1. Hate speech → “I cannot provide harmful or discriminatory responses.”
2. Personal medical advice → “I cannot provide medical advice. Please consult a professional.”
3. Legal contract interpretation → “I cannot give binding legal advice.”

**Escalation Paths:**

* Offer link to human support agent.
* Ask for clarifying input (“Could you rephrase your question?”).

---

## 5. Evaluation Seed

**Automatic Checks:**

1. Output under 150 words.
2. Valid JSON if format required.
3. All required fields (e.g., summary, anomalies, actions) present.

**Human Judgments:**

* **Clarity** (is it easy to read?).
* **Fidelity** (does it preserve the main facts?).

**Failure Logging:** Store failed cases in a CSV with prompt + output + reason.

---

## 6. Parameter Tasting Menu

**Prompt:** “Write a haiku about data science.”

* **Temp = 0.2, top-p=0.8:** Safe, boring. Likely “Data science works / Models learn from large data / Predictions are made.”
* **Temp = 0.7, top-p=0.9:** Balanced, more poetic.
* **Temp = 1.2, top-p=1.0:** Wild, creative, maybe surreal haiku with dragons and quantum potatoes.

**Choice:**

* Brainstorming → high temp (≥1).
* Invoice totals → low temp (≤0.3).

---

## 7. Context Window Thought Experiment

**Strategies:**

1. **Chunking/Windowing:** Split text into smaller windows, process separately.
2. **Summarization:** Compress earlier context into a shorter summary before feeding.
3. **Citations/External Memory (RAG):** Store old content outside the model, re-inject as needed.

**Trade-offs:**

* Chunking may lose cross-window links.
* Summarization may drop nuance.
* RAG needs extra infra but is scalable.
