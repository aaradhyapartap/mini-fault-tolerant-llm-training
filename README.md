# Mini Fault-Tolerant LLM Training Prototype

A small-scale prototype that demonstrates the core building blocks of scalable and fault-tolerant training for large language models. This project was implemented in Google Colab using PyTorch, Hugging Face Transformers, and the WikiText-2 dataset.

## Project Overview

Large language models require distributed systems because they are computationally expensive, memory-intensive, and vulnerable to long training interruptions. While full distributed multi-GPU training was not implemented in this prototype, this project demonstrates the essential components used inside such systems:

- data loading and preprocessing
- tokenizer-based text encoding
- transformer model training
- checkpoint-based fault tolerance
- recovery and resume training
- performance measurement
- text generation after training

This project serves as a small-scale prototype of the logic used in distributed LLM training systems.

## Objective

The goal of this project is to build a beginner-friendly prototype that demonstrates how language model training works and how checkpoint-based recovery can prevent loss of progress when failures occur. The project also connects these implementation details to larger distributed computing ideas such as scalability, parallelism, and system reliability.

## How this relates to distributed computing

This project is related to distributed computing because it implements the fundamental building blocks that are used in large-scale distributed training systems for language models. Specifically, it includes:

- data processing and batching
- iterative model training
- checkpoint saving during execution
- recovery from interruption
- throughput and step-time measurement

In a real distributed system, multiple GPUs or nodes would execute similar training pipelines in parallel and communicate using synchronization mechanisms such as all-reduce. This project demonstrates the same core ideas on a smaller single-GPU scale.

## Workflow

```text
Dataset → Tokenizer → DataLoader → Model (DistilGPT2)
           ↓
       Training Loop
           ↓
   Checkpoint Saving
           ↓
   Failure Simulation
           ↓
   Recovery & Resume
           ↓
 Performance Measurement
           ↓
     Text Generation
