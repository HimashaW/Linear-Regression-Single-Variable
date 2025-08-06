# Linear-Regression-Single-Variable

## Overview

Linear Regression is a fundamental statistical method used to model the relationship between a dependent variable \( y \) and a single independent variable \( x \). It fits a straight line (called the regression line) to the given data points.

The general form of the equation is:

\[
y = mx + c
\]

Where:

- \( y \) = predicted value (dependent variable)  
- \( x \) = input value (independent variable)  
- \( m \) = gradient (slope)  
- \( c \) = intercept  

---

## Deriving the Equation


<img width="262" height="153" alt="Screenshot 2025-08-06 113955" src="https://github.com/user-attachments/assets/6cc86553-0232-4689-b968-7e7358ab4a8f" />

---

## Example Dataset

| x (Independent) | y (Dependent) |
|-----------------|---------------|
| 30              | 34,000        |
| 40              | 41,000        |
| 50              | 42,500        |
| 60              | 54,300        |
| 70              | 56,000        |

---

## 🧮 Manual Calculations

Given:
- ∑x = 30 + 40 + 50 + 60 + 70 = 250  
- ∑y = 34000 + 41000 + 42500 + 54300 + 56000 = 227,800  
- ∑xy = (30 × 34000) + (40 × 41000) + (50 × 42500) + (60 × 54300) + (70 × 56000) = 11,963,000  
- ∑x² = 30² + 40² + 50² + 60² + 70² = 13,500  
- n = 5  


---

### 📐 Slope (m)

m = [5 × 11,963,000 - 250 × 227,800] / [5 × 13,500 - 250²]  
= [59,815,000 - 56,950,000] / [67,500 - 62,500]  
= 2,865,000 / 5,000  
= 573.0


---

### 🧮 Intercept (c)

c = (227,800 - 573.0 × 250) / 5  
= (227,800 - 143,250) / 5  
= 84,550 / 5  
= 16,930.0

---

## Linear Regression - Implementation in Python

Let's implement the simple **linear regression (single-variable)** using the data provided earlier and compare it with the **manually calculated** values:

- Slope (m) ≈ 573  
- Intercept (c) ≈ 16,930

---
<pre lang="markdown"> 
  import numpy as np
  import pandas as pd 
  import matplotlib.pyplot as plt 
  from sklearn.linear_model import LinearRegression 
  
  data = pd.read_csv("Book1.csv") 
  
  plt.scatter(data.videos,data.views,color='blue')
  m,c=np.polyfit(x,y,1)
  plt.plot(x,m*x+c)
  plt.xlabel('Number of videos')
  plt.ylabel('Total Views')
  print (m)
  print (c)
   </pre>
  
<img width="569" height="413" alt="download" src="https://github.com/user-attachments/assets/d778a9fd-360e-43cd-af3e-f95a47c8c5f2" />

---

## Implementating Linear regression model
<pre lang="markdown"> 
  import numpy as np
  import pandas as pd 
  import matplotlib.pyplot as plt 
  from sklearn.linear_model import LinearRegression 
  
  data = pd.read_csv("Book1.csv") 
  x=np.array(data.videos.values)
  y=np.array(data.views.values)
  model =LinearRegression()
  model.fit(x.reshape((-1,1)),y)
  new_x=np.array([45]).reshape((-1,1))
  pred=model.predict(new_x)
  pred
   </pre>


---
