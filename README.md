<div align="center">
<h1>StreamPETR</h1>
<h3>Exploring Object-Centric Temporal Modeling for Efficient Multi-View 3D Object Detection</h3>
</div>

    
## Catalog

- [ ] StreamPETR code
- [ ] PETR code
- [ ] Focal-PETR code
- [ ] Flash Attention
- [ ] Batch size 2 training for temporal models
- [ ] Efficient training in streaming video
- [ ] Checkpoints
  
<!-- ## Introduction -->
This repository is an official implementation of StreamPETR.
## Main Results
We provide some results on nuScenes **val set** with pretrained models. These model are trained on 8x 2080ti **without cbgs**.
StreamPETR:
| config            | mAP      | NDS     |FPS-Pytorch    |   config |   download |
|:--------:|:----------:|:---------:|:--------:|:--------:|:-------------:|
| StreamPETR-R50-704x256   | 45.0%     | 55.0%    | 31.7  | |  
  
