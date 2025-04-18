# Experiments with Hadoop and Spark in Docker

This project aims to measure the execution time and memory usage of a Spark application in two cluster configurations.

## Run experiments

1. Create virtual environment
    ```bash
    python3.10 -m venv experiments_venv
    source experiments_venv/bin/activate
    ```
2. Install required dependencies
    ```bash
    pip install -r requirements.txt
    ```
3. Download dataset from [Google Drive](https://drive.google.com/file/d/1r5NaERzCJXFg14J2Dvnyk4dwdY11Nikn/view?usp=sharing)

4. Run the following script
    ```
   bash run_experiments.sh
    ```
   * Sets up a cluster with 1 DataNode, loads the dataset into HDFS, and runs the Spark application (with and without optimizations)

   * Stops the cluster

   * Sets up a cluster with 3 DataNodes and repeats the experiments

## Run visualization
1. Create virtual environment
    ```bash
    python3.10 -m venv visualization_venv
    source visualization_venv/bin/activate
    ```
2. Install required dependencies
    ```bash
    pip install -r spark_app/requirements.txt
    ```
3. Run the following script
   ```bash
   python visualize_results.py
   ```
   > Image will be put to the `output` directory.

## Demonstration of the results

The charts show that optimizations have sped up table operations, although they have added an overhead at the beginning.

![image](results/ops_time.png)
![image](results/total_time.png)
![image](results/memory_usage_series.png)
![image](results/final_memory_usage.png)
