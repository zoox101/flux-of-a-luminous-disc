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

## Proof

### Assumptions

The equation for flux from a point source:
$F = \frac{L}{4 \pi D^2}$

The equation for the luminosity of an infinitely thin ring on the disc:
$L_{ring} = L_{disc} \frac{C_{disc}}{A_{disc}} dr$

The equation for the circumference of a circle:
$C = 2\pi r$

The equation for the area of a circle:
$A=\pi r^2$

The distance of any point on the ring to the observer:
$D_{ring}=\sqrt{D^2+r^2}$

### Process

$F_{ring}=\frac{L_{ring}}{4\pi D_{ring}^2}$

$L_{ring}=L_{disc}\frac{2\pi r}{\pi R^2}dr$

$F_{ring}=\frac{L_{disc}\frac{2\pi r}{\pi R^2}dr}{4\pi \left(D^2+r^2\right)}$

$F_{ring}=\frac{L_{disc}}{2\pi R^2}\cdot \frac{r}{\left(D^2+r^2\right)}dr$

$F_{disc}=\frac{L_{disc}}{2\pi R^2}\cdot \int _0^R\left(\frac{r}{D^2+r^2}\right)dr$

$F_{disc}=\frac{L_{disc}}{2\pi R^2}\cdot \frac{\ln \left|D^2+R^2\right|-\ln \left|D^2\right|}{2}$

$F_{disc}=\frac{L_{disc}}{4\pi R^2}\cdot \ln \left(\frac{D^2+R^2}{D^2}\right)$

$F_{disc}=\frac{L_{disc}}{4\pi R^2}\cdot \ln \left(\frac{R^2}{D^2}+1\right)$

$Q.E.D.$
