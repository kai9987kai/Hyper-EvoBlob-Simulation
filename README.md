
# Hyper EvoBlob Simulation — Research Edition

A browser-based artificial life and evolutionary simulation where autonomous organisms, called **EvoBlobs**, evolve neural brains, physical traits, memory, signalling behaviour, pheromone use, terrain adaptation, and species-level survival strategies.

This project is a single-file HTML simulation designed for experimentation with open-ended evolution, neural control, artificial ecosystems, speciation, emergent behaviour, and quality-diversity style exploration.

---

## Overview

**Hyper EvoBlob Simulation** creates a living digital ecosystem inside an HTML canvas. Each EvoBlob has:

- A recurrent neural network brain
- Mutable physical traits
- Energy, hunger, size, age, and memory
- Multi-directional sensors
- Pheromone and signal perception
- Evolved movement, turning, boosting, and signalling behaviour
- Species assignment based on genome distance
- Fitness sharing and evolutionary replacement

The simulation includes food, static threats, moving threats, terrain effects, slow zones, pheromone fields, and long-running evolutionary pressure.

---

## Key Features

### Artificial Life Simulation

- Autonomous EvoBlob agents
- Continuous movement and energy economy
- Food collection and threat avoidance
- Replenishing food resources
- Evasive food movement
- Static and moving threats
- Terrain effects including normal, slow, dense, and toxic regions
- Spatial hash grid for faster nearby-object lookup

### Neural Evolution

Each EvoBlob is controlled by a recurrent neural network with:

- Directional sensor inputs
- Internal state inputs
- Relative target inputs
- Pheromone inputs
- Signal inputs
- Memory nodes
- Evolved neural weights
- Evolved physical parameters

The neural outputs control:

- Thrust
- Turning
- Boost/shedding behaviour
- Signal emission
- Recurrent memory state

### Evolutionary System

The ecosystem uses genetic evolution with:

- Mutation
- Crossover
- Physical trait inheritance
- Neural weight inheritance
- Adaptive mutation rates
- Species-level selection
- Fitness sharing
- Stagnation penalties
- Elite preservation
- Inter-species crossover

### Speciation

EvoBlobs are grouped into species using genome-distance comparison. The species system tracks:

- Species ID
- Member count
- Average adjusted fitness
- Average raw fitness
- Best species fitness
- Stagnation age

### Research-Inspired Additions

The upgraded version includes experimental systems inspired by modern artificial life and evolutionary computation:

- Quality-Diversity style archive
- Behavioural niche tracking
- Lineage history
- Ecological event system
- Reproducible seeded simulation support
- Genome import/export
- Live fitness and population graphs
- Better debugging and runtime status feedback

---

## Controls

| Control | Description |
|---|---|
| Start | Begins or resumes the simulation |
| Stop | Pauses the simulation |
| Reset | Reinitializes the world and population |
| Speed | Changes simulation speed multiplier |
| +30 Food | Adds extra food to the ecosystem |
| +10 Threats | Adds additional threats |
| Vis Phero | Shows or hides pheromone fields |
| Vis Grid | Shows or hides the spatial grid |
| Simple Draw | Uses a faster simplified rendering mode |

---

## Visual Meaning

| Element | Meaning |
|---|---|
| Blue/Purple blobs | Living EvoBlob organisms |
| Green circles | Food |
| Red circles | Static threats |
| Purple circles | Moving threats |
| Brown regions | Slow zones |
| Green pheromone overlay | Food pheromone |
| Red pheromone overlay | Threat pheromone |
| Blue pheromone overlay | Signal pheromone |

---

## How to Run

No build system is required.

1. Download or clone this repository.
2. Open the HTML file in a modern browser.
3. Click **Start**.
4. Watch the ecosystem evolve.

Recommended browsers:

- Chrome
- Edge
- Firefox
- Brave

For best performance, use a desktop browser.

---

## File Structure

If using the single-file version:

