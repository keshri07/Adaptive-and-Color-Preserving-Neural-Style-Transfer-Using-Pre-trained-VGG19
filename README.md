# 🎨 Adaptive & Color-Preserving Neural Style Transfer (NST)

This project presents an enhanced **Neural Style Transfer (NST)** framework that introduces **adaptive style weighting** and **color preservation mechanisms** to generate visually coherent and perceptually balanced stylized images.

Unlike traditional NST approaches, this method dynamically adjusts style influence based on image characteristics while maintaining the original color distribution of the content image.

---

##  Key Contributions

-  **Adaptive Style Scaling**  
  Dynamically adjusts style strength using image statistics such as edge density and texture complexity.

-  **Color Preservation Mechanism**  
  Maintains the original color distribution of the content image while transferring only texture and style.

-  **Improved Perceptual Quality**  
  Reduces over-stylization, artifacts, and unnatural distortions.

-  **Efficient Optimization**  
  Built on a pre-trained VGG19 network with optimized loss balancing.

---

##  Method Overview

The proposed framework extends classical Neural Style Transfer by integrating:

### 1. Adaptive Style Control

Instead of using a fixed style weight, the model computes image complexity using:

- Edge density (Sobel operator)
- Statistical features (mean, variance)

These are used to dynamically scale the style contribution:

β_adaptive = f(image complexity)

---

### 2. Color Preservation

To prevent unnatural color shifts:

- Style transfer is applied while preserving luminance/chrominance relationships  
**OR**
- Output colors are re-aligned with the original content image  

This ensures:
- Natural-looking outputs  
- Better applicability to real-world and biomedical images  

---

##  Objective Function

The total loss is defined as:

L_total = α * L_content + β_adaptive * L_style + γ * L_color

Where:

- **L_content** → Content reconstruction loss  
- **L_style** → Style loss using Gram matrices  
- **L_color** → Color preservation loss  
- **α, β, γ** → Weight parameters  

---

##  Project Structure
