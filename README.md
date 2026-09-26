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

## Architecture

The project follows a simple layered architecture designed for clarity and easy extension.

flowchart TD
    A[User Interface<br/>Streamlit Dashboard] --> B[Application Layer<br/>app.py]
    B --> C[Battery Physical Model]
    B --> D[Sensor Simulation]
    B --> E[Analysis Engine]
    
    C --> D
    D --> E
    E --> A

---

## Data Flow

Here is how data moves through the system on every simulation step:

User changes temperature or vehicle mode
↓
Application Layer receives the input
↓
Battery Physical Model updates its internal state
Battery temperature moves toward ambient temperature
Capacity factor is recalculated
SoC changes based on current mode
↓

Sensor Layer generates readings from the model state
(with a small amount of noise for realism)
↓
Analysis Engine processes the sensor data:
Calculates Effective SoC
Estimates remaining range
Evaluates charging efficiency
Generates alerts and recommendations
↓

UI Layer renders the updated metrics, charts, and messages

text### Detailed Data Path

| Stage                  | Input                              | Processing                              | Output                              |
|------------------------|------------------------------------|-----------------------------------------|-------------------------------------|
| User Input             | Sidebar controls                   | —                                       | Ambient temperature, mode           |
| Battery Model          | Previous state + user input        | Temperature & SoC physics               | Updated battery state               |
| Sensors                | Battery state                      | Add realistic noise                     | Raw sensor readings                 |
| Analysis               | Sensor data + battery state        | Calculations & rule-based logic         | Effective SoC, range, alerts        |
| UI                     | Analysis results + history         | Rendering                               | Dashboard                           |

---

## Simulation Step (Simplified)

Every 1–2 seconds (or on manual step):

1. Read user inputs
2. Update battery model
3. Generate sensor data
4. Run analysis
5. Render dashboard
6. Store data point in history (for charts)

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/ev-winter-telematics.git
cd ev-winter-telematics