```text
/
├── index.html
└── README.md
````

The simulation is fully contained in `index.html`.

---

## Recommended GitHub Setup

Rename the upgraded HTML file to:

```text
index.html
```

Then your repository can be hosted directly with GitHub Pages.

### Enable GitHub Pages

1. Go to repository **Settings**
2. Open **Pages**
3. Set source to your main branch
4. Select root directory
5. Save
6. Open the generated GitHub Pages URL

---

## Configuration

Most simulation settings are inside the `config` object in the JavaScript section.

Useful values to experiment with:

```js
populationSize: 200
initialFoodCount: 180
initialThreatCount: 50
initialMovingThreatCount: 20
baseMutationRate: 0.1
baseWeightMutationRate: 0.1
evaluationIntervalSteps: 1000
replacementPercentage: 0.15
speciationDistanceThreshold: 7.0
```

### Performance Tuning

If the simulation is slow, try reducing:

```js
populationSize
initialFoodCount
initialThreatCount
initialMovingThreatCount
numSensors
nnHiddenNodes
```

Or enable:

```text
Simple Draw
```

---

## Evolution Details

Each EvoBlob genome contains two major sections:

### Physical Traits

Examples include:

* Maximum speed
* Acceleration
* Turn rate
* Sensor range
* Maximum radius
* Energy efficiency
* Food energy gain
* Reproduction urge
* Pheromone sensitivity
* Signal sensitivity
* Boost multiplier
* Mutation rates

### Neural Traits

The neural genome stores:

* Input-to-hidden weights
* Hidden-to-output weights
* Hidden biases
* Output biases

These weights define how each EvoBlob reacts to the world.

---

## Fitness System

Fitness is influenced by:

* Staying alive
* Collecting food
* Avoiding threats
* Efficient energy use
* Niche competition
* Age balance
* Species-level performance

The simulation uses both raw fitness and adjusted fitness. Adjusted fitness is affected by nearby competitors and species allocation.

---

## Pheromones and Signals

EvoBlobs can leave environmental traces that other EvoBlobs may sense.

### Pheromone Types

| Type             | Purpose                      |
| ---------------- | ---------------------------- |
| Food pheromone   | Indicates successful feeding |
| Threat pheromone | Indicates danger or damage   |
| Signal pheromone | Social/communication signal  |

These decay over time and form temporary information fields across the world.

---

## Troubleshooting

### Start button does nothing

Use the fixed version of the file. The patched version includes:

* Immediate simulation tick after pressing Start
* Runtime error display
* Safer animation loop handling
* Renamed organism class to avoid conflicts with the browser’s native `Blob` object

### Simulation is very slow

Try:

* Lowering population size
* Enabling Simple Draw
* Turning off pheromone visualization
* Reducing the number of sensors
* Reducing neural hidden nodes

### Blobs die too quickly

Try increasing:

```js
initialEnergy
energyFromFoodBase
foodEnergyGain
initialFoodCount
```

Or lowering:

```js
energyDecayBase
energyLossFromThreat
energyLossFromMovingThreat
```

### Too many species appear

Increase:

```js
speciationDistanceThreshold
```

### Too few species appear

Decrease:

```js
speciationDistanceThreshold
```

---

## Ideas for Future Development

Possible next upgrades:

* Save/load full simulation state
* Replay mode
* Family tree visualizer
* Predator/prey organism types
* Sexual/asexual reproduction modes
* Environmental seasons
* Climate zones
* WebGL renderer
* Worker-thread simulation engine
* Neural network visualizer
* Behaviour clustering dashboard
* Graph export as CSV
* Tournament mode between saved genomes

---

## Educational Uses

This project can be used to explore:

* Artificial life
* Evolutionary algorithms
* Neural networks
* Genetic algorithms
* Emergent behaviour
* Speciation
* Ecosystem simulation
* Agent-based modelling
* Open-ended evolution
* Quality-diversity search

---

## License

You can use, modify, and expand this project freely.

Recommended license:

```text
MIT License
```

---

## Credits

Created as an experimental browser-based artificial life simulation.

The system combines neural control, mutation, speciation, memory, pheromones, terrain, and ecosystem dynamics into a single interactive HTML canvas project.

```
```
