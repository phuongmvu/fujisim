# **FujiSim — Context-Aware Film Simulation Recommender**
*A custom GPT that recommends the best Fujifilm film simulation recipe based on lighting, subject, and vibe — powered entirely by a structured CSV catalog.*

## 📸 Overview
**FujiSim** is an AI-assisted film simulation recommender built through a Custom GPT.  
It uses a structured CSV catalog of personally curated film simulation “recipes” and applies a transparent, weighted scoring system to suggest the most suitable recipe for any shooting scenario.

This project lives at the intersection of:
- structured data modeling  
- AI reasoning  
- human–computer interaction  
- creative technology  

This version focuses purely on **context-aware simulation recommendation** (no image filters or preview features yet).

---

## 🧠 How FujiSim Works

1. **Load the CSV catalog**  
   The GPT parses your film-sim dataset (recipe name, settings, context tags, vibe tags, lighting suitability, etc.).

2. **Interpret your prompt**  
   Example:  
   *“Indoor tungsten portrait with medium skin tone; looking for warm cinematic vibes.”*

3. **Score each recipe** using these factors:
- **Light fit:** 0–3  
- **Subject fit:** 0–2  
- **Vibe fit:** 0–2  
- **Context fit:** 0–2  
- **Risk penalty:** −0 to −1  

4. **Recommend the top 1–3 recipes**  
   With:
   - clear reasoning  
   - optional small tweaks  
   - a compare table  
   - NO hallucinated recipe names  
   - ONLY entries from your CSV  

The GPT is hard-restricted to use *your* catalog and nothing else.

---

## 🧩 CSV Schema (Required Columns)

| Column | Description |
|--------|-------------|
| `name` | Recipe name |
| `base_sim` | Base profile (e.g., Reala, Classic Neg) |
| `settings` | WB/DR/Contrast/Color/etc. (plain text string) |
| `best_contexts` | Tags like: indoor, outdoor, travel, night_street |
| `light_conditions` | tungsten, harsh_sun, overcast, neon |
| `subject_types` | portrait_skin_medium, landscape, architecture |
| `vibe` | cinematic, warm, nostalgic, muted, punchy |
| `notes` | Warnings or special cases |

Use lowercase tags; separate with commas; multi-word tags use **underscores**  
(e.g., `portrait_skin_medium`, `soft_contrast`).

---

## 💬 Example Prompts

- "Recipe to get a luxury, high-end look for an indoor shoot?"
- "Recipe that is versatile for indoor and outdoor shooting on vacation?"

---

## 🧪 Why I Built FujiSim
I shoot with a Fujifilm camera and love how film simulations let me personalize the look of each photo. Over time, I built a curated library of “trusted” custom recipes that reflect my aesthetic preferences. The challenge was choosing the right recipe for each shooting environment — especially when lighting, subject type, and the mood I’m aiming for can dramatically change the outcome.

Although online recommendations or ChatGPT were generally helpful, they weren’t ideal for my workflow, because film simulation preference is deeply personal. My taste often differs from other photographers, and I wanted guidance that was grounded in **my own curated catalog** rather than general internet suggestions.

With this in mind, I built **FujiSim** — a GPT that understands context (lighting, subject, vibe) and recommends the best-fitting recipe strictly from my personal collection. Building this system allowed me to explore how to translate subjective creative preferences into structured metadata and how to design an AI that follows clear, controlled reasoning without hallucinating generic results.

---

## 🛠 Project Structure

```
filmsim-gpt/
│
├── README.md
├── filmsim_gpt_instructions.txt
└── filmsim_catalog_template.csv    # (not included here; add your own)
```

---

## 🚀 How to Use FujiSim

### **1. Create a Custom GPT**
- Go to **ChatGPT → Explore GPTs → Create**
- Paste the entire contents of `filmsim_gpt_instructions.txt` into the **Instructions** field
- Enable:
  - ✔ Code Interpreter
  - ✔ File Uploads

### **2. Upload Your CSV**
Place your film-sim catalog under **Knowledge**.

### **3. Ask for scenarios**
FujiSim will:
- load the CSV  
- evaluate every recipe  
- score them using the matching rubric  
- recommend only recipes from your collection  

---

## 📄 License
This project is for personal and educational use.  
Film simulation recipes belong to their respective creators.
