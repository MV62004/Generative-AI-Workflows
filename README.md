# Generative AI Workflow Optimization & Prompt Engineering

This repository documents optimized, node-based workflows for local Generative AI image generation, developed to streamline creative iteration and resolve hardware bottlenecks. 

## 1. Z Image GGUF Quantization Pipeline
**Objective:** Maximize inference speed and reduce VRAM overhead for rapid T2I (Text-to-Image) experimentation on consumer hardware.
**Implementation:**
- Reverse-engineered and modified complex community workflows to consolidate inputs and streamline the node graph.
- Integrated GGUF quantized model loaders (Q8) to bypass standard bf16 VRAM limitations, preventing hardware throttling and drastically reducing generation times.
- Maintained strict prompt adherence and visual fidelity by calibrating sampler settings to compensate for quantization trade-offs.

Workflow:
<img width="1446" height="680" alt="image" src="https://github.com/user-attachments/assets/e4e3d552-065a-4e55-8de3-3d062f770512" />


## 2. SDXL Inpainting & Iterative Refinement
**Objective:** Identify and correct anatomical or structural inaccuracies in AI-generated outputs without destroying the base composition.

**Implementation:**
- Developed localized inpainting workflows using VAE Encode nodes to mask and target specific flaw areas.
- Utilized seed-locking to maintain baseline lighting and composition while iterating on prompt refinements.
- Integrated targeted LoRA loading for specific anatomical corrections and lighting adjustments.
- **Prompt Engineering:** Strictly managed prompt weighting (capped at 1.1 - 1.3) to prevent latent space degradation and artifacting, relying on precise mask conditioning and CFG tuning for corrections.

**Visual Example:**
![SDXL Inpainting Workflow](sdxl-inpainting-workflow.png)
*Before:* <img width="832" height="1216" alt="image" src="https://github.com/user-attachments/assets/552ad0fd-810d-45dd-83ad-e27e10c174d7" />
→ *After:* <img width="832" height="1216" alt="image" src="https://github.com/user-attachments/assets/26f2302b-1098-4a08-bb30-c8357a1a4f4d" />

*Corrected anatomical inconsistencies in hand positioning through targeted inpainting while preserving original composition and lighting, while replacing the object with a pen.*

Workflow used:
<img width="1461" height="839" alt="image" src="https://github.com/user-attachments/assets/ab29fcb3-1820-480b-b562-b9e8226c0847" />


## Core Competencies Demonstrated
- **Workflow Optimization:** Translating creative briefs into precise, reproducible node graphs.
- **Hardware Efficiency:** Adapting high-resource models for local execution via quantization.
- **Quality Control:** Systematic identification of AI inaccuracies and implementation of prompt/node-based corrections.
