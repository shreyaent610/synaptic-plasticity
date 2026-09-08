# References

This project is an educational toy simulation. The references below provide background for the concepts used in the explanation; they do not imply that the implementation is an official reproduction of any cited model.

## Synaptic plasticity and Hebbian learning

1. Hebb, D. O. (1949). *The Organization of Behavior: A Neuropsychological Theory*. Wiley.
   - Foundational source for the idea commonly summarized as activity-dependent strengthening of connections.

2. Bliss, T. V. P., & Collingridge, G. L. (1993). A synaptic model of memory: long-term potentiation in the hippocampus. *Nature*, 361, 31–39.
   - Background on synaptic plasticity as a mechanism associated with memory.

## Short-term / transient synaptic dynamics

3. Mongillo, G., Barak, O., & Tsodyks, M. (2008). Synaptic theory of working memory. *Science*, 319(5869), 1543–1546.
   - Discusses how short-lived synaptic activity/state can support working-memory-like information storage.

## Brain-inspired / dynamic-memory framing

4. The project uses the user's stated BDH-related framing: temporary activity-dependent changes in connections can serve as a short-term memory mechanism. This repository deliberately labels its implementation as a **simplified educational simulation and not the official BDH model**.

## Important interpretation note

The equation implemented in `index.html` is a deliberately simplified pedagogical rule:

```text
trace_ij(t+1) = (1 - decay) * trace_ij(t)
             + learning * activity_i * activity_j
```

It should not be read as a complete biological model or as the exact update equation of an official BDH system.
