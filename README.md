# CitySim: US City Route Simulator

## Overview

CitySim is a program designed to simulate and calculate routes between US cities based on their geographical locations and population. The application leverages graph theory to determine both the shortest and fastest routes between cities, using real-world geodesic distances and estimated travel times.

Developed for CS302, this project demonstrates proficiency in working with graphs, file I/O, and algorithmic problem-solving.

---

## Features

### 1. **City Data Parsing and Management**
- Parses a file of US cities (`uscities.txt`) to store information such as city names, latitude, longitude, population, and type.
- Categorizes cities into **LOCAL**, **REGIONAL**, or **NATIONAL** based on their population and proximity to other cities.

### 2. **Route Calculations**
- Implements **Dijkstra's Algorithm** to compute:
  - **Shortest Route**: Based on geodesic distances.
  - **Fastest Route**: Based on estimated travel times (flight speeds between NATIONAL cities and driving speeds otherwise).
- Outputs the sequence of cities visited, along with incremental and cumulative distances or travel times.

### 3. **City Graph and Data Tables**
- Generates a **distance table**, **time table**, and **adjacency table** to represent city relationships.
- Uses the **Haversine Formula** to calculate distances between cities, rounded to the nearest 5 miles.

### 4. **Command-Line Options**
- `-info`: Outputs information about cities, distances, and time tables to text files.
- `-dist`: Calculates the shortest route between two specified cities.
- `-time`: Calculates the fastest route between two specified cities.

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/citysim.git
   cd citysim
2. Compile the code using g++:
   ```bash
   g++ -o citysim Citysim.cpp
3. Ensure the input file **uscities.txt** is in the working directory.

---

## Usage
* Command-line Syntax
```bash
./citysim <mode> <datafile>
```
* **mode**
  * **-info:** Generate city, distance, time, and graph information files.
  * **-dist:** Compute the shortest route between two cities.
  * **-time:** Compute the fastest route between two cities.
* **datafile:** Path to **uscities.txt**.

---

## Examples
1. Generate city information files
   ```bash
   ./citysim -info uscities.txt
  This command produces the following output files:
  * **city_info.txt**: City details.
  * **city_dist.txt**: Pairwise city distances.
  * **city_time.txt**: Pairwise city travel times.
  * **city_graph.txt**: Graph representation of city connections.

2. Calculate the shortest route
   ```bash
   ./citysim -dist uscities.txt
   
