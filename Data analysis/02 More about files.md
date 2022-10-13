## Data Analysis

### Some simple analyses
Mean:
```Python
import pandas as pd
import numpy as np

rain = pd.read_csv("https://milliams.com/courses/data_analysis_python/rain.csv")
print(rain.mean())
---
Cardiff       97.400000
Stornoway    100.316892
Oxford        54.787500
Armagh        68.803571
dtype: float64
```

You can also learn more about the details of the data: ask how many years the average rainfall in each city exceeds 100mm:
```Python
rain[rain > 100].count()
---
Cardiff      13
Stornoway    74
Oxford        0
Armagh        1
dtype: int64
```

### File processing
Use [city_pop.csv](https://github.com/Cafwell/Learning-Python/blob/main/Data%20analysis/city_pop.csv)

![](https://github.com/Cafwell/Learning-Python/blob/main/imgs/Data%20Analysis/city_pop.png)

```Python
import pandas as pd
import numpy as np

city_pop_file = "https://milliams.com/courses/data_analysis_python/city_pop.csv"
print(pd.read_csv(city_pop_file))
---
                          This is an example CSV file
0   The text at the top here is not part of the da...
1   to describe the file. You'll see this quite of...
2                     A -1 signifies a missing value.
3                              year;London;Paris;Rome
4                              2001;7.322;2.148;2.547
5                                   2006;7.652;;2.627
6                                      2008;-1;2.211;
7                                 2009;-1;2.234;2.734
8                                        2011;8.174;;
9                                 2012;-1;2.244;2.627
10                                       2015;8.615;;

```

It didnt need start from 'This is an example CSV file', use skiprow:
```Python
a = pd.read_csv(city_pop_file,
                skiprow s= 5  # Start from line 5 (line start from 0)
    )
print(a)
---
   year;London;Paris;Rome
0  2001;7.322;2.148;2.547
1       2006;7.652;;2.627
2          2008;-1;2.211;
3     2009;-1;2.234;2.734
4            2011;8.174;;
5     2012;-1;2.244;2.627
6            2015;8.615;;
```

Separate the columns, use sep:
```Python
a = pd.read_csv(city_pop_file,
                skiprow s= 5,
                sep=";",
    )
print(a)
---
   year  London  Paris   Rome
0  2001   7.322  2.148  2.547
1  2006   7.652    NaN  2.627
2  2008  -1.000  2.211    NaN
3  2009  -1.000  2.234  2.734
4  2011   8.174    NaN    NaN
5  2012  -1.000  2.244  2.627
6  2015   8.615    NaN    NaN
```

There still some missing nums, if we want to add some custom values equivalent to missing values, use na_values:
```Python
a = pd.read_csv(city_pop_file,
                skiprow s= 5,
                sep=";",
                na_values="-1" # All -1 will seem as NaN
    )
print(a)
---
   year  London  Paris   Rome
0  2001   7.322  2.148  2.547
1  2006   7.652    NaN  2.627
2  2008     NaN  2.211    NaN
3  2009     NaN  2.234  2.734
4  2011   8.174    NaN    NaN
5  2012     NaN  2.244  2.627
6  2015   8.615    NaN    NaN
```

Last, we want the 'year' column as the index for this DataFrame, use index_col:
```Python
a = pd.read_csv(city_pop_file,
                skiprow s= 5,
                sep=";",
                na_values="-1"
                 index_col="year"
    )
print(a)
---
      London  Paris   Rome
year                      
2001   7.322  2.148  2.547
2006   7.652    NaN  2.627
2008     NaN  2.211    NaN
2009     NaN  2.234  2.734
2011   8.174    NaN    NaN
2012     NaN  2.244  2.627
2015   8.615    NaN    NaN
```

### Exercise
Read the file at https://milliams.com/courses/data_analysis_python/meantemp_monthly_totals.txt into Pandas (this data is originally from the Met Office and there's a description of the format there too under "Format for monthly CET series data").
This contains some historical weather data for a location in the UK. Import that file as a Pandas DataFrame using read_csv(), making sure that you set the index column, skip the appropriate rows, separate the columns correctly and cover all the possible NaN values.

<details>
  <summary><b>Answer</b></summary>
  <pre><code> 
import pandas as pd
temperature = pd.read_csv(
    "https://milliams.com/courses/data_analysis_python/meantemp_monthly_totals.txt",  # file name
    skiprows=4,  # skip first 6 rows of the header
    delim_whitespace=True,  # whitespace separated columns
    index_col="Year",  # Set the index
    na_values=["-99.9"],  # NaNs
)
temperature.head()
    </code></pre>
</details>

