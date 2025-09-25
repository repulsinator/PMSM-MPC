# ESO-MPC Control for PMSM

This project implements an **Extended State Observer (ESO)** combined with **Model Predictive Control (MPC)** for robust speed regulation of **Permanent Magnet Synchronous Motors (PMSM)**.  

## Features
- Real-time disturbance estimation and compensation with ESO.  
- Optimal control using MPC with prediction and control horizons.  
- Robust against load torque changes and parameter variations.  
- Simulation results showing improved tracking and robustness vs. classical PI control.  

## Future Work
- Hardware-in-the-loop (HIL) testing on DSP/FPGA.  
- Integration with Field-Oriented Control (FOC).  

# ESO-Enhanced Model Predictive Speed Control of PMSM

## Overview
This repository contains the implementation of an **ESO-enhanced Model Predictive Controller (MPC)** for speed regulation of Permanent Magnet Synchronous Motors (PMSM).  
The ESO estimates unmodeled dynamics and disturbances (e.g., load torque, viscous friction variation), while MPC ensures optimal speed tracking within input constraints.

## System Model
- Rotor Position: θ  
- Rotor Speed: ω  
- Control Input: u = i_q  
- Disturbances: d (load torque, parameter mismatch)  

Discrete dynamics:  

ω(k+1) = A_n ω(k) + B_n u(k) + B_d d(k)  

where:  
- A_n = 1 − (B_r / J_r) T_s  
- B_n = (K_m / J_r) T_s  
- B_d = T_s  

## Key Contributions
- ESO for real-time estimation of external torque and parameter uncertainties.  
- MPC with finite prediction horizon (N_p) and control horizon (N_c).  
- Cost function optimization with Q, R weighting matrices.  
- Robust performance under sudden torque load changes.  

## Simulation Results
- Fast disturbance rejection with ESO compensation.  
- Reduced steady-state error compared to PI control.  
- Smooth torque response and stable tracking.  

## References
- Y. Wei et al., *Prediction Horizons Optimized Nonlinear Predictive Control for PMSM*, IEEE T-IE, 2020.  
- ADRC-based ESO framework for nonlinear disturbance estimation.  
