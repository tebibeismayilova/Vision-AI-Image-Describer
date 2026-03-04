# 🖼️ Vision AI — Image Describer

[![Live Demo](https://img.shields.io/badge/🚀_Live_Demo-gradio.live-blue?style=for-the-badge)](https://b3b1916e89220cfb32.gradio.live)

> **👉 Try it live: [https://b3b1916e89220cfb32.gradio.live](https://b3b1916e89220cfb32.gradio.live)**

A free, no-API-key image description system powered by **BLIP Large** (Salesforce) that runs entirely on Google Colab. Upload any image and get detailed AI-generated descriptions using multiple analysis modes.

---

## ✨ Features

- 🧠 **GPT-Style Comprehensive Description** — runs 15 layered questions and weaves them into 4 rich paragraphs (scene, composition, objects, mood)
- 🗂️ **Multi-Select Analysis Modes** — choose one or more focused modes simultaneously
- ✅ **Select All / Clear All** — quickly toggle all modes at once
- 🌐 **Web UI** — clean Gradio interface with drag-and-drop image upload
- 🔗 **Public URL** — share your running app with anyone via Gradio's public link
- 💸 **100% Free** — no API key, no credit card, no account needed

---

## 🗂️ Analysis Modes

| Mode | What it analyzes |
|------|-----------------|
| 📝 Full Description | General scene + foreground + background |
| 🎨 Colors & Composition | Dominant colors, lighting, layout, visual style |
| 👶 Child-Friendly Check | Content appropriateness and themes |
| 📦 List Objects | Main objects, foreground items, background items, people |
| 😊 Mood & Emotion | Atmosphere, feeling, emotional impact |
| 🌍 Scene & Setting | Location, environment, time of day |
| 🔍 Fine Details | Textures, small details, close-up observations |

---

## 🚀 Quick Start (Google Colab)

### Step 1 — Open Google Colab
Go to [colab.research.google.com](https://colab.research.google.com) and create a new notebook.

### Step 2 — Enable GPU (recommended)
```
Runtime → Change runtime type → T4 GPU
```

### Step 3 — Install dependencies
```python
!pip install transformers gradio torch torchvision --quiet
```

### Step 4 — Run the app
Copy the contents of `vision_ai_allinone.py` into a cell and run it.

### Step 5 — Open the app
You will see a public URL in the output:
```
Running on public URL: https://xxxx.gradio.live
```
Open it in any browser on any device.

---

## 📁 Project Structure

```
vision-ai/
│
├── vision_ai_allinone.py   # Main app (all-in-one)
└── README.md
```

---

## ⚙️ How It Works

```
User uploads image
        │
        ▼
┌───────────────────────┐
│  BLIP Large Model     │  ← runs locally, no internet needed
│  (Salesforce)         │
└───────────────────────┘
        │
        ▼
  15 targeted questions
  asked about the image
        │
        ▼
  Answers stitched into
  4 flowing paragraphs
        │
        ▼
  Displayed in Gradio UI
```

The **GPT-Style mode** works by asking BLIP 15 different targeted questions about the image (subject, setting, foreground, background, colors, lighting, textures, people, objects, actions, mood, emotion, style) and then intelligently combining all the answers into coherent paragraphs — simulating the kind of rich description you'd get from a large language model.

---

## ⏱️ Performance

| Hardware | Comprehensive Mode | Single Mode |
|----------|--------------------|-------------|
| CPU | 20–40 seconds | 3–8 seconds |
| T4 GPU (Colab free) | 5–10 seconds | < 2 seconds |

---

## 🧰 Tech Stack

| Tool | Purpose |
|------|---------|
| [BLIP Large](https://huggingface.co/Salesforce/blip-image-captioning-large) | Vision-language model |
| [Transformers](https://github.com/huggingface/transformers) | Model loading & inference |
| [Gradio](https://gradio.app) | Web UI |
| [PyTorch](https://pytorch.org) | Deep learning backend |
| [Pillow](https://python-pillow.org) | Image processing |

---

## 📋 Requirements

```
transformers
gradio
torch
torchvision
Pillow
```

Install all at once:
```bash
pip install transformers gradio torch torchvision
```

---

## 🖼️ Example Output

**Input:** War scene photo with soldiers

**Comprehensive Description output:**
```
A group of soldiers charge across a devastated battlefield surrounded
by smoke and fire. The main subject is armed infantry in military
uniform. The scene is set in a war zone with destroyed terrain,
with dramatic and harsh natural lighting.

Looking at the composition, soldiers are rushing forward in the
foreground while dark smoke and burning debris fill the background.
The dominant colors are brown, grey, and black, and the lighting is
tense and high-contrast. Notable textures include rough dirt,
torn clothing, and charred wood.

The image features multiple soldiers in combat gear. Key objects
include rifles, military helmets, and destroyed landscape. The
activity depicted is an infantry charge under fire.

In terms of atmosphere, the mood is chaotic and intense. This image
makes the viewer feel anxious and alarmed. The visual style can be
described as gritty war photography.
```

---

## 📄 License

This project is open source and free to use. The BLIP model is released under the [BSD-3-Clause License](https://huggingface.co/Salesforce/blip-image-captioning-large) by Salesforce Research.

---

## 🙏 Credits

- **BLIP Model** — [Salesforce Research](https://github.com/salesforce/BLIP)
- **Gradio** — [Hugging Face](https://gradio.app)
- Built with ❤️ using Google Colab
