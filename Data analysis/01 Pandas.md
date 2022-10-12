<div align=center><img src=https://pandas.pydata.org/static/img/pandas.svg height=139.2 weight=344.5></div>

## Introduction
A powerful tool set that based on Numpy for analyzing structured data.

Offcial documents: https://pandas.pydata.org/pandas-docs/stable   
Chinese(中文网): https://www.pypandas.cn/docs

## Example
In Pycharm, should add the “ plt.show() ” statement at the end of the drawing code.

```Python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

t = np.arange(0.0, 2.0, 0.01)
s = np.sin(2*np.pi*t)
fig, ax = plt.subplots()
ax.plot(t, s)
plt.show ()

```
<img src="https://github.com/Cafwell/Learning-Python/blob/main/imgs/Data%20Analysis/Figure_1.png" width="400">

