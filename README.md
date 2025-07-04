# Sketch-Generation-via-Diffusion-Models-using-Sequential-Strokes

This project implements a multi-class sketch generation and evaluation pipeline using a Transformer-based model. It supports training, testing, and evaluation (including FID/KID metrics and sketch feature comparison) for multiple sketch classes (e.g., cat, rabbit, bus, etc.).

### ✨ Key Features
Multi-Class Generation: Train separate models for distinct sketch categories.

Transformer-Based Architecture: Leverages the power of Transformers for sequential stroke generation.

Comprehensive Evaluation: Includes FID/KID metrics for quantitative assessment and detailed sketch feature comparison for qualitative analysis.

Real-time Training Monitoring: Utilize TensorBoard for live visualization of training progress and metrics.

Animated GIF Outputs: Automatically generates step-by-step animated GIFs of sample sketches, showcasing the generation process.



## Project Structure

├── data/                   # Raw sketch data in .ndjson format (per class)   
├── subset/                 # JSON files with train/val/test indices (per class)    
├── checkpoints/            # Model checkpoints (per class)    
├── Technical_Assignment.ipynb  # Main notebook    
├── requirements.txt        # Python dependencies     
└── README.md               # This file      

### Setup & Installation

Install dependencies:

```bash
   pip install -r requirements.txt
```


#### (Optional) Setup GPU:

Make sure you have CUDA and PyTorch with GPU support installed for faster training and evaluation.

### Data Preparation

Place your `.ndjson` sketch data files in the `data/` directory, one file per class (e.g., cat.ndjson, dog.ndjson).
Place your index files (with train/val/test splits) in the subset/ directory, one JSON per class (e.g., cat/indices.json).

### Training

The notebook is designed to train a separate model for each class in `DATA_CLASSES`.

For each class:
The model is initialized and trained from scratch.
Checkpoints are saved in `checkpoints/<class_name>/.`



The training loop in this project logs metrics (loss, accuracy, F1, etc.) using TensorBoard.
You can monitor your model’s training progress in real time.

```bash
   tensorboard --logdir runs
```

Open your browser and go to http://localhost:6006 to view the training curves and metrics.


### Animated GIFs of Generated Sketches
After evaluation, the project will generate and save animated GIFs of sample sketches produced by your trained models.
These GIFs visually demonstrate how the model draws a sketch step by step.
