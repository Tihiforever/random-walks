# Random Walks on Curved Surfaces

An exploration of Random Walks and how they are used and can be manipulated.

---

## Work Log

**09/02/26:** We decided that I would program a random walk 2D generator, after halfterm to discuss on a Microsoft Teams call what else can be added and done.

**10/02/26:** Created my git repository and thought about the design of it and after a short discussion with my maths teacher he suggested I learn polar coordinates and that made me think about how this project is like an ant walking on a piece of paper that is twisted in lots of different ways, as that's how random walking in a 2D shape is, as the 2D grid when in a non-Euclidean form allows for different rules of shapes when a 2D plane is twisted and stretched in a 3D or higher dimension, like how some scientists think the universe is. This allowed me to think about how I would program this.

**11/03/26:** Finished everything outlined, waiting for a response as to what to do next. I have visualised random walking on a 3D torus, but it doesn't work truly as the walker can go inside the torus, which I visualised in Desmos ([here](https://www.desmos.com/3d/j2sfzxhzr9)).

**17/03/26:** Had a discussion on Microsoft Teams explaining my work and the basics of a random walk, and how it is utilised, like in modelling gas particles in physics, taking the walker to be a particle in a gas, it moves around randomly. We also discussed how a random walk in 1D follows a binomial distribution and, after an infinite number of steps, approaches a normal distribution. After this, we discussed what to do next, where it was decided to record lots of random walkers and their distances from an origin and then plot this data relative to the number of steps taken and explore the trend and how the number of steps correlates to the distance from the origin. Then we discussed comparing this infinite plane to a bounded 2D torus and how the distance from the start changes when the walker can "loop" around, and graphing this to compare the difference.

**23/03/26:** Created a second visualisation that allowed more customisability like adding extra walkers and changing step size, along with changing the number of steps it can complete. Annoyingly, I can't upload the files, only screenshots, as this GitHub repo is set to the first prototype and idk how to change it, but I will try to fix this.

