# TRINEX Computing

**Experimental research into hybrid BIT + TRIT computing.**

TRINEX is an experimental project exploring the possibility of using a conventional binary CPU together with a dedicated ternary accelerator for large parallel workloads.

The project is currently at the **software simulation stage**. No custom hardware has been built yet.

> **Important:** Current performance numbers are simulation results and should not be interpreted as proof of real-world hardware performance.

---

## Concept

The basic idea is to keep the conventional binary CPU for general-purpose tasks while using a separate TRIT-based accelerator for workloads that can be processed in parallel.

The goal is not to replace binary computing entirely.

Instead, TRINEX explores whether a **hybrid BIT + TRIT system** can provide better performance for specific large-data workloads.

---

## Why TRIT?

A balanced ternary system uses three states:

```text
-1
 0
+1
```

This provides three possible states per ternary digit (trit).

The project investigates whether these additional states can be useful when implemented as a specialized accelerator rather than as a direct replacement for conventional binary CPUs.

---

## Current Simulation Results

The current simulation models a binary CPU working together with a hypothetical TRIT accelerator.

For large workloads, the simulated system can process parts of the workload simultaneously.

### 256 MB workload

| TRIT efficiency | Simulated speedup |
| --------------: | ----------------: |
|        0.5× BIT |        **1.389×** |
|        1.0× BIT |        **1.737×** |
|        2.0× BIT |        **2.291×** |
|        5.0× BIT |        **3.387×** |

These numbers are based on a software model with simulated transfer bandwidth and processing characteristics.

They are **not hardware benchmark results**.

---

## Workload Size Matters

The simulation shows that the architecture becomes more interesting as the workload becomes larger.

For a TRIT accelerator with simulated performance equal to the BIT CPU:

| Workload |    Speedup |
| -------: | ---------: |
|     1 KB |     0.031× |
|    16 KB |     0.391× |
|    64 KB |     0.933× |
|     1 MB | **1.648×** |
|    16 MB | **1.731×** |
|    64 MB | **1.736×** |
|   256 MB | **1.737×** |

This suggests that communication and control overhead can dominate small workloads, while parallel processing becomes more valuable for larger workloads.

---

## Potential Advantages

### Parallel processing

The binary CPU and TRIT accelerator can work on different portions of a large workload simultaneously.

### Specialized acceleration

The TRIT processor does not need to replace the CPU. It can be designed specifically for workloads where its computational model is useful.

### Large-workload potential

The simulation suggests that larger blocks can better amortize communication and control overhead.

### Hybrid architecture

Conventional binary computing remains available for general-purpose tasks while the accelerator handles selected workloads.

### Research potential

The architecture can be tested progressively:

```text
Software simulation
        ↓
FPGA prototype
        ↓
Hardware prototype
        ↓
ASIC research
```

---

## Current Limitations

TRINEX is still an experimental project.

### No physical hardware yet

All current performance results come from software simulations.

### Binary test hardware

The current simulations run on conventional binary CPUs. They cannot reproduce the electrical characteristics of a real ternary processor.

### Transfer overhead

Communication between the CPU and accelerator can significantly reduce performance for small workloads.

### Real implementation is unknown

A real TRIT processor may have different:

* clock frequency
* memory bandwidth
* latency
* power consumption
* transistor requirements
* area
* thermal characteristics

### Simulation assumptions

The current model uses simplified assumptions for accelerator speed, transfer bandwidth and control overhead.

Real hardware could perform significantly better or worse.

---

## Current Status

**Stage:** Software research / simulation

### Completed

* [x] BIT vs TRIT software experiments
* [x] Multiple TRIT operating modes
* [x] Large-data benchmarks
* [x] Accuracy validation
* [x] Data integrity testing
* [x] Grouped TRIT experiments
* [x] Matrix workload experiments
* [x] BIT + TRIT parallel simulation
* [x] Workload-size comparison

### Planned

* [ ] More realistic communication model
* [ ] DMA simulation
* [ ] Double-buffering simulation
* [ ] Transfer/computation overlap
* [ ] FPGA prototype
* [ ] Hardware measurements
* [ ] Power-efficiency measurements

---

## Important Note

TRINEX does **not** claim that ternary computing is universally faster than binary computing.

The current research question is narrower:

> **Can a specialized TRIT accelerator working alongside a conventional binary CPU provide useful performance advantages on specific workloads?**

The current simulations suggest that this possibility is worth investigating further.

---

## Collaboration

The project is looking for people interested in:

* FPGA development
* digital logic
* CPU architecture
* computer architecture
* hardware acceleration
* ternary computing
* performance benchmarking

The project is currently focused on research and experimentation.

---

## Project Status

**Experimental — Hardware validation has not yet been performed.**

More results will be published as the project progresses.

