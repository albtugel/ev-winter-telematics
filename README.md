# EV Winter Telematics Simulation

Interactive simulation of a telematics system for monitoring electric vehicle (EV) battery performance in cold weather conditions.

This project demonstrates how low temperatures affect battery capacity, charging speed, and driving range. It includes simulated sensors, real-time analysis, alerts, and recommendations — all in a simple and clean web dashboard.

Built for presentations, prototyping, and educational purposes.

---

## Features

- **Simulated Sensors**
  - State of Charge (SoC)
  - Battery voltage
  - Current (charge / discharge)
  - Battery temperature
  - Ambient temperature
  - Power consumption

- **Cold Weather Analysis**
  - Temperature impact on available battery capacity
  - Effective SoC calculation
  - Estimated driving range adjusted for temperature
  - Charging speed reduction in cold conditions

- **Real-time Dashboard**
  - Live sensor readings
  - Interactive charts (SoC, temperature, power)
  - Visual alerts and status indicators
  - Text recommendations based on current conditions

- **Interactive Controls**
  - Adjustable ambient temperature
  - Vehicle modes: Parking / Driving / Charging
  - Start / Stop / Reset simulation
  - Predefined scenarios (optional)

---

## Tech Stack

| Component       | Technology     |
|-----------------|----------------|
| Language        | Python 3.10+   |
| Dashboard       | Streamlit      |
| Data & Math     | NumPy, Pandas  |
| Charts          | Plotly         |

The entire application runs from a single Python file. No backend servers, databases, or complex infrastructure required.

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/ev-winter-telematics.git
cd ev-winter-telematics
