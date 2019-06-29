# Vanilla-GAN

PyTorch implementation of [Generative Adversarial Networks](https://arxiv.org/abs/1406.2661) by Ian Goodfellow et al.

### Loss

Binary Cross Entropy loss was used to train both generator and discriminator. Generator was trained my maximising discriminators probability of being real on fake data instead of other way round, because as mentioned in the paper, it provides stronger gradients early.
<div align='center'>
   <img src="img/loss (1).png" alt="loss_curve" align='center' width="400"/>
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

