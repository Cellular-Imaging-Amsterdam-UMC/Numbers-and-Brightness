---
layout: default
title: Calculations
nav_order: 2
---
# Core calculations
All calculations are derived from Digman et al. (2008).

Here `img` represents a numpy array of shape  `(t, y, x)`.

#### Intensity
Intensity is calculated as:<br>

$$\langle k \rangle = \frac{\sum_i k_i}{K}$$

In python:
```python
average_intensity = np.mean(img, axis=0)
```
#### Variance
Variance is calculated as:<br>

$$\sigma^2 = \frac{\sum_i (k_i - \langle k \rangle)^2}{K}$$

In python:
```python
variance = np.var(img, axis=0)
```
#### Apparent brightness
Apparent brightness is calculated as:<br>

$$B = \frac{\sigma^2}{\langle k \rangle}$$

In python:
```python
apparent_brightness = variance / average_intensity
```
#### Apparent number
Apparent number is calculated as:<br>

$$N = \frac{\langle k \rangle^2}{\sigma^2}$$

In python:
```python
apparent_number = average_intensity**2 / variance
```
#### Brightness
Brightness is calculated as:<br>

$$\varepsilon = \frac{\sigma^2 - \langle k \rangle}{\langle k \rangle - k_0}$$

In python:
```python
brightness = (variance - average_intensity) / (average_intensity - background)
```
#### Number
Number is calculated as:<br>

$$n = \frac{(\langle k \rangle - k_0)^2}{\sigma^2 - \langle k \rangle}$$

In python:
```python
number = ((average_intensity-background)**2) / np.clip((variance - average_intensity), 1e-6, None)
```
Here the denominator is clipped (limited) to a value of 1e-6 to prevent extremely high number values.

#### References:
- Digman, M. A., Dalal, R., Horwitz, A. F., & Gratton, E. (2008). Mapping the Number of Molecules and Brightness in the Laser Scanning Microscope. Biophysical Journal, 94(6), 2320–2332. https://doi.org/10.1529/biophysj.107.114645