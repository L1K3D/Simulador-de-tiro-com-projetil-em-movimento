# Projectile-in-Motion Shooting Simulator

## Overview

The **Projectile-in-Motion Shooting Simulator** is a comprehensive, graphical application designed to simulate and dynamically calculate the trajectory of a projectile launched toward a vertically descending target. Developed in C#, this project offers a robust framework for modeling projectile motion, computing interception parameters, and visualizing results both graphically and through Power BI reports.

The simulator allows users to input various parameters for the projectile and the moving target, computes the necessary physics (such as velocities, angles, and times), and presents the results in an intuitive and analytical format. The system can handle real-world scenarios, including angle constraints and dynamic target movement, providing an educational and analytical tool for studying projectile kinematics.

## Features

- **Graphical Simulation Interface:** User-friendly graphical screens to input parameters, visualize trajectories, and review outcomes.
- **Dynamic Calculation Engine:** Computes projectile trajectories, interception times, velocities, and angles based on user inputs and real-world physics equations.
- **Movable Target Modeling:** Simulates targets in vertical descent, including calculations for time until impact and maximum interception angle.
- **Data Persistence:** Stores simulation parameters and outcomes in a structured database for analysis and reporting.
- **Power BI Integration:** Exports simulation results for further analysis and visualization in Power BI.
- **Python Scripting for Visualization:** Utilizes Python scripts to process simulation data and generate detailed graphs for analysis.
- **Error Handling and Validation:** Provides clear feedback on invalid inputs or physically impossible scenarios.

## Project Structure

- `PPL_Main/`: Main C# application code, including forms and core logic.
  - `Telas/`: Contains the graphical interface components such as `TelaSimulacao.cs`, responsible for the simulation workflow.
- `PythonScripts/`: Scripts for post-processing simulation data and generating graphs (e.g., `GeracaoGrafico.py`).
- `dados_simulacao.txt`: Output file with simulation results used by Python scripts.
- `README.md`: This documentation file.

## How It Works

### 1. Parameter Entry

Users specify initial conditions for both the projectile and the vertically descending target, including:
- Projectile launch angle
- Initial velocities (horizontal and vertical components)
- Distance to target
- Initial height of the target
- Type of projectile movement

### 2. Simulation Execution

The simulator:
- Validates input parameters, ensuring the launch angle is within the physically possible range.
- Converts input angles to radians and computes the projectile's initial velocity components using trigonometric functions.
- Calculates the flight time, trajectory, interception point, and other kinematic properties.
- Models the target's vertical decay and determines the time until it reaches the ground.

### 3. Data Storage

All relevant simulation data (projectile, target, and simulation results) are stored in a relational database using stored procedures for:
- Projectile data (`projetil`)
- Target data (`alvo`)
- Simulation data (`simulacoes`)

### 4. Visualization

- **Graphical Output:** The application displays temporal variations and kinematic data in real time.
- **Python Data Processing:** After simulation, data are written to `dados_simulacao.txt` and a Python script processes this file to generate graphical plots.
- **Power BI Reporting:** Data are exported for business intelligence analysis and reporting.

### 5. Error Handling

If the provided angle does not result in an interception or is outside the valid range, the simulator notifies the user and requests a new input.

## Technical Details

- **Main Language:** C#
- **Database Integration:** Uses stored procedures for structured data insertion and management.
- **Physics Engine:** Implements kinematic equations for projectile motion and target movement.
- **Scripting:** Python with Pandas for data manipulation and Matplotlib (or similar) for visualization.
- **Reporting:** Output data is formatted for Power BI integration, enabling advanced analytics.

## Example Workflow

1. **User enters initial parameters** (angle, velocities, heights).
2. **Simulation is run;** calculations are performed for interception time and trajectory.
3. **Results are shown graphically** and stored in the database.
4. **Python script is triggered** to convert stored data into analytical graphs.
5. **Data is exported to Power BI** for further exploration.

## Use Cases

- Educational tool for physics and engineering students to visualize and understand projectile motion.
- Analytical tool for researchers or professionals studying interception scenarios or projectile targeting.
- Demonstrative software for presenting kinematic principles.

## Requirements

- .NET Framework (for running the C# application)
- Python 3.x (with Pandas and visualization libraries)
- SQL Server or compatible database for data storage
- Power BI (optional, for advanced reporting)

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/L1K3D/Simulador-de-tiro-com-projetil-em-movimento.git
   ```
2. Open the solution in Visual Studio.
3. Configure your database connection as required.
4. Run the application and follow the on-screen instructions.
5. To generate graphs, ensure Python and dependencies are installed and run the relevant scripts in `PythonScripts/`.

## License

This project currently does not specify a license. Please contact the repository owner for usage terms.
