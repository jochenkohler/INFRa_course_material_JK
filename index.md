---
layout: default
title: INDEX
---

# TKT 4196

- [About the course](about)
- [Teaching team](team)
- [Autumn 2020 semester](fall2020)
- [Getting started with Python](py_guide)


# Corona attendance list
Due to the current pandemic, we encourage you to register attendance (every lecture that you attend to) by filling-in the following [form](https://forms.gle/Pn1Ar67fCja78CsP9), scanning the QR-code at the entrance of each classroom, or scanning the following QR-code :

![alt text](https://github.com/Jorgemendozaesp/TKT4196-CourseMaterial/blob/master/QR%20Code%20-%20Corona%20form.png?raw=true)

This helps NTNU inform the corresponding health institution regarding corona cases. 

# NEWS
## Week 42

We begin with a new chapter: Structural Design Standards, and spend Tuesday and Wednesday with Theory and an application. On Friday, we have a last practical class before the deadline for CE2. 

I see that many groups are struggling with the 3D plots. I write here a hint to help this part. Assuming that you have a function f1 which outputs the reliability index and inputs as first argument the diameter and as second argument the height, a code to plot the reliability index as a function of the diameter and height is as follows:

```
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

PHI = np.linspace(0.2,1,15)
H = np.linspace(5,20,15)

pp,hh = np.meshgrid(PHI,H)
BETA = np.zeros_like(pp)

for idx_p in range(len(PHI)):
    for idx_h in range(len(H)):
        BETA[idx_p,idx_h] = obj.f1(pp[idx_p,idx_h],hh[idx_p,idx_h])
        
fig = plt.figure()
ax1 = fig.add_subplot(111, projection='3d')
surf = ax1.plot_surface(pp, hh, BETA,cmap=plt.cm.coolwarm)
ax1.set_xlabel('$\phi$')
ax1.set_xlim(PHI[0],PHI[-1])
ax1.set_ylabel('$h$')
ax1.set_ylim(H[0],H[-1])
ax1.set_zlabel(r'$\beta$')
plt.tight_layout()
plt.show()
```

| Compend. | Type |     Topic                                                 |	Lecturer |	Date       | Location |
|----------|------|-----------------------------------------------------------|----------|-------------|----------|
| Ch7      | T    |	Basis of Structural Design Standards                      |	  K 	   | ti. 13.10	 |  S4      |
| CE2      | P	  | Self study / Q&A Sessions                                 |   M      | on. 14.10	 |  KJL1    |
| E7.1     | E    | Exercise on design standards                              |   K      | fr. 16.10   |	KJL1    |

