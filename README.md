# flux-of-a-luminous-disc
Equation governing the flux experienced by an observer of negligible size positioned on the line running perpendicular to the center of a luminous two dimensional disc:

$$ F = \frac{L}{4 \pi R^2} * \ln{\left(\frac{R^2}{D^2} + 1\right)} $$

Where $F$ is the flux experienced by the observer, $L$ is the luminosity of the disc, $R$ is the radius of the disc, and $D$ is the distance between the center of the disc and the observer.

## Python Code

```python
import math

def get_flux_disc(
  L: float, # Total luminosity of the rod
  D: float, # Distance of the observer from the center of the rod
  R: float  # Radius of the disc
):

  # Flux of a point, prevents divide by zero error when H == 0
  if R == 0:
    return L / (4 * math.pi * (D**2))

  # Flux of a uniform disc
  else:
    return (L / (4 * math.pi * R**2)) * math.log((R**2 / D**2) + 1)
```
