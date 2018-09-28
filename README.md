# FusionNet for Natural Language Inference

This is an example for applying FusionNet to natural language inference task.  
For more details on FusionNet, please refer to Huang et al. paper:  
[FusionNet: Fusing via Fully-Aware Attention with Application to Machine Comprehension](https://arxiv.org/abs/1711.07341)  


Three ways have been provided to run this program: (each is explained seperetly.)
1. Using the codes directly from GitHub repository.
2. Using Docker container.
3. Using Singularity Hub for HPC systems.

### 1. GitHub Clone:

For this method the following packages should be installed:
+ Python (version 3.5.2)
+ PyTorch (0.2.0)
+ spaCy (1.x)
+ NumPy
+ JSON Lines
+ MessagePack

```
git clone https://github.com/sinaehsani6/csc585rep.git
```
Then use the Quick Start to run the program.

### 2. Docker Container:

For the docker container, we used the container uploaded by the authors themself:

If you don't have docker containers, you can download the docker containers from [here](https://www.docker.com/community-edition#/download). 
To enable GPU, [nvidia-docker](https://github.com/NVIDIA/nvidia-docker) may also needs to be installed.  

`docker pull momohuang/fusionnet-docker` to pull the docker file.
`docker run -it momohuang/fusionnet-docker` (Only CPU)  
or  
`nvidia-docker run -it momohuang/fusionnet-docker` (GPU-enabled).  
Then use the Quick Start to run the program.



### 3. Singularity Hub:
For a easier run on HPC systems (HPC systems do not support docker containers), a singularity hub is stablished for an easier use, to run the singularity hub, use the following codes:

```
singularity pull shub://sinaehsani6/FusionNet-NLI
singularity shell FusionNet-NLI
```
 
Then use the Quick Start to run the program.

Quick Start
-----------
`pip install -r requirements.txt`  
`bash download.sh`  
`python prepro.py`  
`python train.py`  
  
`train.py` supports an option `--full_att_type`, where  
`--full_att_type 0`: standard attention  
`--full_att_type 1`: fully-aware attention  
`--full_att_type 2`: fully-aware multi-level attention  
