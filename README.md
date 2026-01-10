# Multimodal-Brain-Age
This project implements a **PyTorch-based multimodal deep learning model** to predict brain age from **3D MRI scans** and **genetic SNP data**.  

⚠️ **Work in Progress** – still under development.



## Features

- Pretraining with **MSE loss**, fine-tuning with **MSE + contrastive loss**  
- Handles **3D MRI volumes** (128×128×128) and **1D SNPs**  
- Saves **model checkpoints** and **training history figures** automatically  



## Data

- **MRI data**: NumPy array `(num_samples, 128,128,128)`  
- **SNP data**: NumPy array `(num_samples, num_snps)`  
- **Age labels**: NumPy array `(num_samples,)`  



## Usage

1. Set paths in `main_train.py`:
```python
brains_file = "/path/to/mri_data.npy"
cas_file = "/path/to/age_labels.npy"
snps_file = "/path/to/snp_data.npy"
save_loc = "/path/to/save/"
```
3. Adjust hyperparameters in main_train.py if needed
```python
epochs = 500           # total number of training epochs
pretrain_epochs = 30   # number of pretraining epochs (MSE only)
batch_size = 16        # number of samples per batch
lr = 1e-3              # learning rate
```
4. Run training
-Pretraining runs first (MSE only)
-Fine-tuning follows (MSE + contrastive loss)
```python
python main_train.py
```
