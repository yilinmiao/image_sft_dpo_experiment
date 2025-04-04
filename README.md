# SFT and DPO Training for High-Quality Image Enhancement

This project implements a system for transforming high-quality photos into premium advertisement cover images using pre-trained foundation models with Supervised Fine-Tuning (SFT) and Direct Preference Optimization (DPO).

## Overview

The system uses deep learning techniques to transform already high-quality photos into even more appealing advertising images by:
1. Leveraging pre-trained foundation models for faster training
2. Applying SFT for initial image enhancement
3. Using DPO for preference-based refinement
4. Comparing different training approaches to identify optimal results

## Key Features

- **Fast Training Pipeline**: Optimized for speed while maintaining quality
- **Foundation Model Approach**: Uses pre-trained ResNet50 as the base model
- **Three-Way Comparison**: Evaluates SFT-only, DPO-only, and combined SFT+DPO approaches
- **Objective Metrics**: Measures performance using PSNR and SSIM

## Project Structure

- `dataset/`: Directory structure for training data:
  - `input/`: Original high-quality images
  - `target/`: Premium advertisement target images
  - `preferred/`: Images considered better by human evaluators
  - `dispreferred/`: Images considered worse by human evaluators
- `models/`: Directory for saving trained model weights
- `results/`: Directory for saving generated images and comparisons

## Training Pipeline

### Phase 1: SFT Training
- Fine-tunes a pre-trained ResNet50 model using supervised learning
- Uses perceptual and L1 losses for optimal image quality
- Includes learning rate scheduling and optimization techniques for faster training

### Phase 2: DPO Training
- Implements the Direct Preference Optimization approach from the paper "Direct Preference Optimization: Your Language Models are Secretly Reward Models" (arXiv:2305.18215)
- Uses human preference data to further refine the model
- Optimizes for speed with techniques like gradient clipping and weight decay

### Phase 3: Evaluation
- Compares three model variants:
  1. Foundation model with SFT only
  2. Foundation model with DPO only
  3. Foundation model with both SFT and DPO training
- Produces clearly labeled output images for each approach

## Performance Considerations

- The pipeline is optimized for fast training on Google Colab
- Uses techniques like:
  - Pre-trained foundation models instead of training from scratch
  - Efficient batch sizes and multi-worker data loading
  - Learning rate scheduling and AdamW optimization
  - Gradient clipping for stability
  - Time tracking to measure performance improvements

## References

1. "Direct Preference Optimization: Your Language Models are Secretly Reward Models" (arXiv:2305.18215)
2. "Training language models to follow instructions with human feedback" (arXiv:2203.02155) 
