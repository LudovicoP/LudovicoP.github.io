---
title: "Simulated Annealing for Global Optimization"
excerpt: "Application of simulated annealing to minimize a highly non-convex 3D function; robust convergence and tuning strategies."
collection: portfolio
---

This project applies simulated annealing to a challenging, highly non-convex 3D objective to study global optimization performance and convergence behaviour. The implementation focuses on annealing schedules, neighborhood proposals, and temperature-tuning strategies that improve the probability of finding the global minimum in repeated restarts.

Key result: empirical experiments reported ~97% convergence to the global minimum under the chosen schedule and tuning heuristics (see PDF for full experiments and diagnostics).

PDF: <a href="/pdfs/Simulated%20Annealing%20over%20highly%20non%20convex%20function.pdf" target="_blank" rel="noopener">View PDF</a>

## Methods

- Simulated annealing with adaptive temperature schedules
- Multiple restarts and convergence diagnostics
- Comparison with gradient-based local optimizers and random search
- Visualisation of the energy landscape and solution trajectories
