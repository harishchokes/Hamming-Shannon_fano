# **Hamming-Shannon_Fano Coding**

## **Aim**
To compute the **Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance** for a **discrete memoryless source** using **Huffman and Shannon-Fano coding** based on the given probabilities and codeword lengths.

## **Tools Required**
- **Python**: A versatile programming language for scientific computing and signal processing.
- **NumPy**: A powerful numerical library in Python for performing array-based operations and mathematical computations.
- **Matplotlib**: A plotting library for generating high-quality graphs and visualizations.


## **Program**
```
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)

for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)

eff = hs / L
eff = round(eff,3)

red =  round(1 - eff,3) 

var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print()
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff*100} %")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
## **OUTPUT**
![image](https://github.com/user-attachments/assets/d7156623-e5d6-480f-8373-318574c04a80)

## **Calculation**
![WhatsApp Image 2025-03-26 at 17 43 38_99671ff9](https://github.com/user-attachments/assets/2c9f4dfc-9ba5-4ca4-8a85-39837d66c148)
![WhatsApp Image 2025-03-26 at 17 43 58_1dc0f250](https://github.com/user-attachments/assets/4de8bee2-8672-433e-99b5-bff5d8a2bab3)

## **Results.**

For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25
```
Average Codeword Length is : 2.625 
Entropy is : 2.625
Efficiency is : 100.0 %
Redudancy is : 0.0
Variance is : 0.484
```

