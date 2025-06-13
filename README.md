# 🧽 Interactive Object Removal with AI Inpainting

Remove unwanted objects from images using computer vision and generative AI. This project provides two interactive workflows:

* **Semantic Segmentation Mode**: Select objects to remove based on class labels (e.g., person, car) using Mask2Former, then inpaint using Stable Diffusion.
* **Freehand Masking Mode**: Manually draw over objects using an HTML canvas and inpaint using the LaMa model.

Runs entirely in Google Colab — no local setup required.

---

## ✨ Features

* 🔍 **Semantic segmentation** with [Mask2Former](https://huggingface.co/facebook/mask2former-swin-large-coco-panoptic) (COCO labels)
* 🧠 **Text-guided inpainting** with [Stable Diffusion 2 Inpainting](https://huggingface.co/stabilityai/stable-diffusion-2-inpainting)
* ✏️ **Freehand masking** via interactive HTML5 canvas
* 🧽 **Fast inpainting** using [LaMa](https://github.com/saic-mdal/lama) (via [simple-lama-inpainting](https://github.com/enesmsahin/simple-lama-inpainting))
* 🖼️ Visual output with overlay masks and multiple regenerated results
* ☁️ Zero setup — designed for Google Colab

---

## 📁 Notebooks

| Notebook                                                                                                       | Description                                                              |
| -------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| [`semantic-object-removal-with-stable-diffusion.ipynb`](./semantic-object-removal-with-stable-diffusion.ipynb) | Select objects using panoptic segmentation, remove with Stable Diffusion |
| [`freehand-object-removal-with-lama.ipynb`](./freehand-object-removal-with-lama.ipynb)                         | Manually draw over regions to remove using LaMa inpainting               |

---

## 🛠️ Dependencies

Installations are handled automatically in Colab, but core libraries include:

* `diffusers`, `transformers`, `torch`, `PIL`
* `OpenCV`, `matplotlib`, `numpy`
* `simple-lama-inpainting` (for LaMa mode)

---

## 🔧 How It Works

### 📌 Semantic Segmentation + Stable Diffusion

1. Load an image and segment it using **Mask2Former**.
2. Select an object by **segment ID**.
3. Enter a **text prompt** describing the background.
4. Inpaint the masked region using **Stable Diffusion**.

### 🖍️ Freehand Masking + LaMa

1. Upload or link an image.
2. Draw freely over unwanted areas on an interactive canvas.
3. Inpaint using **LaMa** for fast background reconstruction.

---

## 🖼️ Example Output

*(You can add example images in the `assets/` folder and reference them here)*

```markdown
![Example using Mask2Former and Stable Diffusion](assets/stable_example.png)
![Example using LaMa freehand mask](assets/lama_example.png)
```

---

## 🙏 Acknowledgments

This project is built on top of the following open-source models and repositories:

* [Stable Diffusion 2 Inpainting](https://huggingface.co/stabilityai/stable-diffusion-2-inpainting) by Stability AI
* [Mask2Former Swin Large (COCO)](https://huggingface.co/facebook/mask2former-swin-large-coco-panoptic) by Meta AI
* [Simple LaMa Inpainting](https://github.com/enesmsahin/simple-lama-inpainting), a wrapper for [LaMa](https://github.com/saic-mdal/lama) from Samsung AI

Thanks to the maintainers and researchers behind these tools.

---

## 📄 License

This project is for research and educational purposes. Please check the licenses of each model for commercial use.
