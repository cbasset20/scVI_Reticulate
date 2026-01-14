# scVI_Reticulate
Running [integration](https://satijalab.org/seurat/articles/integration_introduction) on a Seurat object in R using scVI tools via Reticulate package. 
# Installation
Python (this will install scvi-tools version > 1.0.0)
```bash
conda create -n scvi-env python=3.12
conda activate scvi-env

#install Pytorch to take advantage of accelerated GPU
#Only install this version of pytorch to enable GPU acceleration
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu124 

#(optional) install pytorch for CPU only
#pip3 install torch torchvision torchaudio
#pytorch will install all the numpy scanpy packages that you need. no need to reinstall them.

#Only install this version of Jax to enable GPU acceleration
pip install -U "jax[cuda12]"
#otherwise install it for CPU
#pip install -U jax

pip install -U scvi-tools
pip install -U scvi-tools[tutorials]
pip install -U scvi-tools[optional]
pip install -U scvi-tools[dev]

conda install -c conda-forge r-base r-essentials r-reticulate
```


R
```bash
install.packages('remotes')
install.packages("R.utils")
install.packages("BiocManager")
BiocManager::install("vjcitn/scviR")
install.packages(reticulate)
#this version of seurat wrappers is crucial. IntegrateLayers() function will not work if you install any other version
remotes::install_github(repo="satijalab/seurat-wrappers", ref = remotes::github_pull(184))
```
