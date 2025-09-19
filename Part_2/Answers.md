
# Chapter 2 — Exercises & Solutions

*Generative AI Cookbook Series*

---

## 1. Prompt Playground

**Experiment:**

* Prompt 1: `"Once upon a time in a hidden valley,"` → Output in fairy-tale style.
* Prompt 2: `"Breaking news: Scientists have discovered"` → Output mimics news headline / report.
* Prompt 3: `"# This function calculates the area of a circle"` → Output extends like Python code.

**Answer:**
The same model can adapt its style based on your initial words. It “mirrors” the genre.

---

## 2. Parameter Chef

**Prompt:** `"Tell me a short story about a cat and a robot."`

* **Temperature 0.2:** Predictable, plain story. Safe and boring.
* **Temperature 0.7:** Balanced, creative but coherent. Robot-cat friendship story emerges.
* **Temperature 1.5:** Wild and chaotic. Cat might fly into space and build quantum muffins.

**Answer:**
Low temperature = boring, high temperature = risky, medium = sweet spot for storytelling.

---

## 3. Variations Box

**Prompt:** `"Write a two-line motivational quote about learning AI."`
**num\_return\_sequences=5**

**Example Outputs:**

1. “Learning AI is like climbing a mountain; each step shows a wider horizon.”
2. “Every token you learn brings a new universe closer.”
3. “AI is your apprentice; train it, and it will build your dreams.”
4. “In the code of life, curiosity is the compiler.”
5. “Study AI today; tomorrow, it will study with you.”

**Answer:**
Pick 1 or 3 as “publishable,” laugh at 4 for being too quirky.

---

## 4. Mini Challenge

**Prompt:** `"Write a short poem about a programmer who talks to pigeons."`

**Example Output (distilgpt2):**
“The coder typed at dawn,
While pigeons perched nearby.
They whispered bug reports,
And flapped when builds went awry.”

**Answer:**
Shows that specific, playful prompts can trigger surprisingly coherent outputs even in small models.

---

## ✅ Key Takeaways

* Different prompts guide the **tone and genre** of output.
* Temperature heavily affects creativity vs. coherence.
* Multiple sequences highlight the model’s **probabilistic nature**.
* Being specific in prompts produces the most satisfying results.
