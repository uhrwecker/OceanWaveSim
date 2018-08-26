# OceanWaveSim
Simulation Software for Ocean Waves

# Algorithm:
h: height, u: vel in x, v: vel in y, b: 
1. Initialize h0, u0, v0, b

2. For each timestep, do
* solve departute point alpha[i,n] = delta t u[n](xi)
* compute h, u, v at departure points using 
u[n](xi) = (xi - alpha[i, n] - x[m-1])u[n](x[m]) + (x[m]-x[i]+alpha[i, n])u[n](x[m-1]) / delta x
with x[m] = m*delta x, x at mesh point m
same for v, h
* solve equation in folder
* update u[n+1], v[n+1] as 
u[n+1] = -g*dh[n+1]/dx * delta t + u[n]
v[n+1] = -g*dh[n+1]/dy * delta t + v[n]

## Boundary Conditions
* normal v/u at wall == 0
* tangential v/u at wall undisturbed
* water height does not change across boundaries
