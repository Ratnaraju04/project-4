<div align="center">

# 🖼️ Text-to-Image Generator using Stable Diffusion XL

Generate images from text prompts using **Stable Diffusion XL (SDXL)** and an interactive **Gradio interface**.

![Python](https://img.shields.io/badge/Python-3.10-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-DeepLearning-red)
![Diffusers](https://img.shields.io/badge/HuggingFace-Diffusers-yellow)
![Gradio](https://img.shields.io/badge/UI-Gradio-orange)

</div>

---

## 📌 Project Overview

This project generates images from **text prompts** using **Stable Diffusion XL**.
Users can type a description and the AI model will create a corresponding image.

The project also includes a **Gradio web interface** so users can generate images easily from a browser.

---

## 🖼️ Example Output

Prompt used:

```
superman eating panipuri
```

<div align="center">

![Generated Image](superman_output.png)

</div>

---

## 🚀 Features

* Generate images from natural language prompts
* Uses **Stable Diffusion XL (SDXL)**
* GPU accelerated using **PyTorch**
* Interactive **Gradio web interface**
* High-quality AI image generation

---

## 🧠 Model Used

**stabilityai/stable-diffusion-xl-base-1.0**

Stable Diffusion XL is a powerful diffusion-based model capable of generating **high-resolution and detailed images from text prompts**.

---

## 📂 Project Structure

```
text-to-image-generator/
│
├── text--image.ipynb
├── superman_output.png
├── README.md
```

---

## ⚙️ Installation

Install required libraries:

```
pip install diffusers
pip install invisible_watermark transformers accelerate safetensors
pip install gradio
```

---

## ▶️ How to Run

### 1️⃣ Import Libraries

```python
from diffusers import DiffusionPipeline
import torch
import gradio as gr
```

---

### 2️⃣ Load the Model

```python
pipe = DiffusionPipeline.from_pretrained(
    "stabilityai/stable-diffusion-xl-base-1.0",
    torch_dtype=torch.float16,
    use_safetensors=True,
    variant="fp16"
)

pipe.to("cuda")
```

---

### 3️⃣ Generate Image

```python
prompt = "superman eating panipuri"
image = pipe(prompt=prompt).images[0]
image
```

---

## 🌐 Gradio Interface

```python
def generate_image(prompt):
    image = pipe(prompt=prompt).images[0]
    return image

demo = gr.Interface(
    fn=generate_image,
    inputs=gr.Textbox(label="Enter your prompt"),
    outputs="image",
    title="Text to Image Generator"
)

demo.launch()
```

---

## 💻 Hardware Requirements

* GPU recommended (CUDA supported)
* Minimum **8GB GPU memory**
* Works best on **Google Colab / Kaggle / Local GPU**

---

## 📌 Example Prompts

```
A futuristic city at sunset, ultra realistic, 8k
```

```
Superman eating panipuri
```

```
A cyberpunk samurai walking in neon Tokyo
```

---

## 🔮 Future Improvements

* Add image download option
* Support negative prompts
* Add style presets
* Deploy as a web application
* Optimize inference speed

---

## 📜 License

This project uses the **Stable Diffusion model by Stability AI**.
Follow the license terms when using the model.

---

## 👨‍💻 Author

Ratna Raju

Machine Learning | Deep Learning | AI Projects
