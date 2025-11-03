# polygonhgt--cuspatial-fix
Fixed and updated version of polygon-HGT for CUDA 11.7, RAPIDS 23.04 (cuSpatial 23.04.00, py38), and PyTorch 1.13 compatibility.






## License and Attribution
This project is based on [polygon-HGT](https://github.com/DavidGillsjo/polygon-HGT)  
by **David Gillsjö (2023)**, distributed under the **MIT License**.

Modifications by **Minji Kim (2025)** for:
- CUDA 11.7 and RAPIDS 23.04 compatibility  
- Updated cuSpatial API and PyTorch dependencies  


# Polygon-HGT with cuSpatial (Docker Setup)

This guide explains how to build and run the **Polygon-HGT** project with **cuSpatial** support inside a Docker container.


## 🚀 1. Run Docker Container

Run the container with GPU access and mounted host directories:

```bash
docker run --gpus all -it \
  --user root \
  -v /usr/local/cuda:/usr/local/cuda:ro \
  -v ~:/host_home \
  -p 8011:8888 \
  polygon_hgt_cuspatial:latest bash

```
## 🚀 2. Set CUDA Environment Variables

After entering the container, set up the CUDA environment variables to ensure that CUDA and NVCC are correctly recognized.
```bash
export WANDB_DISABLED=true
export WANDB_MODE=offline
export CUDA_HOME=/usr/local/cuda
export CUDACXX=$CUDA_HOME/bin/nvcc
export PATH=$CUDA_HOME/bin:$PATH
export LD_LIBRARY_PATH=$CUDA_HOME/lib64:$LD_LIBRARY_PATH
```
## ⚙️ 3. CUDA 

Driver Version: 535.183.01
CUDA Version: 12.2
GPU: NVIDIA GeForce RTX 3060 (12GB)

nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2022 NVIDIA Corporation
Built on Wed_Jun__8_16:49:14_PDT_2022
Cuda compilation tools, release 11.7, V11.7.99
Build cuda_11.7.r11.7/compiler.31442593_0


## 📚 Citation
If you use this work, please cite the original Polygon-HGT repository:
howpublished = {\url{[https://github.com/DavidGillsjo/polygon-HGT](https://github.com/DavidGillsjo/polygon-HGT)}}
