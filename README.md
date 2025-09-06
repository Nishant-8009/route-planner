# 🚀 City Route Planner with Dijkstra + Google Maps

This project computes the **shortest path between two cities** (based on either **time** or **cost**) and visualizes it on **Google Maps** inside an automatically generated `output.html` file.

It combines:

* **Graph algorithms (Dijkstra)** for pathfinding
* **CSV parsing** for loading cities and routes
* **Google Maps API** for visualization

---

## 📂 Project Structure

* **`main.cpp`** → Entry point. Handles input, runs Dijkstra, calls output generator.
* **`graphfunctions.h`** → Defines `Graph` class, adjacency helpers, and Dijkstra’s algorithm.
* **`Location.h`** → Defines the `Location` class (city node with coordinates and Dijkstra metadata).
* **`Route.h`** → Defines the `Route` class (connection between two cities with cost/time).
* **`fileoperations.h`** →

  * `locationParser` → Parses city CSV file.
  * `routeParser` → Parses route CSV file.
  * `outputGenerator` → Creates **output.html** with Google Maps visualization.
* **`parser.h`** → Duplicate CSV parsing utilities (without HTML output).

---

## 📊 Input Files

### 1. Cities File (CSV)

Format:

```
Country, City, Latitude, Longitude
India, Delhi, 28.61, 77.20
India, Mumbai, 19.07, 72.87
```

### 2. Routes File (CSV)

Format:

```
Origin, Destination, Type, Time, Cost, Note
Delhi, Mumbai, Plane, 2, 5000, Express Flight
Delhi, Jaipur, Train, 5, 800, Superfast
```

---

## ⚙️ How It Works

1. **Parse data** → Loads cities and routes from CSV files.
2. **Build graph** → Cities = nodes, Routes = edges.
3. **Run Dijkstra** → Finds shortest path (minimizing **time** or **cost**).
4. **Reconstruct path** → Uses stacks of cities and routes.
5. **Generate HTML** → Visualizes the path on Google Maps with markers, polylines, and info windows.

---

## ▶️ Usage

### Compile:

```bash
g++ main.cpp -o route_planner
```

### Run:

```bash
./route_planner cities.csv routes.csv output.html "Delhi" "Mumbai" cheapest
```

Arguments:

1. `cities.csv` → file with locations
2. `routes.csv` → file with routes
3. `output.html` → output visualization file
4. `Origin City`
5. `Destination City`
6. Preference → `"cheapest"` or `"fastest"`

---

## 🌍 Output

* An **`output.html`** file is generated.
* Open it in any browser → Google Maps will show:

  * Markers for start & destination cities.
  * Polyline along the shortest path.
  * Travel info (time/cost/mode) on click.

---

## 🛠️ Tech Stack

* **C++** → Core logic & algorithms
* **Dijkstra’s Algorithm** → Shortest path
* **Google Maps JavaScript API** → Visualization
* **CSV Parsing** → Input handling

---

## 📌 Example

Input:

```
Origin: Delhi
Destination: Mumbai
Preference: cheapest
```

Output:

* Shortest-cost path calculated with Dijkstra.
* `output.html` generated → Open in browser → Displays route map.

---

## ✅ Features

* Shortest path based on **time** or **cost**
* Multi-transport support (plane, train, etc.)
* Interactive Google Maps visualization
* Flexible CSV-based input
