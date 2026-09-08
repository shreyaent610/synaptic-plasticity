# Synaptic Plasticity — A Living Model of Short-Term Neural Memory

An interactive educational toy model demonstrating how temporary, activity-dependent synaptic strengthening can behave like short-term, context-specific memory.

## One-sentence claim

> Temporary Hebbian strengthening enables a neural network to form short-term, context-specific memories without backpropagation or new permanent weights, although these memories decay and can be overwritten by new activity.

## Why this project?

Normally, we think of a neural network as having fixed connections while it processes information. This project explores the alternative idea:

> **What if the connections themselves temporarily change as information arrives?**

In this simplified simulation, recent neural co-activity increases a temporary synaptic trace. The trace can support a short-lived memory, then decay or be reshaped by later activity.

## What is changing?

The project distinguishes between a **stable baseline network** and a **temporary synaptic trace**:

- **Neural activity:** changes when Context A or B is presented.
- **Temporary synaptic trace:** changes through activity-dependent Hebbian strengthening and decay.
- **Memory state:** represented by the strength of the temporary trace associated with each context.
- **Permanent parameters:** are not trained by backpropagation in this toy model; the demonstration updates transient state instead.

The important educational point is that the model's short-term memory is represented by **temporary changes in connection strength**, rather than by creating new permanent weights.

## Conceptual update rule

The interactive model uses the following simplified rule:

```text
trace_ij(t+1) = (1 - decay) * trace_ij(t)
             + learning * activity_i * activity_j
```

This is an educational abstraction of activity-dependent plasticity, not a reproduction of an official BDH implementation.

## Interactive experiment

Open `index.html` in a browser and use the **Interactive Synaptic Plasticity Lab**:

1. Adjust the Hebbian learning rate.
2. Adjust memory decay.
3. Adjust context similarity.
4. Adjust interference strength.
5. Select **Store Context A** to create a temporary trace.
6. Select **Advance Time** repeatedly to observe decay.
7. Store **Context B** to observe competition/interference.
8. Reset and repeat with different parameter combinations.

### Suggested experiments

| Experiment | Expected qualitative behaviour |
|---|---|
| High learning + low decay | Stronger, longer-lived temporary traces |
| High decay | Faster forgetting |
| High similarity + high interference | Greater competition between context memories |
| Low similarity + moderate interference | Greater context separation |

These are qualitative predictions of this toy simulation, not empirical claims about biological brains or the official BDH system.

## BDH framing

This project is **BDH-related conceptually**, using temporary state changes as the central educational idea. It is intentionally presented as a **simplified educational simulation and not the official BDH model**.

The module is meaningful because it makes the distinction between permanent learned parameters and transient activity-dependent state visible and experimentally manipulable.

### Limitation

The simulation is a small toy network with hand-designed activity patterns and simplified update/interference rules. It does **not** reproduce the full architecture, training procedure, biological complexity, or benchmark performance of BDH, and its behaviour should not be interpreted as evidence that the toy mechanism matches the human brain.

## Architecture

```text
                  ┌──────────────────────┐
                  │ Context / Pattern    │
                  └──────────┬───────────┘
                             │
                             ▼
                  ┌──────────────────────┐
                  │ Neural co-activity   │
                  └──────────┬───────────┘
                             │
                             ▼
              ┌──────────────────────────────┐
              │ Temporary Hebbian trace     │
              │ (transient connection state)│
              └──────────────┬───────────────┘
                             │
                    ┌────────┴────────┐
                    ▼                 ▼
             Recall / memory     Decay / interference
                    │                 │
                    └────────┬────────┘
                             ▼
                     Updated trace
```

## Repository structure

```text
synaptic-plasticity/
├── index.html       # Interactive website and simulation
├── README.md        # Project explanation and setup
├── REFERENCES.md   # References and scientific framing
├── LICENSE          # Project license
└── AI_DISCLOSURE.md # AI assistance disclosure
```

## Setup

### Option 1 — Run locally

No build system or dependencies are required.

1. Download or clone this repository.
2. Open `index.html` in a modern web browser.
3. Use the simulation controls and observe the network and memory metrics.

A simple local server can also be used:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000/` in your browser.

### Option 2 — GitHub Pages

The repository is configured to be suitable for GitHub Pages deployment from the `main` branch and repository root. After Pages is enabled, the public site is available at:

`https://shreyaent610.github.io/synaptic-plasticity/`

## Technology

- HTML5
- CSS3
- Vanilla JavaScript
- HTML Canvas for the network visualization
- No external runtime dependencies

## References

See [`REFERENCES.md`](REFERENCES.md) for the scientific and conceptual sources used to frame the project.

## AI disclosure

See [`AI_DISCLOSURE.md`](AI_DISCLOSURE.md). AI tools were used as development/writing assistance; the project is presented as an educational toy simulation rather than as an official implementation of BDH.

## License

This project is released under the MIT License. See [`LICENSE`](LICENSE).
