# Ford Line Health Monitor

AI solution 09 of 14 · Operations · built for **Ford Motor Company**

Prepared by **K Bhargav Raju**.

## Problem statement

Unexpected equipment failures are causing production downtime and increasing maintenance costs. Develop an AI system that analyzes machine sensor data, maintenance history and production schedules to identify failure patterns and recommend preventive maintenance actions.

## Why Ford Motor Company

A Ford assembly plant depends on presses, welding robots and conveyors, and one unplanned breakdown can stop the whole line. This tool reads machine sensors, predicts which machine fails next and books the repair into planned downtime.

## Algorithm

1. **Collect sensor and maintenance data**: Vibration, temperature, motor current, work orders, schedule
2. **Build health features**: Each sensor vs the machine's own healthy baseline (z-score)
3. **Anomaly detection**: Health index from combined z-scores, flag above 3
4. **Remaining useful life**: Trend of the health index to the failure level
5. **7-day failure probability**: Logistic model trained on past failure windows
6. **Failure patterns**: K-means on past failure signatures
7. **Schedule maintenance**: Book each job into the last planned window before failure
8. **Work orders**: AI analyst drafts technician instructions

## Data

24 machines on one body-and-assembly line, 120 days of daily sensor readings and 3 years of failure history (sample data). All figures are illustrative and are not Ford Motor Company's actual numbers.

## How to use

Open `index.html` in any web browser. No installation is needed; the whole tool is one self-contained file.

The controls panel lets you change unplanned downtime cost, safety buffer before predicted failure, and the analysis reruns instantly. "New sample data" generates a fresh dataset.

## AI analyst panel

The "Ask the AI analyst" panel answers questions about the results in plain English through Claude. It works when the page is opened as a Claude artifact on claude.ai. Opened from GitHub, GitHub Pages or a local folder, all the models, charts and controls still run, and the panel shows that it is unavailable.
