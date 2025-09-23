---
layout: single
title: "market-sentiment-analysis-README / Developer Guide"
permalink: /market-sentiment-analysis/readme/
author_profile: false
---


# 📊 Market Sentiment Analysis – 2026-os bemutató





## 🧠 AI Trendfigyelő – Példák és Magyarázatok

Ez az oldal egy gyakorlati bemutató a saját fejlesztésű **AI Trendfigyelő** rendszeremről, amely különböző nyelvi modellek (LLM-ek) segítségével végzi a napi jelentések elemzését, kulcsszavazást, és blogra publikálást. A példák Python + LangChain + OpenAI API + Hugging Face modellek köré épülnek.



### 📌 1. Kulcsszavazás magyar és angol szövegeken (multinyelvű NLP)

```python
from keybert import KeyBERT

kw_model = KeyBERT(model='paraphrase-multilingual-MiniLM-L12-v2')
keywords = kw_model.extract_keywords(szoveg, keyphrase_ngram_range=(1, 2), stop_words=None, top_n=10)
```

- 🔍 **Funkció:** a cikkekből automatikusan kulcsszavakat emel ki.
- 🌍 **Modell:** `paraphrase-multilingual-MiniLM-L12-v2` (magyarul is jól működik).
- ✅ Használható cikk-összegzések, SEO, címkézés céljából.



### 📰 2. AI hírek kulcsszavas csoportosítása, kategorizálás

```python
def classify_keywords(keywords):
    categories = {{
        "ChatGPT": ["gpt", "openai", "chatgpt"],
        "NVIDIA": ["nvidia", "gpu", "cuda"],
        "LLM modellek": ["llama", "mistral", "mixtral", "falcon"],
        "AI politika": ["regulation", "eu ai act", "policy"]
    }}
    # Egyszerű logikai besorolás
```

- 🧠 Automatikus témacímkézés pl. "ChatGPT", "LLM modellek", "NVIDIA", stb.
- 📚 Ezzel könnyen lehet naponta frissülő híreket csoportosítani.



### 📝 3. Markdown poszt generálása Jekyll / GitHub Bloghoz

```python
def generate_post(date, content, keywords):
    frontmatter = f"""
layout: single
title: "AI Trendfigyelő – {{date}}"
date: {{date}}
tags: {{keywords}}
"""
    return frontmatter + "\n\n" + content
```

- 📄 Automatikusan generált blogbejegyzés a napi AI hírekből.
- 🧩 Illeszkedik a GitHub Pages / Jekyll `Minimal Mistakes` témájához.
- 🏷️ Kulcsszavak automatikusan kerülnek be a `tags:` mezőbe.



### 🤖 4. HuggingFace `falcon-7b-instruct` használata magyarul

```python
from transformers import pipeline

pipe = pipeline(
    model="tiiuae/falcon-7b-instruct",
    task="text-generation",
    device=0
)

prompt = "Foglalja össze a következő hírt magyarul:"
output = pipe(prompt + full_article, max_new_tokens=300)
```

- 🇭🇺 **Magyar nyelvű összefoglalás** egy nagy, angolra betanított modell segítségével.
- ✅ GPU-n futtatható lokálisan (pl. RTX 4080).
- 🧵 Használható LangChain-be integrált RAG pipeline-ba is.



### 🔧 5. Parancssoros futtatás, automatikus publikálás

```bash
# Eseményindítás dátum szerint
py publish_to_zoli_blog.py --date 2025-09-14 --include-keywords
```

- 🛠️ A `publish_to_zoli_blog.py` script automatikusan betölti a napi híreket, összegzi őket, kulcsszavaz és publikálja a bejegyzést.
- 🔄 **CI/CD szerű működés** (napi ciklus).



## 📦 Főbb technológiák

| Modul | Használat |
|-|--|
| `KeyBERT` | kulcsszavazás magyarul |
| `transformers` | Hugging Face modellek |
| `LangChain` | összefűzött láncok a generáláshoz |
| `Jupyter Notebook` | prototípus fejlesztés |
| `Markdown` + `Jekyll` | blog poszt generálás |
| `argparse` | parancssori vezérlés |
