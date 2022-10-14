## Pandas and Seaborn

### Pandas
Using in-built pandas plotting tools can do some simple drawing:

For example, drawing trigonometric functions
```Python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

t = np.arange(0.0, 2.0, 0.01)
s = np.sin(2*np.pi*t)
fig, ax = plt.subplots()
ax.plot(t, s)
plt.show ()  # Should add the “plt.show()” statement at the end of the drawing code.

```
<img src="https://github.com/Cafwell/Learning-Python/blob/main/imgs/Data%20Analysis/Figure_1.png" width="380">

Or just drawing a Line Graph
```Python
rain = pd.read_csv("https://milliams.com/courses/data_analysis_python/rain.csv")
rain.plot()
```
<img src="https://github.com/Cafwell/Learning-Python/blob/main/imgs/Data%20Analysis/Figure_2.png" width="380">

But to do more graphs, we will use Seaborn.

### Seaborn
seaborn is a third-party library which provides an easy-to-use interface for plotting tabular data which integrates with pandas really well.
Should import:
```Python
import seaborn as sns
import matplotlib.pyplot as plt
```

Use the official [built-in data](https://github.com/mwaskom/seaborn-data) as an example.
```Python
mpg=sns.load_dataset('mpg')  # import mpg.csv
mpg
```
<img src="https://github.com/Cafwell/Learning-Python/blob/main/imgs/Data%20Analysis/mpg.png" width="700">

#### Displot
```Python
m=sns.load_dataset('mpg')
w1=m['weight'].dropna()
sns.displot(w1, kde=True)
```
<img src="https://github.com/Cafwell/Learning-Python/blob/main/imgs/Data%20Analysis/Figure_3.png" width="380">

In this code, w1=m['weight'].dropna() is used to remove missing values (if there are) from 'weight' , caz distplot can not handle missing data；   
kde=True means show density curve (Does not display by default);

Another parameter - bins, can controls the number of distributed rectangles:
```Python
sns.displot(w1, bins=100, kde=True)
```
<img src="https://github.com/Cafwell/Learning-Python/blob/main/imgs/Data%20Analysis/Figure_4.png" width="380">


To refine the image, here are some more parameters:
```Python
sns.set(style="white", color_codes=True)
sns.displot(w1,rug=True, kde=True,
            bins=30,
            color='green',
            edgecolor='m',
            label='Hello'
            )
plt.xlabel('Weight')
plt.ylabel('Nums')
plt.title('Weight distribution')
plt.show()
```
<img src="https://github.com/Cafwell/Learning-Python/blob/main/imgs/Data%20Analysis/Figure_5.png" width="380">

##### Hue, row and col
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
sns.set(style="darkgrid")

tips = pd.read_csv("https://milliams.com/courses/data_analysis_python/tips.csv")
sns.displot(data=tips, x="total_bill", col='time')
plt.show()
```
<img src="https://github.com/Cafwell/Learning-Python/blob/main/imgs/Data%20Analysis/Figure_6.png" width="500">


##### Kde 
If only need kde, use sns.kdeplot:
```Python
sns.set(style="white")
m=sns.load_dataset('mpg')
w1=m['weight'].dropna()
sns.kdeplot(w1, shade=True, color='y')
plt.show()
```
<img src="https://github.com/Cafwell/Learning-Python/blob/main/imgs/Data%20Analysis/Figure_7.png" width="380">

Two curves in one graph:
```Python
sns.set(style="white", palette="muted", color_codes=True)
m=sns.load_dataset('mpg')
ax1=sns.kdeplot(m['model_year'][m['origin']=='usa'],color='r', label='usa')
ax2=sns.kdeplot(m['model_year'][m['origin']!='usa'],color='b', label='not usa')
plt.legend()  # Show label
plt.show()
```
<img src="https://github.com/Cafwell/Learning-Python/blob/main/imgs/Data%20Analysis/Figure_8.png" width="380">




-----

#### Relplot
This is a graph-level function that uses scatter plots and line plots to represent statistical relationships.


