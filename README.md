# Generative AI Workflow Optimization & Prompt Engineering

This repository documents optimized, node-based workflows for local Generative AI image generation, developed to streamline creative iteration and resolve hardware bottlenecks. 

## 1. Z Image GGUF Quantization Pipeline
**Objective:** Maximize inference speed and reduce VRAM overhead for rapid T2I (Text-to-Image) experimentation on consumer hardware.
**Implementation:**
- Reverse-engineered and modified complex community workflows to consolidate inputs and streamline the node graph.
- Integrated GGUF quantized model loaders (Q8) to bypass standard bf16 VRAM limitations, preventing hardware throttling and drastically reducing generation times.
- Maintained strict prompt adherence and visual fidelity by calibrating sampler settings to compensate for quantization trade-offs.

## 2. SDXL Inpainting & Iterative Refinement
**Objective:** Identify and correct anatomical or structural inaccuracies in AI-generated outputs without destroying the base composition.
**Implementation:**
- Developed localized inpainting workflows using VAE Encode nodes to mask and target specific flaw areas.
- Utilized seed-locking to maintain baseline lighting and composition while iterating on prompt refinements.
- Integrated targeted LoRA loading for specific anatomical corrections and lighting adjustments.
- **Prompt Engineering:** Strictly managed prompt weighting (capped at 1.1 - 1.3) to prevent latent space degradation and artifacting, relying on precise mask conditioning and CFG tuning for corrections.

## Core Competencies Demonstrated
- **Workflow Optimization:** Translating creative briefs into precise, reproducible node graphs.
- **Hardware Efficiency:** Adapting high-resource models for local execution via quantization.
- **Quality Control:** Systematic identification of AI inaccuracies and implementation of prompt/node-based corrections.
