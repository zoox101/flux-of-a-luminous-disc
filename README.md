# flux-of-a-luminous-disc
Equation governing the flux experienced by a zero dimensional observer positioned on the line running perpendicular to the center of a luminous two dimensional disc:

$$ F = \frac{L}{4 \pi R^2} * \ln{\left(\frac{R}{D} + 1\right)} $$

## Python Code

```python
import math

def get_flux_disc(
  L: float, # Total luminosity of the rod
  D: float, # Distance of the observer from the center of the rod
  R: float  # Radius of the disc
):

  # Flux of a point
  if R == 0:
    return L / (4 * math.pi * (D**2))

  # Flux of a uniform disc
  else:
    return (L / (4 * math.pi * R**2)) * math.log((R**2 / D**2) + 1)
```
