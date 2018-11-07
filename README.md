# Pytorch-segmentation-toolbox
Pytorch code for semantic segmentation. This is a minimal code to run PSPnet and Deeplabv3 on Cityscape dataset.
Shortly afterwards, the code will be reviewed and organized for convenience.

### Highlights of Our Implementations
- Synchronous BN
- Fewness of Training Time
- Better Reproduced Performance

### Requirements

To install PyTorch>=0.4.0, please refer to https://github.com/pytorch/pytorch#installation.

### Compiling

Some parts of InPlace-ABN have a native CUDA implementation, which must be compiled with the following commands:
```bash
cd libs
sh build.sh
python build.py
``` 
The `build.sh` script assumes that the `nvcc` compiler is available in the current system search path.
The CUDA kernels are compiled for `sm_50`, `sm_52` and `sm_61` by default.
To change this (_e.g._ if you are using a Kepler GPU), please edit the `CUDA_GENCODE` variable in `build.sh`.

### Dataset and pretrained model

Plesae download cityscapes dataset and unzip the dataset into `YOUR_CS_PATH`.

Please download MIT imagenet pretrained [resnet101-imagenet.pth](http://sceneparsing.csail.mit.edu/model/pretrained_resnet/resnet101-imagenet.pth), and put it into `dataset` folder.

### Training and Evaluation
```bash
./job_local.sh YOUR_CS_PATH
``` 

### Benefits
Some  recent  projects  have  already  benefited  from  ourimplementations.   For  example,  [Object  Context  Network(OCNet)](https://github.com/PkuRainBow/OCNet) currently  achieves  the  state-of-the-art  resultson  Cityscapes  and  ADE20K.  In  addition,  our  code  alsomake great contributions to [Context Embedding with EdgePerceiving (CE2P)](https://github.com/liutinglt/CE2P), which won the 1st places in all hu-man parsing tracks in the 2nd LIP Challange.

### Thanks to the Third Party Libs
[inplace_abn](https://github.com/mapillary/inplace_abn)
[Pytorch-Deeplab](https://github.com/speedinghzl/Pytorch-Deeplab)
[PyTorch-Encoding](https://github.com/zhanghang1989/PyTorch-Encoding)
