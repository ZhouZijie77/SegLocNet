# Installation
**step 0.** Create a conda environment and activate it.
```bash
conda create -n seglocnet python=3.10
conda activate seglocnet
```

**step 1.**
Install PyTorch following [official instructions](https://pytorch.org/get-started/locally/).
```bash
conda install pytorch==2.1.2 torchvision==0.16.2  pytorch-cuda=11.8 -c pytorch -c nvidia
```
**step 2.** Install mmengine, mmcv, mmdet.
```bash
pip install -U openmim
mim install mmengine==0.10.5
mim install 'mmcv>=2.0.0rc4'
mim install 'mmdet>=3.0.0'
```
**step 3.** Install argoverse-api following the [instructions](https://github.com/argoverse/argoverse-api?tab=readme-ov-file#installation).
```bash
git clone https://github.com/argoai/argoverse-api.git
```
Download `hd_maps.tar.gz` from their [website](https://www.argoverse.org/av1.html#download-link) and extract into the root directory of the argoverse-api repo.

```bash
pip install -e ${path_to_root_directory_of_the_argoverse-api_repo}
```

**step 4.** Clone and install SegLocNet.
```bash
git clone https://github.com/ZhouZijie77/SegLocNet.git
cd SegLocNet
pip install -v -e .
python projects/SegLocNet/setup.py develop
```

**step 5.** Install other dependencies.
```bash
pip install utm==0.7.0 rtree==1.3.0 lxml==5.3.0
```
