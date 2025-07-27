# Smart Grid Optimization Using Genetic Algorithm

## Overview
This project implements a genetic algorithm (GA) to optimize electricity distribution in a smart grid system. It minimizes transmission losses while ensuring demand is met across multiple nodes over a 24-hour period. The system generates synthetic data for demand, supply, and transmission losses, performs exploratory data analysis (EDA), and compares serial and parallel GA implementations against a greedy baseline.

## Features
- **Data Generation**: Simulates electricity demand (10 nodes × 24 hours), supply (3 sources × 24 hours), and transmission losses (3 sources × 10 nodes).
- **Exploratory Data Analysis (EDA)**: Visualizes demand and supply trends and correlations using Matplotlib and Seaborn.
- **Optimization**:
  - **Serial Genetic Algorithm**: Optimizes electricity distribution sequentially.
  - **Parallel Genetic Algorithm**: Leverages multiprocessing for faster computation.
  - **Greedy Baseline**: Provides a baseline solution for comparison.
- **Performance Metrics**: Reports fitness scores and execution times for serial and parallel GAs.

## Prerequisites
- Python 3.6+
- Required Python libraries:
  - `numpy`
  - `pandas`
  - `matplotlib`
  - `seaborn`
- Install dependencies using:
  ```bash
  pip install numpy pandas matplotlib seaborn
  ```

## Project Structure
```
smart-grid-optimization/
├── ITS66604_0372064_GRUPASGNMT.ipynb  # Main Jupyter notebook with code
├── README.md                           # Project documentation
└── requirements.txt                    # Python dependencies
```

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/smart-grid-optimization.git
   cd smart-grid-optimization
   ```
2. Create a virtual environment (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Ensure Jupyter Notebook is installed:
   ```bash
   pip install jupyter
   ```

## Usage
1. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
2. Open `ITS66604_0372064_GRUPASGNMT.ipynb` in the Jupyter interface.
3. Run the notebook cells sequentially to:
   - Generate synthetic demand, supply, and transmission loss data.
   - Perform EDA (visualize demand/supply trends and correlations).
   - Execute the serial and parallel genetic algorithms.
   - Compare results with the greedy baseline.
4. View the output, including plots and performance metrics (e.g., execution times, fitness scores).

## Example Output
- **EDA Visualizations**:
  - Line plots of electricity demand per node and supply per source over 24 hours.
  - Heatmaps showing demand and supply correlations.
- **Optimization Results**:
  - Total Demand: 23,970 units
  - Total Supply: 26,054 units
  - Baseline (Greedy) Fitness: -10,000,000.00 (due to an artificially high demand for testing)
  - Execution Times:
    - Serial GA: ~11.96 seconds
    - Parallel GA: ~9.01 seconds

## Methodology
- **Data Generation**:
  - Demand: Random integers between 50 and 151 for 10 nodes over 24 hours.
  - Supply: Random integers between 200 and 501 for 3 sources over 24 hours.
  - Transmission Losses: Random values between 2% and 10% for source-node pairs.
- **EDA**:
  - Uses Matplotlib for time-series plots and Seaborn for correlation heatmaps.
- **Optimization**:
  - The genetic algorithm minimizes transmission losses while meeting demand constraints.
  - The parallel GA uses Python's `multiprocessing` module to speed up fitness evaluations.
  - A greedy baseline allocates supply to nodes heuristically for comparison.
- **Fitness Function**: Penalizes solutions that fail to meet demand (e.g., a high demand of 1,000,000 units in one node triggers a large penalty).

## Limitations
- The project uses synthetic data, which may not reflect real-world smart grid complexities.
- The greedy baseline may produce suboptimal solutions, especially with high demand penalties.
- Parallel GA performance depends on the number of CPU cores available.

## Future Improvements
- Integrate real-world smart grid data for more realistic simulations.
- Enhance the genetic algorithm with advanced mutation/crossover strategies.
- Add support for additional optimization constraints (e.g., cost, renewable energy prioritization).
- Implement interactive visualizations using Plotly or Bokeh.

## Contributing
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -m "Add your feature"`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.





*Generated on July 27, 2025*
