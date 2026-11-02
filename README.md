# Satellite Trajectory Analysis GUI

An interactive desktop application built with Python and Tkinter for modeling, visualizing, and analyzing satellite orbits using Keplerian orbital elements and SGP4 TLE (Two-Line Element) propagation.

## 📌 Features

* **Interactive Orbital Controls:** Real-time adjustments of the 6 classical Keplerian orbital elements via GUI sliders.
* **3D Orbit Visualization:** Renders interactive 3D orbital trajectories around Earth using `PyAstronomy`.
* **SGP4 Altitude Solver:** Calculates satellite altitude over a 24-hour window from TLE orbital data using the SGP4 propagation model.
* **Modern Dark Theme:** Styled with `sv-ttk` (Sun Valley dark theme) and Matplotlib dark background integration.
* **Data Export:** Exports current orbital parameters directly to `data.csv`.

## 📐 Keplerian Orbital Elements

The application allows real-time manipulation of the six Keplerian parameters:

| Parameter | Symbol | Description | Range in GUI |
| :--- | :---: | :--- | :---: |
| **Semi-Major Axis** | $a$ | Defines the size of the orbit | $2,000 - 50,000 \text{ km}$ |
| **Eccentricity** | $e$ | Defines the shape of the orbit ($0 = \text{circular}$) | $0.0 - 1.0$ |
| **Inclination** | $i$ | Tilt of the orbit relative to the equator | $0^\circ - 360^\circ$ |
| **RAAN** | $\Omega$ | Right Ascension of the Ascending Node | $0^\circ - 360^\circ$ |
| **Argument of Perigee** | $\omega$ | Orientation of the orbit in its orbital plane | $1^\circ - 360^\circ$ |
| **Mean Anomaly** | $M$ | Position of the satellite along its orbit | $1^\circ - 360^\circ$ |

### Altitude Calculation Equation

The altitude ($h$) above Earth's surface from position vector $\mathbf{r} = [x, y, z]$ is calculated using:

$$
h = \sqrt{x^2 + y^2 + z^2} - R_E
$$

Where $R_E = 6378.135 \text{ km}$ represents Earth's mean equatorial radius.

## 🛠️ Prerequisites & Installation

Make sure you have Python 3.8+ installed along with the required libraries:

```bash
pip install sv-ttk matplotlib numpy PyAstronomy sgp4
```

## 🚀 How to Run

1. Navigate to the project directory:
   ```bash
   cd Satellite_Trajectory_Analysis_GUI
   ```

2. Run the main GUI script:
   ```bash
   python Satellite_Trajectory_Analysis_GUI.py
   ```

## 🖥️ UI Overview & Usage

* **Left Frame:** Displays two embedded Matplotlib plots:
  1. 24-hour Altitude vs. Time graph generated via SGP4 propagation.
  2. Interactive 3D plot showing Earth, the satellite trajectory, and the periapsis point.
* **Right Frame:** Contains the 6 orbital parameter sliders along with control buttons:
  * **Retrace Orbit:** Recalculates and updates the 3D orbit model based on slider values.
  * **Download CSV:** Exports current parameter settings to `data.csv`.