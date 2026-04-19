# Prompt Visualization

Interactive 3D visualizations exploring how large language models constrain token generation probability spaces through different prompting and reasoning techniques.

## Visualizations

### [Chain of Thought — Sequential Probability Constraint](cot-viz.html)

Demonstrates how chain-of-thought reasoning works by visualizing probability cones in 3D space.

**Modes:**
- **Chain of Thought** - Each reasoning step anchors the next step's probability cone, progressively narrowing the solution space
- **Direct Answer** - The model jumps directly from the wide starting cone to an answer without intermediate reasoning steps
- **Broken Chain** - Shows what happens when a reasoning error occurs; subsequent steps anchor to the wrong location, compounding the error

**Key concept:** Each token/step in reasoning eliminates vast regions of the probability space, making subsequent outputs more constrained and reliable.

---

### [Embedding Space — Prompt Probability Cones](prompt-space-viz.html)

Visualizes how different prompting techniques narrow or broaden the probability cone that constrains token generation.

**Modes:**
- **Zero-Shot** - No examples; the model operates across the full probability space with a wide cone
- **One-Shot** - One example anchors the space; the cone narrows significantly
- **Few-Shot (3 Examples)** - Multiple coherent examples create constructive interference, dramatically narrowing the cone
- **Noisy Examples** - Conflicting examples cause destructive interference, sometimes making the cone wider than zero-shot

**Key concept:** Examples act as anchors in the embedding space. Coherent examples reinforce the intended output region; contradictory examples pull the model in conflicting directions.

---

## Controls

Both visualizations support:
- **Drag** to rotate the 3D view
- **Scroll** to zoom in/out
- **Buttons** to switch between different modes (visualizations are animated automatically)
- **Replay** button to restart the animation

## About

These visualizations illustrate fundamental concepts in large language model behavior:
- Probability cones represent the constrained region of possible next tokens
- Narrower cones = more predictable, constrained outputs
- Wider cones = higher variance, more diverse outputs
- Sequential constraints (chain of thought) and example-based constraints (few-shot) both work by anchoring and narrowing these probability regions
