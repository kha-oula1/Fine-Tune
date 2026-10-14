<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Fine-Tune an SLM for IoT with QLoRA

**Project Link:** [View Project](https://nextwork.ai/projects/183d6ee4-2ad1-470c-aeb2-362886f90497)

**Author:** Khaoula Belhadj  
**Email:** belhadjkhaoula07@gmail.com

---

![Image](https://nextwork.ai/courageous_silver_serene_goblin/uploads/183d6ee4-2ad1-470c-aeb2-362886f90497_nmdvs16p)

## Project Vision: Fine-Tuning a Domain Expert Model

### What this project set out to achieve

In this project, Fine-tune Gemma 3 1B into an IoT expert using QLoRA on a free Colab GPU.





## Setting Up the GPU Environment

### Environment and tooling goals

In this step :
Create a Hugging Face account and generate a write access token.
Open a Google Colab notebook and connect to a T4 GPU.
Install Unsloth and authenticate with Hugging Face

![Image](https://nextwork.ai/courageous_silver_serene_goblin/uploads/183d6ee4-2ad1-470c-aeb2-362886f90497_3kdsquob)

### Confirming Unsloth installation

The version number of the Unsloth installation shown in the output of the verification cell is 2026.10.5.

## Exposing the Base Model's IoT Blind Spots

### Why testing the base model first matters

In this step :
Load Gemma 3 1B in 4-bit quantization on the free T4 GPU.
Test the base model with three IoT questions.
Save the base responses for comparison after fine-tuning.

![Image](https://nextwork.ai/courageous_silver_serene_goblin/uploads/183d6ee4-2ad1-470c-aeb2-362886f90497_f6euyy6r)

### Identifying missing technical depth

Let's analyze Response 3: "Explain how to integrate a DHT22 temperature sensor with Home Assistant using ESPHome."

If a domain expert looked at this output, they would identify several critical inaccuracies, hallucinations, and missing configuration details:

1. Inaccurate Installation Procedures (Hallucinations)
The Model's Output: Tells the user to install ESPHome using a curl pipe command: curl -s https://raw.github.com/... | ESPHome.
Expert Critique: This is highly incorrect and dangerous command-line advice. ESPHome is written in Python and is typically installed using pip install esphome, run as a Docker container, or installed directly as a Home Assistant Add-on with a single click in the UI.

## Loading and Formatting the IoT Training Dataset

### Dataset preparation goals

In this step ; 
Load the Mascarade IoT dataset from Hugging Face Hub.
Format conversations from ShareGPT style into the tokenizer's chat template.

![Image](https://nextwork.ai/courageous_silver_serene_goblin/uploads/183d6ee4-2ad1-470c-aeb2-362886f90497_t6za7vg6)

### Understanding ShareGPT role mapping

ShareGPT role names need to be mapped before training for several critical reasons:

Chat Template Compatibility and Consistency with Pre-training.

## Fine-Tuning with QLoRA on a Free GPU

### Configuring LoRA adapters and training

In this step :
Attach LoRA adapters to the model's attention and MLP layers.
Run supervised fine-tuning for 60 training steps and watch the loss decrease.

![Image](https://nextwork.ai/courageous_silver_serene_goblin/uploads/183d6ee4-2ad1-470c-aeb2-362886f90497_tlwfokll)

### Interpreting the training loss curve

During the 60 steps of fine-tuning, you will typically observe that the training loss steadily decreased (for example, starting from an initial loss around 2.0 to 2.5 and dropping down toward 1.0 to 1.2 or lower by the final step).
Decreasing Loss Matters because convergence and learning and better code quality and accuracy.

## Before vs. After: Publishing a Domain Specialist to Hugging Face Hub

### Comparing and publishing the fine-tuned model

In this step :
Compare fine-tuned model responses with the base model's original answers.
Publish your trained LoRA adapter to Hugging Face Hub.

![Image](https://nextwork.ai/courageous_silver_serene_goblin/uploads/183d6ee4-2ad1-470c-aeb2-362886f90497_nmdvs16p)

![Image](https://nextwork.ai/courageous_silver_serene_goblin/uploads/183d6ee4-2ad1-470c-aeb2-362886f90497_cquefb7x)

## Secret Mission: Exporting to GGUF for Local Inference with Ollama

![Image](https://nextwork.ai/courageous_silver_serene_goblin/uploads/183d6ee4-2ad1-470c-aeb2-362886f90497_utl5b7xo)

### LoRA adapter vs. GGUF: understanding the difference

In this project extension, The main difference is that a LoRA adapter contains the fine-tuning changes, while a GGUF file contains a model exported into a format optimized for inference.

## Reflections and Key Takeaways

### Tools and concepts mastered

The key tools :
google colab
hugging face 
ollama


### Time and challenges

This project took me approximately 30 min

### Looking ahead

<3 :!!!!

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/183d6ee4-2ad1-470c-aeb2-362886f90497)*
