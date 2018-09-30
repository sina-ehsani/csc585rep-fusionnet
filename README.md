# FusionNet for Natural Language Inference

This is an example for applying FusionNet to natural language inference task.  
For more details on FusionNet, please refer to Huang et al. paper:  
[FusionNet: Fusing via Fully-Aware Attention with Application to Machine Comprehension](https://arxiv.org/abs/1711.07341)  


Three ways have been provided to run this program: (each is explained separatley.)
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

If you wan't to use the docker containers, you can download the docker containers from [here](https://www.docker.com/community-edition#/download). 
To enable GPU, [nvidia-docker](https://github.com/NVIDIA/nvidia-docker) may also need to be installed.  

`docker pull sinaehsani/sinafusionnet2` to pull the docker file.
`docker run -it sinaehsani/sinafusionnet2` (Only CPU)  
or  
`nvidia-docker run -it sinaehsani/sinafusionnet2` (GPU-enabled).  
Then use the Quick Start to run the program. (if using this method there is no need for the `pip install -r requirements.txt`) 



### 3. Singularity Hub:
For an easier run on HPC systems (HPC systems do not support Docker containers), a singularity hub is established for an easier use, to run the singularity hub, use the following codes:

```
singularity pull shub://sinaehsani6/FusionNet-NLI
singularity shell FusionNet-NLI
```


Or you can pull the docker image within the singularity (if using this method there is no need for the `pip install -r requirements.txt`) use the following codes to pull the docker container on an HPC environment:
```
singularity pull docker://sinaehsani/sinafusionnet2
singularity shell sinafusionnet2
```
Then use the Quick Start to run the program.

Quick Start
-----------
```
pip install -r requirements.txt
bash download.sh  
python prepro.py 
python train.py
```  
  
`train.py` supports an option `--full_att_type`, where  
`--full_att_type 0`: standard attention  
`--full_att_type 1`: fully-aware attention  
`--full_att_type 2`: fully-aware multi-level attention  
