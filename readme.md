# GitHub Network Graph Visualization

This project visualizes a GitHub user's social coding network in interactive 2D and 3D force-directed graphs using JavaScript and WebGL.

## Features

* **2D and 3D visualizations** of GitHub user networks
* **Clickable nodes** linking to GitHub profiles
* **Right-click to remove** a node and its downstream connections
* **Image support** for node avatars
* **Interactive highlighting** of linked nodes and edges
* **Jupyter Notebook** to generate graph data by scraping GitHub starting from a specified user

## Live Demo

A live version of the visualizations is available via GitHub Pages:

[https://catalinplesu.github.io/github-connections-graph/](https://catalinplesu.github.io/github-connections-graph/)

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/github-network-graph.git
cd github-network-graph
```

### 2. Run a Local Server

These HTML files require a server environment to load the `graph-data.json`. Run the following command in the project root:

```bash
python -m http.server 8000
```

Then navigate to:

* [http://localhost:8000/2d.html](http://localhost:8000/2d.html) – 2D Graph
* [http://localhost:8000/3d.html](http://localhost:8000/3d.html) – 3D Graph

### 3. Generate Data

Use the provided Jupyter Notebook to scrape the GitHub network starting from any user.

```python
# Example usage in notebook
starting_user = "CatalinPlesu"
depth = 2  # Number of link levels to follow
```

Output is saved as `graph-data.json`, which the HTML visualizations use as input.

## Dependencies

* `force-graph` (via CDN)
* `d3.js` (via CDN)
* Python 3.x for running the local server and the Jupyter Notebook
* `requests`, `networkx`, and `matplotlib` in the notebook (install via `pip`)

## Notes

* Zoom with mouse wheel
* Left-click a node to open the GitHub profile in a new tab
* Right-click a node to remove it and its connections
* The 3D graph may be slow on low-end machines
