title: NumPy: Exercises and Solutions
next_title: numpy
next_url: %url:numpy%


## Removing extreme values

### Exercise

%-- include: exercises/numerical/numpy-1.md --%


### Solution

```python
import numpy as np

a = np.random.random(1000)
m = np.mean(a)
sd = np.std(a)
print('Before removing extreme values:')
print('N = {}, M = {}, SD = {}'.format(len(a), m, sd))
new_a = a[(a > m - sd) & (a < m + sd)]
new_m = np.mean(new_a)
new_sd = np.std(new_a)
print('After removing extreme values:')
print('N = {}, M = {}, SD = {}'.format(len(new_a), new_m, new_sd))
```
