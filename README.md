Generative AI Workflow Optimization & Prompt Engineering

This repository documents optimized, node-based workflows for local Generative AI image generation, developed to streamline creative iteration and resolve hardware bottlenecks.

1. Z Image GGUF Quantization Pipeline

Objective: Maximize inference speed and reduce VRAM overhead for rapid Text-to-Image (T2I) experimentation on consumer hardware.

Implementation:

Reverse-engineered and modified complex community workflows to consolidate inputs and streamline the node graph.
Integrated GGUF quantized model loaders (Q8) to reduce VRAM requirements compared with standard BF16 execution, helping prevent hardware throttling and improve generation efficiency.
Maintained prompt adherence and visual fidelity by calibrating sampler settings to compensate for quantization trade-offs.

Workflow:

<p align="center">
<img src="https://github.com/user-attachments/assets/e4e3d552-065a-4e55-8de3-3d062f770512" alt="Z Image GGUF Quantization Workflow" width="100%">
</p>

2. SDXL Inpainting & Iterative Refinement

Objective: Identify and correct anatomical or structural inaccuracies in AI-generated outputs without compromising the original composition.

Implementation:

Developed localized inpainting workflows using VAE Encode nodes to mask and target specific problem areas.
Utilized seed-locking to maintain baseline lighting and composition while iterating on prompt refinements.
Integrated targeted LoRA loading for specific anatomical corrections and lighting adjustments.
Prompt Engineering: Managed prompt weighting (typically 1.1–1.3) to minimize artifacts and latent-space degradation, using precise mask conditioning and CFG tuning for localized corrections.
Before & After Comparison

<p align="center">
<strong>Before — Anatomical Inconsistency</strong>
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/552ad0fd-810d-45dd-83ad-e27e10c174d7" alt="Before SDXL Inpainting - Anatomical Inconsistency" width="80%">
</p>

<p align="center">
<strong>After — Corrected Using Targeted Inpainting</strong>
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/26f2302b-1098-4a08-bb30-c8357a1a4f4d" alt="After SDXL Inpainting - Corrected Hand Positioning and Pen Replacement" width="80%">
</p>

Result: Corrected anatomical inconsistencies in hand positioning through targeted inpainting while preserving the original composition and lighting, including replacing the original object with a pen.

SDXL Inpainting Workflow

<p align="center">
<img src="https://github.com/user-attachments/assets/ab29fcb3-1820-480b-b562-b9e8226c0847" alt="SDXL Inpainting Workflow" width="100%">
</p>

Core Competencies Demonstrated
Workflow Optimization: Translating creative briefs into precise, reproducible node graphs.
Hardware Efficiency: Adapting resource-intensive models for local execution through GGUF quantization.
Quality Control: Systematic identification of AI-generated inaccuracies and implementation of prompt- and node-based corrections.
Prompt Engineering: Fine-tuning prompt weights, CFG, sampler settings, and conditioning for consistent outputs.
Iterative Refinement: Preserving composition while applying localized corrections through controlled inpainting.
