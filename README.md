# Random Walks

An exploration of random walks and how changing the geometry they move through affects their behaviour. I started this project looking at a basic random walk and have gradually changed the space underneath it, from an unbounded plane to a torus and then to different regular and non-uniform tilings.

---

## Work Log

**09/02/26:** We decided that I would program a random walk 2D generator, after half term to discuss on a Microsoft Teams call what else can be added and done.

**10/02/26:** Created my git repository and thought about the design of it and after a short discussion with my maths teacher he suggested I learn polar coordinates and that made me think about how this project is like an ant walking on a piece of paper that is twisted in lots of different ways, as that's how random walking in a 2D shape is, as the 2D grid when in a non-Euclidean form allows for different rules of shapes when a 2D plane is twisted and stretched in a 3D or higher dimension, similar to the way curved spaces can be used to think about the geometry of the universe. This gave me the first idea for how I wanted to approach the programming side of the project.

**11/03/26:** Finished everything outlined, waiting for a response as to what to do next. I also visualised random walking on a 3D torus, although this did not work properly because the walker could move through the surface and inside the torus. I visualised this in Desmos ([here](https://www.desmos.com/3d/j2sfzxhzr9)).

**17/03/26:** Had a discussion on Microsoft Teams explaining my work and the basics of a random walk, and how it is utilised, like in modelling gas particles in physics, taking the walker to be a particle in a gas, it moves around randomly. We also discussed how a random walk in 1D follows a binomial distribution and, after an infinite number of steps, approaches a normal distribution. After this, we discussed what to do next, where it was decided to record lots of random walkers and their distances from an origin and then plot this data relative to the number of steps taken and explore the trend and how the number of steps correlates to the distance from the origin. Then we discussed comparing this infinite plane to a bounded 2D torus and how the distance from the start changes when the walker can "loop" around, and graphing this to compare the difference.

**23/03/26:** Created a second visualisation that allowed more customisability like adding extra walkers and changing step size, along with changing the number of steps it can complete. Annoyingly, I couldn't upload the files themselves at this point, only screenshots, as this GitHub repo was still set to the first prototype. I planned to fix this later.

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

**01/09/26:** Created a Python script and adjusted the old analysis script so that I could simulate the torus and generate the graphs of all the data.

**02/09/26** Wrote up my findings on how the average distance from the origin changes with the size of the torus over a fixed number of steps.

**03/09/26** Used all of my findings to try and formulate a skeleton of a formula that relates to n (the number of steps) and L (the torus size). I did this partly to get an idea of what doing this kind of mathematical research might be like in the future. I then began to write the code for a uniform tiling and how a random walk would change along different types of non-standard lattices.

**04/09/26** I used the code I had written and improved it with the use of AI to make the simulations run faster. This also helped me understand some better programming practices and how the code could be made more efficient. I then used this data to generate all the graphs needed for the write-up.

**05/09/26** Started and finished the write-up of my findings, comparing the different types of tilings with a regular random walk. 

**06/09/26** Completed

---

## To-Do

- [x] Build a random walk visualiser
- [x] Run multiple walkers simultaneously
- [x] Record distance from origin and write to CSV
- [x] Allow unbounded random walk
- [x] Graph data from CSV files — average distance vs steps, heatmaps
- [x] Build bounded torus mode and compare to unbounded plane
- [x] Vary torus size and compare results
- [x] Explore regular tilings (square, triangular, hexagonal)
- [x] Explore uniform and non-uniform tilings
- [ ] Try to figure out how distances change on curved surfaces

---

## Self Exploration

I have discovered a love for geometry and topology, and how distances are affected on curved surfaces. This led me to research how random walks are used in different dimensions. In 1D, over a large number of steps, the walker forms a binomial distribution, which approaches a normal distribution over an infinite number of steps.

When exploring random walks in 2D, I discovered the representation of pi as a random walk and how it changes when the length of pi changes, the base of pi changes, and the difference between using mod 4 and not.

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

All gradients are within 2% of the theoretical value of **0.5**, with R² > 0.999 in every case, confirming the \(\sqrt n\) relationship.

---

## Mean Final Distance vs \(\sqrt n\)

| Steps (n) | Mean final distance | \(\sqrt n\) (theory) | % error |
|-----------|-------------------|-------------|---------|
| 100 | 9.02 | 10.00 | 9.8% |
| 500 | 19.42 | 22.36 | 13.1% |
| 1000 | 28.46 | 31.62 | 10.0% |
| 5000 | 61.65 | 70.71 | 12.8% |
| 10000 | 91.17 | 100.00 | 8.8% |

The mean consistently sits slightly below \(\sqrt n\), this is expected as distance is always positive and the distribution is right-skewed, pulling the mean below the RMS value.

---

## Overall Data Summary

The three plots below show all five runs together. The combined line graph shows every run following the same \(\sqrt n\) curve regardless of step count. The two scatter plots show the average distance per run with ±1 standard deviation error bars, with the first using only the final step distance and the second averaging across all steps.

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

The average distance grows as a smooth \(\sqrt n\) curve in all five runs. The blue line is the simulation data and the dashed line is the \(\sqrt n\) reference.

| 100 steps | 500 steps |
|-----------|-----------|
| ![image](https://github.com/user-attachments/assets/69392823-8435-40cf-a1bd-cba1e75e5290) | ![image](https://github.com/user-attachments/assets/62e0d474-422b-4f32-9cb0-b8c591b647bf) |

| 1000 steps | 5000 steps | 10000 steps |
|------------|------------|-------------|
| ![image](https://github.com/user-attachments/assets/541738ae-db8b-4071-b0a9-dc59272c5413) | ![image](https://github.com/user-attachments/assets/47f6c7af-624f-4ff1-8097-e6086677e66d) | ![image](https://github.com/user-attachments/assets/7d06e99a-adf9-4ec9-be4e-b6c4e6f38ba3) |

---

## Log-Log Plots

A straight line with a gradient of 0.5 on a log-log plot is the mathematical proof of \(\sqrt n\) growth.

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

The density of final positions forms a symmetric blob centred on the origin. The dotted white circle marks the \(\sqrt n\) reference distance, the high-density region sits inside this circle in every run, visually confirming the \(\sqrt n\) relationship.

| 100 steps | 500 steps |
|-----------|-----------|
| ![image](https://github.com/user-attachments/assets/d9dada0f-1087-4529-a7c1-e66f7d43f82b) | ![image](https://github.com/user-attachments/assets/3de8755d-29b7-4d79-acd8-55d49e6d50b0) |

| 1000 steps | 5000 steps | 10000 steps |
|------------|------------|-------------|
| ![image](https://github.com/user-attachments/assets/2fbc3f26-231f-45db-8653-d9547e8ef1d6) | ![image](https://github.com/user-attachments/assets/5af32c77-e565-44b4-a55b-ecb3610e1734) | ![image](https://github.com/user-attachments/assets/311b0df7-da3b-4a2d-9b2f-2d649037ad2c) |

---

## Key Result

On an unbounded 2D plane, the average distance from the origin grows approximately proportional to **√n**. This is confirmed by:
- Log-log gradients all within 2% of 0.5
- R² > 0.999 across all runs
- Radially symmetric final position density with spread matching \(\sqrt n\)
- Right-skewed final distance distribution with mean tracking \(\sqrt n\)

This serves as the **baseline** for comparison against the bounded 2D torus, where the wrapping geometry is expected to cause the distance to plateau rather than grow indefinitely.

---

# Results - 2D Bounded Torus

After confirming the \(\sqrt n\) relationship on the unbounded 2D plane, I wanted to see what happens when the plane is made finite but still allows the walker to move continuously without hitting an actual edge. This led me to the idea of a bounded 2D torus.

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

$$
r_{\max}=\sqrt{5^2+5^2}=\sqrt{50}\approx7.07.
$$

This is already much smaller than the expected distance on an unbounded plane after 5000 steps:

$$
\sqrt{5000}\approx70.7.
$$

This shows why I expected the behaviour of the torus to be very different once the walker has had enough time to explore it.

### Average Distance vs Steps

<img width="1000" height="600" alt="torus_5_avg_distance" src="https://github.com/user-attachments/assets/909a8209-8815-414f-99c5-6260fa424036" />


The average distance initially increases very quickly. However, it then reaches a value of roughly **4.2** and stays around this value for the rest of the simulation.

The mean final distance was:

$$
4.21
$$

This is the first major difference from the unbounded plane. On the unbounded plane the average distance continues to increase as the number of steps increases, following the \(\sqrt n\) relationship. On the size 5 torus, the average distance reaches a plateau because the walker cannot keep getting further away from the origin.

This suggests to me that there are two different stages to the random walk on the torus. At the beginning, the walker behaves similarly to the unbounded random walk because it has not yet explored enough of the torus for the boundaries to have much effect. Eventually, however, the finite size of the torus becomes important and the average distance settles towards a constant value.

### Log-Log Plot

<img width="1000" height="600" alt="torus_5_loglog" src="https://github.com/user-attachments/assets/53731d57-801d-416e-83cc-287abc4b6945" />


The log-log graph gives a gradient of

$$
0.0133
$$

with an \(R^2\) value of

$$
0.10115.
$$

This is very different from the gradient of approximately 0.5 found for the unbounded plane.

However, I don't think it would be correct to say that the torus has a random-walk exponent of 0.0133. The graph clearly isn't a straight line. The initial part of the graph increases and then becomes almost horizontal, so fitting one power law across the whole simulation doesn't describe the actual behaviour particularly well.

Instead, this shows that the \(\sqrt n\) relationship breaks down on a small bounded torus. The important feature is the transition from growth to a plateau.

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
8.10
$$

This is very similar to the behaviour seen on the size 5 torus. The main difference is that the larger torus allows the walkers to move further from the origin before the effects of the finite boundaries become dominant.

The same two stages can therefore be seen here. Initially, the walkers behave more like an unbounded random walk because they have not yet explored enough of the torus for the boundaries to have much effect. Eventually, the finite size of the torus becomes important and the average distance settles towards a constant value.

### Log-Log Plot

<img width="1000" height="600" alt="torus_10_loglog" src="https://github.com/user-attachments/assets/609657d2-8a33-41b4-b98c-71e61b712f45" />


The log-log graph gives a gradient of

$$
0.0460
$$

with an \(R^2\) value of

$$
0.28037.
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

$$
r_{\max}=\sqrt{25^2+25^2}=\sqrt{1250}\approx35.36.
$$

This is still smaller than the expected distance on an unbounded plane after 5000 steps:

$$
\sqrt{5000}\approx70.7.
$$

This shows that the size 25 torus gives the walkers considerably more space to spread out before the effects of the finite boundaries become dominant.

### Average Distance vs Steps

<img width="1000" height="600" alt="torus_25_avg_distance" src="https://github.com/user-attachments/assets/e4e4ea5c-7dd0-49f9-87ec-6219296826d8" />

The average distance initially increases very quickly. It then continues increasing more gradually before reaching a value of roughly **19.5** and staying around this value for the rest of the simulation.

The mean final distance was:

$$
19.57
$$

This is substantially larger than the mean final distances for the size 5 and size 10 tori. This is because the larger torus allows the walkers to travel further from the origin before the finite boundaries begin to limit their distance.

The same two stages can still be seen here. Initially, the walkers behave similarly to an unbounded random walk, with the average distance increasing as the number of steps increases. Eventually, the walkers have explored enough of the torus that the finite size becomes important and the average distance approaches a plateau.

### Log-Log Plot

<img width="1000" height="600" alt="torus_25_loglog" src="https://github.com/user-attachments/assets/90fe09f4-87ce-4d9e-a27e-3081d8859be3" />

The log-log graph gives a gradient of

$$
0.1703
$$

with an \(R^2\) value of

$$
0.65383.
$$

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

$$
r_{\max}=\sqrt{50^2+50^2}=\sqrt{5000}\approx70.71.
$$

Interestingly, this is exactly the same as the expected distance on an unbounded plane after 5000 steps:

$$
\sqrt{5000}\approx70.7.
$$

However, this does not mean that the torus and the unbounded plane behave in the same way. The maximum possible distance on the torus is finite, whereas the unbounded plane has no upper limit. The size 50 torus is simply large enough that the walkers can behave similarly to an unbounded random walk for a much greater number of steps.

### Average Distance vs Steps

<img width="1000" height="600" alt="torus_50_avg_distance" src="https://github.com/user-attachments/assets/aa42c7db-8104-40d1-8959-db26ee0217fb" />


The average distance initially increases very quickly. It then continues to increase more gradually, eventually reaching a value of roughly **39** and remaining around this value for the rest of the simulation.

The mean final distance was:

$$
39.22
$$

This is substantially larger than the mean final distances for the size 5, size 10 and size 25 tori. As the size of the torus increases, the walkers can travel further from the origin before the finite boundaries begin to affect the random walk.

The graph also shows that the plateau is reached later than for the smaller tori. This is because the walkers need more steps to explore a larger torus. The initial behaviour therefore remains closer to that of an unbounded random walk for longer.

### Log-Log Plot

<img width="1000" height="600" alt="torus_50_loglog" src="https://github.com/user-attachments/assets/95e8a9d1-cb1d-4868-94bf-66b1b61234b4" />


The log-log graph gives a gradient of

$$
0.3601
$$

with an \(R^2\) value of

$$
0.93175.
$$

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

The heatmap is much more spread out than for the smaller tori. The walkers are distributed across a large proportion of the available area, with no obvious concentration around the origin. This suggests to me that after 5000 steps the walkers have not yet fully explored the torus.

Because the edges are joined together, the corners of this graph are still not simply the furthest points from the origin. The distance is calculated using the shortest route around the torus, so moving past one edge effectively brings the walker back around from the opposite side.

The maximum possible distance from the origin is

$$
r_{\max}=\sqrt{100^2+100^2}=\sqrt{20000}\approx141.42.
$$

This is now much larger than the expected distance on an unbounded plane after 5000 steps:

$$
\sqrt{5000}\approx70.7.
$$

This means that the torus is large enough that the maximum possible distance is not reached during the simulation. The walkers therefore have much more freedom to behave like an unbounded random walk.

### Average Distance vs Steps

<img width="1000" height="600" alt="torus_100_avg_distance" src="https://github.com/user-attachments/assets/801a14c6-9c7d-474b-88fc-a646ff800fd4" />


The average distance continues to increase throughout the entire simulation. Unlike the smaller tori, there is no clear plateau by 5000 steps.

The mean final distance was:

$$
58.97
$$

This is substantially larger than the mean final distance for the size 50 torus. The walkers are able to continue spreading away from the origin because the torus is large enough that its boundaries have very little effect during the simulation.

The graph also looks much closer to the expected behaviour of an unbounded random walk. The average distance continues to increase with the number of steps rather than settling towards a constant value.

### Log-Log Plot

<img width="1000" height="600" alt="torus_100_loglog" src="https://github.com/user-attachments/assets/3b75d1af-579c-4215-ab4a-a4c2d5a314a4" />


The log-log graph gives a gradient of

$$
0.4875
$$

with an \(R^2\) value of

$$
0.99813.
$$

This is extremely close to the gradient of approximately 0.5 expected for an unbounded two-dimensional random walk.

The very high \(R^2\) value also shows that a power law provides an excellent fit to the data. Unlike the smaller tori, there is no significant flattening towards the end of the graph, so the effects of the finite boundaries are not yet strong enough to noticeably change the relationship.

This suggests to me that for a sufficiently large torus, the random walk can behave almost identically to the unbounded case over the timescale being tested.

### Distribution of Final Distances

<img width="1000" height="600" alt="torus_100_final_distribution" src="https://github.com/user-attachments/assets/086caec7-e271-4616-8ae5-887c9f754caa" />


The final distance distribution is spread over a much larger range than for the smaller tori, with distances reaching approximately **140**. This is close to the calculated maximum distance of 141.42.

The mean final distance was **58.97**, while the median was **57.85**.

The distribution is centred around a much larger distance than for the previous tori, reflecting the fact that the walkers have been able to spread much further from the origin. However, unlike the smaller tori, the maximum possible distance is not acting as a strong constraint on the walkers during this simulation.

Overall, the size 100 torus behaves very similarly to the unbounded plane over the 5000 steps tested. The average distance continues to increase, the log-log plot has a gradient of **0.4875**, very close to the theoretical value of 0.5, and the \(R^2\) value of **0.99813** indicates an extremely strong power-law relationship. This suggests to me that increasing the size of the torus delays the point at which its finite boundaries begin to affect the random walk.

---

## Torus Size 200

The next torus I tested had a size of 200, giving a coordinate range of -200 to 200 in both directions.

<img width="500" height="500" alt="200_final_position_heatmap" src="https://github.com/user-attachments/assets/9cd3d9c0-4a68-4801-a3da-18ea4df3ed6d" />


The heatmap is even more spread out than for the size 100 torus. The walkers are concentrated around the origin but have spread across a substantial area of the torus, with some walkers reaching distances of over 200 lattice units. There is no obvious concentration caused by the boundaries.

Because the edges are joined together, the corners of this graph are still not simply the furthest points from the origin. The distance is calculated using the shortest route around the torus, so moving past one edge effectively brings the walker back around from the opposite side.

The maximum possible distance from the origin is

$$
r_{\max}=\sqrt{200^2+200^2}=\sqrt{80000}\approx282.84.
$$

This is much larger than the expected distance scale after 5000 steps:

$$
\sqrt{5000}\approx70.7.
$$

This means that the torus is now sufficiently large that the maximum possible distance is very unlikely to constrain the walkers during the simulation. The walkers therefore have considerable freedom to behave like an unbounded random walk.

### Average Distance vs Steps

<img width="1000" height="600" alt="torus_200_avg_distance" src="https://github.com/user-attachments/assets/09c78b7c-188d-4f2c-b305-2bbb12624bbe" />


The average distance continues to increase throughout the entire simulation. There is no clear plateau by 5000 steps, showing that the finite boundaries of the torus are not yet having a significant effect on the average distance.

The mean final distance was:

$$
62.57
$$

This is slightly larger than the mean final distance for the size 100 torus. The walkers are therefore able to spread slightly further from the origin as the size of the torus increases.

The graph also looks very similar to the behaviour expected for an unbounded random walk. The average distance continues to increase with the number of steps rather than settling towards a constant value.

### Log-Log Plot

<img width="1000" height="600" alt="torus_200_loglog" src="https://github.com/user-attachments/assets/c5404fb5-05fb-4578-ad07-c3c83b40bed5" />

The log-log graph gives a gradient of

$$
0.5004
$$

with an \(R^2\) value of

$$
0.99945.
$$

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

This shows that increasing the size of the torus allows the walkers to spread further from the origin. However, the increase becomes much smaller between sizes 100 and 200. This suggests to me that once the torus is sufficiently large, increasing its size further has little effect over the 5000 steps being tested.

### Power-Law Exponent

<img width="2000" height="900" alt="exponent_vs_torus_size" src="https://github.com/user-attachments/assets/60fe8605-4d88-420c-8cdd-34fc4420c483" />


To investigate the effect of the torus boundaries more quantitatively, I compared the power-law exponent obtained from the relationship

$$
r \propto n^\alpha
$$

for each torus size.

For an unbounded two-dimensional random walk, the expected exponent is approximately

$$
\alpha=0.5.
$$

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

$$
\alpha=0.4875,
$$

while the size 200 torus gives

$$
\alpha=0.5004.
$$

Therefore, the size 200 torus produces an exponent essentially identical to the theoretical unbounded value.

This provides strong evidence that the deviation from the expected \(n^{0.5}\) relationship for smaller tori is caused by the finite size of the space rather than a change in the underlying random-walk behaviour.

### Mean Final Distance vs Torus Size

<img width="2000" height="900" alt="final_distance_vs_torus_size" src="https://github.com/user-attachments/assets/25ab410a-0348-4cb6-817a-a840802efd16" />

The mean final distance after 5000 steps also increases as the torus size increases.

For small tori, the maximum possible distance is relatively small, so the walkers become constrained by the topology of the space. Increasing the torus size allows the walkers to continue spreading before these finite-size effects become important.

The increase is particularly large between torus sizes 25 and 100. However, the difference between sizes 100 and 200 is much smaller:

$$
58.97 \rightarrow 62.57.
$$

This suggests to me that the random walks are approaching the behaviour expected on an unbounded plane. Once the torus is large compared with the distance typically travelled by a walker, making it even larger has relatively little effect over the fixed 5000-step simulation.

### Overall Conclusion

The results show a clear transition from strongly bounded random-walk behaviour to behaviour that closely resembles an unbounded two-dimensional random walk.

For small torus sizes, the average distance quickly reaches a plateau because the finite topology restricts how far walkers can move from the origin. This produces power-law exponents substantially below the theoretical value of 0.5.

As the torus size increases, the plateau is delayed and eventually disappears within the 5000-step simulation. At the same time, the measured power-law exponent approaches 0.5:

$$
0.013 \rightarrow 0.045 \rightarrow 0.170 \rightarrow 0.360
\rightarrow 0.4875 \rightarrow 0.5004.
$$

The size 200 torus gives an exponent of

$$
0.5004,
$$

which is almost exactly the theoretical value for an unbounded two-dimensional random walk.

Overall, this demonstrates that the effect of the torus boundaries depends strongly on the relationship between the size of the space and the distance travelled by the walkers. A sufficiently large torus can therefore behave almost identically to an unbounded plane over a finite number of steps, while smaller tori produce increasingly strong finite-size effects.

---

## Finding an Equation for the Random Walk

Having established how the average distance changes with both the number of steps and the size of the torus, I wanted to find an equation that could describe the relationship between these variables.

For an unbounded two-dimensional random walk, the expected distance from the origin follows approximately

$$
r\propto\sqrt{n},
$$

where \(r\) is the average distance from the origin and \(n\) is the number of steps. This can be written as

$$
r=kn^{1/2},
$$

where \(k\) is a constant determined by the particular random walk.

However, the torus introduces a second variable: its size. For small tori, the walkers eventually become constrained by the finite space, causing the average distance to stop increasing. Therefore, I wanted to find a function of the form

$$
r=f(n,L),
$$

where \(L\) is the torus size.

The results suggested that the important quantity was not simply \(n\) or \(L\) individually, but their relative sizes. When \(L\) is small compared with the typical distance travelled by the random walk, the boundaries strongly affect the result. When \(L\) is large, the behaviour approaches the unbounded relationship

$$
r\propto n^{1/2}.
$$

This can be seen particularly clearly from the power-law exponents found for each torus. For sizes \(5,10,25,50,100 and 200\), the exponents were approximately

$$
0.013,\quad0.045,\quad0.170,\quad0.360,\quad0.4875,\quad0.5004.
$$

The exponent therefore approaches \(0.5\) as the torus becomes larger. This provided strong evidence that the torus size controls the transition between bounded and unbounded behaviour.

### Comparing the Number of Steps with the Torus Size

I first considered what determines when the boundaries of the torus should begin to matter.

For an unbounded random walk, the characteristic distance travelled after \(n\) steps is proportional to

$$
\sqrt n.
$$

The torus has a characteristic length scale given by \(L\). Therefore, a natural dimensionless quantity to compare the two is

$$
x=\frac{\sqrt n}{L}.
$$

This quantity gives a measure of how large the random walk has become compared with the available space.

If

$$
\frac{\sqrt n}{L}\ll1,
$$

then the walkers have not travelled far enough for the finite size of the torus to have much effect. The walk should therefore behave approximately like an unbounded random walk.

On the other hand, if

$$
\frac{\sqrt n}{L}
$$

becomes large, the walkers have explored a significant proportion of the torus and the finite boundaries should begin to limit the average distance.

This suggested that the equation should depend on \(n\) and \(L\) through this ratio.

I therefore rewrote the relationship in the form

$$
\frac{r}{L}=g\left(\frac{\sqrt n}{L}\right).
$$

This was useful because both sides are now dimensionless. It also means that results from different torus sizes can be compared using the same function.

### Finding the Shape of \(g\)

The graphs showed that the function needed to have two different limiting behaviours.

For small values of

$$
x=\frac{\sqrt n}{L},
$$

the random walk should behave like an unbounded walk. Therefore,

$$
r\approx k\sqrt n.
$$

Dividing by \(L\),

$$
\frac rL\approx k\frac{\sqrt n}{L}=kx.
$$

Therefore \(g(x)\) must initially be approximately linear.

For large \(x\), however, the average distance approaches a limiting value because the torus is finite. Therefore,

$$
\frac rL\rightarrow C
$$

for some constant \(C\).

I therefore needed a function which is approximately linear near \(x=0\), but approaches a constant as \(x\) becomes large.

The hyperbolic tangent has the two properties I needed:

$$
\tanh x\approx x
\qquad\text{for small }x,
$$

while

$$
\tanh x\rightarrow1
\qquad\text{as }x\rightarrow\infty.
$$

This led me to try the simple model

$$
g(x)=C\tanh(ax),
$$

where \(C\) and \(a\) are constants that determine the precise shape and scale of the relationship. Their values can depend on the properties of the random walk being considered.

Substituting

$$
x=\frac{\sqrt n}{L}
$$

gives

$$
\frac{r}{L}=C\tanh\left(\frac{a\sqrt n}{L}\right)
$$

and hence

$$
r(n,L)=CL\tanh\left(\frac{a\sqrt n}{L}\right)
$$

### Checking the Equation

I then checked whether this equation produced the two limiting behaviours observed in the simulations.

For a large torus, or for a small number of steps,

$$
\frac{\sqrt n}{L}\ll1.
$$

Using the approximation

$$
\tanh x\approx x,
$$

the equation becomes

$$
r
\approx
CL\left(\frac{a\sqrt n}{L}\right),
$$

so

$$
r\approx Ca\sqrt n.
$$

Therefore,

$$
r\propto\sqrt n,
$$

which is exactly the behaviour expected for an unbounded two-dimensional random walk.

For a small torus and sufficiently large \(n\),

$$
\frac{\sqrt n}{L}\gg1,
$$

so

$$
\tanh\left(\frac{a\sqrt n}{L}\right)\rightarrow1.
$$

The equation therefore approaches

$$
r\rightarrow CL.
$$

Thus the average distance approaches a constant proportional to the size of the torus, explaining the plateaus observed for the smaller tori.

This also explains the results from the simulations. The size \(5\) and \(10\) tori reach their limiting behaviour very quickly, while the size \(100\) and \(200\) tori continue to behave much more like an unbounded random walk. In particular, the size \(200\) torus produced a power-law exponent of \(0.5004\), almost exactly the theoretical value of \(0.5\).

The equation therefore provides a single mathematical model which connects the two limiting cases:

$$
r(n,L)=CL\tanh\left(\frac{a\sqrt n}{L}\right)
$$

with

$$
r\propto\sqrt n
$$

for an effectively unbounded walk, and

$$
r\propto L
$$

when the finite size of the torus dominates.

This gave me a mathematical explanation for the behaviour seen throughout the simulations: increasing the torus size does not change the fundamental random-walk behaviour, but instead delays the point at which the finite topology begins to constrain the walkers.

---

# Results - Uniform Tilings

Having established how a random walk behaves on both an unbounded plane and a bounded torus, I wanted to investigate what happens when the underlying lattice itself is changed.

Up to this point, all of my two-dimensional random walks had been performed on a square lattice, where each vertex has four possible neighbouring positions. I wanted to see whether changing the geometry and number of neighbours would change the behaviour of the random walk.

This led me to investigate different types of tilings. A tiling covers a surface using geometric shapes without gaps or overlaps, and changing the tiling changes the structure of the lattice that the walker moves across.

I first investigated **uniform tilings**, where every vertex has the same local arrangement. This means that although the lattice can have a different structure from the square lattice, the walker encounters the same type of environment everywhere.

For this investigation, I tested two different uniform tilings and compared their behaviour with the square lattice used in the earlier experiments.

The main questions I wanted to investigate were:

- Does the average distance still follow a \(\sqrt n\) relationship?
- How does changing the number of possible directions affect the average distance?
- Does the distribution of final distances change?
- Does the spatial distribution of the walkers change with the lattice?
- Can the results be explained by the same underlying random-walk behaviour?

The simulations were kept consistent so that the results could be compared directly. Each simulation used **1000 walkers**, with each walker taking **5000 steps**.

---

## Triangle Tiling

The first uniform tiling I investigated was the **triangle tiling**.

Unlike the square lattice, where each vertex has four neighbouring vertices, the triangular lattice has **six neighbouring vertices** at each point. This gives the walker six possible directions in which it can move at every step.

I kept the same number of walkers and steps as in the previous simulations, using 1000 walkers and 5000 steps per walker.

### Average Distance vs Steps

<img width="1000" height="600" alt="triangle_average_distance" src="https://github.com/user-attachments/assets/0ad5b7f4-12b9-46b2-9276-8357351ba818" />


The average distance from the origin increases throughout the simulation. Unlike the bounded torus simulations, there is no plateau, as the triangular lattice is unbounded and the walkers can continue moving away from the origin.

The average distance reaches approximately **63.4** after 5000 steps.

The graph has a similar overall shape to the \(\sqrt n\) relationship observed for the square lattice. The rate of increase becomes smaller as the number of steps increases, which is consistent with square-root growth.

This suggests to me that changing the local structure of the lattice has not removed the underlying random-walk behaviour.

### Log-Log Plot

<img width="1000" height="600" alt="triangle_loglog" src="https://github.com/user-attachments/assets/0282d489-28f6-4231-9e28-21585ca328d3" />


The log-log graph gives a power-law relationship of

$$
r\propto n^{0.5047}
$$

with an \(R^2\) value of

$$
0.99913.
$$

The measured exponent of **0.5047** is extremely close to the theoretical value of **0.5** found for the square lattice.

The difference from 0.5 is approximately **0.0047**, meaning that the measured exponent differs from the expected value by less than 1%.

The \(R^2\) value of **0.99913** also shows that the power-law relationship provides an extremely strong fit to the data.

I found this particularly interesting because the triangular lattice has a different local structure from the square lattice and gives the walker six possible directions instead of four. Despite this, the exponent describing how the distance grows with the number of steps remains approximately the same.

This suggests to me that the change in lattice affects the scale of the random walk rather than fundamentally changing the relationship between distance and the number of steps.

### Distribution of Final Distances

<img width="1000" height="600" alt="triangle_final_distribution" src="https://github.com/user-attachments/assets/d5ab4ad7-26cc-4352-9863-a25b7ef4b3ad" />

The final distance distribution is right-skewed, with most walkers finishing relatively close to the centre and a smaller number travelling considerably further.

The mean final distance was

$$
63.40
$$

while the median was

$$
58.59.
$$

The mean being larger than the median is consistent with the long right-hand tail of the distribution, where a smaller number of walkers reach much larger distances.

The largest observed distances extend beyond **200 lattice units**, although these are reached by only a small number of walkers.

This is similar to the distribution observed for the square-lattice random walk. The distribution is not concentrated around a single distance, but instead has a broad range of possible final distances because each walker takes a different random path.

### Final Position Heatmap

<img width="500" height="500" alt="triangle_final_position_heatmap" src="https://github.com/user-attachments/assets/ae6a743c-105d-41ff-a212-c2a1145cbe97" />


The final position density is concentrated around the origin, with the density gradually decreasing as the distance from the origin increases.

The overall distribution is approximately symmetric around the origin. This is expected because there is no preferred direction in the random walk, so over a large number of walkers the movement in different directions should balance out.

There are also a small number of lower-density regions further from the origin, corresponding to walkers that happened to travel much further than the majority.

The overall shape is similar to the density observed for the square lattice. The walkers form a concentrated central region with a decreasing density towards larger distances.

### Comparison with the Square Lattice

The most significant result from the triangular tiling is that the relationship between average distance and number of steps appears to remain approximately

$$
r\propto\sqrt n.
$$

For the triangular lattice, the measured exponent was

$$
\alpha=0.5047,
$$

compared with approximately

$$
\alpha=0.5
$$

for the square lattice.

The \(R^2\) value of **0.99913** also shows that the relationship is extremely close to a power law.

Therefore, despite changing the lattice from four neighbours to six neighbours, the fundamental scaling behaviour of the random walk appears to remain the same.

The main difference is expected to appear in the constant of proportionality rather than the exponent. In other words, changing the lattice can change how far the walker typically travels after a given number of steps without necessarily changing the fact that the distance grows approximately with \(\sqrt n\).

This gives a useful first result for the investigation of different lattices: the local geometry of the lattice can change the behaviour of the random walk, but the underlying square-root relationship appears to be much more general than just the square lattice.

---

## Hexagonal Tiling

The second uniform tiling I investigated was the **hexagonal tiling**. Unlike the triangular tiling, where each vertex has 6 neighbours, each vertex in a hexagonal tiling has only **3 neighbours**.

This gives a useful comparison with the triangular tiling, as they have very different numbers of possible directions at each step while both remaining uniform tilings of the plane.

Again, I simulated **1000 walkers for 5000 steps**, recording the distance from the origin and the final position of each walker.

### Average Distance vs Steps

<img width="1000" height="600" alt="hexagon_average_distance" src="https://github.com/user-attachments/assets/fb95148c-9809-491e-850e-2e7855e50407" />


The average distance increases throughout the simulation, with no sign of the plateau seen on the bounded torus. This is expected as the hexagonal tiling is an unbounded lattice, so the walker can continue moving away from the origin indefinitely.

After 5000 steps, the average distance is approximately **64.26**.

The overall shape of the graph is very similar to both the square and triangular lattice results. The gradient decreases as the number of steps increases, suggesting that the distance is again following a square-root type relationship.

### Log-Log Plot

<img width="1000" height="600" alt="hexagon_loglog" src="https://github.com/user-attachments/assets/c2f7ecd3-0fad-4846-bd95-c4b2c3a28b6e" />

The log-log plot gives a power-law relationship of

$$
r\propto n^{0.5073}
$$

with

$$
R^2=0.99985.
$$

The measured exponent of **0.5073** is very close to the theoretical value of **0.5** found for an ordinary unbounded random walk.

The difference from 0.5 is only **0.0073**, while the extremely high \(R^2\) value shows that the power-law model fits the data very closely.

I found this particularly interesting because the hexagonal tiling has only 3 possible directions at each vertex, compared with 4 for the square lattice and 6 for the triangular lattice. Despite this difference, the exponent remains very close to \(0.5\).

### Distribution of Final Distances

<img width="1000" height="600" alt="hexagon_final_distribution" src="https://github.com/user-attachments/assets/f7d908da-c51d-4f34-83f2-46c5c7bfc4cc" />

The distribution of final distances is again right-skewed, with most walkers ending relatively close to the origin and a smaller number travelling much further.

The mean final distance was

$$
64.26
$$

and the median was

$$
59.92.
$$

As with the triangular tiling, the mean is greater than the median due to the long right-hand tail of the distribution.

The distribution extends to distances of over **200 lattice units**, although only a very small number of walkers reached these distances.

### Final Position Heatmap

<img width="500" height="500" alt="hexagon_final_position_heatmap" src="https://github.com/user-attachments/assets/1ac62a7e-833f-4f3a-9037-10559020c711" />

The final position density is concentrated around the origin and gradually decreases further away from it.

The distribution remains approximately centred around the origin, with no overall preferred direction. This is expected from the symmetry of the hexagonal lattice and the random choice of direction at each step.

The heatmap also shows a similar overall structure to the triangular tiling. Most walkers remain within a central region, while a smaller number spread much further from the origin.

### Initial Findings

The results from the hexagonal tiling are surprisingly similar to those from the triangular tiling.

Despite the large difference in the number of neighbours, both produce an average distance which follows approximately the same power-law behaviour:

$$
r\propto\sqrt n.
$$

For the hexagonal tiling,

$$
r\propto n^{0.5073},
$$

while for the triangular tiling,

$$
r\propto n^{0.5047}.
$$

Both exponents are extremely close to \(0.5\). This suggests to me that changing the number of neighbours changes the scale of the random walk, but may not change its fundamental dependence on the number of steps.

The next step is therefore to compare the two uniform tilings directly and see whether the differences between them are significant despite their almost identical power-law exponents.

### Comparison with a Standard Random Walk

Perhaps the most significant result is how closely the walks on both uniform tilings resemble a standard two-dimensional random walk.

For a standard unbounded two-dimensional random walk, the typical distance from the origin scales as

$$
r \propto \sqrt{n}
$$

giving a theoretical power-law exponent of

$$
\alpha = \frac{1}{2}.
$$

The results from both tilings agree remarkably well with this behaviour. The triangular tiling gives

$$
\alpha \approx 0.5047
$$

while the hexagonal tiling gives

$$
\alpha \approx 0.5073.
$$

Both values are extremely close to the standard random-walk value of $0.5$. The log-log plots are also almost perfectly linear, with $R^2$ values above $0.999$.

This suggests to me that, despite the different local geometry of the triangular and hexagonal tilings, the random walks behave almost identically to a standard two-dimensional random walk when viewed on a large scale.

The individual paths are constrained by the geometry of their respective tilings, but these local differences appear to average out over many steps. The overall statistical behaviour therefore remains essentially the same: the average distance grows approximately as $\sqrt{n}$.

## Conclusion

The comparison between the two uniform tilings shows that the large-scale behaviour of a random walk is remarkably robust to changes in the underlying regular geometry.

Both the triangular and hexagonal tilings produce:

- Almost identical average-distance curves.
- Power-law behaviour extremely close to $r \propto \sqrt{n}$.
- Power-law exponents very close to $\alpha = 0.5$.
- Very high $R^2$ values for the power-law fits.
- Behaviour that is almost indistinguishable from a standard two-dimensional random walk.

|||
|--|--|
|<img width="1000" height="600" alt="comparison_loglog" src="https://github.com/user-attachments/assets/6eca7c10-e404-4c3f-92d2-e405ae0ada5d" /> |
| <img width="1000" height="600" alt="comparison_average_distance" src="https://github.com/user-attachments/assets/68c7f036-8789-4de1-b7c7-a41f2c23ecc1" /> |

This gives a useful baseline for the next stage of the investigation. If these regular geometries all produce the same large-scale behaviour, the next thing I wanted to know was whether removing that regularity would make a bigger difference.

This gave me the next question for the project: if regular tilings still give the same large-scale behaviour, what happens when the local geometry is no longer the same everywhere? This led me to investigate **non-uniform tilings**.

# Results - Non-Uniform Tilings

Having established how closely different uniform tilings reproduce the behaviour of a standard two-dimensional random walk, I wanted to investigate what happens when the regularity of the lattice itself is removed.

For the uniform tilings, every vertex has the same local arrangement, meaning that the walker encounters the same geometry throughout the entire space. I wanted to see whether changing this so that the local geometry varies across the lattice would produce a measurable change in the behaviour of the random walk.

I therefore investigated **three different non-uniform tilings**, where different types of polygons and local arrangements occur throughout the lattice.

The main questions I wanted to investigate were:

- Does the average distance still follow a \(\sqrt n\) relationship?
- Does changing the local geometry affect the power-law exponent?
- Does the distribution of final distances change?
- Does the spatial distribution of the walkers change?
- Do non-uniform tilings still behave almost identically to a standard two-dimensional random walk?

As with the uniform tilings, the simulations were kept consistent so that the results could be compared directly. Each simulation used **1000 walkers**, with each walker taking **5000 steps**.

---

## Trihexagonal Tiling

The first non-uniform tiling I investigated was the **trihexagonal tiling**.

Unlike the uniform tilings considered previously, the trihexagonal tiling contains both triangles and hexagons. This means that the walker no longer encounters exactly the same local geometry everywhere.

This gives me a first test of whether introducing variation into the underlying geometry actually changes the behaviour of a random walk.

### Average Distance vs Steps

<img width="1000" height="600" alt="trihexagonal_average_distance" src="https://github.com/user-attachments/assets/d31f5676-a8ee-485f-9db4-a7c6a4bafb1c" />

The average distance from the origin increases throughout the simulation, with no plateau as the tiling is unbounded and the walkers can continue moving away from the origin.

After 5000 steps, the average distance is approximately **64.94**.

The overall shape of the graph is very similar to the results from the uniform tilings. The gradient decreases as the number of steps increases, suggesting that the average distance is again following a square-root type relationship.

This is already an interesting result, as introducing non-uniformity into the geometry does not appear to have fundamentally changed the way the average distance grows.

### Log-Log Plot

<img width="1000" height="600" alt="trihexagonal_loglog" src="https://github.com/user-attachments/assets/939d2360-4ed5-4bb7-85e9-7c6fd547862b" />


The log-log plot gives a power-law relationship of

$$
r\propto n^{0.5141}
$$

with

$$
R^2=0.99917.
$$

The measured exponent of **0.5141** is slightly larger than the theoretical value of **0.5** for a standard two-dimensional random walk.

However, the difference is still relatively small. The exponent remains close enough to $0.5$ to suggest that the underlying $\sqrt n$ behaviour has largely been preserved despite the non-uniform geometry.

The extremely high \(R^2\) value of **0.99917** also shows that the power-law relationship provides an excellent fit to the data.

This is particularly interesting when compared with the uniform tilings. The triangular and hexagonal tilings produced exponents of approximately **0.5047** and **0.5073** respectively, while the trihexagonal tiling gives **0.5141**. Although this is a slightly larger deviation from $0.5$, it is still very close to the behaviour of a standard random walk.

### Distribution of Final Distances

<img width="1000" height="600" alt="trihexagonal_final_distribution" src="https://github.com/user-attachments/assets/36841b2d-3c01-4d62-a404-b34cebe0a1cc" />


The distribution of final distances is again right-skewed, with most walkers finishing relatively close to the origin and a smaller number travelling considerably further.

The mean final distance was

$$
64.94
$$

while the median was

$$
58.98.
$$

As with the uniform tilings, the mean is greater than the median due to the long right-hand tail of the distribution.

The distribution also extends to distances of approximately **250 lattice units**, although only a very small number of walkers reached these distances.

Overall, the distribution remains broadly similar to those produced by the uniform tilings. This suggests that the introduction of non-uniform geometry has not dramatically changed the range of distances reached by the walkers.

### Final Position Heatmap

<img width="500" height="500" alt="trihexagonal_final_position_heatmap" src="https://github.com/user-attachments/assets/d616db1d-7d81-4b8e-ad66-764300da21df" />


The final position density is concentrated around the origin, with the majority of walkers remaining within a central region. However, unlike the heatmaps from the uniform tilings, the distribution is **not perfectly circular**.

Instead, the density appears somewhat elongated and irregular, with certain directions extending further from the origin than others.

This could be a consequence of the non-uniform geometry of the trihexagonal tiling. Since the walker encounters different local arrangements of triangles and hexagons, the available paths through the lattice are not locally identical everywhere. Although there is no intentional preferred direction in the random walk, these differences in local geometry could introduce small directional effects which accumulate over many steps.

Another possibility is that the different local structures affect how easily walkers can move through different regions of the lattice. This could produce the slightly stretched or uneven shape seen in the heatmap rather than the approximately circular distribution expected from a standard two-dimensional random walk.

However, this difference in shape does not appear to correspond to a major change in the overall scaling behaviour. The average-distance curve still follows an extremely strong power law with an exponent close to $0.5$.

This suggests to me that the non-uniform geometry may affect the **shape of the spatial distribution** more strongly than it affects the fundamental relationship between distance and the number of steps.

### Initial Findings

The first non-uniform tiling therefore produces a surprisingly similar result to the uniform tilings.

The average distance still follows approximately

$$
r\propto\sqrt n,
$$

with a measured exponent of

$$
\alpha=0.5141.
$$

Although this is slightly further from $0.5$ than the exponents measured for the triangular and hexagonal tilings, it is still remarkably close to the standard random-walk value.

At the same time, the final-position heatmap shows a more noticeable difference. Rather than forming an approximately circular distribution, the walkers produce a somewhat elongated and irregular density pattern.

This suggests to me that non-uniform geometry may not immediately change the fundamental scaling law of the random walk, but it may begin to affect the finer details of how the walkers are distributed across space.

The remaining two non-uniform tilings will therefore show whether this is a feature specific to the trihexagonal tiling or whether it represents a more general effect of removing the regularity of the lattice.

## Snub Square Tiling

The final non-uniform tiling I investigated was the **snub square tiling**.

Like the other non-uniform tilings, the snub square tiling contains more than one type of polygon, meaning that the local geometry encountered by the walker is not identical everywhere.

This provides another test of whether changing the local structure of the underlying geometry affects the behaviour of a random walk.

### Average Distance vs Steps

<img width="1000" height="600" alt="snub_square_average_distance" src="https://github.com/user-attachments/assets/45d3e2b8-7a2b-464b-98b5-1f39796a57bd" />


The average distance from the origin increases throughout the simulation, with no plateau as the tiling is unbounded and the walkers can continue moving away from the origin.

After 5000 steps, the average distance is approximately **60.74**.

The overall shape of the graph is again very similar to the results from both the uniform tilings and the other non-uniform tilings. The gradient decreases as the number of steps increases, suggesting that the average distance is again following a square-root type relationship.

This provides further evidence that introducing non-uniformity into the geometry does not fundamentally change the way the average distance grows.

### Log-Log Plot

<img width="1000" height="600" alt="rhombitrihexagonal_loglog" src="https://github.com/user-attachments/assets/24b63267-153f-41d0-ad56-e58b9e109548" />


The log-log plot gives a power-law relationship of

$$
r\propto n^{0.4904}
$$

with

$$
R^2=0.99959.
$$

The measured exponent of **0.4904** is slightly smaller than the theoretical value of **0.5** for a standard two-dimensional random walk.

However, the difference is very small. The exponent is still extremely close to $0.5$, suggesting that the underlying $\sqrt n$ behaviour has largely been preserved despite the non-uniform geometry.

The extremely high \(R^2\) value of **0.99959** also shows that the power-law relationship provides an excellent fit to the data.

Interestingly, the snub square tiling produces the smallest exponent of the three non-uniform tilings investigated. The trihexagonal tiling produced an exponent of **0.5141**, while the rhombitrihexagonal tiling produced **0.5074**. The snub square tiling therefore gives

$$
0.4904 < 0.5,
$$

while the other two produce values slightly above $0.5$.

Despite these differences, all three values remain very close to the standard random-walk exponent of $0.5$.

### Distribution of Final Distances

<img width="1000" height="600" alt="snub_square_final_distribution" src="https://github.com/user-attachments/assets/7e68af21-c22b-448f-811b-ac5c0f148a68" />


The distribution of final distances is again right-skewed, with most walkers finishing relatively close to the origin and a smaller number travelling considerably further away.

The mean final distance was

$$
60.74
$$

while the median was

$$
55.67.
$$

As with the other tilings, the mean is greater than the median because of the long right-hand tail of the distribution. A smaller number of walkers travel substantially further from the origin, increasing the mean relative to the median.

Overall, the distribution remains broadly similar to those produced by the other tilings. This suggests to me that, despite the different local geometry of the snub square tiling, the overall statistical behaviour of the walkers remains similar.

### Final Position Heatmap

<img width="500" height="500" alt="snub_square_final_position_heatmap" src="https://github.com/user-attachments/assets/5d4891a1-893e-43e2-bd00-6e87508cbf40" />

The final position density is concentrated around the origin, with the majority of walkers remaining within a central region.

As with the trihexagonal tiling, the distribution is not perfectly circular. Instead, there are some irregularities and directional variations in the density.

This may be a consequence of the non-uniform geometry of the snub square tiling. Since the walker encounters different local arrangements of polygons, the available paths through the lattice are not locally identical everywhere. These differences could produce small directional effects which accumulate over many steps.

The heatmap therefore provides another example of the geometry affecting the finer details of the random walk without producing a major change in its overall scaling behaviour.

The average-distance results support this interpretation. Despite the irregularity in the final-position distribution, the average distance still follows an extremely strong power law with an exponent very close to $0.5$.

This suggests to me that, once again, the non-uniform geometry may affect the **shape of the spatial distribution** more noticeably than it affects the fundamental relationship between distance and the number of steps.

### Initial Findings

The snub square tiling produces a surprisingly similar result to the uniform tilings.

The average distance still follows approximately

$$
r\propto\sqrt n,
$$

with a measured exponent of

$$
\alpha=0.4904.
$$

Although this is slightly below the theoretical value of $0.5$, the difference is small, and the extremely high \(R^2\) value of **0.99959** shows that the power-law relationship is an excellent fit to the data.

The final-position density also shows some irregularity compared with the more symmetrical distributions produced by the uniform tilings. This suggests to me that the non-uniform geometry may have a greater effect on the spatial distribution of the walkers than on the fundamental relationship between distance and the number of steps.

The results give another indication that introducing non-uniformity into the tiling does not fundamentally alter the $\sqrt n$ scaling behaviour of a random walk.

The next non-uniform tiling I investigated was the **rhombitrihexagonal tiling**, providing another opportunity to test whether these observations remain consistent across different non-uniform geometries.

## Rhombitrihexagonal Tiling

The third non-uniform tiling I investigated was the **rhombitrihexagonal tiling**.

Like the trihexagonal tiling, the rhombitrihexagonal tiling contains multiple types of polygons. In this case, the tiling contains triangles, squares and hexagons. This means that the walker no longer encounters exactly the same local geometry everywhere.

This gives another test of whether changing the local geometry actually affects the behaviour of the random walk.

### Average Distance vs Steps

<img width="1000" height="600" alt="rhombitrihexagonal_average_distance" src="https://github.com/user-attachments/assets/1fe4cd48-df32-4587-8d30-18dcdffe5c50" />


The average distance from the origin increases throughout the simulation, with no plateau as the tiling is unbounded and the walkers can continue moving away from the origin.

After 5000 steps, the average distance is approximately **62.93**.

The overall shape of the graph is very similar to the results from the uniform tilings. The gradient decreases as the number of steps increases, suggesting that the average distance is again following a square-root type relationship.

This is another interesting result, as introducing non-uniformity into the geometry does not appear to have fundamentally changed the way the average distance grows.

### Log-Log Plot

<img width="1000" height="600" alt="rhombitrihexagonal_loglog" src="https://github.com/user-attachments/assets/a758d7c3-a489-46e3-994b-98f72253a3f7" />


The log-log plot gives a power-law relationship of

$$
r\propto n^{0.5074}
$$

with

$$
R^2=0.99944.
$$

The measured exponent of **0.5074** is slightly larger than the theoretical value of **0.5** for a standard two-dimensional random walk.

However, the difference is still relatively small. The exponent remains close enough to $0.5$ to suggest that the underlying $\sqrt n$ behaviour has largely been preserved despite the non-uniform geometry.

The extremely high \(R^2\) value of **0.99944** also shows that the power-law relationship provides an excellent fit to the data.

This is particularly interesting when compared with the uniform tilings. The triangular and hexagonal tilings produced exponents of approximately **0.5047** and **0.5073** respectively, while the trihexagonal tiling gives **0.5141**. The rhombitrihexagonal tiling gives **0.5074**, which is remarkably close to the exponents obtained for the uniform tilings.

### Distribution of Final Distances

<img width="1000" height="600" alt="rhombitrihexagonal_final_distribution" src="https://github.com/user-attachments/assets/959a6347-d8d9-4f5a-b383-0651ef7408d6" />


The distribution of final distances is again right-skewed, with most walkers finishing relatively close to the origin and a smaller number travelling considerably further.

The mean final distance was

$$
62.93
$$

while the median was

$$
58.83.
$$

As with the uniform tilings, the mean is greater than the median due to the long right-hand tail of the distribution.

The distribution also extends to distances of approximately **180 lattice units**, although only a very small number of walkers reached these distances.

Overall, the distribution remains broadly similar to those produced by the uniform tilings. This suggests that the introduction of non-uniform geometry has not dramatically changed the range of distances reached by the walkers.

### Final Position Heatmap

<img width="500" height="500" alt="rhombitrihexagonal_final_position_heatmap" src="https://github.com/user-attachments/assets/4c10ed17-7e4a-4b58-9634-ddae9b5c2447" />


The final position density is concentrated around the origin, with the majority of walkers remaining within a central region. However, unlike the heatmaps from the uniform tilings, the distribution is **not perfectly circular**.

Instead, the density appears somewhat irregular, with some directions extending further from the origin than others.

This could be a consequence of the non-uniform geometry of the rhombitrihexagonal tiling. Since the walker encounters different local arrangements of triangles, squares and hexagons, the available paths through the lattice are not locally identical everywhere. Although there is no intentional preferred direction in the random walk, these differences in local geometry could introduce small directional effects which accumulate over many steps.

Another possibility is that the different local structures affect how easily walkers can move through different regions of the lattice. This could produce the uneven shape seen in the heatmap rather than the approximately circular distribution expected from a standard two-dimensional random walk.

However, this difference in shape does not appear to correspond to a major change in the overall scaling behaviour. The average-distance curve still follows an extremely strong power law with an exponent very close to $0.5$.

### Comparison

The most striking result from comparing the three tilings is how similar they are despite having different local geometries. The trihexagonal tiling produces the largest average distance and the largest exponent, while the snub square tiling produces the smallest average distance and exponent. The rhombitrihexagonal tiling lies between them.

|||
|--|--|
|<img width="1000" height="600" alt="comparison_average_distance" src="https://github.com/user-attachments/assets/188f5194-7f90-41fb-980a-72703605fe41" />|
|<img width="1000" height="600" alt="comparison_loglog" src="https://github.com/user-attachments/assets/e12fdc66-8017-4891-875b-c01050389a0f" />|
|<img width="800" height="600" alt="power_law_exponents" src="https://github.com/user-attachments/assets/06c7e7da-7d67-457e-adda-1a4b7f650e22" />|

However, all three remain extremely close to the classical random-walk scaling relationship

$$
r \propto \sqrt{n}.
$$



This suggests to me that changing the local geometry of the non-uniform tiling changes the rate of spreading slightly, but does not fundamentally change the diffusive nature of the random walk. At large scales, the walkers appear to retain the same $\sqrt{n}$ behaviour as an ordinary random walk, despite moving across considerably more complicated geometries.

---

## Overall Comparison

Having investigated random walks on a standard lattice, followed by uniform tilings and finally non-uniform tilings, I can now compare how changing the underlying geometry affects the behaviour of the walk.

### Standard Random Walk

The standard random walk provides the baseline for the investigation. In an unbounded two-dimensional random walk, the average distance from the origin follows the familiar relationship

$$
r \propto \sqrt{n},
$$

where $r$ is the average distance from the origin and $n$ is the number of steps.

This gives a power-law exponent of approximately

$$
\alpha = 0.5.
$$

The standard walk therefore provides a useful reference against which the more complicated geometries can be compared.

### Uniform Tilings

The next step was to replace the standard lattice with different uniform tilings. Although these tilings have different local structures and numbers of neighbouring vertices, the overall behaviour remained remarkably similar.

The average distance continued to increase approximately as $\sqrt{n}$, with the main differences appearing in the constant of proportionality rather than in the overall scaling behaviour.

This suggested that the square-root behaviour of a random walk is not specific to the standard square lattice.

### Non-Uniform Tilings

The investigation was then extended to non-uniform tilings, where the local geometry is no longer the same everywhere. The trihexagonal, rhombitrihexagonal and snub square tilings were tested.

Once again, the results showed remarkably similar behaviour. The fitted power-law exponents were:

| Tiling | Power-law exponent $\alpha$ |
|---|---:|
| Trihexagonal | 0.5141 |
| Rhombitrihexagonal | 0.5074 |
| Snub square | 0.4904 |

All three values are extremely close to the standard random-walk value of $0.5$. The fits were also extremely strong, with all three having $R^2 > 0.999$.

I found this particularly interesting because these tilings have considerably more complicated local structures than a standard square lattice. Despite this, the large-scale behaviour of the random walk remains almost unchanged.

### Comparing the Three Cases

The progression from a standard random walk to uniform tilings and then non-uniform tilings therefore produces an interesting result.

As the geometry becomes more complicated:

$$
\text{standard lattice}
\rightarrow
\text{uniform tilings}
\rightarrow
\text{non-uniform tilings},
$$

The exact behaviour of the walk changes slightly, but the fundamental scaling relationship remains approximately

$$
r \propto \sqrt{n}.
$$

The main effect of changing the geometry appears to be changing the constants associated with the walk, rather than fundamentally changing its scaling exponent.

This means that, despite the increasingly complicated local geometry, random walks appear to exhibit a strong degree of universality at large scales.

### What This Suggests

The results suggest that the $\sqrt{n}$ behaviour of random walks is much more general than the standard random walk on a square lattice might initially suggest.

The local geometry clearly matters: the different tilings produce slightly different average distances and slightly different fitted exponents. However, these differences are small compared with the overall similarity in behaviour.

This raises a further question: **does this behaviour continue when the space itself is curved?**

The next possible extension of the investigation would therefore be to study random walks on genuinely curved surfaces, such as a sphere or other curved geometries. This would allow me to investigate whether the same large-scale behaviour survives when the underlying space is no longer flat.


---

# Overall Conclusion and Reflection

Having now investigated random walks on an unbounded plane, a finite torus, uniform tilings and non-uniform tilings, I can look back at the whole investigation and see how the different parts fit together.

The main thing I originally wanted to understand was how changing the geometry of the space would affect the behaviour of a random walk. I started with a fairly simple question about how far a random walker would move after a given number of steps, but this ended up taking me much further than I originally expected.

The first main result I found was the familiar

$$
r\propto\sqrt{n}.
$$

On an unbounded two-dimensional plane, the average distance from the starting point grows approximately like $\sqrt{n}$ rather than linearly with the number of steps. What I found really interesting was that this behaviour continued to appear when I changed the underlying geometry.

The torus showed that the size of the space does matter. For small tori, the walkers quickly became affected by the finite size of the space and the average distance reached a plateau. As the torus became larger, this effect was delayed and the measured exponent approached the theoretical value of $0.5$. The size 200 torus gave an exponent of

$$
0.5004,
$$

which is almost exactly the value expected for an unbounded two-dimensional random walk.

This led me to try and find a mathematical model for the effect of the finite torus. I proposed

$$
r(n,L)=CL\tanh\left(\frac{a\sqrt{n}}{L}\right),
$$

where $C$ and $a$ are constants that describe the behaviour of the walk, $n$ is the number of steps and $L$ is the size of the torus. I liked this model because it gives the two behaviours I was seeing in the simulations. For small $n$, the $\tanh$ term is approximately linear, giving the familiar $\sqrt{n}$ behaviour, while for large $n$ the function approaches a constant related to the size of the torus.

I then wanted to see whether the $\sqrt{n}$ behaviour was specific to a square lattice. I tested different uniform tilings and then moved on to non-uniform tilings, where the local geometry changes across the space. Despite the increasingly complicated geometries, the results were surprisingly similar.

The measured power-law exponents for the non-uniform tilings were

| Tiling | Power-law exponent $\alpha$ |
|---|---:|
| Trihexagonal | 0.5141 |
| Rhombitrihexagonal | 0.5074 |
| Snub square | 0.4904 |

All three are extremely close to the standard random-walk value of $0.5$. This suggests that changing the local geometry changes the exact behaviour of the walk slightly, but does not fundamentally change the relationship between distance and the number of steps.

I think I now have a better idea of why this happens. A random walk can be thought of as the sum of many individual random steps,

$$
S_n=X_1+X_2+\dots+X_n.
$$

If the steps have no overall directional bias and have a finite variance, their variances add approximately linearly with $n$. This means that the variance of the total displacement grows like $n$, so the typical size of the displacement grows like

$$
\sqrt{n}.
$$

This is closely connected to the **Central Limit Theorem (CLT)**. The CLT says that when many independent random variables are added together, their combined distribution tends towards a normal distribution, even if the individual variables are not normally distributed. In the case of a random walk, the individual steps are random, but after many steps their combined effect produces a predictable distribution centred around the starting point. The standard deviation of this distribution grows like $\sqrt{n}$, which is why the typical distance of the walker also follows this scaling.

This helps explain one of the things I found most interesting throughout the project: completely random local decisions can produce very predictable behaviour when viewed on a large enough scale. The exact geometry changes the details of the individual steps, but as long as the basic assumptions behind the CLT still hold, the overall statistical behaviour can remain surprisingly similar.

This also helps explain what I was seeing when I changed the tilings. Changing the geometry changes the exact directions and local paths available to the walker, so it can change the constant factor in the relationship. However, the results suggest that it does not change the fundamental $\sqrt{n}$ scaling. The local geometry can therefore have an effect on the details of the walk without changing its large-scale behaviour.

One of the things I found most interesting about this project was that the results were not always what I expected. I initially thought that making the geometry more complicated would lead to significantly different random-walk behaviour. Instead, the more complicated the tilings became, the more interesting it was that the same basic behaviour kept appearing.

This made me realise that sometimes the interesting part of a mathematical problem is not finding a completely different result, but understanding why apparently different systems produce the same one. In this case, the geometry clearly affects the local behaviour of the walker, but at a large enough scale the same statistical behaviour seems to emerge.

There are still many things I could investigate. For example, I would like to investigate whether the constants $C$ and $a$ in my torus model can be derived mathematically rather than fitted from simulations. I could also look at more unusual tilings, genuinely curved surfaces, or geometries where the assumptions behind the usual random-walk model no longer hold, and see whether the $\sqrt{n}$ behaviour eventually breaks down.

For now, though, I think this is a natural place to finish the investigation. I started by trying to understand a simple random walk and ended up exploring probability, geometry, tilings, numerical simulation and a possible mathematical model for the behaviour I observed. More importantly, the project has left me with more questions than I started with, which is probably my favourite part of it.

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
- [Wolfram Demonstrations — Random Walk Generated by the Digits of Pi](https://demonstrations.wolfram.com/RandomWalkGeneratedByTheDigitsOfPi/)
- [Grünbaum & Shephard — Tilings by Regular Polygons (1977)](https://doi.org/10.2307/2689529)
