# Vanilla-GAN

PyTorch implementation of [Generative Adversarial Networks](https://arxiv.org/abs/1406.2661) by Ian Goodfellow et al. on the MNIST dataset.

<div align='center'>
   <img src="img/progress.gif" alt="progress" align='center' width='300'/>
</div>

### GAN Loss and training
The training of the generator and discriminator networks is based on the following MiniMax game played between the two.

<div align='center'>
   <img src="img/minmax.png" alt="minimax" align='center' width='600'/>
</div>


Binary Cross Entropy loss was used to train both generator and discriminator. Generator was trained my maximising discriminators probability of being real on fake data instead of other way round, because as mentioned in the paper, it provides stronger gradients early.

<div align='center'>
   <img src="img/loss (1).png" alt="loss_curve" align='center' width="500"/>
</div>

### Model

The generator model file is available. Load it like this
```python
import torch

...

model = Generator()
state = torch.load('mnist_generator.pth')
model.load_state_dict(state)
model.eval()

...
```


### References
1. **Ian Goodfellow, et al.** *Generative Adversarial Networks.* NIPS 2014 [[arxiv](https://arxiv.org/abs/1406.2661)]
