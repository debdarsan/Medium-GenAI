# Chapter 4 — Exercises & Solutions
*Generative AI Cookbook Series*

---

## 1. Rewrite the Prompt

**Original:**  
```
Summarize this blog post.
```

**Improved Prompt:**  
```
You are a professional research assistant.
Task: Summarize the following blog post in exactly 3 bullet points.
Constraints: Each bullet under 12 words.
Format: Return as a JSON array with key: "summary".
```

**Why Better?**  
- Defines the role (assistant).  
- Sets task and clear structure.  
- Adds constraints (length + number).  
- Locks down the output format.

---

## 2. Temperature Test

**Prompt Used:**  
```
Summarize the benefits of Python for data science in 2 lines.
```

- **Temperature 0.2 (boring):**  
  “Python is widely used in data science.  
  It has libraries for analysis and visualization.”  

- **Temperature 0.7 (balanced):**  
  “Python shines in data science with libraries like Pandas, NumPy, and Matplotlib.  
  Its simplicity accelerates analysis and model building.”  

- **Temperature 1.2 (creative):**  
  “Python is the Swiss army knife of data science,  
  turning raw chaos into neat insights with a few imports.”  

**Observation:**  
- Low temp = safe, bland.  
- Medium temp = informative, balanced.  
- High temp = metaphorical, risk of drift.

---

## 3. Few-Shot Practice

**Prompt:**  
```
Answer the questions in JSON format with keys: "question" and "answer".

Q: What is 2+2?
A: 4

Q: Who wrote Hamlet?
A: Shakespeare

Q: What is the capital of France?
```

**Model Output (expected):**  
```json
{
  "question": "What is the capital of France?",
  "answer": "Paris"
}
```

**Lesson:**  
By giving examples, the model learns the pattern and follows it.

---

## 4. Roleplay

**Prompt:**  
```
You are a pirate teacher. Explain recursion in programming
as if teaching your crew.
```

**Expected Style:**  
“Arrr, recursion be when a function calls itself, matey!  
Like a treasure map that leads to another map,  
and ye keep followin’ till ye reach the gold.”  

**Lesson:**  
Personas change tone and style dramatically.

---

## 5. JSON Contract

**Prompt:**  
```
You are a QA assistant.
Task: Answer the following question.
Constraints: Respond ONLY in valid JSON.
Format:
{
  "question": "...",
  "answer": "..."
}

Q: What is the boiling point of water in Celsius?
```

**Expected Output:**  
```json
{
  "question": "What is the boiling point of water in Celsius?",
  "answer": "100"
}
```

**Lesson:**  
Explicit format instructions + constraints reduce the chance of freeform text.

---

## ✅ Key Lessons Recap

- Always **upgrade vague prompts** with role, task, constraints, and output format.  
- Temperature dramatically changes tone → choose based on task.  
- Few-shot examples are powerful for teaching format.  
- Roleplay enriches style without changing factual accuracy.  
- JSON contracts enforce structure and machine-readability.
