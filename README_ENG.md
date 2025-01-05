# One Billion Rows: Data Processing Challenge with Python

## Introduction
The goal of this project is to demonstrate how to efficiently process a massive data file containing 1 billion rows (~16GB), specifically for calculating statistics (including aggregation and sorting, which are resource-heavy operations) using Python.

This challenge was inspired by The One Billion Row Challenge, originally proposed for Java.

The data file consists of temperature readings from various weather stations. Each record follows the format <string: station name>;<double: measurement>, with the temperature presented with one decimal point precision.

Here are ten example lines from the file:

```
Hamburg;12.0
Bulawayo;8.9
Palembang;38.8
St. Johns;15.2
Cracow;12.6
Bridgetown;26.9
Istanbul;6.2
Roseau;34.4
Conakry;31.2
Istanbul;23.0
```

The challenge is to develop a Python program capable of reading this file and calculating the minimum, mean (rounded to one decimal place), and maximum temperature for each station, displaying the results in a table sorted by station name.

| station      | min_temperature | mean_temperature | max_temperature |
|--------------|-----------------|------------------|-----------------|
| Abha         | -31.1           | 18.0             | 66.5            |
| Abidjan      | -25.9           | 26.0             | 74.6            |
| Abéché       | -19.8           | 29.4             | 79.9            |
| Accra        | -24.8           | 26.4             | 76.3            |
| Addis Ababa  | -31.8           | 16.0             | 63.9            |
| Adelaide     | -31.8           | 17.3             | 71.5            |
| Aden         | -19.6           | 29.1             | 78.3            |
| Ahvaz        | -24.0           | 25.4             | 72.6            |
| Albuquerque  | -35.0           | 14.0             | 61.9            |
| Alexandra    | -40.1           | 11.0             | 67.9            |
| ...          | ...             | ...              | ...             |
| Yangon       | -23.6           | 27.5             | 77.3            |
| Yaoundé      | -26.2           | 23.8             | 73.4            |
| Yellowknife  | -53.4           | -4.3             | 46.7            |
| Yerevan      | -38.6           | 12.4             | 62.8            |
| Yinchuan     | -45.2           | 9.0              | 56.9            |
| Zagreb       | -39.2           | 10.7             | 58.1            |
| Zanzibar City| -26.5           | 26.0             | 75.2            |
| Zürich       | -42.0           | 9.3              | 63.6            |
| Ürümqi       | -42.1           | 7.4              | 56.7            |
| İzmir        | -34.4           | 17.9             | 67.9            |
## Results

The tests were conducted on a laptop equipped with an Intel(R) Core(TM) i5-1035G1 CPU @ 1.00GHz 1.20 GHz and 8GB of RAM. The implementations used pure Python, Pandas, Polars, and DuckDB. The runtime results for processing the 1-billion-row file are presented below:

## Implementation | Time
Python |	30 minutes
Python + Pandas	| 1263.86 sec
Python + Polars	| 380.86 sec
Python + DuckDB	| 95.41 sec
Thanks to [Koen Vossen] for the Polars implementation.

Conclusion
This challenge clearly highlighted the effectiveness of various Python libraries in handling large volumes of data. Traditional methods like pure Python (30 minutes) and even Pandas (21 minutes) required a series of tactics to implement batch processing, while libraries like Polars and DuckDB proved to be exceptionally efficient, requiring fewer lines of code due to their inherent ability to distribute data in "streaming batches" more effectively. DuckDB stood out, achieving the lowest runtime thanks to its strategy for data execution and processing.

These results emphasize the importance of selecting the right tool for large-scale data analysis, demonstrating that Python, with the right libraries, is a powerful choice for tackling big data challenges.

## Considerations
This project highlights the versatility of the Python ecosystem for data processing tasks, offering valuable insights into choosing the right tools for large-scale analysis.

