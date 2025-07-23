# Apache_Spark-Data-Processing
This project involves data processing and analysis of NYC Taxi Trips data using PySpark. The goal is to implement a data pipeline that performs cleaning, transformation, and aggregation tasks on large datasets, leveraging the distributed processing capabilities of Apache Spark.

### Datasets
- **NYC Taxi Trips Dataset**: Contains records of NYC taxi trips with attributes such as trip distance, number of passengers, origin and destination zones, and total cost.
- **NYC Zones Dataset**: Lists geographic zones within NYC used as pickup and drop-off locations for taxi trips.

### Key Tasks

The project is divided into several tasks that form a full data processing pipeline:

1. **Data Cleaning**: Removing invalid records (e.g., zero distance or no passengers) and handling outliers.
2. **Feature Engineering**: Adding new columns by joining with the zones dataset and calculating trip profitability.
3. **Zone Aggregation and Ranking**: Summarizing and ranking zones based on total trip volume, average profitability, and total passenger volume.
4. **Execution Time Measurement**: Recording total and task-specific execution times for various dataset sizes and formats.

## Project Structure

The Jupyter Notebook is structured to walk through each step of the data processing pipeline:
- **Task 0 - Data Loading**: Defines functions for loading different sizes and formats of the dataset.
- **Task 1 - Data Cleaning**: Contains functions to remove records with zero distance or no passengers and outliers.
- **Task 2 - Feature Engineering**: Joins the trips dataset with the zones dataset and calculates profitability.
- **Task 3 - Zone Aggregation**: Aggregates data by zone and ranks zones by trip volume, profitability, and passenger volume.
- **Task 4 - Pipeline Execution**: Measures execution time for different dataset sizes.

## Getting Started

### Prerequisites

- Python 3.6+
- PySpark
- Pandas
- Jupyter Notebook or JupyterLab

### Installation

To set up the environment, install the necessary packages:

```bash
pip install pyspark pandas
```

### Running the Notebook

1. Clone this repository and open the notebook `Apache_Spark_Project.ipynb` in Jupyter.
2. Set the dataset size (`'S'`, `'M'`, `'L'`, `'XL'`, `'XXL'`) and format (`'parquet'` or `'delta'`) by changing the `SIZE` and `DATA_FORMAT` variables in the notebook.
3. Run all cells to execute the pipeline for the specified dataset configuration.

### Example Usage

To run the pipeline on a small dataset in `parquet` format:

```python
SIZE = 'S'
DATA_FORMAT = 'parquet'
trips = init_trips(SIZE, DATA_FORMAT)
```

## Notes

- The project leverages the `pyspark.sql` API, and it’s recommended to use vectorized operations where possible for better performance.
- Results include summaries of the top 10 zones by trip volume, average profitability, and passenger volume.


--- 
