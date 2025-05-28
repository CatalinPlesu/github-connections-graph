# GitHub Network Graph Visualization

This project visualizes a GitHub user's social coding network in interactive 2D and 3D force-directed graphs using JavaScript and WebGL.

## Features

* Interactive **2D and 3D visualizations** of GitHub user networks
* Clickable nodes linking to GitHub profiles
* Right-click to remove a node and its downstream connections
* Node avatars with **image support** (recommended for \~300 nodes max for performance)
* Highlighting of connected nodes and links
* Jupyter Notebook to scrape and generate graph data starting from a specified user

## Live Demo

[https://catalinplesu.github.io/github-connections-graph/](https://catalinplesu.github.io/github-connections-graph/)

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/github-network-graph.git
cd github-network-graph
```

### 2. Run a Local Server

The HTML files require a server to load `graph-data.json`:

```bash
python -m http.server 8000
```

Access the visualizations at:

* [http://localhost:8000/2d.html](http://localhost:8000/2d.html) – 2D Graph (with images)
* [http://localhost:8000/2d-simple.html](http://localhost:8000/2d-simple.html) – 2D Graph (no images, better for large graphs)
* [http://localhost:8000/3d.html](http://localhost:8000/3d.html) – 3D Graph (with images)

### 3. Generate Graph Data

Use the included Jupyter Notebook to scrape GitHub starting from any user:

```python
starting_user = "CatalinPlesu"
depth = 2  # levels of connections to scrape
```

Output is saved as `graph-data.json` for visualization.

## Dependencies

* `force-graph` and `d3.js` (CDN)
* Python 3.x
* Python packages: `requests`, `networkx`, `matplotlib` (install via `pip`)

## Notes

* Zoom with mouse wheel
* Left-click a node to open the GitHub profile in a new tab
* Right-click a node to remove it and its downstream connections
* **Image-based graphs are recommended for networks of around 300 nodes or fewer to maintain performance**
* The 3D graph may be slow on low-end hardware
