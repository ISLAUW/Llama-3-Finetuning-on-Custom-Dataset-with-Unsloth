# Llama-3-Finetuning-on-Custom-Dataset-with-Unsloth

## 1. Environment and Library Setup
- Installs and imports necessary libraries (Unsloth, torch, Huggingface Transformers, bitsandbytes, etc.).
- Detects GPU capability and optimizes installations for your hardware.

## 2. Model Loading
- Loads the 4-bit quantized Llama-3 8B model using Unsloth’s FastLanguageModel.
  - This is efficient and suitable for consumer GPUs.
  - Loads tokenizer settings as well.

## 3. LoRA Adapter Integration
- Adds LoRA (Low-Rank Adaptation) adapters to the model.
  - Only a small percentage of model parameters are updated during training, which saves memory and speeds up training.

## 4. Prompt Formatting
- Defines an Alpaca-style prompt template.

## 5. Dataset Loading and Preprocessing
- Loads the 'yahma/alpaca-cleaned' dataset from Huggingface.
- Applies the formatting function to create prompt/response pairs for fine-tuning.
## 6. Training Setup
- Uses Huggingface TRL’s SFTTrainer for supervised fine-tuning.
- Sets training parameters (batch size, steps, learning rate, logging, etc.).
- Sets a low number of steps for demo purposes, but this can be increased for real training.
## 7. Training
- Starts the training loop, generates and prints runtime/memory usage statistics.
## 8. Inference (Generating Text)
- Switches the model to inference mode.
- Prepares a sample prompt (e.g., for continuing a Fibonacci sequence).
- Generates output tokens from the fine-tuned model.
- Decodes the output for readability.
## 9. Saving and Reloading
- Provides code to save the LoRA adapter(s) and, optionally, the entire model in several formats.
