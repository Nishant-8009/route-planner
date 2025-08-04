# Travel Route Planner

A C++ program that finds optimal routes between world capitals using Dijkstra's algorithm and generates interactive map visualizations.

## Key Features
- Finds fastest or cheapest routes (plane costs 3x more)
- Supports plane, bus, and train transport
- Generates HTML maps with route visualization
- Works via command line or interactive prompts

## Data Structure
- **Graph**: Cities (nodes) connected by routes (edges)
- **Location**: Capital city with geo-coordinates
- **Route**: Connection with transport type, time, and cost

## Usage
```bash
# Command line:
./travel cities.csv routes.csv output.html Paris Tokyo cheapest

# Interactive:
./travel
> Enter cities file: cities.csv
> Enter routes file: routes.csv
> Output file: trip.html
> Origin: Paris
> Destination: Tokyo
> Preference: cheapest
```

## Output
- Interactive HTML map showing:
  - Route path
  - Stop markers
  - Transport details on click

## Future Improvements
- Add more transport options
- Web/mobile interface
- Real-time data integration
