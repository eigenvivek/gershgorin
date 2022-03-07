# Gershgorin
Visualize the Gershgorin discs that bound the spectrum of a square matrix (see the [Gershgorin disc theorem](https://en.wikipedia.org/wiki/Gershgorin_circle_theorem)).

## Installation

```
python -m pip install gershgorin
```

## Usage
Visualize the Gershgorin discs for a random [Markov matrix](https://en.wikipedia.org/wiki/Stochastic_matrix) shows us that its eigenvalues are bounded within the complex unit circle, guaranteeing convergence of the Markov chain.

```python
import numpy as np
import matplotlib.pyplot as plt
from gershgorin import gershgorin

np.random.seed()

# Sample a random Markov matrix
n = 4
A = np.random.randint(0, 10, (n, n))
A = A / np.sum(A, axis=0)

# Plot the Gershgorin discs
ax = gershgorin(A, annotate=True)

# Add the complex unit circle
x = np.linspace(0, 2 * np.pi, 200)
ax.plot(np.cos(x), np.sin(x), "k--", linewidth=1)

plt.show()
```

![markov](https://user-images.githubusercontent.com/29757116/157113695-117246b1-5f82-46db-90a7-536850769a4d.png)