| | |
|---|---|
| ![image](https://github.com/user-attachments/assets/c1bcbf98-a538-48df-b94e-eea0567dbedf) | ![image](https://github.com/user-attachments/assets/27c59b96-e5f9-4c8f-8094-127d4138f170) |

<video src="https://github.com/user-attachments/assets/a894a74e-201b-47da-bbde-043958e76675" controls width="100%" muted autoplay>
</video>


**18/04/26:** Built a dedicated data collection simulator that could be configured for the number of steps and walkers, exporting a CSV per walker with step, x, y, and distance from origin. Positions are normalised so the origin is always (0, 0) and step size is always 1 unit regardless of pixel size, making data from different runs directly comparable. Also started building the Python script to visualise all collected data. Shown below is the 1000 walker, 10000 step simulation completing, and an example of the newer visualiser with 100 walkers and 100 steps.

| | |
|---|---|
| ![image](https://github.com/user-attachments/assets/021205e1-d7e6-471c-9b50-6504b26c1546) | ![image](https://github.com/user-attachments/assets/ceb19982-2f55-4758-b4b1-de1d8ad539b4) |

<video src="https://github.com/user-attachments/assets/c6406bc6-54a2-444c-830b-aaab9d1bed41" controls width="100%" muted autoplay>
</video>


**19/04/26:** Used a Python script to compile all collected data and generate graphs, making it easier to visualise. Finished making the README look nice and uploaded everything to GitHub Pages.

---

## To-Do

- [x] Build a random walk visualiser
- [x] Run multiple walkers simultaneously
- [x] Record distance from origin and write to CSV
- [x] Allow unbounded random walk
- [x] Graph data from CSV files — average distance vs steps, heatmaps
- [x] Build bounded torus mode and compare to unbounded plane
- [ ] Vary torus size and compare results
- [ ] Explore regular tilings (square, triangular, hexagonal)
- [ ] Explore uniform and non-uniform tilings
- [ ] Try to figure out how distances change on curved surfaces

---

## Self Exploration

I have discovered a love for geometry and topology, and how distances are affected on curved surfaces. This led me to research how random walks are used in different dimensions. In 1D, over a large number of steps, the walker forms a binomial distribution, which approaches a normal distribution over an infinite number of steps.

When exploring random walking in 2D, I discovered the representation of pi as a random walk and how it changes when the length of pi changes, the base of pi changes, and the difference between using mod 4 and not.

| | |
|---|---|
| ![image](https://github.com/user-attachments/assets/8858199a-2968-462e-981f-6f1479e1cbf3) | ![image](https://github.com/user-attachments/assets/69ce5432-f65e-4436-9710-f09959a051a5) |
| Base: 10 · Digits: 6070 | Base: 4 · Digits: 7700 |
| ![image](https://github.com/user-attachments/assets/5eeac821-4a4a-4be1-b2df-3cb10b1e8b95) | ![image](https://github.com/user-attachments/assets/6576582c-546d-4123-a8bb-d2d31e1a132d) |
| Base: 2 · Digits: 2090 | Base: 10 · Digits: 300 |

<video src="https://github.com/user-attachments/assets/a570904e-4ef5-4def-ab40-8af0d44794f6" controls width="100%" muted autoplay>
</video>


Thinking about what different surfaces a random walker could move on led me naturally into geometry. A classic football is a great example of this, as it's covered by pentagons and hexagons stitched together, which is actually a truncated icosahedron, one of the 13 [Archimedean solids](https://en.wikipedia.org/wiki/Archimedean_solid). Archimedean solids are convex polyhedra whose faces are regular polygons and whose vertices are all identical. In 3D, the football's surface is a finite tiling of two polygon types. This made me think about what happens when you flatten that idea out onto an infinite plane.

This led me to [Euclidean tilings by convex regular polygons](https://en.wikipedia.org/wiki/Euclidean_tilings_by_convex_regular_polygons). There are only 3 regular tilings of the plane (where every tile is the same regular polygon): the triangular (3⁶), square (4⁴), and hexagonal (6³) tilings. Beyond those, there are 8 semiregular or Archimedean tilings which use two or more types of regular polygons, but with every vertex identical. The hexagonal tiling is particularly interesting because it is the most efficient way to divide a plane into equal areas with the least perimeter, which is why honeycombs use it. A random walker on a triangular tiling has 6 neighbours at each vertex, on a square tiling has 4, and on a hexagonal tiling has only 3, and that difference in vertex degree directly changes how quickly the walker can spread out, which is exactly what this project investigates.

From tilings, I then discovered [tessellations](https://en.wikipedia.org/wiki/Tessellation) more broadly, the covering of a surface using one or more geometric shapes with no gaps or overlaps. Tessellations extend far beyond regular polygons into aperiodic tilings like Penrose tilings, which never repeat but still fill the plane perfectly, and into hyperbolic geometry where the rules of Euclidean space no longer apply. This opened up the question of what a random walk looks like on a non-repeating or hyperbolic surface, which feeds directly into the later stages of this project.

---

# Results - 2D Unbounded Plane

> 1000 walkers simulated on a 2D square lattice across five runs, recording average distance from origin, distribution of final positions, and final position density at each step count.

---

## Log-Log Gradients

| Steps | Gradient | Theory | R² |
|-------|----------|--------|----|
| 100 | 0.4992 | 0.5000 | 0.99903 |
| 500 | 0.4908 | 0.5000 | 0.99955 |
| 1000 | 0.5073 | 0.5000 | 0.99943 |
| 5000 | 0.4941 | 0.5000 | 0.99965 |
| 10000 | 0.5108 | 0.5000 | 0.99967 |

All gradients are within 2% of the theoretical value of **0.5**, with R² > 0.999 in every case, confirming the √n relationship.

---

## Mean Final Distance vs √n

| Steps (n) | Mean final distance | √n (theory) | % error |
|-----------|-------------------|-------------|---------|
| 100 | 9.02 | 10.00 | 9.8% |
| 500 | 19.42 | 22.36 | 13.1% |
| 1000 | 28.46 | 31.62 | 10.0% |
| 5000 | 61.65 | 70.71 | 12.8% |
| 10000 | 91.17 | 100.00 | 8.8% |

The mean consistently sits slightly below √n, this is expected as distance is always positive and the distribution is right-skewed, pulling the mean below the RMS value.

---

## Overall Data Summary

The three plots below show all five runs together. The combined line graph shows every run following the same √n curve regardless of step count. The two scatter plots show the average distance per run with ±1 standard deviation error bars, with the first using only the final step distance and the second averaging across all steps.

| Combined line — all runs |
|--------------------------|
| <img width="1500" height="900" alt="combined_line" src="https://github.com/user-attachments/assets/ae12294c-18bc-4994-a3a2-5cd6c419d771" />

| Average final distance per run |
|------------------------------------------|
| <img width="1500" height="900" alt="combined_scatter_final" src="https://github.com/user-attachments/assets/a6c83f84-07fb-4269-b1d2-ff21312c68f4" />
 

| Average distance across all steps per run |
|------------------------------------------|
| <img width="1500" height="900" alt="combined_scatter_overall" src="https://github.com/user-attachments/assets/ebe65b2d-d8f6-4fdc-8c25-af46e14be1a7" />
 

---

## Average Distance vs Steps

The average distance grows as a smooth √n curve in all five runs. The blue line is the simulation data and the dashed line is the √n reference.

| 100 steps | 500 steps |
|-----------|-----------|
| ![image](https://github.com/user-attachments/assets/69392823-8435-40cf-a1bd-cba1e75e5290) | ![image](https://github.com/user-attachments/assets/62e0d474-422b-4f32-9cb0-b8c591b647bf) |

| 1000 steps | 5000 steps | 10000 steps |
|------------|------------|-------------|
| ![image](https://github.com/user-attachments/assets/541738ae-db8b-4071-b0a9-dc59272c5413) | ![image](https://github.com/user-attachments/assets/47f6c7af-624f-4ff1-8097-e6086677e66d) | ![image](https://github.com/user-attachments/assets/7d06e99a-adf9-4ec9-be4e-b6c4e6f38ba3) |

---

## Log-Log Plots

A straight line with a gradient of 0.5 on a log-log plot is the mathematical proof of √n growth.

| 100 steps | 500 steps |
|-----------|-----------|
| ![image](https://github.com/user-attachments/assets/9a651942-d1f4-4af7-918b-0aa223be16eb) | ![image](https://github.com/user-attachments/assets/560606ee-a11a-4c85-bd02-ae03fcab2308) |

| 1000 steps | 5000 steps | 10000 steps |
|------------|------------|-------------|
| ![image](https://github.com/user-attachments/assets/67249730-5c0b-40af-8069-dcf8856b824e) | ![image](https://github.com/user-attachments/assets/a7147b2a-f160-46ba-a573-3b25a91de88d) | ![image](https://github.com/user-attachments/assets/3d8d1e66-b003-47f1-8fc3-cab28efe4df8) |

---

## Distribution of Final Distances

The final distances follow a right-skewed distribution in all runs, with the peak shifting right as step count increases. The mean (orange) sits slightly above the median (green) in every case due to the long tail.

| 100 steps | 500 steps |
|-----------|-----------|
| ![image](https://github.com/user-attachments/assets/d9a72f8e-5f88-4d83-8690-fe6011a9931c) | ![image](https://github.com/user-attachments/assets/072a0576-a6f5-49fd-a4da-be9ef4ed818f) |

| 1000 steps | 5000 steps | 10000 steps |
|------------|------------|-------------|
| ![image](https://github.com/user-attachments/assets/99cd7196-f687-4b0a-a26a-7201d8c84213) | ![image](https://github.com/user-attachments/assets/29aada13-3724-496d-86d9-4875ef88b30c) | ![image](https://github.com/user-attachments/assets/8bbeeb1a-8450-4451-8d78-46ec888a28f5) |

---

## Final Position Heatmaps

The density of final positions forms a symmetric blob centred on the origin. The dotted white circle marks the expected RMS distance √n, the high-density region sits inside this circle in every run, visually confirming the √n relationship.

| 100 steps | 500 steps |
|-----------|-----------|
| ![image](https://github.com/user-attachments/assets/d9dada0f-1087-4529-a7c1-e66f7d43f82b) | ![image](https://github.com/user-attachments/assets/3de8755d-29b7-4d79-acd8-55d49e6d50b0) |

| 1000 steps | 5000 steps | 10000 steps |
|------------|------------|-------------|
| ![image](https://github.com/user-attachments/assets/2fbc3f26-231f-45db-8653-d9547e8ef1d6) | ![image](https://github.com/user-attachments/assets/5af32c77-e565-44b4-a55b-ecb3610e1734) | ![image](https://github.com/user-attachments/assets/311b0df7-da3b-4a2d-9b2f-2d649037ad2c) |

---

## Key Result

On an unbounded 2D plane, the average distance from the origin grows proportional to **√n** regardless of the number of steps taken. This is confirmed by:
- Log-log gradients all within 2% of 0.5
- R² > 0.999 across all runs
- Radially symmetric final position density with spread matching √n
- Right-skewed final distance distribution with mean tracking √n

This serves as the **baseline** for comparison against the bounded 2D torus, where the wrapping geometry is expected to cause the distance to plateau rather than grow indefinitely.

---
---

# Results - 2D Bounded Torus

After confirming the √n relationship on the unbounded 2D plane, I wanted to see what happens when the plane is made finite but still allows the walker to move continuously without hitting an actual edge. This led me to the idea of a bounded 2D torus.

Instead of stopping the walker when it reaches an edge, the edges are joined together. This means that if a walker moves past the maximum x coordinate, it reappears at the minimum x coordinate, and the same happens in the y direction. This makes the surface bounded but means the walker can continue walking forever.

I kept the same basic setup as the unbounded simulations so that the results could be compared directly. Each simulation uses 1000 walkers, 5000 steps per walker, and a step size of 1. The only thing I change between runs is the size of the torus.

The torus sizes I chose were **5, 10, 25, 50, 100, and 200**, where a torus of size L has coordinates from -L to L in both directions.

This means that the total width of the coordinate system is 2L, rather than L. I chose a range of sizes so that the smaller tori should reach their bounded behaviour much faster, while the larger tori should behave more like the unbounded plane for longer.

---

## Torus Size 5

The first torus I tested had a size of 5, giving a coordinate range of -5 to 5 in both directions.

<img width=500 height=500 alt="5_final_position_heatmap" src="https://github.com/user-attachments/assets/3694ca34-4069-4a2d-8dcb-5463f5352f8c" />


The heatmap is already very different from the unbounded plane. Instead of producing a roughly circular cloud which continues spreading outwards, the walkers are confined to the finite torus.

Because the edges are joined together, the corners of this graph are not actually further away from the origin in the way they would be on a normal square. The distance is calculated using the shortest route around the torus, so moving past one edge effectively brings the walker back around from the opposite side.

The maximum possible distance from the origin is

\[
r_{\max}=\sqrt{5^2+5^2}=\sqrt{50}\approx7.07.
\]

This is already much smaller than the expected distance on an unbounded plane after 5000 steps:

\[
\sqrt{5000}\approx70.7.
\]

This shows why I expected the behaviour of the torus to be very different once the walker has had enough time to explore it.

### Average Distance vs Steps

<img width="1000" height="600" alt="torus_5_avg_distance" src="https://github.com/user-attachments/assets/909a8209-8815-414f-99c5-6260fa424036" />


The average distance initially increases very quickly. However, it then reaches a value of roughly **4.2** and stays around this value for the rest of the simulation.

The mean final distance was:

\[
\boxed{4.21}
\]

This is the first major difference from the unbounded plane. On the unbounded plane the average distance continues to increase as the number of steps increases, following the √n relationship. On the size 5 torus, the average distance reaches a plateau because the walker cannot keep getting further away from the origin.

This suggests that there are two different stages to the random walk on the torus. At the beginning, the walker behaves similarly to the unbounded random walk because it has not yet explored enough of the torus for the boundaries to have much effect. Eventually, however, the finite size of the torus becomes important and the average distance settles towards a constant value.

### Log-Log Plot

<img width="1000" height="600" alt="torus_5_loglog" src="https://github.com/user-attachments/assets/53731d57-801d-416e-83cc-287abc4b6945" />


The log-log graph gives a gradient of

\[
\boxed{0.0133}
\]

with an \(R^2\) value of

\[
\boxed{0.10115}.
\]

This is very different from the gradient of approximately 0.5 found for the unbounded plane.

However, I don't think it would be correct to say that the torus has a random-walk exponent of 0.0133. The graph clearly isn't a straight line. The initial part of the graph increases and then becomes almost horizontal, so fitting one power law across the whole simulation doesn't describe the actual behaviour particularly well.

Instead, this shows that the √n relationship breaks down on a small bounded torus. The important feature is the transition from growth to a plateau.

### Distribution of Final Distances

<img width="1000" height="600" alt="torus_5_final_distribution" src="https://github.com/user-attachments/assets/3b83b74b-d509-495a-b656-72ae787c456b" />

The final distance distribution is also very different from the unbounded case.

The mean final distance was **4.21**, while the median was **4.47**.

The walkers are spread across the possible distances on the torus rather than forming the long right-hand tail seen in the unbounded simulations. There is also a clear upper limit because the distance cannot exceed approximately 7.07.

This supports the idea that after 5000 steps the walkers have explored a large part of this small torus rather than simply continuing to move away from the origin.

---

## Torus Size 10

The next torus I tested had a size of 10, giving a coordinate range of -10 to 10 in both directions.

<img width="500" height="500" alt="10_final_position_heatmap" src="https://github.com/user-attachments/assets/fd6ec491-28dc-400a-ac11-0824be549367" />


The heatmap shows the same general behaviour as the size 5 torus, although the walkers are now spread over a larger area.

Because the edges are joined together, the corners of this graph are still not simply the furthest points from the origin. The distance is calculated using the shortest route around the torus, so moving past one edge effectively brings the walker back around from the opposite side.

The maximum possible distance from the origin is

$$
r_{\max}=\sqrt{10^2+10^2}=\sqrt{200}\approx14.14.
$$

This is still much smaller than the expected distance on an unbounded plane after 5000 steps:

$$
\sqrt{5000}\approx70.7.
$$

This shows that although the size 10 torus is larger than the size 5 torus, the walkers are still confined to a finite region.

### Average Distance vs Steps

<img width="1000" height="600" alt="torus_10_avg_distance" src="https://github.com/user-attachments/assets/92a11596-dc2f-4ae3-a1ce-9d2297ce28fc" />


The average distance again initially increases very quickly. However, it then reaches a value of roughly **8** and stays around this value for the rest of the simulation.

The mean final distance was:

$$
\boxed{8.10}
$$

This is very similar to the behaviour seen on the size 5 torus. The main difference is that the larger torus allows the walkers to move further from the origin before the effects of the finite boundaries become dominant.

The same two stages can therefore be seen here. Initially, the walkers behave more like an unbounded random walk because they have not yet explored enough of the torus for the boundaries to have much effect. Eventually, the finite size of the torus becomes important and the average distance settles towards a constant value.

### Log-Log Plot

<img width="1000" height="600" alt="torus_10_loglog" src="https://github.com/user-attachments/assets/609657d2-8a33-41b4-b98c-71e61b712f45" />


The log-log graph gives a gradient of

$$
\boxed{0.0460}
$$

with an \(R^2\) value of

$$
\boxed{0.28037}.
$$

Again, this is much smaller than the gradient of approximately 0.5 found for the unbounded plane.

However, as with the size 5 torus, I don't think it would be correct to say that the torus has a random-walk exponent of 0.0460. The graph clearly isn't a straight line. The average distance initially increases before gradually becoming almost horizontal, so fitting one power law across the whole simulation does not describe the actual behaviour particularly well.

Instead, this shows that the \(\sqrt{n}\) relationship breaks down on a bounded torus. The important feature is the transition from initial growth to a plateau.

### Distribution of Final Distances

<img width="1000" height="600" alt="torus_10_final_distribution" src="https://github.com/user-attachments/assets/dfd1e932-9a93-444f-a10f-e30aecc66bdb" />

The final distance distribution is spread over a much larger range than for the size 5 torus, with distances reaching approximately **14**, which agrees with the calculated maximum distance of 14.14.

The mean final distance was **8.10**, while the median was **8.49**.

The larger range of possible distances is expected because the size 10 torus allows the walkers to get further from the origin before reaching the maximum possible distance. However, there is still a clear upper limit because of the finite size of the torus.

Overall, the results are very similar to those of the size 5 torus, but the larger torus allows the walkers to reach greater distances before settling into the same kind of plateau behaviour.

---

## Torus Size 25

The next torus I tested had a size of 25, giving a coordinate range of -25 to 25 in both directions.

<img width="500" height="500" alt="25_final_position_heatmap" src="https://github.com/user-attachments/assets/a5f5c762-4fe1-4672-8596-f9bfacb67950" />

The heatmap shows the same general behaviour as the smaller tori, although the walkers are now spread over a much larger area.

Because the edges are joined together, the corners of this graph are still not simply the furthest points from the origin. The distance is calculated using the shortest route around the torus, so moving past one edge effectively brings the walker back around from the opposite side.

The maximum possible distance from the origin is

\[
r_{\max}=\sqrt{25^2+25^2}=\sqrt{1250}\approx35.36.
\]

This is still smaller than the expected distance on an unbounded plane after 5000 steps:

\[
\sqrt{5000}\approx70.7.
\]

This shows that the size 25 torus gives the walkers considerably more space to spread out before the effects of the finite boundaries become dominant.

### Average Distance vs Steps

<img width="1000" height="600" alt="torus_25_avg_distance" src="https://github.com/user-attachments/assets/e4e4ea5c-7dd0-49f9-87ec-6219296826d8" />

The average distance initially increases very quickly. It then continues increasing more gradually before reaching a value of roughly **19.5** and staying around this value for the rest of the simulation.

The mean final distance was:

\[
\boxed{19.57}
\]

This is substantially larger than the mean final distances for the size 5 and size 10 tori. This is because the larger torus allows the walkers to travel further from the origin before the finite boundaries begin to limit their distance.

The same two stages can still be seen here. Initially, the walkers behave similarly to an unbounded random walk, with the average distance increasing as the number of steps increases. Eventually, the walkers have explored enough of the torus that the finite size becomes important and the average distance approaches a plateau.

### Log-Log Plot

<img width="1000" height="600" alt="torus_25_loglog" src="https://github.com/user-attachments/assets/90fe09f4-87ce-4d9e-a27e-3081d8859be3" />

The log-log graph gives a gradient of

\[
\boxed{0.1703}
\]

with an \(R^2\) value of

\[
\boxed{0.65383}.
\]

This is still smaller than the gradient of approximately 0.5 found for the unbounded plane, although it is noticeably larger than the gradients found for the size 5 and size 10 tori.

However, I don't think it would be correct to say that the torus has a random-walk exponent of 0.1703. The graph is not a straight line across the whole simulation. The average distance initially follows a period of growth before gradually flattening out, so fitting one power law across the whole simulation does not describe the actual behaviour particularly well.

Instead, this shows that the \(\sqrt{n}\) relationship eventually breaks down on a bounded torus. The important feature is the transition from growth to a plateau.

### Distribution of Final Distances

<img width="1000" height="600" alt="torus_25_final_distribution" src="https://github.com/user-attachments/assets/6e87d2f8-8db3-4daa-b335-cca4994741e5" />

The final distance distribution is spread over a much larger range than for the smaller tori, with distances reaching approximately **35**, which agrees with the calculated maximum distance of 35.36.

The mean final distance was **19.57**, while the median was **20.22**.

The walkers are distributed across a much wider range of possible distances because the size 25 torus gives them considerably more space to explore. There is still a clear upper limit because the distance cannot exceed approximately 35.36.

Overall, the size 25 torus shows the same general behaviour as the smaller tori, but the larger size allows the walkers to spread much further from the origin before reaching the plateau. This also makes the initial growth phase more pronounced and gives a gradient closer to the expected value for an unbounded random walk, although the eventual bounded behaviour is still clearly visible.

---

## Torus Size 50

The next torus I tested had a size of 50, giving a coordinate range of -50 to 50 in both directions.

<img width="500" height="500" alt="50_final_position_heatmap" src="https://github.com/user-attachments/assets/21fabfc8-4068-4e7b-88f2-04b5c037f8a9" />

The heatmap is much more spread out than for the smaller tori. The walkers are distributed across a large proportion of the available area, showing that the larger torus gives them considerably more space to explore before the finite boundaries become dominant.

Because the edges are joined together, the corners of this graph are still not simply the furthest points from the origin. The distance is calculated using the shortest route around the torus, so moving past one edge effectively brings the walker back around from the opposite side.

The maximum possible distance from the origin is

\[
r_{\max}=\sqrt{50^2+50^2}=\sqrt{5000}\approx70.71.
\]

Interestingly, this is exactly the same as the expected distance on an unbounded plane after 5000 steps:

\[
\sqrt{5000}\approx70.7.
\]

However, this does not mean that the torus and the unbounded plane behave in the same way. The maximum possible distance on the torus is finite, whereas the unbounded plane has no upper limit. The size 50 torus is simply large enough that the walkers can behave similarly to an unbounded random walk for a much greater number of steps.

### Average Distance vs Steps

<img width="1000" height="600" alt="torus_50_avg_distance" src="https://github.com/user-attachments/assets/aa42c7db-8104-40d1-8959-db26ee0217fb" />


The average distance initially increases very quickly. It then continues to increase more gradually, eventually reaching a value of roughly **39** and remaining around this value for the rest of the simulation.

The mean final distance was:

\[
\boxed{39.22}
\]

This is substantially larger than the mean final distances for the size 5, size 10 and size 25 tori. As the size of the torus increases, the walkers can travel further from the origin before the finite boundaries begin to affect the random walk.

The graph also shows that the plateau is reached later than for the smaller tori. This is because the walkers need more steps to explore a larger torus. The initial behaviour therefore remains closer to that of an unbounded random walk for longer.

### Log-Log Plot

<img width="1000" height="600" alt="torus_50_loglog" src="https://github.com/user-attachments/assets/95e8a9d1-cb1d-4868-94bf-66b1b61234b4" />


The log-log graph gives a gradient of

\[
\boxed{0.3601}
\]

with an \(R^2\) value of

\[
\boxed{0.93175}.
\]

This is much closer to the gradient of approximately 0.5 found for the unbounded plane than the gradients found for the smaller tori.

The high \(R^2\) value also shows that a power law provides a much better fit to the data than it did for the smaller tori. However, the graph still begins to flatten towards the end of the simulation, showing that the finite size of the torus is eventually affecting the random walk.

I therefore would still not describe 0.3601 as the true random-walk exponent of the torus. Instead, it reflects the fact that most of the simulation follows approximate power-law growth, before the average distance begins approaching its maximum possible value.

### Distribution of Final Distances

<img width="1000" height="600" alt="torus_50_final_distribution" src="https://github.com/user-attachments/assets/7c1b37f2-f7ea-4120-83c0-be72ed2954d5" />


The final distance distribution is spread over a much larger range than for the smaller tori, with distances reaching approximately **70**. This is consistent with the calculated maximum distance of 70.71.

The mean final distance was **39.22**, while the median was **40.80**.

The distribution is centred around a much larger distance than for the previous tori, showing how increasing the size of the torus allows the walkers to spread further from the origin. There is still a clear upper limit, however, because the torus is finite.

Overall, the size 50 torus behaves much more like the unbounded plane than the smaller tori do. The average distance continues to grow for longer, the log-log relationship has a much stronger fit, and the final distances reach much larger values. However, the eventual plateau shows that the finite size of the torus still has an effect.

---

## Torus Size 100

The next torus I tested had a size of 100, giving a coordinate range of -100 to 100 in both directions.

<img width="500" height="500" alt="100_final_position_heatmap" src="https://github.com/user-attachments/assets/e9b0fbf3-9a84-4e6a-8654-664b27d0f4cb" />

The heatmap is much more spread out than for the smaller tori. The walkers are distributed across a large proportion of the available area, with no obvious concentration around the origin. This suggests that after 5000 steps the walkers have not yet fully explored the torus.

Because the edges are joined together, the corners of this graph are still not simply the furthest points from the origin. The distance is calculated using the shortest route around the torus, so moving past one edge effectively brings the walker back around from the opposite side.

The maximum possible distance from the origin is

\[
r_{\max}=\sqrt{100^2+100^2}=\sqrt{20000}\approx141.42.
\]

This is now much larger than the expected distance on an unbounded plane after 5000 steps:

\[
\sqrt{5000}\approx70.7.
\]

This means that the torus is large enough that the maximum possible distance is not reached during the simulation. The walkers therefore have much more freedom to behave like an unbounded random walk.

### Average Distance vs Steps

<img width="1000" height="600" alt="torus_100_avg_distance" src="https://github.com/user-attachments/assets/801a14c6-9c7d-474b-88fc-a646ff800fd4" />


The average distance continues to increase throughout the entire simulation. Unlike the smaller tori, there is no clear plateau by 5000 steps.

The mean final distance was:

\[
\boxed{58.97}
\]

This is substantially larger than the mean final distance for the size 50 torus. The walkers are able to continue spreading away from the origin because the torus is large enough that its boundaries have very little effect during the simulation.

The graph also looks much closer to the expected behaviour of an unbounded random walk. The average distance continues to increase with the number of steps rather than settling towards a constant value.

### Log-Log Plot

<img width="1000" height="600" alt="torus_100_loglog" src="https://github.com/user-attachments/assets/3b75d1af-579c-4215-ab4a-a4c2d5a314a4" />


The log-log graph gives a gradient of

\[
\boxed{0.4875}
\]

with an \(R^2\) value of

\[
\boxed{0.99813}.
\]

This is extremely close to the gradient of approximately 0.5 expected for an unbounded two-dimensional random walk.

The very high \(R^2\) value also shows that a power law provides an excellent fit to the data. Unlike the smaller tori, there is no significant flattening towards the end of the graph, so the effects of the finite boundaries are not yet strong enough to noticeably change the relationship.

This suggests that for a sufficiently large torus, the random walk can behave almost identically to the unbounded case over the timescale being tested.

### Distribution of Final Distances

<img width="1000" height="600" alt="torus_100_final_distribution" src="https://github.com/user-attachments/assets/086caec7-e271-4616-8ae5-887c9f754caa" />


The final distance distribution is spread over a much larger range than for the smaller tori, with distances reaching approximately **140**. This is close to the calculated maximum distance of 141.42.

The mean final distance was **58.97**, while the median was **57.85**.

The distribution is centred around a much larger distance than for the previous tori, reflecting the fact that the walkers have been able to spread much further from the origin. However, unlike the smaller tori, the maximum possible distance is not acting as a strong constraint on the walkers during this simulation.

Overall, the size 100 torus behaves very similarly to the unbounded plane over the 5000 steps tested. The average distance continues to increase, the log-log plot has a gradient of **0.4875**, very close to the theoretical value of 0.5, and the \(R^2\) value of **0.99813** indicates an extremely strong power-law relationship. This suggests that increasing the size of the torus delays the point at which its finite boundaries begin to affect the random walk.

---

## Torus Size 200

The next torus I tested had a size of 200, giving a coordinate range of -200 to 200 in both directions.

<img width="500" height="500" alt="200_final_position_heatmap" src="https://github.com/user-attachments/assets/9cd3d9c0-4a68-4801-a3da-18ea4df3ed6d" />


The heatmap is even more spread out than for the size 100 torus. The walkers are concentrated around the origin but have spread across a substantial area of the torus, with some walkers reaching distances of over 200 lattice units. There is no obvious concentration caused by the boundaries.

Because the edges are joined together, the corners of this graph are still not simply the furthest points from the origin. The distance is calculated using the shortest route around the torus, so moving past one edge effectively brings the walker back around from the opposite side.

The maximum possible distance from the origin is

\[
r_{\max}=\sqrt{200^2+200^2}=\sqrt{80000}\approx282.84.
\]

This is much larger than the expected distance scale after 5000 steps:

\[
\sqrt{5000}\approx70.7.
\]

This means that the torus is now sufficiently large that the maximum possible distance is very unlikely to constrain the walkers during the simulation. The walkers therefore have considerable freedom to behave like an unbounded random walk.

### Average Distance vs Steps

<img width="1000" height="600" alt="torus_200_avg_distance" src="https://github.com/user-attachments/assets/09c78b7c-188d-4f2c-b305-2bbb12624bbe" />


The average distance continues to increase throughout the entire simulation. There is no clear plateau by 5000 steps, showing that the finite boundaries of the torus are not yet having a significant effect on the average distance.

The mean final distance was:

\[
\boxed{62.57}
\]

This is slightly larger than the mean final distance for the size 100 torus. The walkers are therefore able to spread slightly further from the origin as the size of the torus increases.

The graph also looks very similar to the behaviour expected for an unbounded random walk. The average distance continues to increase with the number of steps rather than settling towards a constant value.

### Log-Log Plot

<img width="1000" height="600" alt="torus_200_loglog" src="https://github.com/user-attachments/assets/c5404fb5-05fb-4578-ad07-c3c83b40bed5" />

The log-log graph gives a gradient of

\[
\boxed{0.5004}
\]

with an \(R^2\) value of

\[
\boxed{0.99945}.
\]

This is extremely close to the gradient of approximately 0.5 expected for an unbounded two-dimensional random walk.

The \(R^2\) value is even closer to 1 than for the size 100 torus, showing that a power law provides an extremely strong fit to the data. There is also no significant flattening towards the end of the graph, indicating that the finite boundaries are having very little effect over the 5000 steps tested.

The gradient being almost exactly 0.5 suggests that the size 200 torus behaves extremely similarly to an unbounded plane over this timescale.

### Distribution of Final Distances

<img width="1000" height="600" alt="torus_200_final_distribution" src="https://github.com/user-attachments/assets/53604ee5-81f5-4a2d-b993-2b28e378de9c" />


The final distance distribution is spread over a large range, with most walkers ending relatively close to the origin but some reaching distances of over 200 lattice units. The distribution has a long tail towards larger distances.

The mean final distance was **62.57**, while the median was **59.41**.

The distribution is centred around a similar range to the size 100 torus, although the larger torus allows a small number of walkers to reach considerably further from the origin without being affected by the torus boundary.

The maximum possible distance is approximately 282.84, meaning that the observed distances remain well below the theoretical maximum for most walkers. Therefore, the boundary of the torus is not acting as a strong constraint on the distribution during this simulation.

Overall, the size 200 torus behaves very similarly to the unbounded plane over the 5000 steps tested. The average distance continues to increase, the log-log plot has a gradient of **0.5004**, almost exactly the theoretical value of 0.5, and the \(R^2\) value of **0.99945** indicates an extremely strong power-law relationship. This provides further evidence that increasing the size of the torus delays the point at which its finite boundaries begin to affect the random walk.

---

## Overall Results for the Torus

After testing torus sizes of 5, 10, 25, 50, 100 and 200, I can now compare how the size of the torus affects the behaviour of the random walk.

<img width="2000" height="900" alt="comparison_average_distance" src="https://github.com/user-attachments/assets/38278b59-34e0-4a71-90f5-e63c7b3de0e6" />


The comparison of average distance against the number of steps shows a clear transition as the torus becomes larger.

For the smallest torus sizes, the average distance increases rapidly at first before reaching a plateau. The smaller the torus, the earlier this plateau occurs. This happens because the walkers quickly encounter the boundaries of the torus, limiting how far they can become from the origin.

For the larger tori, the average distance continues to increase throughout the 5000 steps tested. The size 100 and size 200 tori show behaviour much closer to an unbounded random walk, with no obvious plateau during the simulation.

The mean final distances for the different torus sizes were approximately:

| Torus size | Mean final distance |
|---:|---:|
| 5 | 4.2 |
| 10 | 8.2 |
| 25 | 19.6 |
| 50 | 39.3 |
| 100 | 58.97 |
| 200 | 62.57 |

This shows that increasing the size of the torus allows the walkers to spread further from the origin. However, the increase becomes much smaller between sizes 100 and 200. This suggests that once the torus is sufficiently large, increasing its size further has little effect over the 5000 steps being tested.

### Power-Law Exponent

<img width="2000" height="900" alt="exponent_vs_torus_size" src="https://github.com/user-attachments/assets/60fe8605-4d88-420c-8cdd-34fc4420c483" />


To investigate the effect of the torus boundaries more quantitatively, I compared the power-law exponent obtained from the relationship

\[
r \propto n^\alpha
\]

for each torus size.

For an unbounded two-dimensional random walk, the expected exponent is approximately

\[
\alpha=0.5.
\]

The measured exponents were approximately:

| Torus size | Power-law exponent \(\alpha\) |
|---:|---:|
| 5 | 0.013 |
| 10 | 0.045 |
| 25 | 0.170 |
| 50 | 0.360 |
| 100 | 0.4875 |
| 200 | 0.5004 |

There is a very clear relationship between torus size and the measured exponent. The smallest torus has an exponent close to zero because the average distance reaches a plateau very quickly. As the torus becomes larger, the exponent increases towards the theoretical value of 0.5.

The size 100 torus gives

\[
\alpha=0.4875,
\]

while the size 200 torus gives

\[
\alpha=0.5004.
\]

Therefore, the size 200 torus produces an exponent essentially identical to the theoretical unbounded value.

This provides strong evidence that the deviation from the expected \(n^{0.5}\) relationship for smaller tori is caused by the finite size of the space rather than a change in the underlying random-walk behaviour.

### Mean Final Distance vs Torus Size

<img width="2000" height="900" alt="final_distance_vs_torus_size" src="https://github.com/user-attachments/assets/25ab410a-0348-4cb6-817a-a840802efd16" />

The mean final distance after 5000 steps also increases as the torus size increases.

For small tori, the maximum possible distance is relatively small, so the walkers become constrained by the topology of the space. Increasing the torus size allows the walkers to continue spreading before these finite-size effects become important.

The increase is particularly large between torus sizes 25 and 100. However, the difference between sizes 100 and 200 is much smaller:

\[
58.97 \rightarrow 62.57.
\]

This suggests that the random walks are approaching the behaviour expected on an unbounded plane. Once the torus is large compared with the distance typically travelled by a walker, making it even larger has relatively little effect over the fixed 5000-step simulation.

### Overall Conclusion

The results show a clear transition from strongly bounded random-walk behaviour to behaviour that closely resembles an unbounded two-dimensional random walk.

For small torus sizes, the average distance quickly reaches a plateau because the finite topology restricts how far walkers can move from the origin. This produces power-law exponents substantially below the theoretical value of 0.5.

As the torus size increases, the plateau is delayed and eventually disappears within the 5000-step simulation. At the same time, the measured power-law exponent approaches 0.5:

\[
0.013 \rightarrow 0.045 \rightarrow 0.170 \rightarrow 0.360
\rightarrow 0.4875 \rightarrow 0.5004.
\]

The size 200 torus gives an exponent of

\[
\boxed{0.5004},
\]

which is almost exactly the theoretical value for an unbounded two-dimensional random walk.

Overall, this demonstrates that the effect of the torus boundaries depends strongly on the relationship between the size of the space and the distance travelled by the walkers. A sufficiently large torus can therefore behave almost identically to an unbounded plane over a finite number of steps, while smaller tori produce increasingly strong finite-size effects.

---

## Finding an Equation for the Random Walk

Having established how the average distance changes with both the number of steps and the size of the torus, I wanted to find an equation that could describe the relationship between these variables.

For an unbounded two-dimensional random walk, the expected distance from the origin follows approximately

\[
r\propto\sqrt{n},
\]

where \(r\) is the average distance from the origin and \(n\) is the number of steps. This can be written as

\[
r=kn^{1/2},
\]

where \(k\) is a constant determined by the particular random walk.

However, the torus introduces a second variable: its size. For small tori, the walkers eventually become constrained by the finite space, causing the average distance to stop increasing. Therefore, I wanted to find a function of the form

\[
r=f(n,L),
\]

where \(L\) is the torus size.

The results suggested that the important quantity was not simply \(n\) or \(L\) individually, but their relative sizes. When \(L\) is small compared with the typical distance travelled by the random walk, the boundaries strongly affect the result. When \(L\) is large, the behaviour approaches the unbounded relationship

\[
r\propto n^{1/2}.
\]

This can be seen particularly clearly from the power-law exponents found for each torus. For sizes \(5,10,25,50,100\) and \(200\), the exponents were approximately

\[
0.013,\quad0.045,\quad0.170,\quad0.360,\quad0.4875,\quad0.5004.
\]

The exponent therefore approaches \(0.5\) as the torus becomes larger. This provided strong evidence that the torus size controls the transition between bounded and unbounded behaviour.

### Comparing the Number of Steps with the Torus Size

I first considered what determines when the boundaries of the torus should begin to matter.

For an unbounded random walk, the characteristic distance travelled after \(n\) steps is proportional to

\[
\sqrt n.
\]

The torus has a characteristic length scale given by \(L\). Therefore, a natural dimensionless quantity to compare the two is

\[
x=\frac{\sqrt n}{L}.
\]

This quantity gives a measure of how large the random walk has become compared with the available space.

If

\[
\frac{\sqrt n}{L}\ll1,
\]

then the walkers have not travelled far enough for the finite size of the torus to have much effect. The walk should therefore behave approximately like an unbounded random walk.

On the other hand, if

\[
\frac{\sqrt n}{L}
\]

becomes large, the walkers have explored a significant proportion of the torus and the finite boundaries should begin to limit the average distance.

This suggested that the equation should depend on \(n\) and \(L\) through this ratio.

I therefore rewrote the relationship in the form

\[
\frac{r}{L}
=
g\left(\frac{\sqrt n}{L}\right).
\]

This was useful because both sides are now dimensionless. It also means that results from different torus sizes can be compared using the same function.

### Finding the Shape of \(g\)

The graphs showed that the function needed to have two different limiting behaviours.

For small values of

\[
x=\frac{\sqrt n}{L},
\]

the random walk should behave like an unbounded walk. Therefore,

\[
r\approx k\sqrt n.
\]

Dividing by \(L\),

\[
\frac rL\approx k\frac{\sqrt n}{L}=kx.
\]

Therefore \(g(x)\) must initially be approximately linear.

For large \(x\), however, the average distance approaches a limiting value because the torus is finite. Therefore,

\[
\frac rL\rightarrow C
\]

for some constant \(C\).

I therefore needed a function which is approximately linear near \(x=0\), but approaches a constant as \(x\) becomes large.

The hyperbolic tangent has exactly these properties:

\[
\tanh x\approx x
\qquad\text{for small }x,
\]

while

\[
\tanh x\rightarrow1
\qquad\text{as }x\rightarrow\infty.
\]

This led me to try

\[
g(x)=C\tanh(ax),
\]

where \(C\) and \(a\) are constants which determine the precise shape and scale of the relationship. Their values can depend on the properties of the random walk being considered.

Substituting

\[
x=\frac{\sqrt n}{L}
\]

gives

\[
\frac rL
=
C\tanh\left(\frac{a\sqrt n}{L}\right),
\]

and hence

\[
\boxed{
r(n,L)
=
CL\tanh\left(\frac{a\sqrt n}{L}\right)
}
\]

### Checking the Equation

I then checked whether this equation produced the two limiting behaviours observed in the simulations.

For a large torus, or for a small number of steps,

\[
\frac{\sqrt n}{L}\ll1.
\]

Using the approximation

\[
\tanh x\approx x,
\]

the equation becomes

\[
r
\approx
CL\left(\frac{a\sqrt n}{L}\right),
\]

so

\[
r\approx Ca\sqrt n.
\]

Therefore,

\[
\boxed{r\propto\sqrt n},
\]

which is exactly the behaviour expected for an unbounded two-dimensional random walk.

For a small torus and sufficiently large \(n\),

\[
\frac{\sqrt n}{L}\gg1,
\]

so

\[
\tanh\left(\frac{a\sqrt n}{L}\right)\rightarrow1.
\]

The equation therefore approaches

\[
r\rightarrow CL.
\]

Thus the average distance approaches a constant proportional to the size of the torus, explaining the plateaus observed for the smaller tori.

This also explains the results from the simulations. The size \(5\) and \(10\) tori reach their limiting behaviour very quickly, while the size \(100\) and \(200\) tori continue to behave much more like an unbounded random walk. In particular, the size \(200\) torus produced a power-law exponent of \(0.5004\), almost exactly the theoretical value of \(0.5\).

The equation therefore provides a single mathematical model which connects the two limiting cases:

\[
\boxed{
r(n,L)
=
CL\tanh\left(\frac{a\sqrt n}{L}\right)
}
\]

with

\[
r\propto\sqrt n
\]

for an effectively unbounded walk, and

\[
r\propto L
\]

when the finite size of the torus dominates.

This gave me a mathematical explanation for the behaviour seen throughout the simulations: increasing the torus size does not change the fundamental random-walk behaviour, but instead delays the point at which the finite topology begins to constrain the walkers.

---

## Sources

- [Wikipedia - Random Walk](https://en.wikipedia.org/wiki/Random_walk)
- [Wikipedia - Torus](https://en.wikipedia.org/wiki/Torus)
- [Wikipedia - Euclidean Tilings by Convex Regular Polygons](https://en.wikipedia.org/wiki/Euclidean_tilings_by_convex_regular_polygons)
- [Wikipedia - Archimedean Solid](https://en.wikipedia.org/wiki/Archimedean_solid)
- [Wikipedia - Tessellation](https://en.wikipedia.org/wiki/Tessellation)
- [Wolfram MathWorld - Torus](https://mathworld.wolfram.com/Torus.html)
- [Wolfram MathWorld - Tessellation](https://mathworld.wolfram.com/Tessellation.html)
- [Wolfram MathWorld - Semiregular Tessellation](https://mathworld.wolfram.com/SemiregularTessellation.html)
- [REU Paper - Courbe](https://math.uchicago.edu/~may/REU2024/REUPapers/Courbe.pdf)
- [Wolfram Community](https://community.wolfram.com/groups/-/m/t/82377)
- [Math StackExchange - Parameterisation of a Torus](https://math.stackexchange.com/questions/1578756/parameterization-of-a-torus)
- [Math StackExchange - Expected Value of Random Walk](https://math.stackexchange.com/questions/103142/expected-value-of-random-walk)
- [Wired — Pi as a Random Walk](https://www.wired.com/2017/03/hey-can-find-pi-random-walk-heres/)
- [Wolfram Demonstrations — Random Walk from Digits of Pi](https://demonstrations.wolfram.com/RandomWalkGeneratedByTheDigitsOfPi/)
- [Grünbaum & Shephard — Tilings by Regular Polygons (1977)](https://doi.org/10.2307/2689529)
