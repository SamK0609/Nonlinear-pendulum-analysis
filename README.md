# Nonlinear Pendulum Simulation

This project simulates a nonlinear simple pendulum using numerical methods. The full equation of motion is solved without the small-angle approximation, allowing analysis of large-angle behaviour, energy conservation, phase space dynamics, and period dependence on amplitude.

---

## Equation of Motion

The nonlinear pendulum is governed by:

d²θ/dt² = -(g/L) sin(θ)

This is rewritten as a system of first-order ODEs:

dθ/dt = ω  
dω/dt = -(g/L) sin(θ)

---

## Numerical Method

The system is solved using:

- SciPy’s `solve_ivp` function
- High precision tolerances (rtol = 1e-9, atol = 1e-9)
- Time interval: 0 to 20 seconds
- NumPy for numerical computation
- Matplotlib for visualisation

---

## Features

### 1. Effect of Initial Angle
The pendulum is simulated for multiple starting angles:
- 10°, 30°, 60°, 90°

This shows how increasing amplitude leads to more nonlinear motion.

---

### 2. Effect of Initial Angular Velocity
Different initial angular velocities are tested to observe their effect on oscillation behaviour.

---

### 3. Nonlinear vs Small-Angle Approximation

The nonlinear solution is compared to:

θ(t) ≈ θ₀ cos(√(g/L) t)

This shows that the small-angle approximation breaks down at larger amplitudes.

---

### 4. Energy Conservation

Total energy is calculated as:

E = 1/2 ω² + g(1 - cos(θ))

The simulation checks numerical stability by measuring energy drift over time.

---

### 5. Phase Space Analysis

Phase portraits (θ vs ω) are plotted for multiple initial angles.

Angle wrapping is applied to keep θ in [-π, π] for clearer visualisation.

---

### 6. Period vs Initial Angle

The oscillation period is estimated using zero-crossings of θ(t).

Results show:
- Constant period at small angles
- Increasing period at larger amplitudes
- Deviation from the small-angle period:

T₀ = 2π √(L/g)

---

## Key Results

- Small-angle approximation becomes inaccurate beyond ~30°
- Period increases with amplitude due to nonlinear effects
- Energy is approximately conserved with small numerical drift
- Phase space trajectories form closed loops (conservative system)

---

## Technologies Used

- Python
- NumPy
- Matplotlib
- SciPy (solve_ivp)

---

## How to Run

Clone the repository:

git clone https://github.com/SamK0609/nonlinear-pendulum.git
cd nonlinear-pendulum  

Install dependencies:

pip install -r requirements.txt  

Run the simulation:

python main.py  

Or run the Jupyter notebook:

jupyter notebook  

---

## Project Structure

nonlinear-pendulum:
- main.py
- Full simulation and plots
- README.md
- requirements.txt

---

## Possible Extensions

- Add damping term (bω)
- Add driven forcing term (chaotic pendulum)
- Animate pendulum motion
- Improve period detection using peak-finding methods
- Compare with analytical elliptic integral solution

---

## Summary

This project demonstrates how nonlinear dynamics significantly change the behaviour of a classical pendulum system and highlights the limitations of linear approximations in physics.
