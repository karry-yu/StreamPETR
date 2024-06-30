# Environment Setup

## Base Environments  
Python >= 3.8 \
CUDA == 11.2 \
PyTorch == 1.9.0 \
mmdet3d == 1.0.0rc6 \
[flash-attn](https://github.com/HazyResearch/flash-attention) == 0.2.2

**Notes**: 
- [flash-attn](https://github.com/HazyResearch/flash-attention) is an optional requirement, which can speedup and save GPU memory. If your device (e.g. TESLA V100) is not compatible with the flash-attn, you can skip its installation and comment the relevant [code](../projects/mmdet3d_plugin/models/utils).
- It is also possible to consider installing version 1.9.0 + of Pytorch, but you need to find the appropriate flash-attn version (e.g. 0.2.8 for CUDA 11.6 and pytorch 1.13).


## Step-by-step installation instructions

Following https://mmdetection3d.readthedocs.io/en/latest/getting_started.html#installation


**a. Create a conda virtual environment and activate it.**
```shell
conda create -n streampetr python=3.8 -y
conda activate streampetr
```

**b. Install PyTorch and torchvision following the [official instructions](https://pytorch.org/).**
```shell
pip install torch==1.9.0+cu111 torchvision==0.10.0+cu111 torchaudio==0.9.0 -f https://download.pytorch.org/whl/torch_stable.html
# Recommended torch>=1.9
```
**c. Install flash-attn (optional).**
```
pip install flash-attn==0.2.2
```

**d. Clone StreamPETR.**
```
git clone https://github.com/exiawsh/StreamPETR
```

**e. Install mmdet3d.**
```shell
pip install mmcv-full==1.6.0 -f https://download.openmmlab.com/mmcv/dist/cu111/torch1.9.0/index.html
pip install mmdet==2.28.2
pip install mmsegmentation==0.30.0
cd ./StreamPETR
git clone https://github.com/open-mmlab/mmdetection3d.git
cd mmdetection3d
git checkout v1.0.0rc6 
pip install -e .
```

**f. For my env**

```shell
# for numba==0.53.0 https://github.com/open-mmlab/mmdetection3d/pull/2416
pip install "numpy<1.24.0"
# https://github.com/open-mmlab/mmdetection/issues/10962
pip install yapf==0.40.1
pip install torch==1.13.1+cu116 torchvision==0.14.1+cu116 --extra-index-url https://download.pytorch.org/whl/cu116

pip install "mmcv-full>=1.5.2,<=1.7.0" -f https://download.openmmlab.com/mmcv/dist/cu116/torch1.13/index.html
pip install mmdet==2.28.2
pip install mmsegmentation==0.30.0
pip install mmdet3d==1.0.0rc6

pip install einops
# flash-att does not support v100, but I installed it anyway to minimize code changes.
wget https://github.com/Dao-AILab/flash-attention/releases/download/v2.3.5/flash_attn-2.3.5+cu116torch1.13cxx11abiFALSE-cp38-cp38-linux_x86_64.whl
pip install flash_attn-2.3.5+cu116torch1.13cxx11abiFALSE-cp38-cp38-linux_x86_64.whl
```
