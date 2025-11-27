# FujiSim GPT — Context-aware Fujifilm X100VI recipe recommender

Use this kit to create a custom GPT that recommends Fujifilm X100VI film simulations based on context.

## Files
- `filmsim_catalog_template.csv` — Starter schema with 5 example rows. Fill/expand with your sims.
- `filmsim_gpt_instructions.txt` — Copy/paste into **GPT Builder → Configure → Instructions**.

## Steps

1. **Prepare your catalog**
   - Open `filmsim_catalog_template.csv` and replace/add rows with your own recipes.
   - Keep headers exactly: `name | base_sim | settings | best_contexts | light_conditions | subject_types | vibe | notes`
   - Keep tag values lowercase; separate multiple tags with commas (`,`).

2. **Create the Custom GPT**
   - In ChatGPT, go to **Explore GPTs → Create**.
   - **Name:** *FujiSim GPT — Context-aware Fujifilm X100VI recipe recommender*  
   - **Description:** "Recommends the best Fujifilm X100VI film simulations for your scene (light, subject, mood), using my personal recipe catalog. Gives reasons, optional tweaks, and a quick compare table."
   - **Profile picture:** (optional) any film-camera icon.
   - **Capabilities:** turn on **Web (optional)** and **Code Interpreter**; enable **Uploads & Links** so the GPT can read your CSV.
   - **Instructions:** paste the content of `filmsim_gpt_instructions.txt`.

3. **Knowledge**
   - Upload your filled `filmsim_catalog_template.csv`. The GPT will parse it on first use.

4. **Test prompts**
   - "Indoor portrait under warm tungsten, medium skin tone, moody vibe — suggest 3 recipes."
   - "Overcast street in SoHo, minimal grain, clean neutral look."
   - "Blue hour city skyline, want cinematic but not over-saturated."
