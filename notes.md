# Notes

## Backdooring
- In `random_training smooth.ipynb`, I created a training procedure for a neural network that approximates a some random neural network. I then added a backdoor to the training procedure that would allow me to observe unexpected (large) output when supplied with an input in a very specific range. This is a simple example of a backdoor attack.

## Detecting Backdoors
- The goal should be to train a neural network that is able to consistently differentiate between a random neural network, and one with a backdoor. This should be fairly simple to do with our constrained, toy example.
  - First, I would need to create a program to generate random neural networks.
  - Then, I would need to create a program to generate a backdoored version of a neural network.
  - To make sure both are working well, I would also need to create some kind of benchmark to determine whether or the backdoor is a 'good' backdoor with a basic L2 norm or something.
  - To make my life easier later, I would also need to create some kind of library that allows me to probe neural networks to extract their activations.
  - Finally, I would need to create a databse of random and backdoored neural networks, and train a neural network to differentiate between the two.
- Ideas to differentiate between the two:
  - According to `random_training smooth.ipynb`, it could be useful to look at the distribution of activations in certain layer only given safe inputs. Visually, I feel like I can differentiate them, maybe an nn can do the same?
