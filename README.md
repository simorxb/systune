# Systune - PI Controller Tuning Example

[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=simorxb/systune)

## Summary
This project demonstrates the use of MATLAB's `systune` function for tuning a fixed-structure PI controller to meet specific design requirements. `systune` is a powerful tool in MATLAB that allows for tuning of control systems with both soft and hard constraints, making it ideal for achieving precise control objectives in complex systems.

## Project Overview
The example explores the tuning of a PI feedback controller to control an object with mass $m = 10 ~ \text{kg}$, subjected to a damping coefficient $k = 0.5 ~ \text{N}\cdot\text{s/m}$ and an external force $F$. The objective is to achieve specific tracking and disturbance rejection requirements while maintaining stability through disk-based gain and phase margins.

### System Model
The dynamic behavior of the object is described by the following differential equation:

$$m \cdot \frac{dv}{dt} = F - k \cdot v$$

The corresponding transfer function of the plant is:

$$G(s) = \frac{V(s)}{F(s)} = \frac{1}{ms + k}$$

### Controller Design
The PI controller designed for this system has the form:

$$C(s) = K_p + \frac{K_i}{s}$$

where $K_p$ and $K_i$ are tuned to achieve a closed-loop response that meets the specified requirements.

### Design Requirements

- **Soft Requirements**
  - Tracking error: 0.1% at 0 rad/s, 100% after 5 rad/s.
  - Disturbance rejection at control input: 0.1% at 0 rad/s, 5% after 1 rad/s.
  - Maximum gain from reference to control input: 50.

- **Hard Requirements**
  - Disk-based gain margin: 20 dB
  - Disk-based phase margin: 60 degrees

### MATLAB Code and Verification
The project includes MATLAB code to define the system, set up the `systune` tuning goals, and validate the controller design. Verification includes plotting the step response, control effort, tracking performance, and disturbance rejection, as well as ensuring that gain and phase margins are within the specified limits.

To view the full code and results, visit the [GitHub repository](https://github.com/simorxb/systune).

## Author
This project is developed by Simone Bertoni. Learn more about my work on my personal website - [Simone Bertoni - Control Lab](https://simonebertonilab.com/).

## Contact
For further communication, connect with me on [LinkedIn](https://www.linkedin.com/in/simone-bertoni-control-eng/).
