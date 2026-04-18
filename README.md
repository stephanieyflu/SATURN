# 🛰️ SATURN
### Satellite Autonomy for Tasking Under Resource Constraints

A framework for **uncertainty-aware autonomous satellite tasking**, combining machine learning, optimization, and sequential decision-making under realistic system constraints.

## Overview

Modern Earth observation satellites operate under strict limitations:
- limited onboard compute
- finite storage capacity
- constrained downlink bandwidth

As a result, a significant fraction of collected imagery is unusable or redundant (e.g., due to cloud cover).

**SATURN** addresses this by modelling satellite tasking as a **sequential decision-making problem under uncertainty**, enabling intelligent selection of observations that maximize long-term information value.

## Key Idea

We formulate satellite tasking as a **resource-constrained decision process**:

- each observation has uncertain value (clouds, events, noise)
- actions must be taken sequentially over time
- decisions affect future resource availability

The goal is to learn or design policies that **maximize information gain while respecting onboard constraints**

## System Architecture

```
Simulation → Perception → Decision → Evaluation
   ↓            ↓            ↓            ↓
Orbit       ML Models     Policies     Metrics
````

### Modules

- **Simulation**
  - Satellite trajectory + Earth observation opportunities

- **Perception**
  - Cloud detection
  - Event detection (e.g., wildfires, vessels)

- **Decision Engine**
  - Heuristic policies
  - Optimization-based selection
  - Reinforcement learning (planned)

- **Resource Model**
  - Storage buffer
  - Downlink constraints
  - Compute limitations

- **Evaluation**
  - Information gain
  - Resource efficiency
  - Regret vs oracle

## 🚀 Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/stephanieyflu/saturn.git
cd saturn
````

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the baseline pipeline

```bash
python scripts/run_simulation.py --config configs/baseline.yaml
```

## Example Experiments

We evaluate multiple policies:

* **Always Capture**
* **Random Policy**
* **Cloud-Aware Heuristic**
* *(Upcoming)* Optimization + RL policies

Outputs include:

* information gain over time
* resource utilization
* comparative performance plots

## Project Structure

```
saturn/
├── src/sat_tasking/
│   ├── simulation/
│   ├── perception/
│   ├── decision/
│   ├── resources/
│   ├── evaluation/
│
├── configs/
├── scripts/
├── experiments/
├── docs/
```

## Research Directions

* uncertainty-aware decision policies
* risk-sensitive optimization
* partially observable models (POMDPs)
* multi-satellite coordination
* reinforcement learning for adaptive tasking

## Datasets

* Sentinel-2 (ESA Copernicus)
* Landsat 8/9 (NASA/USGS)
* NASA FIRMS (wildfires)
* AIS maritime tracking data

## Roadmap

* [ ] MVP pipeline (simulation → perception → decision)
* [ ] baseline policy evaluation
* [ ] uncertainty-aware policies
* [ ] reinforcement learning integration
* [ ] multi-satellite extension
* [ ] research report / workshop submission

## Vision

SATURN aims to serve as:

* a **reproducible benchmark** for satellite autonomy
* a **training ground** for ML + systems + optimization
* a **bridge between student projects and real space systems**
