age groups

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

np.random.seed(42)
probabilities = [0.0361] * 21 + [0.057] * 44 + [0.0069] * 36
probabilities[-1] += 1 - sum(probabilities)  # Adjust the last probability to sum to 1

import numpy as np

np.random.seed(42)
probabilities = [0.0361] * 21 + [0.057] * 44 + [0.0069] * 36
probabilities[-1] += 1 - sum(probabilities)  # Adjust the last probability to sum to 1

# Ensure all probabilities are non-negative and sum to 1
probabilities = np.clip(probabilities, 0, 1)
probabilities /= np.sum(probabilities)

ages = np.random.choice(
    range(0, 101),
    size=100000,
    p=probabilities
)

data = pd.DataFrame({'Age': ages})data = pd.DataFrame({'Age': ages})

age_groups = [(0, 20, 'yellow', '0 to 20 Years\n512 Mn\n36.1%'),
              (21, 64, 'blue', '21 to 64 Years\n807 Mn\n57.0%'),
              (65, 100, 'magenta', '65+ Years\n98 Mn\n6.9%')]
