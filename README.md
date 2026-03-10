# 🖼️ Text-to-Image Generator using Stable Diffusion 

This project generates images from text prompts using **Stable Diffusion XL**.
Users can enter a text description, and the model generates a corresponding image using a diffusion-based deep learning model.

The project also includes a **Gradio interface** to make the model easy to use through a simple web UI.

---

## 🚀 Features

* Generate images from natural language prompts
* Uses **Stable Diffusion XL (SDXL)**
* GPU accelerated using **PyTorch**
* Interactive **Gradio web interface**
* High-quality image generation

---

## 🧠 Model Used

This project uses the pretrained model:

**stabilityai/stable-diffusion-xl-base-1.0**

Stable Diffusion XL is a powerful diffusion model capable of generating high-resolution and detailed images from text prompts.

---

## 📂 Project Structure

```
text-to-image-generator/
│
├── text--image.ipynb      # Main notebook
├── README.md              # Project documentation
```

---

## ⚙️ Installation

Install the required libraries before running the project.

```bash
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

This will open a **web interface** where users can type prompts and generate images.

---

## 💻 Hardware Requirement

* GPU recommended (CUDA supported)
* Minimum **8GB+ GPU memory**
* Works best on **Google Colab / Kaggle / Local GPU**

---

## 📌 Example Prompt

```
A futuristic city at sunset, ultra realistic, 8k
```

```
Superman eating panipuri
```

---

## 🔮 Future Improvements

* Add image download option
* Support negative prompts
* Add image styles
* Deploy as a web application
* Optimize inference speed

---

## 📜 License

This project uses the **Stable Diffusion model by Stability AI**.
Follow the license terms when using the model.

---

## 👨‍💻 Author

Developed by Ratna Raju

Machine Learning | Deep Learning | AI Projects
