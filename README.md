# Condensed Matter Model
 
# 2D Ising Model Simulation using the Metropolis Algorithm

## Overview

This repository contains a **2D Ising model** simulation implemented in Python. The simulation uses the **Metropolis-Hastings** method to evolve a grid of spins (values ±1). A **Matplotlib** animation shows how the spin configuration changes over time.

## Features

- **Random Initial Lattice**: Creates an \(N \times N\) array of spins \(\pm 1\).  
- **Local Energy Updates**: Computes the energy cost of flipping a single spin using its four nearest neighbors (periodic boundary conditions).  
- **Metropolis Sweeps**: Performs a full sweep by visiting every lattice site in random order and deciding whether or not to flip the spin.  
- **Interactive Animation**: Uses `matplotlib.animation.FuncAnimation` to visualize the evolution of the spin lattice.  
- **User-Configurable**: Lattice size `N`, temperature `T`, total sweeps `steps`, and animation interval `plot_interval` are all adjustable.

## Requirements

- **Python 3.x**
- **NumPy**
- **Matplotlib**

Install via:

```pip install numpy matplotlib```


## How to Run

1. **Clone** or **download** this repository.
2. **Open** a terminal in the repository folder.
3. **Run** the Python script:



or (if you modify it to accept command-line args):



A Matplotlib window will appear, showing the spins (red/blue) as the simulation proceeds.

## Code Explanation

1. **`initialize_lattice(N)`**  
Creates an \(N \times N\) NumPy array of ±1 spins.

2. **`energy_change(lattice, i, j, J=1.0)`**  
Calculates the energy difference \(\Delta E\) if we flip the spin at \((i, j)\), using periodic boundary conditions.

3. **`metropolis_step(lattice, beta)`**  
- Visits each site once in random order.  
- Computes \(\Delta E\).  
- Decides whether to flip the spin based on the Metropolis criterion \( \exp(-\beta \Delta E)\).  

4. **`run_simulation(N=50, T=2.2, steps=1000, plot_interval=50)`**  
- Initializes the lattice.  
- Creates a Matplotlib figure and uses `FuncAnimation` to periodically update the lattice and refresh the plot.  
- Returns the final configuration after the animation completes.

## Customization

- **Lattice Size (`N`)**: Change to see finite-size effects.  
- **Temperature (`T`)**: Explore the phase transition near T≈2.27 in 2D.  
- **Sweeps (`steps`)**: Longer runs allow the system to equilibrate.  
- **Plot Interval**: Controls how frequently the animation updates.

## License

Feel free to use, modify, and distribute this code for educational or research purposes. A link back here is always appreciated.

Enjoy exploring the 2D Ising model!


