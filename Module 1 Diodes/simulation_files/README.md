# Power Diodes Simulation Files

This directory contains PSpice simulation files that accompany the Power Diodes Technical Report.

## Simulation Files

### 1. Single-Phase Bridge Rectifier (`single_phase_bridge_rectifier.cir`)
- **Purpose**: Demonstrates single-phase full-wave rectification
- **Based on**: Rashid Power Electronics Example 3.3
- **Key Features**:
  - 120V RMS, 60Hz input voltage
  - RL load (2.5Ω, 6.5mH)
  - 10V DC component in load
  - Four-diode bridge configuration

**Expected Results**:
- Plot I(VX): Output current through load
- Plot V(3,4): Rectified output voltage
- Observe 120Hz ripple frequency (2× input frequency)

### 2. Three-Phase Bridge Rectifier (`three_phase_bridge_rectifier.cir`)
- **Purpose**: Demonstrates three-phase full-wave rectification
- **Based on**: Rashid Power Electronics Example 3.8
- **Key Features**:
  - Three-phase 120V RMS, 60Hz input (120° phase shift)
  - RL load (2.5Ω, 1.5mH)
  - Six-diode bridge configuration

**Expected Results**:
- Plot V(4,5): Six-pulse output voltage
- Plot I(VY): Phase A input current
- Observe 360Hz ripple frequency (6× input frequency)
- Much smoother output compared to single-phase

### 3. Freewheeling Diode Circuit (`freewheeling_diode_circuit.cir`)
- **Purpose**: Demonstrates freewheeling diode operation and protection
- **Key Features**:
  - Switch opening simulation with inductive load
  - Freewheeling diode prevents voltage spikes
  - 10mH inductor with 5Ω resistor

**Expected Results**:
- Observe current continuity through freewheeling diode
- Voltage spike protection when switch opens
- Controlled energy dissipation

## Running the Simulations

### Using PSpice
1. Open PSpice or PSpice Student Version
2. Create a new project and add the `.cir` file
3. Run the simulation (Analysis → Run)
4. View results in Probe

### Using LTSpice (Alternative)
1. Create new schematic
2. Copy the netlist content into a text file with `.asc` extension
3. Modify syntax if needed for LTSpice compatibility
4. Run simulation and plot results

## Key Measurements

### Single-Phase Rectifier
- **Average DC Output**: ~90% of input RMS voltage
- **Ripple Factor**: ~48.2%
- **Peak Inverse Voltage**: √2 × Vs

### Three-Phase Rectifier
- **Average DC Output**: ~135% of line-to-line RMS voltage
- **Ripple Factor**: ~4.2%
- **Peak Inverse Voltage**: √6/2 × VLL

## Troubleshooting

### Common Issues:
1. **Convergence Problems**: Adjust `.OPTIONS` parameters
2. **Probe Not Working**: Ensure `.PROBE` directive is included
3. **Timing Issues**: Check transient analysis parameters

### Tips:
- Start with larger time steps for initial analysis
- Use smaller time steps for detailed waveform analysis
- Monitor diode currents and voltages for proper operation

## References
- Rashid, M.H. (2014). Power Electronics: Devices, Circuits, and Applications (4th ed.)
- Mohan, N., Undeland, T.M., & Robbins, W.P. (2003). Power Electronics: Converters, Applications, and Design (3rd ed.)

## Contact
For questions about these simulations or the accompanying technical report, please refer to the main report document.
