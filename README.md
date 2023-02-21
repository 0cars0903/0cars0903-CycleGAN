# CycleGAN
## GAN
* 실제 데이터의 분포(데이터의 형태, 분산)를 학습하여 유사한 데이터를 생성하는 모델입니다.
* 픽셀들의 분포에 따라 이미지의 특징을 인식 명암이나 사진의 전체적인 채도와는 큰 상관이 없습니다.
* Generator란?
* Discriminator란?
* cross-entropy 개념
## CycleGAN
* GAN와의 차이점?
* pix2pix에서 발전한 사항?
-----------
## Pretrain Model
이번 모델의 Generator와 Discriminator는 Pix2Pix 모델을 기본으로 제작되었습니다.
## Training
### 1. Setup the dataset

dataset 구조는 다음과 같이 정의하였습니다.:

    .
    ├── datasets                   
    |   ├── <dataset_name>         # i.e. apple2orange, horse2zebra
    |   |   ├── train              # Training
    |   |   |   ├── A              # Contains domain A images (i.e. apple)
    |   |   |   └── B              # Contains domain B images (i.e. orange)
    |   |   └── test               # Testing
    |   |   |   ├── A              # Contains domain A images (i.e. orange)
    |   |   |   └── B              # Contains domain B images (i.e. Batman)
    
### 2. Train!
* epoch : 100
* Loss 결과입니다.

![Generator loss](https://github.com/ai-tor/PyTorch-CycleGAN/raw/master/output/loss_G.png)
![Discriminator loss](https://github.com/ai-tor/PyTorch-CycleGAN/raw/master/output/loss_D.png)
![Generator GAN loss](https://github.com/ai-tor/PyTorch-CycleGAN/raw/master/output/loss_G_GAN.png)
![Generator identity loss](https://github.com/ai-tor/PyTorch-CycleGAN/raw/master/output/loss_G_identity.png)
![Generator cycle loss](https://github.com/ai-tor/PyTorch-CycleGAN/raw/master/output/loss_G_cycle.png)

## Testing

말 사진을 얼룩말 사진으로 바꾸어 본 결과입니다.

![Real horse](https://github.com/ai-tor/PyTorch-CycleGAN/raw/master/output/real_A.jpg)
![Fake zebra](https://github.com/ai-tor/PyTorch-CycleGAN/raw/master/output/fake_B.png)
![Real zebra](https://github.com/ai-tor/PyTorch-CycleGAN/raw/master/output/real_B.jpg)
![Fake horse](https://github.com/ai-tor/PyTorch-CycleGAN/raw/master/output/fake_A.png)
