# 🚂 Special Relativity Interactive Simulation

An interactive, physics-accurate web simulation explaining Time Dilation, Length Contraction, and the Relativity of Simultaneity. 

## 🌌 The Context
Albert Einstein's Special Theory of Relativity (1905) revolutionized our understanding of the universe, but its core concepts are notoriously counter-intuitive. Because humans do not move at a significant fraction of the speed of light (c), our brains are hardwired to believe that time and space are absolute. 

When students first encounter the idea that "moving clocks run slow" or "moving objects shrink," it often feels like a mathematical trick rather than physical reality. 

**The Goal of this Project:** To bridge the gap between abstract equations and visual intuition. This simulation translates Einstein's famous train thought experiments into a step-by-step interactive tutorial. By placing the user in the shoes of two different observers, it demonstrates how distance and time *must* physically warp to preserve the ultimate rule of the universe: the speed of light is constant for everyone.

## ✨ Key Physics Concepts Demonstrated
This engine does not use faked, pre-rendered animations. It runs a live physics state machine calculating exact Lorentz transformations (γ ≈ 22.37). 

1. **Length Contraction:** Watch a 200 light-hour train physically compress to 8.94 light-hours from the perspective of a stationary ground observer.
2. **Time Dilation:** Observe two synchronized clocks tick at vastly different rates as the "closing speed" of the light beam forces time to slow down for the moving passenger.
3. **The Relativity of Simultaneity:** The hardest paradox in physics. Using digital clocks bolted to the roof of the train, the simulation proves that a universal "now" does not exist. Two events that happen at the same time for one observer happen 8 days apart for another.
4. **Real-World Proof:** A concluding phase grounding the theoretical math in reality, explaining the 1977 CERN Muon Storage Ring experiment.

## 🛠️ Technical Details & Architecture
* **Stack:** Pure HTML5, CSS3, and Vanilla JavaScript. (Zero dependencies, no React/Vue, no external libraries).
* **Rendering:** Uses the native HTML `<canvas>` API for high-performance drawing and animation loops.
* **Physics Variables:**
  * Rest Length of Train: 200 light-hours
  * Velocity (v): 0.999c
  * Lorentz Factor (γ): 22.366
  * Contracted Length: ≈ 8.94 light-hours

## 🚀 How to Run Locally
Because this is a vanilla web project, it runs natively in any modern browser without a build step or local server.
1. Clone or download this repository.
2. Double-click `index.html` to open it in Chrome, Safari, Firefox, or Edge.
3. Click "Start the Simulation".

## 🤖 AI Collaboration
This project was built as an exercise in AI-assisted development, utilizing LLMs (Claude and Gemini) to architect the physics engine, UI, and tutorial state machine. See `PROMPTS.md` for a breakdown of the prompt engineering used to build this simulation.

## 📜 License
This project is open-source and available under the MIT License.